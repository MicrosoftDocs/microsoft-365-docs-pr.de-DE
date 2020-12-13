---
title: Veröffentlichungshinweise zur Datenklassifizierung
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
description: Veröffentlichungshinweise für die Datenklassifizierung.
ms.openlocfilehash: 2b9302cfa49f9445d3cbeb5109aef70e0c8d8f7f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663040"
---
# <a name="data-classification-release-notes"></a>Veröffentlichungshinweise zur Datenklassifizierung


## <a name="exchange-mailbox-count"></a>Anzahl der Exchange-Postfächer

Beim Ausführen eines Drilldowns in Exchange-Postfächer wird ein kleiner QuickInfo-Tipp angezeigt. Dadurch wird darauf hingewiesen, dass die für den vertraulichen Informationstyp, die Vertraulichkeitsbezeichnung und die Aufbewahrungsbezeichnung angezeigte Gesamtzahl möglicherweise nicht genau mit der Anzahl von Elementen übereinstimmt, die im Postfach zu finden sind. Der Grund dafür ist, dass der Drilldown in den Ordner die Live-Ansichten von Inhalten abruft, die klassifiziert sind, während die Gesamtzahl berechnet wird.


## <a name="rendering-of-encrypted-documents"></a>Rendern von verschlüsselten Dokumenten

Verschlüsselte SharePoint-, Exchange- und OneDrive-Dateien werden im Inhalts-Explorer nicht gerendert. Hierbei handelt es sich um ein heikles Problem, das einen Kompromiss zwischen der Notwendigkeit des Anzeigens von Dateiinhalten im Inhalts-Explorer und der Notwendigkeit der Verschlüsselung von Inhalten erfordert. Mit den Berechtigungen, die von den Rollengruppen **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Listenanzeige** gewährt werden, werden eine Listenansicht der Dateien, die Dateimetadaten sowie ein Link angezeigt, mit dem Sie über den Webclient auf den Inhalt zugreifen können.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Unterstützte Zeichen in den Namen von Aufbewahrungsbezeichnungen in der SharePoint-Suche

Die SharePoint-Suche unterstützt keine Namen von Aufbewahrungsbezeichnungen, die `-` oder `_` enthalten. `Label-MIP` und `Label_MIP` werden beispielsweise nicht unterstützt. Diese Zeichen werden von der SharePoint-Suche nicht in Namen von Aufbewahrungsbezeichnungen und Namen von Typen vertraulicher Informationen unterstützt.

## <a name="onedrive-remains-in-preview"></a>OneDrive bleibt in der Vorschauphase

Vielen Dank für Ihr wertvolles Feedback zur OneDrive-Integration während unseres Vorschauprogramms. Während wir die Einzelheiten bearbeiten, können Sie auf inkonsistente Daten/Flüsse stoßen. Wir werden OneDrive weiterhin in der Vorschauphase präsentieren, bis alle Fehlerkorrekturen umgesetzt sind. Wir wissen Ihre fortgesetzte Unterstützung sehr zu schätzen.


## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit der Datenklassifizierung (Vorschau)](data-classification-overview.md)
- [Beschriftungs-Aktivität anzeigen (Vorschau)](data-classification-activity-explorer.md)
- [Anzeigen von beschriftetem Inhalt (Vorschau)](data-classification-content-explorer.md)
- [Weitere Informationen zu Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)