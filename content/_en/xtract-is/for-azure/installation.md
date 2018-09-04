---
layout: page
title: Installation
description: Installation
product: xtract-is
parent: for-azure
permalink: /:collection/:path
weight: 2
lang: en_GB
---

Follow the [instructions]() on how to set up 3rd party extensibility for Azure-SSIS IR. Only the part with setting up an Azure storage container and creating a Shared Access Signature is relevant.

Download, unzip and place *Xtract IS for Azure* setup in the storage container created previously.
The setup consists of 2 files: XtractISSetup.exe (downloadable from our website or customer portal) and main.cmd. 

![XISforAzure_StorageContainer](/img/content/XISforAzure_StorageContainer.jpg){:class="img-responsive" }

Before starting up the IR, make sure you reference the Custom Container SAS URI created above:

“When you provision or reconfigure your Azure-SSIS IR with PowerShell, before you start your Azure-SSIS IR, run the 
Set-AzureRmDataFactoryV2IntegrationRuntime cmdlet with the SAS URI of your container as the value for new SetupScriptContainerSasUri parameter” as outlined [here]().

![XISforAzure_PS_CustomSetupContainer](/img/content/XISforAzure_PS_CustomSetupContainer.jpg){:class="img-responsive" }

When you provision your Azure-SSIS IR via the Azure Portal UI, enter te Custom Container SAS URI in the respective field, as outlined here.

![XISforAzure_Poral_CustomSetupContainer](/img/content/XISforAzure_Poral_CustomSetupContainer.jpg){:class="img-responsive" }
Finally, start the Integration Runtime. ATTENTION: The startup process of the IR might take 20 to 30 minutes.