---
title: Insider-Risikomanagement Inhalts-Explorer
description: Erfahren Sie mehr über insider risk management Content Explorer in Microsoft 365
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
ms.openlocfilehash: ac5c423bffaa40d1b8cfbc50c68b1ca3f98ed0e6
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819848"
---
# <a name="insider-risk-management-content-explorer"></a>Insider-Risikomanagement Inhalts-Explorer

Der **Insider-Risikomanagement-Inhalts-Explorer** ermöglicht Benutzern, denen die Rolle *"Insider Risk Management Investigators"* zugewiesen wurde, den Kontext und details der Inhalte zu untersuchen, die mit Aktivitäten in Warnungen verknüpft sind. Die Falldaten im Inhalts-Explorer werden täglich aktualisiert, um neue Aktivitäten zu enthalten. Bei allen Warnungen, die für einen Fall bestätigt werden, werden Kopien von Daten- und Nachrichtendateien zur Zeit der Elemente als Momentaufnahme archiviert, während die ursprünglichen Dateien und Nachrichten in den Speicherquellen beibehalten werden. Das Kopieren von Daten und Nachrichten ist für den Benutzer, der der Warnung zugeordnet ist, und für den Besitzer des Inhalts transparent. Bei neuen Fällen dauert es in der Regel etwa eine Stunde, bis Inhalte im Inhalts-Explorer auffüllen. Bei Fällen mit großen Inhaltsmengen kann es länger dauern, bis eine Momentaufnahme erstellt wird. Wenn Inhalte weiterhin im Inhalts-Explorer geladen werden, wird ein Fortschrittsindikator angezeigt, der den Fertigstellungsprozentsatz anzeigt.

In einigen Fällen sind daten, die einem Fall zugeordnet sind, möglicherweise nicht als Momentaufnahme zur Überprüfung im Inhalts-Explorer verfügbar. Diese Situation kann auftreten, wenn Falldaten gelöscht oder verschoben wurden oder wenn bei der Verarbeitung von Falldaten ein temporärer Fehler auftritt. In diesem Fall wählen Sie **Dateien** in der Warnleiste anzeigen aus, um die Dateinamen, den Dateipfad und den Grund für den Fehler für jede Datei anzeigen. Bei Bedarf können diese Informationen in eine CSV-Datei (durch Kommas getrennte Werte) exportiert werden.

Wenn der Inhalt Berechtigungen für die Verwaltung von Informationsrechten enthält, werden diese Berechtigungen für die kopierten Inhalte verwaltet, und Benutzer, denen die Rolle *Insider Risk Management Investigators* zugewiesen ist, benötigen diese Berechtigungen und Rechte, wenn sie die Dateien öffnen und anzeigen müssen. Jeder Datei und Nachricht wird automatisch eine eindeutige Datei-ID im Fall des Insiderrisikomanagements zu Verwaltungszwecken zugewiesen. Dokumente, die Mit Geräteindikatoraktivitäten verknüpft sind, sind nicht im Inhalts-Explorer enthalten.

![Insider-Risikomanagement Inhalts-Explorer](../media/insider-risk-content-explorer.png)

>[!Note]
>Der Inhalts-Explorer enthält Aktivitäten im Zusammenhang mit Microsoft Office Dateien. Aktivitäten auf Websiteebene, z. B. wenn eine SharePoint-Website gelöscht wird oder Wenn Websiteberechtigungen geändert werden, werden nicht im Inhalts-Explorer enthalten.

## <a name="column-options"></a>Spaltenoptionen

Um Risikoanalysten und Ermittlern die Überprüfung erfasster Daten und Nachrichten zu erleichtern und den Kontext für den Fall zu überprüfen, sind mehrere Filter- und Sortiertools im Inhalts-Explorer enthalten. Für die einfache Sortierung unterstützen die **Klassenspalten Date** und **File** die Sortierung mithilfe der Spaltentitel im Inhaltswarteschlangenbereich. Andere Warteschlangenspalten können der Ansicht hinzugefügt werden, um unterschiedliche Pivots für die Dateien und Nachrichten zur Verfügung zu stellen.

Verwenden Sie zum Hinzufügen oder Entfernen von Spaltenüberschriften für die Inhaltswarteschlange das **Steuerelement** Spalten bearbeiten, und wählen Sie aus den folgenden Spaltenoptionen aus. Diese Spalten werden den allgemeinen, E-Mail- und Dokumenteigenschaftsbedingungen zuordnung, die im Inhalts-Explorer unterstützt und weiter unten in diesem Artikel aufgeführt werden.

| **Spaltenoption** | **Beschreibung** |
|:------------------|:----------------|
| **Autor** | Das Autorenfeld aus Office-Dokumenten, das beibehalten wird, wenn ein Dokument kopiert wird. Wenn beispielsweise ein Benutzer ein Dokument erstellt und die E-Mails an eine andere Person senden, die es dann in SharePoint hochlädt, behält das Dokument weiterhin den ursprünglichen Autor bei. |
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
| **Unveränderliche ID** | Unveränderliche ID wie in Office 365 gespeichert. |
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
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten wird die im Feld Autor aus Office-Dokumenten zitierte Person verwendet. Sie können mehrere Namen eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den OR-Operator verbunden. |
| **Typen vertraulicher Informationen** | Die vertraulichen Informationstypen, die im Inhalt identifiziert werden. |
| **Vertraulichkeitsbezeichnungen** | Die Vertraulichkeitsbezeichnungen, die auf den Inhalt angewendet werden. |
| **Sent** | Das Datum, an dem eine E-Mail vom Absender gesendet wurde. Dieses Feld ist die gleiche Eigenschaft wie die Sent email-Eigenschaft. |
| **Größe** | Für E-Mails und Dokumente die Größe des Elements (in Bytes). |
| **Betreff** | Der Text in der Betreffzeile einer E-Mail. |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Wie bereits erläutert, handelt es sich bei der Title-Eigenschaft um Metadaten, die in Microsoft Office sind. Sie können den Namen von mehreren Betreff/Titeln eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den OR-Operator verbunden. |
| **Liste der Designs** | Designs list as calculated for analytics. |
| **Titel** | Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in Office-Dokumenten angegeben sind. Er ist anders als der Dateiname des Dokuments. |
| **Bis** | Der Empfänger einer E-Mail-Nachricht im Feld An. |

## <a name="advanced-search-conditions"></a>Erweiterte Suchbedingungen

Sie können Suchbedingungen hinzufügen, um den Bereich einer Suche zu eindrücken und einen verfeinerteren Satz von Ergebnissen zurücksennen. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung wird logisch mit der Schlüsselwortabfrage (im Schlüsselwortfeld angegeben) durch einen logischen Operator (der als c:c dargestellt wird) verbunden, der in der Funktionalität dem AND-Operator ähnelt. Das bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch eine oder mehrere Bedingungen erfüllen müssen, die in die Suchergebnisse eingeschlossen werden sollen. Mit dieser Funktionalität können Sie ihre Ergebnisse mithilfe von Bedingungen einenknen.

Erweitern Sie für erweiterte Filter- und Suchtools den **Bereich Filter** auf der linken Seite der Inhaltswarteschlange. Wählen Sie die **Schaltfläche Bedingung hinzufügen** aus, um die Bedingungsliste zu öffnen:

### <a name="operators-used-with-conditions"></a>Mit Bedingungen verwendete Operatoren

|**Operator**|**Entsprechung in der Abfrage**|**Beschreibung**|
|:-----------|:-------------------|:--------------|
| **After** |`property>date`| Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die nach dem angegebenen Datum gesendet, empfangen oder geändert wurden.|
| **Before** |`property<date`| Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die vor dem angegebenen Datum gesendet, empfangen oder geändert wurden.|
| **Between** |`date..date`| Wird mit Datums- und Größenbedingungen verwendet. Bei Verwendung mit einer Datumsbedingung werden Elemente zurückgegeben, die innerhalb des angegebenen Datumsbereichs gesendet, empfangen oder geändert wurden. Bei Verwendung mit einer Größenbedingung werden Elemente zurückgegeben, deren Größe innerhalb des angegebenen Bereichs liegt.|
| **Enthält alle** |`(property:value) OR (property:value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die alle angegebenen Zeichenfolgenwerte enthalten. |
| **Contains any of** |`(property:value) OR (property:value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die mindestens einen Teil der angegebenen Zeichenfolgenwerte enthalten.|
| **Enthält keines von** |`-property:value`  <br/> `NOT property:value`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die keinen Teil des angegebenen Zeichenfolgenwerts enthalten.|
| **Entspricht keinem der** |`-property=value`  <br/> `NOT property=value`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die die angegebene Zeichenfolge nicht enthalten.|
| **Gleich** |`size=value`| Gibt Elemente zurück, die der angegebenen Größe entspricht. <sup>1</sup>|
| **Equals any of** |`(property=value) OR (property=value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die genau den angegebenen Zeichenfolgenwerten entsprechen.|
| **Entspricht keinem der** |`(property=value) OR (property=value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die nicht mit einem oder mehreren angegebenen Zeichenfolgenwerten übereinstimmen. |
| **Größer als** |`size>value`| Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer als der angegebene Wert ist. <sup>1</sup>|
| **Greater or equal** |`size>=value`| Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer oder gleich dem angegebenen Wert ist. <sup>1</sup>|
| **Kleiner als** |`size<value`| Gibt Elemente zurück, die größer oder gleich dem bestimmten Wert sind. <sup>1</sup>|
| **Less or equal** |`size<=value`| Gibt Elemente zurück, die größer oder gleich dem bestimmten Wert sind. <sup>1</sup>|
| **Not equal** |`size<>value`| Gibt Elemente zurück, die nicht der angegebenen Größe entspricht. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> Dieser Operator ist nur für Bedingungen verfügbar, die die Size-Eigenschaft verwenden.

### <a name="common-property-conditions"></a>Allgemeine Eigenschaftenbedingungen

| **Bedingungsoption** | **Beschreibung** |
|:---------------------|:----------------|
| **Date** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Für Dokumente das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Bei Dokumenten wird die im Feld Autor aus Office-Dokumenten zitierte Person verwendet. Sie können mehrere Namen eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den **OR-Operator** verbunden. |
| **Größe** | Für E-Mails und Dokumente die Größe des Elements (in Bytes). |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Bei Dokumenten der Titel des Dokuments. Die Title-Eigenschaft in Dokumenten sind Metadaten, die in Microsoft Office angegeben sind. Sie können den Namen von mehreren Betreff/Titeln eingeben, getrennt durch Kommas. Zwei oder mehr Werte werden logisch durch den OR-Operator verbunden. |

### <a name="email-property-conditions"></a>Bedingungen der E-Mail-Eigenschaft

In der folgenden Tabelle sind die im Inhalts-Explorer verfügbaren Bedingungen für die E-Mail-Nachrichteneigenschaft aufgeführt.

| **Bedingungsoption** | **Beschreibung** |
|:---------------------|:----------------|
| **Bcc** | Das Feld Bcc einer E-Mail-Nachricht. |
| **Cc** | Das Cc-Feld einer E-Mail-Nachricht. |
| **E-Mail-Sicherheit** | Sicherheitseinstellung der Nachricht. |
| **E-Mail-Vertraulichkeit** | Vertraulichkeitseinstellung der Nachricht. |
| **E-Mail-Satz-ID** | Gruppen-ID für alle Nachrichten im gleichen E-Mail-Satz. |
| **From** | Der Absender einer E-Mail-Nachricht. |
| **Verfügt über Eine Anlage** | Gibt an, ob eine Nachricht über eine Anlage verfügt. Verwenden Sie die **Werte true** oder **false**. |
| **Importance** | Die Wichtigkeit einer E-Mail-Nachricht, die ein Absender festlegen kann, wenn er eine Nachricht sendet. Standardmäßig werden Nachrichten mit normaler Wichtigkeit gesendet, außer wenn der Absender die Wichtigkeit auf **Hoch** oder **Niedrig** setzt.   |
| **Enddatum der Besprechung** | Enddatum der Besprechung für Besprechungen. |
| **Anfangsdatum der Besprechung** | Besprechungsanfangsdatum für Besprechungen. |
| **Nachrichten art** | Der Typ der E-Mail-Nachricht, nach der gesucht werden soll. Mögliche Werte: Kontakte, Dokumente, E-Mails, externe Daten, Faxe, Im, Journale, Besprechungen, Microsoft Teams (gibt Elemente aus Chats, Besprechungen und Anrufen in Microsoft Teams zurück), Notizen, Beiträge, rssfeeds, Aufgaben, Voicemail |
| **Teilnehmerdomäne** | Liste aller Domänen der Teilnehmer einer Nachricht. |
| **Teilnehmer** | Alle Personenfelder in einer E-Mail-Nachricht. Diese Felder sind From, To, Cc und Bcc. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. |
| **Empfängerdomänen** | Liste aller Domänen von Empfängern einer Nachricht. |
| **Sender** | Absenderfeld (Von) für Nachrichtentypen.  Format ist **DisplayName \<SmtpAddress>**. |
| **Absenderdomäne** | Domäne des Absenders. |
| **Betreff** | Der Text in der Betreffzeile einer E-Mail.  <br/> **Hinweis:** Wenn Sie die Subject-Eigenschaft in einer Abfrage verwenden, gibt die Suche alle Nachrichten zurück, in denen die Betreffzeile den gesuchten Text enthält. Mit anderen Worten, die Abfrage gibt nicht nur nachrichten zurück, die eine genaue Übereinstimmung haben. Wenn Sie z. B. nach suchen, enthalten Ihre Ergebnisse Nachrichten mit dem Betreff `subject:"Quarterly Financials"` "Quarterly Financials 2018". |
| **Bis** | Das Feld „An“ einer E-Mail-Nachricht. |
| **Eindeutig in E-Mail-Satz** | False, wenn ein Duplikat der Anlage im E-Mail-Satz vorhanden ist. |

## <a name="document-property-conditions"></a>Bedingungen für Die Dokumenteigenschaft

In der folgenden Tabelle sind eigenschaftenbedingungen für Dokumente aufgeführt, die im Inhalts-Explorer verfügbar sind. Viele dieser Eigenschaftenbedingungen werden für Überprüfungssätze freigegeben, die in [Advanced eDiscovery-Fällen enthalten sind.](document-metadata-fields-in-Advanced-eDiscovery.md)

| **Bedingungsoption** | **Beschreibung** |
|:---------------------|:----------------|
| **Anwalts-Client-Berechtigungsergebnis** | Bewertung der Inhalte des Anwalts-Client-Berechtigungsmodells. |
| **Autor** | Das Autorenfeld aus Office-Dokumenten, das beibehalten wird, wenn ein Dokument kopiert wird. Wenn beispielsweise ein Benutzer ein Dokument erstellt und die E-Mails an eine andere Person senden, die es dann in SharePoint hochlädt, behält das Dokument weiterhin den ursprünglichen Autor bei. |
| **Konformitätsbezeichnungen** | In Office 365 angewendete Compliancebezeichnungen. |
| **Zusammengesetzter Pfad** | Vom Menschen lesbarer Pfad, der die Quelle des Elements beschreibt. |
| **Unterhaltungs-ID** | Unterhaltungs-ID aus der Nachricht. |
| **Erstellungszeitpunkt** | Der Zeitpunkt, zu dem die Datei oder E-Mail-Nachricht erstellt wurde. |
| **Custodian** | Name des Verwahrers, dem das Element zugeordnet war. |
| **Dominantes Design** | Dominantes Design, wie für analysen berechnet. |
| **Familien-ID** | Familien-ID-Gruppen alle Elemente; Für E-Mails enthält dieses Feld die Nachricht und alle Anlagen. für Dokumente enthält dieses Feld das Dokument und alle eingebetteten Elemente. |
| **Dateiklasse** | Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: **E-Mail oder **Anlage**. |
| **Dateitypen** | Die Erweiterung einer Datei; Beispiel: docx, one, pptx oder xlsx. |
| **Hat Anwaltsteilnehmer** | True, wenn mindestens einer der Teilnehmer in der Anwaltsliste gefunden wird. Andernfalls ist der Wert False. |
| **Unveränderliche ID** | Unveränderliche ID wie in Office 365 gespeichert. |
| **Inklusiver Typ** | Inklusiver Typ, der für die Analyse berechnet wird: **0** – nicht einschließlich; **1** – einschließlich; **2** – inklusives Minus; **3** – inklusive Kopie. |
| **Elementklasse** | Vom #A0 bereitgestellte Elementklasse; z. **B. IPM. Hinweis** |
| **Zuletzt geändert** | Das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Lade-ID** | Load ID, in der das Element in einen Überprüfungssatz geladen wurde. |
| **Ortsname** | Zeichenfolge, die die Quelle des Elements identifiziert.  Für Exchange ist dieses Feld die SMTP-Adresse des Postfachs. Für SharePoint und OneDrive die URL zur Websitesammlung. |
| **Als repräsentativ gekennzeichnet** | Ein Dokument aus jedem Satz exakter Duplikate wird als Vertreter gekennzeichnet. |
| **Native Dateierweiterung** | Native Erweiterung des Elements. |
| **Systemeigener Dateiname** | Systemeigener Dateiname des Elements. |
| **NdEtSortExclAttach** | Verkettung von E-Mail-Satz und ND-Satz für effiziente Sortierung zur Überprüfungszeit; D wird als Präfix zu ND-Sätzen und E zu E-Mail-Sätzen hinzugefügt. |
| **Pivot-ID** | Die ID eines Pivots. |
| **Potenziell privilegiert** | True, wenn das Erkennungsmodell der Anwalts-Client-Rechte das Dokument als potenziell privilegiert betrachtet. |
| **Verarbeitungsstatus** | Verarbeitungsstatus, nachdem das Element einem Überprüfungssatz hinzugefügt wurde. |
| **Perzentil lesen** | Lesen Sie perzentil für das Dokument basierend auf Relevanz. |
| **Relevanzpunktzahl** | Relevanzpunktzahl eines Dokuments basierend auf Relevanz. |
| **Relevanztag** | Relevanzpunktzahl eines Dokuments basierend auf Relevanz. |
| **Repräsentative ID** | Numerischer Bezeichner für jeden Satz exakter Duplikate. |
| **Tags** | Tags, die in einem Überprüfungssatz angewendet werden. |
| **Liste der Designs** | Designs list as calculated for analytics. |
| **Titel** | Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in Office-Dokumenten angegeben sind. Er ist anders als der Dateiname des Dokuments. |
| **Wurde behoben** | True, wenn das Element behoben wurde, andernfalls False. |
| **Wörter zählen** | Die Anzahl der Wörter in einer Datei. |
