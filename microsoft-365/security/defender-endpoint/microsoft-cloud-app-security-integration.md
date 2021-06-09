---
title: Übersicht über Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender für Endpunkt lässt sich in Cloud App Security integrieren, indem alle Cloud-App-Netzwerkaktivitäten weitergeleitet werden.
keywords: Cloud, App, Netzwerk, Sichtbarkeit, Nutzung
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844742"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="8482b-104">übersicht über Microsoft Cloud App Security in Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8482b-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8482b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8482b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8482b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8482b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8482b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8482b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="8482b-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="8482b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8482b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8482b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8482b-110">Microsoft Cloud App Security (Cloud App Security) ist eine umfassende Lösung, die Einblicke in Cloud-Apps und -Dienste bietet, indem Sie den Zugriff auf Cloud-Apps steuern und einschränken und gleichzeitig Complianceanforderungen für in der Cloud gespeicherte Daten erzwingen können.</span><span class="sxs-lookup"><span data-stu-id="8482b-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="8482b-111">Weitere Informationen finden Sie unter [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="8482b-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="8482b-112">Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten mit Windows 10 Version 1809 oder höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8482b-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="8482b-113">Integration von Microsoft Defender für Endpunkt und Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8482b-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="8482b-114">Cloud App Security Ermittlung basiert auf Clouddatenverkehrsprotokollen, die von Unternehmensfirewall- und Proxyservern an sie weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8482b-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="8482b-115">Microsoft Defender für Endpunkt lässt sich in Cloud App Security integrieren, indem alle Cloud-App-Netzwerkaktivitäten gesammelt und weitergeleitet werden, sodass die Cloud-App-Nutzung sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="8482b-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="8482b-116">Die Überwachungsfunktionalität ist in das Gerät integriert und bietet eine vollständige Abdeckung der Netzwerkaktivität.</span><span class="sxs-lookup"><span data-stu-id="8482b-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="8482b-117">Die Integration bietet die folgenden wesentlichen Verbesserungen an der vorhandenen Cloud App Security Ermittlung:</span><span class="sxs-lookup"><span data-stu-id="8482b-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="8482b-118">Überall verfügbar– Da die Netzwerkaktivität direkt vom Endpunkt erfasst wird, ist sie überall verfügbar, wo sich das Gerät im oder außerhalb des Unternehmensnetzwerks befindet, da es nicht mehr vom Datenverkehr abhängt, der über die Unternehmensfirewall oder Proxyserver geleitet wird.</span><span class="sxs-lookup"><span data-stu-id="8482b-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="8482b-119">Funktioniert sofort einsatzbereit, keine Konfiguration erforderlich – Das Weiterleiten von Clouddatenverkehrsprotokollen an Cloud App Security erfordert eine Firewall- und Proxyserverkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="8482b-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="8482b-120">Bei der Integration von Defender für Endpunkt und Cloud App Security ist keine Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8482b-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="8482b-121">Schalten Sie es einfach in Microsoft Defender Security Center Einstellungen ein, und Sie können loslegen.</span><span class="sxs-lookup"><span data-stu-id="8482b-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="8482b-122">Gerätekontext: Clouddatenverkehrsprotokollen fehlt der Gerätekontext.</span><span class="sxs-lookup"><span data-stu-id="8482b-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="8482b-123">Defender für Endpunkt-Netzwerkaktivität wird mit dem Gerätekontext gemeldet (welches Gerät auf die Cloud-App zugegriffen hat), sodass Sie genau verstehen können, wo (Gerät) die Netzwerkaktivität stattgefunden hat, zusätzlich zu dem, wer (Benutzer) sie ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="8482b-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="8482b-124">Weitere Informationen zur Cloudermittlung finden Sie unter [Arbeiten mit ermittelten Apps.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="8482b-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="8482b-125">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="8482b-125">Related topic</span></span>

- [<span data-ttu-id="8482b-126">Konfigurieren der Integration von Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8482b-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
