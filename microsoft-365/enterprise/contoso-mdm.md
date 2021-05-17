---
title: Verwaltung mobiler Geräte bei Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie, wie Contoso Microsoft Intune in Microsoft 365 Für Unternehmen verwendet, um seine Geräte und die Apps zu verwalten, die auf ihnen ausgeführt werden.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753993"
---
# <a name="mobile-device-management-for-contoso"></a>Verwaltung mobiler Geräte bei Contoso

Microsoft 365 für Unternehmen umfasst Intune und eine Reihe von Azure-Diensten, die die Verwaltung und Sicherheit mobiler Geräte und Anwendungen unterstützen.

Contoso verfügt über viele mobile fähige Mitarbeiter. Einige verfügen über Büros an Contoso-Standorten, andere über keine Büros. Contoso benötigte eine Möglichkeit, um die Produktivität der Mitarbeiter zu ermöglichen, aber die Geräte, die Auf diesen Geräten gespeicherten Contoso-Daten und das Anwendungsverhalten zu schützen.

## <a name="plan"></a>Planen

Contoso hat die folgenden Intune-Verwendungsfälle für die Verwaltung mobiler Geräte für unternehmen Microsoft 365 identifiziert:

- Schützen Exchange Online E-Mails und Daten, damit sie von mobilen Geräten sicher zugegriffen werden können.
- Implementieren Sie ein Bring-your-own-device (BYOD)-Programm für Contoso-Mitarbeiter.
- Issue organization-owned phones and limited-use shared tablets to Contoso employees.

Contoso verwendet Intune nicht für:

- Ermöglichen Sie Mitarbeitern den sicheren Zugriff Microsoft 365 von einem nicht verwalteten öffentlichen Kiosk aus.
- Schützen Sie lokale E-Mails und Daten, damit sie von mobilen Geräten sicher zugegriffen werden können, da es keine lokalen Microsoft-Exchange gibt.

## <a name="deploy"></a>Bereitstellen

Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:

- Festlegen von Intune als Autorität für die Mobile Geräteverwaltung (Mobile Device Management, MDM) und Verwenden von Intune in Azure zum Verwalten von Inhalten und Verwalten der Geräte
- Erstellt Azure Active Directory (Azure AD)-Gruppen für Geräte für die Registrierung und Intune-Einstellungen und gerätebasierte Richtlinien für bedingten Zugriff

  Weitere Informationen finden Sie unter [Richtlinien für den bedingten Zugriff von Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Aktivieren der Apple-Geräteplattform zur Unterstützung von Mitarbeitern mit iPads, iMacs und iPhones sowie unternehmenseigenen iPhones
- Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.
- Für Geräte, die nicht registriert sind, implementierten Sie eine Reihe von Mobile Application Management (MAM)-Richtlinien, um die Authentifizierung für den Zugriff auf Microsoft 365 erfordern.
- Es wurden Intune-Richtlinien erstellt, die Folgendes erzwingen:
  - Zugelassene Apps.
  - Geräteverschlüsselung, um nicht autorisierten Zugriff zu verhindern.
  - Eine sechsstellige PIN oder ein Kennwort.
  - Ein Inaktivitätstimeoutzeitraum.
  - Antivirus- und Schadsoftwareschutz sowie Signaturupdates mit Windows Defender auf Windows 10 Geräten.
  - Automatische Updates auf Windows 10, die die neuesten Sicherheitsupdates enthalten.
  - Übertragen von Zertifikaten auf verwaltete Geräte.
  - Eine klare Trennung der geschäftlichen und persönlichen Daten. Benutzer oder Administratoren können Unternehmensdaten selektiv vom Gerät löschen, aber persönliche Daten wie Bilder, persönliche E-Mail-Konten und persönliche Dateien unberührt lassen.

Contoso registrierte bereitgestellte PCs und unternehmenseigene Smartphones und Tablets, indem diese den entsprechenden Intune-Gerätegruppen hinzugefügt wurden. Außerdem haben sie ein BYOD-Programm für Mitarbeiter eingerichtet, um ihre persönlichen Geräte zu registrieren. Registrierte Geräte erhalten Intune-Richtlinien, was zu verwalteten und gesicherten Geräten und ihren Anwendungen führt. Geräte, die nicht registriert sind, verfügen über Mammutrichtlinien (Mobile Application Management), die zulässige Anwendungen angeben.

Hier ist die Bereitstellungsarchitektur für die Mobile Device Management von Contoso.

![Bereitstellungsinfrastruktur für mobile Geräteverwaltung von Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, [](contoso-info-protect.md) wie Contoso die Informationsschutzfunktionen von Microsoft 365 Unternehmen verwendet, um wichtige digitale Ressourcen in der gesamten Organisation zu klassifizieren, zu identifizieren und zu schützen.

## <a name="see-also"></a>Siehe auch

[Geräteverwaltung für Microsoft 365](device-management-roadmap-microsoft-365.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)

