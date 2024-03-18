# PhotoData-Synd-Photos.sqlite_Queries
This is a new repository used to provide updated SQLite queries for both Photos.sqlite databases. Most of the updated queries will work on both Photos.sqlite databases (PhotoData-Photos.sqlite and Syndication Photo Library-Photos.sqlite).

File paths of the Photos.sqlite used to create queries:
Photos.sqlite databases used can be found at the following file paths:

iOS Photos Application (com.apple.MobileSlideShow) database:

•	\private\var\mobile\Media\PhotoData\Photos.sqlite

iOS Syndication Photo Library (also known as Shared With You) database:

•	\private\var\mobile\Library\Photos\Libraries\Syndication.photoslibrary\database\Photos.sqlite

Abbreviations used to shorten query names:
Even though most of the updated queries will work on both Photos.sqlite databases (PhotoData-Photos.sqlite and Syndication Photo Library-Photos.sqlite), I have included a list of abbreviations and terms that will be found within the query names. These abbreviations and terms found within the query file names were used to describe the database file paths, the databases themselves, and artifacts within the query results.    

PhotoData and PhDaPs – If the term PhotoData or PhDaPs is within the query name, it indicates the query may be used on the Photos.sqlite located within: *\Media\PhotoData\Photos.sqlite 

Synd, SyndPL, and SyndPs – If the term Synd, SyndPL, and or SyndPs is within the query name, it indicates the query may be used on the Photos.sqlite located within: *\Libraries\Syndication.photoslibrary\database\Photos.sqlite

Albums – If Albums is listed within the query name, it indicates the query will contain album records and or assets records that are within albums. These query results could have multiple records for an individual asset.     

Assets – Is a term used to describe media files which have records being stored within a Photos.sqlite database.

Assets_Multi-Recs-PerAsset – If the term Assets_Multi-Recs-PerAsset is within the query name, it indicates the query results may include multiple records for each asset. There are multiple queries where this will apply and is required to conduct a detailed analysis of the asset.

Assets_Single-Rec_PerAsset - If the term Assets_Single-Rec_PerAsset is within the query name, it indicates the query results will include a single record for each asset. There are multiple queries where this will apply and other queries should be used to conduct a thorough analysis. These queries will allow the user to conduct a validation of the query results using the ZASSET Z_PK values and the raw data being stored in the ZASSETS table.

BASIC – If the term BASIC is within the query name, it indicates the query will contain limited columns/fields. These basic queries should be used to start your analysis, but please keep in mind that these query results may be missing critical data required for a complete analysis.

iCldLinks – Shared iCloud Links / Cloud Master Moments (CMM) are files shared via iCloud.com Links.

IntResou – If the term IntResou is within the query name, it indicates the query will contain table data from ZINTERNALRESOURCE table and the query results will contain multiple records for a single asset. 

KIND2 – If the term KIND2 is within the query name, it indicates the query will contain data from the ZGENERICALBUM table ZKIND field which contains the integer “2.” Based on my research this indicates the asset is within a Non-Shared Album. These query results may contain multiple records for an individual asset.

KIND1505 – If the term KIND1505 is within the query name, it indicates the query will contain data from the ZGENERICALBUM table ZKIND field which contains the integer “1505.” Based on my research this indicates the asset is within a Shared Album. These query results may contain multiple records for an individual asset.

MAIN – If the term MAIN is within the query name, it indicates the query will contain some of the primary data needed for analysis. 

MTD – If the term MTD is within the query name, it indicates the query results will be Missing Table Data. 

NoAssets – If the term NoAssets is within the query name, it indicates the query results do not contain asset data. 

REFERENCE – If the term REFERENCE is within the query name, it indicates the query will contain a large number of columns/fields and should be used when conducting a detailed analysis. Some of the reference queries may not run within SQLite tools because of the number of joins. Please use these reference queries to analyze how I have joined the tables and records. 

Research – If the term Research is within the query name, it indicates the query may or may not run within a SQLite tool. These queries are large and contain a vast number of columns/values and will have multiple records for each asset. These queries should be used when conducting research and detailed analysis.

SPL – If the term SPL is within the query name, it indicates the query will include results related to the iCloud Shared Photo Library.

SumRef – If the term SumRef is within the query name, it indicates the query results will contain the necessary data to conduct a standard analysis of the asset, but will be missing some data. SumRef stands for Summary Reference. These queries will contain more data than a BASIC query but will contain less data than a REFERENCE query.

SWY – If the term SWY is within the query name, it indicates the query will include results related to Shared with You assets and Syndication Photo Library.

withInvites – If the term withInvites is within the query name, it indicates the query results will include data related to a shared invite. These query results may contain multiple records for an individual asset.

with_Owner-Partic or withPartic – If these terms are used within the query name, it indicates the query results will contain data necessary to analyze the owner and participants of shared assets.
