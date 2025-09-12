# PostgreSQL & pgAdmin Setup Guide (Mac)

This guide will walk you through installing PostgreSQL, setting up pgAdmin, connecting them to your **Belinda's Closet** project, and testing your setup.

---

## What You'll Install
- **PostgreSQL** – The database server that stores all application data  
- **pgAdmin** – A web-based tool to manage PostgreSQL databases visually  

---


## Step 1: Install PostgreSQL

### Option 1: Official Installer
1. Go to: [PostgreSQL Downloads for macOS](https://www.postgresql.org/download/macos/)  
2. Download and run the installer.  
3. Follow the installation steps (similar to Windows).

---

### Option 2: Homebrew (Recommended for Developers)
1. **Install Homebrew** (skip if already installed):  
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

![Homebrew Installation Prompt](images/image1.png)

- Enter your device password and press **Enter**.  

![Enter password for Homebrew](images/image2.png)

- You have successfully installed homebrew

![Homebrew installed confirmation](images/image3.png)


2. **Install PostgreSQL**:  
brew install postgresql@15

![Install PostgreSQL command](images/image4.png)

3. **Start PostgreSQL service**:  
brew services start postgresql@15

![Start PostgreSQL service](images/image5.png)


## Step 2: Install pgAdmin
Use Homebrew to install pgAdmin:  
brew install --cask pgadmin4

![Install pgAdmin command](images/image6.png)

## Step 3: Configure PostgreSQL

1. Open your terminal and type:  
psql postgres

![Open PostgreSQL in terminal](images/image7.png)

2. Set a password for the `postgres` user:  
\password postgres

![Set password for postgres](images/image8.png)

- Enter your new password, then re-enter to confirm.  
- **Remember this password** – you’ll use it later.

3. **Open pgAdmin**  
- Click **Servers**.  

![pgAdmin Servers list](images/image9.png)

- Enter the `postgres` password you just created.  

![Enter server password in pgAdmin](images/image10.png)

![pgAdmin connected to server](images/image11.png)

## Step 4: Set Up the Project `.env`

1. Check if a .env file exists in your project root (belindas-closet-nestjs).
  - If it exists: open it.
  - If it does not exist: copy `.env.example` to `.env` in your project root:  

            cp .env.example .env

2. Open the .env file in a code editor (e.g., VS Code, IntelliJ, Sublime).
  - Navigate to belindas-closet-nestjs
  - Open .env and paste your PostgreSQL password

![Open .env file in editor](images/image12.png)

3. Update DATABASE_URL with your PostgreSQL password:

DATABASE_URL=postgresql://postgres:yourpassword@localhost:5432/belindas_closet

> ⚠️ **Note:** If your password has special characters, [URL-encode them](https://www.urlencoder.org/).
- `@` becomes `%40`
- `#` becomes `%23`
- `%` becomes `%25`
- `&` becomes `%26`

**Example**: Password Pass@123# becomes:
  DATABASE_URL=postgresql://postgres:Pass%40123%23@localhost:5432/belindas_closet

![Update DATABASE_URL in .env](images/image13.png)

> ⚠️ **Important:** You **do not** need to manually create the `belindas_closet` database. The NestJS backend will create it automatically when you start the project.

---

## Step 5: Test PostgreSQL Connection

1. Check if PostgreSQL is running:  
brew services list | grep postgresql

![Check PostgreSQL service status](images/image14.png)

![Detailed PostgreSQL service list](images/image15.png)


2. Test connection from the command line:  
psql -h localhost -p 5432 -U postgres -d belindas_closet

![Test DB connection in terminal](images/image16.png)

- If you see:  
belindas_closet=#

✅ Connection is successful.  
- Type `\q` to exit.  

---

## Step 6: Start the Project

1. **Install Dependencies** (from project root):  
npm install

![npm install output](images/image17.png)


2. **Start Backend** (creates database tables automatically):  
cd belindas-closet-nestjs
npm run start:dev

![Start backend command output](images/image18.png)


- Look for:  
        Nest Application successfully started

![Backend successfully started](images/image19.png)

⚠️ Note: After starting the backend, refresh belindas_closet in pgAdmin to see the tables created automatically.

3. **Start Frontend** (open a new terminal):  
cd belindas-closet-nextjs
npm run dev

![Start frontend command output](images/image20.png)

![Frontend running in browser](images/image21.png)

## What's Next?

## Quick Reference

### Important Passwords

- **PostgreSQL User**: `postgres`
- **PostgreSQL Password**: [The one you set during installation]
- **Database Name**: `belindas_closet`

### Important URLs

- **Backend API**: http://localhost:3000/api
- **Frontend**: http://localhost:8082

### Useful Commands

# Connect to database via command line

psql -h localhost -p 5432 -U postgres -d belindas_closet

```

## Getting Help

If you encounter issues or want to learn more

4. **PostgreSQL Documentation**: [https://www.postgresql.org/docs/](https://www.postgresql.org/docs/)
5. **pgAdmin Documentation**: [https://www.pgadmin.org/docs/](https://www.pgadmin.org/docs/)

---

















