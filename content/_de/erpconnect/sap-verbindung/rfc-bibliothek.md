---
layout: page
title: RFC-Bibliothek
description: RFC-Bibliothek
product: erpconnect
parent: sap-verbindung
permalink: /:collection/:path
weight: 4
lang: de_DE
old_url: /ERPConnect-DE/default.aspx?pageid=rfc-bibliothek
---

Die RFC API (Remote Function Call) erlaubt den Aufbau einer RFC-Verbindung zu einem SAP-System von einem externen System, welches als Client oder Server mit dem SAP-System kommunizieren kann.<br>
Die RFC API existiert in zwei unterschiedlichen Versionen: 
- Klassiche RFC-API 
- Netweaver-RFC-API 

SAP Library: [RFC API: Classical & NetWeaver](https://help.sap.com/saphelp_nwpi71/helpdata/de/45/18e96cd26321a1e10000000a1553f6/frameset.htm) 

**Klassische RFC-Bibliothek**

Die klassische RFC-Bibliothek wird standardmäßig für die SAP-Verbindung gesetzt. 


Netweaver RFC-Bibliothek

ERPConnect unterstützt die Netweaver RFC-Bibliothek seit der Version 4.6.0 (siehe [Version History](https://my.theobald-software.com/index.php?/Knowledgebase/Article/View/82/52/erpconnect-version-history)). 

Dazu setzen Sie die Eigenschaft Protocol des R3Connection-Objekts auf ClientProtocol.NWRFC. 

```
R3Connection.Protocol = ClientProtocol.NWRFC;
```

Bei der Verwendung der Netweaver-DLLs sind bestimmte DLLs jeweils für die 32- bzw. 64-Bit Umgebung nötig.

Für die 64-Bit Umgebung sind folgende DLLs nötig:
- ERPConnect20.dll oder ERPConnect35.dll oder ERPConnect40.dll oder ERPConnect45.dll
- ERPConnectNW.dll
- sapnwrfc.dll
- icuuc34.dll
- icudt34.dll
- icuin34.dll 

Die ERPConnect* .dll werden mit ERPConnect mitgeliefert. Die restlichen DLLs müssen von den SAP-Seiten heruntergeladen werden.

- Properties / Connection String
