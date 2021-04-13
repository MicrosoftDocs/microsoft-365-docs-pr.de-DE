---
title: Konfigurieren des Timeoutzeitraums für Microsoft Defender Antivirus-Cloudblocks
description: Sie können konfigurieren, wie lange Microsoft Defender Antivirus die Ausführung einer Datei blockiert, während Sie auf eine Cloudermittlung warten.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Cloud, Timeout, Block, Zeitraum, Sekunden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690452"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="a1729-104">Konfigurieren des Timeoutzeitraums für Cloudblocks</span><span class="sxs-lookup"><span data-stu-id="a1729-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1729-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a1729-105">**Applies to:**</span></span>

- [<span data-ttu-id="a1729-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a1729-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a1729-107">Wenn Microsoft Defender Antivirus eine verdächtige Datei findet, kann sie die Ausführung der Datei verhindern, während sie den [Microsoft Defender Antivirus-Clouddienst abfragt.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a1729-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a1729-108">Der Standardzeitraum, für den die Datei blockiert [wird,](configure-block-at-first-sight-microsoft-defender-antivirus.md) beträgt 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="a1729-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="a1729-109">Sie können einen zusätzlichen Zeitraum angeben, bis die Datei ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="a1729-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="a1729-110">Dadurch kann sichergestellt werden, dass genügend Zeit zur Verfügung steht, um eine ordnungsgemäße Bestimmung vom Microsoft Defender Antivirus-Clouddienst zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a1729-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="a1729-111">Voraussetzungen für die Verwendung des erweiterten Timeouts für Cloudblocks</span><span class="sxs-lookup"><span data-stu-id="a1729-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="a1729-112">[Beim ersten Blick blockieren](configure-block-at-first-sight-microsoft-defender-antivirus.md) und die erforderlichen Komponenten müssen aktiviert sein, bevor Sie einen längeren Timeoutzeitraum angeben können.</span><span class="sxs-lookup"><span data-stu-id="a1729-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="a1729-113">Angeben des erweiterten Timeoutzeitraums</span><span class="sxs-lookup"><span data-stu-id="a1729-113">Specify the extended timeout period</span></span>

<span data-ttu-id="a1729-114">Sie können gruppenrichtlinien verwenden, um ein erweitertes Timeout für Cloudüberprüfungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a1729-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="a1729-115">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a1729-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a1729-116">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="a1729-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="a1729-117">Erweitern der Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="a1729-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="a1729-118">Doppelklicken Sie auf **Erweiterte Cloudüberprüfung konfigurieren,** und stellen Sie sicher, dass die Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a1729-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="a1729-119">Geben Sie den zusätzlichen Zeitraum an, um zu verhindern, dass die Datei ausgeführt wird, während sie auf eine Cloudermittlung wartet.</span><span class="sxs-lookup"><span data-stu-id="a1729-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="a1729-120">Sie können die zusätzliche Zeit in Sekunden zwischen 1 Sekunde und 50 Sekunden angeben.</span><span class="sxs-lookup"><span data-stu-id="a1729-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="a1729-121">Diese Zeit wird den standardmäßigen 10 Sekunden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a1729-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="a1729-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1729-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1729-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a1729-123">Related topics</span></span>

- [<span data-ttu-id="a1729-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a1729-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a1729-125">Verwenden von Antivirentechnologien der nächsten Generation durch Cloud-basierten Schutz</span><span class="sxs-lookup"><span data-stu-id="a1729-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a1729-126">Konfigurieren von Block bei erster Sicht</span><span class="sxs-lookup"><span data-stu-id="a1729-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a1729-127">Aktivieren des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a1729-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)