---
title: Wiederherstellen isolierter Dateien in Microsoft Defender AV
description: Sie können Dateien und Ordner wiederherstellen, die von Microsoft Defender AV isoliert wurden.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275384"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="0c7ae-103">Wiederherstellen isolierter Dateien in Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="0c7ae-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0c7ae-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0c7ae-104">**Applies to:**</span></span>

- [<span data-ttu-id="0c7ae-105">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0c7ae-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0c7ae-106">Wenn Microsoft Defender Antivirus so konfiguriert ist, dass Bedrohungen auf Ihrem Gerät erkannt und behoben werden, Microsoft Defender Antivirus verdächtige Dateien isoliert.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="0c7ae-107">Wenn Sie sicher sind, dass eine isolierte Datei keine Bedrohung darstellt, können Sie sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="0c7ae-108">Öffnen **Windows-Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="0c7ae-109">Wählen **Sie Virenschutz & Bedrohungsschutz aus,** und klicken Sie dann auf **Schutzverlauf**.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="0c7ae-110">Filtern Sie in der Liste aller zuletzt verwendeten Elemente nach **Isolierte Elemente**.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="0c7ae-111">Wählen Sie ein Element aus, das Sie behalten möchten, und ergreifen Sie eine Aktion, z. B. die Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="0c7ae-112">Das Wiederherstellen einer Datei aus der Quarantäne kann auch über die Eingabeaufforderung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0c7ae-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="0c7ae-113">Weitere [Informationen finden Sie unter Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span><span class="sxs-lookup"><span data-stu-id="0c7ae-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="0c7ae-114">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0c7ae-114">Related articles</span></span>

- [<span data-ttu-id="0c7ae-115">Konfigurieren der Korrektur für Scans</span><span class="sxs-lookup"><span data-stu-id="0c7ae-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0c7ae-116">Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="0c7ae-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0c7ae-117">Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort</span><span class="sxs-lookup"><span data-stu-id="0c7ae-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0c7ae-118">Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="0c7ae-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0c7ae-119">Konfigurieren Microsoft Defender Antivirus Ausschlüssen auf Windows Server</span><span class="sxs-lookup"><span data-stu-id="0c7ae-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)