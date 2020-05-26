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
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327606"
---
# <a name="data-classification-release-notes"></a>Veröffentlichungshinweise zur Datenklassifizierung

Lesen Sie diese Versionshinweise, damit Sie diese Datenklassifizierung optimal nutzen können.

## <a name="exchange-mailbox-count"></a>Anzahl der Exchange-Postfächer

Beim Ausführen eines Drilldowns in Exchange-Postfächer wird ein kleiner QuickInfo-Tipp angezeigt. Dadurch wird darauf hingewiesen, dass die für den vertraulichen Informationstyp, die Vertraulichkeitsbezeichnung und die Aufbewahrungsbezeichnung angezeigte Gesamtzahl möglicherweise nicht genau mit der Anzahl von Elementen übereinstimmt, die im Postfach zu finden sind. Der Grund dafür ist, dass der Drilldown in den Ordner die Live-Ansichten von Inhalten abruft, die klassifiziert sind, während die Gesamtzahl berechnet wird.


## <a name="rendering-of-encrypted-documents"></a>Rendern von verschlüsselten Dokumenten

Verschlüsselte SharePoint-, Exchange- und OneDrive-Dateien werden im Inhalts-Explorer nicht gerendert. Hierbei handelt es sich um ein heikles Problem, das einen Kompromiss zwischen der Notwendigkeit des Anzeigens von Dateiinhalten im Inhalts-Explorer und der Notwendigkeit der Verschlüsselung von Inhalten erfordert. Mit den Berechtigungen, die von den Rollengruppen **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Listenanzeige** gewährt werden, werden eine Listenansicht der Dateien, die Dateimetadaten sowie ein Link angezeigt, mit dem Sie über den Webclient auf den Inhalt zugreifen können.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Unterstützte Zeichen in den Namen von Aufbewahrungsbezeichnungen in der SharePoint-Suche

Die SharePoint-Suche unterstützt keine Namen von Aufbewahrungsbezeichnungen, die `-` oder `_` enthalten. `Label-MIP` und `Label_MIP` werden beispielsweise nicht unterstützt. Diese Zeichen werden von der SharePoint-Suche nicht in Namen von Aufbewahrungsbezeichnungen und Namen von Typen vertraulicher Informationen unterstützt.

## <a name="onedrive-remains-in-preview"></a>OneDrive bleibt in der Vorschauphase

Wir haben uns Ihr wertvolles Feedback zur OneDrive-Integration während unseres Vorschauprogramms angehört. Während wir die Einzelheiten bearbeiten, können Sie auf inkonsistente Daten/Flüsse stoßen. Wir werden weiterhin OneDrive in der Vorschauphase präsentieren, bis alle Fehlerkorrekturen umgesetzt sind. Wir wissen Ihre anhaltende Unterstützung diesbezüglich zu schätzen.


## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit der Datenklassifizierung (Vorschau)](data-classification-overview.md)
- [Beschriftungs-Aktivität anzeigen (Vorschau)](data-classification-activity-explorer.md)
- [Anzeigen von beschriftetem Inhalt (Vorschau)](data-classification-content-explorer.md)
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](labels.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)