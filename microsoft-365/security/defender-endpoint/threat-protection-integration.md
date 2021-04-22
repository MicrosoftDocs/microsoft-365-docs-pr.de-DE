---
title: Integrieren von Microsoft Defender for Endpoint in andere Microsoft-Lösungen
description: Erfahren Sie, wie Microsoft Defender for Endpoint in andere Microsoft-Lösungen integriert wird, einschließlich Microsoft Defender for Identity und Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 Defender, bedingter Zugriff, Office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, Microsoft Cloud App Security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935533"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="d795a-104">Microsoft Defender für Endpoint und andere Microsoft-Lösungen</span><span class="sxs-lookup"><span data-stu-id="d795a-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d795a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d795a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d795a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d795a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d795a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d795a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d795a-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d795a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d795a-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d795a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="d795a-110">Integration in andere Microsoft-Lösungen</span><span class="sxs-lookup"><span data-stu-id="d795a-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="d795a-111">Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden.</span><span class="sxs-lookup"><span data-stu-id="d795a-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="d795a-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="d795a-112">Azure Defender</span></span>
<span data-ttu-id="d795a-113">Microsoft Defender for Endpoint bietet eine umfassende Serverschutzlösung, einschließlich der Funktionen für die Erkennung und Reaktion von Endpunkten (Endpoint Detection and Response, EDR) auf Windows-Servern.</span><span class="sxs-lookup"><span data-stu-id="d795a-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="d795a-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="d795a-114">Azure Sentinel</span></span>
<span data-ttu-id="d795a-115">Mit dem Microsoft Defender for Endpoint-Connector können Sie Warnungen von Microsoft Defender for Endpoint in Azure Sentinel streamen.</span><span class="sxs-lookup"><span data-stu-id="d795a-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="d795a-116">Auf diese Weise können Sie Sicherheitsereignisse in Ihrer Organisation umfassender analysieren und Playbooks für eine effektive und sofortige Reaktion erstellen.</span><span class="sxs-lookup"><span data-stu-id="d795a-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="d795a-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d795a-117">Azure Information Protection</span></span>
<span data-ttu-id="d795a-118">Wir haben die Azure Information Protection-Integration kürzlich veraltet, da unsere Endpoint DLP-Funktionen eine verbesserte Ermittlungs- und Schutzlösung für vertrauliche Daten enthalten, die auf Endpunktgeräten gespeichert sind und eine bessere Sichtbarkeit und Integration zwischen Lösungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d795a-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="d795a-119">Dies wurde im folgenden Blog [angekündigt.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)</span><span class="sxs-lookup"><span data-stu-id="d795a-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="d795a-120">Es wird empfohlen, dass Kunden zu Endpoint DLP wechseln.</span><span class="sxs-lookup"><span data-stu-id="d795a-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="d795a-121">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="d795a-121">Conditional Access</span></span>
<span data-ttu-id="d795a-122">Die dynamische Geräterisikobewertung von Microsoft Defender for Endpoint ist in die Bewertung für bedingten Zugriff integriert und stellt sicher, dass nur sichere Geräte Zugriff auf Ressourcen haben.</span><span class="sxs-lookup"><span data-stu-id="d795a-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="d795a-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d795a-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="d795a-124">Microsoft Cloud App Security nutzt Microsoft Defender for Endpoint-Endpunktsignale, um eine direkte Sichtbarkeit der Verwendung von Cloudanwendung zu ermöglichen, einschließlich der Verwendung nicht unterstützter Clouddienste (Shadow-IT) von allen überwachten Microsoft Defender for Endpoint-Geräten.</span><span class="sxs-lookup"><span data-stu-id="d795a-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="d795a-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="d795a-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="d795a-126">Verdächtige Aktivitäten sind Prozesse, die in einem Benutzerkontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d795a-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="d795a-127">Die Integration zwischen Microsoft Defender for Endpoint und Microsoft Defender for Identity bietet die Flexibilität der Durchführung von Cybersicherheitsuntersuchungen über Aktivitäten und Identitäten hinweg.</span><span class="sxs-lookup"><span data-stu-id="d795a-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="d795a-128">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="d795a-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="d795a-129">[Defender für Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) schützt Ihre Organisation durch sichere Links, sichere Anlagen, erweiterte Antiphishing- und Spoof intelligence-Funktionen vor Schadsoftware in E-Mail-Nachrichten oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="d795a-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="d795a-130">Die Integration zwischen Microsoft Defender für Office 365 und Microsoft Defender for Endpoint ermöglicht Es Sicherheitsanalysten, den Einstiegspunkt eines Angriffs zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="d795a-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="d795a-131">Durch die Freigabe von Bedrohungsinformationen können Angriffe verhindert und verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="d795a-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="d795a-132">Defender for Office 365-Daten werden für Ereignisse innerhalb der letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d795a-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="d795a-133">Bei Warnungen werden Defender for Office 365-Daten basierend auf der ersten Aktivitätszeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d795a-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="d795a-134">Danach sind die Daten in Defender for Office 365 nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d795a-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="d795a-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d795a-135">Skype for Business</span></span>
<span data-ttu-id="d795a-136">Die Skype for Business-Integration bietet Analysten die Möglichkeit, über eine einfache Schaltfläche über das Portal mit einem potenziell gefährdeten Benutzer oder Gerätebesitzer zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d795a-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="d795a-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d795a-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="d795a-138">Mit Microsoft 365 Defender bilden Microsoft Defender für Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="d795a-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="d795a-139">Weitere Informationen zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d795a-139">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="d795a-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d795a-140">Related topics</span></span>
- [<span data-ttu-id="d795a-141">Konfigurieren der Integration und anderer erweiterter Features</span><span class="sxs-lookup"><span data-stu-id="d795a-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="d795a-142">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d795a-142">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="d795a-143">Microsoft 365 Defender aktivieren</span><span class="sxs-lookup"><span data-stu-id="d795a-143">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="d795a-144">Schützen von Benutzern, Daten und Geräten mit bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="d795a-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
