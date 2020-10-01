---
title: Microsoft 365 Cloud-only Identity
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Benutzer und Gruppen erstellt werden, wenn Ihr Microsoft 365-Abonnement nur eine Cloud-Identität verwendet.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327927"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365 Cloud-only Identity

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Bei der reinen cloudbasierten Identität werden alle Ihre Benutzer, Gruppen und Kontakte im Azure Active Directory (Azure AD)-Mandanten Ihres Microsoft 365-Abonnements gespeichert. Hier sind die grundlegenden Komponenten der reinen Cloudidentität.
 
![Die grundlegenden Komponenten von Cloud-only Identity](../media/about-microsoft-365-identity/cloud-only-identity.png)

Benutzer und ihre Benutzerkonten in Organisationen können auf verschiedene Arten kategorisiert werden. Einige sind beispielsweise Mitarbeiter und haben einen permanenten Status. Bei einigen handelt es sich um Kreditoren, Auftragnehmer oder Partner mit einem temporären Status. Einige sind externe Benutzer, die über keine Benutzerkonten verfügen, aber weiterhin Zugriff auf bestimmte Dienste und Ressourcen für die Unterstützung von Interaktion und Zusammenarbeit erhalten müssen. Beispiel:

- Mandantenkonten stellen Benutzer in Ihrem Unternehmen dar, die Sie für Clouddienste lizenzieren.

- Business-to-Business(B2B)-Konten stellen Benutzer außerhalb Ihres Unternehmens dar, die Sie zur Zusammenarbeit einladen.

Übernehmen Sie eine Bestandsaufnahme der Benutzertypen in Ihrer Organisation. Was sind die Gruppierungen? Beispielsweise können Sie Benutzer nach allgemeinen Funktionen oder Zweck in Ihrer Organisation gruppieren.

Darüber hinaus können einige Clouddienste für Benutzer außerhalb Ihres Unternehmens ohne Benutzerkonten freigegeben werden. Sie müssen diese Benutzergruppen ebenfalls identifizieren.

Sie können Gruppen in Azure AD für verschiedene Zwecke verwenden, die die Verwaltung Ihrer Cloud-Umgebung vereinfachen. Beispielsweise können Sie mit Azure Ad Gruppen Folgendes tun:

- Verwenden Sie Gruppenbasierte Lizenzierungen, um Ihren Benutzerkonten automatisch Lizenzen für Microsoft 365 zuzuweisen, sobald diese als Mitglieder hinzugefügt werden.
- Hinzufügen von Benutzerkonten zu bestimmten Gruppen dynamisch basierend auf Benutzerkonto Attributen wie Abteilungsname.
- Automatische Bereitstellung von Benutzern für Software as a Service (SaaS)-Anwendungen und zum Schutz des Zugriffs auf diese Anwendungen mit mehrstufiger Authentifizierung (MFA) und anderen Richtlinien für bedingten Zugriff.
- Bereitstellungsberechtigungen und Zugriffsebenen für SharePoint Online Teamwebsites.

## <a name="next-steps-for-cloud-only-identity"></a>Nächste Schritte für Cloud-only Identity

- [Verwalten von Benutzerkonten](manage-microsoft-365-accounts.md)
- [Zuweisen von Lizenzen zu Benutzerkonten](assign-licenses-to-user-accounts.md)
- [Verwalten von Gruppen und Gruppenmitgliedschaften](manage-microsoft-365-groups.md)
- [Verwalten von Kennwörtern für Benutzerkonten](manage-microsoft-365-passwords.md)
