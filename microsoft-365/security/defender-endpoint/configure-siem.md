---
title: Pull detections to your SIEM tools from Microsoft Defender for Endpoint
description: Erfahren Sie, wie Sie die REST-API verwenden und unterstützte Sicherheitsinformationen und Ereignisverwaltungstools für den Empfang und das Abrufen von Erkennungen konfigurieren.
keywords: Konfigurieren von Siem, Verwaltungstools für Sicherheitsinformationen und Ereignisse, Splunk, Arcsight, benutzerdefinierte Indikatoren, Rest-API, Warnungsdefinitionen, Kompromissindikatoren
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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222335"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="b9614-104">Ziehen von Erkennungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="b9614-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9614-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b9614-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9614-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b9614-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9614-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9614-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b9614-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b9614-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9614-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b9614-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="b9614-110">Pull detections using security information and events management (SIEM) tools</span><span class="sxs-lookup"><span data-stu-id="b9614-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="b9614-111">[Microsoft Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="b9614-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="b9614-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="b9614-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="b9614-113">-Die Microsoft Defender for Endpoint Alert-API ist die neueste API für den Warnungsverbrauch und enthält eine detaillierte Liste verwandter Nachweise für jede Warnung.</span><span class="sxs-lookup"><span data-stu-id="b9614-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="b9614-114">Weitere Informationen finden Sie unter [Warnungsmethoden und -eigenschaften und](alerts.md) [Warnungen auflisten.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b9614-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="b9614-115">Defender for Endpoint unterstützt Sicherheitsinformations- und Ereignisverwaltungstools (SIEM) zum Ziehen von Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="b9614-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="b9614-116">Defender for Endpoint macht Warnungen über einen in Azure gehosteten HTTPS-Endpunkt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9614-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="b9614-117">Der Endpunkt kann so konfiguriert werden, dass Erkennungen von Ihrem Unternehmens-Mandanten in Azure Active Directory (AAD) mithilfe des OAuth 2.0-Authentifizierungsprotokolls für eine AAD-Anwendung, die den spezifischen SIEM-Connector darstellt, der in Ihrer Umgebung installiert ist, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9614-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="b9614-118">Defender for Endpoint unterstützt derzeit die folgenden spezifischen SIEM-Lösungstools über ein dediziertes SIEM-Integrationsmodell:</span><span class="sxs-lookup"><span data-stu-id="b9614-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="b9614-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="b9614-119">IBM QRadar</span></span>
- <span data-ttu-id="b9614-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="b9614-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="b9614-121">Andere SIEM-Lösungen (z. B. Splunk, RSA NetWitness) werden über ein anderes Integrationsmodell unterstützt, das auf der neuen Warnungs-API basiert.</span><span class="sxs-lookup"><span data-stu-id="b9614-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="b9614-122">Weitere Informationen finden Sie auf der [Seite Partneranwendung,](https://securitycenter.microsoft.com/interoperability/partners) und wählen Sie den Abschnitt Sicherheitsinformationen und Analysen aus, um ausführliche Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b9614-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="b9614-123">Um eines dieser unterstützten SIEM-Tools zu verwenden, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="b9614-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="b9614-124">Aktivieren der SIEM-Integration in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b9614-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="b9614-125">Konfigurieren Des unterstützten SIEM-Tools:</span><span class="sxs-lookup"><span data-stu-id="b9614-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="b9614-126">Konfigurieren von Micro Focus ArcSight zum Ziehen von Defender for Endpoint-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="b9614-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="b9614-127">Konfigurieren von IBM QRadar zum Ziehen von Defender for Endpoint-Erkennungen Weitere Informationen finden Sie unter [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span><span class="sxs-lookup"><span data-stu-id="b9614-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="b9614-128">Weitere Informationen zur Liste der in der Erkennungs-API verfügbar gemachten Felder finden Sie unter [Defender for Endpoint Detection fields](api-portal-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b9614-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
