## Naming Convention and T-SQL Code Style
Official Reference and useful links:
- [Transact-SQL Formatting Standards](https://www.red-gate.com/simple-talk/sql/t-sql-programming/transact-sql-formatting-standards-coding-styles/) (by Robert Sheldon)
- [How I Write SQL, Part 1: Naming Conventions](https://launchbylunch.com/posts/2014/Feb/16/sql-naming-conventions/)
- [Subjectivity Naming Standards](https://blogs.sentryone.com/aaronbertrand/subjectivity-naming-standards/) (by Aaron Bertrand)
- [Writing Readable SQL](https://www.codeproject.com/Articles/126380/Writing-Readable-SQL) (by Red Gate)
- [SQL Style Guide](https://www.sqlstyle.guide/) (by Simon Holywell)
- [sys.objects](https://docs.microsoft.com/en-us/sql/relational-databases/system-catalog-views/sys-objects-transact-sql?view=sql-server-2017)
- [CLR Stored Procedures](https://docs.microsoft.com/en-us/previous-versions/sql/sql-server-2008/ms131094(v=sql.100))
- [Sql Coding Style](http://wiki.c2.com/?SqlCodingStyle)
- [SQL Server Code Review Checklist for Developers](https://www.sqlshack.com/sql-server-code-review-checklist-for-developers/) (by Samir Behara)

### MS SQL Object Naming Convention
| <sub>Object</sub>	| <sub>Code</sub>	| <sub>Notation</sub>	| <sub>Length</sub>	| <sub>Plural</sub>	| <sub>Prefix</sub>	| <sub>Abbreviation</sub>	| <sub> Mask </sub>	 | <sub>Example</sub> |
| ------ | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | 					
| <sub>Database</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>30</sub>	| <sub>No</sub>	| <sub>No</sub>	| <sub>Yes</sub>	| <sub>[A-z]</sub>	 | <sub>MyDatabase</sub> |
| <sub>Database Trigger</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>50</sub>	| <sub>No</sub>	| <sub>TR_</sub>	| <sub>Yes</sub>	| <sub>[A-z]</sub>	 | <sub>TR_CheckLogin</sub> |
| <sub>Schema</sub>	| <sub></sub>	| <sub>lowercase</sub>	| <sub>30</sub>	| <sub>No</sub>	| <sub>No</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>myschema</sub> |
| <sub>File Table</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>FT_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>FT_MyTable</sub> |
| <sub>Global Temporary Table</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>117</sub>	| <sub>No</sub>	| <sub>No</sub>	| <sub>Yes</sub>	| <sub>##[A-z][0-9]</sub>	 | <sub>##MyTable</sub> |
| <sub>Local Temporary Table</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>116</sub>	| <sub>No</sub>	| <sub>No</sub>	| <sub>Yes</sub>	| <sub>#[A-z][0-9]</sub>	 | <sub>#MyTable</sub> |
| <sub>Table</sub>	| <sub>U</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>No</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>MyTable</sub> |
| <sub>Table Column</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>No</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>MyColumn</sub> |
| <sub>Table Default Values</sub>	| <sub>D</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>DF_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>DF_MyTable_MyColumn</sub> |
| <sub>Table Check Column Constraint</sub>	| <sub>C</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>CС_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>CС_MyTable_MyColumn</sub> |
| <sub>Table Check Table Constraint</sub>	| <sub>C</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>TС_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>TС_MyTable_MyColumn_AnotherColumn</sub> |
| <sub>Table Primary Key</sub>	| <sub>PK</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>PK_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>PK_MyTableID</sub> |
| <sub>Table Alternative Key</sub>	| <sub>UQ</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>AK_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>AK_MyTable_MyColumn_AnotherColumn</sub> |
| <sub>Table Foreign Key</sub>	| <sub>F</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>FK_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>FK_MyTable_ForeignTableID</sub> |
| <sub>Table Clustered Index</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>IDX_C_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>IDX_C_MyTable_MyColumn_AnotherColumn</sub> |
| <sub>Table Non Clustered Index</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>IDX_NC_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>IDX_NC_MyTable_MyColumn_AnotherColumn</sub> |
| <sub>Table Trigger</sub>	| <sub>TR</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>TR_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>TR_MyTable_LogicalName</sub> |
| <sub>View</sub>	| <sub>V</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>VW_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>VW_LogicalName</sub> |
| <sub>Stored Procedure</sub>	| <sub>P</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>usp_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>usp_LogicalName</sub> |
| <sub>Scalar User-Defined Function</sub>	| <sub>FN</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>udf_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>udf_FunctionLogicalName</sub> |
| <sub>Table-Valued Function</sub>	| <sub>FN</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>tvf_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>tvf_FunctionLogicalName</sub> |
| <sub>User-Defined Table Types</sub>	| <sub>TT</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>TT_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>TT_LogicalName</sub> |
| <sub>Synonym</sub>	| <sub>SN</sub>	| <sub>camelCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>sy_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>sy_logicalName</sub> |
| <sub>Sequence</sub>	| <sub>SO</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>sq_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>sq_TableName</sub> |
| <sub>CLR Assembly</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>CA</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>CALogicalName</sub> |
| <sub>CLR Stored Procedures</sub>	| <sub>PC</sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>pc_</sub>	| <sub>Yes</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>pc_CAName_LogicalName</sub> |
| <sub>CLR Scalar User-Defined Function</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>cudf_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>cudf_CAName_LogicalName</sub> |
| <sub>CLR Table-Valued Function</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>ctvf_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>ctvf_CAName_LogicalName</sub> |
| <sub>CLR User-Defined Aggregates</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>ca_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>ca_CAName_LogicalName</sub> |
| <sub>CLR User-Defined Types</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>ct_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>ct_CAName_LogicalName</sub> |
| <sub>CLR Triggers</sub>	| <sub></sub>	| <sub>PascalCase</sub>	| <sub>128</sub>	| <sub>No</sub>	| <sub>ctr_</sub>	| <sub>No</sub>	| <sub>[A-z][0-9]</sub>	 | <sub>ctr_CAName_LogicalName</sub> |

### T-SQL Code Style
MS SQL T-SQL Best Practices and Programming Guidelines:
- Delimiters: spaces (not tabs).
- All finished expressions should have `;` at the end.
- The first argument in `SELECT` expression should be on the next line with it (see ex below).
- Arguments are divided by line breaks, commas should be placed before an argument (see ex below).
```
SELECT 
  FirstName
  ,LastName 
FROM …
```
- Use `TOP` function with brackets because `TOP` has supports use of an expression, such as `(@Rows*2)`, or a subquery:
` SELECT TOP(100) LastName …. `
Also `TOP` without brackets does not work with ` UPDATE ` and ` DELETE ` statements.
```
-- Not working without ()
DECLARE @n int = 1;
SELECT TOP@n name FROM sys.objects;
```
- Keywords should be in UPPERCASE
- Data types declaration should be in lowercase
- ` FROM, WHERE, INTO, JOIN, GROUP BY, ORDER BY ` expressions should be aligned so, that all their arguments are placed under each other 
```
WITH CTE_MyCTE AS (
    SELECT 
         t1.Value1 AS Val1
         ,t1.Value2 AS Val2
         ,t2.Value3 AS Val3
     FROM dbo.Table AS t1
     INNER JOIN dbo.Table2 AS 2t ON t1.Value1 = t2.Value1
     WHERE t1.Value1 > 1
       AND t2.Value2 >= 101
)
SELECT 
     t1.Value1 AS Val1
     ,t1.Value2 AS Val2
     ,t2.Value3 AS Val3
  INTO #TempTable
  FROM CTE_MyCTE AS cte
 ORDER BY t2.Value2;
```
- All objects must used with schema names but without database and server name: ` FROM dbo.Table ` (
if it is not required in a specific case)
- Avoid using ` INSERT INTO ` a permanent table with ` ORDER BY `
- Avoid using shortname (`wk, yyyy, d ` etc.) with date/time operations, use full names: `month, day, year`
- Parameters name should be in **camelCase**: `@textParam`
- Dont duplicate ` DECLARE ` block, also dont use shortname for variables
```
DECLARE
@userName nvarchar(250), --but not @un or @n
@userAge int; --but not @ua or @a
```
- The procedure or function should begin with parameter check
- Create sp_ procedures only in master database - SQL Server will always scan through the system catalog first
- Always use `BEGIN TRY` and `BEGIN CATCH`, ALSO `BEGIN … END` AFTER `IF` or `ELSE`
- Always use /* */ instead inline comment --
- Use `SET NOCOUNT ON;` for stops the message that shows the count of the number of rows affected by a Transact-SQL statement (for stored proc)
