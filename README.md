# PhotoData-Synd-Photos.sqlite_Queries
PhotoData – Photos.sqlite and Syndication Photo Library – Photos.sqlite Query Updates

Hello again, if you have not already noticed, I moved the queries around on my GitHub in preparation of updates based on new research. The research will be published at a later time. Over the years I have had a few requests to provide additional information about each query and how each one can be used for a particular type of artifact. I have tried this once before but received some feedback that there were too many queries. Given the findings of my recent research, I have once again created several different queries that might assist with getting better defined results. The updates have been based on iOS versions 15.8.2 – 17.3.1, but some of these updates have been constructed to work with older iOS versions.  

iOS Versions used to create queries:
17.3.1		16.7.4		15.8.2		14.7		13.4.1		12.4.8		11.1.2
17.2.1		16.1.2		15.6		14.3
17.0		16.1		15.4.1		

File paths of the Photos.sqlite used to create queries:
Photos.sqlite databases used can be found at the following file paths:

iOS Photos Application (com.apple.MobileSlideShow) database:
•	\private\var\mobile\Media\PhotoData\Photos.sqlite

iOS Syndication Photo Library (also known as Shared with You) database:
•	\private\var\mobile\Library\Photos\Libraries\Syndication.photoslibrary\database\Photos.sqlite

Abbreviations used to shorten query names:
Even though most of the updated queries will work on both Photos.sqlite databases (PhotoData-Photos.sqlite and Syndication Photo Library-Photos.sqlite), I have included a list of abbreviations and terms that will be found within the query names. These abbreviations and terms found within the query file names were used to describe the database file paths, the databases themselves, and artifacts within the query results.    

PhotoData and PhDaPs – If the term PhotoData or PhDaPs is within the query name, it indicates the query may be used on the Photos.sqlite located within: 
•	*\Media\PhotoData\Photos.sqlite 

Synd, SyndPL, and SyndPs – If the term Synd, SyndPL, and or SyndPs is within the query name, it indicates the query may be used on the Photos.sqlite located within:
•	*\Libraries\Syndication.photoslibrary\database\Photos.sqlite

Albums – If Albums is listed within the query name, it indicates the query will contain album records and or assets records that are within albums. These query results could have multiple records for an individual asset.     

Assets – Is a term used to describe media files which have records being stored within a Photos.sqlite database.

Assets_Multi-Recs-PerAsset – If the term Assets_Multi-Recs-PerAsset is within the query name, it indicates the query results may include multiple records for each asset. There are multiple queries where this will apply and is required to conduct a detailed analysis of the asset. When a query result contains multiple records for one asset, the ZASSET Z_PK field and values can be used to isolate the records for analysis. See WHERE statement text file for assistance with isolating the asset records.

Assets_Single-Rec_PerAsset - If the term Assets_Single-Rec_PerAsset is within the query name, it indicates the query results will include a single record for each asset. There are multiple queries where this will apply and other queries should be used to conduct a thorough analysis. These queries will allow the user to conduct a validation of the query results using the ZASSET Z_PK values and the raw data being stored in the ZASSETS table.

AssetType12 - If the term AssetType12 is within the query name, it indicates the query will contain data from the ZASSET table ZSAVEDASSETTYPE field which contains the integer “12.” Based on my research, this indicates the asset is from the Syndication Photo Library and is a Shared with You asset. 

iCldLinks – If the term iCldLinks is within the query name, it indicates the query will contain data for assets that have been prepared for sharing via Shared iCloud Links also known as Cloud Master Moments (CMM).

IntResou – If the term IntResou is within the query name, it indicates the query will contain table data from ZINTERNALRESOURCE table and the query results will contain multiple records for a single asset. 

KIND2 – If the term KIND2 is within the query name, it indicates the query will contain data from the ZGENERICALBUM table ZKIND field which contains the integer “2.” Based on my research, this indicates the asset is within a Non-Shared Album. These query results may contain multiple records for an individual asset.

KIND1505 – If the term KIND1505 is within the query name, it indicates the query will contain data from the ZGENERICALBUM table ZKIND field which contains the integer “1505.” Based on my research, this indicates the asset is within a Shared Album. These query results may contain multiple records for an individual asset, if the asset can be found within multiple albums.

NoAssets – If the term NoAssets is within the query name, it indicates the query results do not contain asset data. 

REFERENCE – If the term REFERENCE is within the query name, it indicates the query will contain a large number of fields/columns and should be used when conducting a detailed analysis. Some of the reference queries may not function properly within SQLite tools because of the number of tables being joined and the number of columns. Please use these reference queries to analyze how I have joined the tables to produce a complete asset record. 

SPL – If the term SPL is within the query name, it indicates the query will include results related to the iCloud Shared Photo Library.

SWY – If the term SWY is within the query name, it indicates the query will include results related to Syndication Photo Library and Shared with You assets.

SyndicNotNull - If the term SyndicNotNull is within the query name, it indicates the query will contain data for assets that have a value in the ZADDITIONALASSETATTRIBUTES table ZSYNDICATIONIDENTIFIER field. Based on my research, when an asset is displayed within the camera roll as a part of the Syndication Photo Library and is a Shared with You asset, it will contain a unique identifier within this field.

wAddAssetData – If the term wAddAssetData is within the query name, it indicates the query will include additional asset data that might not be included with other queries. 

withInvites – If the term withInvites is within the query name, it indicates the query results will include data related to a shared invite. These query results may contain multiple records for an individual asset if the link has been shared with multiple participants or if new shared links have been shared over time.

with_Owner-Partic or withPartic – If these terms are used within the query name, it indicates the query results will contain data necessary to analyze the owner and participants of shared assets. 

Photos.sqlite Query Names, identifiers and defined results:
During this round of Photos.sqlite updates, I have used sequence numbers in an effort to categorize the different queries based on several factors to include particular artifacts and the size of the query results. In general, the higher the query sequence number, the more records and data fields will be included in the query results. The following is a list of sequence numbers and the types of data that might be included within the query results.     

0.*:
Query names starting with 0.* are supplemental information that can be used in conjunction with other analysis. The two queries listed within this category is a query for the migration table and a list of WHERE statements that can be used to isolate specific asset data within the query results.

1.*:
Query names starting with 1.* are core asset queries. These queries will provide core asset data being stored within a Photos.sqlite database. These queries start with 1.1 which can provide some basic information about the assets. As the sequence numbers increase, the number of records and fields will increase to allow for additional data to be visible for analysis.

2.*:
Query names starting with 2.* are queries focused around Albums. These queries will provide album data and data indicating if a particular asset(s) are associated with an album.

3.*:
Query names starting with 3.* are queries that will allow for analysis of data related to Non-Shared Albums. These queries will provide data related to Non-Shared Albums and data indicating which assets are associated with Non-Shared Albums.

4.*:
Query names starting with 4.* are queries that will allow for analysis of data related to Shared Albums. These queries will provide data related to Shared Albums and data indicating which assets are associated with Shared Albums.

5.*:
Query names starting with 5.* are queries that will allow for analysis of data related to iCloud Shared Photo Library (SPL). These queries will provide data related to iCloud Shared Photo Library, data indicating the owner and participants of an asset and the library, and the status of invites to the iCloud Shared Photo Library. 

6.*:
Query names starting with 6.* are queries that will allow for analysis of data related to Shared iCloud Links. These queries will provide data related to Shared iCloud Links and data indicating who shared the assets.

7.*:
Query names starting with 7.* are queries that will allow for analysis of data related to Syndication Photo Library and Shared with You Assets. These queries will provide data related to Syndication Photo Library (Shared with You) assets that may have been displayed in the local camera roll. Additionally the query results may include identifiers such as emails or phone numbers to identify who may have shared asset.  

8.*:
Query names starting with 8.* are queries that will allow for analysis of data related to different types of shared assets (iCloud Shared Photo Library - SPL, Syndication Photo Library - SWY, and Shared iCloud Links - CMM).

9.*:
Query names starting with 9.* are queries that will allow for analysis of data related to recently deleted assets.

10.*:
Query names starting with 10.* are queries that will allow for analysis of assets which contain valid location coordinates.

11.*:
Query names starting with 11.* are queries that will allow for analysis of data related to assets that have been marked as hidden.

12.*:
Query names starting with 12.* are queries that will allow for analysis of data related to assets that have been marked as favorite.

13.*:
Query names starting with 13.* are queries that will allow for analysis of data related to assets that have been adjusted via the native photos application edit tool.

14.*:
Query names starting with 14.* are queries that will allow for analysis of data related to assets that have been captured using action shots with burst mode. This data will include indications of assets visible within the camera roll and those that are not visible within the camera roll. 

15.*:
Query names starting with 15.* are queries that will allow for analysis of assets that have a last viewed timestamp.

The query file names may contain additional indicators about is being included in the query results. If you have questions about the queries please visit my blog, https://theforensicscooter.com/, or email me at, forensicscooter@gmail.com.
