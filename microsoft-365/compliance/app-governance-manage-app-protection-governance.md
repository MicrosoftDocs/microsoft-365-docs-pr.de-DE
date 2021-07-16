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
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>App-Governance-Add-On für Microsoft Cloud App Security (Vorschau)

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Cyberangriffe werden immer raffinierter in der Art und Weise, wie sie die in Ihren lokalen und Cloudinfrastrukturen bereitgestellten Apps ausnutzen, die einen Ausgangspunkt für Privilegieneskalation, Lateral-Movement und die Exfiltration Ihrer Daten darstellen. Um die potenziellen Risiken zu verstehen und diese Arten von Angriffen zu stoppen, müssen Sie einen klaren Einblick in die App-Compliance-Situation Ihres Unternehmens erhalten, um schnell zu erkennen, wenn eine App anomales Verhalten zeigt, und um zu reagieren, wenn dieses Verhalten Risiken für Ihre Umgebung, Daten und Benutzer darstellt.

Das App-Governance-Add-On-Feature zu Microsoft Cloud App Security ist eine Sicherheits- und Richtlinienverwaltungsfunktion, die für OAuth-aktivierte Apps entwickelt wurde, die über Microsoft Graph-APIs auf Microsoft 365-Daten zugreifen. App-Governance bietet vollständige Transparenz, Abhilfemaßnahmen und Governance in Bezug darauf, wie diese Apps und ihre Benutzer auf Ihre in Microsoft 365 gespeicherten vertraulichen Daten zugreifen, sie nutzen und teilen, und zwar durch ergebnisorientierte Einblicke sowie automatisierte Richtlinienwarnungen und -aktionen.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

App-Governance bietet:

- Umfassende **Einblicke**: Zeigen Sie alle Drittanbieter-Apps für die Microsoft 365-Plattform auf Ihrem Mandanten in einem einzigen Dashboard an. Sie können den Status und die Warnungsaktivitäten aller Apps anzeigen und darauf reagieren oder antworten.
- Umfassende **Governance**: Erstellen Sie proaktive oder reaktive Richtlinien für Muster und Verhaltensweisen von Apps und Benutzern, schützen Sie Ihre Benutzer vor der Verwendung nicht konformer oder bösartiger Apps und schränken Sie den Zugriff riskanter Apps auf Ihre Daten ein.
- Umfassende **Erkennung**: Sie werden gewarnt und benachrichtigt, wenn Anomalien in der App-Aktivität auftreten und wenn nicht konforme, schädliche oder riskante Apps verwendet werden.
- Umfassende **Abhilfemaßnahmen**: Verwenden Sie zusammen mit automatischen Korrekturfunktionen rechtzeitig Wartungssteuerelemente, um auf erkannte ungewöhnliche App-Aktivitäten zu reagieren.

App-Governance ist eine plattformbasierte Lösung, die ein integraler Bestandteil des Microsoft 365 App-Ökosystems ist. App-Governance überwacht und steuert OAuth-fähige Apps, die bei Azure Active Directory (Azure AD) registriert sind und über die Microsoft Graph-API auf Daten zugreifen. App-Governance bietet Ihnen Steuerungen für das Anwendungsverhaltens, um den Sicherheits- und Compliancestatus Ihrer IT-Infrastruktur zu stärken.

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>Ein erster Einblick in die App-Governance

Um das App-Governance-Dashboard anzuzeigen, wechseln Sie zu [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Beachten Sie, dass Ihr Anmeldekonto über eine der [Administratorrollen](app-governance-get-started.md#administrator-roles) verfügen muss, um App-Governance-Daten anzuzeigen.

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>App-Governance-Integration mit Azure AD und Microsoft Cloud App Security

App-Governance, Azure AD und Microsoft Cloud App Security sammeln verschiedene Datasets und stellen diese bereit:

- App-Governance bietet detaillierte Informationen zur Aktivität einer App auf API-Ebene.
- Azure AD stellt grundlegende App-Metadaten und ausführliche Informationen zu Anmeldungen bei Apps bereit.
- Microsoft Cloud App Security stellt Informationen zum App-Risiko bereit.

Indem Sie Informationen über App-Governance, Azure AD und Microsoft Cloud App Security freigeben, können Sie aggregierte Informationen in einem Portal anzeigen und mühelos eine Verknüpfung mit einem anderen Portal herstellen, um weitere Informationen zu erhalten. Hier sind einige Beispiele:

- Informationen zu App-Anmeldungen in App-Governance:

  Im App-Governance-Portal können Sie die aggregierte Anmeldeaktivität für jede App anzeigen und einen Link zurück zum Azure Active Directory Admin Center erstellen, um Details zu Anmeldeereignissen zu erhalten.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Informationen zur API-Verwendung im Microsoft Cloud App Security-Portal:

  Im Microsoft Cloud App Security-Portal können Sie die API-Nutzungsebene und aggregierte Datenübertragungen anzeigen sowie über einen Link zum App-Governance-Portal mit weiteren Details zugreifen.

Hier ist eine Zusammenfassung der Integration.

![Integration von App-Governance mit Azure AD und Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Zusätzlich sendet App-Governance seine Warnungen als Signale an Microsoft Cloud App Security und Microsoft 365 Defender, und App-Governance empfängt Warnungen von Microsoft Cloud App Security, um eine detailliertere Analyse von App-basierten Sicherheitsvorfällen zu ermöglichen.

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

## <a name="using-app-governance"></a>Verwenden von App-Governance

Die Verwendung von App-Governance zum Schutz Ihres Mandanten und seiner Daten vor potenziell gefährlichen oder bösartigen Apps fällt in diese drei Kernfunktionen:

| Funktion | Beschreibung |
|:-------|:-----|
| [App-Transparenz und -Einblicke](app-governance-visibility-insights-overview.md) | Erhalten Sie eine 360°-Ansicht zu Datenverkehr und Aktivitäten der Microsoft 365-Anwendungen auf Ihrem Mandanten. |
| [App-Richtlinien für verstärkte Governance](app-governance-app-policies-overview.md) | Erstellen Sie proaktive oder reaktive App-Richtlinien, mit denen Sie die Governance für Ihre Microsoft 365-Apps durchsetzen können. |
| [Erkennung und Behebung](app-governance-detect-remediate-overview.md) | Überwachen Sie Ihre Apps basierend auf Plattformerkennungswarnungen oder richtliniengenerierten Erkennungswarnungen auf anomales App-Verhalten, und beheben Sie dieses, entweder automatisch basierend auf App-Richtlinieneinstellungen oder manuell. |
|||
