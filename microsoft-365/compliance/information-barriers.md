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
ms.openlocfilehash: 6ca1502c16accc0d9d9c0453e407eadaeb4c12e5
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980068"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Informationen zu Informationsbarrieren in Microsoft 365

Microsoft Cloud Services umfassen leistungsstarke Funktionen für Kommunikation und Zusammenarbeit. Angenommen, Sie möchten die Kommunikation und Zusammenarbeit zwischen zwei Gruppen einschränken, um ein Interessenkonflikt in Ihrer Organisation zu vermeiden. Oder Sie möchten die Kommunikation und Zusammenarbeit zwischen bestimmten Personen innerhalb Ihrer Organisation einschränken, um interne Informationen zu schützen. Microsoft 365 ermöglicht die Kommunikation und Zusammenarbeit zwischen Gruppen und Organisationen. Gibt es also eine Möglichkeit, die Kommunikation und Zusammenarbeit zwischen bestimmten Benutzergruppen bei Bedarf einzuschränken? Mit Informationsbarrieren können Sie!

Microsoft Teams, SharePoint Online und OneDrive for Business unterstützen Informationsbarrieren. Wenn Ihr [Abonnement](#required-licenses-and-permissions) Informationsbarrieren enthält, kann ein Complianceadministrator oder ein Administrator für Informationsbarrieren Richtlinien definieren, um die Kommunikation zwischen Benutzergruppen in Microsoft Teams zu ermöglichen oder zu verhindern. Richtlinien für Informationsbarrieren können in folgenden Situationen verwendet werden:

- Der Benutzer in der Gruppe "Tagesklasse" sollte keine Dateien mit dem Marketingteam kommunizieren oder mit ihm teilen.
- Finanzmitarbeiter, die an vertraulichen Unternehmensinformationen arbeiten, sollten keine Dateien mit bestimmten Gruppen innerhalb ihrer Organisation kommunizieren oder mit diesen teilen.
- Ein internes Team mit Material für das Handelsgeheimnis sollte nicht mit Personen in bestimmten Gruppen innerhalb ihrer Organisation anrufen oder mit ihnen chatten.
- Ein Forschungsteam sollte nur ein Produktentwicklungsteam anrufen oder online mit ihm chatten.

> [!IMPORTANT]
> Informationsbarrieren ***unterstützen** nur _ Zwei-Wege-Einschränkungen. One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing _*_is not supported_**.

Für alle diese Beispielszenarien (und vieles mehr) können Richtlinien für Informationsbarrieren definiert werden, um die Kommunikation in Microsoft Teams zu verhindern oder zu erlauben. Solche Richtlinien können verhindern, dass Benutzer mit diesen Personen anrufen oder chatten, die sie nicht verwenden sollten, oder Personen die Kommunikation nur mit bestimmten Gruppen in Microsoft Teams ermöglichen. Wenn Richtlinien für Informationsbarrieren in Kraft sind, werden bei jedem Versuch von Benutzern, die von diesen Richtlinien abgedeckt werden, mit anderen in Microsoft Teams zu kommunizieren, Prüfungen durchgeführt, um die Kommunikation zu verhindern (oder zu erlauben), wie durch Richtlinien für Informationsbarrieren definiert). Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Informationsbarrieren in Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

> [!IMPORTANT]
> Derzeit gelten Informationsbarrieren nicht für die E-Mail-Kommunikation. Darüber hinaus sind Informationsbarrieren unabhängig von [Compliance-Grenzen.](set-up-compliance-boundaries.md)<p> Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, stellen Sie sicher, dass in Ihrer Organisation keine Richtlinien für das [Exchange-Adressbuch](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) wirksam sind. (Informationsbarrieren basieren auf Adressbuchrichtlinien.)

## <a name="what-happens-with-information-barriers"></a>Was mit Informationsbarrieren geschieht

Wenn Richtlinien für Informationsbarrieren verwendet werden, können Personen, die nicht mit anderen Benutzern kommunizieren oder Dateien für andere Benutzer freigeben sollten, diese Benutzer nicht finden, auswählen, chatten oder anrufen. Bei Informationsbarrieren werden Überprüfungen durchgeführt, um unbefugte Kommunikation zu verhindern.

Anfänglich gelten Informationsbarrieren nur für Microsoft Teams-Chats und -Kanäle. Richtlinien für Informationsbarrieren ermitteln in Microsoft Teams die folgenden Arten von nicht autorisierter Kommunikation:

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

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Informationsbarrieren in Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

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

- [Weitere Informationen zu Informationsbarrieren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [Informationen zu den Attributen, die für Richtlinien für Informationsbarrieren verwendet werden können](information-barriers-attributes.md)
- [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)
- [Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)
- [Weitere Informationen zu Informationsbarrieren in SharePoint Online](https://docs.microsoft.com/sharepoint/information-barriers)
- [Weitere Informationen zu Informationsbarrieren in OneDrive for Business](https://docs.microsoft.com/onedrive/information-barriers)