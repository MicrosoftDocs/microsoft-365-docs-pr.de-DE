---
title: Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltestatus in einem zentralen eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
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
ms.custom: seo-marvel-apr2020
description: Informationen zum Ausführen eines Skripts zum Hinzufügen von Postfächern & OneDrive für Unternehmen Websites zu einem neuen Haltestatus, der einem eDiscovery-Fall im Microsoft 365 Compliance Center zugeordnet ist.
ms.openlocfilehash: 31c3bfef4eda4802618020f607bc7706780f3629
ms.sourcegitcommit: 4a9e1b6851b988bcd31e87b184fc185be949840d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49525614"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="c4f92-103">Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltestatus in einem zentralen eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="c4f92-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="c4f92-104">Security & Compliance Center PowerShell stellt Cmdlets bereit, mit denen Sie zeitaufwändige Aufgaben im Zusammenhang mit dem Erstellen und Verwalten von eDiscovery-Fällen automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="c4f92-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="c4f92-105">Unter Verwendung des zentralen eDiscovery-Falls im Security & Compliance Center wird derzeit eine große Anzahl von Speicherorten für Depot Inhalte Zeit-und Vorbereitungs bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c4f92-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="c4f92-106">Vor dem Erstellen eines Haltestatus müssen Sie beispielsweise die URL für jede OneDrive für Unternehmen Website erfassen, die Sie in die Warteschleife stellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c4f92-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="c4f92-107">Anschließend müssen Sie für jeden Benutzer, den Sie in die Warteschleife setzen möchten, das Postfach und die OneDrive für Unternehmen Website in das Archiv eintragen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="c4f92-108">Sie können das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="c4f92-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="c4f92-109">Im Skript werden Sie zur Angabe des Namens der meine Website Domäne Ihrer Organisation aufgefordert (beispielsweise `contoso` in der URL https://contoso-my.sharepoint.com) , dem Namen eines vorhandenen eDiscovery-Falls, dem Namen des neuen haltebereichs, der dem Fall zugeordnet ist, einer Liste von e-Mail-Adressen der Benutzer, die Sie in die Warteschleife setzen möchten, und einer Suchabfrage, die verwendet werden soll, wenn Sie einen abfragebasierten Speicher erstellen möchten</span><span class="sxs-lookup"><span data-stu-id="c4f92-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="c4f92-110">Das Skript ruft dann die URL für die OneDrive für Unternehmen Website für jeden Benutzer in der Liste ab, erstellt den neuen Haltestatus und fügt dann das Postfach und die OneDrive für Unternehmen Website für jeden Benutzer in der Liste in den Haltebereich ein.</span><span class="sxs-lookup"><span data-stu-id="c4f92-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="c4f92-111">Das Skript generiert auch Protokolldateien, die Informationen zum neuen Haltestatus enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4f92-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="c4f92-112">Hier sind die Schritte, um dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="c4f92-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="c4f92-113">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="c4f92-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="c4f92-114">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="c4f92-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="c4f92-115">Schritt 3: Ausführen des Skripts zum Erstellen eines Haltestatus und Hinzufügen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="c4f92-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="c4f92-116">Vor dem Hinzufügen von Benutzern zu einem Haltestatus</span><span class="sxs-lookup"><span data-stu-id="c4f92-116">Before you add users to a hold</span></span>

- <span data-ttu-id="c4f92-117">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center und SharePoint Online Administrator sein, um das Skript in Schritt 3 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="c4f92-118">Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c4f92-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="c4f92-119">Es können maximal 1.000 Postfächer und 100-Websites zu einem Haltestatus hinzugefügt werden, der einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c4f92-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="c4f92-120">Wenn Sie davon ausgehen, dass jeder Benutzer, den Sie in der Warteschleife platzieren möchten, über eine OneDrive für Unternehmen Website verfügt, können Sie mithilfe des Skripts in diesem Artikel maximal 100 Benutzer zu einem Haltestatus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="c4f92-121">Achten Sie darauf, dass Sie die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, in demselben Ordner speichern.</span><span class="sxs-lookup"><span data-stu-id="c4f92-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="c4f92-122">Dadurch wird das Ausführen des Skripts vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="c4f92-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="c4f92-123">Das Skript fügt die Liste der Benutzer zu einem neuen Haltestatus hinzu, der einem vorhandenen Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c4f92-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="c4f92-124">Stellen Sie sicher, dass der Fall, dem Sie den Haltebereich zuordnen möchten, erstellt wird, bevor Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="c4f92-125">Das Skript in diesem Artikel unterstützt die moderne Authentifizierung beim Herstellen einer Verbindung mit Security & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4f92-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="c4f92-126">Sie können das Skript wie folgt verwenden, wenn Sie eine Microsoft 365-oder eine Microsoft 365 gcc-Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="c4f92-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="c4f92-127">Wenn Sie eine Office 365 Deutschland-Organisation, eine Microsoft 365 gcc High Organization oder eine Microsoft 365 DoD-Organisation sind, müssen Sie das Skript bearbeiten, damit es erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c4f92-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="c4f92-128">Insbesondere müssen Sie die Linie bearbeiten `Connect-IPPSSession` und die Parameter *ConnectionUri* und *AzureADAuthorizationEndpointUri* (und die entsprechenden Werte für Ihren Organisationstyp) verwenden, um eine Verbindung mit Security & Compliance Center PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="c4f92-129">Weitere Informationen finden Sie in den Beispielen unter [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="c4f92-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="c4f92-130">Jedes Mal, wenn Sie das Skript ausführen, werden neue Security & Compliance PowerShell und SharePoint Online Management Shell-Sitzungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="c4f92-130">Each time you run the script, new Security & Compliance PowerShell and SharePoint Online Management Shell sessions are created.</span></span> <span data-ttu-id="c4f92-131">Sie können also alle für Sie verfügbaren PowerShell-Sitzungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4f92-131">So you could use up all the PowerShell sessions available to you.</span></span> <span data-ttu-id="c4f92-132">Um dies zu verhindern, können Sie die folgenden Befehle ausführen, um die Verbindung der aktiven PowerShell-Sitzungen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-132">To prevent this from happening, you can run the following commands to disconnect your active PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

   ```powershell
   Disconnect-SPOService
   ```

- <span data-ttu-id="c4f92-133">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="c4f92-133">The script includes minimal error handling.</span></span> <span data-ttu-id="c4f92-134">Der primäre Zweck besteht darin, das Postfach und die OneDrive für Unternehmen Website jedes Benutzers schnell und einfach aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="c4f92-134">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="c4f92-p110">Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c4f92-p110">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="c4f92-140">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="c4f92-140">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="c4f92-141">Der erste Schritt besteht darin, die SharePoint Online-Verwaltungsshell zu installieren, falls Sie noch nicht auf Ihrem lokalen Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c4f92-141">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="c4f92-142">Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen Sie installieren, da Sie Voraussetzungen enthält, die für das in Schritt 3 ausgeführte Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c4f92-142">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="c4f92-143">Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive für Unternehmen Websites abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-143">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="c4f92-144">Wechseln Sie zum [Einrichten der SharePoint Online Verwaltungsshell Windows PowerShell Umgebung](https://go.microsoft.com/fwlink/p/?LinkID=286318) , und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online-Verwaltungsshell auf dem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c4f92-144">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="c4f92-145">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="c4f92-145">Step 2: Generate a list of users</span></span>

<span data-ttu-id="c4f92-146">Mit dem Skript in Schritt 3 wird ein Haltestatus erstellt, der einem eDiscovery-Fall zugeordnet ist, sowie das Hinzufügen der Postfächer und OneDrive für Unternehmen Websites einer Liste von Benutzern in den Haltebereich.</span><span class="sxs-lookup"><span data-stu-id="c4f92-146">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="c4f92-147">Sie können die e-Mail-Adressen einfach in eine Textdatei eingeben oder einen Befehl in Windows PowerShell ausführen, um eine Liste mit e-Mail-Adressen zu erhalten und diese in einer Datei zu speichern (in demselben Ordner, in dem Sie das Skript in Schritt 3 speichern werden).</span><span class="sxs-lookup"><span data-stu-id="c4f92-147">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="c4f92-148">Es folgt ein PowerShell-Befehl (den Sie mit der Remote-PowerShell ausführen, die mit Ihrer Exchange Online Organisation verbunden ist), um eine Liste der e-Mail-Adressen für alle Benutzer in Ihrer Organisation abzurufen und in einer Textdatei namens "HoldUsers.txt" zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c4f92-148">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="c4f92-149">Nachdem Sie diesen Befehl ausgeführt haben, öffnen Sie die Textdatei, und entfernen Sie die Kopfzeile, die den Eigenschaftennamen enthält  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="c4f92-149">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="c4f92-150">Entfernen Sie dann alle e-Mail-Adressen außer denjenigen für die Benutzer, die Sie dem Haltestatus hinzufügen möchten, den Sie in Schritt 3 erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-150">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="c4f92-151">Stellen Sie sicher, dass keine leeren Zeilen vor oder nach der Liste der e-Mail-Adressen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c4f92-151">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="c4f92-152">Schritt 3: Ausführen des Skripts zum Erstellen eines Haltestatus und Hinzufügen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="c4f92-152">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="c4f92-153">Wenn Sie das Skript in diesem Schritt ausführen, werden Sie aufgefordert, die folgenden Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c4f92-153">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="c4f92-154">Stellen Sie sicher, dass diese Informationen vor dem Ausführen des Skripts verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c4f92-154">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="c4f92-155">**Ihre Benutzeranmeldeinformationen:** Das Skript verwendet Ihre Anmeldeinformationen zum Herstellen einer Verbindung mit dem Security & Compliance Center mit Remote-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4f92-155">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="c4f92-156">Außerdem werden diese Anmeldeinformationen für den Zugriff auf SharePoint Online verwendet, um die OneDrive für Unternehmen-URLs für die Liste der Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-156">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="c4f92-157">**Name Ihrer meine Website Domäne:** Die meine Website Domäne ist die Domäne, die alle OneDrive für Unternehmen Websites in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="c4f92-157">**Name of your My Site domain:** The My Site domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="c4f92-158">Wenn beispielsweise die URL für Ihre meine Website Domäne lautet **https://contoso-my.sharepoint.com** , geben Sie ein,  `contoso` Wenn Sie vom Skript aufgefordert werden, den Namen Ihrer meine Website Domäne einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c4f92-158">For example, if the URL for your My Site domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your My Site domain.</span></span>

- <span data-ttu-id="c4f92-159">**Name der Anfrage:** Der Name eines vorhandenen Falls.</span><span class="sxs-lookup"><span data-stu-id="c4f92-159">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="c4f92-160">Mit dem Skript wird ein neuer Haltebereich erstellt, der diesem Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c4f92-160">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="c4f92-161">**Name des haltebereichs:** Der Name des haltebereichs, der vom Skript erstellt und mit dem angegebenen Fall verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="c4f92-161">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="c4f92-162">**Suchabfrage für einen abfragebasierten Haltestatus:** Sie können einen abfragebasierten Haltebereich erstellen, sodass nur der Inhalt, der die angegebenen Suchkriterien erfüllt, in der Warteschleife gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c4f92-162">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="c4f92-163">Um den gesamten Inhalt aufzubewahren, drücken Sie die **EINGABETASTE** , wenn Sie zur Eingabe einer Suchabfrage aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c4f92-163">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="c4f92-164">**Einschalten des Haltestatus oder nicht:** Sie können festlegen, dass das Skript den Haltestatus einschaltet, nachdem es erstellt wurde, oder das Skript den Haltebereich erstellen kann, ohne es zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c4f92-164">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="c4f92-165">Wenn das Skript nicht aktiviert ist, können Sie es später im Security & Compliance Center aktivieren oder indem Sie die folgenden PowerShell-Befehle ausführen:</span><span class="sxs-lookup"><span data-stu-id="c4f92-165">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="c4f92-166">**Name der Textdatei mit der Liste der Benutzer** -der Name der Textdatei aus Schritt 2, die die Liste der Benutzer enthält, die dem Haltestatus hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-166">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="c4f92-167">Wenn sich diese Datei im gleichen Ordner wie das Skript befindet, geben Sie einfach den Namen der Datei ein (beispielsweise HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="c4f92-167">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="c4f92-168">Wenn sich die Textdatei in einem anderen Ordner befindet, geben Sie den vollständigen Pfadnamen der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="c4f92-168">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="c4f92-169">Nachdem Sie die Informationen gesammelt haben, für die das Skript Sie auffordert, besteht der letzte Schritt darin, das Skript auszuführen, um den neuen Haltestatus zu erstellen und ihm Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-169">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="c4f92-170">Speichern Sie den folgenden Text in einer Windows PowerShell Skriptdatei unter Verwendung eines filename-Suffixes von `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="c4f92-170">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="c4f92-171">Beispiel: `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c4f92-171">For example, `AddUsersToHold.ps1`.</span></span>

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
   write-host "***********************************************"
   " "
   # Connect to SCC PowerShell using modern authentication
   if (!$SccSession)
   {
     Import-Module ExchangeOnlineManagement
     Connect-IPPSSession
   }
   # Get user credentials to connect to SPO Management Shell
   $credentials = Get-Credential -Message "Type your credentials again to connect to SharePoint Online Management Shell"
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

2. <span data-ttu-id="c4f92-172">Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="c4f92-172">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="c4f92-173">Ausführen des Skripts; Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c4f92-173">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="c4f92-174">Geben Sie die Informationen ein, die Sie vom Skript angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="c4f92-174">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="c4f92-175">Das Skript stellt eine Verbindung mit der Security & Compliance Center PowerShell her und erstellt dann den neuen Haltebereich im eDiscovery-Fall und fügt die Postfächer und OneDrive für Unternehmen für die Benutzer in der Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4f92-175">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="c4f92-176">Sie können den Fall auf der **eDiscovery** -Seite im Security & Compliance Center aufrufen, um den neuen Haltestatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c4f92-176">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="c4f92-177">Nachdem das Skript ausgeführt wurde, werden die folgenden Protokolldateien erstellt und in dem Ordner gespeichert, in dem sich das Skript befindet.</span><span class="sxs-lookup"><span data-stu-id="c4f92-177">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="c4f92-178">**LocationsOnHold.txt:** Enthält eine Liste von Postfächern und OneDrive für Unternehmen Websites, die das Skript erfolgreich in der Warteschleife gespeichert hat.</span><span class="sxs-lookup"><span data-stu-id="c4f92-178">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="c4f92-179">**LocationsNotOnHold.txt:** Enthält eine Liste von Postfächern und OneDrive für Unternehmen Websites, die das Skript nicht in der Warteschleife platziert hat.</span><span class="sxs-lookup"><span data-stu-id="c4f92-179">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="c4f92-180">Wenn ein Benutzer über ein Postfach verfügt, jedoch nicht über einen OneDrive für Unternehmen-Standort, wird der Benutzer in die Liste der OneDrive für Unternehmen-Websites aufgenommen, die nicht in der Warteschleife gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="c4f92-180">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="c4f92-181">**GetCaseHoldPolicy.txt:** Enthält die Ausgabe des **Get-CaseHoldPolicy-** Cmdlets für den neuen Haltestatus, den das Skript nach dem Erstellen des neuen Haltestatus ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="c4f92-181">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="c4f92-182">Die Informationen, die von diesem Cmdlet zurückgegeben werden, umfassen eine Liste der Benutzer, deren Postfächer und OneDrive für Unternehmen Websites gespeichert wurden, und ob der Haltebereich aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c4f92-182">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="c4f92-183">**GetCaseHoldRule.txt:** Enthält die Ausgabe des **Get-CaseHoldRule-** Cmdlets für den neuen Haltestatus, den das Skript nach dem Erstellen des neuen Haltestatus ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="c4f92-183">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="c4f92-184">Die Informationen, die von diesem Cmdlet zurückgegeben werden, enthalten die Suchabfrage, wenn Sie das Skript zum Erstellen eines abfragebasierten haltebereichs verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c4f92-184">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
