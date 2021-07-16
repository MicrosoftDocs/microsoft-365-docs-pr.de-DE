---
title: App-Governance in Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Implementieren von Microsoft App-Governance-Funktionen zum Steuern Ihrer Apps.
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430696"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a><span data-ttu-id="d36df-103">App-Governance-Add-On für Microsoft Cloud App Security (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d36df-103">App governance add-on to Microsoft Cloud App Security (in preview)</span></span>

><span data-ttu-id="d36df-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d36df-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d36df-105">Cyberangriffe werden immer raffinierter in der Art und Weise, wie sie die in Ihren lokalen und Cloudinfrastrukturen bereitgestellten Apps ausnutzen, die einen Ausgangspunkt für Privilegieneskalation, Lateral-Movement und die Exfiltration Ihrer Daten darstellen.</span><span class="sxs-lookup"><span data-stu-id="d36df-105">Cyberattacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructures, establishing a starting point for privilege escalation, lateral movement, and exfiltration of your data.</span></span> <span data-ttu-id="d36df-106">Um die potenziellen Risiken zu verstehen und diese Arten von Angriffen zu stoppen, müssen Sie einen klaren Einblick in die App-Compliance-Situation Ihres Unternehmens erhalten, um schnell zu erkennen, wenn eine App anomales Verhalten zeigt, und um zu reagieren, wenn dieses Verhalten Risiken für Ihre Umgebung, Daten und Benutzer darstellt.</span><span class="sxs-lookup"><span data-stu-id="d36df-106">To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture to quickly identify when an app exhibits anomalous behaviors and to respond when these behaviors present risks to your environment, data, and users.</span></span>

<span data-ttu-id="d36df-107">Das App-Governance-Add-On-Feature zu Microsoft Cloud App Security ist eine Sicherheits- und Richtlinienverwaltungsfunktion, die für OAuth-aktivierte Apps entwickelt wurde, die über Microsoft Graph-APIs auf Microsoft 365-Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d36df-107">The app governance add-on feature to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.</span></span> <span data-ttu-id="d36df-108">App-Governance bietet vollständige Transparenz, Abhilfemaßnahmen und Governance in Bezug darauf, wie diese Apps und ihre Benutzer auf Ihre in Microsoft 365 gespeicherten vertraulichen Daten zugreifen, sie nutzen und teilen, und zwar durch ergebnisorientierte Einblicke sowie automatisierte Richtlinienwarnungen und -aktionen.</span><span class="sxs-lookup"><span data-stu-id="d36df-108">App governance delivers full visibility, remediation, and governance into how these apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions.</span></span>

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

<span data-ttu-id="d36df-109">App-Governance bietet:</span><span class="sxs-lookup"><span data-stu-id="d36df-109">App governance provides you with comprehensive:</span></span>

- <span data-ttu-id="d36df-110">Umfassende **Einblicke**: Zeigen Sie alle Drittanbieter-Apps für die Microsoft 365-Plattform auf Ihrem Mandanten in einem einzigen Dashboard an.</span><span class="sxs-lookup"><span data-stu-id="d36df-110">**Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard.</span></span> <span data-ttu-id="d36df-111">Sie können den Status und die Warnungsaktivitäten aller Apps anzeigen und darauf reagieren oder antworten.</span><span class="sxs-lookup"><span data-stu-id="d36df-111">You can see all the apps’ status and alert activities and react or respond to them.</span></span>
- <span data-ttu-id="d36df-112">Umfassende **Governance**: Erstellen Sie proaktive oder reaktive Richtlinien für Muster und Verhaltensweisen von Apps und Benutzern, schützen Sie Ihre Benutzer vor der Verwendung nicht konformer oder bösartiger Apps und schränken Sie den Zugriff riskanter Apps auf Ihre Daten ein.</span><span class="sxs-lookup"><span data-stu-id="d36df-112">**Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.</span></span>
- <span data-ttu-id="d36df-113">Umfassende **Erkennung**: Sie werden gewarnt und benachrichtigt, wenn Anomalien in der App-Aktivität auftreten und wenn nicht konforme, schädliche oder riskante Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d36df-113">**Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.</span></span>
- <span data-ttu-id="d36df-114">Umfassende **Abhilfemaßnahmen**: Verwenden Sie zusammen mit automatischen Korrekturfunktionen rechtzeitig Wartungssteuerelemente, um auf erkannte ungewöhnliche App-Aktivitäten zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="d36df-114">**Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.</span></span>

<span data-ttu-id="d36df-115">App-Governance ist eine plattformbasierte Lösung, die ein integraler Bestandteil des Microsoft 365 App-Ökosystems ist.</span><span class="sxs-lookup"><span data-stu-id="d36df-115">App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem.</span></span> <span data-ttu-id="d36df-116">App-Governance überwacht und steuert OAuth-fähige Apps, die bei Azure Active Directory (Azure AD) registriert sind und über die Microsoft Graph-API auf Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d36df-116">App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API.</span></span> <span data-ttu-id="d36df-117">App-Governance bietet Ihnen Steuerungen für das Anwendungsverhaltens, um den Sicherheits- und Compliancestatus Ihrer IT-Infrastruktur zu stärken.</span><span class="sxs-lookup"><span data-stu-id="d36df-117">App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.</span></span>

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a><span data-ttu-id="d36df-118">Ein erster Einblick in die App-Governance</span><span class="sxs-lookup"><span data-stu-id="d36df-118">A first glimpse at app governance</span></span>

<span data-ttu-id="d36df-119">Um das App-Governance-Dashboard anzuzeigen, wechseln Sie zu [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="d36df-119">To see the app governance dashboard, go to [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="d36df-120">Beachten Sie, dass Ihr Anmeldekonto über eine der [Administratorrollen](app-governance-get-started.md#administrator-roles) verfügen muss, um App-Governance-Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d36df-120">Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a><span data-ttu-id="d36df-121">App-Governance-Integration mit Azure AD und Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d36df-121">App governance integration with Azure AD and Microsoft Cloud App Security</span></span>

<span data-ttu-id="d36df-122">App-Governance, Azure AD und Microsoft Cloud App Security sammeln verschiedene Datasets und stellen diese bereit:</span><span class="sxs-lookup"><span data-stu-id="d36df-122">App governance, Azure AD, and Microsoft Cloud App Security collect and provide different data sets:</span></span>

- <span data-ttu-id="d36df-123">App-Governance bietet detaillierte Informationen zur Aktivität einer App auf API-Ebene.</span><span class="sxs-lookup"><span data-stu-id="d36df-123">App governance provides detailed information about an app’s activity at the API level.</span></span>
- <span data-ttu-id="d36df-124">Azure AD stellt grundlegende App-Metadaten und ausführliche Informationen zu Anmeldungen bei Apps bereit.</span><span class="sxs-lookup"><span data-stu-id="d36df-124">Azure AD provides foundational app metadata and detailed information on sign-ins to apps.</span></span>
- <span data-ttu-id="d36df-125">Microsoft Cloud App Security stellt Informationen zum App-Risiko bereit.</span><span class="sxs-lookup"><span data-stu-id="d36df-125">Microsoft Cloud App Security provides app risk information.</span></span>

<span data-ttu-id="d36df-p106">Indem Sie Informationen über App-Governance, Azure AD und Microsoft Cloud App Security freigeben, können Sie aggregierte Informationen in einem Portal anzeigen und mühelos eine Verknüpfung mit einem anderen Portal herstellen, um weitere Informationen zu erhalten. Hier sind einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d36df-p106">By sharing information across app governance, Azure AD, and Microsoft Cloud App Security, you can display aggregate information in one portal and easily link to another portal for more information. Here are some examples:</span></span>

- <span data-ttu-id="d36df-128">Informationen zu App-Anmeldungen in App-Governance:</span><span class="sxs-lookup"><span data-stu-id="d36df-128">App sign-in information in app governance:</span></span>

  <span data-ttu-id="d36df-129">Im App-Governance-Portal können Sie die aggregierte Anmeldeaktivität für jede App anzeigen und einen Link zurück zum Azure Active Directory Admin Center erstellen, um Details zu Anmeldeereignissen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d36df-129">From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.</span></span>

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- <span data-ttu-id="d36df-130">Informationen zur API-Verwendung im Microsoft Cloud App Security-Portal:</span><span class="sxs-lookup"><span data-stu-id="d36df-130">API usage information in the Microsoft Cloud App Security portal:</span></span>

  <span data-ttu-id="d36df-131">Im Microsoft Cloud App Security-Portal können Sie die API-Nutzungsebene und aggregierte Datenübertragungen anzeigen sowie über einen Link zum App-Governance-Portal mit weiteren Details zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d36df-131">From the Microsoft Cloud App Security portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.</span></span>

<span data-ttu-id="d36df-132">Hier ist eine Zusammenfassung der Integration.</span><span class="sxs-lookup"><span data-stu-id="d36df-132">Here's a summary of the integration.</span></span>

![Integration von App-Governance mit Azure AD und Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

<span data-ttu-id="d36df-134">Zusätzlich sendet App-Governance seine Warnungen als Signale an Microsoft Cloud App Security und Microsoft 365 Defender, und App-Governance empfängt Warnungen von Microsoft Cloud App Security, um eine detailliertere Analyse von App-basierten Sicherheitsvorfällen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d36df-134">Additionally, app governance sends its alerts as signals to Microsoft Cloud App Security and Microsoft 365 Defender, and app governance receives alerts from Microsoft Cloud App Security, to enable more detailed analysis of app-based security incidents.</span></span>

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a><span data-ttu-id="d36df-135">Verwenden von App-Governance</span><span class="sxs-lookup"><span data-stu-id="d36df-135">Using app governance</span></span>

<span data-ttu-id="d36df-136">Die Verwendung von App-Governance zum Schutz Ihres Mandanten und seiner Daten vor potenziell gefährlichen oder bösartigen Apps fällt in diese drei Kernfunktionen:</span><span class="sxs-lookup"><span data-stu-id="d36df-136">Using app governance to protect your tenant and its data from potentially malicious or ill-behaved apps falls into these three core capabilities:</span></span>

| <span data-ttu-id="d36df-137">Funktion</span><span class="sxs-lookup"><span data-stu-id="d36df-137">Capability</span></span> | <span data-ttu-id="d36df-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d36df-138">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="d36df-139">App-Transparenz und -Einblicke</span><span class="sxs-lookup"><span data-stu-id="d36df-139">App visibility and insights</span></span>](app-governance-visibility-insights-overview.md) | <span data-ttu-id="d36df-140">Erhalten Sie eine 360°-Ansicht zu Datenverkehr und Aktivitäten der Microsoft 365-Anwendungen auf Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="d36df-140">Get a 360° view on traffic and activity of the Microsoft 365 applications in your tenant.</span></span> |
| [<span data-ttu-id="d36df-141">App-Richtlinien für verstärkte Governance</span><span class="sxs-lookup"><span data-stu-id="d36df-141">App policies for reinforced governance</span></span>](app-governance-app-policies-overview.md) | <span data-ttu-id="d36df-142">Erstellen Sie proaktive oder reaktive App-Richtlinien, mit denen Sie die Governance für Ihre Microsoft 365-Apps durchsetzen können.</span><span class="sxs-lookup"><span data-stu-id="d36df-142">Create proactive or reactive app policies, which will allow you to enforce governance for your Microsoft 3635 apps.</span></span> |
| [<span data-ttu-id="d36df-143">Erkennung und Behebung</span><span class="sxs-lookup"><span data-stu-id="d36df-143">Detection and remediation</span></span>](app-governance-detect-remediate-overview.md) | <span data-ttu-id="d36df-144">Überwachen Sie Ihre Apps basierend auf Plattformerkennungswarnungen oder richtliniengenerierten Erkennungswarnungen auf anomales App-Verhalten, und beheben Sie dieses, entweder automatisch basierend auf App-Richtlinieneinstellungen oder manuell.</span><span class="sxs-lookup"><span data-stu-id="d36df-144">Based on platform detection alerts or policy-generated detection alerts, monitor your apps for anomalous app behavior and remediate them, either automatically based on app policy settings or manually.</span></span> |
|||
