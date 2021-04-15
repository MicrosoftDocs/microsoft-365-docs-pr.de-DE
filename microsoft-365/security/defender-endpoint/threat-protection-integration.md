---
title: Integrieren von Microsoft Defender for Endpoint in andere Microsoft-Lösungen
description: Erfahren Sie, wie Microsoft Defender for Endpoint in andere Microsoft-Lösungen integriert wird, einschließlich Microsoft Defender for Identity und Azure Security Center.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 Defender, bedingter Zugriff, Office, erweiterter Bedrohungsschutz, Microsoft Defender for Identity, Microsoft Defender for Office, Azure Security Center, Microsoft Cloud App Security, Azure Sentinel
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
ms.openlocfilehash: 7d12afd27288655f4f5a82eeed24686f27171a7a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765395"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="e1bf2-104">Microsoft Defender für Endpoint und andere Microsoft-Lösungen</span><span class="sxs-lookup"><span data-stu-id="e1bf2-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e1bf2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e1bf2-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1bf2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e1bf2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e1bf2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1bf2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e1bf2-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e1bf2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e1bf2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="e1bf2-110">Integration in andere Microsoft-Lösungen</span><span class="sxs-lookup"><span data-stu-id="e1bf2-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="e1bf2-111">Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-security-center"></a><span data-ttu-id="e1bf2-112">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="e1bf2-112">Azure Security Center</span></span>
<span data-ttu-id="e1bf2-113">Microsoft Defender for Endpoint bietet eine umfassende Serverschutzlösung, einschließlich der Funktionen für die Erkennung und Reaktion von Endpunkten (Endpoint Detection and Response, EDR) auf Windows-Servern.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="e1bf2-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="e1bf2-114">Azure Sentinel</span></span>
<span data-ttu-id="e1bf2-115">Mit dem Microsoft Defender for Endpoint-Connector können Sie Warnungen von Microsoft Defender for Endpoint in Azure Sentinel streamen.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="e1bf2-116">Auf diese Weise können Sie Sicherheitsereignisse in Ihrer Organisation umfassender analysieren und Playbooks für eine effektive und sofortige Reaktion erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="e1bf2-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="e1bf2-117">Azure Information Protection</span></span>
<span data-ttu-id="e1bf2-118">Wir haben die Azure Information Protection-Integration kürzlich veraltet, da unsere Endpoint DLP-Funktionen eine verbesserte Ermittlungs- und Schutzlösung für vertrauliche Daten enthalten, die auf Endpunktgeräten gespeichert sind und eine bessere Sichtbarkeit und Integration zwischen Lösungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="e1bf2-119">Dies wurde im folgenden Blog [angekündigt.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)</span><span class="sxs-lookup"><span data-stu-id="e1bf2-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="e1bf2-120">Es wird empfohlen, dass Kunden zu Endpoint DLP wechseln.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="e1bf2-121">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="e1bf2-121">Conditional Access</span></span>
<span data-ttu-id="e1bf2-122">Die dynamische Geräterisikobewertung von Microsoft Defender for Endpoint ist in die Bewertung für bedingten Zugriff integriert und stellt sicher, dass nur sichere Geräte Zugriff auf Ressourcen haben.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="e1bf2-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e1bf2-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="e1bf2-124">Microsoft Cloud App Security nutzt Microsoft Defender for Endpoint-Endpunktsignale, um eine direkte Sichtbarkeit der Verwendung von Cloudanwendung zu ermöglichen, einschließlich der Verwendung nicht unterstützter Clouddienste (Shadow-IT) von allen überwachten Microsoft Defender for Endpoint-Geräten.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="e1bf2-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e1bf2-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="e1bf2-126">Verdächtige Aktivitäten sind Prozesse, die in einem Benutzerkontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="e1bf2-127">Die Integration zwischen Microsoft Defender for Endpoint und Azure ATP bietet die Flexibilität der Durchführung von Cybersicherheitsuntersuchungen über Aktivitäten und Identitäten hinweg.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-127">The integration between Microsoft Defender for Endpoint and Azure ATP provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="e1bf2-128">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="e1bf2-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="e1bf2-129">[Defender für Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) schützt Ihre Organisation vor Schadsoftware in E-Mail-Nachrichten oder Dateien über ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing und Spoof Intelligence-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="e1bf2-130">Durch die Integration zwischen Office 365 ATP und Microsoft Defender for Endpoint können Sicherheitsanalysten den Einstiegspunkt eines Angriffs untersuchen.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-130">The integration between Office 365 ATP and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="e1bf2-131">Durch die Freigabe von Bedrohungsinformationen können Angriffe verhindert und verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="e1bf2-132">Defender for Office 365-Daten werden für Ereignisse innerhalb der letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="e1bf2-133">Bei Warnungen werden Defender for Office 365-Daten basierend auf der ersten Aktivitätszeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="e1bf2-134">Danach sind die Daten in Defender for Office 365 nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="e1bf2-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e1bf2-135">Skype for Business</span></span>
<span data-ttu-id="e1bf2-136">Die Skype for Business-Integration bietet Analysten die Möglichkeit, über eine einfache Schaltfläche über das Portal mit einem potenziell gefährdeten Benutzer oder Gerätebesitzer zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="e1bf2-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1bf2-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="e1bf2-138">Mit Microsoft 365 Defender bilden Microsoft Defender für Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="e1bf2-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="e1bf2-139">Weitere Informationen zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1bf2-139">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="e1bf2-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e1bf2-140">Related topics</span></span>
- [<span data-ttu-id="e1bf2-141">Konfigurieren der Integration und anderer erweiterter Features</span><span class="sxs-lookup"><span data-stu-id="e1bf2-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="e1bf2-142">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1bf2-142">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="e1bf2-143">Microsoft 365 Defender aktivieren</span><span class="sxs-lookup"><span data-stu-id="e1bf2-143">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="e1bf2-144">Schützen von Benutzern, Daten und Geräten mit bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="e1bf2-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
