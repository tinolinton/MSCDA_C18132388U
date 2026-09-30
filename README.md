# MSCDA SSIS ETL Project (C18132388U)

Individual SQL Server Integration Services (SSIS) project for the MSc Data Analytics coursework. It implements a parent/child ETL pattern that extracts data from the Northwind sample database and loads a retail data warehouse (`retail_db`).

## Packages

| Package | Purpose |
|---------|---------|
| `Parent.Package.dtsx` | Orchestrates the child packages and controls the run |
| `Child.Extracting.dtsx` | Extracts source data from Northwind |
| `Child.Staging.dtsx` | Loads extracted data into staging tables |
| `child.extract.dtsx` | Additional extraction routine |

Connection managers (`*.conmgr`) point at a local Northwind source and the `retail_db` destination on 127.0.0.1; `Project.params` holds the project-level parameters.

## Opening the project

1. Open `MSCDA_C18132388U.sln` in Visual Studio with the SSIS extension (SSDT).
2. Update the connection managers to point at your Northwind source and `retail_db` destination.
3. Run `Parent.Package.dtsx`; it executes the extract and staging children in order.
