---
title: DSGVO
description: Technische Unterstützung von Microsoft– FASTTRACK-MIGRATIONSTOOLSET ZUM ÜBERMITTELN VON LÖSCHANFORDERUNGEN
keywords: FastTrack-Migration, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
author: MohitKumar
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 6fdb06cf8a5e1141d33959c814dc94ddd979546d
ms.sourcegitcommit: df0ed4e9097acfee3cb128882102b3081144eb68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938740"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="29058-104">FastTrack-Migrationstoolset zum Übermitteln von Löschanforderungen</span><span class="sxs-lookup"><span data-stu-id="29058-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="29058-105">Zweck des Toolsets</span><span class="sxs-lookup"><span data-stu-id="29058-105">Toolset purpose</span></span>

<span data-ttu-id="29058-p101">Für den Fall, dass Sie als Kunde derzeit an FastTrack-Migrationen beteiligt sind, wird durch das Löschen des Office 365-Benutzerkontos nicht die Datenkopie im Besitz des Microsoft FastTrack-Teams gelöscht, die ausschließlich für das Abschließen der Migration beibehalten wird. Wenn Sie möchten dass das Microsoft FastTrack-Team während der Migration auch die Datenkopie löscht, übermitteln Sie eine diesbezügliche Anforderung über dieses Toolset. Im normalen Geschäftsverlauf löscht Microsoft FastTrack alle Datenkopien, sobald die Migration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="29058-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this toolset. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span> 

### <a name="supported-platforms"></a><span data-ttu-id="29058-109">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="29058-109">Supported platforms</span></span>
<span data-ttu-id="29058-p102">Microsoft unterstützt die erste Version dieses Toolsets auf der Windows-Plattform und der PowerShell-Konsole. Die folgenden bekannten Plattformen werden von diesem Toolset unterstützt:</span><span class="sxs-lookup"><span data-stu-id="29058-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="29058-112">***Tabelle 1 – Von diesem Toolset unterstützte Plattformen***</span><span class="sxs-lookup"><span data-stu-id="29058-112">***Table 1 - Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="29058-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="29058-113">**Windows 7**</span></span>|<span data-ttu-id="29058-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="29058-114">**Windows 8**</span></span>|<span data-ttu-id="29058-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="29058-115">**Windows 10**</span></span>|<span data-ttu-id="29058-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="29058-116">**Windows Server 2012**</span></span>|<span data-ttu-id="29058-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="29058-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="29058-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="29058-118">PS 5.0</span></span>|<span data-ttu-id="29058-119">Nicht</span><span class="sxs-lookup"><span data-stu-id="29058-119">Not</span></span><br/><span data-ttu-id="29058-120">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-120">Supported</span></span>|<span data-ttu-id="29058-121">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-121">Supported</span></span>|<span data-ttu-id="29058-122">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-122">Supported</span></span>|<span data-ttu-id="29058-123">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-123">Supported</span></span>|<span data-ttu-id="29058-124">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-124">Supported</span></span>|
|<span data-ttu-id="29058-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="29058-125">PS 5.1</span></span>|<span data-ttu-id="29058-126">Nicht</span><span class="sxs-lookup"><span data-stu-id="29058-126">Not</span></span><br/><span data-ttu-id="29058-127">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-127">Supported</span></span>|<span data-ttu-id="29058-128">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-128">Supported</span></span>|<span data-ttu-id="29058-129">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-129">Supported</span></span>|<span data-ttu-id="29058-130">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-130">Supported</span></span>|<span data-ttu-id="29058-131">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="29058-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="29058-132">Abrufen des Toolsets</span><span class="sxs-lookup"><span data-stu-id="29058-132">Obtaining the toolset</span></span>

<span data-ttu-id="29058-p103">Dieses Toolset ist im PowerShell-Katalog in der PowerShell-Konsolenanwendung verfügbar. Zum Suchen und Laden dieses Cmdlet-Moduls öffnen Sie zunächst PowerShell im Administratormodus, damit die erforderlichen Berechtigungen zum Installieren des Moduls vorhanden sind. Wenn Sie PowerShell zum ersten Mal verwenden, geben Sie auf der Windows-Taskleiste im Suchfeld „PowerShell“ ein. Wählen Sie die Konsole mit einem Rechtsklick aus, wählen Sie **als Administrator ausführen**, und klicken Sie dann auf **Ja**, um Windows PowerShell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="29058-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell – Als Administrator ausführen](media/fasttrack-powershell_image.png)

![PowerShell – Änderungen durch App zulassen](media/fasttrack-run-powershell_image.png)

<span data-ttu-id="29058-p104">Nachdem die Konsole geöffnet wurde, müssen Sie Berechtigungen für die Skriptausführung festlegen. Geben Sie den folgenden Befehl ein, um die Ausführung der Skripts zuzulassen: „Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process“</span><span class="sxs-lookup"><span data-stu-id="29058-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’</span></span>

<span data-ttu-id="29058-141">Sie werden aufgefordert, diese Aktion zu bestätigen, da der Administrator den Bereich nach eigenem Ermessen ändern kann...</span><span class="sxs-lookup"><span data-stu-id="29058-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion..</span></span>

<span data-ttu-id="29058-142">***Festlegen der Ausführungsrichtlinie***</span><span class="sxs-lookup"><span data-stu-id="29058-142">***Set Execution Policy***</span></span>

![Festlegen einer Änderung der Ausführungsrichtlinie in PowerShell](media/powershell-set-execution-policy_image.png)

<span data-ttu-id="29058-144">Da die Konsole nun so eingerichtet ist, dass die Skriptausführung zulässig ist, führen Sie diesen Befehl aus, um das Modul zu installieren:</span><span class="sxs-lookup"><span data-stu-id="29058-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="29058-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="29058-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="29058-146">Voraussetzungen für Modul</span><span class="sxs-lookup"><span data-stu-id="29058-146">Prerequisites for module</span></span>
<span data-ttu-id="29058-p105">Zur erfolgreichen Ausführung dieses Moduls müssen Sie u.U. abhängige Module für die Verwendung installieren, falls diese nicht bereits installiert sind. Möglicherweise müssen Sie PowerShell neu starten.</span><span class="sxs-lookup"><span data-stu-id="29058-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="29058-149">Zum Übermitteln einer Datensubjektanforderung müssen Sie sich zuerst mithilfe Ihrer Anmeldeinformationen für Office 365 anmelden – durch Eingabe der richtigen Anmeldeinformationen wird Ihr Status als globaler Administrator überprüft, und Mandanteninformationen werden erfasst.</span><span class="sxs-lookup"><span data-stu-id="29058-149">In order to submit a DSR, you must first login using your Office 365 credentials – entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="29058-150">**Login-FastTrackAccount -ApiKey: \<Vom FastTrack-MVM bereitgestellter API-Schlüssel\>**</span><span class="sxs-lookup"><span data-stu-id="29058-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="29058-151">Nach der erfolgreichen Anmeldung werden die Anmeldeinformationen und der Schlüssel zur Verwendung mit FastTrack-Modulen für den Rest der aktuellen PowerShell-Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="29058-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="29058-152">Wenn Sie eine Verbindung mit einer Cloudumgebung für andere als kommerzielle Zwecke herstellen müssen, muss dem *Login*-Befehl *-Environment* mit einer der folgenden gültigen Umgebungen hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="29058-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will needed to be added to *Login* command with one of the following valid environments:</span></span>
- <span data-ttu-id="29058-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="29058-153">AzureCloud</span></span>
- <span data-ttu-id="29058-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="29058-154">AzureChinaCloud</span></span>
- <span data-ttu-id="29058-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="29058-155">AzureGermanCloud</span></span>
- <span data-ttu-id="29058-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="29058-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="29058-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <Cloudumgebung\>**</span><span class="sxs-lookup"><span data-stu-id="29058-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="29058-158">Führen Sie den folgenden Befehl aus, um eine Anforderung betroffener Personen zu übermitteln: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="29058-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="29058-p106">Bei Erfolg gibt das Cmdlet ein Transaktions-ID-Objekt zurück. Bewahren Sie die Transaktions-ID auf.</span><span class="sxs-lookup"><span data-stu-id="29058-p106">On success – the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="29058-161">Überprüfen des Status einer Anforderungstransaktion</span><span class="sxs-lookup"><span data-stu-id="29058-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="29058-162">Führen Sie die folgende Funktion mit der zuvor ermittelten Transaktions-ID aus: Get-FastTrackGdprDsrRequest -TransactionID: “IhreTransaktionsID”</span><span class="sxs-lookup"><span data-stu-id="29058-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="29058-163">Transaktionstatuscodes</span><span class="sxs-lookup"><span data-stu-id="29058-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="29058-164">**Transaktion**</span><span class="sxs-lookup"><span data-stu-id="29058-164">**Transaction**</span></span> |<span data-ttu-id="29058-165">**Status**</span><span class="sxs-lookup"><span data-stu-id="29058-165">**Status**</span></span>|
|<span data-ttu-id="29058-166">**Erstellt**</span><span class="sxs-lookup"><span data-stu-id="29058-166">**Created**</span></span> |<span data-ttu-id="29058-167">Anforderung wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="29058-167">Request has been created</span></span>|
|<span data-ttu-id="29058-168">**Fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="29058-168">**Failed**</span></span>|<span data-ttu-id="29058-169">Fehler beim Erstellen der Anforderung. Übermitteln Sie sie erneut, oder wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="29058-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="29058-170">**Abgeschlossen**</span><span class="sxs-lookup"><span data-stu-id="29058-170">**Completed**</span></span>|<span data-ttu-id="29058-171">Anforderung wurde abgeschlossen und bereinigt</span><span class="sxs-lookup"><span data-stu-id="29058-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="29058-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29058-172">Learn more</span></span>
[<span data-ttu-id="29058-173">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="29058-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)