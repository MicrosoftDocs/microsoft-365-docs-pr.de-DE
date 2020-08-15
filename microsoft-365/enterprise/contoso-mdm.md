---
title: Verwaltung mobiler Geräte bei Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie, wie Contoso Microsoft InTune in Microsoft 365 für Unternehmen verwendet, um die Geräte und die darauf ausgeführten apps zu verwalten.
ms.openlocfilehash: 40d9473bcadfa636f6fd2b2c6c861c27dae8497c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685842"
---
# <a name="mobile-device-management-for-contoso"></a>Verwaltung mobiler Geräte bei Contoso

Microsoft 365 für Unternehmen umfasst InTune und eine Gruppe von Azure-Diensten zur Unterstützung der Verwaltung und Sicherheit von mobilen Geräten und Anwendungen.

Bei Contoso arbeiten viele Mitarbeiter mit Mobilunterstützung, von denen einige Büros an Contoso-Standorten haben und einige nicht in Büros arbeiten. Das Unternehmen benötigte eine Möglichkeit, die Mitarbeiterproduktivität zu steigern und dabei gleichzeitig die auf diesen Geräten gespeicherten Contoso-Daten sowie das Anwendungsverhalten zu schützen.

## <a name="plan"></a>Planen

Anfang der Analyse der Verwaltung mobiler Geräte für Microsoft 365 für Unternehmen identifizierte Contoso die folgenden InTune-Anwendungsfälle:

- Schützen von Exchange Online-E-Mails und -Daten, damit von mobilen Geräten sicher auf diese zugegriffen werden kann
- Implementieren eines BYOD-Programms (Bring Your Own Device) für Contoso-Mitarbeiter
- Verteilen von Telefonen im Besitz der Organisation und gemeinsam genutzten Tablets mit beschränkter Nutzung an Contoso-Mitarbeiter

Contoso verwendet Intune nicht für Folgendes:

- Mitarbeitern den sicheren Zugriff auf Microsoft 365 über einen nicht verwalteten öffentlichen Kiosk ermöglichen
- Schützen von lokalen E-Mails und Daten, damit von mobilen Geräten sicher darauf zugegriffen werden kann, da es keine lokalen Microsoft Exchange-Server mehr gibt

## <a name="deploy"></a>Bereitstellen

Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:

- Intune wurde als MDM-Autorität (Mobile Geräteverwaltung) eingerichtet, und Intune wird auf Azure verwendet, um Inhalte und Geräte zu verwalten.
- Es wurden Azure AD-Gruppen für Geräte zur Registrierung und Intune-Einstellungen sowie gerätebasierte Richtlinien für bedingten Zugriff erstellt.

  Weitere Informationen finden Sie unter [Richtlinien für den bedingten Zugriff von Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Die Apple-Geräteplattform wurde aktiviert, um Mitarbeiter mit iPads, iMacs, iPhones und iPhone-basierten Telefonen im Besitz des Unternehmens zu unterstützen.
- Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.
- Für Geräte, die nicht registriert sind, eine Reihe von MAM-Richtlinien (Mobile Application Management), die die Authentifizierung für den Zugriff auf Microsoft 365-Dienste erfordern
- Es wurden Intune-Richtlinien erstellt, die Folgendes erzwingen:
  - Zulässige Apps
  - Geräteverschlüsselung, um nicht autorisierten Zugriff zu verhindern
  - Eine sechsstellige PIN oder ein Kennwort
  - Ein Zeitlimit für Inaktivität
  - Schutz vor Viren und Schadsoftware und Signaturupdates mit Windows Defender auf Windows 10-Geräten
  - Automatische Updates für Windows 10-Geräte, die die neuesten Sicherheitsupdates enthalten
  - Verschieben von Zertifikaten auf verwaltete Geräte
  - Eine klare Trennung der geschäftlichen und persönlichen Daten. Benutzer oder Administratoren können Unternehmensdaten selektiv vom Gerät löschen, aber persönliche Daten wie Bilder, persönliche E-Mail-Konten und persönliche Dateien unberührt lassen.

Nach der Bereitstellung hat Contoso PCs sowie Smartphones und Tablets im Besitz des Unternehmens registriert, indem diese zu den entsprechenden Intune-Gerätegruppe hinzugefügt wurden, und es wurde ein BYOD-Programm eingeführt, im Rahmen dessen Mitarbeiter ihre persönlichen Geräte registrieren können. Registrierte Geräte erhielten Intune-Richtlinien, die zu verwalteten und geschützten Geräten und Anwendungen führten. Geräte, die nicht registriert wurden, weisen MAM-Richtlinien auf, in denen zulässige Anwendungen angegeben werden.

Hier ist Contosos Bereitstellungsarchitektur für die Verwaltung mobiler Geräte.

![Contosos Bereitstellungsarchitektur für die Verwaltung mobiler Geräte](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-info-protect.md) , wie Contoso die Informationen Schutzfunktionen von Microsoft 365 für Unternehmen verwendet, um wichtige digitale Objekte in Ihrer Organisation zu klassifizieren, zu identifizieren und zu schützen.

## <a name="see-also"></a>Siehe auch

[Geräteverwaltung für Microsoft 365](device-management-roadmap-microsoft-365.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)

