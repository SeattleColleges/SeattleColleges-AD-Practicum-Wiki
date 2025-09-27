# PostgreSQL & pgAdmin Setup Guide (Windows)

This guide will walk you through installing PostgreSQL, setting up pgAdmin, connecting them to your **Belinda's Closet** project, and testing your setup.

---

## What You'll Install
- **PostgreSQL** – The database server that stores all application data  
- **pgAdmin** – A web-based tool to manage PostgreSQL databases visually  

---

## Step 1: Install PostgreSQL

1. Go to: [PostgreSQL Downloads](https://www.postgresql.org/download/)  
2. Select **Windows**.  

![Select Windows](images/win.image1.png)

3. Select the installer.  

![Select Installer](images/win.image2.png)

4. Choose the latest and appropriate installer for Windows.  

![Choose Installer](images/win.image3.png)

5. Run the installer from your **Downloads** directory.  

![Run Installer](images/win.image4.png)

6. If prompted, allow the app to run → click **OK**.  

7. Click **Next**.  

![Click Next](images/win.image5.png)

8. Choose installation directory or leave default.  

![Choose Directory](images/win.image6.png)

9. Click **Next** to install all selected components (you may choose only PostgreSQL Server + pgAdmin).  

![Select Components](images/win.image7.png)

10. Choose your **Data Directory** or proceed with default (this is where all databases will be stored).  

![Choose Data Directory](images/win.image8.png)

11. **Set a password** for the `postgres` superuser.  
⚠️ Remember this password – you’ll use it multiple times (psql shell, pgAdmin, project).  

![Set Password](images/win.image9.png)

12. Leave the default port (**5432**).  

![Default Port](images/win.image10.png)

13. Leave the default location.  

![Default Location](images/win.image11.png)

14. Review settings → click **Next**.  

![Review Settings](images/win.image12.png)

15. Click **Next** to install.  

![Start Install](images/win.image13.png)

16. Wait for installation to complete (may take a few minutes).  

![Installing](images/win.image14.png)

17. Once done, click **Finish**.  

![Finish Install](images/win.image15.png)

18. From the dropdown list, select **PostgreSQL 17 (x64)** on port 5432.  

![Select PostgreSQL](images/win.image16.png)

19. Select the already installed database driver and click **Next**.  

![Select Driver](images/win.image17.png)

20. Leave default options and click **Next**.  

![Default Options](images/win.image18.png)

21. Continue installation (skip if already installed, but let it finish to confirm all components).  

![Continue Install](images/win.image19.png)

22. Click **Finish**.  

![Finish Setup](images/win.image20.png)

✅ You have now installed PostgreSQL.  
👉 Restart your machine to complete setup.  

---

## Step 2: pgAdmin Setup

pgAdmin is a web-based interface to manage PostgreSQL databases visually.

### 2.1 Install pgAdmin (if not installed)
1. Go to: [pgAdmin Downloads](https://www.pgadmin.org/download/pgadmin-4-windows/)  
2. Download the Windows installer and run it.  
3. Follow the installer steps (Next → Accept defaults → Install → Finish).  

### 2.2 Launch pgAdmin
1. Open **pgAdmin** from the Start menu.  
2. The first time, it will ask you to set a **Master Password**. This is separate from the PostgreSQL password and secures pgAdmin.  
3. Enter the password you set for the `postgres` user during PostgreSQL installation when connecting to the server.

## Step 3. Create Database

## Option 1: Create Database (psql shell)

1. Open **psql shell**.  
2. Press **Enter** for defaults until prompted for password.  

![psql Shell](images/win.image21.png)
![psql Shell](images/win.image22.png)
![psql Shell](images/win.image23.png)
![psql Shell](images/win.image24.png)

3. Enter the password you set during installation.  

![Enter Password](images/win.image25.png)

✅ Now you’re connected

![You are now Connected](images/win.image26.png)

## Option 2: Create Database (pgAdmin)

1. Launch **pgAdmin**.  
2. Click on **servers** and enter password

![Enter Password](images/win.image27.png)

3. Right-click on **Databases** → **Create** → **Database**.  

![Create Database](images/win.image28.png)

4. Name your database:  belindas_closet


5. Click **Save**.  

![Save Database](images/win.image29.png)

✅ Database is now created.

---

## Step 4: Set Up the Project `.env`

1. Check if a .env file exists in your project root (belindas-closet-nestjs).
  - If it exists: open it.
  - If it does not exist: copy `.env.example` to `.env` in your project root:  

            cp .env.example .env

2. Open the .env file in a code editor (e.g., VS Code, IntelliJ, Sublime).
  - Navigate to belindas-closet-nestjs
  - Open .env and paste your PostgreSQL password

![Open .env file in editor](images/win.image26.png)

3. Update DATABASE_URL with your PostgreSQL password:

DATABASE_URL=postgresql://postgres:yourpassword@localhost:5432/belindas_closet

> ⚠️ **Note:** If your password has special characters, [URL-encode them](https://www.urlencoder.org/).
- `@` becomes `%40`
- `#` becomes `%23`
- `%` becomes `%25`
- `&` becomes `%26`

**Example**: Password Pass@123# becomes:
  DATABASE_URL=postgresql://postgres:Pass%40123%23@localhost:5432/belindas_closet

![Update DATABASE_URL in .env](images/win.image27.png)

> ⚠️ **Important:** You **do not** need to manually create the `belindas_closet` database. The NestJS backend will create it automatically when you start the project.

---

## Step 5: Test PostgreSQL Connection

1. Check if PostgreSQL is running:

pg_isready

2. Test connection from the command line:

psql -h localhost -p 5432 -U postgres -d belindas_closet

If you see:

belindas_closet=#

✅ Connection is successful.

Type \q to exit.

---

## Step 6: Start the Project

1. **Install Dependencies** (from project root):

npm install

2. **Start Backend** (creates database tables automatically):

cd belindas-closet-nestjs
npm run start:dev

Look for:
Nest Application successfully started

⚠️ After starting the backend, refresh belindas_closet in pgAdmin to see the tables created automatically.

3. **Start Frontend** (open a new terminal):

cd belindas-closet-nextjs
npm run dev

✅ The frontend will run in your browser.

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