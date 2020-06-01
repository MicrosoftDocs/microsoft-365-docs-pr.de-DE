---
title: Massenhafte Hinzufügen von Depot Betreuern zu einem erweiterten eDiscovery-Fall
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432438"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="fd122-102">Massen-Hinzufügen von Depot Betreuern zu einem erweiterten eDiscovery-Fall (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="fd122-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="fd122-103">Für erweiterte eDiscovery-Fälle, in denen viele depotverwalter involviert sind, können Sie mehrere Verwalter gleichzeitig durch eine CSV-Datei importieren, die alle Informationen enthält, die erforderlich sind, um Sie zu einem Fall hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fd122-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="fd122-104">Massen-Hinzufügen von Depot Betreuern</span><span class="sxs-lookup"><span data-stu-id="fd122-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="fd122-105">Geben Sie Case ein, und navigieren Sie zur Registerkarte **Quellen** .</span><span class="sxs-lookup"><span data-stu-id="fd122-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="fd122-106">Klicken Sie auf **depotverwalter importieren** .</span><span class="sxs-lookup"><span data-stu-id="fd122-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="fd122-107">Klicken Sie auf der Seite Flyout auf **leere Vorlage herunterladen** , um eine CSV-Depot Vorlagendatei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fd122-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="fd122-108">Fügen Sie die Informationen zum Freiheitsentzug der CSV-Datei hinzu, und speichern Sie Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="fd122-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="fd122-109">Im nächsten Abschnitt finden Sie Informationen zu den Eigenschaften in der CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="fd122-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="fd122-110">Klicken Sie auf der Registerkarte **Quellen** erneut auf **Verwalter importieren** .</span><span class="sxs-lookup"><span data-stu-id="fd122-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="fd122-111">Klicken Sie auf der Seite Flyout auf **Durchsuchen** , und laden Sie die CSV-Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="fd122-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="fd122-112">Nachdem die CSV-Datei hochgeladen wurde, wird ein BulkAddCustodian-Auftrag erstellt und auf der Registerkarte **Aufträge** angezeigt. Der Auftrag überprüft die depotverwalter und die zugehörigen Datenquellen und fügt Sie dann der Registerkarte **Verwalter** auf der Seite **Quellen** der Anfrage hinzu.</span><span class="sxs-lookup"><span data-stu-id="fd122-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="fd122-113">Depot-CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="fd122-113">Custodian CSV file</span></span>

<span data-ttu-id="fd122-114">Nachdem Sie die CSV-Vorlage heruntergeladen haben, können Sie in jeder Zeile Verwalter und deren Datenquelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fd122-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="fd122-115">Achten Sie darauf, die Spaltennamen in der Kopfzeile nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fd122-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="fd122-116">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="fd122-116">Column name</span></span>|<span data-ttu-id="fd122-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd122-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="fd122-118">**Depot Kontakt**</span><span class="sxs-lookup"><span data-stu-id="fd122-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="fd122-119">UPN-e-Mail der Depotbank.</span><span class="sxs-lookup"><span data-stu-id="fd122-119">UPN email of custodian.</span></span> <span data-ttu-id="fd122-120">Beispiel: Sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fd122-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="fd122-121">**Exchange aktiviert**</span><span class="sxs-lookup"><span data-stu-id="fd122-121">**Exchange Enabled**</span></span> | <span data-ttu-id="fd122-122">TRUE/false-Wert, ob depotverwalter Postfach hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd122-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="fd122-123">**OneDrive aktiviert**</span><span class="sxs-lookup"><span data-stu-id="fd122-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="fd122-124">TRUE/false-Wert, ob das OneDrive für Unternehmen Konto des Verwalters hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd122-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="fd122-125">**Ist OnHold**</span><span class="sxs-lookup"><span data-stu-id="fd122-125">**Is OnHold**</span></span>        | <span data-ttu-id="fd122-126">TRUE/false-Wert, ob depotverwalter in den Haltebereich platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd122-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="fd122-127">**Workload1-Typ**</span><span class="sxs-lookup"><span data-stu-id="fd122-127">**Workload1 Type**</span></span>         | <span data-ttu-id="fd122-128">Zeichenfolgenwert, der den Typ der Datenquelle angibt, die der Depotbank zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd122-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="fd122-129">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fd122-129">Possible values include:</span></span> <br /><span data-ttu-id="fd122-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="fd122-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="fd122-131">**Workload1-Speicherort**</span><span class="sxs-lookup"><span data-stu-id="fd122-131">**Workload1 Location**</span></span>     | <span data-ttu-id="fd122-132">Je nach Arbeits Auslastungs wäre dies der Datenspeicherort Ihrer Arbeitsauslastung (beispielsweise die e-Mail-Adresse eines Exchange-Postfachs oder die URL für eine SharePoint-Website).</span><span class="sxs-lookup"><span data-stu-id="fd122-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="fd122-133">Hier ist ein Beispiel für eine CSV-Datei mit Depotinformationen:</span><span class="sxs-lookup"><span data-stu-id="fd122-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="fd122-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="fd122-134">ContactEmail</span></span>      | <span data-ttu-id="fd122-135">Exchange aktiviert</span><span class="sxs-lookup"><span data-stu-id="fd122-135">Exchange Enabled</span></span> | <span data-ttu-id="fd122-136">OneDrive aktiviert</span><span class="sxs-lookup"><span data-stu-id="fd122-136">OneDrive Enabled</span></span> | <span data-ttu-id="fd122-137">Ist OnHold</span><span class="sxs-lookup"><span data-stu-id="fd122-137">Is OnHold</span></span> | <span data-ttu-id="fd122-138">Workload1-Typ</span><span class="sxs-lookup"><span data-stu-id="fd122-138">Workload1 Type</span></span> | <span data-ttu-id="fd122-139">Workload1-Speicherort</span><span class="sxs-lookup"><span data-stu-id="fd122-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="fd122-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fd122-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="fd122-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd122-141">TRUE</span></span>             | <span data-ttu-id="fd122-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd122-142">TRUE</span></span>             | <span data-ttu-id="fd122-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd122-143">TRUE</span></span>      | <span data-ttu-id="fd122-144">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="fd122-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="fd122-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fd122-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="fd122-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd122-146">TRUE</span></span>             | <span data-ttu-id="fd122-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd122-147">TRUE</span></span>             | <span data-ttu-id="fd122-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="fd122-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="fd122-149">Depotbank und Datenquellen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd122-149">Custodian and data source validation</span></span>

<span data-ttu-id="fd122-150">Wenn Sie die Depot-CSV-Datei hochladen, führt Advanced eDiscovery folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="fd122-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="fd122-151">Überprüft die depotverwalter und deren Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="fd122-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="fd122-152">Indiziert alle Datenquellen für jede Depotstelle und platziert Sie in der Warteschleife (wenn die Eigenschaft ist OnHold auf true festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="fd122-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="fd122-153">Depot Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd122-153">Custodian validation</span></span>

<span data-ttu-id="fd122-154">Derzeit wird nur das Importieren von Depot Inhabern unterstützt, die sich in Azure Active Directory (AAD) befinden.</span><span class="sxs-lookup"><span data-stu-id="fd122-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="fd122-155">Mithilfe des UPN-Werts in der Spalte **Kontakt-e-Mail** in der CSV-Datei validieren und finden Sie Verwalter.</span><span class="sxs-lookup"><span data-stu-id="fd122-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="fd122-156">Überprüfte Verwalter werden automatisch dem Fall hinzugefügt und auf der Registerkarte **Depot** auf der Seite **Quellen** der Anfrage aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd122-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="fd122-157">Wenn eine Depotstelle nicht überprüft werden kann, werden Sie im Fehlerprotokoll für den BulkAddCustodian-Auftrag aufgeführt, der in der Anfrage auf der Registerkarte **Aufträge** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="fd122-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="fd122-158">Nicht validierte depotverwalter werden dem Fall nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fd122-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="fd122-159">Datenquellen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="fd122-159">Data source validation</span></span>

<span data-ttu-id="fd122-160">Nachdem die Verwalter überprüft und dem Fall hinzugefügt wurden, wird jede Datenquelle validiert, die einer Depotbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fd122-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="fd122-161">Wenn keine Datenquelle für eine Depotstelle gefunden werden kann, wird der Wert, der **nicht überprüft** wurde, in der Spalte **validiert** auf der Registerkarte **Depot** für diese Depotbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd122-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="fd122-162">Remediation nicht validierter Datenquellen</span><span class="sxs-lookup"><span data-stu-id="fd122-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="fd122-163">So beheben Sie Verwalter mit nicht validierten Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="fd122-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="fd122-164">Wählen Sie auf der Registerkarte **depotverwalter** eine nicht validierte Depotbank aus.</span><span class="sxs-lookup"><span data-stu-id="fd122-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="fd122-165">Führen Sie auf der Seite depotverwalter einen Bildlauf zum Abschnitt **Datenquellen** durch, um die Datenquellen anzuzeigen, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fd122-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="fd122-166">Es werden sowohl validierte als auch nicht validierte Datenquellen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd122-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="fd122-167">Klicken Sie im Abschnitt **Datenquellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fd122-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="fd122-168">Entfernen Sie auf der Seite **Speicherorte auswählen** eine nicht validierte Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="fd122-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="fd122-169">Klicken Sie auf der Seite **weitere Speicherorte auswählen** auf **Aktualisieren** , um zusätzliche Datenquellen für eine Depotstelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fd122-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
