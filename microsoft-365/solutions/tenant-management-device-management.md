---
title: 'Schritt 5: Geräte- und App-Verwaltung für Ihre Microsoft 365 Enterprise-Mandanten'
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
ms.custom:
- Ent_Solutions
description: Stellen Sie die richtige Option für die Geräte- und App-Verwaltung für Ihre Microsoft 365-Mandanten.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908583"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Schritt 5: Geräte- und App-Verwaltung für Ihre Microsoft 365 Enterprise-Mandanten

Microsoft 365 Enterprise umfasst Features, mit denen Sie Geräte und die Verwendung von Apps auf diesen Geräten in Ihrer Organisation mit mobiler Geräteverwaltung (Mobile Device Management, MDM) und mobiler Anwendungsverwaltung (Mobile Application Management, MAM) verwalten können. Sie können iOS-, Android-, macOS- und Windows-Geräte verwalten, um den Zugriff auf die Ressourcen Ihrer Organisation, einschließlich Ihrer Daten, zu schützen. Sie können beispielsweise verhindern, dass E-Mails an Personen außerhalb Ihrer Organisation gesendet werden, oder Organisationsdaten von personenbezogenen Daten auf den persönlichen Geräten Ihrer Mitarbeiter isolieren.

Hier ist ein Beispiel für die Überprüfung und Verwaltung von Benutzern, deren Geräten und deren Verwendung von lokalen und Cloud-Produktivitäts-Apps wie Microsoft Teams.

![Validierung und Verwaltung von Benutzern, Geräten und Apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Um Die Ressourcen Ihrer Organisation zu schützen und zu schützen, enthält Microsoft 365 Enterprise Features, mit deren Hilfe Geräte und deren Zugriff auf Apps verwaltet werden können. Es gibt zwei Optionen für die Geräteverwaltung:

- Microsoft Intune, eine umfassende Geräte- und App-Verwaltungslösung für Unternehmen.
- Grundlegende Mobilität und Sicherheit, eine Teilmenge der Intune-Dienste, die in allen Microsoft 365-Produkten zum Verwalten von Geräten in Ihrer Organisation enthalten sind. Weitere Informationen finden Sie unter ["Funktionen der grundlegenden Mobilität und Sicherheit".](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)

Wenn Sie über Microsoft 365 E3 oder E5 verfügen, sollten Sie Intune verwenden.

## <a name="microsoft-intune"></a>Microsoft Intune

Sie verwenden [Microsoft Intune,](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) um den Zugriff auf Ihre Organisation mithilfe von MDM oder MAM zu verwalten. MDM ist, wenn Benutzer ihre Geräte in Intune "registrieren". Nach der Registrierung eines Geräts handelt es sich um ein verwaltetes Gerät, das die Richtlinien, Regeln und Einstellungen Ihrer Organisation empfangen kann. Sie können beispielsweise bestimmte Apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten möchten ihre Geräte möglicherweise nicht registrieren oder von Intune und den Richtlinien Ihrer Organisation verwaltet werden. Dennoch müssen Sie die Ressourcen und Daten Ihrer Organisation schützen. In diesem Szenario können Sie Ihre Apps mithilfe von MAM schützen. Sie können beispielsweise eine MAM-Richtlinie verwenden, die erfordert, dass ein Benutzer beim Zugriff auf SharePoint auf dem Gerät eine PIN ein eingeben muss.

Außerdem bestimmen Sie, wie Sie persönliche Geräte und Geräte im Besitz der Organisation verwalten. Je nach Verwendung sollten Sie Geräte unterschiedlich behandeln.

## <a name="identity-and-device-access-configurations"></a>Konfigurationen für den Identitäts- und Gerätezugriff

Microsoft bietet eine Reihe von Konfigurationen für den Identitäts- und [Gerätezugriff,](../security/office-365-security/microsoft-365-policies-configurations.md) um eine sichere und produktive Belegschaft sicherzustellen. Diese Konfigurationen umfassen die Verwendung von:

- Azure AD-Richtlinien für den bedingten Zugriff
- Microsoft Intune – Gerätekonformität und Richtlinien zum Schutz von Apps
- Azure AD Identity Protection - Benutzerrisikorichtlinien
- Zusätzliche Richtlinien von Cloud-Apps

Hier ist ein Beispiel für die Anwendung dieser Einstellungen und Richtlinien zum Überprüfen und Einschränken von Benutzern, deren Geräten und ihrer Verwendung lokaler und Cloudproduktivitäts-Apps wie Microsoft Teams.

![Identitäts- und Gerätezugriffskonfigurationen für Anforderungen und Einschränkungen für Benutzer, deren Geräte und deren Verwendung von Apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Verwenden Sie für den Gerätezugriff und die App-Verwaltung die Konfigurationen in den folgenden Artikeln:

- [Voraussetzungen](../security/office-365-security/identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Ergebnisse von Schritt 5

Für die Geräte- und App-Verwaltung für Ihren Microsoft 365-Mandanten haben Sie die Intune-Einstellungen und -Richtlinien festgelegt, um Benutzer, deren Geräte und deren Verwendung lokaler und Cloudproduktivitäts-Apps zu überprüfen und einzuschränken.

Hier ist ein Beispiel für einen Mandanten mit Intune-Geräte- und -App-Verwaltung, in dem die neuen Elemente hervorgehoben sind.

![Beispiel für einen Mandanten mit Intune-Geräte- und -App-Verwaltung](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In dieser Abbildung hat der Mandant:

- Geräte im Besitz der Organisation, die in Intune registriert sind.
- Intune-Geräte- und -App-Richtlinien für registrierte und persönliche Geräte.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Laufende Wartung der Geräte- und App-Verwaltung

Es kann sein, dass Sie regelmäßig: 

- Verwalten der Geräteregistrierung.
- Überarbeiten Sie Ihre Einstellungen und Richtlinien für zusätzliche Apps, Geräte und Sicherheitsanforderungen.
