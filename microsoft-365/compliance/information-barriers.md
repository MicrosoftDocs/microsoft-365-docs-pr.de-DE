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
localization_priority: None
description: Verwenden Sie Informationsbarrieren, um die Kommunikation mit Microsoft Teams in Ihrer Organisation sicherzustellen.
ms.openlocfilehash: 341c4f54ac48cbebd17b8d9ded267091f098dcbd
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232008"
---
# <a name="information-barriers"></a>Informationsbarrieren

## <a name="overview"></a>Übersicht

Microsoft Cloud Services umfassen leistungsstarke Funktionen für Kommunikation und Zusammenarbeit. Angenommen, Sie möchten die Kommunikation zwischen zwei Gruppen einschränken, um zu verhindern, dass in Ihrer Organisation ein Interessenkonflikt auftritt. Oder Sie möchten möglicherweise die Kommunikation zwischen bestimmten Personen innerhalb Ihrer Organisation einschränken, um interne Informationen zu schützen. Microsoft 365 ermöglicht die Kommunikation und Zusammenarbeit zwischen Gruppen und Organisationen, gibt es also eine Möglichkeit, die Kommunikation zwischen bestimmten Benutzergruppen einzuschränken, wenn dies erforderlich ist? Mit Informationsbarrieren, können Sie! 

Informationsbarrieren werden jetzt, beginnend mit Microsoft Teams, ausgerollt. Unter der Voraussetzung, dass Ihr [Abonnement](#required-licenses-and-permissions) Informationsbarrieren enthält, kann ein Compliance-Administrator oder ein Administrator für Informationsbarrieren Richtlinien definieren, um die Kommunikation zwischen Benutzergruppen in Microsoft Teams zu ermöglichen oder zu verhindern. Richtlinien für Informationsbarrieren können für Situationen wie diese verwendet werden:

- Benutzer in der Day Trader-Gruppe sollten nicht mit dem Marketing Team kommunizieren
- Finanz Personal, das an vertraulichen Unternehmensinformationen arbeitet, sollte nicht mit bestimmten Gruppen innerhalb Ihrer Organisation kommunizieren.
- Ein internes Team mit Geschäfts geheimem Material sollte nicht online mit Personen in bestimmten Gruppen innerhalb Ihrer Organisation anrufen oder chatten.
- Ein Forschungsteam sollte nur online mit einem Produktentwicklungsteam anrufen oder chatten

> [!IMPORTANT]
> Informationsbarrieren ***unterstützen nur*** zwei-Wege-Einschränkungen. Unidirektionale Einschränkungen wie Marketing können mit Day Traders kommunizieren, aber Day Trader können nicht mit Marketing kommunizieren ***wird nicht unterstützt***.

Für alle diese Beispielszenarien (und mehr) können Richtlinien für Informationsbarrieren definiert werden, um die Kommunikation in Microsoft Teams zu verhindern oder zuzulassen. Mithilfe solcher Richtlinien kann verhindert werden, dass Personen Anrufe oder Chats mit Personen durchlaufen, die Sie nicht haben sollten, oder dass Personen nur mit bestimmten Gruppen in Microsoft Teams kommunizieren können. Wenn die Richtlinien für Informationsbarrieren wirksam sind und Benutzer, die von diesen Richtlinien abgedeckt werden, versuchen, mit anderen Personen in Microsoft Teams zu kommunizieren, werden Überprüfungen durchgeführt, um die Kommunikation zu verhindern (oder zulassen) (gemäß den Richtlinien für Informationsbarrieren). Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Information Barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

> [!IMPORTANT]
> Derzeit gelten Informationsbarrieren nicht für e-Mail-Kommunikationen oder für die Dateifreigabe über SharePoint Online oder OneDrive. Darüber hinaus sind Informationsbarrieren unabhängig von [Compliance-Grenzen](set-up-compliance-boundaries.md).<p>Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, müssen Sie sicherstellen, dass in Ihrer Organisation keine [Exchange-adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) wirksam sind. (Informationsbarrieren basieren auf adressbuchrichtlinien.) 

## <a name="what-happens-with-information-barriers"></a>Was geschieht mit Informationsbarrieren?

Wenn Richtlinien für Informationsbarrieren vorhanden sind, können Personen, die nicht mit anderen bestimmten Benutzern kommunizieren sollten, diese Benutzer nicht finden, auswählen, chatten oder anrufen. Mit Informationsbarrieren sind Überprüfungen vorhanden, um eine unbefugte Kommunikation zu verhindern.

Anfänglich gelten Informationsbarrieren nur für Chats und Kanäle von Microsoft Teams. In Microsoft Teams bestimmen und verhindern Richtlinien für Informationsbarrieren die folgenden Arten von nicht autorisierter Kommunikation:
- Suchen nach einem Benutzer
- Hinzufügen eines Mitglieds zu einem Team
- Starten einer Chatsitzung mit einer Person
- Starten eines Gruppenchats
- Einladen von Personen zum teilnehmen an einer Besprechung
- Freigeben eines Bildschirms
- Platzieren eines Anrufs 

Wenn die beteiligten Personen in eine Informations Sperrrichtlinie einbezogen werden, um die Aktivität zu verhindern, können Sie nicht fortfahren. Darüber hinaus kann potenziell jeder, der in eine Richtlinie für Informationsbarrieren eingeschlossen ist, für die Kommunikation mit anderen Personen in Microsoft Teams gesperrt werden. Wenn Personen, die von Richtlinien für Informationsbarrieren betroffen sind, Teil desselben Teams oder Gruppenchats sind, werden Sie möglicherweise aus diesen Chatsitzungen entfernt, und die weitere Kommunikation mit der Gruppe ist möglicherweise nicht zulässig.

Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Information Barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Informationsbarrieren werden jetzt ausgerollt und in Abonnements eingeschlossen, beispielsweise:

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Microsoft 365 Compliance E5

Weitere Informationen finden Sie unter [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

Um [Richtlinien für Informationsbarrieren zu definieren oder zu bearbeiten](information-barriers-policies.md), muss Ihnen eine der folgenden Rollen zugewiesen sein:

- Microsoft 365 globaler Administrator
- Office 365 globaler Administrator
- Complianceadministrator
- IB-Konformitätsverwaltung (Dies ist eine neue Rolle!)

(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)

Sie müssen mit PowerShell-Cmdlets vertraut sein, um Richtlinien für Informationsbarrieren zu definieren, zu validieren oder zu bearbeiten. Obwohl wir einige Beispiele für PowerShell-Cmdlets im [How-to-Artikel](information-barriers-policies.md)bereitstellen, müssen Sie zusätzliche Details wie Parameter für Ihre Organisation kennen.

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Informationsbarrieren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [Siehe die Attribute, die für Richtlinien für Informationsbarrieren verwendet werden können.](information-barriers-attributes.md)

- [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)

- [Bearbeiten (oder entfernen) von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md) 
