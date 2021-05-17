---
title: Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden
description: Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166053"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="0365e-104">Konfigurieren von Benachrichtigungen, die an MSSPs gesendet werden</span><span class="sxs-lookup"><span data-stu-id="0365e-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0365e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0365e-105">**Applies to:**</span></span>
- [<span data-ttu-id="0365e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0365e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0365e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0365e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0365e-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0365e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0365e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0365e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="0365e-110">Dieser Schritt kann entweder vom MSSP-Kunden oder vom MSSP durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0365e-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="0365e-111">MSSPs müssen über die entsprechenden Berechtigungen verfügen, um dies im Namen des MSSP-Kunden zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0365e-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="0365e-112">Nachdem der Zugriff auf das Portal gewährt wurde, können Benachrichtigungsregeln erstellt werden, damit E-Mails an MSSPs gesendet werden, wenn dem Mandanten zugeordnete Warnungen erstellt und festgelegte Bedingungen erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="0365e-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="0365e-113">Weitere Informationen finden Sie unter [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span><span class="sxs-lookup"><span data-stu-id="0365e-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="0365e-114">Diese Kontrollkästchen müssen aktiviert sein:</span><span class="sxs-lookup"><span data-stu-id="0365e-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="0365e-115">**Name der Organisation hinzufügen** – Der Name des Kunden wird E-Mail-Benachrichtigungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0365e-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="0365e-116">**Mandantenspezifischer Portallink hinzufügen** – Url des Warnungslinks hat mandantenspezifischen Parameter (tid=target_tenant_id), der direkten Zugriff auf das Zielmandantportal ermöglicht</span><span class="sxs-lookup"><span data-stu-id="0365e-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="0365e-117">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0365e-117">Related topics</span></span>
- [<span data-ttu-id="0365e-118">Gewähren von MSSP-Zugriff auf das Portal</span><span class="sxs-lookup"><span data-stu-id="0365e-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="0365e-119">Zugreifen auf das MSSP-Kundenportal</span><span class="sxs-lookup"><span data-stu-id="0365e-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="0365e-120">Abrufen von Benachrichtigungen vom Kunden-Mandanten</span><span class="sxs-lookup"><span data-stu-id="0365e-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
