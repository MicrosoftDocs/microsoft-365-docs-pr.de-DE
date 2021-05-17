---
title: Zugreifen auf das Microsoft Defender Security Center MSSP-Kundenportal
description: Zugreifen auf das Microsoft Defender Security Center MSSP-Kundenportal
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164857"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="83183-104">Zugreifen auf das Microsoft Defender Security Center MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="83183-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="83183-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="83183-105">**Applies to:**</span></span>
- [<span data-ttu-id="83183-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="83183-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="83183-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83183-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="83183-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="83183-108">**Applies to:**</span></span>

- [<span data-ttu-id="83183-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="83183-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="83183-110">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="83183-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83183-111">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="83183-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="83183-112">Diese Schritte richten sich an den MSSP.</span><span class="sxs-lookup"><span data-stu-id="83183-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="83183-113">Standardmäßig greifen MSSP-Kunden über die folgende URL auf Microsoft Defender Security Center Mandanten zu: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="83183-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="83183-114">MSSPs müssen jedoch eine mandantenspezifische URL im folgenden Format verwenden: für den Zugriff  `https://securitycenter.windows.com?tid=customer_tenant_id` auf das MSSP-Kundenportal.</span><span class="sxs-lookup"><span data-stu-id="83183-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="83183-115">Im Allgemeinen müssen MSSPs jedem Azure AD des MSSP-Kunden hinzugefügt werden, den er verwalten möchte.</span><span class="sxs-lookup"><span data-stu-id="83183-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="83183-116">Verwenden Sie die folgenden Schritte, um die MSSP-Kunden-Mandanten-ID zu erhalten, und verwenden Sie dann die ID, um auf die mandantenspezifische URL zu zugreifen:</span><span class="sxs-lookup"><span data-stu-id="83183-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="83183-117">Melden Sie sich als MSSP mit Ihren Anmeldeinformationen bei Azure AD an.</span><span class="sxs-lookup"><span data-stu-id="83183-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="83183-118">Wechseln Sie zum Mandanten des MSSP-Kunden.</span><span class="sxs-lookup"><span data-stu-id="83183-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="83183-119">Wählen **Azure Active Directory > Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="83183-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="83183-120">Sie finden die Mandanten-ID im Feld Verzeichnis-ID.</span><span class="sxs-lookup"><span data-stu-id="83183-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="83183-121">Greifen Sie auf das MSSP-Kundenportal zu, indem Sie den `customer_tenant_id` Wert in der folgenden URL ersetzen: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="83183-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="83183-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="83183-122">Related topics</span></span>
- [<span data-ttu-id="83183-123">Gewähren von MSSP-Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="83183-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="83183-124">Warnungsbenachrichtigungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="83183-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="83183-125">Abrufen von Benachrichtigungen vom Kunden-Mandanten</span><span class="sxs-lookup"><span data-stu-id="83183-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
