---

copyright:
  years: 2014, 2019
lastupdated: "2018-03-14"

keywords: 

subcollection: Db2onCloud

---

<!-- Attribute definitions --> 
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}


# Current Plans

Access to IBM Cloud Db2 on Cloud service instances for users in your account is controlled by IBM Cloud [Identity and Access Management (IAM)](/docs/iam?topic=iam-getstarted) and database access is provided by standard access controls provided by the database. 

## User Types

### Database Users
These are the users that are used to access the database.  Traditionally these are the OS users in a typical Db2 deployment although in the cloud we use our own user registry.  Db2 understands these users as native to the database. The database priveleges for the users can be granted or revoked as can roles that are developed by the user. 

Database users are not granted any service level functions.  For example a database administrator who has access to the data does not have access to change the configuration of the system outside of the database priveleges that they have been given.  

### IAM User
IAM is only integrated with high-level service access, which governs privileges and operations available in the Db2 on Cloud Console and database.  Access to the database by these IAM users is provided by allowing and IAM user or service ID access to a specific Db2 user. (see above)


# Access and Roles

Customers can use JDBC or any Db2 Client to connect to their database. THere are 2 ways customers can access the database. They can use their database username and password assoicated with their account or use the IAM token (or APIKey which gets the token) that is mapped to the associated database user. IAM authentication is performed as the authentication mechanism. Permissions are not controlled by IAM however, they are controlled by database level priveleges of the associated users. 

## Console Access
Console access is controlled by IAM. An IAM user can be assigned access to all Db2 service instances, all Db2 service instances in a resource group or a specific service instance by IAM interfaces. Within these parameters they can be assigned platform and service level access.


| Role         | Console user mgmt | Console SQL Editor/tables | Console Monitoring info | Console Settings (including scale, backup, etc) | Console info panels |
| ------------ |:-----------------:| -------------------------:| -----------------------:| ----------------:| ------------------:|
| IAM - Platform - Operator     | No     | No (unless mapped to db2 user) | Yes                     | Yes              | Yes |
| IAM - Platform - Viewer       | No     | No (unless mapped to db2 user) | Yes                     | No               | Yes |
| IAM - Platform - Administraor | Yes    | No (unless mapped to db2 user) | Yes                     | Yes              | Yes |
| IAM - Platform - Editor       | No     | No (unless mapped to db2 user) | Yes                     | Yes              | Yes |
| Non-IAM but autheticate with JDBC| Only change password| Yes | No | No | Yes |


# Legacy Plans

## Managing users
{: #user_mgmt}

Management of users that were given access to the database is the sole responsibility of the user or users with the administrator role. The administrator has the responsibility to manage how other users in your organization access your database.
{: shortdesc}

The database administrator role manages the following types of user access: 
* Web console. From the web console, users can run queries against the database.
* Database. The administrator can grant granular access permissions to the database, including being able to access only certain tables, schemas, or even rows or columns. 

For more information about user management, see [Database user management](https://www.ibm.com/support/knowledgecenter/SSFMBX/com.ibm.swg.im.dashdb.security.doc/doc/user_mgmnt.html){:external}
