---
title: Beendigungskriterien für die Information Protection-Infrastruktur
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868087"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Beendigungskriterien für die Information Protection-Infrastruktur

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Bevor Sie Ihre Foundation-Infrastruktur fertig stellen, stellen Sie sicher, dass die Information Protection-Infrastruktur diese Bedingungen erfüllt. 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert

Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.

Sie verwenden mindestens drei Sicherheitsstufen:

- Baseline
- Vertraulich
- Streng geregelt

Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>Erforderlich: Erhöhte Sicherheit für Office 365 ist konfiguriert

Sie haben die folgenden Einstellungen für erhöhte Sicherheit basierend auf den Informationen unter [Konfigurieren von Ihrem Office 365-Mandanten zur Erhöhung der Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) konfiguriert:

- Richtlinien für die Bedrohungsverwaltung im Office 365 Security & Compliance Center
- Zusätzliche mandantenweite Exchange Online-Einstellungen
- Mandantenweite Freigaberichtlinien im SharePoint Admin Center
- Azure Active Directory-Einstellungen

Sie haben auch [Office 365 Advanced Threat Protection (ATP) aktiviert](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Optional: Klassifikation ist in der gesamten Umgebung konfiguriert

Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für die Daten in Ihrer Organisation erarbeitet, darunter Folgendes:

- Typen vertraulicher Daten
- Office 365-Bezeichnungen
- Azure Information Protection-Bezeichnungen

Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Optional: Konfigurieren von Privileged Access Management in Office 365

Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Office 365-Konfiguration zu erstellen. Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen. 

## <a name="next-step"></a>Nächster Schritt

Sie können jetzt [Arbeitslasten und Szenarien](deploy-workloads.md) wie Microsoft Teams und Exchange Online bereitstellen, die zusätzlich zu Ihrer Microsoft 365 Enterprise Foundation-Infrastruktur ausgeführt werden.
