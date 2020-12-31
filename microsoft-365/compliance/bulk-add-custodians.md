---
title: Importieren von Depot Inhabern in einen erweiterten eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Verwenden Sie das Import Tool DTO, um schnell mehrere Verwalter und die zugehörigen Datenquellen zu einem Fall in Advanced eDiscovery hinzuzufügen.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740302"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="37824-103">Importieren von Depot Inhabern in einen erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="37824-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="37824-104">Für erweiterte eDiscovery-Fälle, in denen viele depotverwalter involviert sind, können Sie mehrere Verwalter gleichzeitig importieren, indem Sie eine CSV-Datei verwenden, die die Informationen enthält, die erforderlich sind, um Sie zu einem Fall hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="37824-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="37824-105">Import Verwalter</span><span class="sxs-lookup"><span data-stu-id="37824-105">Import custodians</span></span>

1. <span data-ttu-id="37824-106">Öffnen Sie den erweiterten eDiscovery-Fall, und wählen Sie die Registerkarte **Datenquellen** aus.</span><span class="sxs-lookup"><span data-stu-id="37824-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="37824-107">Klicken Sie auf **Datenquellen**  >  -**Import Verwalter** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37824-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="37824-108">Klicken Sie auf der Seite " **depotverwalter importieren** " auf **leere Vorlage herunterladen** , um eine Depot Vorlagen-CSV-Datei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="37824-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Herunterladen einer CSV-Vorlage aus der Flyout-Seite "Verwalter importieren"](../media/ImportCustodians1.png)

4. <span data-ttu-id="37824-110">Fügen Sie die Informationen zum Freiheitsentzug der CSV-Datei hinzu, und speichern Sie Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="37824-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="37824-111">Im Abschnitt [Depot-CSV-Datei](#custodian-csv-file) finden Sie Informationen zu den erforderlichen Eigenschaften in der CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="37824-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="37824-112">Nachdem Sie die CSV-Datei mit den Depotinformationen vorbereitet haben, kehren Sie zur Registerkarte **Datenquellen** zurück, und klicken Sie erneut auf Datenquellen-   >  **Import Verwalter** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37824-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="37824-113">Klicken Sie auf der Seite **depotverwalter importieren** auf **Durchsuchen** , und laden Sie dann die CSV-Datei hoch, die die Depotinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="37824-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="37824-114">Nachdem die CSV-Datei hochgeladen wurde, wird ein Auftrag mit dem Namen **BulkAddCustodian** erstellt und auf der Registerkarte **Aufträge** angezeigt. Der Auftrag überprüft die Verwalter und die zugehörigen Datenquellen und fügt Sie dann zur Seite **Datenquellen** des Falls hinzu.</span><span class="sxs-lookup"><span data-stu-id="37824-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="37824-115">Depot-CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="37824-115">Custodian CSV file</span></span>

<span data-ttu-id="37824-116">Nachdem Sie die Vorlage CSV Depot heruntergeladen haben, können Sie in jeder Zeile Verwalter und deren Datenquelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37824-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="37824-117">Achten Sie darauf, die Spaltennamen in der Kopfzeile nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="37824-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="37824-118">Verwenden Sie die Spalten Arbeits Auslastungs und Arbeits Auslastungs Speicherort, um einer Depotbank andere Datenquellen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="37824-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="37824-119">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="37824-119">Column name</span></span>|<span data-ttu-id="37824-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37824-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="37824-121">**Depot Kontakt**</span><span class="sxs-lookup"><span data-stu-id="37824-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="37824-122">Die UPN-e-Mail-Adresse des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="37824-122">The custodian's UPN email address.</span></span> <span data-ttu-id="37824-123">Beispiel: Sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37824-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="37824-124">**Exchange aktiviert**</span><span class="sxs-lookup"><span data-stu-id="37824-124">**Exchange Enabled**</span></span> | <span data-ttu-id="37824-125">TRUE/false-Wert, der das Postfach des Depotinhabers einschließen oder nicht einschließen soll.</span><span class="sxs-lookup"><span data-stu-id="37824-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="37824-126">**OneDrive aktiviert**</span><span class="sxs-lookup"><span data-stu-id="37824-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="37824-127">TRUE/false-Wert, der das OneDrive für Unternehmen Konto des Verwalters enthält oder nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="37824-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="37824-128">**Ist OnHold**</span><span class="sxs-lookup"><span data-stu-id="37824-128">**Is OnHold**</span></span>        | <span data-ttu-id="37824-129">TRUE/false-Wert, der angibt, ob die Depotdaten Quellen aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="37824-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="37824-130">**Workload1-Typ**</span><span class="sxs-lookup"><span data-stu-id="37824-130">**Workload1 Type**</span></span>         |<span data-ttu-id="37824-131">Zeichenfolgenwert, der den Typ der Datenquelle angibt, die der Depotbank zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="37824-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="37824-132">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="37824-132">Possible values include:</span></span> <br/><span data-ttu-id="37824-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="37824-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="37824-134">-SharePointSite</span><span class="sxs-lookup"><span data-stu-id="37824-134">- SharePointSite</span></span><br/><span data-ttu-id="37824-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="37824-135">- TeamsMailbox</span></span><br/><span data-ttu-id="37824-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="37824-136">- TeamsSite</span></span><br/> <span data-ttu-id="37824-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="37824-137">- YammerMailbox</span></span><br/><span data-ttu-id="37824-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="37824-138">- YammerSite</span></span> |
|<span data-ttu-id="37824-139">**Workload1-Speicherort**</span><span class="sxs-lookup"><span data-stu-id="37824-139">**Workload1 Location**</span></span>     | <span data-ttu-id="37824-140">Je nach Arbeits Auslastungs ist dies der Speicherort der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="37824-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="37824-141">Beispielsweise die e-Mail-Adresse für ein Exchange-Postfach oder die URL für eine SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="37824-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="37824-142">Hier ist ein Beispiel für eine CSV-Datei mit Depotinformationen:</span><span class="sxs-lookup"><span data-stu-id="37824-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="37824-143">Depot Kontakt</span><span class="sxs-lookup"><span data-stu-id="37824-143">Custodian contactEmail</span></span>      | <span data-ttu-id="37824-144">Exchange aktiviert</span><span class="sxs-lookup"><span data-stu-id="37824-144">Exchange Enabled</span></span> | <span data-ttu-id="37824-145">OneDrive aktiviert</span><span class="sxs-lookup"><span data-stu-id="37824-145">OneDrive Enabled</span></span> | <span data-ttu-id="37824-146">Ist OnHold</span><span class="sxs-lookup"><span data-stu-id="37824-146">Is OnHold</span></span> | <span data-ttu-id="37824-147">Workload1-Typ</span><span class="sxs-lookup"><span data-stu-id="37824-147">Workload1 Type</span></span> | <span data-ttu-id="37824-148">Workload1-Speicherort</span><span class="sxs-lookup"><span data-stu-id="37824-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="37824-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37824-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="37824-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="37824-150">TRUE</span></span>             | <span data-ttu-id="37824-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="37824-151">TRUE</span></span>             | <span data-ttu-id="37824-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="37824-152">TRUE</span></span>      | <span data-ttu-id="37824-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="37824-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="37824-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37824-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="37824-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="37824-155">TRUE</span></span>             | <span data-ttu-id="37824-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="37824-156">TRUE</span></span>             | <span data-ttu-id="37824-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="37824-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="37824-158">Depotbank und Datenquellen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="37824-158">Custodian and data source validation</span></span>

<span data-ttu-id="37824-159">Nachdem Sie die Depot-CSV-Datei hochgeladen haben, führt Advanced eDiscovery folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="37824-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="37824-160">Überprüft die depotverwalter und deren Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="37824-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="37824-161">Indiziert alle Datenquellen für jede Depotbank und legt Sie in die Warteschleife (wenn die Eigenschaft **ist OnHold** in der CSV-Datei auf true festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="37824-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="37824-162">Depot Überprüfung</span><span class="sxs-lookup"><span data-stu-id="37824-162">Custodian validation</span></span>

<span data-ttu-id="37824-163">Derzeit unterstützen wir nur das Importieren von Depot Betreuern, die in der Azure-Active Directory Ihrer Organisation (Azure AD) enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="37824-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="37824-164">Das depotverwalter-Import Tool sucht und überprüft Verwalter mithilfe des UPN-Werts in der Spalte **Depot Kontakt** in der CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="37824-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="37824-165">Überprüfte Verwalter werden automatisch der Anfrage hinzugefügt und auf der Registerkarte **Datenquellen** der Anfrage aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="37824-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="37824-166">Wenn eine Depotstelle nicht überprüft werden kann, werden Sie im Fehlerprotokoll für den BulkAddCustodian-Auftrag aufgeführt, der in der Anfrage auf der Registerkarte **Aufträge** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="37824-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="37824-167">Nicht validierte depotverwalter werden dem Fall nicht hinzugefügt oder auf der Registerkarte **Datenquellen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="37824-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="37824-168">Datenquellen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="37824-168">Data source validation</span></span>

<span data-ttu-id="37824-169">Nachdem Verwalter überprüft und dem Fall hinzugefügt wurden, werden alle primären Postfächer und OneDrive-Konten hinzugefügt, die einer Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="37824-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="37824-170">Wenn jedoch eine der anderen Datenquellen (wie SharePoint-Websites, Microsoft Teams, Microsoft 365-Gruppen oder Jammer Gruppen), die einer Depotbank zugeordnet sind, nicht gefunden werden können, wird keine dieser Informationen der Depotbank zugewiesen, und der Wert, der **nicht validiert** wurde, wird in der Spalte **Status** neben der Depotbank auf der Registerkarte **Datenquellen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="37824-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="37824-171">So fügen Sie einer Depotbank validierte Datenquellen hinzu:</span><span class="sxs-lookup"><span data-stu-id="37824-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="37824-172">Wählen Sie auf der Registerkarte **Datenquellen** eine Depotbank aus, die nicht validierte Datenquellen enthält.</span><span class="sxs-lookup"><span data-stu-id="37824-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="37824-173">Führen Sie auf der Seite depotverwalter einen Bildlauf zum Abschnitt **Speicherorte** durch, um sowohl validierte als auch nicht validierte Datenquellen anzuzeigen, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="37824-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="37824-174">Klicken Sie oben auf der Flyout-Seite auf **Bearbeiten** , um ungültige Datenquellen zu entfernen oder neue hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="37824-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="37824-175">Nachdem Sie nicht validierte Datenquellen entfernt oder ein neues hinzugefügt haben, wird der Wert **aktiv** in der Spalte **Status** für die Depotbank auf der Registerkarte **Datenquellen** angezeigt. Zum Hinzufügen von Quellen, die zuvor als ungültig erschienen sind, führen Sie die folgenden korrekturschritte aus, um Sie manuell zu einer Depotbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="37824-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="37824-176">Remediation ungültige Datenquellen</span><span class="sxs-lookup"><span data-stu-id="37824-176">Remediating invalid data sources</span></span>

<span data-ttu-id="37824-177">Manuelles Hinzufügen und Zuordnen einer zuvor ungültigen Datenquelle:</span><span class="sxs-lookup"><span data-stu-id="37824-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="37824-178">Wählen Sie auf der Registerkarte **Datenquellen** eine Depotbank aus, um eine zuvor ungültige Datenquelle manuell hinzuzufügen und zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="37824-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="37824-179">Klicken Sie oben auf der Flyout-Seite auf **Bearbeiten** , um der Depotbank Postfächer, Websites, Teams oder Jammer Gruppen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="37824-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="37824-180">Klicken Sie dazu neben dem entsprechenden Datenspeicherort auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="37824-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="37824-181">Klicken Sie auf **weiter** , um die Seite **halte Einstellungen** anzuzeigen, und konfigurieren Sie die Einstellung halten für die Datenquellen, die Sie hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="37824-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="37824-182">Klicken Sie auf **weiter** , um die Seite **Verwalter überprüfen** anzuzeigen, und klicken Sie dann auf über **Mitteln** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="37824-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
