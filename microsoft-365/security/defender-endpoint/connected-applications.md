---
title: Verbundene Anwendungen in Microsoft Defender for Endpoint
ms.reviewer: ''
description: Anzeigen von Anwendungen mit verbundenen Partnern, die das Standard-OAuth 2.0-Protokoll verwenden, um sich zu authentifizieren und Token für die Verwendung mit Microsoft Defender für Endpunkt-APIs zur Verfügung zu stellen.
keywords: partner, applications, third-party, connections, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893497"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="5297d-104">Verbundene Anwendungen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5297d-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5297d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5297d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5297d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5297d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5297d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5297d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5297d-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5297d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5297d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5297d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="5297d-110">Verbundene Anwendungen werden mithilfe von APIs in die Defender for Endpoint-Plattform integriert.</span><span class="sxs-lookup"><span data-stu-id="5297d-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="5297d-111">Anwendungen verwenden das Standard-OAuth 2.0-Protokoll, um sich zu authentifizieren und Token für die Verwendung mit Microsoft Defender for Endpoint-APIs zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="5297d-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="5297d-112">Darüber hinaus können Azure Active Directory (Azure AD)-Anwendungen Mandantenadministratoren explizit steuern, auf welche APIs über die entsprechende App zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5297d-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="5297d-113">Sie müssen diese Schritte [ausführen,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) um die APIs mit der verbundenen Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5297d-113">You'll need to follow [these steps](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="5297d-114">Zugreifen auf die Seite der verbundenen Anwendung</span><span class="sxs-lookup"><span data-stu-id="5297d-114">Access the connected application page</span></span>
<span data-ttu-id="5297d-115">Wählen Sie im linken Navigationsmenü **Partner & APIs**  >  **Connected AAD applications aus.**</span><span class="sxs-lookup"><span data-stu-id="5297d-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="5297d-116">Anzeigen verbundener Anwendungsdetails</span><span class="sxs-lookup"><span data-stu-id="5297d-116">View connected application details</span></span>
<span data-ttu-id="5297d-117">Die Seite Verbundene Anwendungen enthält Informationen zu den Azure AD-Anwendungen, die mit Microsoft Defender for Endpoint in Ihrer Organisation verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="5297d-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="5297d-118">Sie können die Verwendung der verbundenen Anwendungen überprüfen: zuletzt gesehen, Anzahl der Anforderungen in den letzten 24 Stunden und Anforderungstrends in den letzten 30 Tagen.</span><span class="sxs-lookup"><span data-stu-id="5297d-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Abbildung von verbundenen Apps](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="5297d-120">Bearbeiten, Neukonfiguration oder Löschen einer verbundenen Anwendung</span><span class="sxs-lookup"><span data-stu-id="5297d-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="5297d-121">Der **Link Anwendungseinstellungen öffnen** öffnet die entsprechende Azure AD-Anwendungsverwaltungsseite im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="5297d-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="5297d-122">Über das Azure-Portal können Sie Berechtigungen verwalten, die verbundenen Anwendungen neu konfigurieren oder löschen.</span><span class="sxs-lookup"><span data-stu-id="5297d-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
