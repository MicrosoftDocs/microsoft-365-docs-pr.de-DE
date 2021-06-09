---
title: Verbundene Anwendungen in Microsoft Defender für Endpunkt
ms.reviewer: ''
description: Zeigen Sie verbundene Partneranwendungen an, die das standardmäßige OAuth 2.0-Protokoll zum Authentifizieren und Bereitstellen von Token für die Verwendung mit Microsoft Defender für Endpunkt-APIs verwenden.
keywords: Partner, Anwendungen, Drittanbieter, Verbindungen, Sentinelone, Spur, Bitdefender, Corrata, Morphisec, paloalto, ziften, besser mobil
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
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845582"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="29a5d-104">Verbundene Anwendungen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="29a5d-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29a5d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="29a5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="29a5d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="29a5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29a5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29a5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="29a5d-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="29a5d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="29a5d-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="29a5d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="29a5d-110">Verbundene Anwendungen können mithilfe von APIs in die Defender für Endpunkt-Plattform integriert werden.</span><span class="sxs-lookup"><span data-stu-id="29a5d-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="29a5d-111">Anwendungen verwenden das OAuth 2.0-Standardprotokoll zum Authentifizieren und Bereitstellen von Token für die Verwendung mit Microsoft Defender für Endpunkt-APIs.</span><span class="sxs-lookup"><span data-stu-id="29a5d-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="29a5d-112">Darüber hinaus können Mandantenadministratoren mit Azure Active Directory (Azure AD)-Anwendungen explizit steuern, auf welche APIs mithilfe der entsprechenden App zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="29a5d-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="29a5d-113">Sie müssen diese [Schritte](/microsoft-365/security/defender-endpoint/apis-intro) ausführen, um die APIs mit der verbundenen Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="29a5d-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="29a5d-114">Zugreifen auf die verbundene Anwendungsseite</span><span class="sxs-lookup"><span data-stu-id="29a5d-114">Access the connected application page</span></span>
<span data-ttu-id="29a5d-115">Wählen Sie im linken Navigationsmenü **Partner & APIs**  >  **Connected AAD applications** aus.</span><span class="sxs-lookup"><span data-stu-id="29a5d-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="29a5d-116">Anzeigen von Details zu verbundenen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="29a5d-116">View connected application details</span></span>
<span data-ttu-id="29a5d-117">Die Seite "Verbundene Anwendungen" enthält Informationen zu den Azure AD-Anwendungen, die mit Microsoft Defender für Endpunkt in Ihrer Organisation verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="29a5d-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="29a5d-118">Sie können die Verwendung der verbundenen Anwendungen überprüfen: zuletzt gesehen, anzahl der Anforderungen in den letzten 24 Stunden und Anforderungstrends in den letzten 30 Tagen.</span><span class="sxs-lookup"><span data-stu-id="29a5d-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Abbildung der verbundenen Apps](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="29a5d-120">Bearbeiten, Neukonfigurieren oder Löschen einer verbundenen Anwendung</span><span class="sxs-lookup"><span data-stu-id="29a5d-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="29a5d-121">Der Link **"Anwendungseinstellungen öffnen"** öffnet die entsprechende Azure AD-Anwendungsverwaltungsseite im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="29a5d-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="29a5d-122">Über das Azure-Portal können Sie Berechtigungen verwalten, neu konfigurieren oder die verbundenen Anwendungen löschen.</span><span class="sxs-lookup"><span data-stu-id="29a5d-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
