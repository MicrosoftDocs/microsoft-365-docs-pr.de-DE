---
title: Inhalts-Explorer für Insider-Risikomanagement
description: Informationen zum Inhalts-Explorer für Insider-Risikomanagement in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Compliance
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
ms.openlocfilehash: 3ff3c652d5446167ac3c2bf78a2405c21929ea11
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226467"
---
# <a name="insider-risk-management-content-explorer"></a>Inhalts-Explorer für Insider-Risikomanagement

Der **Inhalts-Explorer** für Insider-Risikomanagement ermöglicht Benutzern, denen die Rolle *"Ermittler für Insider-Risikomanagement"* zugewiesen ist, den Kontext und details von Inhalten im Zusammenhang mit Aktivitäten in Warnungen zu untersuchen. Die Falldaten im Inhalts-Explorer werden täglich aktualisiert, um neue Aktivitäten einzuschließen. Für alle Warnungen, die in einem Fall bestätigt werden, werden Kopien von Daten- und Nachrichtendateien als Momentaufnahme in der Zeit der Elemente archiviert, während die ursprünglichen Dateien und Nachrichten in den Speicherquellen beibehalten werden. Falls erforderlich, können Falldatendateien als portable Dokumentdatei (PDF) oder im Originaldateiformat exportiert werden.

Das Kopieren von Daten und Nachrichten ist für den mit der Warnung verbundenen Benutzer und für den Besitzer des Inhalts transparent. Bei neuen Fällen dauert es in der Regel etwa eine Stunde, bis Inhalte im Inhalts-Explorer aufgefüllt werden. Bei Fällen mit großen Mengen von Inhalten kann es länger dauern, eine Momentaufnahme zu erstellen. Wenn Inhalte weiterhin im Inhalts-Explorer geladen werden, wird eine Statusanzeige angezeigt, die den Prozentsatz der Fertigstellung anzeigt.

In einigen Fällen sind daten, die einem Fall zugeordnet sind, möglicherweise nicht als Momentaufnahme für die Überprüfung im Inhalts-Explorer verfügbar. Diese Situation kann auftreten, wenn Falldaten gelöscht oder verschoben wurden oder wenn bei der Verarbeitung von Falldaten ein temporärer Fehler auftritt. Wählen Sie in diesem Fall **Dateien** in der Warnleiste anzeigen aus, um die Dateinamen, den Dateipfad und den Grund für den Fehler für jede Datei anzuzeigen. Bei Bedarf können diese Informationen in eine .csv datei (durch Trennzeichen getrennte Werte) exportiert werden.

Wenn der Inhalt Berechtigungen für die Verwaltung von Informationsrechten enthält, werden diese Berechtigungen für die kopierten Inhalte beibehalten, und Benutzer, denen die Rolle *"Ermittler des Insider-Risikomanagements"* zugewiesen ist, benötigen diese Berechtigungen und Rechte, wenn sie die Dateien öffnen und anzeigen müssen. Jeder Datei und Nachricht wird automatisch eine eindeutige Datei-ID im Fall des Insider-Risikomanagements für Verwaltungszwecke zugewiesen. Dokumente, die Geräteindikatoraktivitäten zugeordnet sind, sind nicht im Inhalts-Explorer enthalten.

> [!NOTE]
> Der Inhalts-Explorer enthält Aktivitäten im Zusammenhang mit Microsoft Office Dateien. Aktivitäten auf Websiteebene, z. B. wenn eine SharePoint Website gelöscht wird oder wenn Websiteberechtigungen geändert werden, sind nicht im Inhalts-Explorer enthalten.

## <a name="column-options"></a>Spaltenoptionen

Um Risikoanalysten und Ermittlern die Überprüfung erfasster Daten und Nachrichten sowie die Überprüfung des Kontexts für den Fall zu erleichtern, sind mehrere Filter- und Sortiertools im Inhalts-Explorer enthalten. Für **die** einfache Sortierung unterstützen die Spalten der Date- und **File-Klasse** die Sortierung mithilfe der Spaltentitel im Inhaltwarteschlangenbereich. Andere Warteschlangenspalten können der Ansicht hinzugefügt werden, um unterschiedliche Pivots für die Dateien und Nachrichten bereitzustellen.

Um Spaltenüberschriften für die Inhaltswarteschlange hinzuzufügen oder zu entfernen, verwenden Sie das Steuerelement **Spalten bearbeiten,** und wählen Sie aus den folgenden Spaltenoptionen aus. Diese Spalten entsprechen den allgemeinen, E-Mail- und Dokumenteigenschaftenbedingungen, die im Inhalts-Explorer unterstützt und weiter unten in diesem Artikel aufgeführt werden.

| **Spaltenoption** | **Beschreibung** |
|:------------------|:----------------|
| **Autor** | Das Feld "Autor" aus Office Dokumenten, das beim Kopieren eines Dokuments beibehalten wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die E-Mails an eine andere Person sendet, die es dann in SharePoint hochlädt, behält das Dokument den ursprünglichen Autor bei. |
| **Bcc** | Für E-Mail-Nachrichten verfügbar, die Benutzer im Bcc-Nachrichtenfeld. |
| **Cc** | Für E-Mail-Nachrichten verfügbar, die Benutzer im Nachrichtenfeld "Cc". |
| **Zusammengesetzter Pfad** | Lesbarer Pfad, der die Quelle des Elements beschreibt. |
| **Unterhaltungs-ID** | Unterhaltungs-ID aus der Nachricht. |
| **Unterhaltungsindex** | Unterhaltungsindex aus der Nachricht. |
| **Erstellungszeitpunkt** | Der Zeitpunkt, zu dem die Datei oder E-Mail-Nachricht erstellt wurde. |
| **Datum (UTC)** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Bei Dokumenten das Datum, an dem ein Dokument zuletzt geändert wurde. Datum ist in koordinierter Weltzeit (UTC).|
| **Dominantes Design** | Dominantes Design, wie es für Analysen berechnet wird. |
| **E-Mail-Satz-ID** | Gruppen-ID für alle Nachrichten in demselben E-Mail-Satz. |
| **Familien-ID** | Familien-ID gruppiert alle Elemente; für E-Mails enthält diese Spalte die Nachricht und alle Anlagen; für Dokumente enthält diese Spalte das Dokument und alle eingebetteten Elemente. |
| **Dateiklasse** | Für Inhalte aus SharePoint und OneDrive: **Dokument**; für Inhalte aus Exchange: **E-Mail** oder **Anlage**. |
| **Datei-ID** | Dokumentbezeichner innerhalb des Falls eindeutig. |
| **Dateitypsymbol** | Die Erweiterung einer Datei; z. B. docx, one, pptx oder xlsx. Dieses Feld ist die gleiche Eigenschaft wie die FileExtension-Websiteeigenschaft. |
| **ID** | Der GUID-Bezeichner für die Datei. |
| **Unveränderliche ID** | Unveränderliche ID wie in Office 365 gespeichert. |
| **Inklusiver Typ** | Inklusiver Typ, der für Analysen berechnet wird: **0** – nicht inklusiv; **1** – einschließlich; **2** – inklusive Minus; **3** – inklusive Kopie. |
| **Zuletzt geändert** | Das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Als repräsentativ markiert** | Ein Dokument aus jeder Gruppe exakter Duplikate wird als Vertreter gekennzeichnet. |
| **Nachrichtenart** | Der Typ der E-Mail-Nachricht, nach der gesucht werden soll. Mögliche Werte: Kontakte, Dokumente, E-Mail, externe Daten, Faxe, Chat, Nachrichten, Besprechungen, Microsoft Teams (Gibt Elemente aus Chats, Besprechungen und Anrufen in Microsoft Teams zurück), Notizen, Beiträge, RSS-Feeds, Aufgaben, Voicemail |
| **Teilnehmer** | Liste aller Teilnehmer einer Nachricht; z. B. Sender, To, Cc, Bcc. |
| **Pivot-ID** | Die ID eines Pivots. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. Dieses Feld ist die gleiche Eigenschaft wie die Eigenschaft "Empfangene E-Mail". |
| **Empfänger** | Alle Empfängerfelder in einer E-Mail-Nachricht. Diese Felder sind "An", "Cc" und "Bcc". |
| **Repräsentative ID** | Numerischer Bezeichner jedes Satzes exakter Duplikate. |
| **Sender** | Der Absender einer E-Mail-Nachricht. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten die Person, die im Feld "Autor" aus Office Dokumenten stammt. Sie können mehrere Namen durch Kommas getrennt eingeben. Zwei oder mehr Werte werden vom OR-Operator logisch verbunden. |
| **Typen vertraulicher Informationen** | Die vertraulichen Informationstypen, die im Inhalt identifiziert werden. |
| **Vertraulichkeitsbezeichnungen** | Die auf den Inhalt angewendeten Vertraulichkeitsbezeichnungen. |
| **Sent** | Das Datum, an dem eine E-Mail vom Absender gesendet wurde. Dieses Feld entspricht der Eigenschaft "Gesendete E-Mail". |
| **Size** | Für E-Mails und Dokumente die Größe des Elements (in Bytes). |
| **Betreff** | Der Text in der Betreffzeile einer E-Mail. |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Wie zuvor erläutert, handelt es sich bei der Title-Eigenschaft um Metadaten, die in Microsoft Office Dokumenten angegeben sind. Sie können den Namen mehrerer Subjekte/Titel durch Kommas getrennt eingeben. Zwei oder mehr Werte werden vom OR-Operator logisch verbunden. |
| **Designliste** | Designliste wie für Analysen berechnet. |
| **Titel** | Der Titel des Dokuments. Die Title-Eigenschaft ist Metadaten, die in Office Dokumenten angegeben sind. Sie unterscheidet sich vom Dateinamen des Dokuments. |
| **Ziel** | Der Empfänger einer E-Mail-Nachricht im Feld "An". |

## <a name="filtering"></a>Filtern

Sie können einen oder mehrere Filter verwenden, um den Umfang einer Suche einzugrenzen und einen optimierteren Satz von Ergebnissen zurückzugeben. Wählen Sie zum Festlegen eines Filters oben in der Inhaltswarteschlange **Filter** aus. Viele Filter enthalten zusätzliche Filteroptionen, um die vom Filter zurückgegebenen Ergebnisse einzugrenzen. Beispielsweise enthält der *Date-Filter* Steuerelemente zum Konfigurieren eines *Anfangs-* und *Enddatums* für den **Datumsfilter.** Wählen Sie ein oder mehrere Filterelemente aus den folgenden Kategorien aus:

### <a name="common-filters"></a>Allgemeine Filter

| **Filter** | **Beschreibung** |
|:---------------------|:----------------|
| **Datum (UTC)** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Bei Dokumenten das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten die Person, die im Feld *"Autor"* aus Office Dokumenten stammt. Sie können mehrere Namen durch Kommas getrennt eingeben. |
| **Source** | Der Speicherort des Dokuments in Ihrer Organisation. Beispiel: ein bestimmter SharePoint Standort. |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Die Title-Eigenschaft in Dokumenten ist Metadaten, die in Microsoft Office Dokumenten angegeben sind. Sie können den Namen mehrerer Subjekte/Titel durch Kommas getrennt eingeben. Zwei oder mehr Werte werden vom OR-Operator logisch verbunden. |

### <a name="email-filters"></a>E-Mail-Filter

| **Filter** | **Beschreibung** |
|:---------------------|:----------------|
| **Bcc** | Das Bcc-Feld einer E-Mail-Nachricht. |
| **Cc** | Das Feld "Cc" einer E-Mail-Nachricht. |
| **Hat Anlage** | Gibt an, ob eine Nachricht über eine Anlage verfügt. Werte werden als **"true"** oder **"false"** aufgelistet. |
| **Ist E-Mail-Anlage?** | Wenn das Dokument eine Anlage ist, wird der Wert als **Ja** aufgeführt. |
| **Eingebettetes Dokument** | Wenn das Dokument in die E-Mail-Nachricht eingebettet ist, wird der Wert als **Ja** aufgeführt. |
| **Ist Inlineanlage** | Wenn das Dokument eine Inlineanlage in der E-Mail-Nachricht ist, wird der Wert als **Ja** aufgeführt. |
| **Teilnehmer** | Alle Personenfelder in einer E-Mail-Nachricht. Diese Felder sind From, To, Cc und Bcc. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. |
| **Empfängerdomänen** | Liste aller Domänen von Empfängern einer Nachricht. |
| **Empfänger** | Die Empfänger der E-Mail-Nachricht. |
| **Sender** | Absenderfeld (Von) für Nachrichtentypen.  Format ist **DisplayName \<SmtpAddress>**. |
| **Absenderdomäne** | Domäne des Absenders. |
| **Ziel** | Das Feld „An“ einer E-Mail-Nachricht. |
| **Eindeutig im E-Mail-Satz** | False, wenn ein Duplikat der Anlage in ihrem E-Mail-Satz vorhanden ist. |

## <a name="document-filters"></a>Dokumentfilter

| **Filters** | **Beschreibung** |
|:---------------------|:----------------|
| **Compliancebezeichnungen** | In Office 365 angewendete Compliancebezeichnungen. |
| **Erstellungszeit (UTC)** | Datum und Uhrzeit der Erstellung der Datei oder E-Mail-Nachricht. Datum und Uhrzeit werden in koordinierter Weltzeit (UTC) angegeben. |
| **Datum der letzten Änderung (UTC)** | Das Datum, an dem ein Dokument zuletzt geändert wurde. Datum und Uhrzeit werden in koordinierter Weltzeit (UTC) angegeben. |
| **Kategorie** | Der Erweiterungstyp der Datei. |
| **Benutzeraktivitätsereignisse** | Aktivität für Elemente im Zusammenhang mit bestimmten Benutzeraktivitäten in einem Fall.  Wenn Sie beispielsweise einen Link zu "Inhalt erkunden" für eine Aktivität auf der Seite **"Benutzeraktivität"** eines Falls auswählen, wird dieser Filter verwendet, um Elemente im Zusammenhang mit dieser Aktivität anzuzeigen. |
| **Arbeitsprodukt** | Der Typ des Arbeitsprodukts für das Dokument. Beispielsweise Anmerkungen oder Tags im Dokument. |
