---
title: Warum Sie PowerShell für Microsoft 365 verwenden müssen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Zusammenfassung: Hier erfahren Sie, warum Sie PowerShell zum Verwalten von Microsoft 365, in einigen Fällen effizienter und in anderen Fällen erforderlich verwenden müssen.'
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690306"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="2ca9d-103">Warum Sie PowerShell für Microsoft 365 verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="2ca9d-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="2ca9d-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2ca9d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2ca9d-105">Mit dem Microsoft 365 Admin Center können Sie nicht nur Ihre Microsoft 365-Benutzerkonten und-Lizenzen verwalten, sondern auch Ihre Microsoft 365-Dienste wie Exchange Online, Teams und SharePoint Online verwalten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="2ca9d-106">Sie können diese Elemente jedoch auch mit PowerShell-Befehlen verwalten, indem Sie eine Befehlszeilen-und Skriptsprachen Umgebung für Geschwindigkeit, Automatisierung und zusätzliche Funktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="2ca9d-107">In diesem Artikel erfahren Sie, wie Sie PowerShell zum Verwalten von Microsoft 365 verwenden können:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="2ca9d-108">Aufdecken zusätzlicher Informationen, die im Microsoft 365 Admin Center nicht angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="2ca9d-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="2ca9d-109">Konfigurieren von Features und Einstellungen nur mit PowerShell möglich</span><span class="sxs-lookup"><span data-stu-id="2ca9d-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="2ca9d-110">Ausführen von Massenvorgängen</span><span class="sxs-lookup"><span data-stu-id="2ca9d-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="2ca9d-111">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="2ca9d-111">Filtering data</span></span>
    
- <span data-ttu-id="2ca9d-112">Drucken oder Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="2ca9d-112">Print or save data</span></span>
    
- <span data-ttu-id="2ca9d-113">Verwalten von Across-Diensten</span><span class="sxs-lookup"><span data-stu-id="2ca9d-113">Manage across services</span></span>
    
<span data-ttu-id="2ca9d-114">Bevor Sie beginnen, sollten Sie wissen, dass PowerShell für Microsoft 365 eine Reihe von Modulen für Windows PowerShell ist, eine Befehlszeilenumgebung für Windows-basierte Dienste und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="2ca9d-115">Diese Umgebung erstellt eine Befehlsshell-Sprache, die um zusätzliche Module erweitert werden kann, und bietet eine Möglichkeit zum Ausführen einfacher oder komplexer Befehle oder Skripts.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="2ca9d-116">Wenn Sie beispielsweise die PowerShell für Microsoft 365-Module installiert und eine Verbindung mit Ihrem Microsoft 365-Abonnement hergestellt haben, können Sie diesen Befehl ausführen, um alle Benutzerpostfächer für Microsoft Exchange Online aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="2ca9d-117">Das erhalten der Liste der Postfächer kann auch problemlos über das Microsoft 365 Admin Center erfolgen, aber die Anzahl der Elemente in allen Listen für alle Websites für alle Ihre Webanwendungen kann nicht einfach ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="2ca9d-118">Beachten Sie, dass PowerShell für Microsoft 365 darauf ausgelegt ist, ihre Fähigkeit zum Verwalten von Microsoft 365 zu erweitern und zu verbessern, nicht um das Microsoft 365 Admin Center zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="2ca9d-119">Als Administrator müssen Sie sich mit der Verwendung von PowerShell für Microsoft 365 zumindest vertraut machen, da es einige Konfigurationsverfahren gibt, die nur mit PowerShell für Microsoft 365-Befehle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="2ca9d-120">In diesen Fällen müssen Sie sich mit den folgenden Themen vertraut machen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="2ca9d-121">Installieren Sie die PowerShell für Microsoft 365-Module (nur einmal für jeden Administratorcomputer ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="2ca9d-122">Stellen Sie eine Verbindung zu Ihrem Microsoft 365-Abonnement her (einmal für jede PowerShell-Sitzung ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="2ca9d-123">Sammeln Sie die Informationen, die zum Ausführen der erforderlichen PowerShell für Microsoft 365-Befehle benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="2ca9d-124">Führen Sie die PowerShell für Microsoft 365-Befehle erfolgreich aus.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="2ca9d-125">Nachdem Sie diese grundlegenden Fähigkeiten erlernt haben, müssen Sie Ihre Postfachbenutzer nicht mit dem Befehl **Get-Mailbox** auflisten, und Sie müssen nicht verstehen, wie ein neuer Befehl wie der vorherige erstellt wird, um alle Elemente in allen Listen für alle Standorte für alle Web-Apps zu zählen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="2ca9d-126">Microsoft und die Community von Administratoren können Ihnen bei Bedarf behilflich sein.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="2ca9d-127">PowerShell für Microsoft 365 kann zusätzliche Informationen aufdecken, die Sie mit dem Microsoft 365 Admin Center nicht sehen können.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="2ca9d-128">Im Microsoft 365 Admin Center werden viele nützliche Informationen angezeigt, aber das bedeutet nicht, dass alle möglichen Informationen angezeigt werden, die von Microsoft 365 für Benutzer, Lizenzen, Postfächer und Websites gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="2ca9d-129">Im folgenden finden Sie ein Beispiel für **Benutzer und Gruppen** im Microsoft 365 Admin Center:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Beispiel für die Anzeige von Benutzern und Gruppen im Microsoft 365 Admin Center.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="2ca9d-131">Hier werden für zahlreiche Zwecke die benötigten Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="2ca9d-132">Es kann jedoch vorkommen, dass Sie mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-132">However, there are times when you need more.</span></span> <span data-ttu-id="2ca9d-133">Beispielsweise hängen Microsoft 365-Lizenzierung (und die Microsoft 365-Funktionen, die einem Benutzer zur Verfügung stehen) teilweise von dem geografischen Standort dieses Benutzers ab.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="2ca9d-134">Die Richtlinien und Features, die Sie auf einen Benutzer erweitern können, der in den USA lebt, sind möglicherweise nicht die gleichen Richtlinien und Features, die Sie auf einen Benutzer erweitern können der in Indien oder in Belgien lebt.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="2ca9d-135">Sie können das Microsoft 365 Admin Center verwenden, um den geografischen Standort eines Benutzers mit den folgenden Schritten zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="2ca9d-136">Doppelklicken Sie auf den **Anzeigenamen** des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="2ca9d-137">Klicken Sie im Bereich "Benutzereigenschaften" auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="2ca9d-138">Klicken Sie unter "Details" auf **Zusätzliche Details**.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="2ca9d-139">Führen Sie einen Bildlauf nach unten bis zu **Land oder Region** aus.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Beispiel für die Regionsinformationen für einen Benutzer im Microsoft 365 Admin Center.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="2ca9d-141">Notieren Sie den Anzeigenamen des Benutzers auf einem Blatt Papier, oder kopieren ihn in Editor.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="2ca9d-142">Sie müssen diese Vorgehensweise für jeden Benutzer wiederholen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="2ca9d-143">Bei zahlreichen Benutzern kann dies eine mühsame Aufgabe sein.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="2ca9d-144">Mit PowerShell für Microsoft 365 können Sie diese Informationen für alle Benutzer mit dem folgenden Befehl anzeigen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="2ca9d-145">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="2ca9d-146">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="2ca9d-147">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-147">Here is an example of the display:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

> [!TIP]
>  <span data-ttu-id="2ca9d-148">Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen ( **Get-AzureADUser** ), aber nur den Namen und den Speicherort für jeden Benutzer anzeigen ( **Select DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="2ca9d-149">Da PowerShell für Microsoft 365 eine Command Shell-Sprache unterstützt, können Sie die Informationen, die Sie über den Befehl **Get-AzureADUser** erhalten haben, weiter bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="2ca9d-150">Vielleicht möchten Sie diese Benutzer beispielsweise nach Ihrem Standort sortieren, alle brasilianischen Benutzer zusammen gruppieren, alle Benutzer in den USA zusammen usw. Hier ist der Befehl:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="2ca9d-151">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-151">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

> [!TIP]
>  <span data-ttu-id="2ca9d-152">Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, zeigen Sie jedoch nur den Namen und den Speicherort für jeden Benutzer an, und sortieren Sie diese zuerst nach ihrem Speicherort und anschließend nach Ihren Namen ( **Sort UsageLocation, DisplayName** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="2ca9d-p110">Sie können auch eine zusätzliche Filterung verwenden. Wenn Sie beispielsweise nur Informationen zu Benutzern in Brasilien anzeigen möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p110">You can also employ additional filtering. For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="2ca9d-155">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="2ca9d-156">Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, deren Standort Brasilien ist ( **wobei {$ \_ . UsageLocation-EQ "br"}** ), und zeigen Sie dann den Namen und den Speicherort für jeden Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="2ca9d-157">**Ein kurzer Hinweis zu größeren Domänen**</span><span class="sxs-lookup"><span data-stu-id="2ca9d-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="2ca9d-158">Wenn Sie eine sehr große Domäne mit Zehntausenden von Benutzers haben, könnte dies bei einigen Beispielen in diesem Artikel zu "Einschränkungen" kommen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="2ca9d-159">Je nach Computerleistung und verfügbarer Bandbreite möchten Sie zu viel auf einmal.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="2ca9d-160">Aus diesem Grund möchten größere Organisationen möglicherweise einige dieser PowerShell für Microsoft 365-Befehle in zwei Befehle aufteilen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="2ca9d-161">Dieser einer Befehle gibt beispielsweise alle Benutzerkonten zurück und zeigt den Namen und Standort für jedes Konto an:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="2ca9d-p112">Das funktioniert auch gut bei kleineren Domänen. In großen Organisationen müssen Sie den Befehl möglicherweise in zwei Befehle aufteilen: Ein Befehl zum Speichern der Benutzerkontoinformationen in einer Variablen und ein anderer Befehl zum Anzeigen der erforderlichen Informationen. Es folgt ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p112">That works great for smaller domains. In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information. Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="2ca9d-165">Die Interpretation dieses Satzes von PowerShell-Befehlen lautet:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="2ca9d-166">Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen mit dem Namen $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="2ca9d-167">Den Inhalt der Variablen „$x“ anzeigen, dabei aber für jeden Benutzer nur Namen und Standort einschließen (**$x | Select DisplayName, UsageLocation**)</span><span class="sxs-lookup"><span data-stu-id="2ca9d-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="2ca9d-168">Microsoft 365 verfügt über Features, die Sie nur mit PowerShell für Microsoft 365 konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="2ca9d-169">Das Microsoft 365 Admin Center soll den Zugriff auf die am häufigsten oder bedeutsamsten administrativen Aufgaben ermöglichen, die für die meisten Personen gelten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="2ca9d-170">Das heißt, das Microsoft 365 Admin Center wurde so konzipiert, dass der typische Administrator mithilfe des Tools die am häufigsten verwendeten Verwaltungsaufgaben ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="2ca9d-171">Mit dieser Definition bedeutet dies, dass es einige Aufgaben gibt, die nicht mithilfe des Microsoft 365 Admin Center ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="2ca9d-172">Das Skype for Business Online Admin Center bietet beispielsweise ein paar Optionen zum Erstellen benutzerdefinierter Besprechungseinladungen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Beispiel für die Anzeige von benutzerdefinierten Besprechungseinladungen im Skype for Business Online Admin Center](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="2ca9d-p114">Mit diesen Einstellungen können Sie Besprechungseinladungen eine gewisse persönliche Note und Professionalität verleihen. Besprechungskonfigurationseinstellungen erlauben Ihnen jedoch mehr, als einfach benutzerdefinierte Besprechungseinladungen zu erstellen. Besprechungen ermöglichen standardmäßig beispielsweise Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p114">With these settings, you can add a touch of personalization and professionalism to meeting invitations. However, there's more to meeting configuration settings than simply creating custom meeting invitations. For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="2ca9d-177">anonymen Benutzern, automatischen Zugang zu jeder Besprechung zu erhalten</span><span class="sxs-lookup"><span data-stu-id="2ca9d-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="2ca9d-178">Teilnehmern, die Besprechung aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="2ca9d-179">das Festlegen aller Benutzer in Ihrer Organisation als Referenten, wenn sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="2ca9d-180">Diese Einstellungen sind im Skype for Business Online Admin Center nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="2ca9d-181">Sie können Sie jedoch über PowerShell für Microsoft 365 steuern.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="2ca9d-182">Nachfolgend sehen Sie einen Befehl, der diese drei Einstellungen deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="2ca9d-183">Für diesen Befehl müssen Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366) installieren.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="2ca9d-184">Die Interpretation dieses PowerShell-Befehls lautet: für die Einstellungen für neue Skype for Business Online Besprechungen (" **CsMeetingConfiguration** "), deaktivieren Sie die Möglichkeit, dass anonyme Benutzer automatisch an Besprechungen teilnehmen können ( **-AdmitAnonymousUsersByDefault $false** ), deaktivieren Sie die Möglichkeit, Besprechungen zu erfassen ( **-AllowConferenceRecording $false** ), und legen Sie nicht alle Benutzer aus Ihrer Organisation als Referenten fest ( **-DesignateAsPresenter "None"** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="2ca9d-185">Wenn Sie Ihre Meinung ändern und diese Standardeinstellungen wiederherstellen möchten (alle aktiviert), führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="2ca9d-186">Dies ist nur ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-186">This is just one example.</span></span> <span data-ttu-id="2ca9d-187">Es gibt andere, daher müssen Sie sich als Administrator mit der Ausführung von PowerShell für Microsoft 365-Befehle vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="2ca9d-188">PowerShell für Microsoft 365 eignet sich hervorragend zum Ausführen von Massenvorgängen</span><span class="sxs-lookup"><span data-stu-id="2ca9d-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="2ca9d-189">Historisch gesehen sind visuelle Schnittstellen wie das Microsoft 365 Admin Center besonders wertvoll, wenn Sie einen einzelnen Vorgang ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="2ca9d-190">Wenn Sie beispielsweise ein Benutzerkonto deaktivieren müssen, können Sie das Microsoft 365 Admin Center verwenden, um ein CheckBox-Steuerelement schnell zu finden und zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="2ca9d-191">Dies kann einfacher sein, als eine ähnliche Operation in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="2ca9d-192">Wenn Sie jedoch viele Dinge oder einige ausgewählte Dinge in einer großen Menge anderer Dinge ändern müssen, ist das Microsoft 365 Admin Center möglicherweise nicht die beste Nutzung ihrer Zeit.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="2ca9d-193">Wenn Sie beispielsweise das Präfix für Tausende von Telefonnummern ändern oder einen bestimmten Benutzer, Ken Myers, von all Ihren SharePoint Online Websites entfernen mussten, wie würden Sie dies im Microsoft 365 Admin Center tun?</span><span class="sxs-lookup"><span data-stu-id="2ca9d-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="2ca9d-194">Beim zweiten Beispiel haben Sie mehrere Hundert SharePoint Online-Standorte und wissen nicht einmal, bei welchen Ken Meyer ein Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="2ca9d-195">Das bedeutet, dass Sie am Microsoft 365 Admin Center beginnen und dann dieses Verfahren für jeden Standort ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="2ca9d-196">Klicken Sie auf die **URL** des Standorts.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="2ca9d-197">Klicken Sie im Feld **Websitesammlungs-Eigenschaften** auf den Link **Websiteadresse**, um die Website zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="2ca9d-198">Klicken Sie auf der Website auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="2ca9d-199">Klicken Sie im Dialogfeld **Freigabe** auf den Link, der Ihnen alle Benutzer mit Berechtigungen für die Website zeigt:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![Beispiel der Anzeige der Mitglieder einer SharePoint Online-Website im SharePoint Online Admin Center.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="2ca9d-201">Klicken Sie im Dialogfeld **Freigegeben für** auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="2ca9d-202">Führen Sie in der Liste der Benutzer einen Bildlauf nach unten zu Ken Myer durch, wählen Sie ihn aus (angenommen, dass er Berechtigungen für diese Website besitzt), und klicken Sie dann auf **Benutzerberechtigungen entfernen**.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="2ca9d-203">Dies kann bei mehreren Hundert Seiten lange dauern.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="2ca9d-204">Die Alternative besteht darin, PowerShell für Microsoft 365 und den folgenden Befehl zum Entfernen von Ken Myers von allen ihren Websites zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="2ca9d-205">Für diesen Befehl müssen Sie das [SharePoint Online PowerShell-Modul](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installieren.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="2ca9d-206">Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement ( **Get-SPOSite** ) ab, und entfernen Sie für jeden Standort Ken Meyer aus der Liste der Benutzer, die darauf zugreifen können ( **foreach {Remove-Ehepartner-Site $ \_ . URL-LoginName "kenmyer@litwareinc.com"}** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="2ca9d-207">Da wir Microsoft 365 sagen, Ken Meyer von jeder Website zu entfernen, einschließlich derer, in denen er keinen Zugriff hat, zeigt die Anzeige dieses Befehls Fehler für die Websites an, in denen der Zugriff derzeit nicht erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="2ca9d-208">Wir können eine zusätzliche Bedingung für diesen Befehl verwenden, um Ken Meyer nur von den Standorten zu entfernen, an denen er in der Anmeldeliste vorhanden ist, die aufgeführten Fehler richten jedoch an den Standorten selbst keinen Schaden an.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="2ca9d-209">Dieser Befehl kann einige Minuten dauern, bis Hunderte von Websites ausgeführt werden, statt Stunden lang über das Microsoft 365 Admin Center zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="2ca9d-p121">Nachfolgend finden Sie ein weiteres Beispiel für eine Massenoperation. Verwenden Sie diesen Befehl, um Bonnie Kearney, einen neuen SharePoint-Administrator, zu allen Standorten in der Organisation hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p121">Here is another bulk operation example. Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="2ca9d-212">Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement und für jede Website ab, und gewähren Sie Bonnie Kearney Zugriff, indem Sie Ihren Anmeldenamen zur Mitgliedergruppe der Website hinzufügen ( **foreach {Add-Partner-Site $ \_ . URL-LoginName "bkearney@litwareinc.com"-Gruppe "Members"}** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="2ca9d-213">PowerShell für Microsoft 365 eignet sich hervorragend zum Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="2ca9d-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="2ca9d-214">Das Microsoft 365 Admin Center bietet verschiedene Möglichkeiten zum Filtern Ihrer Daten, um eine gezielte Teilmenge von Informationen schnell und einfach zu finden.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="2ca9d-215">Mit Exchange können Sie beispielsweise leicht nach praktisch jeder Eigenschaft eines Benutzerpostfachs filtern.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="2ca9d-216">Nachfolgend sehen Sie beispielsweise die Liste der Postfächer aller Benutzer, die in Bloomington wohnen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Beispiel für eine erweiterte Suche im Microsoft 365 Admin Center für die Liste der Postfächer für alle Benutzer, die in der Stadt Bloomington Leben.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="2ca9d-p123">Im Exchange Admin Center können Sie auch Filterkriterien kombinieren. Sie können beispielsweise nach den Postfächern aller in Bloomington lebenden Personen suchen, die zudem in der Finanzabteilung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p123">The Exchange Admin center also lets you combine filter criteria. For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="2ca9d-p124">Es gibt jedoch Einschränkungen dafür, was mit dem Exchange Admin Center alles möglich ist. Vielleicht möchten Sie beispielsweise die Postfächer aller in Bloomington oder San Diego lebenden Personen suchen oder die Postfächer aller Personen, die nicht in Bloomington leben.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p124">However, there are limitations to what you can do in the Exchange Admin center. For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="2ca9d-222">Mit PowerShell für Microsoft 365 können Sie eine Liste von Postfächern für alle Personen erhalten, die in den Städten Bloomington oder San Diego mit folgendem Befehl Leben:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="2ca9d-223">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="2ca9d-224">Die Interpretation dieses PowerShell-Befehls lautet: Abrufen aller Benutzer des aktuellen Microsoft 365-Abonnements mit einem Postfach in den Städten San Diego oder Bloomington ( **wobei {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-und ($ \_ . City-EQ "San Diego"-oder $ \_ . City-EQ "Bloomington")}** ), und zeigen Sie dann den Namen und die Stadt für jeden an ( **Wählen Sie DisplayName, Ort** ) aus.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="2ca9d-225">Verwenden Sie den folgenden Befehl, um alle Postfächer von Benutzern aufzuführen, die überall leben, nur nicht in Bloomington:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="2ca9d-226">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-226">Here is an example of the display:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

> [!TIP]
>  <span data-ttu-id="2ca9d-227">Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Benutzer des aktuellen Microsoft 365-Abonnements ab, deren Postfach sich nicht in der Stadt Bloomington befindet ( **wobei {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-und $ \_ . City-ne "Bloomington"}** ), und zeigen Sie dann den Namen und die Stadt für jeden an.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="2ca9d-228">Sie können auch Platzhalterzeichen in ihren PowerShell-Filtern verwenden, um einen Teil eines Namens abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="2ca9d-229">Angenommen, Sie suchen nach einem Benutzerkonto, und Sie können sich nur daran erinnern, dass der Nachname Anderson oder vielleicht Henderson oder vielleicht aber auch Jorgenson war.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="2ca9d-230">Sie können den Benutzer im Microsoft 365 Admin Center nachverfolgen, indem Sie das Such Tool verwenden und drei verschiedene Suchvorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="2ca9d-231">Eine für  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="2ca9d-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="2ca9d-232">Eine für  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="2ca9d-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="2ca9d-233">Und eine für  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="2ca9d-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="2ca9d-234">Da alle drei Namen in "Son" enden, können Sie PowerShell mitteilen, dass alle Benutzer angezeigt werden sollen, deren Name in "Son" endet.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="2ca9d-235">Hier ist der Befehl:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="2ca9d-236">Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, aber einen Filter verwenden, der nur die Benutzer auflistet, deren Nachname in "Son" endet ( **-Filter ' {LastName-like " \* Son"} '** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="2ca9d-237">Der \* steht für eine beliebige Gruppe von Zeichen, bei denen es sich um Buchstaben im Fall des Nachnamens des Benutzers handelt.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="2ca9d-238">PowerShell für Microsoft 365 erleichtert das Drucken oder Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="2ca9d-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="2ca9d-239">Im Microsoft 365 Admin Center können Sie Listen mit Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="2ca9d-240">Nachfolgend sehen Sie ein Beispiel im Skype for Business Online Admin Center, bei dem eine Liste von Benutzern angezeigt wird, die für Skype for Business Online aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Beispiel für das Skype for Business Online Admin Center, in dem eine Liste von Benutzern angezeigt wird, die für Skype for Business Online aktiviert wurden.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="2ca9d-242">Um diese Informationen in einer Datei zu speichern, müssen Sie sie kopieren und in ein Dokument oder in Excel einfügen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="2ca9d-243">Für das Kopieren ist auf jeden Fall eine zusätzliche Formatierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="2ca9d-244">Darüber hinaus bietet das Microsoft 365 Admin Center keine Möglichkeit, die angezeigte Liste direkt zu drucken.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="2ca9d-245">Glücklicherweise können Sie PowerShell verwenden, um die Liste nicht nur anzuzeigen, sondern in einer Datei zu speichern, die problemlos in Excel importiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="2ca9d-246">Nachfolgend sehen Sie einen Beispielbefehl, um Skype for Business Online-Benutzerdaten in einer CSV-Datei (durch Trennzeichen getrennte Datei) zu speichern, die einfach als Tabelle in ein Excel-Arbeitsblatt importiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="2ca9d-247">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-247">Here is an example of the display:</span></span>
  
![Beispiel für eine Tabelle, die in ein Excel-Arbeitsblatt importiert wurde, mit Skype for Business Online-Benutzerdaten, die als CSV-Datei gespeichert wurden.](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="2ca9d-249">Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Skype for Business Online Benutzer im aktuellen Microsoft 365-Abonnement ab ( **Get-CsOnlineUser** ), beziehen Sie nur den Benutzernamen, den UPN und den Speicherort ( **Wählen Sie DisplayName, userPrincipalName, UsageLocation** ) aus, und speichern Sie diese Informationen dann in der CSV-Datei namens C: \\ Logs \\SfBUsers.csv ( **Export-CSV-Path "C: \\ Logs \\SfBUsers.csv"-NoTypeInformation**</span><span class="sxs-lookup"><span data-stu-id="2ca9d-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="2ca9d-p131">Sie können auch Optionen verwenden, um diese Liste als XML-Datei oder als HTML-Seite zu speichern. Mit zusätzlichen PowerShell-Befehlen könnten Sie die Datei direkt als Excel-Datei mit beliebigen benutzerdefinierten Formatierungen speichern.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p131">You can also use options to save this list as an XML file or as an HTML page. In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="2ca9d-252">Sie können auch die Ausgabe eines PowerShell-Befehls senden, mit dem eine Liste direkt an den Standarddrucker in Windows angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="2ca9d-253">Nachfolgend sehen Sie einen Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="2ca9d-254">Das gedruckte Dokument sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-254">Here's what your printed document will look like:</span></span>
  
![Beispiel für ein gedrucktes Dokument, bei dem es sich um die Ausgabe eines PowerShell-Befehls handelt, der direkt auf dem Standarddrucker in Windows aufgeführt ist.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="2ca9d-256">Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Skype for Business Online Benutzer im aktuellen Microsoft 365-Abonnement ab, beziehen Sie nur den Benutzernamen, den UPN und den Speicherort, und senden Sie diese Informationen dann an den standardmäßigen Windows-Drucker ( **Out-Printer** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="2ca9d-257">Das gedruckte Dokument hat dieselbe einfache Formatierung wie die Anzeige im PowerShell-Befehlsfenster, aber nachdem Sie einen PowerShell-Befehl erstellt haben, um die benötigten Elemente aufzulisten, fügen Sie einfach **| Out-Printer** an das Ende des Befehls, um eine Kopie aus dem Arbeitsspeicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="2ca9d-258">Mit PowerShell für Microsoft 365 können Sie serverübergreifende Produkte verwalten.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="2ca9d-259">Die verschiedenen Komponenten, aus denen Microsoft 365 besteht, sind für die Zusammenarbeit konzipiert.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="2ca9d-260">Nehmen Sie beispielsweise an, dass Sie einen neuen Benutzer zu Microsoft 365 hinzufügen und, wenn Sie dies tun, diese Informationen als Abteilung und Telefonnummer des Benutzers angeben.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="2ca9d-261">Diese Informationen sind dann verfügbar, wenn Sie über einen der Microsoft 365-Dienste auf die Informationen des Benutzers zugreifen: Skype for Business Online, Exchange oder SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="2ca9d-p134">Hierbei handelt es sich um allgemeine Informationen, die für die ganze Produktsuite gleich sind. Produktspezifische Informationen, wie die zu einem Exchange-Benutzerpostfach, sind in der Regel nicht in der gesamten Suite verfügbar. Wenn Sie beispielsweise wissen möchten, ob das Postfach eines Benutzers aktiviert ist oder nicht, sind diese Informationen nur im Exchange Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-p134">But that's for common information that spans the suite of products. Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite. For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="2ca9d-265">Angenommen, Sie möchten einen Bericht erstellen, in dem die folgenden Informationen für alle Benutzer enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="2ca9d-266">Den Anzeigenamen des Benutzers</span><span class="sxs-lookup"><span data-stu-id="2ca9d-266">The user's display name</span></span>
    
- <span data-ttu-id="2ca9d-267">Ob der Benutzer für Microsoft 365 lizenziert ist</span><span class="sxs-lookup"><span data-stu-id="2ca9d-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="2ca9d-268">Ob das Exchange-Postfach des Benutzers aktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="2ca9d-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="2ca9d-269">Ob der Benutzer für Skype for Business Online aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="2ca9d-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="2ca9d-270">Sie können derzeit nicht das Microsoft 365 Admin Center verwenden, um einen solchen Bericht problemlos zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="2ca9d-271">Stattdessen müssen Sie ein separates Dokument erstellen, um die Informationen wie ein Excel-Arbeitsblatt zu speichern und alle Benutzernamen und Lizenzierungsinformationen aus dem Microsoft 365 Admin Center abzurufen, Postfachinformationen aus dem Exchange Admin Center abzurufen, Skype for Business Online Informationen aus dem Skype for Business Online Admin Center abzurufen und diese Informationen dann zusammenzufassen und zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="2ca9d-272">Die Alternative besteht darin, ein PowerShell-Skript zu verwenden, um diesen Bericht für Sie zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="2ca9d-273">Das folgende Beispielskript ist komplizierter als die bisher in diesem Artikel gezeigten Befehle.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="2ca9d-274">Es zeigt jedoch das Potenzial der Verwendung von PowerShell, um Ansichten von Informationen zu erstellen, die ansonsten sehr schwierig zu tun sind.</span><span class="sxs-lookup"><span data-stu-id="2ca9d-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="2ca9d-275">Nachfolgend sehen Sie das Skript, das die erforderliche Liste kompilieren und anzeigen kann:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-275">Here is the script that can compile and display the needed list:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="2ca9d-276">Nachfolgend sehen Sie ein Beispiel der Anzeige:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-276">Here is an example of the display:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="2ca9d-277">Die Interpretation dieses PowerShell-Skripts lautet:</span><span class="sxs-lookup"><span data-stu-id="2ca9d-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="2ca9d-278">Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen mit dem Namen $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="2ca9d-279">Eine Schleife starten, die über alle Benutzer in der Variablen mit dem Namen $x ausgeführt wird (**foreach ($i in $x)**).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="2ca9d-280">Eine Variable mit dem Namen $y definieren und die Postfachinformationen des Benutzers darin speichern (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="2ca9d-281">Eine neue Eigenschaft zu den Benutzerinformationen mit dem Namen IsMailBoxEnabled hinzufügen und diese als Wert der IsMailBoxEnabled-Eigenschaft des Benutzerpostfachs hinzufügen (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="2ca9d-282">Eine Variable mit dem Namen $y definieren und die Skype for Business Online-Informationen des Benutzers darin speichern (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="2ca9d-283">Eine neue Eigenschaft mit dem Namen EnabledForSfB zu den Benutzerinformationen hinzufügen und diese auf den Wert der Enabled-Eigenschaft der Skype_for_Business_Online-Informationen des Benutzers festlegen (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span><span class="sxs-lookup"><span data-stu-id="2ca9d-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="2ca9d-284">Die Benutzerliste anzeigen, dabei aber jeweils nur den Namen, den Lizenzstatus und die beiden neuen Eigenschaften einschließen, die angeben, ob das Postfach aktiviert ist und ob der jeweilige Benutzer für Skype for Business Online aktiviert ist (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**)</span><span class="sxs-lookup"><span data-stu-id="2ca9d-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ca9d-285">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca9d-285">See also</span></span>

[<span data-ttu-id="2ca9d-286">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ca9d-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2ca9d-287">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ca9d-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2ca9d-288">Verwenden der Windows PowerShell zum Erstellen von Berichten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ca9d-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

