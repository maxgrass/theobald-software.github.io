---
layout: page
title: Benutzerverwaltung
description: Benutzerverwaltung
product: xtract-universal
parent: sicherheit_in_xu_3_x
permalink: /:collection/:path
weight: 1
lang: de_DE
old_url: /Xtract-Universal-DE/default.aspx?pageid=benutzerverwaltung1
---

Die Verbindung zwischen Xtract Unviersal Designer und Xtract Universal Server erfolgt über unterschiedliche Authentisierung und Verschlüsselungsverfahren:

1. Windows AD Benutzer (außerhalb von Xtract Universal angelegt)
2. Custom Benutzer (innerhalb von Xtract Universal angelegt, in XU 2.x als "basic user" bezeichnet)
3. Anonym (keine Anmeldedaten benötigt, keine Verschlüsselung)

![XU3_Designer_Authentication](/img/content/XU3_Designer_Authentication.jpg){:class="img-responsive"}

XU unterstützt verschiedene Kombinationen von Transportverschlüsselung + Authentisierung:

**Windows credentials (current user)**<br>
Der AD-Benutzer, der den XU Designer ausführt, authentisiert sich gegenüber dem XU Server per Kerberos. Alle zwischen Designer + Server ausgetauschten Daten werden per Kerberos verschlüsselt.

**Windows credentials (different user)**<br> 
Der AD-Benutzer, dessen Benutzername und Passwort in das Anmeldefenster eingegeben werden, authentisiert sich gegenüber dem XU Server per Kerberos. Alle zwischen Designer + Server ausgetauschten Daten werden per Kerberos verschlüsselt.

**Custom credentials (TLS encryption)**<br>
Der Custom User, dessen Benutzername und Passwort in das Anmeldefenster eingegeben werden, authentisiert sich gegenüber dem XU Server. Alle zwischen Designer + Server ausgetauschten Daten werden per TLS verschlüsselt.<br>
Um TLS Transportverschlüsselung zu verwenden, wird ein X.509 Serverzertifikat für den XU Service benötigt (kann in den Server Settings hinterlegt werden).<br>
Im Anmeldefenster muss im Feld Server der DNS Hostname des Servers eingetragen werden, für den das Zertifikat ausgestellt wurde.

**Custom credentials (Kerberos encryption)**<br>
Der Custom User, dessen Benutzername und Passwort in das Anmeldefenster eingegeben werden, authentisiert sich gegenüber dem XU Server. Alle zwischen Designer + Server ausgetauschten Daten werden per Kerberos verschlüsselt.

**Anonymous (no encryption)**<br>
Es findet keine Authentisierung statt. Die zwischen Designer + Server ausgetauschten Daten werden ohne Transportverschlüsselung im Klartext übertragen.

Diese unterschiedlichen Anmeldeoptionen können in den Server Settings aktiviert/deaktiviert werden.

![XU3_ServerSettings_authenticaion_methods](/img/content/XU3_ServerSettings_authenticaion_methods.jpg){:class="img-responsive"}

**Target principal**<br>
Um Kerberos Transportverschlüsselung zu verwenden, oder einen Active Directory Benutzer zu authentisieren, wird ein Kerberos Target Principal Name benötigt. Dies kann entweder ein User Principal Name sein (Benutzername in @-Schreibweise) oder ein Service Principal Name.<br>
UPN: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa380525(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa380525(v=vs.85).aspx)<br>
SPN: [https://msdn.microsoft.com/en-us/library/ms677949(VS.85).aspx](https://msdn.microsoft.com/en-us/library/ms677949(VS.85).aspx)

Der Target Principal Name muss entweder dem UPN des Benutzers entsprechen, unter dem der XU Windows Service ausgeführt wird, oder einem SPN, der diesem Benutzer zugeordnet ist.<br>
Standardmäßig wird der XU Service unter dem Local System Account ausgeführt. Im AD tritt dieser Benutzer als Computeraccount auf. Dem Computeraccount ist standardmäßig der SPN *HOST/[hostname]@[domain]* zugeordnet.<br>
Deswegen muss der Target Principal Name im Anmeldefenster nur geändert werden, wenn der Service Account des XU Windows Service geändert wurde.


![XU_Service](/img/content/XU_Service.jpg){:class="img-responsive"}

**Benutzer**
Das Anlegen von Custom Benutzern funktioniert so wie das Anlegen von Basic Benutzern in XU 2.x. Zum Zeitpunkt der Benutzeranlage müssen noch keine Rechte vergeben werden, siehe Kapitel Zugriffsverwaltung.<br>
Custom Benutzer werden angelegt und Custom Benutzergruppen zugeordnet via *Security - Manage Users*.

![XU3_assign_UserGroups](/img/content/XU3_assign_UserGroups.png){:class="img-responsive"}

**Benutzergruppen**<br>
In XU 2.x konnten Benutzergruppen nur in Xtract Universal angelegt werden. XU 3.x unterstützt zusätzlich Windows AD Benutzergruppen, welche außerhalb von Xtract Universal angelegt werden. Zum Zeitpunkt der Benutzergruppenanlage müssen noch keine Rechte vergeben werden, siehe Kapitel Zugriffsverwaltung.<br>
Windows AD Benutzer werden Windows AD Benutzergruppen außerhalb von Xtract Universal zugeordnet.

**ACHTUNG:**<br>
Custom User können nur custom Benutzergruppen zugeordnet werden.<br>
Windows AD User können nur Windows AD Gruppen zugeordnet werden, jedoch nicht zu custom Benutzergruppen. Das ist ein "Breaking Change" im Vergleich zu XU 2.x.

Daraus folgt, dass Windows AD User, die unter XU 2.x custom Benutzergruppen zugeordnet waren bei der Migration nach XU 3.x aus diesen Gruppen verschwinden.

Die Zugriffsverwaltung wird dadurch nicht beeinflusst. Allerdings wird der Zugriff auf Benutzerebene aufgelöst. Soll der Zugriff auf Gruppenebene erfolgen, müssten die Windows AD Benutzer neu anzulegenden Windows AD Gruppen zugeordnet werden.

Im Gegensatz zu zu Windows AD Benutzergruppen werden Custom Benutzergruppen im Xtract Universal Designer angelegt.

![XU3_new_UserGroup](/img/content/XU3_new_UserGroup.jpg){:class="img-responsive"}


