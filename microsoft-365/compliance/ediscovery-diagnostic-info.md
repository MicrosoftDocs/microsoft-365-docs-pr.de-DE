---
title: Sammeln von eDiscovery-Diagnoseinformationen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie eDiscovery-Diagnoseinformationen für einen Microsoft Support-Fall erfassen.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926555"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="331d5-103">Sammeln von eDiscovery-Diagnoseinformationen</span><span class="sxs-lookup"><span data-stu-id="331d5-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="331d5-104">Gelegentlich benötigen Microsoft Support-Techniker spezifische Informationen zu Ihrem Problem, wenn Sie einen Supportfall im Zusammenhang mit Core eDiscovery oder Advanced eDiscovery öffnen.</span><span class="sxs-lookup"><span data-stu-id="331d5-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="331d5-105">Dieser Artikel enthält Anleitungen zum Sammeln von Diagnoseinformationen, mit deren Hilfe Techniker Probleme untersuchen und beheben können.</span><span class="sxs-lookup"><span data-stu-id="331d5-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="331d5-106">In der Regel müssen Sie diese Informationen erst erfassen, wenn Sie von einem Microsoft Support-Techniker dazu aufgefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="331d5-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="331d5-107">Die Ausgabe der Cmdlets und Diagnoseinformationen, die in diesem Artikel beschrieben werden, kann vertrauliche Informationen zu Rechtsstreitigkeiten oder internen Untersuchungen in Ihrer Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="331d5-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="331d5-108">Bevor Sie die unformatierte Diagnoseinformationen an den Microsoft Support senden, sollten Sie die Informationen überprüfen und vertrauliche Informationen (z. B. Namen oder andere Informationen zu Parteien, die an Einem Rechtsstreit oder Untersuchung beteiligten) durch redactieren, indem Sie sie durch `XXXXXXX` ersetzen.</span><span class="sxs-lookup"><span data-stu-id="331d5-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="331d5-109">Wenn Sie diese Methode verwenden, wird dem Microsoft-Supporttechniker auch angezeigt, dass informationen redacted wurden.</span><span class="sxs-lookup"><span data-stu-id="331d5-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="331d5-110">Sammeln von Diagnoseinformationen für Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="331d5-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="331d5-111">Das Sammeln von Diagnoseinformationen für Core eDiscovery ist cmdlet-basiert, sodass Sie Security & Compliance Center PowerShell verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="331d5-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="331d5-112">In den folgenden PowerShell-Beispielen werden Cmdlets ausgeführt und die Ausgabe dann in einer angegebenen Textdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="331d5-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="331d5-113">In den meisten Supportfällen sollten Sie nur einen dieser Befehle ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="331d5-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="331d5-114">Um die folgenden Cmdlets ausführen zu können, stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell ein. </span> ](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="331d5-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="331d5-115">Führen Sie nach der Verbindung einen oder mehrere der folgenden Befehle aus, und ersetzen Sie Platzhalter durch die tatsächlichen Objektnamen.</span><span class="sxs-lookup"><span data-stu-id="331d5-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="331d5-116">Nachdem Sie die generierte Textdatei überprüft und vertrauliche Informationen umaktiviert haben, senden Sie sie an den Microsoft Support-Techniker, der an Ihrem Fall arbeitet.</span><span class="sxs-lookup"><span data-stu-id="331d5-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="331d5-117">Sie können die Befehle in diesem Abschnitt auch ausführen, um Diagnoseinformationen für die auf der Seite Inhaltssuche im Microsoft 365 Compliance Center aufgeführten Such- und Exportinformationen zu sammeln. </span><span class="sxs-lookup"><span data-stu-id="331d5-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="331d5-118">Sammeln von Informationen zu Suchen</span><span class="sxs-lookup"><span data-stu-id="331d5-118">Collect information about searches</span></span>

<span data-ttu-id="331d5-119">Der folgende Befehl sammelt Informationen, die bei der Untersuchung von Problemen mit einer Inhaltssuche oder einer Suche im Zusammenhang mit einem Core eDiscovery-Fall hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="331d5-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="331d5-120">Sammeln von Informationen zu Suchaktionen</span><span class="sxs-lookup"><span data-stu-id="331d5-120">Collect information about search actions</span></span>

<span data-ttu-id="331d5-121">Mit dem folgenden Befehl werden Informationen gesammelt, um Probleme beim Anzeigen, Exportieren oder Löschen der Ergebnisse einer Inhaltssuche oder einer Suche zu untersuchen, die einem Core eDiscovery-Fall zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="331d5-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="331d5-122">Sie können den Namen der Suchaktion identifizieren, indem Sie auf einen Export klicken, der auf der Registerkarte **Exporte aufgeführt** ist. Zum Identifizieren der Namen von Vorschau- und Bereinigungsaktionen können Sie das **Cmdlet Get-ComplianceSearchAction** ausführen, um eine Liste aller Aktionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="331d5-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="331d5-123">Das Format für den Namen der Suchaktion wird durch Anfügen , oder an den Namen der `_Preview` `_Export` entsprechenden Suche `_Purge` erstellt.</span><span class="sxs-lookup"><span data-stu-id="331d5-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="331d5-124">Sammeln von Informationen zu eDiscovery-Halteinformationen</span><span class="sxs-lookup"><span data-stu-id="331d5-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="331d5-125">Wenn ein eDiscovery-Haltebereich, der einem Core eDiscovery-Fall zugeordnet ist, nicht wie erwartet funktioniert, führen Sie den folgenden Befehl aus, um Informationen zur Case Hold Policy und der zugehörigen Fall hold Rule für das eDiscovery-Haltebereich zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="331d5-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="331d5-126">Der *Name der Case-Hold-Richtlinie* im folgenden Befehl entspricht dem Namen des eDiscovery-Halteraums.</span><span class="sxs-lookup"><span data-stu-id="331d5-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="331d5-127">Sie können diesen Namen auf den **Registerkarten** Haltebereich im Fall Core eDiscovery identifizieren.</span><span class="sxs-lookup"><span data-stu-id="331d5-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="331d5-128">Sammeln aller Fallinformationen</span><span class="sxs-lookup"><span data-stu-id="331d5-128">Collect all case information</span></span>

<span data-ttu-id="331d5-129">Manchmal ist nicht ersichtlich, welche Informationen vom Microsoft Support benötigt werden, um Ihr Problem zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="331d5-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="331d5-130">In diesem Fall können Sie alle Diagnoseinformationen für einen Core eDiscovery-Fall erfassen.</span><span class="sxs-lookup"><span data-stu-id="331d5-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="331d5-131">Der *Core eDiscovery-Fallname* im folgenden Befehl entspricht dem Namen eines Falls, der auf der Seite **Core eDiscovery** im Microsoft 365 Compliance Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="331d5-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="331d5-132">Sammeln von Diagnoseinformationen für Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="331d5-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="331d5-133">Auf **der** Registerkarte Einstellungen in einem Advanced eDiscovery-Fall können Sie die Diagnoseinformationen für den Fall schnell kopieren.</span><span class="sxs-lookup"><span data-stu-id="331d5-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="331d5-134">Die Diagnoseinformationen werden in der Zwischenablage gespeichert, damit Sie sie in eine Textdatei einfügen und an den Microsoft Support senden können.</span><span class="sxs-lookup"><span data-stu-id="331d5-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="331d5-135">Wechseln Sie zu, und klicken Sie dann auf Alle [https://compliance.microsoft.com](https://compliance.microsoft.com/) **> eDiscovery > Advanced anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="331d5-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="331d5-136">Wählen Sie einen Fall aus, und klicken Sie dann auf die **Registerkarte** Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="331d5-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="331d5-137">Klicken **Sie unter Fallinformationen** auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="331d5-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="331d5-138">Klicken Sie auf der Flyoutseite auf **Diagnoseinformationen kopieren,** um die Informationen in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="331d5-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="331d5-139">Öffnen Sie eine Textdatei (in Editor), und fügen Sie die Informationen dann in die Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="331d5-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="331d5-140">Speichern Sie die Textdatei, und nennen Sie sie etwa `AeD Diagnostic Info YYYY.MM.DD` (z. B. `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="331d5-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="331d5-141">Nachdem Sie die Datei überprüft und vertrauliche Informationen umaktiviert haben, senden Sie sie an den Microsoft Support-Techniker, der an Ihrem Fall arbeitet.</span><span class="sxs-lookup"><span data-stu-id="331d5-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>