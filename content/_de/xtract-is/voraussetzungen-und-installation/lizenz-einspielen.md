---
layout: page
title: Lizenz einspielen
description: Lizenz einspielen
product: xtract-is
parent: voraussetzungen-und-installation
permalink: /:collection/:path
weight: 4
lang: de_DE
old_url: /Xtract-IS-DE/default.aspx?pageid=lizenz-einspielen
---

Standardmäßig wird bei der Installation eine Demo-Version installiert, die zeitlich beschränkt ist. Wenn Sie Xtract IS gekauft haben, bekommen Sie von uns eine Lizenzdatei (XtractISLicense.json, ehemals XtractIS.License.dll) zugesendet, in der u.A. Firmenname und lizensierte Server verschlüsselt sind.

Um die Lizenz einzuspielen, starten Sie das Programm XtractLicenseManager.exe (aus dem Programm-Menü). Die aktuell aktive Lizenz wird angezeigt, im folgenden Fall ist es eine Demo-Lizenz.

![XIS-License-Manager](/img/content/XIS-License-Manager.jpg){:class="img-responsive"}

Klicken Sie nun auf *Install*. Ein Dateiauswahldialog öffnet sich. Wählen Sie Ihre gekaufte Lizenz und bestätigen Sie mit *OK*. Wenn Sie den Lizenzmanager noch einmal starten, werden dort Ihre individuellen Lizenzdaten angezeigt. Ihre Lizenzdaten können Sie im Übrigen auch direkt in den Xtract IS SSIS-Komponenten anzeigen lassen, indem Sie auf *XtractIS Info* klicken.

Dieses Bild zeigt eine korrekt installierte, dauerhafte Lizenz.

![XIS_License_Info](/img/content/XIS_License_Info.jpg){:class="img-responsive"}

Xtract.License.dll Dateien werden im GAC registriert.<br> 
XtractISLicense.json Dateien werden nach CSIDL_COMMON_APPDATA\TheobaldSoftware\XtractIS\ bzw. <br>C:\ProgramData\TheobaldSoftware\XtractIS\ kopiert.

