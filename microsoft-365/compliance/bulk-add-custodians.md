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
description: Verwenden Sie das Tool Bulk-Add, um schnell mehrere Verwalter und die zugehörigen Datenquellen zu einem Fall in Advanced eDiscovery hinzuzufügen.
ms.openlocfilehash: 921d4a1616d97f2adde7e40baa5c73f607c849b6
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741642"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="a58c7-103">Massenhafte Hinzufügen von Depot Betreuern zu einem erweiterten eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="a58c7-103">Bulk-add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="a58c7-104">Für erweiterte eDiscovery-Fälle, in denen viele depotverwalter involviert sind, können Sie mehrere Verwalter gleichzeitig durch eine CSV-Datei importieren, die alle Informationen enthält, die erforderlich sind, um Sie zu einem Fall hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a58c7-104">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="a58c7-105">Massen-Hinzufügen von Depot Betreuern</span><span class="sxs-lookup"><span data-stu-id="a58c7-105">Bulk-add custodians</span></span>

1. <span data-ttu-id="a58c7-106">Geben Sie Case ein, und navigieren Sie zur Registerkarte **Quellen** .</span><span class="sxs-lookup"><span data-stu-id="a58c7-106">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="a58c7-107">Klicken Sie auf **depotverwalter importieren** .</span><span class="sxs-lookup"><span data-stu-id="a58c7-107">Click **Import custodians**</span></span>

3. <span data-ttu-id="a58c7-108">Klicken Sie auf der Seite Flyout auf **leere Vorlage herunterladen** , um eine CSV-Depot Vorlagendatei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="a58c7-108">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="a58c7-109">Fügen Sie die Informationen zum Freiheitsentzug der CSV-Datei hinzu, und speichern Sie Sie auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="a58c7-109">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="a58c7-110">Im nächsten Abschnitt finden Sie Informationen zu den Eigenschaften in der CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="a58c7-110">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="a58c7-111">Klicken Sie auf der Registerkarte **Quellen** erneut auf **Verwalter importieren** .</span><span class="sxs-lookup"><span data-stu-id="a58c7-111">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="a58c7-112">Klicken Sie auf der Seite Flyout auf **Durchsuchen** , und laden Sie die CSV-Datei hoch.</span><span class="sxs-lookup"><span data-stu-id="a58c7-112">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="a58c7-113">Nachdem die CSV-Datei hochgeladen wurde, wird ein BulkAddCustodian-Auftrag erstellt und auf der Registerkarte **Aufträge** angezeigt. Der Auftrag überprüft die depotverwalter und die zugehörigen Datenquellen und fügt Sie dann der Registerkarte **Verwalter** auf der Seite **Quellen** der Anfrage hinzu.</span><span class="sxs-lookup"><span data-stu-id="a58c7-113">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="a58c7-114">Depot-CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="a58c7-114">Custodian CSV file</span></span>

<span data-ttu-id="a58c7-115">Nachdem Sie die CSV-Vorlage heruntergeladen haben, können Sie in jeder Zeile Verwalter und deren Datenquelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a58c7-115">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="a58c7-116">Achten Sie darauf, die Spaltennamen in der Kopfzeile nicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a58c7-116">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="a58c7-117">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="a58c7-117">Column name</span></span>|<span data-ttu-id="a58c7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a58c7-118">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="a58c7-119">**Depot Kontakt**</span><span class="sxs-lookup"><span data-stu-id="a58c7-119">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="a58c7-120">UPN-e-Mail der Depotbank.</span><span class="sxs-lookup"><span data-stu-id="a58c7-120">UPN email of custodian.</span></span> <span data-ttu-id="a58c7-121">Beispiel: Sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a58c7-121">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="a58c7-122">**Exchange aktiviert**</span><span class="sxs-lookup"><span data-stu-id="a58c7-122">**Exchange Enabled**</span></span> | <span data-ttu-id="a58c7-123">TRUE/false-Wert, ob depotverwalter Postfach hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a58c7-123">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="a58c7-124">**OneDrive aktiviert**</span><span class="sxs-lookup"><span data-stu-id="a58c7-124">**OneDrive Enabled**</span></span> | <span data-ttu-id="a58c7-125">TRUE/false-Wert, ob das OneDrive für Unternehmen Konto des Verwalters hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a58c7-125">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="a58c7-126">**Ist OnHold**</span><span class="sxs-lookup"><span data-stu-id="a58c7-126">**Is OnHold**</span></span>        | <span data-ttu-id="a58c7-127">TRUE/false-Wert, ob depotverwalter in den Haltebereich platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a58c7-127">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="a58c7-128">**Workload1-Typ**</span><span class="sxs-lookup"><span data-stu-id="a58c7-128">**Workload1 Type**</span></span>         | <span data-ttu-id="a58c7-129">Zeichenfolgenwert, der den Typ der Datenquelle angibt, die der Depotbank zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a58c7-129">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="a58c7-130">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a58c7-130">Possible values include:</span></span> <br /><span data-ttu-id="a58c7-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="a58c7-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="a58c7-132">**Workload1-Speicherort**</span><span class="sxs-lookup"><span data-stu-id="a58c7-132">**Workload1 Location**</span></span>     | <span data-ttu-id="a58c7-133">Je nach Arbeits Auslastungs wäre dies der Datenspeicherort Ihrer Arbeitsauslastung (beispielsweise die e-Mail-Adresse eines Exchange-Postfachs oder die URL für eine SharePoint-Website).</span><span class="sxs-lookup"><span data-stu-id="a58c7-133">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="a58c7-134">Hier ist ein Beispiel für eine CSV-Datei mit Depotinformationen:</span><span class="sxs-lookup"><span data-stu-id="a58c7-134">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="a58c7-135">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="a58c7-135">ContactEmail</span></span>      | <span data-ttu-id="a58c7-136">Exchange aktiviert</span><span class="sxs-lookup"><span data-stu-id="a58c7-136">Exchange Enabled</span></span> | <span data-ttu-id="a58c7-137">OneDrive aktiviert</span><span class="sxs-lookup"><span data-stu-id="a58c7-137">OneDrive Enabled</span></span> | <span data-ttu-id="a58c7-138">Ist OnHold</span><span class="sxs-lookup"><span data-stu-id="a58c7-138">Is OnHold</span></span> | <span data-ttu-id="a58c7-139">Workload1-Typ</span><span class="sxs-lookup"><span data-stu-id="a58c7-139">Workload1 Type</span></span> | <span data-ttu-id="a58c7-140">Workload1-Speicherort</span><span class="sxs-lookup"><span data-stu-id="a58c7-140">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="a58c7-141">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a58c7-141">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="a58c7-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="a58c7-142">TRUE</span></span>             | <span data-ttu-id="a58c7-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="a58c7-143">TRUE</span></span>             | <span data-ttu-id="a58c7-144">TRUE</span><span class="sxs-lookup"><span data-stu-id="a58c7-144">TRUE</span></span>      | <span data-ttu-id="a58c7-145">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="a58c7-145">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="a58c7-146">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a58c7-146">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="a58c7-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="a58c7-147">TRUE</span></span>             | <span data-ttu-id="a58c7-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="a58c7-148">TRUE</span></span>             | <span data-ttu-id="a58c7-149">TRUE</span><span class="sxs-lookup"><span data-stu-id="a58c7-149">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="a58c7-150">Depotbank und Datenquellen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a58c7-150">Custodian and data source validation</span></span>

<span data-ttu-id="a58c7-151">Wenn Sie die Depot-CSV-Datei hochladen, führt Advanced eDiscovery folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a58c7-151">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="a58c7-152">Überprüft die depotverwalter und deren Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="a58c7-152">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="a58c7-153">Indiziert alle Datenquellen für jede Depotstelle und platziert Sie in der Warteschleife (wenn die Eigenschaft ist OnHold auf true festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="a58c7-153">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="a58c7-154">Depot Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a58c7-154">Custodian validation</span></span>

<span data-ttu-id="a58c7-155">Derzeit wird nur das Importieren von Depot Inhabern unterstützt, die sich in Azure Active Directory (AAD) befinden.</span><span class="sxs-lookup"><span data-stu-id="a58c7-155">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="a58c7-156">Mithilfe des UPN-Werts in der Spalte **Kontakt-e-Mail** in der CSV-Datei validieren und finden Sie Verwalter.</span><span class="sxs-lookup"><span data-stu-id="a58c7-156">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="a58c7-157">Überprüfte Verwalter werden automatisch dem Fall hinzugefügt und auf der Registerkarte **Depot** auf der Seite **Quellen** der Anfrage aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a58c7-157">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="a58c7-158">Wenn eine Depotstelle nicht überprüft werden kann, werden Sie im Fehlerprotokoll für den BulkAddCustodian-Auftrag aufgeführt, der in der Anfrage auf der Registerkarte **Aufträge** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="a58c7-158">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="a58c7-159">Nicht validierte depotverwalter werden dem Fall nicht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a58c7-159">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="a58c7-160">Datenquellen Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a58c7-160">Data source validation</span></span>

<span data-ttu-id="a58c7-161">Nachdem die Verwalter überprüft und dem Fall hinzugefügt wurden, wird jede Datenquelle validiert, die einer Depotbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a58c7-161">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="a58c7-162">Wenn keine Datenquelle für eine Depotstelle gefunden werden kann, wird der Wert, der **nicht überprüft** wurde, in der Spalte **validiert** auf der Registerkarte **Depot** für diese Depotbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a58c7-162">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="a58c7-163">Remediation nicht validierter Datenquellen</span><span class="sxs-lookup"><span data-stu-id="a58c7-163">Remediating unvalidated data sources</span></span>

<span data-ttu-id="a58c7-164">So beheben Sie Verwalter mit nicht validierten Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="a58c7-164">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="a58c7-165">Wählen Sie auf der Registerkarte **depotverwalter** eine nicht validierte Depotbank aus.</span><span class="sxs-lookup"><span data-stu-id="a58c7-165">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="a58c7-166">Führen Sie auf der Seite depotverwalter einen Bildlauf zum Abschnitt **Datenquellen** durch, um die Datenquellen anzuzeigen, die der Depotbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a58c7-166">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="a58c7-167">Es werden sowohl validierte als auch nicht validierte Datenquellen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a58c7-167">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="a58c7-168">Klicken Sie im Abschnitt **Datenquellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a58c7-168">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="a58c7-169">Entfernen Sie auf der Seite **Speicherorte auswählen** eine nicht validierte Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="a58c7-169">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="a58c7-170">Klicken Sie auf der Seite **weitere Speicherorte auswählen** auf **Aktualisieren** , um zusätzliche Datenquellen für eine Depotstelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a58c7-170">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
