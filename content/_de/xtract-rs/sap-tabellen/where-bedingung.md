---
layout: page
title: WHERE Bedingung
description: WHERE Bedingung
product: xtract-rs
parent: sap-tabellen
permalink: /:collection/:path
weight: 3
lang: de_DE
old_url: /Xtract-RS-DE/default.aspx?pageid=where-bedingung
---

Die WHERE-Bedingung muss dem SAP OpenSQL Syntax entsprechen.

- Vor und nach dem Gleichheitszeichen müssen Sie immer ein Leerzeichen eingeben, z.B. JAHR = '1999'. Für YEAR= '1999 ', YEAR ='1999' or YEAR='1999' erhalten Sie die Fehlermeldung 'A dynamically specified column Name is unknown'.
- Fließkommazahlen müssen immer in einfache Hochkommata gesetzt werden, z.B. KMENG > '10.3'.  Für KMENG > 10.3 erhalten Sie die Fehlermeldung 'The WHERE clause has an unexpected format'.
- Die Where-Bedingung darf keinen Zeilenumbruch (Eingabe-Taste) enthalten.

Weitere Informationen über die OpenSQL Syntax finden Sie auf der SAP Hilfe-Seite: [http://help.sap.com/saphelp_470/helpdata/de/fc/eb3a1f358411d1829f0000e829fbfe/frameset.htm](http://help.sap.com/saphelp_470/helpdata/de/fc/eb3a1f358411d1829f0000e829fbfe/frameset.htm)

**Interne SAP-Darstellung**<br>
Werte müssen in interner SAP-Darstellung angegeben werden: 

- Das Datum 01.01.1999 hat die interne Darstellung 19990101 (YYYYMMDD)
- Die Periode 001.1999 hat die interne Darstellung  1999001 (YYYYPPP)
- Bei Nummern müssen auch führende Nullen angegeben werden: Kundennumer 1000 hat die interne Darstellung 0000001000