---
title: 'Schritt 5: Geräte- und App-Verwaltung für Microsoft 365 für Enterprise-Mandanten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Stellen Sie die richtige Option für die Geräte- und App-Verwaltung für Ihre Microsoft 365 zur Auswahl.
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050994"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Schritt 5. Geräte- und App-Verwaltung für Microsoft 365 für Enterprise-Mandanten

Microsoft 365 für Unternehmen umfasst Features, mit denen Sie Geräte und die Verwendung von Apps auf diesen Geräten in Ihrer Organisation mit mobiler Geräteverwaltung (Mobile Device Management, MDM) und mobiler Anwendungsverwaltung (Mobile Application Management, MAM) verwalten können. Sie können iOS-, Android-, macOS- und Windows verwalten, um den Zugriff auf die Ressourcen Ihrer Organisation, einschließlich Ihrer Daten, zu schützen. Sie können beispielsweise verhindern, dass E-Mails an Personen außerhalb Ihrer Organisation gesendet werden, oder Sie können Organisationsdaten von personenbezogenen Daten auf den persönlichen Geräten Ihrer Mitarbeiter isolieren.

Hier ist ein Beispiel für die Überprüfung und Verwaltung von Benutzern, deren Geräten und deren Verwendung lokaler und Cloudproduktivitäts-Apps wie Microsoft Teams.

![Überprüfung und Verwaltung von Benutzern, Geräten und Apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Um Die Ressourcen Ihrer Organisation zu schützen und zu schützen, enthält Microsoft 365 for Enterprise Features, mit deren Hilfe Geräte und deren Zugriff auf Apps verwaltet werden können. Es gibt zwei Optionen für die Geräteverwaltung:

- Microsoft Intune, eine umfassende Geräte- und App-Verwaltungslösung für Unternehmen.
- Grundlegende Mobilität und Sicherheit, eine Teilmenge der Intune-Dienste, die in allen Microsoft 365 zum Verwalten von Geräten in Ihrer Organisation enthalten sind. Weitere Informationen finden Sie unter [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).

Wenn Sie über Microsoft 365 E3 oder E5 verfügen, sollten Sie Intune verwenden.

## <a name="microsoft-intune"></a>Microsoft Intune

Sie verwenden [Microsoft Intune,](/mem/intune/fundamentals/planning-guide) um den Zugriff auf Ihre Organisation mithilfe von MDM oder MAM zu verwalten. MDM ist, wenn Benutzer ihre Geräte in Intune "registrieren". Nach der Registrierung eines Geräts handelt es sich um ein verwaltetes Gerät, das die Richtlinien, Regeln und Einstellungen Ihrer Organisation empfangen kann. Sie können beispielsweise bestimmte Apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten möchten ihre Geräte möglicherweise nicht registrieren oder von Intune und den Richtlinien Ihrer Organisation verwaltet werden. Sie müssen jedoch weiterhin die Ressourcen und Daten Ihrer Organisation schützen. In diesem Szenario können Sie Ihre Apps mithilfe von MAM schützen. Sie können z. B. eine MAM-Richtlinie verwenden, für die ein Benutzer eine PIN eingeben muss, wenn er auf SharePoint Gerät zutritt.

Außerdem bestimmen Sie, wie Sie persönliche Geräte und geräte im Besitz der Organisation verwalten. Sie können Geräte je nach Verwendung unterschiedlich behandeln.

## <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

Microsoft bietet eine Reihe von Konfigurationen für den Identitäts- und [Gerätezugriff,](../security/defender-365-security/microsoft-365-policies-configurations.md) um eine sichere und produktive Belegschaft sicherzustellen. Diese Konfigurationen umfassen die Verwendung von:

- Azure AD-Richtlinien für den bedingten Zugriff
- Microsoft Intune und App-Schutzrichtlinien
- Azure AD Identity Protection-Benutzerrisikorichtlinien
- Zusätzliche Richtlinien von Cloud-Apps

Im Folgenden finden Sie ein Beispiel für die Anwendung dieser Einstellungen und Richtlinien zum Überprüfen und Einschränken von Benutzern, ihren Geräten und ihrer Verwendung lokaler und Cloudproduktivitäts-Apps wie Microsoft Teams.

![Identitäts- und Gerätezugriffskonfigurationen für Anforderungen und Einschränkungen für Benutzer, ihre Geräte und deren Verwendung von Apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Verwenden Sie für den Gerätezugriff und die App-Verwaltung die Konfigurationen in den folgenden Artikeln:

- [Voraussetzungen](../security/defender-365-security/identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Ergebnisse von Schritt 5

Für die Geräte- und App-Verwaltung für Ihren Microsoft 365-Mandanten haben Sie die Intune-Einstellungen und -Richtlinien festgelegt, um Benutzer, ihre Geräte und deren Verwendung lokaler und Cloudproduktivitäts-Apps zu überprüfen und einzuschränken.

Im Folgenden finden Sie ein Beispiel für einen Mandanten mit Intune-Geräte- und App-Verwaltung mit hervorgehobenen neuen Elementen.

![Beispiel für einen Mandanten mit Intune-Geräte- und App-Verwaltung](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In dieser Abbildung verfügt der Mandant über:

- Geräte im Besitz der Organisation, die in Intune registriert sind.
- Intune-Geräte- und App-Richtlinien für registrierte und persönliche Geräte.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Fortlaufende Wartung der Geräte- und App-Verwaltung

Auf fortlaufender Basis müssen Sie möglicherweise: 

- Verwalten der Geräteregistrierung.
- Überarbeiten Sie Ihre Einstellungen und Richtlinien für zusätzliche Apps, Geräte und Sicherheitsanforderungen.