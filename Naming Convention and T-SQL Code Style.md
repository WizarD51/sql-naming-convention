## Naming Convention and T-SQL Code Style
Official Reference and useful links

### MS SQL Object Naming Convention

| Object |	Code |	Notation |	Length |	Plural |	Prefix |	Abbreviation | Mask |	Example |
| ------ | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | 
| Database	 | 	 | PascalCase	 | 30	 | No	 | No	 | Yes	 | [A-z]	 | MyDatabase |
| Database Trigger	 | 	 | PascalCase	 | 50	 | No	 | TR_	 | Yes	 | [A-z]	 | TR_CheckLogin |
| Schema	 | 	 | lowercase	 | 30	 | No	 | No	 | Yes	 | [A-z][0-9]	 | myschema |
| File Table	 | 	 | PascalCase	 | 128	 | No	 | FT_	 | Yes	 | [A-z][0-9]	 | FT_MyTable |
| Global Temporary Table	 | 	 | PascalCase	 | 117	 | No	 | No	 | Yes	 | ##[A-z][0-9]	 | ##MyTable |
| Local Temporary Table	 | 	 | PascalCase	 | 116	 | No	 | No	 | Yes	 | #[A-z][0-9]	 | #MyTable |
| Table	 | U	 | PascalCase	 | 128	 | No	 | No	 | Yes	 | [A-z][0-9]	 | MyTable |
| Table Column	 | 	 | PascalCase	 | 128	 | No	 | No	 | Yes	 | [A-z][0-9]	 | MyColumn |
| Table Default Values	 | D	 | PascalCase	 | 128	 | No	 | DF_	 | Yes	 | [A-z][0-9]	 | DF_MyTable_MyColumn |
| Table Check Column Constraint	 | C	 | PascalCase	 | 128	 | No	 | CС_	 | Yes	 | [A-z][0-9]	 | CС_MyTable_MyColumn |
| Table Check Table Constraint	 | C	 | PascalCase	 | 128	 | No	 | TС_	 | Yes	 | [A-z][0-9]	 | TС_MyTable_MyColumn_AnotherColumn |
| Table Primary Key	 | PK	 | PascalCase	 | 128	 | No	 | PK_	 | Yes	 | [A-z][0-9]	 | PK_MyTableID |
| Table Alternative Key	 | UQ	 | PascalCase	 | 128	 | No	 | AK_	 | Yes	 | [A-z][0-9]	 | AK_MyTable_MyColumn_AnotherColumn |
| Table Foreign Key	 | F	 | PascalCase	 | 128	 | No	 | FK_	 | Yes	 | [A-z][0-9]	 | FK_MyTable_ForeignTableID |
| Table Clustered Index	 | 	 | PascalCase	 | 128	 | No	 | IDX_C_	 | Yes	 | [A-z][0-9]	 | IDX_C_MyTable_MyColumn_AnotherColumn |
| Table Non Clustered Index	 | 	 | PascalCase	 | 128	 | No	 | IDX_NC_	 | Yes	 | [A-z][0-9]	 | IDX_NC_MyTable_MyColumn_AnotherColumn |
| Table Trigger	 | TR	 | PascalCase	 | 128	 | No	 | TR_	 | Yes	 | [A-z][0-9]	 | TR_MyTable_LogicalName |
| View	 | V	 | PascalCase	 | 128	 | No	 | VW_	 | No	 | [A-z][0-9]	 | VW_LogicalName |
| Stored Procedure	 | P	 | PascalCase	 | 128	 | No	 | usp_	 | No	 | [A-z][0-9]	 | usp_LogicalName |
| Scalar User-Defined Function	 | FN	 | PascalCase	 | 128	 | No	 | udf_	 | No	 | [A-z][0-9]	 | udf_FunctionLogicalName |
| Table-Valued Function	 | FN	 | PascalCase	 | 128	 | No	 | tvf_	 | No	 | [A-z][0-9]	 | tvf_FunctionLogicalName |
| User-Defined Table Types	 | TT	 | PascalCase	 | 128	 | No	 | TT_	 | No	 | [A-z][0-9]	 | TT_LogicalName |
| Synonym	 | SN	 | camelCase	 | 128	 | No	 | sy_	 | No	 | [A-z][0-9]	 | sy_logicalName |
| Sequence	 | SO	 | PascalCase	 | 128	 | No	 | sq_	 | No	 | [A-z][0-9]	 | sq_TableName |
| CLR Assembly	 | 	 | PascalCase	 | 128	 | No	 | CA	 | Yes	 | [A-z][0-9]	 | CALogicalName |
| CLR Stored Procedures	 | PC	 | PascalCase	 | 128	 | No	 | pc_	 | Yes	 | [A-z][0-9]	 | pc_CAName_LogicalName |
| CLR Scalar User-Defined Function	 | 	 | PascalCase	 | 128	 | No	 | cudf_	 | No	 | [A-z][0-9]	 | cudf_CAName_LogicalName |
| CLR Table-Valued Function	 | 	 | PascalCase	 | 128	 | No	 | ctvf_	 | No	 | [A-z][0-9]	 | ctvf_CAName_LogicalName |
| CLR User-Defined Aggregates	 | 	 | PascalCase	 | 128	 | No	 | ca_	 | No	 | [A-z][0-9]	 | ca_CAName_LogicalName |
| CLR User-Defined Types	 | 	 | PascalCase	 | 128	 | No	 | ct_	 | No	 | [A-z][0-9]	 | ct_CAName_LogicalName |
| CLR Triggers	 | 	 | PascalCase	 | 128	 | No	 | ctr_	 | No	 | [A-z][0-9]	 | ctr_CAName_LogicalName |

### T-SQL Code Style
MS SQL T-SQL Best Practices and Programming Guidelines
