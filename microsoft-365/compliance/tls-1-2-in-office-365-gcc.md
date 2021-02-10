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
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166440"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="02615-103">Deaktivieren von TLS 1.0 und 1.1 in Office 365 GCC High and DoD</span><span class="sxs-lookup"><span data-stu-id="02615-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="02615-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="02615-104">Summary</span></span>

<span data-ttu-id="02615-105">Um die neuesten Compliancestandards für das Federal Risk and Authorization Management Program (FedRAMP) einzuhalten, deaktivieren wir die Transport Layer Security (TLS)-Versionen 1.1 und 1.0 in Microsoft 365 für GCC High- und DoD-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="02615-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="02615-106">Diese Änderung wurde zuvor über den Microsoft Support bei der Vorbereitung der obligatorischen Verwendung von [TLS 1.2 in Office 365 angekündigt.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="02615-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="02615-107">Die Sicherheit Ihrer Daten ist wichtig, und wir sind bestrebt, Transparenz über Änderungen zu gewährleisten, die sich auf Ihre Nutzung des Diensts auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="02615-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="02615-108">Obwohl die [Microsoft TLS 1.0-Implementierung](https://support.microsoft.com/help/3117336) keine bekannten Sicherheitsrisiken hat, bleiben wir bei den FedRAMP-Compliancestandards.</span><span class="sxs-lookup"><span data-stu-id="02615-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="02615-109">Daher haben wir TLS 1.1 und 1.0 in Office 365 in GCC High- und DoD-Umgebungen am 15. Januar 2020 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="02615-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="02615-110">Informationen zum Entfernen von TLS 1.1- und 1.0-Abhängigkeiten finden Sie im folgenden Whitepaper:</span><span class="sxs-lookup"><span data-stu-id="02615-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="02615-111">Beheben des TLS 1.0-Problems</span><span class="sxs-lookup"><span data-stu-id="02615-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="02615-112">Sie müssen stattdessen TLS Version 1.2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="02615-112">You must use TLS version 1.2 instead.</span></span> <span data-ttu-id="02615-113">Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="02615-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="02615-114">Für SharePoint und OneDrive müssen Sie .NET aktualisieren und konfigurieren, um TLS 1.2 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="02615-114">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="02615-115">Weitere Informationen finden Sie unter [Aktivieren von TLS 1.2 auf Clients.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="02615-115">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="02615-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02615-116">More information</span></span>

<span data-ttu-id="02615-117">Ab dem 15. Januar 2020 wird Office 365 in den GCC High- und DoD-Umgebungen TLS 1.1 und 1.0 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02615-117">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="02615-118">Bis zum 15. Januar 2020 sollten alle Kombinationen von Clientservern und Browserservern TLS Version 1.2 (oder höher) verwenden, um sicherzustellen, dass alle Verbindungen ohne Probleme mit Office 365-Diensten hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="02615-118">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="02615-119">Dies erfordert möglicherweise Updates für bestimmte Kombinationen von Clientservern und Browserservern.</span><span class="sxs-lookup"><span data-stu-id="02615-119">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="02615-120">Wenn Sie bis zum 15. Januar 2020 nicht auf TLS Version 1.2 (oder eine spätere Version) aktualisieren, werden Beim Versuch, eine Verbindung mit Office 365 herzustellen, Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="02615-120">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="02615-121">Darüber hinaus müssen Sie im Rahmen der Lösung auf TLS 1.2 (oder eine spätere Version) aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="02615-121">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="02615-122">Wir wissen, dass die folgenden Clients TLS 1.2 nicht verwenden können:</span><span class="sxs-lookup"><span data-stu-id="02615-122">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="02615-123">Android 4.3 und niedrigere Versionen</span><span class="sxs-lookup"><span data-stu-id="02615-123">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="02615-124">Firefox Version 5.0 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="02615-124">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="02615-125">Internet Explorer 8–10 unter Windows 7 und früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="02615-125">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="02615-126">Internet Explorer 10 auf Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="02615-126">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="02615-127">Safari 6.0.4/OS X 10.8.4 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="02615-127">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="02615-128">Es wird empfohlen, Ihre Clients zu aktualisieren, um sicherzustellen, dass Sie unterbrechungsfreien Zugriff auf Office 365 GCC High und DoD erhalten.</span><span class="sxs-lookup"><span data-stu-id="02615-128">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="02615-129">Obwohl die aktuelle Analyse der Verbindungen mit Microsoft Online Services zeigt, dass die meisten Dienste und Endpunkte nur eine sehr geringe TLS 1.1- und 1.0-Nutzung feststellen, wird diese Änderung zur Verfügung gestellt, damit Sie alle betroffenen Clients oder Server nach Bedarf aktualisieren können, bevor die Unterstützung für TLS 1.1 und 1.0 endet.</span><span class="sxs-lookup"><span data-stu-id="02615-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="02615-130">Wenn Sie eine lokale Infrastruktur für Hybridszenarien oder Active Directory Federation Services (AD FS) verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen unterstützen kann, die TLS 1.2 (oder höher) verwenden.</span><span class="sxs-lookup"><span data-stu-id="02615-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="02615-131">Zusätzlich zu den Ausfällen, die bei Verwendung der aufgeführten Clients, die TLS 1.2 nicht verwenden können, möglicherweise ausfälle werden, wird durch das Entfernen von TLS 1.1 und 1.0 verhindert, dass Sie das folgende Produkt von Microsoft verwenden können:</span><span class="sxs-lookup"><span data-stu-id="02615-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="02615-132">Lync Phone</span><span class="sxs-lookup"><span data-stu-id="02615-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="02615-133">Informationsquellen</span><span class="sxs-lookup"><span data-stu-id="02615-133">References</span></span>

<span data-ttu-id="02615-134">Im folgenden Supportartikel werden Anleitungen und Referenzen beschrieben, um sicherzustellen, dass Ihre Clients TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="02615-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="02615-135">Vorbereiten der obligatorischen Verwendung von TLS 1.2 in Office 365</span><span class="sxs-lookup"><span data-stu-id="02615-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
