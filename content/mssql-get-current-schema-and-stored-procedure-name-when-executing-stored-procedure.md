+++
author = "Ganesh"
categories = ["SQL", "MSSQL"]
date = 2022-07-16T18:30:00Z
description = ""
image = ""
title = "[MSSQL] Get current Schema and Stored Procedure name when executing stored procedure"
type = "post"

+++
    ```sql
    -- Example
    CREATE PROC [dbo].[sp_TestSP]
    AS
    BEGIN
    	DECLARE @SCHEMA_NAME VARCHAR(8)	= OBJECT_SCHEMA_NAME(@@PROCID)          -- 'dbo'
    	DECLARE @SP_NAME VARCHAR(64)	= OBJECT_NAME(@@PROCID)                 -- 'sp_TestSP'
    
    	SELECT CONCAT('[', @SCHEMA_NAME, '].[', @SP_NAME, ']') AS [CurrentSP]   -- '[dbo].[sp_TestSP]'
    END;
    ```
    
    **Reference:**
    - [@@PROCID (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/functions/procid-transact-sql?view=sql-server-ver15)
    - [OBJECT_NAME (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/functions/object-name-transact-sql?view=sql-server-ver15)
    - [OBJECT_SCHEMA_NAME (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/functions/object-schema-name-transact-sql?view=sql-server-ver15)