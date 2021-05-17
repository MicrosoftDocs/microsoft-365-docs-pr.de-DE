---
title: Planen der Organisations- und Lebenszyklussteuerung für Microsoft 365 gruppen und Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lean about lifecycle governance options for collaboration tools in Microsoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907928"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planen der Organisations- und Lebenszyklussteuerung für Microsoft 365 gruppen und Microsoft Teams

Microsoft 365 gruppen verfügt über eine reihe von Tools, um die Governancefunktionen zu implementieren, die Ihre Organisation benötigt. 

Der folgende Abschnitt beschreibt die Möglichkeiten, empfiehlt bewährte Methoden und gibt Hinweise, wie die richtigen Fragen gestellt werden können, um die Anforderungen an die Governance zu bestimmen und wie diese erfüllt werden können.

## <a name="control-who-can-create-microsoft-365-groups"></a>Steuern, wer benutzergruppen Microsoft 365 kann

Gruppen können von Endbenutzern aus mehreren Endpunkten erstellt werden, einschließlich Outlook, SharePoint, Teams und anderen Umgebungen.

![Bildbeschreibung](../media/04.png)

Wir empfehlen dringend Self-Service, um Gruppenbesitzer zu unterstützen und Benutzern zu helfen, ihre Arbeit einfacher zu erledigen. Das Einschränken der Gruppen- und Teamerstellung kann die Produktivität der Benutzer beeinträchtigen, da viele Microsoft 365 erfordern, dass Gruppen erstellt werden, damit der Dienst funktioniert.

Berücksichtigen Sie die folgenden Steuerungsoptionen für die Gruppenerstellung:

- Verwenden Sie zum Einschränken der Gruppensprawlung [Ablaufrichtlinien](microsoft-365-groups-expiration-policy.md) für Gruppen, um nicht verwendete Gruppen automatisch zu löschen.
- Beschränken Sie die Gruppenerstellung auf Mitglieder einer [Sicherheitsgruppe](/azure/active-directory/users-groups-roles/groups-create-rule) mit dynamischer Mitgliedschaft, die z. B. alle Vollzeitmitarbeiter enthält.
- Beschränken Sie die Gruppenerstellung auf eine Sicherheitsgruppe, und fordern Sie, dass Benutzer Schulungen in den Gruppenverwendungsrichtlinien Ihrer Organisation abschließen müssen, um Mitglied der Sicherheitsgruppe zu werden.

Wenn Sie einschränken möchten, wer Gruppen erstellen kann, finden Sie unter [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) weitere Informationen zur Konfiguration dieser Gruppe.

## <a name="group-delete-restore-and-archiving"></a>Gruppenlöschen, Wiederherstellen und Archivierung

Wenn eine Microsoft 365 gelöscht wird, wird sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe immer noch wiederherstellen können. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

Wenn Aufbewahrungsrichtlinien zum Beibehalten von Chats, Dateien oder E-Mails erstellt wurden, werden diese Elemente beibehalten, nachdem die Gruppe gelöscht wurde. Weitere [Informationen finden Sie unter Informationen](../compliance/retention.md) zu Aufbewahrungsrichtlinien.

Wenn Sie eine Gruppe löschen möchten, aber den Inhalt aus einem oder mehreren der mit einer Gruppe verbundenen Dienste beibehalten möchten, finden Sie weitere Informationen unter Archivieren von [Gruppen,](end-life-cycle-groups-teams-sites-yammer.md) Teams und Yammer Informationen.

## <a name="group-naming-policy"></a>Gruppenbenennungsrichtlinie

Eine Gruppenbenennungsrichtlinie kann Ihnen dabei helfen, Gruppen auf zwei Arten zu steuern:

- Eine Präfix-/Suffixbenennungsrichtlinie kann verwendet werden, um feste Zeichenfolgen oder Azure AD-Attribute am Anfang oder Ende eines Gruppennamens und der zugehörigen E-Mail-Adresse zu erzwingen. Auf diese Art können Sie sicherstellen, dass beispielsweise Abteilungsnamen oder Regionen in Gruppennamen enthalten sind.
- Eine Richtlinie für blockierte Wörter kann sicherstellen, dass bestimmte Wörter, z. B. die Namen von Führungskräften, nicht in Gruppennamen verwendet werden.

Benennungsrichtlinien werden angewendet, wenn Gruppen aus einem der mit einer Gruppe verbundenen Dienste erstellt werden.

Wenn Sie sich für die Verwendung von Benennungsrichtlinien für Gruppen entscheiden, lesen Sie [Microsoft 365 Namensrichtlinie für Gruppen](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Gruppenablaufrichtlinie

Sie können einen Ablaufzeitraum angeben, und alle Gruppen, die das Ende dieses Zeitraums erreichen und nicht verlängert werden, werden gelöscht. Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung.

Sobald Sie festgelegt haben, dass Gruppen ablaufen:
- Besitzer der Gruppe werden benachrichtigt, die Gruppe zu verlängern, sobald sich der Ablauf nähert.
- Aktive Gruppen werden automatisch erneuert.
- Alle nicht verlängerten Gruppen werden gelöscht.
- Alle gelöschten Gruppen können von den Gruppenbesitzern oder dem Administrator innerhalb von 30 Tagen wiederhergestellt werden.

Ablaufrichtlinien sind eine gute Möglichkeit, die Zersiedelung von Gruppen zu begrenzen, indem sichergestellt wird, dass nicht mehr verwendete Gruppen gelöscht werden. Wenn Sie eine Gruppenablaufrichtlinie erstellen möchten, lesen Sie [Microsoft 365 Gruppenablaufrichtlinie](microsoft-365-groups-expiration-policy.md).

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)