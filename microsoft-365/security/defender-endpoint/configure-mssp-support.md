---
title: Konfigurieren der Unterstützung von verwalteten Sicherheitsdienstanbietern
description: Ausführen der erforderlichen Schritte zum Konfigurieren der MSSP-Integration mit Microsoft Defender for Endpoint
keywords: Managed Security Service Provider, mssp, configure, integration
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165249"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="81843-104">Konfigurieren der Integration von verwalteten Sicherheitsdienstanbietern</span><span class="sxs-lookup"><span data-stu-id="81843-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="81843-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="81843-105">**Applies to:**</span></span>
- [<span data-ttu-id="81843-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="81843-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="81843-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81843-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="81843-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="81843-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="81843-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="81843-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="81843-110">Sie müssen die folgenden Konfigurationsschritte ausführen, um die Integration des anbieters für verwaltete Sicherheit (Managed Security Service Provider, MSSP) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81843-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="81843-111">Die folgenden Begriffe werden in diesem Artikel verwendet, um zwischen dem Dienstanbieter und dem Dienstanbieter zu unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="81843-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="81843-112">MSSPs: Sicherheitsorganisationen, die anbieten, Sicherheitsgeräte für eine Organisation zu überwachen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="81843-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="81843-113">MSSP-Kunden: Organisationen, die die Dienste von MSSPs nutzen.</span><span class="sxs-lookup"><span data-stu-id="81843-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="81843-114">Die Integration ermöglicht es MSSPs, die folgenden Aktionen zu ergreifen:</span><span class="sxs-lookup"><span data-stu-id="81843-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="81843-115">Zugriff auf das Microsoft Defender Security Center-Portal des MSSP-Kunden</span><span class="sxs-lookup"><span data-stu-id="81843-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="81843-116">Erhalten von E-Mail-Benachrichtigungen und</span><span class="sxs-lookup"><span data-stu-id="81843-116">Get email notifications, and</span></span> 
- <span data-ttu-id="81843-117">Abrufen von Warnungen über SieM-Tools (Security Information and Event Management)</span><span class="sxs-lookup"><span data-stu-id="81843-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="81843-118">Bevor MSSPs diese Aktionen ausführen können, muss der MSSP-Kunde zugriff auf seinen Defender for Endpoint-Mandanten gewähren, damit der MSSP auf das Portal zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="81843-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="81843-119">In der Regel ergreifen MSSP-Kunden die ersten Konfigurationsschritte, um MSSPs Zugriff auf ihren Windows Defender Security Central-Mandanten zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="81843-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="81843-120">Nachdem der Zugriff gewährt wurde, können andere Konfigurationsschritte vom MSSP-Kunden oder vom MSSP durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="81843-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="81843-121">Im Allgemeinen müssen die folgenden Konfigurationsschritte unternommen werden:</span><span class="sxs-lookup"><span data-stu-id="81843-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="81843-122">**Gewähren des MSSP-Zugriffs auf Microsoft Defender Security Center**</span><span class="sxs-lookup"><span data-stu-id="81843-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="81843-123">Diese Aktion muss vom MSSP-Kunden durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="81843-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="81843-124">Es gewährt dem MSSP Zugriff auf den Defender for Endpoint-Mandanten des MSSP-Kunden.</span><span class="sxs-lookup"><span data-stu-id="81843-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="81843-125">**Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden**</span><span class="sxs-lookup"><span data-stu-id="81843-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="81843-126">Diese Aktion kann vom MSSP-Kunden oder vom MSSP ergriffen werden.</span><span class="sxs-lookup"><span data-stu-id="81843-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="81843-127">Dadurch erfahren die MSSPs, welche Warnungen sie für den MSSP-Kunden adressiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="81843-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="81843-128">**Abrufen von Warnungen vom Mandanten des MSSP-Kunden in das SIEM-System**</span><span class="sxs-lookup"><span data-stu-id="81843-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="81843-129">Diese Aktion wird vom MSSP ergriffen.</span><span class="sxs-lookup"><span data-stu-id="81843-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="81843-130">Es ermöglicht MSSPs das Abrufen von Warnungen in SIEM-Tools.</span><span class="sxs-lookup"><span data-stu-id="81843-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="81843-131">**Abrufen von Warnungen vom Mandanten des MSSP-Kunden mithilfe von APIs**</span><span class="sxs-lookup"><span data-stu-id="81843-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="81843-132">Diese Aktion wird vom MSSP ergriffen.</span><span class="sxs-lookup"><span data-stu-id="81843-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="81843-133">Es ermöglicht MSSPs das Abrufen von Warnungen mithilfe von APIs.</span><span class="sxs-lookup"><span data-stu-id="81843-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="81843-134">Mehr-Mandanten-Zugriff für MSSPs</span><span class="sxs-lookup"><span data-stu-id="81843-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="81843-135">Informationen zum Implementieren eines delegierten Zugriffs mit mehreren Mandanten finden Sie unter [Multi-Tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span><span class="sxs-lookup"><span data-stu-id="81843-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="81843-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="81843-136">Related topics</span></span>
- [<span data-ttu-id="81843-137">Gewähren von MSSP-Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="81843-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="81843-138">Zugreifen auf das MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="81843-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="81843-139">Konfigurieren von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="81843-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="81843-140">Abrufen von Warnungen vom Kunden-Mandanten</span><span class="sxs-lookup"><span data-stu-id="81843-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

