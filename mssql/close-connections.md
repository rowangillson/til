# Drop all connections to a database
    use master
    ALTER DATABASE [database] SET SINGLE_USER WITH ROLLBACK IMMEDIATE 

    --do you stuff here 

    ALTER DATABASE [iLM.Demo] SET MULTI_USER