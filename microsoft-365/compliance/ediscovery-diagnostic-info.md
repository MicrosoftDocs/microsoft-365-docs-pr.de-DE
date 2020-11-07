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
description: Hier erfahren Sie, wie Sie eDiscovery-Diagnoseinformationen für einen Microsoft-Support Fall sammeln.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944392"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="f7d07-103">Sammeln von eDiscovery-Diagnoseinformationen</span><span class="sxs-lookup"><span data-stu-id="f7d07-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="f7d07-104">Gelegentlich benötigen Microsoft-Supporttechniker spezifische Informationen zu Ihrem Problem, wenn Sie einen Support Fall öffnen, der sich auf die zentrale eDiscovery oder die erweiterte eDiscovery bezieht.</span><span class="sxs-lookup"><span data-stu-id="f7d07-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="f7d07-105">Dieser Artikel enthält Anleitungen zum Sammeln von Diagnoseinformationen, um Support Ingenieure bei der Untersuchung und Lösung von Problemen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f7d07-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="f7d07-106">Normalerweise müssen Sie diese Informationen erst sammeln, wenn Sie von einem Microsoft-Support Techniker dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="f7d07-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7d07-107">Die Ausgabe der in diesem Artikel beschriebenen Cmdlets und Diagnoseinformationen kann vertrauliche Informationen zu Rechtsstreitigkeiten oder internen Untersuchungen in Ihrer Organisation enthalten.</span><span class="sxs-lookup"><span data-stu-id="f7d07-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="f7d07-108">Vor dem Senden der RAW-Diagnoseinformationen an den Microsoft-Support sollten Sie die Informationen überprüfen und alle vertraulichen Informationen (wie Namen oder andere Informationen zu redact oder Ermittlungsverfahren) durch ersetzen `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="f7d07-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="f7d07-109">Durch die Verwendung dieser Methode wird dem Microsoft-Support Techniker auch angezeigt, dass die Informationen verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="f7d07-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="f7d07-110">Sammeln von Diagnoseinformationen für die zentrale eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f7d07-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="f7d07-111">Das Sammeln von Diagnoseinformationen für die zentrale eDiscovery ist Cmdlet-basiert, daher müssen Sie Sicherheits & Compliance Center PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7d07-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="f7d07-112">In den folgenden PowerShell-Beispielen werden Cmdlets ausgeführt, und anschließend wird die Ausgabe in einer angegebenen Textdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f7d07-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="f7d07-113">In den meisten Supportfällen sollten Sie nur einen der folgenden Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7d07-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="f7d07-114">Wenn Sie die folgenden Cmdlets ausführen möchten, stellen [Sie eine Verbindung mit </span> Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="f7d07-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="f7d07-115">Nachdem Sie eine Verbindung hergestellt haben, führen Sie einen oder mehrere der folgenden Befehle aus, und stellen Sie sicher, dass Sie Platzhalter durch die tatsächlichen Objektnamen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f7d07-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="f7d07-116">Nachdem Sie die generierte Textdatei überprüft und vertrauliche Informationen verarbeitet haben, senden Sie Sie an den Microsoft-Support Techniker, der an Ihrem Fall arbeitet.</span><span class="sxs-lookup"><span data-stu-id="f7d07-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="f7d07-117">Sie können auch die Befehle in diesem Abschnitt ausführen, um Diagnoseinformationen zu den suchen und Exporten zu sammeln, die auf der Seite " **Inhaltssuche** " im Microsoft 365 Compliance Center aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="f7d07-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="f7d07-118">Sammeln von Informationen zu Suchvorgängen</span><span class="sxs-lookup"><span data-stu-id="f7d07-118">Collect information about searches</span></span>

<span data-ttu-id="f7d07-119">Mit dem folgenden Befehl werden Informationen gesammelt, die beim Untersuchen von Problemen mit einer Inhaltssuche oder einer Suche im Zusammenhang mit einem zentralen eDiscovery-Fall hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="f7d07-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="f7d07-120">Sammeln von Informationen zu Suchaktionen</span><span class="sxs-lookup"><span data-stu-id="f7d07-120">Collect information about search actions</span></span>

<span data-ttu-id="f7d07-121">Mit dem folgenden Befehl werden Informationen zum Untersuchen von Problemen bei der Vorschau, beim Exportieren oder Löschen der Ergebnisse einer Inhaltssuche oder einer Suche im Zusammenhang mit einem zentralen eDiscovery-Fall gesammelt.</span><span class="sxs-lookup"><span data-stu-id="f7d07-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="f7d07-122">Sie können den Namen der Suchaktion identifizieren, indem Sie auf die Registerkarte **Exports** klicken. Zum Identifizieren der Namen von Vorschau-und Löschaktionen können Sie das Cmdlet **Get-ComplianceSearchAction** ausführen, um eine Liste aller Aktionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7d07-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="f7d07-123">Das Format für den Namen der Suchaktion wird durch Anfügen von `_Preview` `_Export` oder `_Purge` an den Namen der entsprechenden Suche erstellt.</span><span class="sxs-lookup"><span data-stu-id="f7d07-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="f7d07-124">Sammeln von Informationen über eDiscovery-Haltestatus</span><span class="sxs-lookup"><span data-stu-id="f7d07-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="f7d07-125">Wenn ein eDiscovery-Haltestatus, der einem zentralen eDiscovery-Fall zugeordnet ist, nicht wie erwartet funktioniert, führen Sie den folgenden Befehl aus, um Informationen zur Case Hold-Richtlinie und der zugehörigen Fall halten-Regel für den eDiscovery-Haltestatus zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="f7d07-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="f7d07-126">Der *Name der Case Hold-Richtlinie* im folgenden Befehl entspricht dem Namen des eDiscovery-Haltestatus.</span><span class="sxs-lookup"><span data-stu-id="f7d07-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="f7d07-127">Sie können diesen Namen auf den Registerkarten "halte **Status** " im zentralen eDiscovery-Fall identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f7d07-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="f7d07-128">Sammeln aller Fall Informationen</span><span class="sxs-lookup"><span data-stu-id="f7d07-128">Collect all case information</span></span>

<span data-ttu-id="f7d07-129">Manchmal ist nicht ersichtlich, welche Informationen der Microsoft-Support zur Untersuchung Ihres Problems benötigt.</span><span class="sxs-lookup"><span data-stu-id="f7d07-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="f7d07-130">In dieser Situation können Sie alle Diagnoseinformationen für einen zentralen eDiscovery-Fall erfassen.</span><span class="sxs-lookup"><span data-stu-id="f7d07-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="f7d07-131">Der *Name des zentralen eDiscovery-Falls* im folgenden Befehl entspricht dem Namen eines Falls, der auf der **zentralen eDiscovery** -Seite im Microsoft 365 Compliance Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f7d07-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="f7d07-132">Sammeln von Diagnoseinformationen für Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f7d07-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="f7d07-133">Auf der Registerkarte **Einstellungen** in einem erweiterten eDiscovery-Fall können Sie schnell die Diagnoseinformationen für den Fall kopieren.</span><span class="sxs-lookup"><span data-stu-id="f7d07-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="f7d07-134">Die Diagnoseinformationen werden in der Zwischenablage gespeichert, sodass Sie Sie in eine Textdatei einfügen und an den Microsoft-Support senden können.</span><span class="sxs-lookup"><span data-stu-id="f7d07-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="f7d07-135">Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **alle > eDiscovery > erweitert anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f7d07-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="f7d07-136">Wählen Sie einen Fall aus, und klicken Sie dann auf die Registerkarte **Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="f7d07-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="f7d07-137">Klicken Sie unter **Fall Informationen** auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="f7d07-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="f7d07-138">Klicken Sie auf der Seite Flyout auf **Diagnoseinformationen kopieren** , um die Informationen in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f7d07-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="f7d07-139">Öffnen Sie eine Textdatei (im Editor), und fügen Sie die Informationen in die Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="f7d07-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="f7d07-140">Speichern Sie die Textdatei, und nennen Sie Sie so etwas wie `AeD Diagnostic Info YYYY.MM.DD` (beispielsweise `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="f7d07-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="f7d07-141">Nachdem Sie die Datei überprüft und vertrauliche Informationen verarbeitet haben, senden Sie Sie an den Microsoft-Support Techniker, der an Ihrem Fall arbeitet.</span><span class="sxs-lookup"><span data-stu-id="f7d07-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
