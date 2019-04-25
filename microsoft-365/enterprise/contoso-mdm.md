---
title: Verwaltung mobiler Geräte bei Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen Sie, wie Contoso EMS in Microsoft 365 Enterprise verwendet, um seine Geräte und die Apps zu verwalten, die darauf ausgeführt werden.
ms.openlocfilehash: f47d6a1ee608d33802f1c523d3b954af3771f212
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278042"
---
# <a name="mobile-device-management-for-contoso"></a>Verwaltung mobiler Geräte bei Contoso

**Zusammenfassung:** Verstehen Sie, wie Contoso EMS in Microsoft 365 Enterprise verwendet, um seine Geräte und die Apps zu verwalten, die darauf ausgeführt werden.

Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise besteht aus Microsoft Intune und einer Reihe von Azure-Diensten zur Unterstützung der Verwaltung mobiler Geräte und Anwendungen und der Sicherheit.

Bei Contoso arbeiten viele Mitarbeiter mit Mobilunterstützung, von denen einige Büros an Contoso-Standorten haben und einige nicht in Büros arbeiten. Das Unternehmen benötigte eine Möglichkeit, die Mitarbeiterproduktivität zu steigern und dabei gleichzeitig die auf diesen Geräten gespeicherten Contoso-Daten sowie das Anwendungsverhalten zu schützen.

## <a name="plan"></a>Planen

Bei der Analyse der Verwaltung mobiler Geräte für Microsoft 365 Enterprise identifizierte Contoso frühzeitig die folgenden Intune-Anwendungsfälle:

- Schützen von Exchange Online-E-Mails und -Daten, damit von mobilen Geräten sicher auf diese zugegriffen werden kann
- Implementieren eines BYOD-Programms (Bring Your Own Device) für Contoso-Mitarbeiter
- Verteilen von Telefonen im Besitz der Organisation und gemeinsam genutzten Tablets mit beschränkter Nutzung an Contoso-Mitarbeiter

Contoso verwendet Intune nicht für Folgendes:

- Zulassen, dass Mitarbeiter von einem nicht verwalteten öffentlichen Kiosk sicher auf Office 365 zugreifen
- Schützen von lokalen E-Mails und Daten, damit von mobilen Geräten sicher darauf zugegriffen werden kann, da es keine lokalen Microsoft Exchange-Server mehr gibt

## <a name="deploy"></a>Bereitstellen

Contoso hat seine Infrastruktur für die Verwaltung mobiler Geräte folgendermaßen eingerichtet:

- Intune wurde als MDM-Autorität (Mobile Geräteverwaltung) eingerichtet, und Intune wird auf Azure verwendet, um Inhalte und Geräte zu verwalten.
- Es wurden Azure AD-Gruppen für Geräte zur Registrierung und Intune-Einstellungen sowie gerätebasierte Richtlinien für bedingten Zugriff erstellt.

  Weitere Informationen finden Sie unter [Richtlinien für den bedingten Zugriff von Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).

- Die Apple-Geräteplattform wurde aktiviert, um Mitarbeiter mit iPads, iMacs, iPhones und iPhone-basierten Telefonen im Besitz des Unternehmens zu unterstützen.
- Es wurden Contoso-spezifische Nutzungsbedingungen erstellt, die während der Installation des Unternehmensportals für Contoso auf mobilen Geräten angezeigt werden.
- Für Geräte, die nicht registriert sind, wurde eine Reihe von MAM-Richtlinien (für mobile Anwendungsverwaltung) erstellt, die eine Authentifizierung für den Zugriff auf Office 365-Dienste erfordern.
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

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-info-protect.md), wie Contoso die Funktionen zum Schutz von Informationen von Microsoft 365 Enterprise verwendet, um wichtige digitale Ressourcen in der gesamten Organisation zu klassifizieren, zu identifizieren und zu schützen.

## <a name="see-also"></a>Siehe auch

[Verwaltung mobiler Geräte für Microsoft 365 Enterprise](mobility-infrastructure.md)

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)

