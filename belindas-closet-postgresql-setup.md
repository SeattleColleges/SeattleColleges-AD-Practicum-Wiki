# Belinda’s Closet PostgreSQL Setup Guide

## Overview
This document provides step-by-step instructions to set up a PostgreSQL database for the Belinda’s Closet project.

---

## Prerequisites
Before starting, ensure you have the following installed:

- PostgreSQL (latest version)
- pgAdmin or any PostgreSQL client

---

## Step 1: Install PostgreSQL
1. Download PostgreSQL from the official website: https://www.postgresql.org/download/
2. Run the installer and follow the setup instructions.
3. Set a strong password for the default `postgres` user.
4. Keep note of the port number (default: 5432).

---

## Step 2: Verify Installation
After installation:
- Open pgAdmin or terminal
- Connect using:
  - Username: `postgres`
  - Password: **********
  - Port: `5432`

---

## Step 3: Create Database
Run the following command to create a new database:

```sql
CREATE DATABASE belindas_closet;