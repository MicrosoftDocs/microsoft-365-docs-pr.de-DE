---
title: Migrieren von Legacy-eDiscovery-suchen und-Archiven zum Microsoft 365 Compliance Center
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 3d0bba3c75bda77cbffbbd515215a10d579755be
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558562"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="a585b-102">Migrieren von Legacy-eDiscovery-suchen und-Archiven zum Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a585b-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="a585b-103">Das Microsoft 365 Compliance Center bietet eine verbesserte Erfahrung für die eDiscovery-Verwendung, einschließlich: höhere Zuverlässigkeit, bessere Leistung und viele Features, die auf eDiscovery-Workflows zugeschnitten sind, einschließlich Fällen zum Organisieren Ihrer Inhalte nach Materie, Überprüfen der Sätze auf Überprüfen Sie Inhalte und Analysen zur Unterstützung von culldaten zur Überprüfung, beispielsweise in einer fast doppelten Gruppierung, in e-Mail-Threading, in der Design Analyse und in der Vorhersage Codierung.</span><span class="sxs-lookup"><span data-stu-id="a585b-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="a585b-104">Damit Kunden die neuen und verbesserten Funktionen nutzen können, bietet dieser Artikel grundlegende Anleitungen zur Migration von in-Place-eDiscovery-suchen und-Archiven vom Exchange Admin Center zum Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a585b-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="a585b-105">Da es viele unterschiedliche Szenarien gibt, finden Sie in diesem Artikel Allgemeine Anleitungen für Übergangs suchen und-Aufbewahrungen in einem zentralen eDiscovery-Fall im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a585b-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a585b-106">Die Verwendung von eDiscovery-Fällen ist nicht immer erforderlich, aber Sie fügen eine zusätzliche Sicherheitsebene hinzu, indem Sie Berechtigungen zuweisen, um zu steuern, wer Zugriff auf die eDiscovery-Fälle in Ihrer Organisation hat.</span><span class="sxs-lookup"><span data-stu-id="a585b-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a585b-107">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="a585b-107">Before you begin</span></span>

- <span data-ttu-id="a585b-108">Sie müssen Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security #a0 Compliance Center sein, um die in diesem Artikel beschriebenen PowerShell-Befehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a585b-108">You have to be a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="a585b-109">Außerdem müssen Sie Mitglied der Rollengruppe "Discoveryverwaltung" in der Exchange-Verwaltungskonsole sein.</span><span class="sxs-lookup"><span data-stu-id="a585b-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="a585b-110">Dieser Artikel enthält Anleitungen zum Erstellen eines eDiscovery-Haltestatus.</span><span class="sxs-lookup"><span data-stu-id="a585b-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="a585b-111">Die Aufbewahrungsrichtlinie wird über einen asynchronen Prozess auf Postfächer angewendet.</span><span class="sxs-lookup"><span data-stu-id="a585b-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="a585b-112">Wenn Sie einen eDiscovery-Speicher erstellen, müssen Sie sowohl eine CaseHoldPolicy als auch eine CaseHoldRule erstellen, andernfalls wird der Haltebereich nicht erstellt, und es werden keine inhaltsspeicherorte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a585b-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-office-365-security--compliance-center-powershell"></a><span data-ttu-id="a585b-113">Schritt 1: Herstellen einer Verbindung mit Exchange Online PowerShell und Office 365 Security #a0 Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="a585b-113">Step 1: Connect to Exchange Online PowerShell and Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a585b-114">Der erste Schritt besteht darin, eine Verbindung mit Exchange Online PowerShell und Office 365 Security #a0 Compliance Center PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a585b-114">The first step is to connect to Exchange Online PowerShell and Office 365 Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="a585b-115">Sie können das folgende Skript kopieren, in ein PowerShell-Fenster einfügen und dann ausführen.</span><span class="sxs-lookup"><span data-stu-id="a585b-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="a585b-116">Sie werden zur Eingabe von Anmeldeinformationen für die Organisation aufgefordert, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a585b-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session -AllowClobber -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="a585b-117">Sie müssen die Befehle in den folgenden Schritten in dieser PowerShell-Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="a585b-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="a585b-118">Schritt 2: Abrufen einer Liste von in-Place-eDiscovery-suchen mithilfe von Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="a585b-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="a585b-119">Nachdem Sie sich authentifiziert haben, können Sie eine Liste der Compliance-eDiscovery-suchen erhalten, indem Sie das Cmdlet **Get-MailboxSearch** ausführen.</span><span class="sxs-lookup"><span data-stu-id="a585b-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="a585b-120">Kopieren Sie den folgenden Befehl, und fügen Sie ihn in PowerShell ein, und führen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="a585b-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="a585b-121">Eine Liste der Suchvorgänge wird mit ihren Namen und dem Status einer in-Place-Aufbewahrungs Liste aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a585b-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="a585b-122">Die Ausgabe des Cmdlets ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a585b-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell-Beispiel Get-MailboxSearch](media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="a585b-124">Schritt 3: Abrufen von Informationen zu den Compliance-eDiscovery-suchen und in-Place-Archiven, die Sie migrieren möchten</span><span class="sxs-lookup"><span data-stu-id="a585b-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="a585b-125">Wieder verwenden Sie das Cmdlet **Get-MailboxSearch** , dieses Mal jedoch, um die Eigenschaften der Suche abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a585b-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="a585b-126">Sie können diese Eigenschaften in einer Variablen speichern, um Sie später zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a585b-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="a585b-127">Im folgenden Beispiel werden die Ergebnisse des Cmdlets **Get-MailboxSearch** in einer Variablen gespeichert, und anschließend werden die Eigenschaften der Suche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a585b-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="a585b-128">Die Ausgabe dieser beiden Befehle ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a585b-128">The output of these two commands will be similar to the following:</span></span>

![Beispiel für eine PowerShell-Ausgabe mit Get-MailboxSearch für eine individuelle Suche](media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="a585b-130">Die Dauer des in-situ-Speichers in diesem Beispiel ist unbestimmt (*ItemHoldPeriod: Unlimited*).</span><span class="sxs-lookup"><span data-stu-id="a585b-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="a585b-131">Dies ist typisch für eDiscovery-und rechtliche Ermittlungs Szenarien.</span><span class="sxs-lookup"><span data-stu-id="a585b-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="a585b-132">Wenn die Aufbewahrungsdauer einen anderen Wert als unbegrenzt hat, liegt der Grund wahrscheinlich daran, dass der Haltebereich zum Beibehalten von Inhalt in einem Aufbewahrungs Szenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a585b-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="a585b-133">Anstatt die eDiscovery-Cmdlets in Office 365 Security #a0 Compliance Center PowerShell für Aufbewahrungs Szenarien zu verwenden, empfehlen wir die Verwendung von [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy) und [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule) , um Inhalte beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="a585b-133">Instead of using the eDiscovery cmdlets in Office 365 Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="a585b-134">Das Ergebnis der Verwendung dieser Cmdlets ähnelt der Verwendung von **New-CaseHoldPolicy** und **New-CaseHoldRule**, aber Sie können einen Aufbewahrungszeitraum und eine Aufbewahrungsaktion angeben, beispielsweise das Löschen von Inhalten nach Ablauf des Aufbewahrungszeitraums.</span><span class="sxs-lookup"><span data-stu-id="a585b-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="a585b-135">Darüber hinaus ist es für die Verwendung der Aufbewahrungs-Cmdlets nicht erforderlich, die Aufbewahrungszeiträume einem eDiscovery-Fall zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a585b-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="a585b-136">Schritt 4: Erstellen eines Falls im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a585b-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="a585b-137">Um einen eDiscovery-Speicher zu erstellen, müssen Sie einen eDiscovery-Fall erstellen, dem der Haltestatus zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a585b-137">In order to create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="a585b-138">Im folgenden Beispiel wird ein eDiscovery-Fall mithilfe eines Namens Ihrer Wahl erstellt.</span><span class="sxs-lookup"><span data-stu-id="a585b-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="a585b-139">Die Eigenschaften des neuen Falls werden in einer Variablen gespeichert, um Sie später zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a585b-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="a585b-140">Sie können diese Eigenschaften anzeigen, indem Sie `$case | FL` den Befehl ausführen, nachdem Sie die Anfrage erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a585b-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

![Beispiel für das Ausführen des Befehls "New-ComplianceCase"](media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="a585b-142">Schritt 5: Erstellen des eDiscovery-Haltestatus</span><span class="sxs-lookup"><span data-stu-id="a585b-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="a585b-143">Nachdem der Fall erstellt wurde, können Sie den Haltebereich erstellen und ihn der Groß-/Kleinschreibung zuordnen, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a585b-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="a585b-144">Es ist wichtig zu beachten, dass Sie sowohl eine Case Hold-Richtlinie als auch eine Case Hold-Regel erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="a585b-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="a585b-145">Wenn die Case Hold-Regel nicht erstellt wird, nachdem Sie die Case Hold-Richtlinie erstellt haben, wird der eDiscovery-Speicher nicht erstellt, und alle Inhalte werden nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a585b-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="a585b-146">Führen Sie die folgenden Befehle aus, um die eDiscovery-Aufbewahrung neu zu erstellen, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a585b-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="a585b-147">In diesen Beispielen werden die Eigenschaften von in-situ-Speicher aus Schritt 3 verwendet, den Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a585b-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
$rule = New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Beispiel für die Verwendung von NewCaseHoldPolicy-und NewCaseHoldRule-Cmdlets](media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="a585b-149">Schritt 6: Überprüfen des eDiscovery-Haltestatus</span><span class="sxs-lookup"><span data-stu-id="a585b-149">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="a585b-150">Um sicherzustellen, dass beim Erstellen des Haltestatus keine Probleme aufgetreten sind, sollten Sie überprüfen, ob der halte Verteilungsstatus erfolgreich verläuft.</span><span class="sxs-lookup"><span data-stu-id="a585b-150">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="a585b-151">Verteilung bedeutet, dass der Haltebereich auf alle im *ExchangeLocation* -Parameter im vorherigen Schritt angegebenen inhaltsspeicherorte angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a585b-151">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="a585b-152">Dazu können Sie das Cmdlet **Get-CaseHoldPolicy** ausführen.</span><span class="sxs-lookup"><span data-stu-id="a585b-152">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="a585b-153">Da die Eigenschaften, die in der *$Policy* Variablen gespeichert wurden, die Sie im vorherigen Schritt erstellt haben, nicht automatisch in der Variablen aktualisiert werden, müssen Sie das Cmdlet erneut ausführen, um zu überprüfen, ob die Verteilung erfolgreich verläuft.</span><span class="sxs-lookup"><span data-stu-id="a585b-153">Because the properties saved to the *$policy* variable that you created in the previous step are not automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="a585b-154">Es kann zwischen 5 Minuten und 24 Stunden dauern, bis die Fall Aufbewahrungsrichtlinien erfolgreich verteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="a585b-154">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="a585b-155">Führen Sie den folgenden Befehl aus, um zu überprüfen, ob die eDiscovery-Aufbewahrung erfolgreich verteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="a585b-155">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="a585b-156">Der Wert von **Success** für die *Eigenschaften distributionstatus* -Eigenschaft gibt an, dass der Haltebereich erfolgreich an den Inhaltsspeicherorten positioniert wurde.</span><span class="sxs-lookup"><span data-stu-id="a585b-156">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="a585b-157">Wenn die Verteilung noch nicht abgeschlossen ist, wird der Wert **Ausstehend** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a585b-157">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell-Get-CaseHoldPolicy-Beispiel](media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="a585b-159">Schritt 7: Erstellen der Suche</span><span class="sxs-lookup"><span data-stu-id="a585b-159">Step 7: Create the search</span></span>

<span data-ttu-id="a585b-160">Der letzte Schritt besteht darin, die Suche neu zu erstellen, die Sie in Schritt 3 identifiziert haben, und Sie der Groß-/Kleinschreibung zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a585b-160">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="a585b-161">Nachdem Sie die Suche erstellt haben, können Sie Sie mit dem Cmdlet **Start-ComplianceSearch** ausführen oder zu einem späteren Zeitpunkt ausführen.</span><span class="sxs-lookup"><span data-stu-id="a585b-161">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch-Beispiel](media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="a585b-163">Schritt 8: Überprüfen der Groß-/Kleinschreibung, des Haltestatus und der Suche im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a585b-163">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="a585b-164">Um sicherzustellen, dass alles ordnungsgemäß eingerichtet ist, wechseln Sie zum Microsoft 365 Compliance [https://compliance.microsoft.com](https://compliance.microsoft.com)Center unter, und klicken Sie auf **eDiscovery #a0 Core**.</span><span class="sxs-lookup"><span data-stu-id="a585b-164">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 Compliance Center eDiscovery](media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="a585b-166">Der in Schritt 3 erstellte Fall wird auf der **zentralen eDiscovery** -Seite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a585b-166">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="a585b-167">Öffnen Sie den Fall, und beachten Sie dann die in Schritt 4 erstellte Aufbewahrungszeit auf der Registerkarte halte **Status** . Sie können auf den Haltebereich klicken, um Details anzuzeigen, einschließlich der Anzahl der Postfächer, auf die der Haltebereich angewendet wird, und des Verteilungsstatus.</span><span class="sxs-lookup"><span data-stu-id="a585b-167">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![eDiscovery hält im Microsoft 365 Compliance Center](media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="a585b-169">Die Suche, die Sie in Schritt 7 erstellt haben, wird auf der Registerkarte **Suchen** im eDiscovery-Fall aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a585b-169">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![eDiscovery-Fall Suche im Microsoft 365 Compliance Center](media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="a585b-171">Wenn Sie eine Compliance-eDiscovery-Suche migrieren, diese aber keinem eDiscovery-Fall zuordnen, wird Sie auf der Seite "Inhaltssuche" im Microsoft 365 Compliance Center aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a585b-171">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="a585b-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a585b-172">More information</span></span>

- <span data-ttu-id="a585b-173">Weitere Informationen zum Compliance-eDiscovery #a0 im Exchange Admin Center finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a585b-173">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="a585b-174">Compliance-eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a585b-174">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="a585b-175">In-Situ-Speicher und Beweissicherungsverfahren</span><span class="sxs-lookup"><span data-stu-id="a585b-175">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="a585b-176">Weitere Informationen zu den im Artikel verwendeten PowerShell-Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a585b-176">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="a585b-177">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="a585b-177">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [<span data-ttu-id="a585b-178">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="a585b-178">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [<span data-ttu-id="a585b-179">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="a585b-179">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [<span data-ttu-id="a585b-180">New-CaseHoldRule</span><span class="sxs-lookup"><span data-stu-id="a585b-180">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [<span data-ttu-id="a585b-181">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="a585b-181">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [<span data-ttu-id="a585b-182">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a585b-182">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [<span data-ttu-id="a585b-183">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a585b-183">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- <span data-ttu-id="a585b-184">Weitere Informationen zum Microsoft 365 Compliance Center finden Sie unter [Overview of the Microsoft 365 Compliance Center](microsoft-365-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a585b-184">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
