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
description: 'Summary: Understand why you must use PowerShell to manage Microsoft 365, in some cases more efficiently and in other cases by necessity.'
ms.openlocfilehash: a60220001a148b3a24a996bb6e0154f80214b019
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924588"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="5838a-103">Warum Sie PowerShell für Microsoft 365 verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="5838a-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="5838a-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5838a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5838a-105">Mit dem Microsoft 365 Admin Center können Sie Ihre Microsoft 365-Benutzerkonten und -Lizenzen verwalten.</span><span class="sxs-lookup"><span data-stu-id="5838a-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="5838a-106">Sie können auch Ihre Microsoft 365-Dienste verwalten, z. B. Exchange Online, Teams und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5838a-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="5838a-107">Wenn Sie stattdessen PowerShell zum Verwalten dieser Dienste verwenden, können Sie die Befehlszeilen- und Skriptsprachenumgebung für Geschwindigkeit, Automatisierung und zusätzliche Funktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="5838a-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="5838a-108">In diesem Artikel wird gezeigt, wie Sie PowerShell verwenden, um Microsoft 365 zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="5838a-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="5838a-109">Weitere Informationen, die Sie im Microsoft 365 Admin Center nicht sehen können</span><span class="sxs-lookup"><span data-stu-id="5838a-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="5838a-110">Konfigurieren von Features und Einstellungen nur mit PowerShell möglich</span><span class="sxs-lookup"><span data-stu-id="5838a-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="5838a-111">Massenvorgänge</span><span class="sxs-lookup"><span data-stu-id="5838a-111">Do bulk operations</span></span>
    
- <span data-ttu-id="5838a-112">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="5838a-112">Filter data</span></span>
    
- <span data-ttu-id="5838a-113">Drucken oder Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="5838a-113">Print or save data</span></span>
    
- <span data-ttu-id="5838a-114">Dienstübergreifend verwalten</span><span class="sxs-lookup"><span data-stu-id="5838a-114">Manage across services</span></span>
    
<span data-ttu-id="5838a-115">Beachten Sie, dass PowerShell für Microsoft 365 eine Reihe von Modulen für Windows PowerShell ist, eine Befehlszeilenumgebung für Windows-basierte Dienste und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5838a-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="5838a-116">In dieser Umgebung wird eine Befehlsshellsprache erstellt, die mit zusätzlichen Modulen erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5838a-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="5838a-117">Es bietet eine Möglichkeit, einfache oder komplexe Befehle oder Skripts auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5838a-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="5838a-118">Nachdem Sie beispielsweise die PowerShell für Microsoft 365-Module installiert und eine Verbindung mit Ihrem Microsoft 365-Abonnement hergestellt haben, können Sie den folgenden Befehl ausführen, um alle Benutzerpostfächer für Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="5838a-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="5838a-119">Sie können die Liste der Postfächer auch über das Microsoft 365 Admin Center erhalten, aber das Zählen der Elemente in allen Listen für alle Websites für alle Ihre Web-Apps ist nicht einfach.</span><span class="sxs-lookup"><span data-stu-id="5838a-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="5838a-120">PowerShell für Microsoft 365 soll Ihnen bei der Verwaltung von Microsoft 365 helfen und nicht das Microsoft 365 Admin Center ersetzen.</span><span class="sxs-lookup"><span data-stu-id="5838a-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="5838a-121">Administratoren müssen PowerShell für Microsoft 365 verwenden können, da einige Konfigurationsverfahren nur über PowerShell für Microsoft 365-Befehle ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="5838a-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="5838a-122">In diesen Fällen müssen Sie wissen, wie Sie:</span><span class="sxs-lookup"><span data-stu-id="5838a-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="5838a-123">Installieren Sie die PowerShell für Microsoft 365-Module (nur einmal für jeden Administratorcomputer).</span><span class="sxs-lookup"><span data-stu-id="5838a-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="5838a-124">Stellen Sie eine Verbindung mit Ihrem Microsoft 365-Abonnement (einmal für jede PowerShell-Sitzung) herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5838a-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="5838a-125">Sammeln Sie die Informationen, die zum Ausführen der erforderlichen PowerShell für Microsoft 365-Befehle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5838a-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="5838a-126">Führen Sie PowerShell für Microsoft 365-Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="5838a-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="5838a-127">Nachdem Sie diese grundlegenden Kenntnisse gelernt haben, müssen Sie ihre Postfachbenutzer nicht mithilfe des **Befehls Get-Mailbox** auflisten.</span><span class="sxs-lookup"><span data-stu-id="5838a-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="5838a-128">Sie müssen auch nicht verstehen, wie Sie einen neuen Befehl wie den zuvor genannten Befehl erstellen, um alle Elemente in allen Listen für alle Websites für alle Ihre Web-Apps zu zählen.</span><span class="sxs-lookup"><span data-stu-id="5838a-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="5838a-129">Microsoft und die Community der Administratoren können Ihnen bei solchen Aufgaben bei Bedarf helfen.</span><span class="sxs-lookup"><span data-stu-id="5838a-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="5838a-130">PowerShell für Microsoft 365 kann Informationen preis geben, die Sie im Microsoft 365 Admin Center nicht sehen können</span><span class="sxs-lookup"><span data-stu-id="5838a-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="5838a-131">Das Microsoft 365 Admin Center zeigt viele nützliche Informationen an.</span><span class="sxs-lookup"><span data-stu-id="5838a-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="5838a-132">Es werden jedoch nicht alle möglichen Informationen angezeigt, die Microsoft 365 zu Benutzern, Lizenzen, Postfächern und Websites speichert.</span><span class="sxs-lookup"><span data-stu-id="5838a-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="5838a-133">Hier ist ein Beispiel für *Benutzer und Gruppen* im Microsoft 365 Admin Center:</span><span class="sxs-lookup"><span data-stu-id="5838a-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Beispiel für die Anzeige von Benutzern und Gruppen im Microsoft 365 Admin Center.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="5838a-135">Diese Ansicht enthält die Informationen, die Sie in vielen Fällen benötigen.</span><span class="sxs-lookup"><span data-stu-id="5838a-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="5838a-136">Es kann jedoch vorkommen, dass Sie mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="5838a-136">However, there are times when you need more.</span></span> <span data-ttu-id="5838a-137">Beispielsweise hängt die Microsoft 365-Lizenzierung (und die für einen Benutzer verfügbaren Microsoft 365-Features) teilweise vom geografischen Standort des Benutzers ab.</span><span class="sxs-lookup"><span data-stu-id="5838a-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="5838a-138">Die Richtlinien und Features, die Sie auf einen Benutzer erweitern können, der in den USA lebt, sind möglicherweise nicht mit denen identisch, die Sie auf einen Benutzer in Indien oder Belgien erweitern können.</span><span class="sxs-lookup"><span data-stu-id="5838a-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="5838a-139">Führen Sie die folgenden Schritte im Microsoft 365 Admin Center aus, um den geografischen Standort eines Benutzers zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="5838a-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="5838a-140">Doppelklicken Sie auf den **Anzeigenamen** des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5838a-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="5838a-141">Wählen Sie im Anzeigebereich benutzereigenschaften Details **aus.**</span><span class="sxs-lookup"><span data-stu-id="5838a-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="5838a-142">Wählen Sie in der Detailanzeige weitere **Details aus.**</span><span class="sxs-lookup"><span data-stu-id="5838a-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="5838a-143">Scrollen Sie, bis Sie die Überschrift **Land oder Region finden:**</span><span class="sxs-lookup"><span data-stu-id="5838a-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Beispiel für die Regioneninformationen für einen Benutzer im Microsoft 365 Admin Center.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="5838a-145">Notieren Sie den Anzeigenamen des Benutzers auf einem Blatt Papier, oder kopieren ihn in Editor.</span><span class="sxs-lookup"><span data-stu-id="5838a-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="5838a-146">Sie müssen diese Vorgehensweise für jeden Benutzer wiederholen.</span><span class="sxs-lookup"><span data-stu-id="5838a-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="5838a-147">Wenn Sie über viele Benutzer verfügen, kann dieser Vorgang mühsam sein.</span><span class="sxs-lookup"><span data-stu-id="5838a-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="5838a-148">Mit PowerShell für Microsoft 365 können Sie diese Informationen für alle Benutzer mithilfe des folgenden Befehls anzeigen:</span><span class="sxs-lookup"><span data-stu-id="5838a-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="5838a-149">PowerShell Core unterstützt das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets, die *Msol* im Namen haben, nicht.</span><span class="sxs-lookup"><span data-stu-id="5838a-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="5838a-150">Sie müssen diese Cmdlets von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5838a-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="5838a-151">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="5838a-152">Die Interpretation dieses PowerShell-Befehls ist: Alle Benutzer im aktuellen Microsoft 365-Abonnement (**Get-AzureADUser**) erhalten, aber nur den Namen und speicherort für jeden Benutzer anzeigen ( Wählen Sie **DisplayName, UsageLocation** aus).</span><span class="sxs-lookup"><span data-stu-id="5838a-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="5838a-153">Da PowerShell für Microsoft 365 eine Befehlsshellsprache unterstützt, können Sie die durch den **Befehl Get-AzureADUser erhaltenen Informationen** weiter bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5838a-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="5838a-154">Vielleicht möchten Sie diese Benutzer beispielsweise nach ihrem Standort sortieren, indem Sie alle brasilianischen Benutzer, alle Benutzer in den Vereinigten Staaten und so weiter gruppieren.</span><span class="sxs-lookup"><span data-stu-id="5838a-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="5838a-155">Hier ist der Befehl:</span><span class="sxs-lookup"><span data-stu-id="5838a-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="5838a-156">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="5838a-157">Die Interpretation dieses PowerShell-Befehls ist: Alle Benutzer im aktuellen Microsoft 365-Abonnement erhalten, aber nur den Namen und Speicherort für jeden Benutzer anzeigen und zuerst nach dem Speicherort und dann nach dem Namen sortieren (**Sort UsageLocation, DisplayName**).</span><span class="sxs-lookup"><span data-stu-id="5838a-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="5838a-158">Sie können auch zusätzliche Filterung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5838a-158">You can also use additional filtering.</span></span> <span data-ttu-id="5838a-159">Wenn Sie beispielsweise nur Informationen zu Benutzern in Brasilien anzeigen möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="5838a-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="5838a-160">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="5838a-161">Die Interpretation dieses PowerShell-Befehls lautet: Alle Benutzer im aktuellen Microsoft 365-Abonnement mit dem Speicherort Brasilien (**Where {$ \_ . UsageLocation -eq "BR"}**) und dann den Namen und Speicherort für jeden Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5838a-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="5838a-162">**Hinweis zu großen Domänen**</span><span class="sxs-lookup"><span data-stu-id="5838a-162">**A note about large domains**</span></span>
  
<span data-ttu-id="5838a-163">Wenn Sie über eine große Domäne mit Zehntausenden von Benutzern verfügen, kann das Ausprobieren einiger beispiele, die wir in diesem Artikel zeigen, zu Drosselung führen.</span><span class="sxs-lookup"><span data-stu-id="5838a-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="5838a-164">Basierend auf Faktoren wie Rechenleistung und verfügbarer Netzwerkbandbreite versuchen Sie möglicherweise, gleichzeitig zu viel zu tun.</span><span class="sxs-lookup"><span data-stu-id="5838a-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="5838a-165">Große Organisationen möchten einige dieser PowerShell-Vorgänge möglicherweise in zwei Befehle aufteilen.</span><span class="sxs-lookup"><span data-stu-id="5838a-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="5838a-166">Der folgende Befehl gibt z. B. alle Benutzerkonten zurück und zeigt den Namen und Speicherort für die einzelnen Benutzerkonten an:</span><span class="sxs-lookup"><span data-stu-id="5838a-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="5838a-167">Das funktioniert auch gut bei kleineren Domänen.</span><span class="sxs-lookup"><span data-stu-id="5838a-167">That works great for smaller domains.</span></span> <span data-ttu-id="5838a-168">In einer großen Organisation können Sie diesen Vorgang jedoch in zwei Befehle aufteilen: einen Befehl zum Speichern der Benutzerkontoinformationen in einer Variablen und einen anderen, um die erforderlichen Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5838a-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="5838a-169">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5838a-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="5838a-170">Die Interpretation dieser Gruppe von PowerShell-Befehlen ist:</span><span class="sxs-lookup"><span data-stu-id="5838a-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="5838a-171">Laden Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen namens $x (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="5838a-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="5838a-172">Zeigt den Inhalt der Variablen *$x* an, enthält jedoch nur den Namen und den Speicherort für jeden Benutzer (**$x | Wählen Sie DisplayName, UsageLocation** aus.</span><span class="sxs-lookup"><span data-stu-id="5838a-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="5838a-173">Microsoft 365 verfügt über Features, die Sie nur mit PowerShell für Microsoft 365 konfigurieren können</span><span class="sxs-lookup"><span data-stu-id="5838a-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="5838a-174">Das Microsoft 365 Admin Center soll Zugriff auf allgemeine, nützliche Verwaltungsaufgaben bieten, die für die meisten Umgebungen gelten.</span><span class="sxs-lookup"><span data-stu-id="5838a-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="5838a-175">Anders ausgedrückt: Das Microsoft 365 Admin Center wurde so konzipiert, dass der typische Administrator die gängigsten Verwaltungsaufgaben ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="5838a-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="5838a-176">Es gibt jedoch einige Aufgaben, die im Admin Center nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="5838a-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="5838a-177">Beispielsweise bietet das Skype for Business Online Admin Center einige Optionen zum Erstellen benutzerdefinierter Besprechungseinladungen:</span><span class="sxs-lookup"><span data-stu-id="5838a-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Beispiel für die Anzeige von benutzerdefinierten Besprechungseinladungen im Skype for Business Online Admin Center](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="5838a-179">Mit diesen Einstellungen können Sie Besprechungseinladungen eine gewisse persönliche Note und Professionalität verleihen.</span><span class="sxs-lookup"><span data-stu-id="5838a-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="5838a-180">Es gibt jedoch mehr für Besprechungskonfigurationseinstellungen, als einfach benutzerdefinierte Besprechungseinladungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5838a-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="5838a-181">Besprechungen ermöglichen standardmäßig beispielsweise Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5838a-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="5838a-182">anonymen Benutzern, automatischen Zugang zu jeder Besprechung zu erhalten</span><span class="sxs-lookup"><span data-stu-id="5838a-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="5838a-183">Teilnehmern, die Besprechung aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="5838a-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="5838a-184">das Festlegen aller Benutzer in Ihrer Organisation als Referenten, wenn sie an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="5838a-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="5838a-185">Diese Einstellungen sind im Skype for Business Online Admin Center nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5838a-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="5838a-186">Sie können sie über PowerShell für Microsoft 365 steuern.</span><span class="sxs-lookup"><span data-stu-id="5838a-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="5838a-187">Hier ist ein Befehl, der diese drei Einstellungen deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="5838a-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="5838a-188">Zum Ausführen dieses Befehls müssen Sie das [Skype for Business Online PowerShell-Modul installieren. ](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="5838a-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="5838a-189">Die Interpretation dieses PowerShell-Befehls ist:</span><span class="sxs-lookup"><span data-stu-id="5838a-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="5838a-190">Deaktivieren Sie in den Einstellungen für neue Skype for Business Online-Besprechungen (**Set-CsMeetingConfiguration**), anonymen Benutzern den automatischen Eingang zu Besprechungen zu ermöglichen (**-AdmitAnonymousUsersByDefault $False**).</span><span class="sxs-lookup"><span data-stu-id="5838a-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="5838a-191">Deaktivieren Der Teilnehmer kann Besprechungen aufzeichnen (**-AllowConferenceRecording $False**).</span><span class="sxs-lookup"><span data-stu-id="5838a-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="5838a-192">Geben Sie nicht alle Benutzer aus Ihrer Organisation als Moderatoren an (**-DesignateAsPresenter "None"**).</span><span class="sxs-lookup"><span data-stu-id="5838a-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="5838a-193">Führen Sie diesen Befehl aus, um diese Standardeinstellungen wiederherzustellen (aktivieren Sie die Optionen):</span><span class="sxs-lookup"><span data-stu-id="5838a-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="5838a-194">Es gibt auch andere ähnliche Szenarien, weshalb Administratoren wissen sollten, wie PowerShell für Microsoft 365-Befehle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5838a-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="5838a-195">PowerShell für Microsoft 365 ist ideal für Massenvorgänge</span><span class="sxs-lookup"><span data-stu-id="5838a-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="5838a-196">Visuelle Schnittstellen wie das Microsoft 365 Admin Center sind am wertvollsten, wenn Sie über einen einzelnen Vorgang verfügen.</span><span class="sxs-lookup"><span data-stu-id="5838a-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="5838a-197">Wenn Sie beispielsweise ein Benutzerkonto deaktivieren müssen, können Sie das Admin Center verwenden, um ein Kontrollkästchen schnell zu finden und zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5838a-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="5838a-198">Dies ist möglicherweise einfacher als das Ausführen eines ähnlichen Vorgangs in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5838a-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="5838a-199">Wenn Sie jedoch viele Dinge oder ausgewählte Dinge in einer großen Reihe anderer Dinge ändern müssen, ist das Microsoft 365 Admin Center möglicherweise nicht das beste Tool.</span><span class="sxs-lookup"><span data-stu-id="5838a-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="5838a-200">Nehmen wir beispielsweise an, Sie müssen das Präfix für Tausende von Telefonnummern ändern oder den bestimmten Benutzer *Ken Myer* von allen SharePoint Online-Websites entfernen.</span><span class="sxs-lookup"><span data-stu-id="5838a-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="5838a-201">Wie würden Sie dies im Microsoft 365 Admin Center tun?</span><span class="sxs-lookup"><span data-stu-id="5838a-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="5838a-202">Im letzten Beispiel sagen Sie, Sie haben mehrere hundert SharePoint Online-Websites, und Sie wissen nicht, bei welchen Ken Meyer ein Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="5838a-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="5838a-203">Sie müssen im Microsoft 365 Admin Center beginnen und dann dieses Verfahren für jede Website ausführen:</span><span class="sxs-lookup"><span data-stu-id="5838a-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="5838a-204">Wählen Sie die **URL** der Website aus.</span><span class="sxs-lookup"><span data-stu-id="5838a-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="5838a-205">Wählen Sie **im Feld Websitesammlungseigenschaften** den **Link Websiteadresse** aus, um die Website zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5838a-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="5838a-206">Wählen Sie auf der Website Freigeben **aus.**</span><span class="sxs-lookup"><span data-stu-id="5838a-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="5838a-207">Wählen Sie **im** Dialogfeld Freigeben den Link aus, der alle Benutzer mit Berechtigungen für die Website zeigt:</span><span class="sxs-lookup"><span data-stu-id="5838a-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![Beispiel der Anzeige der Mitglieder einer SharePoint Online-Website im SharePoint Online Admin Center.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="5838a-209">Wählen Sie **im Dialogfeld** Freigegeben mit die Option **Erweitert aus.**</span><span class="sxs-lookup"><span data-stu-id="5838a-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="5838a-210">Scrollen Sie in der Liste der Benutzer nach unten, suchen und wählen Sie Ken Myer aus (vorausgesetzt, er verfügt über Berechtigungen für die Website), und wählen Sie **dann Benutzerberechtigungen entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="5838a-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="5838a-211">Dies würde für *mehrere* hundert Websites sehr lange dauern.</span><span class="sxs-lookup"><span data-stu-id="5838a-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="5838a-212">Die Alternative besteht im Ausführen des folgenden Befehls in PowerShell für Microsoft 365, um Ken Myer von allen Ihren Websites zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="5838a-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="5838a-213">Für diesen Befehl müssen Sie das [SharePoint Online PowerShell-Modul installieren.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="5838a-213">This command requires that you install the [SharePoint Online PowerShell module](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="5838a-214">Die Interpretation dieses PowerShell-Befehls lautet: Alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement (**Get-SPOSite**) und für jede Website Ken Meyer aus der Liste der Benutzer entfernen, die darauf zugreifen können (**ForEach {Remove-SPOUser -Site $ \_ . Url -LoginName "kenmyer \@ litwareinc.com"}**).</span><span class="sxs-lookup"><span data-stu-id="5838a-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="5838a-215">Wir teilen Microsoft 365 mit, Ken Meyer von jeder Website zu entfernen, einschließlich derjenigen, auf die er keinen Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="5838a-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="5838a-216">Die Ergebnisse zeigen also Fehler für websites, auf die er keinen Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="5838a-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="5838a-217">Wir können eine zusätzliche Bedingung für diesen Befehl verwenden, um Ken Meyer nur von den Websites zu entfernen, auf deren Anmeldeliste er sich befindet.</span><span class="sxs-lookup"><span data-stu-id="5838a-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="5838a-218">Die zurückgegebenen Fehler verursachen jedoch keinen Schaden für die Websites selbst.</span><span class="sxs-lookup"><span data-stu-id="5838a-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="5838a-219">Dieser Befehl kann einige Minuten dauern, bis er für Hunderte von Websites ausgeführt wird, anstatt stundenlang durch das Microsoft 365 Admin Center zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5838a-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="5838a-220">Hier sehen Sie ein weiteres Beispiel für einen Massenvorgang.</span><span class="sxs-lookup"><span data-stu-id="5838a-220">Here's another bulk operation example.</span></span> <span data-ttu-id="5838a-221">Verwenden Sie diesen Befehl, um *"Bonnie Kearney",* einen neuen SharePoint-Administrator, zu allen Websites in der Organisation hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="5838a-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="5838a-222">Die Interpretation dieses PowerShell-Befehls lautet: Alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement erhalten und für jede Website den Zugriff auf "Bonnie Kearney" zulassen, indem sie ihren Anmeldenamen der Gruppe Mitglieder der Website hinzufügen (**ForEach {Add-SPOUser -Site $ \_ . Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).</span><span class="sxs-lookup"><span data-stu-id="5838a-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="5838a-223">PowerShell für Microsoft 365 ist beim Filtern von Daten sehr gut</span><span class="sxs-lookup"><span data-stu-id="5838a-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="5838a-224">Das Microsoft 365 Admin Center bietet verschiedene Möglichkeiten, Ihre Daten zu filtern, um eine gezielte Teilmenge von Informationen auf einfache Weise zu finden.</span><span class="sxs-lookup"><span data-stu-id="5838a-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="5838a-225">Mit Exchange können Sie beispielsweise leicht nach praktisch jeder Eigenschaft eines Benutzerpostfachs filtern.</span><span class="sxs-lookup"><span data-stu-id="5838a-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="5838a-226">Hier ist beispielsweise die Liste der Postfächer für alle Benutzer, die in bloomington leben:</span><span class="sxs-lookup"><span data-stu-id="5838a-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Beispiel für eine erweiterte Suche im Microsoft 365 Admin Center für die Liste der Postfächer für alle Benutzer, die in bloomington leben.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="5838a-228">Im Exchange Admin Center können Sie auch Filterkriterien kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5838a-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="5838a-229">Beispielsweise finden Sie die Postfächer für alle Personen, die in Bloomington leben und in der Finanzabteilung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5838a-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="5838a-230">Es gibt jedoch Einschränkungen für das, was Sie im Exchange Admin Center tun können.</span><span class="sxs-lookup"><span data-stu-id="5838a-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="5838a-231">Beispielsweise konnten Sie nicht so einfach die Postfächer von Personen finden, die in *Bloomington* oder San Diego leben, oder die Postfächer für alle Personen, die nicht in Bloomington leben.</span><span class="sxs-lookup"><span data-stu-id="5838a-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="5838a-232">Sie können den folgenden PowerShell für Microsoft 365-Befehl verwenden, um eine Liste der Postfächer für alle Personen zu erhalten, die in Bloomington oder San Diego leben:</span><span class="sxs-lookup"><span data-stu-id="5838a-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="5838a-233">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="5838a-234">Die Interpretation dieses PowerShell-Befehls lautet: Alle Benutzer im aktuellen Microsoft 365-Abonnement mit einem Postfach in San Diego oder Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . City -eq "San Diego" -or $ \_ . City -eq "Bloomington")}**), und zeigen Sie dann den Namen und die Stadt für jede (**Select DisplayName, City**) an.</span><span class="sxs-lookup"><span data-stu-id="5838a-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="5838a-235">Und hier ist der Befehl zum Auflisten aller Postfächer für Personen, die an einem beliebigen Ort mit Ausnahme von Bloomington leben:</span><span class="sxs-lookup"><span data-stu-id="5838a-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="5838a-236">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="5838a-237">Die Interpretation dieses PowerShell-Befehls lautet: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$ \_ . RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**), und zeigen Sie dann den Namen und die Stadt für jeden an.</span><span class="sxs-lookup"><span data-stu-id="5838a-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="5838a-238">Verwenden von Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="5838a-238">Use wildcards</span></span>

<span data-ttu-id="5838a-239">Sie können auch Platzhalterzeichen in Ihren PowerShell-Filtern verwenden, um einen Teil eines Namens zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5838a-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="5838a-240">Angenommen, Sie suchen nach einem Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="5838a-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="5838a-241">Sie können sich nur daran erinnern, dass der Nachname des Benutzers *Anderson* oder *vielleicht Henderson* oder *Jorgenson war.*</span><span class="sxs-lookup"><span data-stu-id="5838a-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="5838a-242">Sie können diesen Benutzer im Microsoft 365 Admin Center nachverfolgen, indem Sie das Suchtool verwenden und drei verschiedene Suchen durchführen:</span><span class="sxs-lookup"><span data-stu-id="5838a-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="5838a-243">Eine für  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="5838a-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="5838a-244">Eine für  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="5838a-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="5838a-245">Und eine für  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="5838a-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="5838a-246">Da alle drei namen in "son" enden, können Sie PowerShell mitteilen, dass alle Benutzer angezeigt werden, deren Name in "son" endet.</span><span class="sxs-lookup"><span data-stu-id="5838a-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="5838a-247">Hier ist der Befehl:</span><span class="sxs-lookup"><span data-stu-id="5838a-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="5838a-248">Die Interpretation dieses PowerShell-Befehls lautet: Alle Benutzer im aktuellen Microsoft 365-Abonnement erhalten, verwenden Sie jedoch einen Filter, der nur die Benutzer auflistet, deren Nachnamen in "son" enden (**-Filter '{LastName -like " \* son"}'**).</span><span class="sxs-lookup"><span data-stu-id="5838a-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="5838a-249">Der steht für einen beliebigen Satz von Zeichen, bei denen es sich um Buchstaben \* im Nachnamen des Benutzers handelt.</span><span class="sxs-lookup"><span data-stu-id="5838a-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="5838a-250">PowerShell für Microsoft 365 erleichtert das Drucken oder Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="5838a-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="5838a-251">Im Microsoft 365 Admin Center können Sie Listen mit Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5838a-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="5838a-252">Hier ist ein Beispiel für das Skype for Business Online Admin Center, in dem eine Liste der Benutzer angezeigt wird, die für Skype for Business Online aktiviert wurden:</span><span class="sxs-lookup"><span data-stu-id="5838a-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Beispiel für das Skype for Business Online Admin Center, in dem eine Liste von Benutzern angezeigt wird, die für Skype for Business Online aktiviert wurden.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="5838a-254">Um diese Informationen in einer Datei zu speichern, müssen Sie sie in ein Dokument oder ein Microsoft Excel-Arbeitsblatt einfügen.</span><span class="sxs-lookup"><span data-stu-id="5838a-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="5838a-255">In beiden Fällen kann zusätzliche Formatierung erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="5838a-255">Either case might require additional formatting.</span></span> <span data-ttu-id="5838a-256">Darüber hinaus bietet das Microsoft 365 Admin Center keine Möglichkeit, die angezeigte Liste direkt zu drucken.</span><span class="sxs-lookup"><span data-stu-id="5838a-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="5838a-257">Glücklicherweise können Sie PowerShell verwenden, um die Liste nicht nur zu anzeigen, sondern sie in einer Datei zu speichern, die problemlos in Excel importiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5838a-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="5838a-258">Hier ist ein Beispielbefehl zum Speichern von Skype for Business Online-Benutzerdaten in einer CSV-Datei (Comma-Separated Values), die dann einfach als Tabelle in einem Excel-Arbeitsblatt importiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="5838a-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="5838a-259">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-259">Here's an example of the results:</span></span>
  
![Beispiel für eine Tabelle, die in ein Excel-Arbeitsblatt für Skype for Business Online-Benutzerdaten importiert wurde, die in einer durch Kommas getrennten Wertedatei gespeichert wurden.](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="5838a-261">Die Interpretation dieses PowerShell-Befehls ist: Alle Skype for Business Online-Benutzer im aktuellen Microsoft 365-Abonnement erhalten (**Get-CsOnlineUser**); nur den Benutzernamen, den UPN und den Speicherort abrufen (**Select DisplayName, UserPrincipalName, UsageLocation**); und speichern Sie diese Informationen dann in einer CSV-Datei namens C: \\ Logs \\SfBUsers.csv (**Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation**).</span><span class="sxs-lookup"><span data-stu-id="5838a-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="5838a-262">Sie können auch Optionen verwenden, um diese Liste als XML-Datei oder HTML-Seite zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5838a-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="5838a-263">Mit zusätzlichen PowerShell-Befehlen könnten Sie sie direkt als Excel-Datei speichern, mit jeder beliebigen benutzerdefinierten Formatierung.</span><span class="sxs-lookup"><span data-stu-id="5838a-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="5838a-264">Sie können auch die Ausgabe eines PowerShell-Befehls senden, der eine Liste direkt an den Standarddrucker in Windows anzeigt.</span><span class="sxs-lookup"><span data-stu-id="5838a-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="5838a-265">Hier ist ein Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="5838a-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="5838a-266">Das gedruckte Dokument sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5838a-266">Here's what your printed document will look like:</span></span>
  
![Beispiel für ein gedrucktes Dokument, das die Ausgabe eines PowerShell-Befehls war, der direkt an den Standarddrucker in Windows gesendet wurde.](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="5838a-268">Die Interpretation dieses #A0 ist: Alle Skype for Business #A1 im aktuellen Microsoft 365-Abonnement erhalten; nur den Benutzernamen, den UPN und den Speicherort abrufen; und senden Sie diese Informationen dann an den Standardmäßigen **Windows-Drucker ( Out-Printer**).</span><span class="sxs-lookup"><span data-stu-id="5838a-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="5838a-269">Das gedruckte Dokument hat dieselbe einfache Formatierung wie die Anzeige im PowerShell-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="5838a-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="5838a-270">Um eine Kopie zu erhalten, fügen Sie einfach **| Out-Printer** bis zum Ende des Befehls.</span><span class="sxs-lookup"><span data-stu-id="5838a-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="5838a-271">Mit PowerShell für Microsoft 365 können Sie serverübergreifend verwalten</span><span class="sxs-lookup"><span data-stu-id="5838a-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="5838a-272">Die Komponenten aus Microsoft 365 sind für die Zusammenarbeit konzipiert.</span><span class="sxs-lookup"><span data-stu-id="5838a-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="5838a-273">Angenommen, Sie fügen Microsoft 365 einen neuen Benutzer hinzu, und Sie geben informationen wie die Abteilung und Telefonnummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="5838a-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="5838a-274">Diese Informationen sind dann verfügbar, wenn Sie auf die Informationen des Benutzers in einem der Microsoft 365-Dienste zugreifen: Skype for Business Online, Exchange oder SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5838a-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="5838a-275">Hierbei handelt es sich um allgemeine Informationen, die für die ganze Produktsuite gleich sind.</span><span class="sxs-lookup"><span data-stu-id="5838a-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="5838a-276">Produktspezifische Informationen, z. B. Informationen zum Exchange-Postfach eines Benutzers, sind in der Regel nicht in der gesamten Suite verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5838a-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="5838a-277">Informationen dazu, ob das Postfach eines Benutzers aktiviert ist oder nicht, sind beispielsweise nur im Exchange Admin Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5838a-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="5838a-278">Angenommen, Sie möchten einen Bericht erstellen, in dem die folgenden Informationen für alle Benutzer enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="5838a-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="5838a-279">Den Anzeigenamen des Benutzers</span><span class="sxs-lookup"><span data-stu-id="5838a-279">The user's display name</span></span>
    
- <span data-ttu-id="5838a-280">Gibt an, ob der Benutzer für Microsoft 365 lizenziert ist</span><span class="sxs-lookup"><span data-stu-id="5838a-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="5838a-281">Ob das Exchange-Postfach des Benutzers aktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="5838a-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="5838a-282">Ob der Benutzer für Skype for Business Online aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="5838a-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="5838a-283">Sie können einen solchen Bericht nicht einfach im Microsoft 365 Admin Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="5838a-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5838a-284">Stattdessen müssten Sie ein separates Dokument erstellen, um die Informationen zu speichern, z. B. ein Excel-Arbeitsblatt.</span><span class="sxs-lookup"><span data-stu-id="5838a-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="5838a-285">Dann erhalten Sie alle Benutzernamen und Lizenzierungsinformationen aus dem Microsoft 365 Admin Center, erhalten Postfachinformationen aus dem Exchange Admin Center, erhalten Skype for Business Online-Informationen aus dem Skype for Business Online Admin Center, und kombinieren Sie diese Informationen.</span><span class="sxs-lookup"><span data-stu-id="5838a-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="5838a-286">Die Alternative besteht in der Verwendung eines PowerShell-Skripts, um den Bericht für Sie zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5838a-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="5838a-287">Das folgende Beispielskript ist komplizierter als die Befehle, die Sie bisher in diesem Artikel gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="5838a-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="5838a-288">Es zeigt jedoch das Potenzial der Verwendung von PowerShell zum Erstellen von Informationsansichten, die andernfalls schwer zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="5838a-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="5838a-289">Hier ist das Skript zum Kompilieren und Anzeigen der benötigten Liste:</span><span class="sxs-lookup"><span data-stu-id="5838a-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="5838a-290">Hier ein Beispiel für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5838a-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="5838a-291">Die Interpretation dieses PowerShell-Skripts ist:</span><span class="sxs-lookup"><span data-stu-id="5838a-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="5838a-292">Laden Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen mit dem Namen *$x* (**$x = Get-AzureADUser**).</span><span class="sxs-lookup"><span data-stu-id="5838a-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="5838a-293">Starten Sie eine Schleife, die über alle Benutzer in der Variablen $x (**foreach ($i in $x) ausgeführt wird.**</span><span class="sxs-lookup"><span data-stu-id="5838a-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="5838a-294">Definieren Sie eine Variable *namens $y* und speichern Sie die Postfachinformationen des Benutzers in dieser ( $y =**Get-Mailbox -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="5838a-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="5838a-295">Fügen Sie den Benutzerinformationen mit dem Namen *IsMailBoxEnabled* eine neue Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="5838a-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="5838a-296">Legen Sie ihn auf den Wert der IsMailBoxEnabled-Eigenschaft des Postfachs des Benutzers fest (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="5838a-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="5838a-297">Definieren Sie eine Variable *namens $y*, und speichern Sie die Skype for Business Online-Informationen des Benutzers in dieser ( $y =**Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="5838a-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="5838a-298">Fügen Sie den Benutzerinformationen mit dem Namen *EnabledForSfB* eine neue Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="5838a-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="5838a-299">Legen Sie ihn auf den Wert der Enabled-Eigenschaft der Skype for Business Online-Informationen des Benutzers fest (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span><span class="sxs-lookup"><span data-stu-id="5838a-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="5838a-300">Zeigt die Liste der Benutzer an, enthält jedoch nur ihren Namen, ob sie lizenziert sind, und die beiden neuen Eigenschaften, die angeben, ob ihr Postfach aktiviert ist und ob sie für Skype for Business Online aktiviert sind (**$x | Wählen Sie DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** aus.</span><span class="sxs-lookup"><span data-stu-id="5838a-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5838a-301">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5838a-301">See also</span></span>

[<span data-ttu-id="5838a-302">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5838a-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5838a-303">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5838a-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5838a-304">Verwenden der Windows PowerShell zum Erstellen von Berichten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5838a-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)