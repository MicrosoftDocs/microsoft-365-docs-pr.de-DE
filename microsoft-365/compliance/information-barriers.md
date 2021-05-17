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
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051877"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Informationen zu Informationsbarrieren in Microsoft 365

Die Microsoft-Clouddienste umfassen leistungsfähige Funktionen für Kommunikation und Zusammenarbeit. Angenommen, Sie möchten die Kommunikation und Zusammenarbeit zwischen zwei Gruppen einschränken, um zu verhindern, dass in Ihrer Organisation ein Interessenkonflikt auftritt. Oder Sie möchten die Kommunikation und Zusammenarbeit zwischen bestimmten Personen innerhalb Ihrer Organisation einschränken, um interne Informationen zu schützen. Microsoft 365 ermöglicht die Kommunikation und Zusammenarbeit zwischen Gruppen und Organisationen. Gibt es also eine Möglichkeit, die Kommunikation und Zusammenarbeit zwischen bestimmten Benutzergruppen bei Bedarf einzuschränken? Mit Informationsbarrieren können Sie!

Microsoft Teams, SharePoint Online und OneDrive for Business unterstützen Informationsbarrieren. Vorausgesetzt, Ihr [Abonnement](#required-licenses-and-permissions) enthält Informationsbarrieren, kann ein Complianceadministrator oder Informationsbarrierenadministrator Richtlinien definieren, um die Kommunikation zwischen Benutzergruppen in Microsoft Teams zu ermöglichen oder zu verhindern. Richtlinien für Informationsbarrieren können für Situationen wie die folgenden verwendet werden:

- Benutzer der Händlergruppe am Tag sollte keine Dateien mit dem Marketingteam kommunizieren oder teilen
- Finanzmitarbeiter, die an vertraulichen Unternehmensinformationen arbeiten, sollten dateien nicht mit bestimmten Gruppen innerhalb ihrer Organisation kommunizieren oder freigeben.
- Ein internes Team mit Geheimmaterial sollte nicht online mit Personen in bestimmten Gruppen innerhalb ihrer Organisation anrufen oder chatten.
- Ein Forschungsteam sollte nur online mit einem Produktentwicklungsteam anrufen oder chatten
- Eine Website für Eine Tag-Händler-Gruppe sollte von niemandem außerhalb der Gruppe der Taghändler freigegeben oder darauf zugegriffen werden

> [!IMPORTANT]
> Informationsbarrieren ***unterstützen nur** _ Zwei-Wege-Einschränkungen. Eine Möglichkeit einschränkungen, z. B. Marketing kann kommunizieren und mit Tageshändlern zusammenarbeiten, aber Tageshändler können nicht kommunizieren und mit Marketing _* zusammenarbeiten wird _nicht_ unterstützt **.

Für alle diese Beispielszenarien (und mehr) können Richtlinien für Informationsbarrieren definiert werden, um Kommunikation und Zusammenarbeit in Microsoft Teams, SharePoint Online und OneDrive zu verhindern oder zu ermöglichen. Solche Richtlinien können verhindern, dass Personen mit Personen telefonieren oder chatten, die sie nicht sollten, oder personen können nur mit bestimmten Gruppen in Microsoft Teams kommunizieren. Wenn Richtlinien für Informationsbarrieren wirksam sind, werden Immer dann, wenn Benutzer, die von diesen Richtlinien abgedeckt werden, versuchen, mit anderen in Microsoft Teams zu kommunizieren und mit ihnen zusammenzuarbeiten, werden SharePoint Online- oder #A0 durchgeführt, um Kommunikation und Zusammenarbeit (gemäß Definition durch Richtlinien für Informationsbarrieren) zu verhindern (oder zu ermöglichen).

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter:

- [Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Informationsbarrieren in SharePoint Online](/sharepoint/information-barriers)
- [Informationsbarrieren in OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Derzeit gelten Informationsbarrieren nicht für die E-Mail-Kommunikation. Darüber hinaus sind Informationsbarrieren unabhängig von [Compliancegrenzen](set-up-compliance-boundaries.md).<p> Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, stellen Sie sicher, dass in Ihrer Organisation keine [Exchange-Adressbuchrichtlinien](/exchange/address-books/address-book-policies/address-book-policies) wirksam sind. (Informationsbarrieren basieren auf Adressbuchrichtlinien.)

## <a name="what-happens-with-information-barriers"></a>Was mit Informationsbarrieren geschieht

Wenn Richtlinien für Informationsbarrieren erstellt werden, können Personen, die keine Dateien mit anderen bestimmten Benutzern kommunizieren oder freigeben sollten, diese Benutzer nicht finden, auswählen, chatten oder anrufen. Mit Informationsbarrieren werden Prüfungen durchgeführt, um nicht autorisierte Kommunikation und Zusammenarbeit zu verhindern. 

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

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

In SharePoint Online und OneDrive bestimmen Und verhindern Richtlinien für Informationsbarrieren die folgenden Arten von nicht autorisierter Zusammenarbeit:

- Hinzufügen eines Mitglieds zu einer Website
- Zugreifen auf Website oder Inhalte durch einen Benutzer
- Freigeben von Website oder Inhalten für einen anderen Benutzer
- Durchsuchen einer Website

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Informationsbarrieren in SharePoint Online.](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Informationsbarrieren werden jetzt ins Rollen gebracht und sind in Abonnements enthalten, z. B.:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 Compliance E5/A5
- Microsoft 365 Insider Risk Management

Weitere Informationen finden Sie unter [Microsoft 365 Licensing Guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

Zum [Definieren oder Bearbeiten von Richtlinien](information-barriers-policies.md)für Informationsbarrieren müssen Ihnen eine der folgenden Rollen zugewiesen werden:

- Globaler Microsoft 365-Administrator
- Globaler Office 365-Administrator
- Complianceadministrator
- IB-Compliance-Management

(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).)

Sie müssen mit PowerShell-Cmdlets vertraut sein, um Richtlinien für Informationsbarrieren zu definieren, zu überprüfen oder zu bearbeiten. Obwohl wir im [How-to-Artikel](information-barriers-policies.md)mehrere Beispiele für PowerShell-Cmdlets bereitstellen, müssen Sie weitere Details wie Parameter für Ihre Organisation kennen.

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Weitere Informationen zu Informationsbarrieren in SharePoint Online](/sharepoint/information-barriers)
- [Weitere Informationen zu Informationsbarrieren in OneDrive](/onedrive/information-barriers)
- [Informationen zu den Attributen, die für Richtlinien für Informationsbarrieren verwendet werden können](information-barriers-attributes.md)
- [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)
- [Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)