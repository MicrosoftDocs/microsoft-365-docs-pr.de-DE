---
title: Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie beschriftete Elemente systemintern anzeigen.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268523"
---
# <a name="using-data-classification-content-explorer-preview"></a>Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)

Mit dem Inhalts-Explorers zur Datenklassifizierung können Sie die Elemente, die auf der Übersichtsseite zusammengefasst wurden, systemintern anzeigen.

## <a name="content-explorer"></a>Inhalts-Explorer

Der Inhalts-Explorer ist eine aktuelle Momentaufnahme der Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder von Elementen, die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden.

![Screenshot des erweiterten Inhalts-Explorers](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>Berechtigungen

Es gibt zwei Rollen, die den Zugriff auf den Inhalts-Explorer gewähren:

- **Inhalts Explorer-Listenanzeige**: Mit der Mitgliedschaft in dieser Rolle können Sie jedes Element und dessen Position anzeigen.

- **Inhalts-Explorer-Inhaltsanzeige**: Mit der Mitgliedschaft in dieser Rolle können Sie die Inhalte aller Elemente in der Liste anzeigen.

Das Konto, das Sie für den Zugriff auf den Inhalts-Explorer verwenden, muss eine oder beide Rollen aufweisen. Hierbei handelt es sich um unabhängige Rollen, die nicht kumulativ sind. Wenn Sie beispielsweise einem Konto die Möglichkeit geben möchten, nur die Elemente und deren Speicherorte anzuzeigen, erteilen Sie Inhalts-Explorer-Listenanzeige-Rechte. Wenn Sie möchten, dass dasselbe Konto auch in der Lage ist, die Inhalte der Elemente in der Liste anzuzeigen, erteilen Sie zusätzlich Inhalts-Explorer-Inhaltsanzeige-Rechte.

### <a name="how-to-use-content-explorer"></a>Verwendung des Inhalts-Explorers

1. Öffnen Sie **Microsoft 365 Compliance Center**  > **Datenklassifizierung** > **Inhalts-Explorer**.
2. Wenn Sie den Namen der Bezeichnung oder den Typ vertraulicher Informationen kennen, können Sie ihn in das Suchfeld eingeben.
3. Alternativ können Sie auch nach dem Element suchen, indem Sie den Beschriftungstyp erweitern und die Bezeichnung in der Liste auswählen. Nachfolgend wird ein Element aus dem Bereich der Aufbewahrungsbezeichnung der Liste angezeigt.
4. Wählen Sie unter **Alle Standorte** einen Standort aus, und gliedern Sie die Ordnerstruktur bis zu dem Element weiter auf.
5. Doppelklicken Sie, um das Element systemintern im Inhalts-Explorer zu öffnen.

## <a name="see-also"></a>Siehe auch

- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](labels.md)
- [Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)
- [Übersicht über Aufbewahrungsrichtlinien](retention-policies.md)
