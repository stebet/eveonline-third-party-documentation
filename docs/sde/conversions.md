# Conversions
## Intoduction

Originally, the SDE was provided solely as an MS SQL server backup file. As the SDE is commonly used in environments where MS SQL is not available or would be overkill, a number of people maintain conversion routines and copies, to make it available in a more useful format.

As more formats were introduced, containing extra data, these routines were expanded to bring the data back into a single format.

As the various methods for conversion result in differing versions, with different layouts of data, conversions will be listed by the primary maintainer.

## [EVE SDE Database Builder - by Zifrian](https://forums.eveonline.com/default.aspx?g=posts&t=500859)
EVE SDE Database Builder is a Windows app that lets users import the SDE 6 different database types. Additionally, users can customize the import by language type and selecting specific SDE yaml files to import or ignore.

Key features:
* Imports all YAML files in about 30 minutes (the universe files take about 23 minutes alone).
* Allows the selection of specific YAML files so users don’t have to import or build the entire database each time.
* Imports the SDE YAML files into Microsoft Access, SQLite, and CSV files with the option to save CSV to SSV – Semi-colon separated values with European decimal format (10.000,00) for use in Excel by non-US decimal format users.
* Imports the SDE YAML files into local servers for Microsoft SQL Server, PostgreSQL, and MySQL. To use these import types, you need to have a local server installed on your machine to connect to.
* Settings to import tables with translated fields for English, French, German, Japanese, Chinese, and Russian. When a field is translatable, the program will import the selected language.
* Threaded processing allows for increasing import times. Users can select to use maximum threads (no limit) or a number of 1-24 threads depending on their system. Users can set the threads in the File menu.
* Contains an updater function to update the program when changes are uploaded to GitHub. 

Main links for the application:
* [Screenshot of the program](http://i.imgur.com/iQIyUrw.png)
* [Binaries for installing the program](https://github.com/EVEIPH/EVE-SDE-Database-Builder/raw/master/Latest%20Files/EVE%20SDE%20Database%20Builder%20Install.zip)
* [Github for the code](https://github.com/EVEIPH/EVE-SDE-Database-Builder)
* [SQL Schema, which is updated to new data and changes CCP has added](https://github.com/EVEIPH/EVE-SDE-Database-Builder/blob/master/Latest%20Files/EVESDEDB_Schema.sql)

## [Desmont McCallock](https://forums.eveonline.com/profile/Desmont%20McCallock)

[Conversion Tool](https://forums.eveonline.com/default.aspx?g=posts&m=6168357)

Desmont provides a tool to run on Windows, to merge the other data back into the SQL Server SDE, and to convert into a variety of formats, either at full database, or individual tables.

* SQL Server
* MySQL
* Postgres
* MS Access
* SQLite
* CSV

This tool converts to a format close to the SDE as it was before CCP changed how it was produced -splitting it sqlserver, yaml and sqlite files- with blueprint information going into ramTypeRequirements. As such it should be more compatible with some older tools.

## [Steve Ronuken - Fuzzwork Enterprises](https://www.fuzzwork.co.uk/dump/)

Steve provides conversions of the SDE for download, in the following formats:

* SQL Server
* MySQL (both [full database](https://www.fuzzwork.co.uk/dump/mysql-latest.tar.bz2) and [single table](https://www.fuzzwork.co.uk/dump/latest/))
* [Postgres](https://www.fuzzwork.co.uk/dump/postgres-latest.dmp.bz2) (both public schema, and evetools schema)
* [SQLite](https://www.fuzzwork.co.uk/dump/sqlite-latest.sqlite.bz2)
* [CSV/XLS](https://www.fuzzwork.co.uk/dump/latest/) (depending on row counts)

.bz2 files can be unzipped with 7zip, on Windows.
Historical copies are kept available. When data is migrated into alternate formats, it's generally copied back into the old table format, but not always. The industry data, for example, is in a number of new industryActivity tables. While allowing for greater flexibility, this can break some older tools.

Conversion is performed by:

* [https://github.com/fuzzysteve/SDE-loaders](https://github.com/fuzzysteve/SDE-loaders) to pull everything into SQL Server
* MySQL Migration Wizard in the Mysql Workbench to convert to MySQL
* pgloader to pull the mysql data into postgres
* mysql2sqlite.sh to pull the mysql data into sqlite
* DBIx::Dump to export the individual files.
