---
title: Migrieren von älteren eDiscovery-Suchen und -Haltedaten zum Microsoft 365 Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ef5562aa6f5c7519d19452100b55dd4bc30d4126
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926323"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="6af93-102">Migrieren von älteren eDiscovery-Suchen und -Haltedaten zum Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6af93-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="6af93-103">Das Microsoft 365 Compliance Center bietet eine verbesserte Erfahrung für die eDiscovery-Verwendung, einschließlich: höhere Zuverlässigkeit, bessere Leistung und viele Features, die auf eDiscovery-Workflows zugeschnitten sind, einschließlich Fällen, in denen Ihre Inhalte nach Inhalten organisiert werden, Überprüfungssätze zur Überprüfung von Inhalten und Analysen, um daten für die Überprüfung zu überprüfen, z. B. beinahe duplizierte Gruppierungen, E-Mail-Threading, Designsanalyse und Vorhersagecodierung.</span><span class="sxs-lookup"><span data-stu-id="6af93-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="6af93-104">Damit Kunden die neuen und verbesserten Funktionen nutzen können, enthält dieser Artikel grundlegende Anleitungen zum Migrieren von In-Place eDiscovery-Suchen und -Haltefunktionen vom Exchange Admin Center zum Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="6af93-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="6af93-105">Da es viele verschiedene Szenarien gibt, bietet dieser Artikel allgemeine Anleitungen für die Übergangssuche und die Übergänge zu einem zentralen eDiscovery-Fall im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="6af93-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6af93-106">Die Verwendung von eDiscovery-Fällen ist nicht immer erforderlich, sie fügen jedoch eine zusätzliche Sicherheitsebene hinzu, indem Sie Berechtigungen zuweisen können, um zu steuern, wer Zugriff auf die eDiscovery-Fälle in Ihrer Organisation hat.</span><span class="sxs-lookup"><span data-stu-id="6af93-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6af93-107">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="6af93-107">Before you begin</span></span>

- <span data-ttu-id="6af93-108">Sie müssen Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center sein, um die in diesem Artikel beschriebenen PowerShell-Befehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6af93-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="6af93-109">Sie müssen auch Mitglied der Rollengruppe Discoveryverwaltung im Exchange Admin Center sein.</span><span class="sxs-lookup"><span data-stu-id="6af93-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="6af93-110">Dieser Artikel enthält Anleitungen zum Erstellen eines eDiscovery-Halteraums.</span><span class="sxs-lookup"><span data-stu-id="6af93-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="6af93-111">Die Halterichtlinie wird über einen asynchronen Prozess auf Postfächer angewendet.</span><span class="sxs-lookup"><span data-stu-id="6af93-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="6af93-112">Beim Erstellen eines eDiscovery-Halteraums müssen Sie sowohl caseHoldPolicy als auch CaseHoldRule erstellen, andernfalls wird der Halteraum nicht erstellt, und Inhaltsstandorte werden nicht in die Warteschleife gesetzt.</span><span class="sxs-lookup"><span data-stu-id="6af93-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="6af93-113">Schritt 1: Herstellen einer Verbindung mit Exchange Online PowerShell und & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="6af93-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6af93-114">Der erste Schritt besteht im Herstellen einer Verbindung mit Exchange Online PowerShell und Security & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6af93-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="6af93-115">Sie können das folgende Skript kopieren, in ein PowerShell-Fenster einfügen und dann ausführen.</span><span class="sxs-lookup"><span data-stu-id="6af93-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="6af93-116">Sie werden zur Eingabe von Anmeldeinformationen für die Organisation aufgefordert, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="6af93-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="6af93-117">Sie müssen die Befehle in den folgenden Schritten in dieser PowerShell-Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6af93-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="6af93-118">Schritt 2: Eine Liste der eDiscovery-In-Place mithilfe von Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6af93-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="6af93-119">Nachdem Sie sich authentifiziert haben, können Sie eine Liste der In-Place eDiscovery-Suchen erhalten, indem Sie das **Cmdlet Get-MailboxSearch** ausführen.</span><span class="sxs-lookup"><span data-stu-id="6af93-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="6af93-120">Kopieren Sie den folgenden Befehl, und fügen Sie ihn in PowerShell ein, und führen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="6af93-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="6af93-121">Eine Liste der Suchbegriffe wird mit ihren Namen und dem Status aller In-Place aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6af93-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="6af93-122">Die Ausgabe des Cmdlets ähnelt der folgenden:</span><span class="sxs-lookup"><span data-stu-id="6af93-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell-BeispielGet-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="6af93-124">Schritt 3: Informationen zu eDiscoveryIn-Place suchen und In-Place, die Sie migrieren möchten</span><span class="sxs-lookup"><span data-stu-id="6af93-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="6af93-125">Auch hier verwenden Sie das **Cmdlet Get-MailboxSearch,** aber dieses Mal, um die Eigenschaften der Suche zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6af93-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="6af93-126">Sie können diese Eigenschaften später in einer Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="6af93-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="6af93-127">Im folgenden Beispiel werden die Ergebnisse des **Cmdlets Get-MailboxSearch** in einer Variablen gespeichert und dann die Eigenschaften der Suche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6af93-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="6af93-128">Die Ausgabe dieser beiden Befehle ähnelt der folgenden:</span><span class="sxs-lookup"><span data-stu-id="6af93-128">The output of these two commands will be similar to the following:</span></span>

![Beispiel für die PowerShell-Ausgabe von Get-MailboxSearch für eine einzelne Suche](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="6af93-130">Die Dauer des In-Place in diesem Beispiel ist unbegrenzt (*ItemHoldPeriod: Unlimited*).</span><span class="sxs-lookup"><span data-stu-id="6af93-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="6af93-131">Dies ist typisch für eDiscovery- und rechtliche Untersuchungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="6af93-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="6af93-132">Wenn die Aufbewahrungsdauer einen anderen Wert als auf unbestimmte Zeit hat, liegt der Grund wahrscheinlich daran, dass der Haltespeicher zum Beibehalten von Inhalten in einem Aufbewahrungsszenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6af93-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="6af93-133">Anstatt die eDiscovery-Cmdlets in Security & Compliance Center PowerShell für Aufbewahrungsszenarien zu verwenden, sollten Sie [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) und [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) verwenden, um Inhalte zu behalten.</span><span class="sxs-lookup"><span data-stu-id="6af93-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="6af93-134">Das Ergebnis der Verwendung dieser Cmdlets ähnelt der Verwendung von **New-CaseHoldPolicy** und **New-CaseHoldRule,** Sie können jedoch einen Aufbewahrungszeitraum und eine Aufbewahrungsaktion angeben, z. B. das Löschen von Inhalten nach Ablauf des Aufbewahrungszeitraums.</span><span class="sxs-lookup"><span data-stu-id="6af93-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="6af93-135">Wenn Sie die Aufbewahrungs-Cmdlets verwenden, müssen Sie die Aufbewahrungsspeicher auch nicht einem eDiscovery-Fall zuordnen.</span><span class="sxs-lookup"><span data-stu-id="6af93-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="6af93-136">Schritt 4: Erstellen eines Falls im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6af93-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="6af93-137">Zum Erstellen eines eDiscovery-Halteraums müssen Sie einen eDiscovery-Fall erstellen, um den Halteraum zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6af93-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="6af93-138">Im folgenden Beispiel wird ein eDiscovery-Fall mit einem Namen Ihrer Wahl erstellt.</span><span class="sxs-lookup"><span data-stu-id="6af93-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="6af93-139">Die Eigenschaften des neuen Falls werden später in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6af93-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="6af93-140">Sie können diese Eigenschaften anzeigen, indem Sie den `$case | FL` Befehl ausführen, nachdem Sie den Fall erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="6af93-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Beispiel für das Ausführen des New-ComplianceCase Befehls](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="6af93-142">Schritt 5: Erstellen des eDiscovery-Halteraums</span><span class="sxs-lookup"><span data-stu-id="6af93-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="6af93-143">Nachdem der Fall erstellt wurde, können Sie den Halteraum erstellen und dem Fall zuordnen, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="6af93-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="6af93-144">Beachten Sie, dass Sie sowohl eine Fall-Halterichtlinie als auch eine Fall-Halteregel erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6af93-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="6af93-145">Wenn die Fall-Halteregel nicht erstellt wird, nachdem Sie eine Fall-Halterichtlinie erstellt haben, wird die eDiscovery-Halterichtlinie nicht erstellt, und Inhalte werden nicht in den Halteraum gestellt.</span><span class="sxs-lookup"><span data-stu-id="6af93-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="6af93-146">Führen Sie die folgenden Befehle aus, um den eDiscovery-Halteraum neu zu erstellen, den Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6af93-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="6af93-147">In diesen Beispielen werden die Eigenschaften In-Place aus Schritt 3 verwendet, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6af93-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="6af93-148">Der erste Befehl erstellt eine neue Fallaufforderungsrichtlinie und speichert die Eigenschaften in einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="6af93-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="6af93-149">Mit dem zweiten Befehl wird die entsprechende Fallaufforderungsregel erstellt.</span><span class="sxs-lookup"><span data-stu-id="6af93-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Beispiel für die Verwendung von Cmdlets NewCaseHoldPolicy und NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="6af93-151">Schritt 6: Überprüfen des eDiscovery-Halteraums</span><span class="sxs-lookup"><span data-stu-id="6af93-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="6af93-152">Um sicherzustellen, dass beim Erstellen des Haltestatus keine Probleme auftreten, sollten Sie überprüfen, ob der Status der Halteverteilung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6af93-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="6af93-153">Verteilung bedeutet, dass der Halteraum auf alle im *ExchangeLocation-Parameter* im vorherigen Schritt angegebenen Inhaltspositionen angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6af93-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="6af93-154">Dazu können Sie das **Cmdlet Get-CaseHoldPolicy** ausführen.</span><span class="sxs-lookup"><span data-stu-id="6af93-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="6af93-155">Da die in der im vorherigen *Schritt $policy* gespeicherten Eigenschaften nicht automatisch in der Variablen aktualisiert werden, müssen Sie das Cmdlet erneut ausführen, um sicherzustellen, dass die Verteilung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6af93-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="6af93-156">Es kann zwischen 5 Minuten und 24 Stunden dauern, bis Case Hold-Richtlinien erfolgreich verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="6af93-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="6af93-157">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob der eDiscovery-Halteraum erfolgreich verteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="6af93-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="6af93-158">Der Wert **von Success** für die *DistributionStatus-Eigenschaft* gibt an, dass der Haltestatus erfolgreich an den Inhaltsstandorten platziert wurde.</span><span class="sxs-lookup"><span data-stu-id="6af93-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="6af93-159">Wenn die Verteilung noch nicht abgeschlossen ist, wird der Wert **Ausstehend** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6af93-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell Get-CaseHoldPolicy Beispiel](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="6af93-161">Schritt 7: Erstellen der Suche</span><span class="sxs-lookup"><span data-stu-id="6af93-161">Step 7: Create the search</span></span>

<span data-ttu-id="6af93-162">Der letzte Schritt besteht in der neu erstellten Suche, die Sie in Schritt 3 identifiziert haben, und ordnen Sie sie dem Fall zu.</span><span class="sxs-lookup"><span data-stu-id="6af93-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="6af93-163">Nachdem Sie die Suche erstellt haben, können Sie sie mit dem **Cmdlet Start-ComplianceSearch** ausführen oder zu einem späteren Zeitpunkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="6af93-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch Beispiel](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="6af93-165">Schritt 8: Überprüfen von Fall, Halte und Suche im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6af93-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="6af93-166">Um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist, wechseln Sie zum Microsoft 365 Compliance Center unter , und klicken Sie auf [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="6af93-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 Compliance Center eDiscovery](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="6af93-168">Der fall, den Sie in Schritt 3 erstellt haben, wird auf der **Seite Core eDiscovery** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6af93-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="6af93-169">Öffnen Sie den Fall, und beachten Sie dann den halte, den Sie in Schritt 4 in auf der Registerkarte Halte **halte erstellt** haben. Sie können auf den Haltestatus klicken, um Details anzuzeigen, einschließlich der Anzahl der Postfächer, auf die der Haltestatus angewendet wird, und den Verteilungsstatus.</span><span class="sxs-lookup"><span data-stu-id="6af93-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![eDiscovery im Microsoft 365 Compliance Center](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="6af93-171">Die suche, die Sie in Schritt 7  erstellt haben, wird auf der Registerkarte Suchen des eDiscovery-Falls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6af93-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![eDiscovery-Fallsuche im Microsoft 365 Compliance Center](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="6af93-173">Wenn Sie eine In-Place eDiscovery-Suche migrieren, sie jedoch keinem eDiscovery-Fall zuordnen, wird sie auf der Seite Inhaltssuche im Microsoft 365 Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6af93-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="6af93-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6af93-174">More information</span></span>

- <span data-ttu-id="6af93-175">Weitere Informationen zu In-Place eDiscovery & im Exchange Admin Center finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="6af93-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="6af93-176">Compliance-eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6af93-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="6af93-177">In-Situ-Speicher und Beweissicherungsverfahren</span><span class="sxs-lookup"><span data-stu-id="6af93-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="6af93-178">Weitere Informationen zu den im Artikel verwendeten PowerShell-Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="6af93-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="6af93-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6af93-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="6af93-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="6af93-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="6af93-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="6af93-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="6af93-182">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="6af93-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="6af93-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="6af93-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="6af93-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6af93-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="6af93-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6af93-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="6af93-186">Weitere Informationen zum Microsoft 365 Compliance Center finden Sie [unter Overview of the Microsoft 365 Compliance Center](microsoft-365-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6af93-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>