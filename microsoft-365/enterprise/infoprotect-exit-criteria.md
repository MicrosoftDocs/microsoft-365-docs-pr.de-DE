---
title: Beendigungskriterien für die Information Protection-Infrastruktur
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283696"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Beendigungskriterien für die Information Protection-Infrastruktur

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Stellen Sie sicher, dass Ihre Information Protection-Infrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert

Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.

Sie verwenden mindestens drei Sicherheitsstufen:

- Baseline
- Vertraulich
- Streng geregelt

Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Erforderlich: Erhöhte Sicherheit für Microsoft 365 ist konfiguriert

Sie haben die folgenden Einstellungen für [höhere Sicherheit von Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) konfiguriert:

- Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center
- Zusätzliche mandantenweite Exchange Online-Einstellungen
- Mandantenweite Freigaberichtlinien im SharePoint Admin Center
- Azure Active Directory-Einstellungen (Azure AD)

Sie haben zudem [Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams aktiviert](https://docs.microsoft.com/de-DE/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Optional: Klassifikation ist in der gesamten Umgebung konfiguriert

Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für Data Governance- und Sicherheitsrichtlinien in Ihrer Organisation erarbeitet. 

Diese Richtlinien entsprechen der Konfiguration und Bereitstellung von:

- Typen vertraulicher Daten
- Aufbewahrungsbezeichnungen
- Vertraulichkeitsbezeichnungen
- Azure Information Protection-Bezeichnungen

Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Optional: Konfigurieren von Privileged Access Management in Office 365

Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen. Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen. 

## <a name="results-and-next-steps"></a>Ergebnisse und nächste Schritte

Ihre Information Protection-Infrastruktur für Microsoft 365 Enterprise verwendet definierte Sicherheitsstufen, erhöhte Sicherheit für Office 365, Klassifizierungen anhand vertraulicher Datentypen und -bezeichnungen und privilegierte Zugriffsverwaltung.

Wenn Sie die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise befolgen, Sie können jetzt für alle Ihre [Arbeitslasten und Szenarien](deploy-workloads.md) die Vorteile der Funktionen und Konfiguration der Foundation-Infrastruktur nutzen.
