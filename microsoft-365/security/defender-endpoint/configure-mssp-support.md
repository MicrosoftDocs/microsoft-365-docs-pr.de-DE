---
title: Konfigurieren der Unterstützung von verwalteten Sicherheitsdienstanbietern
description: Führen Sie die erforderlichen Schritte aus, um die MSSP-Integration mit Microsoft Defender für Endpunkt zu konfigurieren.
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339358"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="4d044-104">Konfigurieren von verwalteten Sicherheitsdienstanbietern (Managed Security Service Provider, MSSP)</span><span class="sxs-lookup"><span data-stu-id="4d044-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4d044-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4d044-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d044-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4d044-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d044-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d044-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4d044-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="4d044-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4d044-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="4d044-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4d044-110">Sie müssen die folgenden Konfigurationsschritte ausführen, um die Integration des verwalteten Sicherheitsdienstanbieters (Managed Security Service Provider, MSSP) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4d044-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="4d044-111">Die folgenden Begriffe werden in diesem Artikel verwendet, um zwischen dem Dienstanbieter und dem Dienstanbieter zu unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="4d044-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="4d044-112">MSSPs: Sicherheitsorganisationen, die anbieten, Sicherheitsgeräte für eine Organisation zu überwachen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4d044-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="4d044-113">MSSP-Kunden: Organisationen, die die Dienste von MSSPs nutzen.</span><span class="sxs-lookup"><span data-stu-id="4d044-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="4d044-114">Die Integration ermöglicht MSSPs die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="4d044-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="4d044-115">Zugriff auf das Microsoft 365 Defender-Portal des MSSP-Kunden</span><span class="sxs-lookup"><span data-stu-id="4d044-115">Get access to MSSP customer's Microsoft 365 Defender portal</span></span>
- <span data-ttu-id="4d044-116">Abrufen von E-Mail-Benachrichtigungen und</span><span class="sxs-lookup"><span data-stu-id="4d044-116">Get email notifications, and</span></span> 
- <span data-ttu-id="4d044-117">Abrufen von Warnungen über SIEM-Tools (Security Information and Event Management)</span><span class="sxs-lookup"><span data-stu-id="4d044-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="4d044-118">Bevor MSSPs diese Aktionen ausführen können, muss der MSSP-Kunde Zugriff auf den Defender für Endpunkt-Mandanten gewähren, damit der MSSP auf das Portal zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="4d044-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="4d044-119">In der Regel führen MSSP-Kunden die anfänglichen Konfigurationsschritte aus, um MSSPs Zugriff auf ihren Windows Defender Security Central-Mandanten zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="4d044-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="4d044-120">Nachdem der Zugriff gewährt wurde, können andere Konfigurationsschritte entweder vom MSSP-Kunden oder vom MSSP ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4d044-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="4d044-121">Im Allgemeinen müssen die folgenden Konfigurationsschritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4d044-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="4d044-122">**Gewähren des MSSP-Zugriffs auf Microsoft 365 Defender**</span><span class="sxs-lookup"><span data-stu-id="4d044-122">**Grant the MSSP access to Microsoft 365 Defender**</span></span> <br>
<span data-ttu-id="4d044-123">Diese Aktion muss vom MSSP-Kunden ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4d044-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="4d044-124">Sie gewährt dem MSSP Zugriff auf den Defender für Endpunkt-Mandanten des MSSP-Kunden.</span><span class="sxs-lookup"><span data-stu-id="4d044-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="4d044-125">**Konfigurieren von Warnungsbenachrichtigungen, die an MSSPs gesendet werden**</span><span class="sxs-lookup"><span data-stu-id="4d044-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="4d044-126">Diese Aktion kann entweder vom MSSP-Kunden oder von MSSP ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4d044-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="4d044-127">Dadurch können die MSSPs wissen, welche Warnungen sie für den MSSP-Kunden behandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="4d044-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="4d044-128">**Abrufen von Warnungen vom Mandanten des MSSP-Kunden in das SIEM-System**</span><span class="sxs-lookup"><span data-stu-id="4d044-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="4d044-129">Diese Aktion wird vom MSSP ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d044-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="4d044-130">Es ermöglicht MSSPs, Warnungen in SIEM-Tools abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d044-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="4d044-131">**Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs**</span><span class="sxs-lookup"><span data-stu-id="4d044-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="4d044-132">Diese Aktion wird vom MSSP ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d044-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="4d044-133">Es ermöglicht MSSPs, Warnungen mithilfe von APIs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4d044-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="4d044-134">Mehrinstanzenfähiger Zugriff für MSSPs</span><span class="sxs-lookup"><span data-stu-id="4d044-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="4d044-135">Informationen zum Implementieren eines delegierten Mehrmandantenzugriffs finden Sie unter ["Mehrinstanzenzugriff für Verwaltete Sicherheitsdienstanbieter".](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)</span><span class="sxs-lookup"><span data-stu-id="4d044-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="4d044-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4d044-136">Related topics</span></span>
- [<span data-ttu-id="4d044-137">Gewähren von MSSP-Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="4d044-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="4d044-138">Zugreifen auf das MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="4d044-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="4d044-139">Warnungsbenachrichtigungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4d044-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="4d044-140">Abrufen von Benachrichtigungen vom Kunden-Mandanten</span><span class="sxs-lookup"><span data-stu-id="4d044-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

