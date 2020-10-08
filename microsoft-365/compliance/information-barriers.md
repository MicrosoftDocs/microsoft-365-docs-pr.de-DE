---
title: Erfahren Sie mehr über Informationsbarrieren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
description: Verwenden Sie Informationsbarrieren, um die Kommunikation mit Microsoft Teams in Ihrer Organisation sicherzustellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7b223de8eba68d49a8cc0c90239305eb05bb1090
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379189"
---
# <a name="information-barriers"></a>Informationsbarrieren

Microsoft Cloud Services umfassen leistungsstarke Funktionen für Kommunikation und Zusammenarbeit. Angenommen, Sie möchten die Kommunikation und Zusammenarbeit zwischen zwei Gruppen einschränken, um zu verhindern, dass in Ihrer Organisation ein Interessenkonflikt auftritt. Oder vielleicht möchten Sie die Kommunikation und Zusammenarbeit zwischen bestimmten Personen innerhalb Ihrer Organisation einschränken, um interne Informationen zu schützen. Microsoft 365 ermöglicht die Kommunikation und Zusammenarbeit zwischen Gruppen und Organisationen, gibt es also die Möglichkeit, die Kommunikation und Zusammenarbeit bei Bedarf auf bestimmte Benutzergruppen einzuschränken? Mit Informationsbarrieren, können Sie! 

Informationsbarrieren werden jetzt in Microsoft Teams, SharePoint Online und OneDrive für Unternehmen unterstützt. Unter der Voraussetzung, dass Ihr [Abonnement](#required-licenses-and-permissions) Informationsbarrieren enthält, kann ein Compliance-Administrator oder ein Administrator für Informationsbarrieren Richtlinien definieren, um die Kommunikation zwischen Benutzergruppen in Microsoft Teams zu ermöglichen oder zu verhindern. Richtlinien für Informationsbarrieren können für Situationen wie diese verwendet werden:

- Benutzer in der Day Trader-Gruppe sollten keine Dateien mit dem Marketing Team kommunizieren oder freigeben
- Finanz Personal, das an vertraulichen Unternehmensinformationen arbeitet, sollte keine Dateien mit bestimmten Gruppen innerhalb Ihrer Organisation kommunizieren oder freigeben
- Ein internes Team mit Geschäfts geheimem Material sollte nicht online mit Personen in bestimmten Gruppen innerhalb Ihrer Organisation anrufen oder chatten.
- Ein Forschungsteam sollte nur online mit einem Produktentwicklungsteam anrufen oder chatten

> [!IMPORTANT]
> Informationsbarrieren ***unterstützen nur*** zwei-Wege-Einschränkungen. Unidirektionale Einschränkungen wie Marketing können mit Day Traders kommunizieren, aber Day Trader können nicht mit Marketing kommunizieren ***wird nicht unterstützt***.

Für alle diese Beispielszenarien (und mehr) können Richtlinien für Informationsbarrieren definiert werden, um die Kommunikation in Microsoft Teams zu verhindern oder zuzulassen. Mithilfe solcher Richtlinien kann verhindert werden, dass Personen Anrufe oder Chats mit Personen durchlaufen, die Sie nicht haben sollten, oder dass Personen nur mit bestimmten Gruppen in Microsoft Teams kommunizieren können. Wenn die Richtlinien für Informationsbarrieren wirksam sind und Benutzer, die von diesen Richtlinien abgedeckt werden, versuchen, mit anderen Personen in Microsoft Teams zu kommunizieren, werden Überprüfungen durchgeführt, um die Kommunikation zu verhindern (oder zulassen) (gemäß den Richtlinien für Informationsbarrieren). Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Information Barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!IMPORTANT]
> Derzeit gelten Informationsbarrieren nicht für e-Mail-Kommunikation. Darüber hinaus sind Informationsbarrieren unabhängig von [Compliance-Grenzen](set-up-compliance-boundaries.md).<p>Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, müssen Sie sicherstellen, dass in Ihrer Organisation keine [Exchange-adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) wirksam sind. (Informationsbarrieren basieren auf adressbuchrichtlinien.) 

## <a name="what-happens-with-information-barriers"></a>Was geschieht mit Informationsbarrieren?

Wenn Richtlinien für Informationsbarrieren vorhanden sind, können Personen, die keine Dateien kommunizieren oder mit anderen bestimmten Benutzern teilen möchten, diese Benutzer nicht finden, auswählen, chatten oder anrufen. Bei Informationsbarrieren werden Überprüfungen durchgeführt, um unbefugte Kommunikation zu verhindern.

Anfänglich gelten Informationsbarrieren nur für Chats und Kanäle von Microsoft Teams. Richtlinien für Informationsbarrieren ermitteln in Microsoft Teams die folgenden Arten von nicht autorisierter Kommunikation:

- Nach einem Benutzer suchen
- Hinzufügen eines Mitglieds zu einem Team
- Starten einer Chatsitzung mit einer anderen Person
- Starten eines Gruppen-Chats
- Einladen einer Person zur Teilnahme an einer Besprechung
- Freigeben eines Bildschirms
- Tätigen eines Anrufs
- Freigeben einer Datei für einen anderen Benutzer
- Zugriff auf Datei über Freigabe Link 

Wenn für die beteiligten Personen eine Richtlinie für Informationsbarrieren gilt, die diese Aktivität untersagt, können sie damit nicht fortfahren. Potenziell kann außerdem jede Person, für die eine Richtlinie für Informationsbarrieren gilt, daran gehindert werden, mit anderen Personen in Microsoft Teams zu kommunizieren. Personen, die von Richtlinien für Informationsbarrieren betroffen sind und die Teilnehmer desselben Teams- oder Gruppenchats sind, werden möglicherweise aus diesen Chatsitzungen entfernt, und die weitere Kommunikation mit der Gruppe ist u. U. nicht zulässig.

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Information Barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Informationsbarrieren werden jetzt ausgerollt und in Abonnements eingeschlossen, beispielsweise:

- Microsoft 365 E5/a5
- Office 365 E5/a5
- Office 365 Advanced Compliance
- Microsoft 365 Compliance E5/a5
- Microsoft 365 Insider Risk Management

Weitere Informationen finden Sie unter [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

Um [Richtlinien für Informationsbarrieren zu definieren oder zu bearbeiten](information-barriers-policies.md), muss Ihnen eine der folgenden Rollen zugewiesen sein:

- Globaler Microsoft 365-Administrator
- Globaler Office 365-Administrator
- Complianceadministrator
- IB-Konformitätsverwaltung (Dies ist eine neue Rolle!)

(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)

Sie müssen mit PowerShell-Cmdlets vertraut sein, um Richtlinien für Informationsbarrieren zu definieren, zu validieren oder zu bearbeiten. Obwohl wir einige Beispiele für PowerShell-Cmdlets im [How-to-Artikel](information-barriers-policies.md)bereitstellen, müssen Sie zusätzliche Details wie Parameter für Ihre Organisation kennen.

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Informationsbarrieren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [Siehe die Attribute, die für Richtlinien für Informationsbarrieren verwendet werden können.](information-barriers-attributes.md)
- [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)
- [Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)
- [Weitere Informationen zu Informationsbarrieren in SharePoint Online](https://docs.microsoft.com/sharepoint/information-barriers)
- [Weitere Informationen zu Informationsbarrieren in OneDrive für Unternehmen](https://docs.microsoft.com/onedrive/information-barriers)