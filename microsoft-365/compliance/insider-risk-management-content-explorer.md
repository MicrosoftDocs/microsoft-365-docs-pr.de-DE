---
title: Insider-Risikomanagement Inhalts-Explorer
description: Erfahren Sie mehr über insider risk management Content explorer in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 44a17471f1e2ba92d0099f62b95dec8d0e56a224
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957492"
---
# <a name="insider-risk-management-content-explorer"></a>Insider-Risikomanagement Inhalts-Explorer

Der **Insider-Risikomanagement-Inhalts-Explorer** ermöglicht Benutzern, denen die Rolle *"Insider Risk Management Investigators"* zugewiesen wurde, den Kontext und details der Inhalte zu untersuchen, die mit Aktivitäten in Warnungen verknüpft sind. Die Falldaten im Inhalts-Explorer werden täglich aktualisiert, um neue Aktivitäten zu enthalten. Bei allen Warnungen, die für einen Fall bestätigt werden, werden Kopien von Daten- und Nachrichtendateien zur Zeit der Elemente als Momentaufnahme archiviert, während die ursprünglichen Dateien und Nachrichten in den Speicherquellen beibehalten werden. Falls erforderlich, können Falldatendateien als portable Dokumentdatei (PDF) oder im ursprünglichen Dateiformat exportiert werden.

Das Kopieren von Daten und Nachrichten ist für den Benutzer, der der Warnung zugeordnet ist, und für den Besitzer des Inhalts transparent. Bei neuen Fällen dauert es in der Regel etwa eine Stunde, bis Inhalte im Inhalts-Explorer auffüllen. Bei Fällen mit großen Inhaltsmengen kann es länger dauern, bis eine Momentaufnahme erstellt wird. Wenn Inhalte weiterhin im Inhalts-Explorer geladen werden, wird ein Fortschrittsindikator angezeigt, der den Fertigstellungsprozentsatz anzeigt.

In einigen Fällen sind daten, die einem Fall zugeordnet sind, möglicherweise nicht als Momentaufnahme zur Überprüfung im Inhalts-Explorer verfügbar. Diese Situation kann auftreten, wenn Falldaten gelöscht oder verschoben wurden oder wenn bei der Verarbeitung von Falldaten ein temporärer Fehler auftritt. In diesem Fall wählen Sie **Dateien** in der Warnleiste anzeigen aus, um die Dateinamen, den Dateipfad und den Grund für den Fehler für jede Datei anzeigen. Bei Bedarf können diese Informationen in eine datei .csv (durch Kommas getrennte Werte) exportiert werden.

Wenn der Inhalt Berechtigungen für die Verwaltung von Informationsrechten enthält, werden diese Berechtigungen für die kopierten Inhalte verwaltet, und Benutzer, denen die Rolle *Insider Risk Management Investigators* zugewiesen ist, benötigen diese Berechtigungen und Rechte, wenn sie die Dateien öffnen und anzeigen müssen. Jeder Datei und Nachricht wird automatisch eine eindeutige Datei-ID im Fall des Insiderrisikomanagements zu Verwaltungszwecken zugewiesen. Dokumente, die Mit Geräteindikatoraktivitäten verknüpft sind, sind nicht im Inhalts-Explorer enthalten.

>[!Note]
>Der Inhalts-Explorer enthält Aktivitäten im Zusammenhang mit Microsoft Office Dateien. Aktivitäten auf Websiteebene, z. B. wenn eine SharePoint gelöscht wird oder wenn Websiteberechtigungen geändert werden, werden nicht in den Inhalts-Explorer einbezogen.

## <a name="column-options"></a>Spaltenoptionen

Um Risikoanalysten und Ermittlern die Überprüfung erfasster Daten und Nachrichten zu erleichtern und den Kontext für den Fall zu überprüfen, sind mehrere Filter- und Sortiertools im Inhalts-Explorer enthalten. Für die einfache Sortierung unterstützen die **Klassenspalten Date** und **File** die Sortierung mithilfe der Spaltentitel im Inhaltswarteschlangenbereich. Andere Warteschlangenspalten können der Ansicht hinzugefügt werden, um unterschiedliche Pivots für die Dateien und Nachrichten zur Verfügung zu stellen.

Verwenden Sie zum Hinzufügen oder Entfernen von Spaltenüberschriften für die Inhaltswarteschlange das **Steuerelement** Spalten bearbeiten, und wählen Sie aus den folgenden Spaltenoptionen aus. Diese Spalten werden den allgemeinen, E-Mail- und Dokumenteigenschaftsbedingungen zuordnung, die im Inhalts-Explorer unterstützt und weiter unten in diesem Artikel aufgeführt werden.

| **Spaltenoption** | **Beschreibung** |
|:------------------|:----------------|
| **Autor** | Das Autorenfeld aus Office, das beibehalten wird, wenn ein Dokument kopiert wird. Wenn beispielsweise ein Benutzer ein Dokument erstellt und die E-Mails an eine andere Person senden, die es dann in SharePoint hochlädt, behält das Dokument weiterhin den ursprünglichen Autor bei. |
| **Bcc** | Verfügbar für E-Mail-Nachrichten, die Benutzer im Feld Bcc-Nachricht. |
| **Cc** | Für E-Mail-Nachrichten verfügbar, die Benutzer im Feld Cc-Nachricht. |
| **Zusammengesetzter Pfad** | Vom Menschen lesbarer Pfad, der die Quelle des Elements beschreibt. |
| **Unterhaltungs-ID** | Unterhaltungs-ID aus der Nachricht. |
| **Unterhaltungsindex** | Unterhaltungsindex aus der Nachricht. |
| **Erstellungszeitpunkt** | Der Zeitpunkt, zu dem die Datei oder E-Mail-Nachricht erstellt wurde. |
| **Datum (UTC)** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Für Dokumente das Datum, an dem ein Dokument zuletzt geändert wurde. Datum ist in koordinierter Weltzeit (COORDINATED Universal Time, UTC).|
| **Dominantes Design** | Dominantes Design, wie für analysen berechnet. |
| **E-Mail-Satz-ID** | Gruppen-ID für alle Nachrichten im gleichen E-Mail-Satz. |
| **Familien-ID** | Familien-ID-Gruppen alle Elemente; Für E-Mails enthält diese Spalte die Nachricht und alle Anlagen. für Dokumente enthält diese Spalte das Dokument und alle eingebetteten Elemente. |
| **Dateiklasse** | Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: **E-Mail** oder **Anlage**. |
| **Datei-ID** | Dokument-ID innerhalb des Falls eindeutig. |
| **Dateitypsymbol** | Die Erweiterung einer Datei; Beispiel: docx, one, pptx oder xlsx. Dieses Feld ist die gleiche Eigenschaft wie die FileExtension-Websiteeigenschaft. |
| **ID** | Der GUID-Bezeichner für die Datei. |
| **Unveränderliche ID** | Unveränderliche ID wie in Office 365. |
| **Inklusiver Typ** | Inklusiver Typ, der für die Analyse berechnet wird: **0** – nicht einschließlich; **1** – einschließlich; **2** – inklusives Minus; **3** – inklusive Kopie. |
| **Zuletzt geändert** | Das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Als repräsentativ gekennzeichnet** | Ein Dokument aus jedem Satz exakter Duplikate wird als Vertreter gekennzeichnet. |
| **Nachrichten art** | Der Typ der E-Mail-Nachricht, nach der gesucht werden soll. Mögliche Werte: Kontakte, Dokumente, E-Mails, externe Daten, Faxe, Im, Journale, Besprechungen, Microsoft Teams (gibt Elemente aus Chats, Besprechungen und Anrufen in Microsoft Teams zurück), Notizen, Beiträge, RSS-Feeds, Aufgaben, Voicemail |
| **Teilnehmer** | Liste aller Teilnehmer einer Nachricht; z. B. Sender, An, Cc, Bcc. |
| **Pivot-ID** | Die ID eines Pivots. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. Dieses Feld ist die gleiche Eigenschaft wie die Received email-Eigenschaft. |
| **Empfänger** | Alle Empfängerfelder in einer E-Mail-Nachricht. Diese Felder sind To, Cc und Bcc. |
| **Repräsentative ID** | Numerischer Bezeichner für jeden Satz exakter Duplikate. |
| **Sender** | Der Absender einer E-Mail-Nachricht. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten wird die im Feld Autor aus den Dokumenten Office zitiert. Sie können mehrere Namen eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den OR-Operator verbunden. |
| **Typen vertraulicher Informationen** | Die vertraulichen Informationstypen, die im Inhalt identifiziert werden. |
| **Vertraulichkeitsbezeichnungen** | Die Vertraulichkeitsbezeichnungen, die auf den Inhalt angewendet werden. |
| **Sent** | Das Datum, an dem eine E-Mail vom Absender gesendet wurde. Dieses Feld ist die gleiche Eigenschaft wie die Sent email-Eigenschaft. |
| **Größe** | Für E-Mails und Dokumente die Größe des Elements (in Bytes). |
| **Betreff** | Der Text in der Betreffzeile einer E-Mail. |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Wie bereits erläutert, handelt es sich bei der Title-Eigenschaft um Metadaten, die in Microsoft Office angegeben sind. Sie können den Namen von mehreren Betreff/Titeln eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den OR-Operator verbunden. |
| **Liste der Designs** | Designs list as calculated for analytics. |
| **Titel** | Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in dokumenten Office werden. Er ist anders als der Dateiname des Dokuments. |
| **Ziel** | Der Empfänger einer E-Mail-Nachricht im Feld An. |

## <a name="filtering"></a>Filtern

Sie können einen oder mehrere Filter verwenden, um den Bereich einer Suche zu einenten und einen verfeinerten Satz von Ergebnissen zurückzukehren. Wählen Sie zum Festlegen eines Filters **oben** in der Inhaltswarteschlange Filter aus. Viele Filter enthalten zusätzliche Filteroptionen, mit deren Hilfe die vom Filter zurückgegebenen Ergebnisse einengt werden. Der Filter *Date* enthält beispielsweise Steuerelemente zum Konfigurieren eines *Start-* und *Enddatums* für den **Datumsfilter.** Wählen Sie ein oder mehrere Filterelemente aus den folgenden Kategorien aus:

### <a name="common-filters"></a>Allgemeine Filter

| **Filter** | **Beschreibung** |
|:---------------------|:----------------|
| **Datum (UTC)** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Für Dokumente das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten wird die im Feld *Autor* aus den Dokumenten Office zitiert. Sie können mehrere Namen eingeben, getrennt durch Kommas. |
| **Source** | Der Speicherort des Dokuments in Ihrer Organisation. Beispielsweise eine bestimmte SharePoint Standort. |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Die Title-Eigenschaft in Dokumenten sind Metadaten, die in Microsoft Office angegeben sind. Sie können den Namen von mehreren Betreff/Titeln eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den OR-Operator verbunden. |

### <a name="email-filters"></a>E-Mail-Filter

| **Filter** | **Beschreibung** |
|:---------------------|:----------------|
| **Bcc** | Das Feld Bcc einer E-Mail-Nachricht. |
| **Cc** | Das Cc-Feld einer E-Mail-Nachricht. |
| **Verfügt über Eine Anlage** | Gibt an, ob eine Nachricht über eine Anlage verfügt. Werte werden als **true oder** **false aufgeführt.** |
| **Ist E-Mail-Anlage** | Wenn es sich bei dem Dokument um eine Anlage handelt, wird der Wert als **Ja aufgeführt.** |
| **Eingebettetes Dokument** | Wenn das Dokument in die E-Mail-Nachricht eingebettet ist, wird der Wert als **Ja aufgeführt.** |
| **Is inline attachment** | Wenn es sich bei dem Dokument um eine Inlineanlage in der E-Mail-Nachricht handelt, wird der Wert als **Ja aufgeführt.** |
| **Teilnehmer** | Alle Personenfelder in einer E-Mail-Nachricht. Diese Felder sind From, To, Cc und Bcc. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. |
| **Empfängerdomänen** | Liste aller Domänen von Empfängern einer Nachricht. |
| **Empfänger** | Die E-Mail-Nachrichtenempfänger. |
| **Sender** | Absenderfeld (Von) für Nachrichtentypen.  Format ist **DisplayName \<SmtpAddress>**. |
| **Absenderdomäne** | Domäne des Absenders. |
| **Ziel** | Das Feld „An“ einer E-Mail-Nachricht. |
| **Eindeutig in E-Mail-Satz** | False, wenn ein Duplikat der Anlage im E-Mail-Satz vorhanden ist. |

## <a name="document-filters"></a>Dokumentfilter

| **Filters** | **Beschreibung** |
|:---------------------|:----------------|
| **Konformitätsbezeichnungen** | Compliancebezeichnungen, die in Office 365. |
| **Created time (UTC)** | Datum und Uhrzeit der Datei oder E-Mail-Nachricht. Datum und Uhrzeit befinden sich in koordinierter Weltzeit (COORDINATED Universal Time, UTC). |
| **Datum der letzten Änderung (UTC)** | Das Datum, an dem ein Dokument zuletzt geändert wurde. Datum und Uhrzeit befinden sich in koordinierter Weltzeit (COORDINATED Universal Time, UTC). |
| **Kategorie** | Der Erweiterungstyp der Datei. |
| **Benutzeraktivitätsereignisse** | Aktivität für Elemente im Zusammenhang mit bestimmten Benutzeraktivitäten in einem Fall.  Wenn Sie beispielsweise einen Link zu "Inhalt erkunden"  für eine Aktivität auf der Seite Benutzeraktivität eines Falls auswählen, wird dieser Filter verwendet, um Elemente anzuzeigen, die mit dieser Aktivität in Zusammenhang stehen. |
| **Arbeitsprodukt** | Der Typ des Arbeitsprodukts für das Dokument. Beispielsweise Anmerkungen oder Tags im Dokument. |
