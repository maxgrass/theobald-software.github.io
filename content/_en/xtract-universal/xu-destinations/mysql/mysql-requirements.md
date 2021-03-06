---
layout: page
title: Requirements
description: Requirements
product: xtract-universal
parent: mysql
permalink: /:collection/:path
weight: 1
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=mysql-requirements
---

Before using this destination the ADO.NET Driver for MySQL (Connector/NET) needs to be installed.

The driver is available from [here](https://www.mysql.com/products/connector/). Please download the latest stable driver version. 

At the first use of the MySQL destination, the Destination Details dialog pops up to select the required MySql.Data.dll.

Make sure to select the file from the v4.0 folder: C:\Program Files (x86)\MySQL\MySQL Connector Net 6.9.6\Assemblies\v4.0 

![mysql_ADO.NET](/img/content/mysql_ADO.NET.jpg){:class="img-responsive"}

After selecting the file click on Save and Close. 

**ATTENTION**: To do so, you need to run Xtract Universal as administrator.
