---
title: Veraltern von TLS 1,0 und 1,1 in Office 365 gcc High und DoD
description: Erläutert, wie Microsoft das Datum vorwärts verschiebt, um die Unterstützung für TLS 1,1 und 1,0 in gcc-High-und DoD-Umgebungen in Office 365 zu beenden und die Verwendung von TLS 1,2 vorzubereiten.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024825"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="8f3e9-103">Veraltern von TLS 1,0 und 1,1 in Office 365 gcc High und DoD</span><span class="sxs-lookup"><span data-stu-id="8f3e9-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f3e9-104">Die Welt befindet sich mitten in einer Pandemie, und wir bei Microsoft sind uns der Auswirkungen auf unsere Kunden und Partner bewusst.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="8f3e9-105">Um unsere gewerblichen Kunden zu entlasten, haben wir jede Abschreibungserzwingung von TLS 1.0 und 1.1 vorübergehend ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="8f3e9-106">Nach der Stabilisierung der aktuellen Krise wird ein Update auf einem überarbeiteten Zeitplan gesendet.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="8f3e9-107">(Dieser Artikel wird überarbeitet, um die Änderung widerzuspiegeln.)</span><span class="sxs-lookup"><span data-stu-id="8f3e9-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="8f3e9-108">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8f3e9-108">Summary</span></span>

<span data-ttu-id="8f3e9-109">Um die neuesten Compliance-Standards für das Federal Risk and Authorization Management Program (FedRAMP) einzuhalten, werden Transport Layer Security (TLS)-Versionen 1,1 und 1,0 in Microsoft Office 365 für gcc-High-und DoD-Umgebungen veraltet.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="8f3e9-110">Diese Änderung wurde zuvor über den Microsoft-Support [zur Vorbereitung der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)angekündigt.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="8f3e9-111">Wir verstehen, dass die Sicherheit Ihrer Daten wichtig ist, und wir setzen uns für Transparenz bei Änderungen ein, die sich auf Ihre Nutzung des Diensts auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="8f3e9-112">Obwohl die [Microsoft TLS 1,0-Implementierung](https://support.microsoft.com/help/3117336) keine bekannten Sicherheitsrisiken aufweist, werden wir weiterhin den FedRAMP-Konformitätsstandards verpflichtet.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="8f3e9-113">Daher werden TLS 1,1 und 1,0 in Office 365 in gcc High-und DoD-Umgebungen ab dem 15. Januar 2020 veraltet sein.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="8f3e9-114">Informationen zum Entfernen von TLS 1,1-und 1,0-Abhängigkeiten finden Sie in folgendem Whitepaper:</span><span class="sxs-lookup"><span data-stu-id="8f3e9-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="8f3e9-115">Lösen des TLS 1,0-Problems</span><span class="sxs-lookup"><span data-stu-id="8f3e9-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="8f3e9-116">Bei der Vorbereitung auf diese Änderung für TLS 1,1 und 1,0 sollten Sie stattdessen die TLS-Version 1,2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="8f3e9-117">Weitere Informationen finden Sie unter [vorbereiten auf die obligatorische Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="8f3e9-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="8f3e9-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f3e9-118">More information</span></span>

<span data-ttu-id="8f3e9-119">Ab dem 15. Januar 2020 werden Office 365 in der gcc-hoch-und der DoD-Umgebung TLS 1,1 und 1,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="8f3e9-120">Bis zum 15. Januar 2020 sollten alle Kombinationen von Clientservern und Browser Servern TLS-Version 1,2 (oder eine höhere Version) verwenden, um sicherzustellen, dass alle Verbindungen ohne Probleme für Office 365 Dienste ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="8f3e9-121">Dies erfordert möglicherweise Aktualisierungen für bestimmte Kombinationen von Clientservern und Browser Servern.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="8f3e9-122">Wenn Sie nicht auf TLS-Version 1,2 (oder eine höhere Version) bis zum 15. Januar 2020 aktualisieren, treten Probleme auf, wenn Sie versuchen, eine Verbindung mit Office 365 herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="8f3e9-123">Darüber hinaus müssen Sie als Teil der Lösung auf TLS 1,2 (oder eine höhere Version) aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="8f3e9-124">Wir wissen, dass die folgenden Clients TLS 1,2 nicht verwenden können:</span><span class="sxs-lookup"><span data-stu-id="8f3e9-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="8f3e9-125">Android 4.3 und niedrigere Versionen</span><span class="sxs-lookup"><span data-stu-id="8f3e9-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="8f3e9-126">Firefox Version 5.0 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="8f3e9-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="8f3e9-127">Internet Explorer 8 – 10 auf Windows 7 und früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="8f3e9-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="8f3e9-128">Internet Explorer 10 auf Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="8f3e9-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="8f3e9-129">Safari 6.0.4/OS X 10.8.4 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="8f3e9-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="8f3e9-130">Es wird empfohlen, dass Sie Ihre Clients aktualisieren, um sicherzustellen, dass Sie einen unterbrechungsfreien Zugriff auf Office 365 gcc High und DoD gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="8f3e9-131">Obwohl die aktuelle Analyse der Verbindungen mit Microsoft Online Services zeigt, dass die meisten Dienste und Endpunkte nur sehr wenig TLS 1,1 und 1,0 verwenden, wird diese Änderung mitgeteilt, sodass Sie alle betroffenen Clients oder Server bei Bedarf aktualisieren können, bevor die Unterstützung für TLS 1,1 und 1,0 endet.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="8f3e9-132">Wenn Sie eine lokale Infrastruktur für Hybrid Szenarien oder Active Directory Verbunddienste (AD FS) verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen unterstützenkann, die TLS 1,2 (oder eine höhere Version) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f3e9-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="8f3e9-133">Zusätzlich zu den Ausfällen, die bei der Verwendung der aufgeführten Clients auftreten, die TLS 1,2 nicht verwenden können, wird das Entfernen von TLS 1,1 und 1,0 verhindert, dass Sie das folgende Microsoft-Produkt verwenden können:</span><span class="sxs-lookup"><span data-stu-id="8f3e9-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="8f3e9-134">Lync-Telefon</span><span class="sxs-lookup"><span data-stu-id="8f3e9-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="8f3e9-135">Informationsquellen</span><span class="sxs-lookup"><span data-stu-id="8f3e9-135">References</span></span>

<span data-ttu-id="8f3e9-136">Im folgenden Support Artikel werden Anleitungen und Verweise beschrieben, mit denen Sie sicherstellen können, dass Ihre Clients TLS 1,2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="8f3e9-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="8f3e9-137">Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3e9-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
