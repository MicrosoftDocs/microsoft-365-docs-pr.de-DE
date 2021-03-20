---
title: Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltebereich in einem Core eDiscovery-Fall
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
description: Erfahren Sie, wie Sie ein Skript ausführen, um Postfächer & OneDrive for & einem neuen Archiv hinzuzufügen, das einem eDiscovery-Fall im Microsoft 365 Compliance Center zugeordnet ist.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909915"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="796e4-103">Verwenden eines Skripts zum Hinzufügen von Benutzern zu einem Haltebereich in einem Core eDiscovery-Fall</span><span class="sxs-lookup"><span data-stu-id="796e4-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="796e4-104">Security & Compliance Center PowerShell bietet Cmdlets, mit denen Sie zeitaufwändige Aufgaben im Zusammenhang mit dem Erstellen und Verwalten von eDiscovery-Fällen automatisieren können.</span><span class="sxs-lookup"><span data-stu-id="796e4-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="796e4-105">Derzeit dauert die Verwendung des Core eDiscovery-Falls im Security & Compliance Center zum Platzieren einer großen Anzahl von Speicherorten für Custodian-Inhalte Zeit und Vorbereitung.</span><span class="sxs-lookup"><span data-stu-id="796e4-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="796e4-106">Bevor Sie beispielsweise einen Halteraum erstellen, müssen Sie die URL für jede OneDrive for #A0 sammeln, die Sie in der Warteschleife platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="796e4-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="796e4-107">Anschließend müssen Sie für jeden Benutzer, den Sie in der Warteschleife platzieren möchten, ihr Postfach und die OneDrive for #A0 zum Archiv hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="796e4-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="796e4-108">Sie können das Skript in diesem Artikel verwenden, um diesen Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="796e4-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="796e4-109">Das Skript fordert Sie auf, den Namen der Domäne "Meine Website" Ihrer Organisation (z. B. in der URL , den Namen eines vorhandenen `contoso` eDiscovery-Falls, den Namen des neuen Haltebereichs, der dem Fall zugeordnet ist, eine Liste der E-Mail-Adressen der Benutzer, die Sie in den Haltebereich setzen möchten, und eine Suchabfrage, die verwendet werden soll, wenn Sie einen abfragebasierten Haltebereich erstellen https://contoso-my.sharepoint.com) möchten.</span><span class="sxs-lookup"><span data-stu-id="796e4-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="796e4-110">Das Skript ruft dann die URL für die OneDrive for #A0 für jeden Benutzer in der Liste ab, erstellt den neuen Halteraum und fügt dann das Postfach und die OneDrive for #A1 für jeden Benutzer in der Liste dem Archiv hinzu.</span><span class="sxs-lookup"><span data-stu-id="796e4-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="796e4-111">Das Skript generiert auch Protokolldateien, die Informationen zum neuen Halteraum enthalten.</span><span class="sxs-lookup"><span data-stu-id="796e4-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="796e4-112">Hier sind die Schritte, um dies zu geschehen:</span><span class="sxs-lookup"><span data-stu-id="796e4-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="796e4-113">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="796e4-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="796e4-114">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="796e4-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="796e4-115">Schritt 3: Ausführen des Skripts zum Erstellen eines Halte- und Hinzufügens von Benutzern</span><span class="sxs-lookup"><span data-stu-id="796e4-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="796e4-116">Vor dem Hinzufügen von Benutzern zu einem Halteraum</span><span class="sxs-lookup"><span data-stu-id="796e4-116">Before you add users to a hold</span></span>

- <span data-ttu-id="796e4-117">Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center und ein SharePoint Online-Administrator sein, um das Skript in Schritt 3 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="796e4-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="796e4-118">Weitere Informationen finden Sie unter [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="796e4-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="796e4-119">Einem Archiv, das einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist, können maximal 1.000 Postfächer und 100 Websites hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="796e4-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="796e4-120">Unter der Annahme, dass jeder Benutzer, den Sie in der Warteschleife platzieren möchten, über eine OneDrive for #A0 verfügt, können Sie mithilfe des Skripts in diesem Artikel maximal 100 Benutzer zu einem Halteraum hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="796e4-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="796e4-121">Achten Sie darauf, die Liste der Benutzer, die Sie in Schritt 2 und das Skript in Schritt 3 erstellen, im gleichen Ordner zu speichern.</span><span class="sxs-lookup"><span data-stu-id="796e4-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="796e4-122">Dies erleichtert das Ausführen des Skripts.</span><span class="sxs-lookup"><span data-stu-id="796e4-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="796e4-123">Das Skript fügt die Liste der Benutzer zu einem neuen Halteraum hinzu, der einem vorhandenen Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="796e4-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="796e4-124">Stellen Sie sicher, dass der Fall, dem Sie den Halteraum zuordnen möchten, erstellt wird, bevor Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="796e4-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="796e4-125">Das Skript in diesem Artikel unterstützt die moderne Authentifizierung beim Herstellen einer Verbindung mit security & Compliance Center PowerShell und SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="796e4-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="796e4-126">Sie können das Skript wie folgt verwenden, wenn Sie eine Microsoft 365- oder Microsoft 365-GCC-Organisation sind.</span><span class="sxs-lookup"><span data-stu-id="796e4-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="796e4-127">Wenn Sie eine Office 365 Deutschland-Organisation, eine Microsoft 365 GCC High-Organisation oder eine Microsoft 365 DoD-Organisation sind, müssen Sie das Skript bearbeiten, um es erfolgreich auszuführen.</span><span class="sxs-lookup"><span data-stu-id="796e4-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="796e4-128">Insbesondere müssen Sie die Zeile bearbeiten und die `Connect-IPPSSession` *Parameter ConnectionUri* und *AzureADAuthorizationEndpointUri* (und die entsprechenden Werte für Ihren Organisationstyp) verwenden, um eine Verbindung mit Security & Compliance Center PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="796e4-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="796e4-129">Weitere Informationen finden Sie in den Beispielen unter [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="796e4-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="796e4-130">Das Skript trennt automatisch die Verbindung & Compliance Center PowerShell und SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="796e4-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="796e4-131">Das Skript enthält eine minimale Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="796e4-131">The script includes minimal error handling.</span></span> <span data-ttu-id="796e4-132">Der Hauptzweck besteht im schnellen und einfachen Platzieren des Postfachs und der OneDrive for #A0 jedes Benutzers.</span><span class="sxs-lookup"><span data-stu-id="796e4-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="796e4-p109">Die in diesem Thema bereitgestellten Beispielskripts werden in den Microsoft-Standardsupportprogrammen oder -diensten nicht unterstützt. Die Beispielskripts werden wie besehen ohne Garantie jeglicher Art bereitgestellt. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Alle Risiken, die aus der Nutzung oder Ausführung der Beispielskripts und Dokumentation entstehen, liegen bei Ihnen. Microsoft, seine Autoren oder an der Erstellung, Produktion oder Bereitstellung der Skripts beteiligte Personen sind in keinem Fall haftbar für entstandene Schäden (darunter entgangene Gewinne, Geschäftsunterbrechungen, Verluste von Geschäftsinformationen oder sonstige finanzielle Verluste), die aus der Nutzung oder der Nutzungsunfähigkeit der Bespielskripts oder Dokumentation entstanden sind, selbst dann nicht, wenn Microsoft über eventuelle Folgen informiert wurde.</span><span class="sxs-lookup"><span data-stu-id="796e4-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="796e4-138">Schritt 1: Installieren der SharePoint Online-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="796e4-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="796e4-139">Der erste Schritt besteht in der Installation der SharePoint Online-Verwaltungsshell, wenn sie noch nicht auf Ihrem lokalen Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="796e4-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="796e4-140">Sie müssen die Shell in diesem Verfahren nicht verwenden, aber Sie müssen sie installieren, da sie die erforderlichen Voraussetzungen für das Skript enthält, das Sie in Schritt 3 ausführen.</span><span class="sxs-lookup"><span data-stu-id="796e4-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="796e4-141">Diese Voraussetzungen ermöglichen es dem Skript, mit SharePoint Online zu kommunizieren, um die URLs für die OneDrive for #A0 zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="796e4-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="796e4-142">Wechseln Sie [zu Einrichten der SharePoint Online-Verwaltungsshell Windows PowerShell,](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) und führen Sie Schritt 1 und Schritt 2 aus, um die SharePoint Online-Verwaltungsshell auf Ihrem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="796e4-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="796e4-143">Schritt 2: Generieren einer Liste von Benutzern</span><span class="sxs-lookup"><span data-stu-id="796e4-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="796e4-144">Mit dem Skript in Schritt 3 wird ein Archiv erstellt, das einem eDiscovery-Fall zugeordnet ist, und die Postfächer und OneDrive for #A0 einer Benutzerliste zum Archiv hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="796e4-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="796e4-145">Sie können einfach die E-Mail-Adressen in eine Textdatei eingeben oder einen Befehl in Windows PowerShell ausführen, um eine Liste der E-Mail-Adressen zu erhalten und sie in einer Datei zu speichern (in dem Ordner, in dem Sie das Skript in Schritt 3 speichern).</span><span class="sxs-lookup"><span data-stu-id="796e4-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="796e4-146">Hier sehen Sie einen PowerShell-Befehl (den Sie mithilfe von Remote PowerShell ausführen, der mit Ihrer Exchange Online-Organisation verbunden ist), um eine Liste der E-Mail-Adressen für alle Benutzer in Ihrer Organisation zu erhalten und in einer Textdatei namens HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="796e4-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="796e4-147">Öffnen Sie nach dem Ausführen dieses Befehls die Textdatei, und entfernen Sie die Kopfzeile, die den Eigenschaftennamen enthält,  `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="796e4-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="796e4-148">Entfernen Sie dann alle E-Mail-Adressen mit Ausnahme der Adressen für die Benutzer, die Sie dem in Schritt 3 erstellten Halteraum hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="796e4-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="796e4-149">Stellen Sie sicher, dass vor oder nach der Liste der E-Mail-Adressen keine leeren Zeilen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="796e4-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="796e4-150">Schritt 3: Ausführen des Skripts zum Erstellen eines Halte- und Hinzufügens von Benutzern</span><span class="sxs-lookup"><span data-stu-id="796e4-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="796e4-151">Wenn Sie das Skript in diesem Schritt ausführen, werden Sie zur Eingabe der folgenden Informationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="796e4-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="796e4-152">Stellen Sie sicher, dass diese Informationen bereit sind, bevor Sie das Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="796e4-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="796e4-153">**Ihre Benutzeranmeldeinformationen:** Das Skript verwendet Ihre Anmeldeinformationen, um eine Verbindung mit security & Compliance Center mit PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="796e4-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="796e4-154">Außerdem werden diese Anmeldeinformationen verwendet, um auf SharePoint Online zu zugreifen, um die OneDrive for #A0 für die Benutzerliste zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="796e4-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="796e4-155">**Name Ihrer SharePoint-Domäne:** Das Skript fordert Sie auf, diesen Namen ein eingeben, damit es eine Verbindung mit dem SharePoint Admin Center herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="796e4-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="796e4-156">Außerdem wird der Domänenname für die OneDrive-URLs in Ihrer Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="796e4-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="796e4-157">Wenn beispielsweise die URL für Ihr Admin Center und die URL für OneDrive ist, geben Sie ein, wenn das Skript Sie zur Eingabe Ihres `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` Domänennamens anfordert.</span><span class="sxs-lookup"><span data-stu-id="796e4-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="796e4-158">**Name des Falls:** Der Name eines vorhandenen Falls.</span><span class="sxs-lookup"><span data-stu-id="796e4-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="796e4-159">Das Skript erstellt einen neuen Halteraum, der diesem Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="796e4-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="796e4-160">**Name des Halteraums:** Der Name des Halteraums, den das Skript erstellt und dem angegebenen Fall zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="796e4-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="796e4-161">**Suchabfrage für einen abfragebasierten Halteraum:** Sie können einen abfragebasierten Halteraum erstellen, sodass nur der Inhalt, der die angegebenen Suchkriterien erfüllt, in der Warteschleife platziert wird.</span><span class="sxs-lookup"><span data-stu-id="796e4-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="796e4-162">Drücken Sie einfach die EINGABETASTE, wenn Sie zur Eingabe einer Suchabfrage aufgefordert werden, um alle Inhalte in der Warteschleife zu platzieren. </span><span class="sxs-lookup"><span data-stu-id="796e4-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="796e4-163">**Aktivieren des Haltepunkts oder nicht:** Sie können das Skript nach der Erstellung aktivieren oder das Skript den Halteraum erstellen lassen, ohne es zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="796e4-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="796e4-164">Wenn sie das Skript nicht aktivieren, können Sie es später im Security & Compliance Center oder durch Ausführen der folgenden PowerShell-Befehle aktivieren:</span><span class="sxs-lookup"><span data-stu-id="796e4-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="796e4-165">**Name der Textdatei mit** der Liste der Benutzer – Der Name der Textdatei aus Schritt 2, die die Liste der Benutzer enthält, die dem Halteraum hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="796e4-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="796e4-166">Wenn sich diese Datei im gleichen Ordner wie das Skript befindet, geben Sie einfach den Namen der Datei ein (z. B. HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="796e4-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="796e4-167">Wenn sich die Textdatei in einem anderen Ordner befindet, geben Sie den vollständigen Pfadnamen der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="796e4-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="796e4-168">Nachdem Sie die Vom Skript aufgeforderten Informationen gesammelt haben, besteht der letzte Schritt in der Ausführung des Skripts zum Erstellen des neuen Halteraums und hinzufügen von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="796e4-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="796e4-169">Speichern Sie den folgenden Text in Windows PowerShell skriptdatei mithilfe des Dateinamensuffixs `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="796e4-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="796e4-170">Beispiel: `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="796e4-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="796e4-171">Öffnen Sie auf dem lokalen Computer Windows PowerShell, und wechseln Sie zu dem Ordner, in dem Sie das Skript gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="796e4-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="796e4-172">Führen Sie das Skript aus. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="796e4-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="796e4-173">Geben Sie die Vom Skript aufgeforderten Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="796e4-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="796e4-174">Das Skript stellt eine Verbindung mit Security & Compliance Center PowerShell ein, erstellt dann den neuen Halteraum im eDiscovery-Fall und fügt die Postfächer und OneDrive for Business für die Benutzer in der Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="796e4-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="796e4-175">Sie können zu dem Fall auf der **eDiscovery-Seite** im Security & Compliance Center wechseln, um das neue Haltefeld zu sehen.</span><span class="sxs-lookup"><span data-stu-id="796e4-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="796e4-176">Nachdem das Skript ausgeführt wurde, werden die folgenden Protokolldateien erstellt und in dem Ordner gespeichert, in dem sich das Skript befindet.</span><span class="sxs-lookup"><span data-stu-id="796e4-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="796e4-177">**LocationsOnHold.txt:** Enthält eine Liste der Postfächer und OneDrive for Business-Websites, die das Skript erfolgreich in der Warteschleife platziert hat.</span><span class="sxs-lookup"><span data-stu-id="796e4-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="796e4-178">**LocationsNotOnHold.txt:** Enthält eine Liste der Postfächer und OneDrive for Business-Websites, die das Skript nicht in der Warteschleife gespeichert hat.</span><span class="sxs-lookup"><span data-stu-id="796e4-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="796e4-179">Wenn ein Benutzer über ein Postfach verfügt, aber keine OneDrive for #A0 ist, wird der Benutzer in die Liste der OneDrive for #A1 aufgenommen, die nicht in der Warteschleife platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="796e4-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="796e4-180">**GetCaseHoldPolicy.txt:** Enthält die Ausgabe des **Cmdlets Get-CaseHoldPolicy** für den neuen Halteraum, den das Skript nach dem Erstellen des neuen Halteraums ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="796e4-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="796e4-181">Die von diesem Cmdlet zurückgegebenen Informationen enthalten eine Liste der Benutzer, deren Postfächer und OneDrive for #A0 gesperrt wurden und ob der Halteraum aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="796e4-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="796e4-182">**GetCaseHoldRule.txt:** Enthält die Ausgabe des **Cmdlets Get-CaseHoldRule** für den neuen Halteraum, den das Skript nach dem Erstellen des neuen Halteraums ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="796e4-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="796e4-183">Die von diesem Cmdlet zurückgegebenen Informationen enthalten die Suchabfrage, wenn Sie das Skript zum Erstellen eines abfragebasierten Haltefelds verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="796e4-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>