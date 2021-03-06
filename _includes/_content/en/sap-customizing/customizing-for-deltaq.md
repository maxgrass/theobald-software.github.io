**Caution:** Those steps for the DeltaQ customizing except step 2 are client specific. 

In order to be able to use the DeltaQ components, some customizing settings have to be made in SAP as described step-by-step in the following:

**Step 1**

Create a new RFC destination of the type 3 in your SM59 transaction (you can name it e.g. XTRACT01). You don't need to conduct a transmission test; you only have to have a destination.

**Step 2 (optional)**

Step 2 to create a logican system is optional, since the functional module in step 3 will automatically create it if it does not exist. 
 
With the help of the SALE transaction, create a logical system with the same name as your destination in step 1.

![DeltaQ-Customizing-01](/img/content/DeltaQ-Customizing-01.png){:class="img-responsive" }

**Step 3**

Go to transaction SE37 and bring up the RSAP_BIW_CONNECT_40 module in the test environment. Fill in your import parameters as shown in the screenshot. 
The parameter I_SLOGSYS is the logical name of the source system. If you're not sure what this is, consult the T000 table for the respective client (LOGSYS field). 
The field I_SAPRL will have a default value set by the SAP system.
With F8 you can then execute the module.

**Caution:** This step needs some parts (2-3) of the SAP System to be modifiable, for more information refer to the following [knowledge base article]().

**Caution:** The values for the fields I_BASIC_IDOC and I_TSPREFIX must be unique for the different RFC Destiantions.
If you set the values ZXTIDOC and XT for XTRACT01, you can set e.g. ZX2IDOC and X2 for XTRACT02.

![DeltaQ-Customizing-03](/img/content/DeltaQ-Customizing-03.png){:class="img-responsive" }

**Step 4**

Now go back into the SM59 transaction and delete the destination that you created in step 1 (Detailed *View -> Menu -> Delete*). Then create a new destination with exactly the same name, but this time of the type *T*=TCP/IP. The activation type has to be a *Registered Server Program*. Enter the name of the destination for the program ID.
Set the following fields:

**Gateway Host:** is the name (or IP address) of YOUR SAP system (ptmalg is the name of our SAP system used in this example)<br>
**Gateway Service:** is generally *sapgwNN*, where NN is the ID of your SAP system, i.e. a number between 00 andd 99. 

![DeltaQ-Customizing-04](/img/content/DeltaQ-Customizing-04.png){:class="img-responsive" }

**Optional, but recommended:** Starting from Xtract IS version 2.15.0, the resend of tRFC errors (see DeltaQ settings) is deprecated. While it is still supported, its use is no longer recommended. When creating a new DeltaQ extraction, it is therefore deactivated by default (formerly it was activated by default). Instead, we recommend changing the tRFC options for the RFC destination you just created. In SM59 go to *Edit - tRFC Options* and set the *parameter Connection attempts up to task to 30* and *Time betw*. 2 tries *[min]* to 2. 

**Step 5**

Launch the RSAS_RBWBCRL_STORE module as shown below. Its purpose is to activate the new target system.

![DeltaQ-Customizing-05](/img/content/DeltaQ-Customizing-05.png){:class="img-responsive" }

**Step 6**

Refer to our [knowledge base](https://my.theobald-software.com/index.php?/Knowledgebase/Article/View/100/0/registering-rfc-server-in-sap-releases-above-kernel-release-720) for registering the RFC Server in SAP

**Caution:** Step 6 is for SAP Kernel Release 720 or higher.


**Step 7**

Go to SAP transaction SMQS. Change the Max.Conn. parameter to 10. Increase this value when running several DeltaQ extractions in parallel on the same RFC destination.


For any Errors please refer to our [DeltaQ Troubleshooting Guide](https://my.theobald-software.com/index.php?/Knowledgebase/Article/View/107/4/deltaq-troubleshooting-guide) .              