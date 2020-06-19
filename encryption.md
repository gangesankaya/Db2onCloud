---

copyright:
  years: 2014, 2020
lastupdated: "2020-02-06"

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

# Data security & encryption
{: #encryption}

The {{site.data.keyword.Db2_on_Cloud_long}} service has security built into all levels of its architecture.
{: shortdesc}

The following methods are used to secure your data:
-  The default keys are managed by Key Protect. Bring-your-own-key (BYOK) for encryption is also available through Key Protect Integration.
backups are encrypted. 
- Data in motion is encrypted through SSL/TLS. The current supported version of this encryption is TLS 1.2.
- All Db2 on Cloud storage is provided on storage encrypted with LUKS using AES-256.
- Backplane network connectivity is supported through IBM Cloud Service Endpoints
- Database-level security is supported through Role-Based Access Control (RBAC) and Row and Column Access Control (RCAC)

Administrators can make encrypted connections mandatory. For more information, see [SSL connectivity](/docs/Db2onCloud?topic=Db2onCloud-ssl_support).


