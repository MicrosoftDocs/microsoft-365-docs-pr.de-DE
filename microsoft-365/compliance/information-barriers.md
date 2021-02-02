---
title: Informationen zu Informationsbarrieren in Microsoft 365
description: Verwenden Sie Informationsbarrieren, um die Kommunikationskonformität mithilfe von Microsoft Teams in Ihrer Organisation sicherzustellen.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 003347d46bed2529831a92681e73630d58a1f653
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071270"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Informationen zu Informationsbarrieren in Microsoft 365

Microsoft Cloud Services umfassen leistungsstarke Funktionen für Kommunikation und Zusammenarbeit. Angenommen, Sie möchten die Kommunikation und Zusammenarbeit zwischen zwei Gruppen einschränken, um ein Interessenkonflikt in Ihrer Organisation zu vermeiden. Oder Sie möchten die Kommunikation und Zusammenarbeit zwischen bestimmten Personen innerhalb Ihrer Organisation einschränken, um interne Informationen zu schützen. Microsoft 365 ermöglicht die Kommunikation und Zusammenarbeit zwischen Gruppen und Organisationen. Gibt es also eine Möglichkeit, die Kommunikation und Zusammenarbeit zwischen bestimmten Benutzergruppen bei Bedarf einzuschränken? Mit Informationsbarrieren können Sie!

Microsoft Teams, SharePoint Online und OneDrive for Business unterstützen Informationsbarrieren. Wenn Ihr [Abonnement](#required-licenses-and-permissions) Informationsbarrieren enthält, kann ein Complianceadministrator oder ein Administrator für Informationsbarrieren Richtlinien definieren, um die Kommunikation zwischen Benutzergruppen in Microsoft Teams zu ermöglichen oder zu verhindern. Richtlinien für Informationsbarrieren können in folgenden Situationen verwendet werden:

- Der Benutzer in der Gruppe "Tagesklasse" sollte keine Dateien mit dem Marketingteam kommunizieren oder mit ihm teilen.
- Finanzmitarbeiter, die an vertraulichen Unternehmensinformationen arbeiten, sollten keine Dateien mit bestimmten Gruppen innerhalb ihrer Organisation kommunizieren oder mit diesen teilen.
- Ein internes Team mit Material für das Handelsgeheimnis sollte nicht mit Personen in bestimmten Gruppen innerhalb ihrer Organisation anrufen oder mit ihnen chatten.
- Ein Forschungsteam sollte nur ein Produktentwicklungsteam anrufen oder online mit ihm chatten.
- Eine Website für eine Tagesgruppe sollte nicht von Personen außerhalb der Tagesgruppe freigegeben oder darauf zugegriffen werden.

> [!IMPORTANT]
> Informationsbarrieren ***unterstützen** nur _ Zwei-Wege-Einschränkungen. One way restrictions, such as marketing can communicate and collaborate with day traders, but day traders cannot communicate and collaborate with marketing _*_is not supported_**.

Für alle diese Beispielszenarien (und vieles mehr) können Richtlinien für Informationsbarrieren definiert werden, um die Kommunikation und Zusammenarbeit in Microsoft Teams, SharePoint Online und OneDrive zu verhindern oder zu ermöglichen. Solche Richtlinien können verhindern, dass Benutzer mit personen, die sie nicht sollten, anrufen oder chatten, oder personen können nur mit bestimmten Gruppen in Microsoft Teams kommunizieren. Wenn Richtlinien für Informationsbarrieren in Kraft sind, wenn Benutzer, die von diesen Richtlinien abgedeckt werden, versuchen, mit anderen in Microsoft Teams zu kommunizieren und mit ihnen zusammenzuarbeiten, werden SharePoint Online- oder #A0 durchgeführt, um Kommunikation und Zusammenarbeit (gemäß definition durch Richtlinien für Informationsbarrieren) zu verhindern (oder zu erlauben).

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter:

- [Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Informationsbarrieren in SharePoint Online](/sharepoint/information-barriers)
- [Informationsbarrieren in OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Derzeit gelten Informationsbarrieren nicht für die E-Mail-Kommunikation. Darüber hinaus sind Informationsbarrieren unabhängig von [Compliance-Grenzen.](set-up-compliance-boundaries.md)<p> Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, stellen Sie sicher, dass in Ihrer Organisation keine Richtlinien für das [Exchange-Adressbuch](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) wirksam sind. (Informationsbarrieren basieren auf Adressbuchrichtlinien.)

## <a name="what-happens-with-information-barriers"></a>Was mit Informationsbarrieren geschieht

Wenn Richtlinien für Informationsbarrieren verwendet werden, können Personen, die nicht mit anderen Benutzern kommunizieren oder Dateien für andere Benutzer freigeben sollten, diese Benutzer nicht finden, auswählen, chatten oder anrufen. Mit Informationsbarrieren werden Prüfungen durchgeführt, um nicht autorisierte Kommunikation und Zusammenarbeit zu verhindern. 

Informationsbarrieren gelten für Microsoft Teams (Chats und Kanäle), SharePoint Online und OneDrive. Richtlinien für Informationsbarrieren ermitteln in Microsoft Teams die folgenden Arten von nicht autorisierter Kommunikation:

- Nach einem Benutzer suchen
- Hinzufügen eines Mitglieds zu einem Team
- Starten einer Chatsitzung mit einer anderen Person
- Starten eines Gruppen-Chats
- Einladen einer Person zur Teilnahme an einer Besprechung
- Freigeben eines Bildschirms
- Tätigen eines Anrufs
- Freigeben einer Datei für einen anderen Benutzer
- Zugriff auf Datei über Freigabelink

Wenn für die beteiligten Personen eine Richtlinie für Informationsbarrieren gilt, die diese Aktivität untersagt, können sie damit nicht fortfahren. Potenziell kann außerdem jede Person, für die eine Richtlinie für Informationsbarrieren gilt, daran gehindert werden, mit anderen Personen in Microsoft Teams zu kommunizieren. Personen, die von Richtlinien für Informationsbarrieren betroffen sind und die Teilnehmer desselben Teams- oder Gruppenchats sind, werden möglicherweise aus diesen Chatsitzungen entfernt, und die weitere Kommunikation mit der Gruppe ist u. U. nicht zulässig.

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Informationsbarrieren in Microsoft Teams.](/MicrosoftTeams/information-barriers-in-teams)

In SharePoint Online und OneDrive bestimmen und verhindern Richtlinien für Informationsbarrieren die folgenden Arten von nicht autorisierten Zusammenarbeiten:

- Hinzufügen eines Mitglieds zu einer Website
- Zugreifen auf Website oder Inhalt durch einen Benutzer
- Freigeben von Website oder Inhalten für einen anderen Benutzer
- Durchsuchen einer Website

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Informationsbarrieren in SharePoint Online.](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Informationsbarrieren werden jetzt ins Rollen gebracht und sind in Abonnements enthalten, z. B.:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 Compliance E5/A5
- Microsoft 365 Insider Risk Management

Weitere Informationen finden Sie unter [Microsoft 365-Lizenzierungsanleitungen für & Compliance.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

Zum [Definieren oder Bearbeiten von](information-barriers-policies.md)Richtlinien für Informationsbarrieren muss Ihnen eine der folgenden Rollen zugewiesen sein:

- Globaler Microsoft 365-Administrator
- Globaler Office 365-Administrator
- Complianceadministrator
- IB-Compliance-Management

(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter "Berechtigungen" im [Office 365 Security & Compliance Center.)](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

Sie müssen mit den PowerShell-Cmdlets vertraut sein, um Richtlinien für Informationsbarrieren zu definieren, zu überprüfen oder zu bearbeiten. Obwohl wir im Artikel "Gewusst wie" [](information-barriers-policies.md)mehrere Beispiele für PowerShell-Cmdlets bereitstellen, müssen Sie andere Details für Ihre Organisation kennen, z. B. Parameter.

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Weitere Informationen zu Informationsbarrieren in SharePoint Online](/sharepoint/information-barriers)
- [Weitere Informationen zu Informationsbarrieren in OneDrive](/onedrive/information-barriers)
- [Informationen zu den Attributen, die für Richtlinien für Informationsbarrieren verwendet werden können](information-barriers-attributes.md)
- [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)
- [Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)