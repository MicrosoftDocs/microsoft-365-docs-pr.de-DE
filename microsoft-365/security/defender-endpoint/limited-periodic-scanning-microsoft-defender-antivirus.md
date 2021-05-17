---
title: Aktivieren der eingeschränkten Microsoft Defender Antivirus Überprüfungsfunktion
description: Mit eingeschränkter regelmäßiger Überprüfung können Sie Microsoft Defender Antivirus zusätzlich zu Ihren anderen installierten AV-Anbietern verwenden.
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274593"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="9d7c4-104">Verwendung von eingeschränkten periodischen Scans in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9d7c4-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9d7c4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9d7c4-105">**Applies to:**</span></span>

- [<span data-ttu-id="9d7c4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d7c4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9d7c4-107">Bei der begrenzten regelmäßigen Überprüfung handelt es sich um eine spezielle Art von Bedrohungserkennung und -behebung, die aktiviert werden kann, wenn Sie ein anderes Antivirenprodukt auf einem Windows 10 haben.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="9d7c4-108">Sie kann nur in bestimmten Situationen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="9d7c4-109">Weitere Informationen zur eingeschränkten regelmäßigen Überprüfung und zur Microsoft Defender Antivirus verwendung mit anderen Antivirenprodukten finden Sie [unter Microsoft Defender Antivirus Kompatibilität](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="9d7c4-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="9d7c4-110">**Microsoft empfiehlt die Verwendung dieses Features in Unternehmensumgebungen nicht. Dies ist ein Feature, das in erster Linie für Verbraucher vorgesehen ist.**</span><span class="sxs-lookup"><span data-stu-id="9d7c4-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="9d7c4-111">Dieses Feature verwendet nur eine begrenzte Teilmenge der Microsoft Defender Antivirus, um Schadsoftware zu erkennen, und kann die meisten Schadsoftware und potenziell unerwünschte Software nicht erkennen.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="9d7c4-112">Darüber hinaus sind die Verwaltungs- und Berichtsfunktionen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="9d7c4-113">Microsoft empfiehlt Unternehmen, ihre primäre Antivirenlösung zu wählen und sie exklusiv zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="9d7c4-114">Aktivieren begrenzter regelmäßiger Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="9d7c4-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="9d7c4-115">Standardmäßig aktiviert Microsoft Defender Antivirus sich selbst auf einem Windows 10-Gerät, wenn kein anderes Antivirenprodukt installiert ist oder das andere Produkt veraltet, abgelaufen oder nicht ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="9d7c4-116">Wenn Microsoft Defender Antivirus aktiviert ist, werden die üblichen Optionen angezeigt, um sie auf diesem Gerät zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="9d7c4-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Windows-Sicherheit-App mit Microsoft Defender AV-Optionen, einschließlich Scanoptionen, Einstellungen und Updateoptionen](images/vtp-wdav.png)

<span data-ttu-id="9d7c4-118">Wenn ein anderes Antivirenprodukt installiert ist und ordnungsgemäß funktioniert, Microsoft Defender Antivirus selbst deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="9d7c4-119">Die Windows-Sicherheit-App ändert den Abschnitt **Virenschutz &,** um den Status des AV-Produkts anzuzeigen, und stellt einen Link zu den Konfigurationsoptionen des Produkts zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="9d7c4-120">Unterhalb von AV-Produkten von Drittanbietern wird ein neuer Link als Microsoft Defender Antivirus **angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="9d7c4-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="9d7c4-121">Wenn Sie auf diesen Link klicken, wird der Umschalter, der eine eingeschränkte regelmäßige Überprüfung ermöglicht, erweitert.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="9d7c4-122">Beachten Sie, dass die eingeschränkte periodische Option eine Umschalte ist, um die regelmäßige Überprüfung zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="9d7c4-123">Wenn Sie den Schalter auf **Ein** verschieben, werden die standardmäßigen Microsoft Defender AV-Optionen unterhalb des Drittanbieter-AV-Produkts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="9d7c4-124">Die eingeschränkte regelmäßige Überprüfungsoption wird am unteren Rand der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d7c4-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9d7c4-125">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9d7c4-125">Related articles</span></span>

- [<span data-ttu-id="9d7c4-126">Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="9d7c4-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9d7c4-127">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="9d7c4-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)