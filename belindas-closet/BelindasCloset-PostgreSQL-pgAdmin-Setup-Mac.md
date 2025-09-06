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

< Add Image >

- Enter your device password and press **Enter**.  

< Add Image >


2. **Install PostgreSQL**:  
brew install postgresql@15

< Add Image >

3. **Start PostgreSQL service**:  
brew services start postgresql@15

< Add Image >


## Step 2: Install pgAdmin
Use Homebrew to install pgAdmin:  
brew install --cask pgadmin4

< Add Image >

## Step 3: Configure PostgreSQL

1. Open your terminal and type:  
psql -U postgres

< Add Image >

3. Set a password for the `postgres` user:  
\password postgres

- Enter your new password, then re-enter to confirm.  
- **Remember this password** – you’ll use it later.

< Add Image >


3. **Open pgAdmin**  
- Click **Servers**.  
- Enter the `postgres` password you just created.  

< Add Image >

## Step 4: Set Up the Project `.env`

1. Copy `.env.example` to `.env` in your project root:  
cp .env.example .env

2. Open `.env` and update `DATABASE_URL` with your PostgreSQL password:  
DATABASE_URL=postgresql://postgres:yourpassword@localhost:5432/belindas_closet

> ⚠️ **Note:** If your password has special characters, [URL-encode them](https://www.urlencoder.org/).
- `@` becomes `%40`
- `#` becomes `%23`
- `%` becomes `%25`
- `&` becomes `%26`


**Example**: Password Pass@123# becomes: 
  DATABASE_URL=postgresql://postgres:Pass%40123%23@localhost:5432/belindas_closet

< Add Image .env file open >

> ⚠️ **Important:** You **do not** need to manually create the `belindas_closet` database. The NestJS backend will create it automatically when you start the project.

---

## Step 5: Test PostgreSQL Connection

1. Check if PostgreSQL is running:  
brew services list | grep postgresql

< Add Image brew services list output>

2. Test connection from the command line:  
psql -h localhost -p 5432 -U postgres -d belindas_closet

< Add Image >

- If you see:  
belindas_closet=#

✅ Connection is successful.  
- Type `\q` to exit.  

< Add Image successful database connection>

---

## Step 6: Start the Project

1. **Install Dependencies** (from project root):  
npm install

< Add Image npm install output>


3. **Start Backend** (creates database tables automatically):  
cd belindas-closet-nestjs
npm run start:dev

< Add Image npm run start>


- Look for:  
[Nest] Application successfully started

< Add Image backend start output>


3. **Start Frontend** (open a new terminal):  
cd belindas-closet-nextjs
npm run dev

< Add Image npm run dev>

< Add Image front start output>

















