---
title: Planen der Organisations-und Lebenszyklus-Steuerung für Microsoft 365-Gruppen und Microsoft Teams
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lean about Lifecycle Governance-Optionen für Tools für die Zusammenarbeit in Microsoft 365
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662641"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planen der Organisations-und Lebenszyklus-Steuerung für Microsoft 365-Gruppen und Microsoft Teams

Microsoft 365 Groups verfügt über eine umfangreiche Reihe von Tools zum Implementieren der Steuerungsfunktionen, die Ihre Organisation benötigt. 

Der folgende Abschnitt beschreibt die Möglichkeiten, empfiehlt bewährte Methoden und gibt Hinweise, wie die richtigen Fragen gestellt werden können, um die Anforderungen an die Governance zu bestimmen und wie diese erfüllt werden können.

## <a name="control-who-can-create-microsoft-365-groups"></a>Steuern der Benutzer, die Microsoft 365-Gruppen erstellen können

Gruppen können von Endbenutzern aus mehreren Endpunkten einschließlich Outlook, SharePoint, Teams und anderen Umgebungen erstellt werden.

![Bildbeschreibung](../media/04.png)

Self-Service wird dringend empfohlen, um Gruppenbesitzer zu bevollmächtigen und Benutzern zu helfen, ihre Arbeit leichter erledigen zu lassen. Das Einschränken der Gruppen-und TEAMERSTELLUNG kann die Produktivität der Benutzer verlangsamen, da viele Microsoft 365-Dienste die Erstellung von Gruppen für den Dienst erfordern.

Die folgenden Steuerungsoptionen für die Gruppenerstellung sollten beachtet werden:

- Verwenden Sie zum Begrenzen der Gruppen Zersiedelung Gruppen [Ablaufrichtlinien](microsoft-365-groups-expiration-policy.md) , um Gruppen automatisch zu löschen, die nicht verwendet werden.
- Beschränken Sie die Gruppenerstellung auf Mitglieder einer [Sicherheitsgruppe mit einer dynamischen Mitgliedschaft](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) , die beispielsweise alle Vollzeitmitarbeiter enthält.
- Beschränken Sie die Gruppenerstellung auf eine Sicherheitsgruppe, und fordern Sie die Benutzer auf, Schulungen in den Gruppen Nutzungsrichtlinien Ihrer Organisation durchzuführen, um Mitglieder der Sicherheitsgruppe zu werden.

Wenn Sie einschränken möchten, wer Gruppen erstellen kann, finden Sie weitere Informationen zum Konfigurieren dieses Themas unter [Manage who can create Microsoft 365 Groups](manage-creation-of-groups.md) .

## <a name="group-delete-restore-and-archiving"></a>Löschen, wiederherstellen und Archivieren von Gruppen

Wenn eine Microsoft 365-Gruppe gelöscht wird, wird Sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als "vorläufiges Löschen" bezeichnet, weil Sie die Gruppe immer noch wiederherstellen können. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

Wenn Aufbewahrungsrichtlinien vorhanden sind, um Chat, Dateien oder e-Mail beizubehalten, werden diese Elemente nach dem Löschen der Gruppe beibehalten. Weitere Informationen finden Sie unter [erfahren Sie mehr über Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) .

Wenn Sie eine Gruppe löschen, aber den Inhalt von einem oder mehreren der Gruppen verbundenen Dienste beibehalten möchten, finden Sie weitere Informationen unter [Archivieren von Gruppen, Teams und jammern](end-life-cycle-groups-teams-sites-yammer.md) .

## <a name="group-naming-policy"></a>Gruppenbenennungsrichtlinie

Mithilfe einer Benennungsrichtlinie für Gruppen können Sie Gruppen auf zwei Arten steuern:

- Eine Namensrichtlinie für Präfix/Suffix kann verwendet werden, um feste Zeichenfolgen oder Azure AD Attribute am Anfang oder Ende eines Gruppennamens und der zugehörigen e-Mail-Adresse zu erzwingen. Auf diese Weise können Sie sicherstellen, dass z. b. Abteilungsnamen oder Regionen in Gruppennamen eingeschlossen werden.
- Eine Richtlinie für blockierte Wörter kann sicherstellen, dass bestimmte Wörter wie die Namen von Führungskräften nicht in Gruppennamen verwendet werden.

Benennungsrichtlinien werden angewendet, wenn Gruppen von einem der Gruppen verbundenen Dienste erstellt werden.

Wenn Sie sich für die Verwendung von Benennungsrichtlinien für Gruppen entscheiden, lesen Sie die [Benennungsrichtlinie für Microsoft 365-Gruppen](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Gruppenablaufrichtlinie

Sie können einen Ablaufzeitraum angeben, und jede Gruppe, die das Ende dieses Zeitraums erreicht und nicht erneuert wird, wird gelöscht. Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung.

Nachdem Sie Gruppen so festgelegt haben, dass Sie ablaufen:
- Besitzer der Gruppe werden benachrichtigt, um die Gruppe zu erneuern, wenn sich der Ablauf nähert.
- Aktive Gruppen werden automatisch erneuert.
- Eine Gruppe, die nicht erneuert wird, wird gelöscht.
- Jede gelöschte Gruppe kann innerhalb von 30 Tagen von den Gruppenbesitzern oder dem Administrator wiederhergestellt werden.

Ablaufrichtlinien sind eine gute Möglichkeit zum Begrenzen der Gruppen Zersplitterung, indem sichergestellt wird, dass nicht mehr verwendete Gruppen gelöscht werden. Wenn Sie eine Gruppen Ablaufrichtlinie erstellen möchten, finden Sie weitere Informationen unter [Microsoft 365 Group-Ablaufrichtlinie](microsoft-365-groups-expiration-policy.md).
