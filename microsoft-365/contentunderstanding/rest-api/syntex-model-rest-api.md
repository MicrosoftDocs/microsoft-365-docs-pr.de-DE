---
title: SharePoint Syntex-Dokumentverständnismodell-REST-API
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Überblick über die SharePoint Syntex-Dokumentverständnismodell-REST-API.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908089"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>SharePoint Syntex-Dokumentverständnismodell-REST-API

Sie können die SharePoint-REST-Schnittstelle verwenden, um eine Dokumentverständnismodell zu erstellen, das Modell auf eine oder mehrere Bibliotheken anzuwenden oder es von diesen zu entfernen, und um Informationen über das Modell zu erhalten oder zu aktualisieren. 

Der REST-Dienst in SharePoint Online (sowie in lokalen Bereitstellungen von SharePoint 2016 und höher) erlaubt die Zusammenfassung mehrerer Anforderungen in einem einzigen Aufruf an den Service mittels der ODATA-Abfrageoption „$batch“. 

Einzelheiten und Links zu Codebeispielen finden Sie unter [Durchführen von Batchanforderungen mit den REST-APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

## <a name="prerequisites"></a>Voraussetzungen

Lesen Sie vor der Umsetzung der Beispiele in diesem Artikel zunächst die folgenden Artikel:

- [Grundlegendes zum SharePoint-REST-Dienst](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [Ausführen grundlegender Vorgänge unter Verwendung von SharePoint-REST-Endpunkten](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>REST-Befehle

Die folgenden REST-Befehle stehen für die Arbeit mit Syntex-Dokumentverständnismodellen zur Verfügung:

- [Modell erstellen](rest-createmodel-method.md) – Erstellt ein Modell und den zugehörigen Inhaltstyp.
- [GetByUniqueId](rest-getbyuniqueid-method.md) – Ruft Informationen zu einem SharePoint Syntex-Dokumentverständnismodell ab oder aktualisiert diese.
- [GetByTitle](rest-getbytitle-method.md) – Ruft Informationen zu einem SharePoint Syntex-Dokumentverständnismodell mittels dem Modelltitel ab oder aktualisiert diese.
- [Modell anwenden](rest-applymodel-method.md) – Wendet ein trainiertes Dokumentverständnismodell auf eine oder mehrere Bibliotheken an (oder synchronisiert es).
- [Modell- und Bibliotheksinformationen abrufen](rest-getmodelandlibraryinfo.md) – Ruft Informationen ab über das Modell und die Bibliothek, auf die es angewendet wurde.
- [UpdateModelSettings](rest-updatemodelsettings-method.md) – Aktualisiert verfügbare Modelleinstellungen (zugehörige Aufbewahrungsbezeichnung und Modellbeschreibung) für eine SharePoint Syntex-Dokumentverständnismodell.
- [BatchDelete](rest-batchdelete-method.md) – Entfernt ein angewendetes Dokumentverständnismodell von einer oder mehreren Bibliotheken.
- [Erstellen einer Klassifizierungsanforderung](rest-createclassificationrequest.md) – Erstellt eine Anforderung zur Klassifizierung einer bestimmten Datei oder bestimmter Dateien mittels dem angewendeten Modell.

## <a name="scenarios"></a>Szenarien

Beachten Sie die folgenden Szenario-Beispiele, die sich nicht intuitiv aus dem Methodennamen ergeben. Weitere Informationen finden Sie im jeweiligen Artikel.

Die Methode „Modell erstellen“ erstellt nur das Modellobjekt und den zugehörigen Inhaltstyp. Sie müssen das Modell zuerst im Inhaltscenter trainieren, bevor es auf eine Bibliothek angewendet werden kann.

Die Methode „Modell anwenden“ wird verwendet, um das Modell auf der Zielbibliothek zu konfigurieren, um Dokumente zu klassifizieren und optional zusätzliche Informationen zu extrahieren. Diese API unterstützt auch die Batch-Anwendung des Modells auf mehrere Bibliotheken.

Die Methode „Modell entfernen“ entfernt das Modell nur von einer oder mehreren Bibliotheken, auf die es zuvor angewendet wurde. Wenn Sie das Modell löschen wollen, müssen Sie es zuerst aus allen Bibliotheken entfernen, auf die es angewendet wurde.


## <a name="see-also"></a>Siehe auch

[Übersicht über das Dokumentenverständnis](../document-understanding-overview.md)

