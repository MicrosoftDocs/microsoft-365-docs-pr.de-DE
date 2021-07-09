---
title: Zugreifen auf das Microsoft 365 Defender MSSP-Kundenportal
description: Zugreifen auf das Microsoft 365 Defender MSSP-Kundenportal
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339586"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a><span data-ttu-id="2d080-104">Zugreifen auf das Microsoft 365 Defender MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="2d080-104">Access the Microsoft 365 Defender MSSP customer portal</span></span>

<span data-ttu-id="2d080-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2d080-105">**Applies to:**</span></span>
- [<span data-ttu-id="2d080-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2d080-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2d080-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d080-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2d080-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2d080-108">**Applies to:**</span></span>

- [<span data-ttu-id="2d080-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2d080-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="2d080-110">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2d080-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d080-111">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="2d080-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="2d080-112">Diese Schritte werden an den MSSP weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="2d080-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="2d080-113">Mssp-Kunden greifen standardmäßig über die folgende URL auf ihren Microsoft Defender Security Center Mandanten `https://securitycenter.windows.com` zu:</span><span class="sxs-lookup"><span data-stu-id="2d080-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="2d080-114">MSSPs müssen jedoch eine mandantenspezifische URL im folgenden Format verwenden:  `https://securitycenter.windows.com?tid=customer_tenant_id` für den Zugriff auf das MSSP-Kundenportal.</span><span class="sxs-lookup"><span data-stu-id="2d080-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="2d080-115">Im Allgemeinen müssen MSSPs jedem Azure AD des MSSP-Kunden hinzugefügt werden, den er verwalten möchte.</span><span class="sxs-lookup"><span data-stu-id="2d080-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="2d080-116">Führen Sie die folgenden Schritte aus, um die MSSP-Kundenmandanten-ID abzurufen, und verwenden Sie dann die ID, um auf die mandantenspezifische URL zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="2d080-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="2d080-117">Melden Sie sich als MSSP mit Ihren Anmeldeinformationen bei Azure AD an.</span><span class="sxs-lookup"><span data-stu-id="2d080-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="2d080-118">Wechseln Sie zum Verzeichnis zum Mandanten des MSSP-Kunden.</span><span class="sxs-lookup"><span data-stu-id="2d080-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="2d080-119">Wählen Sie **Azure Active Directory > Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="2d080-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="2d080-120">Sie finden die Mandanten-ID im Verzeichnis-ID-Feld.</span><span class="sxs-lookup"><span data-stu-id="2d080-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="2d080-121">Greifen Sie auf das MSSP-Kundenportal zu, indem Sie den `customer_tenant_id` Wert in der folgenden URL ersetzen: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="2d080-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2d080-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2d080-122">Related topics</span></span>
- [<span data-ttu-id="2d080-123">Gewähren von MSSP-Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="2d080-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="2d080-124">Warnungsbenachrichtigungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2d080-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="2d080-125">Abrufen von Benachrichtigungen vom Kunden-Mandanten</span><span class="sxs-lookup"><span data-stu-id="2d080-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
