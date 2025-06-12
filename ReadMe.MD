🔧 3-Tier Application – Database Server Setup

1. Database Server (MySQL)

Port Number: 3306

🔹 Step-by-Step Installation & Configuration

✅ Switch to root user

sudo su -

✅ Install MySQL Server

dnf install mysql-server -y

✅ Start and Enable MySQL Service

systemctl start mysqld

systemctl status mysqld   # Check if it's running

systemctl enable mysqld   # Enable on boot

✅ Verify Port and Process

netstat -lntp          # Ensure port 3306 is open

ps -ef | grep mysql    # Verify MySQL process is running

🔐 Set Root Password

By default, MySQL uses the root user without a set password. Configure it securely:

mysql_secure_installation --set-root-pass ExpenseApp@1

📌 Note: Replace ExpenseApp@1 with your desired password.

🔄 Client-Server Clarification

Server Software --> mysql-server

Client Software --> Mysql

✅ Install MySQL Client

dnf install mysql -y

✅ Connecting to MySQL

	• From the same server (local):

Mysql
	
	• From a remote system (client):

mysql -h <IP_ADDRESS> -u root -p<password>


🗃️ Database Structure Overview

MySQL Server
  └── Schemas / Databases
        └── Tables

Example Use Cases:

user --> user information

posts --> blog posts

videos --> video metadata

📊 Useful MySQL Commands

SHOW DATABASES; 	            # List all databases

USE <database-name>;	        # Switch to specific database

SHOW TABLES;	                # List tables in selected DB

SELECT * FROM <table-name>;	    # Display all rows in a table
