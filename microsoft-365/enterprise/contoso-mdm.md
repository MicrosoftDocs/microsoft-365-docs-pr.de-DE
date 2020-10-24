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
description: Erfahren Sie, wie Contoso Microsoft InTune in Microsoft 365 für Unternehmen verwendet, um die Geräte und die darauf ausgeführten apps zu verwalten.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753993"
---
# <a name="mobile-device-management-for-contoso"></a>Verwaltung mobiler Geräte bei Contoso

Microsoft 365 für Unternehmen umfasst InTune und eine Gruppe von Azure-Diensten, die die Verwaltung mobiler Geräte und Anwendungen sowie die Sicherheit unterstützen.

Contoso verfügt über viele Mobil aktivierte Mitarbeiter. Einige haben Niederlassungen an Contoso-Standorten und einige haben keine Büros. Contoso benötigte eine Möglichkeit, die Mitarbeiterproduktivität zu ermöglichen, aber die Geräte, die auf diesen Geräten gespeicherten Contoso-Daten und das Anwendungsverhalten sicher zu halten.

## <a name="plan"></a>Plan

Contoso hat die folgenden InTune-Anwendungsfälle für die Verwaltung mobiler Geräte für Microsoft 365 für Unternehmen identifiziert:

- Schützen Sie Exchange Online e-Mails und Daten, damit Sie auf mobilen Geräten sicher zugänglich sind.
- Implementieren Sie ein BYOD-Programm ("Holen Sie Ihr eigenes Gerät") für Contoso-Mitarbeiter.
- Stellen Sie die unternehmenseigenen Telefone und die Limited-use Shared Tablets für Contoso-Mitarbeiter aus.

Contoso verwendet InTune nicht für Folgendes:

- Ermöglichen Sie Mitarbeitern den sicheren Zugriff auf Microsoft 365 von einem nicht verwalteten öffentlichen Kiosk aus.
- Schützen Sie lokale e-Mails und Daten, damit Sie auf mobilen Geräten sicher zugegriffen werden kann, da keine lokalen Microsoft Exchange Server vorhanden sind.

## <a name="deploy"></a>Bereitstellen

Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:

- Festlegen von InTune als MDM-Autorität (Mobile Device Management) und Verwenden von InTune in Azure zum Verwalten von Inhalten und Verwalten der Geräte
- Erstellt Azure Active Directory (Azure AD) Gruppen für Geräte für die Registrierung und InTune-Einstellungen und gerätebasierte Richtlinien für bedingten Zugriff

  Weitere Informationen finden Sie unter [bedingte Zugriffsrichtlinien für Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Die Apple-Geräteplattform wurde aktiviert, um Mitarbeiter mit iPads, iMacs und iPhones sowie unternehmenseigenen iPhones zu unterstützen.
- Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.
- Für Geräte, die nicht registriert sind, wurde eine Reihe von MAM-Richtlinien (Mobile Application Management) implementiert, um die Authentifizierung für den Zugriff auf Microsoft 365-Dienste zu erfordern.
- Es wurden Intune-Richtlinien erstellt, die Folgendes erzwingen:
  - Zugelassene apps.
  - Geräteverschlüsselung zur Verhinderung von nicht autorisiertem Zugriff.
  - Eine sechsstellige PIN oder ein Kennwort.
  - Ein Timeoutzeitraum für Inaktivität.
  - Antiviren-und Malware Schutz sowie Signaturupdates mit Windows Defender auf Windows 10-Geräten.
  - Automatische Updates auf Windows 10-Geräten, die die neuesten Sicherheitsupdates enthalten.
  - Pushing Certificates to Managed Devices.
  - Eine klare Trennung der geschäftlichen und persönlichen Daten. Benutzer oder Administratoren können Unternehmensdaten selektiv vom Gerät löschen, aber persönliche Daten wie Bilder, persönliche E-Mail-Konten und persönliche Dateien unberührt lassen.

Contoso hat bereitgestellte PCs und unternehmenseigene Smartphones und Tablets registriert, indem Sie Sie den entsprechenden InTune-Gerätegruppen hinzugefügt haben. Sie haben außerdem ein BYOD-Programm für Mitarbeiter eingerichtet, die Ihre persönlichen Geräte registrieren. Für registriertes Gerät werden InTune-Richtlinien empfangen, die verwaltete und gesicherte Geräte und deren Anwendungen zur Folge haben. Für Geräte, die nicht registriert sind, gibt es Richtlinien für Mobile Anwendungsverwaltung (MAM), die zugelassene Anwendungen angeben.

Hier ist die Bereitstellungsarchitektur für die Mobile Geräteverwaltung von contoso.

![Bereitstellungsinfrastruktur für die Mobile Geräteverwaltung von Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso die [Informationen Schutzfunktionen](contoso-info-protect.md) von Microsoft 365 für Unternehmen verwendet, um wichtige digitale Objekte in Ihrer Organisation zu klassifizieren, zu identifizieren und zu schützen.

## <a name="see-also"></a>Siehe auch

[Geräteverwaltung für Microsoft 365](device-management-roadmap-microsoft-365.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)

