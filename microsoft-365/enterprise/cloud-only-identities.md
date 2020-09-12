---
title: Microsoft 365 Cloud-only Identity
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
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
ms.openlocfilehash: 6ec727ea3648f1daa3af42763e5f497715b987a2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547758"
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

Sie erstellen neue ***Benutzer*** mit:

- [Das Microsoft 365 Admin Center](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [PowerShell für Microsoft 365](create-user-accounts-with-microsoft-365-powershell.md)

Sie erstellen neue ***Gruppen*** mit:

- [Das Microsoft 365 Admin Center](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [PowerShell für Microsoft 365](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a>Nächster Schritt für Cloud-only Identity

[Zuweisen von Lizenzen zu Benutzerkonten](assign-licenses-to-user-accounts.md)
