---
title: Beendigungskriterien für die Information Protection-Infrastruktur
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: 267a6efaef5a5bcfb0ec9f8e0e9f33d525f5ce74
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071945"
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

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Erforderlich: Erhöhte Sicherheit für Microsoft 365 ist konfiguriert

Sie haben die folgenden Einstellungen für [höhere Sicherheit von Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) konfiguriert:

- Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center
- Zusätzliche mandantenweite Exchange Online-Einstellungen
- Mandantenweite Freigaberichtlinien im SharePoint Admin Center
- Azure Active Directory-Einstellungen (Azure AD)

Sie haben zudem [Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Optional: Klassifikation ist in der gesamten Umgebung konfiguriert

Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für Data Governance- und Sicherheitsrichtlinien in Ihrer Organisation erarbeitet. 

Diese Richtlinien entsprechen der Konfiguration und Bereitstellung von:

- Typen vertraulicher Daten
- Aufbewahrungsbezeichnungen
- Vertraulichkeitsbezeichnungen
- Azure Information Protection-Bezeichnungen

Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen. 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Optional: Windows Information Protection wird in Ihrer Umgebung eingesetzt.

Für Ihre angemeldeten Windows 10 Enterprise-Geräte wird eine Intune-Richtlinie bereitgestellt und angewendet, die definiert:

- Welche Apps geschützt werden sollen.
- Der Schutzgrad.
- Wo der Schutz gilt.

Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-deploy-windows-information-protection.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Optional: Office 365 Verhinderung von Datenverlust (DLP) wird bereitgestellt.

Sie haben die DLP-Richtlinien analysiert, getestet und dann eingeführt, mit Standorten und Regeln, Bedingungen und Maßnahmen, die Ihre Organisation benötigt, um Kunden und andere Arten von privaten Daten zu schützen und branchenspezifische und regionale Vorschriften und Anforderungen einzuhalten.

Ihre Datenkompatibilität- und Ihr Sicherheits-Personal nutzt das Office 365 Security & Compliance Dashboard zur Überwachung von DLP-Vorfällen.

Gegebenenfalls hilft Ihnen [Schritt 5](infoprotect-data-loss-prevention.md), diese Anforderung zu erfüllen. 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Optional: Konfigurieren von Privileged Access Management in Office 365

Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen. Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 6](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen. 

## <a name="results-and-next-steps"></a>Ergebnisse und nächste Schritte

Ihre Information Protection-Infrastruktur für Microsoft 365 Enterprise verwendet definierte Sicherheitsstufen, erhöhte Sicherheit für Office 365, Klassifizierungen anhand vertraulicher Datentypen und -bezeichnungen und privilegierte Zugriffsverwaltung.

Wenn Sie die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise befolgen, Sie können jetzt für alle Ihre [Arbeitslasten und Szenarien](deploy-workloads.md) die Vorteile der Funktionen und Konfiguration der Foundation-Infrastruktur nutzen.
