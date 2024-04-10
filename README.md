# get-data-into-powerbi

The database content isn't important for this course, but if you want to use a database similar to the the one in the demos download and unzip the archive. 
The MobileSales archive is made up of 2 files. Make sure they are in the same folder before unzipping. The resulting script file is large (1.2Gb), 
so you will have to load from the command prompt using sqlcmd

(Alternatively you can download the MobileSales.bacpac file and import it into SQL Server Management Studio using Import Data-tier Application. This version of the database is significantly smaller than the one used in the demos, so the report numbers won;t be the same.)

Once unzipped open in text editor that can handle large files like Notepad++. On lines 7 and 9 edit the FILENAME path to place the database files in the correct 
location for your SQLServer setup.

USE [master]  
GO  
/****** Object:  Database [MobileSales]    Script Date: 15/06/2022 12:25:36 PM ******/  
CREATE DATABASE [MobileSales]  
 CONTAINMENT = NONE  
 ON  PRIMARY   
( NAME = N'MobileSales_Data', FILENAME = N'D:\MSSQL\Data\MobileSales.mdf' , SIZE = 1010176KB , MAXSIZE = UNLIMITED, FILEGROWTH = 10%)  
 LOG ON   
( NAME = N'MobileSales_Log', FILENAME = N'D:\MSSQL\Logs\MobileSales.ldf' , SIZE = 25480KB , MAXSIZE = 2048GB , FILEGROWTH = 10%)  
 WITH CATALOG_COLLATION = DATABASE_DEFAULT    
GO  

Open a command prompt and import the script with the command below
https://docs.microsoft.com/en-us/sql/ssms/scripting/sqlcmd-use-the-utility?view=sql-server-ver16


sqlcmd -S ComputerName\InstanceName -i C:\path to unzipped script file\MobileSales.sql

