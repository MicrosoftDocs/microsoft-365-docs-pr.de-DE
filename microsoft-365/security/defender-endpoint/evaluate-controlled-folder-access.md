---
title: Bewerten des kontrollierten Ordnerzugriffs
description: Erfahren Sie, wie der kontrollierte Ordnerzugriff dazu beitragen kann, Dateien vor der Änderung durch schädliche Apps zu schützen.
keywords: Exploit-Schutz, Windows 10, Windows Defender, Ransomware, Schützen, Bewerten, Testen, Demo, Testen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218748"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="3cd78-104">Bewerten des kontrollierten Ordnerzugriffs</span><span class="sxs-lookup"><span data-stu-id="3cd78-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3cd78-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3cd78-105">**Applies to:**</span></span>
- [<span data-ttu-id="3cd78-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3cd78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3cd78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cd78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3cd78-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="3cd78-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3cd78-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="3cd78-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="3cd78-110">[Der kontrollierte Ordnerzugriff](controlled-folders.md) ist ein Feature, das Ihre Dokumente und Dateien vor Änderungen durch verdächtige oder schädliche Apps schützt.</span><span class="sxs-lookup"><span data-stu-id="3cd78-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="3cd78-111">Der kontrollierte Ordnerzugriff wird auf Windows Server 2019- und Windows 10-Clients unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3cd78-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="3cd78-112">Es ist besonders hilfreich beim Schutz vor [Ransomware,](https://www.microsoft.com/wdsi/threats/ransomware) die versucht, Ihre Dateien zu verschlüsseln und als Host zu halten.</span><span class="sxs-lookup"><span data-stu-id="3cd78-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="3cd78-113">Dieser Artikel hilft Ihnen bei der Auswertung des kontrollierten Ordnerzugriffs.</span><span class="sxs-lookup"><span data-stu-id="3cd78-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="3cd78-114">Es wird erläutert, wie Sie den Überwachungsmodus aktivieren, damit Sie das Feature direkt in Ihrer Organisation testen können.</span><span class="sxs-lookup"><span data-stu-id="3cd78-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="3cd78-115">Sie können auch die Microsoft Defender for Endpoint-Demoszenariowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass das Feature funktioniert und wie es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="3cd78-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="3cd78-116">Verwenden des Überwachungsmodus zum Messen der Auswirkung</span><span class="sxs-lookup"><span data-stu-id="3cd78-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="3cd78-117">Aktivieren Sie den kontrollierten Ordnerzugriff im  Überwachungsmodus, um einen Datensatz zu sehen, was passiert wäre, wenn er vollständig aktiviert wäre.</span><span class="sxs-lookup"><span data-stu-id="3cd78-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="3cd78-118">Testen Sie, wie das Feature in Ihrer Organisation funktioniert, um sicherzustellen, dass es sich nicht auf Ihre Unternehmensanwendungen auswirken wird.</span><span class="sxs-lookup"><span data-stu-id="3cd78-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="3cd78-119">Sie können auch eine Vorstellung davon erhalten, wie viele verdächtige Dateiänderungsversuche in der Regel über einen bestimmten Zeitraum erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3cd78-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="3cd78-120">Verwenden Sie das folgende PowerShell-Cmdlet, um den Überwachungsmodus zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3cd78-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="3cd78-121">Wenn Sie vollständig überwachen möchten, wie der kontrollierte Ordnerzugriff in Ihrer Organisation funktioniert, müssen Sie ein Verwaltungstool verwenden, um diese Einstellung auf Geräten in Ihren Netzwerken bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="3cd78-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="3cd78-122">Sie können die Einstellung auch mithilfe von Gruppenrichtlinien, Intune, mobiler Geräteverwaltung (Mobile Device Management, MDM) oder Microsoft Endpoint Manager konfigurieren und bereitstellen, wie im Thema "Zugriff auf hauptgesteuerte Ordner" [beschrieben.](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="3cd78-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="3cd78-123">Überprüfen von Ereignissen für den kontrollierten Ordnerzugriff in der Windows-Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="3cd78-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="3cd78-124">Die folgenden Ereignisse für den kontrollierten Ordnerzugriff werden in der Windows-Ereignisanzeige unter Dem Ordner Microsoft/Windows/Windows Defender/Operational angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3cd78-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="3cd78-125">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3cd78-125">Event ID</span></span> | <span data-ttu-id="3cd78-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cd78-126">Description</span></span>
-|-
 <span data-ttu-id="3cd78-127">5007</span><span class="sxs-lookup"><span data-stu-id="3cd78-127">5007</span></span> | <span data-ttu-id="3cd78-128">Ereignis, wenn Einstellungen geändert werden</span><span class="sxs-lookup"><span data-stu-id="3cd78-128">Event when settings are changed</span></span>
 <span data-ttu-id="3cd78-129">1124</span><span class="sxs-lookup"><span data-stu-id="3cd78-129">1124</span></span> | <span data-ttu-id="3cd78-130">Überwachtes kontrolliertes Ordnerzugriffsereignis</span><span class="sxs-lookup"><span data-stu-id="3cd78-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="3cd78-131">1123</span><span class="sxs-lookup"><span data-stu-id="3cd78-131">1123</span></span> | <span data-ttu-id="3cd78-132">Blockiertes Ereignis für den kontrollierten Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="3cd78-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="3cd78-133">Sie können ein [Windows Event Forwarding-Abonnement so konfigurieren,](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) dass die Protokolle zentral erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="3cd78-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="3cd78-134">Anpassen geschützter Ordner und Apps</span><span class="sxs-lookup"><span data-stu-id="3cd78-134">Customize protected folders and apps</span></span>

<span data-ttu-id="3cd78-135">Während der Auswertung können Sie der Liste der geschützten Ordner hinzufügen oder bestimmten Apps das Ändern von Dateien erlauben.</span><span class="sxs-lookup"><span data-stu-id="3cd78-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="3cd78-136">Weitere [Informationen finden](controlled-folders.md) Sie unter Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff zum Konfigurieren des Features mit Verwaltungstools, einschließlich Gruppenrichtlinien, PowerShell und MDM-Konfigurationsdienstanbietern (CSPs).</span><span class="sxs-lookup"><span data-stu-id="3cd78-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cd78-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cd78-137">See also</span></span>

* [<span data-ttu-id="3cd78-138">Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="3cd78-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="3cd78-139">Bewerten von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3cd78-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="3cd78-140">Verwenden des Überwachungsmodus</span><span class="sxs-lookup"><span data-stu-id="3cd78-140">Use audit mode</span></span>](audit-windows-defender.md)
