---
title: Deaktivieren von TLS 1.0 und 1.1 in Office 365 GCC High and DoD
description: Erläutert, wie Microsoft die Unterstützung für TLS 1.1 und 1.0 in GCC High- und DoD-Umgebungen in Microsoft 365 deaktiviert.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233751"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="7f201-103">Deaktivieren von TLS 1.0 und 1.1 in Office 365 GCC High and DoD</span><span class="sxs-lookup"><span data-stu-id="7f201-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="7f201-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7f201-104">Summary</span></span>

<span data-ttu-id="7f201-105">Um die neuesten Compliancestandards für das Federal Risk and Authorization Management Program (FedRAMP) einzuhalten, deaktivieren wir die Transport Layer Security (TLS)-Versionen 1.1 und 1.0 in Microsoft 365 für GCC High- und DoD-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="7f201-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="7f201-106">Diese Änderung wurde zuvor über den Microsoft Support bei der Vorbereitung der obligatorischen Verwendung von [TLS 1.2 in Office 365 angekündigt.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="7f201-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="7f201-107">Die Sicherheit Ihrer Daten ist wichtig, und wir sind bestrebt, Transparenz über Änderungen zu gewährleisten, die sich auf Ihre Nutzung des Diensts auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="7f201-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="7f201-108">Obwohl die [Microsoft TLS 1.0-Implementierung](https://support.microsoft.com/help/3117336) keine bekannten Sicherheitsrisiken hat, bleiben wir bei den FedRAMP-Compliancestandards.</span><span class="sxs-lookup"><span data-stu-id="7f201-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="7f201-109">Daher haben wir TLS 1.1 und 1.0 in Office 365 in GCC High- und DoD-Umgebungen am 15. Januar 2020 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f201-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="7f201-110">Informationen zum Entfernen von TLS 1.1- und 1.0-Abhängigkeiten finden Sie im folgenden Whitepaper:</span><span class="sxs-lookup"><span data-stu-id="7f201-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="7f201-111">Beheben des TLS 1.0-Problems</span><span class="sxs-lookup"><span data-stu-id="7f201-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="7f201-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f201-112">More information</span></span>

<span data-ttu-id="7f201-113">Ab dem 15. Januar 2020 wird Office 365 in den GCC High- und DoD-Umgebungen TLS 1.1 und 1.0 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f201-113">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="7f201-114">Bis zum 15. Januar 2020 sollten alle Kombinationen von Clientservern und Browserservern TLS Version 1.2 (oder höher) verwenden, um sicherzustellen, dass alle Verbindungen ohne Probleme mit Office 365-Diensten hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="7f201-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="7f201-115">Dies erfordert möglicherweise Updates für bestimmte Kombinationen von Clientservern und Browserservern.</span><span class="sxs-lookup"><span data-stu-id="7f201-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="7f201-116">Wenn Sie bis zum 15. Januar 2020 nicht auf TLS Version 1.2 (oder eine spätere Version) aktualisieren, werden Beim Versuch, eine Verbindung mit Office 365 herzustellen, Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="7f201-116">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="7f201-117">Darüber hinaus müssen Sie im Rahmen der Lösung auf TLS 1.2 (oder eine spätere Version) aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7f201-117">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="7f201-118">Sie müssen Ihre Clientcomputer aktualisieren, um sicherzustellen, dass Sie unterbrechungsfreien Zugriff auf Office 365 GCC High und DoD erhalten.</span><span class="sxs-lookup"><span data-stu-id="7f201-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="7f201-119">Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f201-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="7f201-120">.NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7f201-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="7f201-121">Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter Aktivieren [von TLS 1.2 (Transport Layer Security)](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)auf Clients.</span><span class="sxs-lookup"><span data-stu-id="7f201-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="7f201-122">Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="7f201-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="7f201-123">Wir wissen, dass die folgenden Clientanwendungen TLS 1.2 nicht verwenden können:</span><span class="sxs-lookup"><span data-stu-id="7f201-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="7f201-124">Android 4.3 und niedrigere Versionen</span><span class="sxs-lookup"><span data-stu-id="7f201-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="7f201-125">Firefox Version 5.0 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="7f201-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="7f201-126">Internet Explorer 8–10 unter Windows 7 und früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="7f201-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="7f201-127">Internet Explorer 10 auf Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="7f201-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="7f201-128">Safari 6.0.4/OS X 10.8.4 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="7f201-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="7f201-129">Obwohl die aktuelle Analyse der Verbindungen mit Microsoft Online Services zeigt, dass die meisten Dienste und Endpunkte nur eine sehr geringe TLS 1.1- und 1.0-Nutzung feststellen, wird diese Änderung zur Verfügung gestellt, damit Sie alle betroffenen Clients oder Server nach Bedarf aktualisieren können, bevor die Unterstützung für TLS 1.1 und 1.0 endet.</span><span class="sxs-lookup"><span data-stu-id="7f201-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="7f201-130">Wenn Sie eine lokale Infrastruktur für Hybridszenarien oder Active Directory Federation Services (AD FS) verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen unterstützen kann, die TLS 1.2 (oder höher) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f201-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="7f201-131">Zusätzlich zu den Ausfällen, die bei Verwendung der aufgeführten Clients, die TLS 1.2 nicht verwenden können, möglicherweise ausfälle werden, wird durch das Entfernen von TLS 1.1 und 1.0 verhindert, dass Sie das folgende Produkt von Microsoft verwenden können:</span><span class="sxs-lookup"><span data-stu-id="7f201-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="7f201-132">Lync Phone</span><span class="sxs-lookup"><span data-stu-id="7f201-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="7f201-133">Informationsquellen</span><span class="sxs-lookup"><span data-stu-id="7f201-133">References</span></span>

<span data-ttu-id="7f201-134">Im folgenden Supportartikel werden Anleitungen und Referenzen beschrieben, um sicherzustellen, dass Ihre Clients TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="7f201-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="7f201-135">Vorbereiten der obligatorischen Verwendung von TLS 1.2 in Office 365</span><span class="sxs-lookup"><span data-stu-id="7f201-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
