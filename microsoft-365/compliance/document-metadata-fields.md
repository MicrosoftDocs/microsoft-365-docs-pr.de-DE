---
title: Dokumentmetadaten-Felder in Daten Untersuchungen (Vorschau)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Zeigen Sie eine Tabelle an, in der die Metadatenfelder für Dokumente in einem in Data Investigations (Preview) festgelegten Nachweis aufgeführt sind.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4462b2031bc50f3d167b9340b6df5dba5a412d78
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357625"
---
# <a name="document-metadata-fields-in-data-investigations-preview"></a>Dokumentmetadaten-Felder in Daten Untersuchungen (Vorschau)

In der folgenden Tabelle sind die Metadatenfelder für Dokumente in einem in einer Untersuchung in Data Investigations (Preview) festgelegten Evidence-Feld aufgeführt. Die Tabelle gibt den Namen des Metadatenfelds an, ob das Feld durchsucht werden kann, wenn eine Abfrage in einem Evidence-DataSet ausgeführt wird, ob das Feld vorhanden ist, wenn die Datei Metadaten eines ausgewählten Dokuments in einem Beweissatz angezeigt werden, und ob das Feld beim Exportieren von Dokumenten enthalten ist. 

> [!NOTE]
> Die Werte in Klammern in der Spalte **durchsuchbar in Beweis Sätzen** sind der Name der Eigenschaft, nach der Sie suchen können. Die Werte in Klammern in der Spalte **sichtbar in Datei Metadaten** sind der Name der Eigenschaft, die angezeigt wird, wenn Sie die Datei Metadaten anzeigen.

|**Feldname** </br>|**Durchsuchbar in Beweis Sätzen** |**Sichtbar in Datei Metadaten** |**Exportiert** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Case-Tags                  | Ja (Tags)                                      |                         | Ja         |
|Konformitäts Bezeichnungen          |                                                 |                         | Ja         |
|Zusammengesetzter Pfad              |                                                 |                         | Ja         |
|Container-ID               |                                                 |                         | Ja         |
|Unterhaltungsindex         |                                                 |                         | Ja         |
|Custodian                  | Ja (Depotbank)                                 |   Ja (Depotbank)       | Ja         |
|Datenquelle                | Ja (Quelle)                                    |   Ja (Arbeitsauslastung)          | Ja         |
|Datum                       | Ja (Datum)                                      |   Ja (Datum UTC)        | Ja         |
|Deduplizierten zusammengesetzten Pfad      |                                                 |                         | Ja         |
|Deduped depotverwalter         |                                                 |                         | Ja         |
|Deduplizierte Datei-IDs           |                                                 |                         | Ja         |
|Doc-Autoren                | Ja (Autor) *                                   |    Ja (Autor)         | Ja         |
|Doc-Kommentare               | Ja (Kommentare)                                  |                         | Ja         |
|Doc-Unternehmen                |                                                 |                         | Ja         |
|Erstelltes doc-Datum           | Ja (erstellt) *                              |    Ja (Erstellungszeit)   | Ja         |
|Doc-Datum geändert          | Ja (lastModifiedDate) *                         |                         | Ja         |
|Doc-Schlüsselwörter               |                                                 |                         | Ja         |
|Doc zuletzt gespeichert von          |                                                 |                         | Ja         |
|Doc geändert von            |                                                 |                         | Ja         |
|Betreff des Dokuments                |                                                 |  Ja (Betreff/Titel)    | Ja         |
|Doc-Vorlage               |                                                 |                         | Ja         |
|Doc-Titel                  | Ja (Titel)                                     |  Ja (Titel)            | Ja         |
|Doc-Version                |                                                 |                         | Ja         |
|Dominantes Design             | Ja (dominantTheme)                             |  Ja (dominantes Design)   | Ja         |
|Doppelte Teilmenge           |                                                 |                         | Ja         |
|E-Mail-Aktion               |                                                 |                         | Ja         |
|BCC-e-Mail                  | Ja (BCC)                                       |                         | Ja         |
|E-Mail CC                   | Ja (CC)                                        |                         | Ja         |
|E-Mail-Unterhaltungs-ID      |                                                 |                         | Ja         |
|E-Mail-Datum empfangen        | Ja (empfangen)                                  |   Ja (empfangen)        | Ja         |
|Gesendetes e-Mail-Datum            | Ja (gesendet)                                      |   Ja (gesendet)            | Ja         |
|E-Mail weist eine Anlage auf       |                                                 |                         | Ja         |
|E-Mail-Wichtigkeit           |                                                 |                         | Ja         |
|E-Mail-Internetkopfzeilen     |                                                 |                         | Ja         |
|E-Mail-Ebene                |                                                 |                         | Ja         |
|E-Mail-Nachrichten-ID           |                                                 |                         | Ja         |
|E-Mail-Teilnehmer Domänen  | Ja (participantDomains)                        |                         | Ja         |
|E-Mail-Teilnehmer         | Ja (Teilnehmer)                              |                         | Ja         |
|E-Mail-Empfängerdomänen    | Ja (recipientDomains)                          |                         | Ja         |
|E-Mail-Empfänger           | Ja (Empfänger)                                |                         | Ja         |
|E-Mail-Sicherheit             |                                                 |                         | Ja         |
|E-Mail-Absender               | Ja (Absender)                                    |   Ja (Absender)          | Ja         |
|E-Mail-Absenderdomäne        | Ja (senderDomain)                              |                         | Ja         |
|E-Mail-Empfindlichkeit          |                                                 |                         | Ja         |
|E-Mail-Gruppe                  | Ja (emailSetId)                                |   Ja (EmailSetID)      | Ja         |
|E-Mail-Betreff              | Ja (Betreff)                                   |   Ja (Betreff/Titel)   | Ja         |
|E-Mail-Thread               |                                                 |                         | Ja         |
|E-Mail an                   | Ja (an)                                        |                         | Ja         |
|Fehlercode                 | Ja (processingStatus)                          |                         | Ja         |
|Nativen Pfad exportieren         |                                                 |                         | Ja         |
|Extrahierte Text Länge      |                                                 |                         | Ja         |
|Extrahierter Text Pfad        |                                                 |                         | Ja         |
|Familien-ID                  | Ja (Familien-ID)                                  |   Ja (Familien-ID)        | Ja         |
|Familiengröße                |                                                 |                         | Ja         |
|File-Klasse                 | Ja (fileclass)                                 |   Yes (File-Klasse)      | Ja         |
|Datei-ID                    | Ja (Datei-Nr)                                    |   Ja (ID)              | Ja         |
|Verfügt über Text                   |                                                 |                         | Ja         |
|Inklusiv-Typ             | Ja (inklusivetype)                             |   Ja (einschließlich Typ)  | Ja         |
|Eingabedatum geändert        |                                                 |                         | Ja         |
|Eingabedatei-ID              |                                                 |                         | Ja         |
|Eingabepfad                 |                                                 |                         | Ja         |
|Internetnachrichten-ID        |                                                 |                         | Ja         |
|Ist repräsentativ          | Ja (markAsRepresentative)                      |                         | Ja         |
|Elementklasse                 |                                                 |                         | Ja         |
|Laden-ID                    | Ja (Lade-Nr)                                    |                         | Ja         |
|Speicherort Name              |                                                 |                         | Ja         |
|Als Pivot markiert            | Ja (markAsPivot)                               |   Ja (als Pivot gekennzeichnet) | Ja         |
|Nachrichten Art               | Ja (messageKind)                               |                         | Ja         |
|Systemeigene Erweiterung           |                                                 |                         | Ja         |
|Name der systemeigenen Datei           |                                                 |    Ja (filename)      | Ja         |
|Natives MD5                 |                                                 |                         | Ja         |
|Native SHA 256             |                                                 |                         | Ja         |
|Systemeigene Größe                | Ja (Größe)                                      |   Ja (NativeSize)     | Ja         |
|Systemeigener Typ                | Ja (filetype)                                  |   Yes (Dateityp)       | Ja         |
|ND et Sort exkl Attach     |                                                 |                         | Ja         |
|ND et Sort incl anfügen     |                                                 |                         | Ja         |
|ND-Gruppe                     |                                                 |                         | Ja         |
|O365-Autoren               | Ja (Autor) *                                   |   Ja (Absender/Autor)   | Ja         |
|O365 erstellt von            |                                                 |                         | Ja         |
|O365-Erstellungsdatum          | Ja (erstellt) *                              |                         | Ja         |
|O365-Datum geändert         | Ja (lastModifiedDate) *                         |   Ja (Datum der letzten Änderung) | Ja      |
|O365 geändert von           |                                                 |                         | Ja         |
|Übergeordneter Knoten                |                                                 |                         | Ja         |
|Pivot-ID                   | Ja (Pivot-Nr)                                   |  Ja (Pivot-Nr)          | Ja         |
|Empfängeranzahl            |                                                 |                         | Ja         |
|Zeilennummer                 |                                                 |                         | Ja         |
|ID festlegen                     |                                                 |                         | Ja         |
|Erste Bestellung inklusive festlegen |                                                 |                         | Ja         |
|Ähnlichkeits Prozent         |                                                 |                         | Ja         |
|Themenliste                | Ja (themeslist)                                | Ja (Liste Designs)       | Ja         |
|Word count                 | Ja (WordCount)                                 |                         | Ja         |
|Relevanz Score (Issue)    | Ja (relevanceScore_issueNum)                   |                         |             |
|Quantil lesen (Problem)    | Ja (readPercentile_issueNum)                   |                         |             |
|Relevanz-Tag (Problem)      | Ja (relevanceTag_issueNum)                     |                         |             |
|||||

  \* Wenn in einem Dokument eingebettete Werte vorhanden sind, priorisiert die Suche für diese Felder diese Werte; Andernfalls wird versucht, den Wert aus Office 365 anzuzeigen.
