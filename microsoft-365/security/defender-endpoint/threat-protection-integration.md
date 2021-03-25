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
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068455"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="e9a72-104">Microsoft Defender für Endpoint und andere Microsoft-Lösungen</span><span class="sxs-lookup"><span data-stu-id="e9a72-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e9a72-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e9a72-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9a72-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e9a72-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e9a72-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9a72-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e9a72-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e9a72-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e9a72-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e9a72-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="e9a72-110">Integration in andere Microsoft-Lösungen</span><span class="sxs-lookup"><span data-stu-id="e9a72-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="e9a72-111">Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden.</span><span class="sxs-lookup"><span data-stu-id="e9a72-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-security-center"></a><span data-ttu-id="e9a72-112">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="e9a72-112">Azure Security Center</span></span>
<span data-ttu-id="e9a72-113">Microsoft Defender for Endpoint bietet eine umfassende Serverschutzlösung, einschließlich der Funktionen für die Erkennung und Reaktion von Endpunkten (Endpoint Detection and Response, EDR) auf Windows-Servern.</span><span class="sxs-lookup"><span data-stu-id="e9a72-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="e9a72-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="e9a72-114">Azure Sentinel</span></span>
<span data-ttu-id="e9a72-115">Mit dem Microsoft Defender for Endpoint-Connector können Sie Warnungen von Microsoft Defender for Endpoint in Azure Sentinel streamen.</span><span class="sxs-lookup"><span data-stu-id="e9a72-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="e9a72-116">Auf diese Weise können Sie Sicherheitsereignisse in Ihrer Organisation umfassender analysieren und Playbooks für eine effektive und sofortige Reaktion erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9a72-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="e9a72-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="e9a72-117">Azure Information Protection</span></span>
<span data-ttu-id="e9a72-118">Schützen Sie vertrauliche Daten, und ermöglichen Sie gleichzeitig die Produktivität am Arbeitsplatz durch Datenermittlung und Datenschutz.</span><span class="sxs-lookup"><span data-stu-id="e9a72-118">Keep sensitive data secure while enabling productivity in the workplace through data discovery and data protection.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="e9a72-119">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="e9a72-119">Conditional Access</span></span>
<span data-ttu-id="e9a72-120">Die dynamische Geräterisikobewertung von Microsoft Defender for Endpoint ist in die Bewertung für bedingten Zugriff integriert und stellt sicher, dass nur sichere Geräte Zugriff auf Ressourcen haben.</span><span class="sxs-lookup"><span data-stu-id="e9a72-120">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="e9a72-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e9a72-121">Microsoft Cloud App Security</span></span>
<span data-ttu-id="e9a72-122">Microsoft Cloud App Security nutzt Microsoft Defender for Endpoint-Endpunktsignale, um eine direkte Sichtbarkeit der Verwendung von Cloudanwendung zu ermöglichen, einschließlich der Verwendung nicht unterstützter Clouddienste (Shadow-IT) von allen überwachten Microsoft Defender for Endpoint-Geräten.</span><span class="sxs-lookup"><span data-stu-id="e9a72-122">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="e9a72-123">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e9a72-123">Microsoft Defender for Identity</span></span>
<span data-ttu-id="e9a72-124">Verdächtige Aktivitäten sind Prozesse, die in einem Benutzerkontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e9a72-124">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="e9a72-125">Die Integration zwischen Microsoft Defender for Endpoint und Azure ATP bietet die Flexibilität der Durchführung von Cybersicherheitsuntersuchungen über Aktivitäten und Identitäten hinweg.</span><span class="sxs-lookup"><span data-stu-id="e9a72-125">The integration between Microsoft Defender for Endpoint and Azure ATP provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="e9a72-126">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="e9a72-126">Microsoft Defender for Office</span></span>
<span data-ttu-id="e9a72-127">[Defender für Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) schützt Ihre Organisation vor Schadsoftware in E-Mail-Nachrichten oder Dateien über ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing und Spoof Intelligence-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e9a72-127">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="e9a72-128">Durch die Integration zwischen Office 365 ATP und Microsoft Defender for Endpoint können Sicherheitsanalysten den Einstiegspunkt eines Angriffs untersuchen.</span><span class="sxs-lookup"><span data-stu-id="e9a72-128">The integration between Office 365 ATP and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="e9a72-129">Durch die Freigabe von Bedrohungsinformationen können Angriffe verhindert und verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="e9a72-129">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="e9a72-130">Defender for Office 365-Daten werden für Ereignisse innerhalb der letzten 30 Tage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9a72-130">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="e9a72-131">Bei Warnungen werden Defender for Office 365-Daten basierend auf der ersten Aktivitätszeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9a72-131">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="e9a72-132">Danach sind die Daten in Defender for Office 365 nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9a72-132">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="e9a72-133">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e9a72-133">Skype for Business</span></span>
<span data-ttu-id="e9a72-134">Die Skype for Business-Integration bietet Analysten die Möglichkeit, über eine einfache Schaltfläche über das Portal mit einem potenziell gefährdeten Benutzer oder Gerätebesitzer zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e9a72-134">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="e9a72-135">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9a72-135">Microsoft 365 Defender</span></span>
<span data-ttu-id="e9a72-136">Mit Microsoft 365 Defender bilden Microsoft Defender für Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="e9a72-136">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="e9a72-137">Weitere Informationen zu Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9a72-137">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="e9a72-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e9a72-138">Related topics</span></span>
- [<span data-ttu-id="e9a72-139">Konfigurieren der Integration und anderer erweiterter Features</span><span class="sxs-lookup"><span data-stu-id="e9a72-139">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="e9a72-140">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9a72-140">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="e9a72-141">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9a72-141">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="e9a72-142">Schützen von Benutzern, Daten und Geräten mit bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="e9a72-142">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
