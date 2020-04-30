---
title: Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltestatus in einem eDiscovery-Fall im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: Ausführen eines Skripts zum schnellen Hinzufügen von Postfächern und OneDrive für Unternehmen Websites zu einem neuen Haltestatus, der einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist.
ms.openlocfilehash: 499a4ce3eb0f7be59f71565c0c841f323a364305
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942988"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a><span data-ttu-id="d96ae-103">Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltestatus in einem eDiscovery-Fall im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d96ae-103">Use a script to add users to a hold in an eDiscovery case in the Security & Compliance Center</span></span>

<span data-ttu-id="d96ae-104">Das Security & Compliance Center bietet viele Windows PowerShell-Cmdlets, mit denen Sie zeitaufwändige Aufgaben im Zusammenhang mit dem Erstellen und Verwalten von eDiscovery-Fällen automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="d96ae-104">The Security & Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="d96ae-105">Mit dem eDiscovery Case-Tool im Security & Compliance Center können Sie derzeit eine große Anzahl von Speicherorten für Depot Inhalte Zeit-und Vorbereitungs bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="d96ae-106">Vor dem Erstellen eines Haltestatus müssen Sie beispielsweise die URL für jede OneDrive für Unternehmen Website erfassen, die Sie in die Warteschleife stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d96ae-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="d96ae-107">Anschließend müssen Sie für jeden Benutzer, den Sie in die Warteschleife setzen möchten, das Postfach und die OneDrive für Unternehmen Website in das Archiv eintragen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="d96ae-108">In zukünftigen Versionen des Security & Compliance Center wird dies einfacher.</span><span class="sxs-lookup"><span data-stu-id="d96ae-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="d96ae-109">Bis dahin können Sie das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="d96ae-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="d96ae-110">Im Skript werden Sie zur Angabe des Namens der mysite-Domäne Ihrer Organisation aufgefordert (beispielsweise " **contoso** " https://contoso-my.sharepoint.com)in der URL, der Name eines vorhandenen eDiscovery-Falles, der Name des neuen haltebereichs, der dem Fall zugeordnet ist, eine Liste der e-Mail-Adressen der Benutzer, die Sie speichern möchten, und eine Suchabfrage, die verwendet werden soll, wenn Sie einen abfragebasierten Speicher</span><span class="sxs-lookup"><span data-stu-id="d96ae-110">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="d96ae-111">Das Skript ruft dann die URL für die OneDrive für Unternehmen Website für jeden Benutzer in der Liste ab, erstellt den neuen Haltestatus und fügt dann das Postfach und die OneDrive für Unternehmen Website für jeden Benutzer in der Liste in den Haltebereich ein.</span><span class="sxs-lookup"><span data-stu-id="d96ae-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="d96ae-112">Das Skript generiert auch Protokolldateien, die Informationen zum neuen Haltestatus enthalten.</span><span class="sxs-lookup"><span data-stu-id="d96ae-112">The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="d96ae-113">Hier sind die Schritte, um dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="d96ae-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="d96ae-114">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d96ae-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="d96ae-115">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="d96ae-115">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="d96ae-116">Schritt 3: Ausführen des Skripts zum Erstellen eines Haltestatus und Hinzufügen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="d96ae-116">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-begin"></a><span data-ttu-id="d96ae-117">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="d96ae-117">Before you begin</span></span>

- <span data-ttu-id="d96ae-118">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center und SharePoint Online globaler Administrator sein, um das Skript in Schritt 3 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span> <span data-ttu-id="d96ae-119">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d96ae-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="d96ae-120">Es können maximal 1.000 Postfächer und 100-Websites zu einem Haltestatus hinzugefügt werden, der einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d96ae-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="d96ae-121">Wenn Sie davon ausgehen, dass jeder Benutzer, den Sie in der Warteschleife platzieren möchten, über eine OneDrive für Unternehmen Website verfügt, können Sie mithilfe des Skripts in diesem Artikel maximal 100 Benutzer zu einem Haltestatus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="d96ae-122">Achten Sie darauf, dass Sie die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, in demselben Ordner speichern.</span><span class="sxs-lookup"><span data-stu-id="d96ae-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="d96ae-123">Dadurch wird das Ausführen des Skripts vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="d96ae-123">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="d96ae-124">Das Skript fügt die Liste der Benutzer zu einem neuen Haltestatus hinzu, der einem vorhandenen Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d96ae-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="d96ae-125">Stellen Sie sicher, dass der Fall, dem Sie den Haltebereich zuordnen möchten, erstellt wird, bevor Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="d96ae-126">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="d96ae-126">The script includes minimal error handling.</span></span> <span data-ttu-id="d96ae-127">Der primäre Zweck besteht darin, das Postfach und die OneDrive für Unternehmen Website jedes Benutzers schnell und einfach aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="d96ae-127">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="d96ae-p108">Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d96ae-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="d96ae-133">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d96ae-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="d96ae-134">Der erste Schritt besteht darin, die SharePoint Online-Verwaltungsshell zu installieren, falls Sie noch nicht auf Ihrem lokalen Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d96ae-134">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="d96ae-135">Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen Sie installieren, da Sie Voraussetzungen enthält, die für das in Schritt 3 ausgeführte Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d96ae-135">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="d96ae-136">Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive für Unternehmen Websites abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-136">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="d96ae-137">Wechseln Sie zum [Einrichten der SharePoint Online Verwaltungsshell Windows PowerShell Umgebung](https://go.microsoft.com/fwlink/p/?LinkID=286318) , und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online-Verwaltungsshell auf dem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d96ae-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="d96ae-138">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="d96ae-138">Step 2: Generate a list of users</span></span>

<span data-ttu-id="d96ae-139">Mit dem Skript in Schritt 3 wird ein Haltestatus erstellt, der einem eDiscovery-Fall zugeordnet ist, sowie das Hinzufügen der Postfächer und OneDrive für Unternehmen Websites einer Liste von Benutzern in den Haltebereich.</span><span class="sxs-lookup"><span data-stu-id="d96ae-139">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="d96ae-140">Sie können die e-Mail-Adressen einfach in eine Textdatei eingeben oder einen Befehl in Windows PowerShell ausführen, um eine Liste mit e-Mail-Adressen zu erhalten und diese in einer Datei zu speichern (in demselben Ordner, in dem Sie das Skript in Schritt 3 speichern werden).</span><span class="sxs-lookup"><span data-stu-id="d96ae-140">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="d96ae-141">Es folgt ein PowerShell-Befehl (den Sie mit der Remote-PowerShell ausführen, die mit Ihrer Exchange Online Organisation verbunden ist), um eine Liste der e-Mail-Adressen für alle Benutzer in Ihrer Organisation abzurufen und in einer Textdatei mit dem Namen "HoldUsers. txt" zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d96ae-141">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="d96ae-142">Nachdem Sie diesen Befehl ausgeführt haben, öffnen Sie die Textdatei, und entfernen Sie die Kopfzeile, die `PrimarySmtpAddress`den Eigenschaftennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="d96ae-142">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="d96ae-143">Entfernen Sie dann alle e-Mail-Adressen außer denjenigen für die Benutzer, die Sie dem Haltestatus hinzufügen möchten, den Sie in Schritt 3 erstellen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-143">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="d96ae-144">Stellen Sie sicher, dass keine leeren Zeilen vor oder nach der Liste der e-Mail-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d96ae-144">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="d96ae-145">Schritt 3: Ausführen des Skripts zum Erstellen eines Haltestatus und Hinzufügen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="d96ae-145">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="d96ae-146">Wenn Sie das Skript in diesem Schritt ausführen, werden Sie aufgefordert, die folgenden Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="d96ae-146">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="d96ae-147">Stellen Sie sicher, dass diese Informationen vor dem Ausführen des Skripts verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d96ae-147">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="d96ae-148">**Ihre Benutzeranmeldeinformationen** – das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit dem Security & Compliance Center mit Remote-PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-148">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="d96ae-149">Außerdem werden diese Anmeldeinformationen für den Zugriff auf SharePoint Online verwendet, um die OneDrive für Unternehmen-URLs für die Liste der Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-149">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="d96ae-150">**Name Ihrer mysite-Domäne** : die mysite-Domäne ist die Domäne, die alle OneDrive für Unternehmen Websites in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="d96ae-150">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="d96ae-151">Wenn beispielsweise die URL für Ihre mysite-Domäne lautet **https://contoso-my.sharepoint.com**, geben `contoso` Sie ein, wenn Sie vom Skript nach dem Namen Ihrer mysite-Domäne gefragt werden.</span><span class="sxs-lookup"><span data-stu-id="d96ae-151">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="d96ae-152">**Name der Groß-/Kleinschreibung** -der Name eines vorhandenen Falls.</span><span class="sxs-lookup"><span data-stu-id="d96ae-152">**Name of the case** - The name of an existing case.</span></span> <span data-ttu-id="d96ae-153">Mit dem Skript wird ein neuer Haltebereich erstellt, der diesem Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d96ae-153">The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="d96ae-154">**Name des Haltestatus** -der Name des haltebereichs, der vom Skript erstellt und mit dem angegebenen Fall verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="d96ae-154">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="d96ae-155">**Suchabfrage für einen abfragebasierten halte** Status-Sie können einen abfragebasierten Speicher erstellen, sodass nur der Inhalt, der die angegebenen Suchkriterien erfüllt, in der Warteschleife gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d96ae-155">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="d96ae-156">Um den gesamten Inhalt aufzubewahren, drücken Sie die **EINGABETASTE** , wenn Sie zur Eingabe einer Suchabfrage aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d96ae-156">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="d96ae-157">Gibt an, ob das Skript aktiviert **werden soll oder nicht,** nachdem es erstellt wurde, oder wenn das Skript den Haltebereich erstellen kann, ohne es zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d96ae-157">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="d96ae-158">Wenn das Skript nicht aktiviert ist, können Sie es später im Security & Compliance Center aktivieren oder indem Sie die folgenden PowerShell-Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="d96ae-158">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="d96ae-159">**Name der Textdatei mit der Liste der Benutzer** -der Name der Textdatei aus Schritt 2, die die Liste der Benutzer enthält, die dem Haltestatus hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-159">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="d96ae-160">Wenn sich diese Datei im gleichen Ordner wie das Skript befindet, geben Sie einfach den Namen der Datei ein (beispielsweise "HoldUsers. txt").</span><span class="sxs-lookup"><span data-stu-id="d96ae-160">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="d96ae-161">Wenn sich die Textdatei in einem anderen Ordner befindet, geben Sie den vollständigen Pfadnamen der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="d96ae-161">If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="d96ae-162">Nachdem Sie die Informationen gesammelt haben, für die das Skript Sie auffordert, besteht der letzte Schritt darin, das Skript auszuführen, um den neuen Haltestatus zu erstellen und ihm Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-162">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="d96ae-163">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von. ps1; Beispiel: `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="d96ae-163">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
  ```powershell
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
      }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. <span data-ttu-id="d96ae-164">Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="d96ae-164">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="d96ae-165">Ausführen des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d96ae-165">Run the script; for example:</span></span>
    
      ```powershell
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="d96ae-166">Geben Sie die Informationen ein, die Sie vom Skript angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="d96ae-166">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="d96ae-167">Das Skript stellt eine Verbindung mit der Security & Compliance Center PowerShell her und erstellt dann den neuen Haltebereich im eDiscovery-Fall und fügt die Postfächer und OneDrive für Unternehmen für die Benutzer in der Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="d96ae-167">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="d96ae-168">Sie können den Fall auf der **eDiscovery** -Seite im Security & Compliance Center aufrufen, um den neuen Haltestatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d96ae-168">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="d96ae-169">Nachdem das Skript ausgeführt wurde, werden die folgenden Protokolldateien erstellt und in dem Ordner gespeichert, in dem sich das Skript befindet.</span><span class="sxs-lookup"><span data-stu-id="d96ae-169">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="d96ae-170">**LocationsOnHold. txt** – enthält eine Liste von Postfächern und OneDrive für Unternehmen Websites, die vom Skript erfolgreich gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="d96ae-170">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="d96ae-171">**LocationsNotOnHold. txt** – enthält eine Liste von Postfächern und OneDrive für Unternehmen Websites, die das Skript nicht in der Warteschleife aufbewahren konnte.</span><span class="sxs-lookup"><span data-stu-id="d96ae-171">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="d96ae-172">Wenn ein Benutzer über ein Postfach verfügt, jedoch nicht über einen OneDrive für Unternehmen-Standort, wird der Benutzer in die Liste der OneDrive für Unternehmen-Websites aufgenommen, die nicht in der Warteschleife gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="d96ae-172">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="d96ae-173">**GetCaseHoldPolicy. txt** – enthält die Ausgabe des Cmdlets **Get-CaseHoldPolicy** für den neuen Haltestatus, den das Skript nach dem Erstellen des neuen Haltestatus ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="d96ae-173">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="d96ae-174">Die Informationen, die von diesem Cmdlet zurückgegeben werden, umfassen eine Liste der Benutzer, deren Postfächer und OneDrive für Unternehmen Websites gespeichert wurden, und ob der Haltebereich aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d96ae-174">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="d96ae-175">**GetCaseHoldRule. txt** – enthält die Ausgabe des Cmdlets **Get-CaseHoldRule** für den neuen Haltestatus, den das Skript nach dem Erstellen des neuen Haltestatus ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="d96ae-175">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="d96ae-176">Die Informationen, die von diesem Cmdlet zurückgegeben werden, enthalten die Suchabfrage, wenn Sie das Skript zum Erstellen eines abfragebasierten haltebereichs verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d96ae-176">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
