---
title: Versionshinweise zur Datenklassifizierung (Vorschau)
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
description: Versionshinweise für die öffentliche Vorschau der Datenklassifizierung.
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887337"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>Versionshinweise für die öffentliche Vorschau der Datenklassifizierung (Vorschau)

In dieser öffentlichen Vorschau wird eine neue Funktionalität eingeführt, mit der das Überprüfen Ihrer vertraulichen Inhalte und beschrifteten Inhalte beginnt, *bevor* Sie Richtlinien erstellen. Dies wird als **Zero Change Management** bezeichnet. Auf diese Weise können Sie die Auswirkungen aller Aufbewahrungs- und Vertraulichkeitsbezeichnungen in Ihrer Umgebung sehen und damit beginnen, Ihre Anforderungen im Zusammenhang mit Schutz- und Governancerichtlinien zu überdenken.

Lesen Sie diese Versionshinweise, damit Sie diese öffentliche Vorschau optimal nutzen können. Die Punkte zwischen dem jetzigen Zeitpunkt und der allgemeinen Verfügbarkeit (GA) werden ebenfalls behandelt.

## <a name="permissions-for-accessing-content-explorer"></a>Berechtigungen für den Zugriff auf den Inhalts-Explorer

Der Zugriff auf den Inhalts-Explorer ist hochgradig eingeschränkt, da Sie damit den Inhalt überprüfter Dateien lesen können. Für den Zugriff auf den Inhalts-Explorer ist die Mitgliedschaft in den Rollengruppen **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Inhaltsanzeige** erforderlich. Kein Konto hat standardmäßig Zugriff auf den Inhalts-Explorer. Lesen Sie die Informationen unter [Verwenden des Daten Inhalts-Explorers zur Datenklassifizierung (Vorschau)](data-classification-content-explorer.md#permissions). Ein globaler Administrator, ein Compliance-Administrator oder ein Datenadministrator kann die erforderliche Rollengruppenmitgliedschaft **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Inhaltsanzeige** zuweisen.

> [!TIP]
> Die Rollengruppen **Inhalts Explorer-Listenanzeige** und **Inhalts-Explorer-Inhaltsanzeige** werden möglicherweise nicht auf der Seite "Berechtigungen" angezeigt, wohingegen die rollenbasierten Zugriffssteuerungen (RBAC) weltweit bereitgestellt werden. Wenn sie auf der Seite "Berechtigungen" nicht angezeigt werden, müssen Sie eine benutzerdefinierte Rollengruppe erstellen und der benutzerdefinierten Rollengruppe die `data classification list viewer`-Rolle bzw. die `data classification content viewer`-Rolle zuweisen.

## <a name="exchange-mailbox-count"></a>Anzahl der Exchange-Postfächer

Beim Ausführen eines Drilldowns in Exchange-Postfächer wird ein kleiner QuickInfo-Tipp angezeigt. Dadurch wird darauf hingewiesen, dass die für den vertraulichen Informationstyp, die Vertraulichkeitsbezeichnung und die Aufbewahrungsbezeichnung angezeigte Gesamtzahl möglicherweise nicht genau mit der Anzahl von Elementen übereinstimmt, die im Postfach zu finden sind. Der Grund dafür ist, dass der Drilldown in den Ordner die Live-Ansichten von Inhalten abruft, die klassifiziert sind, während die Gesamtzahl berechnet wird.

## <a name="seeing-guids-instead-of-label-names"></a>Anzeigen von GUIDs anstelle von Bezeichnungsnamen

Bei Kunden der privaten Vorschau kam es vor, dass das Löschen einer Beschriftung, die bereits einem Inhalt zugeordnet wurde, dazu führt, dass die Bezeichnungsnamen im Inhalts Explorer und im Aktivitäts-Explorer in eine 32-Bit-GUID anstelle des Bezeichnungsnamens aufgelöst werden. 

## <a name="rendering-of-encrypted-documents"></a>Rendern von verschlüsselten Dokumenten

Verschlüsselte SharePoint-, Exchange- und OneDrive-Dateien werden im Inhalts-Explorer nicht gerendert. Hierbei handelt es sich um ein heikles Problem, das einen Kompromiss zwischen der Notwendigkeit des Anzeigens von Dateiinhalten im Inhalts-Explorer und der Notwendigkeit der Verschlüsselung von Inhalten erfordert. Mit den Berechtigungen, die von den Rollengruppen **Inhalts-Explorer-Listenanzeige** und **Inhalts-Explorer-Listenanzeige** gewährt werden, werden eine Listenansicht der Dateien, die Dateimetadaten sowie ein Link angezeigt, mit dem Sie über den Webclient auf den Inhalt zugreifen können.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Unterstützte Zeichen in den Namen von Aufbewahrungsbezeichnungen in der SharePoint-Suche

Die SharePoint-Suche unterstützt keine Namen von Aufbewahrungsbezeichnungen, die `-` oder `_` enthalten. `Label-MIP` und `Label_MIP` werden beispielsweise nicht unterstützt. Diese Zeichen werden von der SharePoint-Suche nicht in Namen von Aufbewahrungsbezeichnungen und Namen von Typen vertraulicher Informationen unterstützt.

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit der Datenklassifizierung (Vorschau)](data-classification-overview.md)
- [Beschriftungs-Aktivität anzeigen (Vorschau)](data-classification-activity-explorer.md)
- [Anzeigen von beschriftetem Inhalt (Vorschau)](data-classification-content-explorer.md)
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](labels.md)
- [Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)

