---
layout: page
title: Table output
description: Table output
product: xtract-universal
parent: bw-hierarchies
permalink: /:collection/:path
weight: 2
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=table-output
---

Compared to other source components, the output of hierarchy components is fixed. It always has the same columns for every hierarchy, as described in the following:

**NodeID**<br>
Unique node key.

**ParentNodeID**<br>
Key for parent node.

**FirstChildNodeID**<br>
Key for first child node.

**NextNodeID**<br>
Key for next node in the same hierarchical level.

**InfoObjectName**<br>
Name of InfoObject behind the corresponding node.

**NodeName**<br>
The node’s (technical) name.

**NodeText** <br>
The descriptive text in the respective logon language (only when FetchText is set to true in the settings).

The original hierarchy of PM_COUNTRY looks in SAP as follows:

![Hierarchy-Table-Output](/img/content/Hierarchy-Table-Output.png){:class="img-responsive"}

The output in the browser looks as follows:

![Hierarchy-Table-Output-Browser](/img/content/Hierarchy-Table-Output-Browser.png){:class="img-responsive"}
