---
title: Insider Risk Management-Inhalts-Explorer (Vorschau)
description: Informationen zum Insider Risk Management-Inhalts-Explorer in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a8c1c77bdfa3236ce8f2222fd21a7fba0535f149
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41590646"
---
# <a name="insider-risk-management-content-explorer-preview"></a>Insider Risk Management-Inhalts-Explorer (Vorschau)

Das Insider Risk Management Content Explorer ermöglicht Risikoanalysten und Ermittlern, den Kontext und die Details der in Warnungen erfassten Kommunikation zu untersuchen. Bei allen Warnungen werden Kopien von Daten und Nachrichtendateien als Momentaufnahme der Elemente archiviert, wobei die ursprünglichen Dateien und Nachrichten in den Speicherquellen beibehalten werden. Das Kopieren von Daten und Nachrichten ist für den der Warnung zugeordneten Mitarbeiter und den Besitzer des Inhalts transparent. Die Berechtigungseinstellungen und Zugriffsrechte für die Daten werden für den kopierten Inhalt und Nachrichten verwaltet, und Risikoanalysten und Ermittler benötigen diese Berechtigungen und Rechte, wenn Sie die Dateien öffnen und anzeigen müssen. Jeder Datei und jeder Nachricht wird im Fall des Insider Risikomanagements für Verwaltungszwecke automatisch eine eindeutige Datei-ID zugewiesen.

## <a name="column-options"></a>Spaltenoptionen

Um Risikoanalysten und Ermittlern das Überprüfen von erfassten Daten und Nachrichten und das Überprüfen des Kontexts auf den Fall zu erleichtern, sind mehrere Filter-und Sortier Tools im Inhalts-Explorer enthalten. Für die grundlegende Sortierung unterstützen die Spalten **Date** und **File Class** die Sortierung mithilfe der Spaltentitel im Inhalts Wartebereich. Andere Warteschlangen Spalten können zur Ansicht hinzugefügt werden, um unterschiedliche Pivots für die Dateien und Nachrichten bereitzustellen.

Verwenden Sie zum Hinzufügen oder Entfernen von Spaltenüberschriften für die Inhalts Warteschlange das Steuerelement **Spalten bearbeiten** , und wählen Sie eine der folgenden Spaltenoptionen aus. Diese Spalten entsprechen den im Inhalts-Explorer unterstützten allgemeinen, e-Mail-und Dokumenteigenschaften Bedingungen und werden weiter unten in diesem Thema aufgeführt.

| **Column-Option** | **Beschreibung** |
|:------------------|:----------------|
| **Autor** | Das Feld Autor aus Office-Dokumenten, das bleibt, wenn ein Dokument kopiert wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die e-Mails an eine andere Person weitergeben, die es dann in SharePoint hoch lädt, behält das Dokument weiterhin den ursprünglichen Autor bei. |
| **Bcc** | Für e-Mail-Nachrichten verfügbar, die Benutzer im Feld Bcc-Nachricht. |
| **Cc** | Für e-Mail-Nachrichten verfügbar, die Benutzer im Feld CC-Nachricht. |
| **Zusammengesetzter Pfad** | Mensch lesbarer Pfad, der die Quelle des Elements beschreibt. |
| **Unterhaltungs-ID** | Unterhaltungs-ID aus der Nachricht. |
| **Unterhaltungsindex** | Unterhaltungsindex aus der Nachricht. |
| **Erstellungszeitpunkt** | Die Zeit, zu der die Datei oder e-Mail-Nachricht erstellt wurde. |
| **Date** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Für Dokumente das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Dominantes Design** | Dominantes Design, berechnet für Analyse. |
| **E-Mail-ID festlegen** | Gruppen-ID für alle Nachrichten in derselben e-Mail-Gruppe. |
| **Familien-ID** | Familien-ID-Gruppen alle Elemente zusammen; für e-Mail umfasst dies die Nachricht und alle Anlagen; für Dokumente umfasst dies das Dokument und alle eingebetteten Elemente. |
| **File-Klasse** | Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: * * e-Mail oder **Anhang**. |
| **Datei-ID** | In der Anfrage eindeutige Dokument-ID. |
| **Dateityp Symbol** | Die Erweiterung einer Datei; beispielsweise docx, 1, PPTX oder xlsx. Dies ist die gleiche Eigenschaft wie die FileExtension-Website Eigenschaft. |
| **ID** | Der GUID-Bezeichner für die Datei. |
| **Unveränderliche ID** | Unveränderliche ID wie in Office 365 gespeichert. |
| **Inklusiv-Typ** | Integrativer Typ, berechnet für Analyse: **0** -nicht inklusive; **1** – inklusive; **2** – inklusive minus; **3** -inclusive-Kopie. |
| **Zuletzt geändert** | Das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Als repräsentativ gekennzeichnet** | Ein Dokument aus den einzelnen Sätzen exakter Duplikate wird als Repräsentanten markiert. |
| **Nachrichten Art** | Der Typ der zu suchenden e-Mail-Nachricht. Mögliche Werte: Kontakte, Dokumente, e-Mail, externe Daten, Faxe, Sofortnachrichten, Journale, Besprechungen, Microsoft Teams (gibt Elemente aus Chats, Besprechungen und anrufen in Microsoft Teams zurück), Notizen, Beiträge, RSSfeeds, Aufgaben, Voicemail |
| **Teilnehmer** | Liste aller Teilnehmer einer Nachricht; Beispiel: Sender, an, CC, BCC. |
| **Pivot-ID** | Die ID eines Pivots. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Empfangen“. |
| **Empfänger** | Alle Empfängerfelder in einer e-Mail-Nachricht. Diese Felder sind to, CC und Bcc. |
| **Vertreter-ID** | Numerischer Bezeichner der einzelnen Sätze exakter Duplikate. |
| **Absender** | Der Absender einer E-Mail-Nachricht. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Für Dokumente die im Feld Autor zitierte Person aus Office-Dokumenten. Sie können mehr als einen Namen eingeben, getrennt durch Kommas. Mindestens zwei Werte sind durch den or-Operator logisch miteinander verbunden. |
| **Sent** | Das Datum, an dem eine E-Mail vom Absender gesendet wurde. Dies ist die gleiche Eigenschaft wie die E-Mail-Eigenschaft „Gesendet“. |
| **Größe** | Für e-Mail und Dokumente die Größe des Elements (in Byte). |
| **Betreff** | Der Text in der Betreffzeile einer E-Mail. |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Für Dokumente der Titel des Dokuments. Wie bereits erläutert, ist die Title-Eigenschaft in Microsoft Office Dokumenten angegebene Metadaten. Sie können den Namen von mehr als einem Betreff/Titel eingeben, getrennt durch Kommas. Mindestens zwei Werte sind durch den or-Operator logisch miteinander verbunden. |
| **Themenliste** | Für Analyse berechnete Themenliste. |
| **Title** | Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in Office-Dokumenten angegeben sind. Er unterscheidet sich von dem Dateinamen des Dokuments. |
| **Ziel** | Der Empfänger einer e-Mail-Nachricht im Feld an. |

## <a name="advanced-search-conditions"></a>Erweiterte Suchbedingungen

Sie können Suchbedingungen hinzufügen, um den Umfang einer Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist logisch mit der Stichwortabfrage (im Feld Schlüsselwort angegeben) durch einen logischen Operator (der als c:c dargestellt wird) verbunden, der in der Funktionalität des and-Operators ähnelt. Das bedeutet, dass Elemente sowohl die Stichwortabfrage als auch eine oder mehrere Bedingungen erfüllen müssen, die in den Suchergebnissen enthalten sein sollen. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden.

Erweitern Sie für erweiterte Filter-und Such Tools den Bereich **Filter** auf der linken Seite der Inhalts Warteschlange. Wählen Sie die Schaltfläche **Bedingung hinzufügen** aus, um die Liste Bedingung zu öffnen:

### <a name="operators-used-with-conditions"></a>Mit Bedingungen verwendete Operatoren

|**Operator**|**Entsprechung in der Abfrage**|**Beschreibung**|
|:-----------|:-------------------|:--------------|
| **After** |`property>date`| Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die nach dem angegebenen Datum gesendet, empfangen oder geändert wurden.|
| **Before** |`property<date`| Wird mit Datumsbedingungen verwendet. Gibt die Elemente zurück, die vor dem angegebenen Datum gesendet, empfangen oder geändert wurden.|
| **Zwischen** |`date..date`| Wird mit Datums- und Größenbedingungen verwendet. Bei Verwendung mit einer Datumsbedingung werden Elemente zurückgegeben, die innerhalb des angegebenen Datumsbereichs gesendet, empfangen oder geändert wurden. Bei Verwendung mit einer Größenbedingung werden Elemente zurückgegeben, deren Größe innerhalb des angegebenen Bereichs liegt.|
| **Enthält alle** |`(property:value) OR (property:value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die einen oder mehrere angegebene Zeichenfolgenwerte enthalten. |
| **Contains any of** |`(property:value) OR (property:value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die mindestens einen Teil der angegebenen Zeichenfolgenwerte enthalten.|
| **Enthält keines der** |`-property:value`  <br/> `NOT property:value`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die keinen Teil des angegebenen Zeichenfolgenwerts enthalten.|
| **Entspricht nicht** |`-property=value`  <br/> `NOT property=value`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die die angegebene Zeichenfolge nicht enthalten.|
| **Gleich** |`size=value`| Gibt Elemente zurück, die der angegebenen Größe entsprechen. <sup>1</sup>|
| **Equals any of** |`(property=value) OR (property=value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die genau den angegebenen Zeichenfolgenwerten entsprechen.|
| **Entspricht keinem von** |`(property=value) OR (property=value)`| Wird mit Bedingungen für Eigenschaften verwendet, die einen Zeichenfolgenwert angeben. Gibt Elemente zurück, die nicht mit einem oder mehreren angegebenen Zeichenfolgenwerten übereinstimmen. |
| **Größer als** |`size>value`| Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer als der angegebene Wert ist. <sup>1</sup>|
| **Greater or equal** |`size>=value`| Gibt Elemente zurück, bei denen die angegebene Eigenschaft größer oder gleich dem angegebenen Wert ist. <sup>1</sup>|
| **Kleiner als** |`size<value`| Gibt Elemente zurück, die größer oder gleich dem angegebenen Wert sind. <sup>1</sup>|
| **Less or equal** |`size<=value`| Gibt Elemente zurück, die größer oder gleich dem angegebenen Wert sind. <sup>1</sup>|
| **Not equal** |`size<>value`| Gibt Elemente zurück, die nicht der angegebenen Größe entsprechen. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> dieser Operator steht nur für Bedingungen zur Verfügung, die die Size-Eigenschaft verwenden.

### <a name="common-property-conditions"></a>Allgemeine Eigenschaftenbedingungen

| **Bedingungs Option** | **Beschreibung** |
|:---------------------|:----------------|
| **Date** | Bei E-Mails: Das Datum, an dem die Nachricht vom Empfänger empfangen oder vom Absender gesendet wurde.   Für Dokumente das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Absender/Autor** | Bei E-Mails: Die Person, die eine Nachricht gesendet hat.  Für Dokumente die im Feld Autor zitierte Person aus Office-Dokumenten. Sie können mehr als einen Namen eingeben, getrennt durch Kommas. Mindestens zwei Werte sind durch den **or** -Operator logisch miteinander verbunden. |
| **Größe** | Für e-Mail und Dokumente die Größe des Elements (in Byte). |
| **Betreff/Titel** | Bei E-Mails: Der Text in der Betreffzeile einer Nachricht.   Für Dokumente der Titel des Dokuments. Bei der Title-Eigenschaft in Documents handelt es sich um in Microsoft Office Dokumenten angegebene Metadaten. Sie können den Namen von mehr als einem Betreff/Titel eingeben, getrennt durch Kommas. Mindestens zwei Werte sind durch den or-Operator logisch miteinander verbunden. |

### <a name="email-property-conditions"></a>Bedingungen für die e-Mail-Eigenschaft

In der folgenden Tabelle sind die Eigenschaftenbedingungen für e-Mail-Nachrichten aufgelistet, die im Inhalts-Explorer

| **Bedingungs Option** | **Beschreibung** |
|:---------------------|:----------------|
| **Bcc** | Das Feld "Bcc" einer e-Mail-Nachricht. |
| **Cc** | Das Feld "CC" einer e-Mail-Nachricht. |
| **E-Mail-Sicherheit** | Sicherheitseinstellung der Nachricht. |
| **E-Mail-Empfindlichkeit** | Empfindlichkeitseinstellung der Nachricht. |
| **E-Mail-ID festlegen** | Gruppen-ID für alle Nachrichten in derselben e-Mail-Gruppe. |
| **Von** | Der Absender einer E-Mail-Nachricht. |
| **Weist eine Anlage auf** | Gibt an, ob eine Nachricht eine Anlage enthält. Verwenden Sie die Werte **true** oder **false**. |
| **Importance** | Die Wichtigkeit einer E-Mail-Nachricht, die ein Absender festlegen kann, wenn er eine Nachricht sendet. Standardmäßig werden Nachrichten mit normaler Wichtigkeit gesendet, außer wenn der Absender die Wichtigkeit auf **Hoch** oder **Niedrig** setzt.   |
| **Enddatum der Besprechung** | Termin für Besprechungsende für Besprechungen. |
| **Besprechungs Startdatum** | Besprechungs Starttermin für Besprechungen. |
| **Nachrichten Art** | Der Typ der zu suchenden e-Mail-Nachricht. Mögliche Werte: Kontakte, Dokumente, e-Mail, externe Daten, Faxe, Sofortnachrichten, Journale, Besprechungen, Microsoft Teams (gibt Elemente aus Chats, Besprechungen und anrufen in Microsoft Teams zurück), Notizen, Beiträge, RSSfeeds, Aufgaben, Voicemail |
| **Teilnehmer Domäne** | Liste aller Domänen von Teilnehmern einer Nachricht. |
| **Teilnehmer** | Alle Personen Felder in einer e-Mail-Nachricht. Diese Felder sind von, in, CC und Bcc. |
| **Received** | Das Datum, an dem eine E-Mail-Nachricht von einem Empfänger empfangen wurde. |
| **Empfängerdomänen** | Liste aller Domänen der Empfänger einer Nachricht. |
| **Absender** | Absenderfeld (von) für Nachrichtentypen.  Das Format **ist \<DisplayName SmtpAddress>**. |
| **Absenderdomäne** | Domäne des Absenders. |
| **Betreff** | Der Text in der Betreffzeile einer E-Mail.  <br/> **Hinweis:** Wenn Sie die Subject-Eigenschaft in einer Abfrage verwenden, gibt die Suche alle Nachrichten zurück, in denen die Betreffzeile den gesuchten Text enthält. Mit anderen Worten: die Abfrage gibt nicht nur die Nachrichten zurück, die eine exakte Übereinstimmung aufweisen. Wenn Sie beispielsweise nach suchen `subject:"Quarterly Financials"`, enthalten Ihre Ergebnisse Nachrichten mit dem Betreff "Quarterly Financials 2018". |
| **Ziel** | Das Feld „An“ einer E-Mail-Nachricht. |
| **Eindeutig in e-Mail-Gruppe** | False, wenn in der e-Mail-Gruppe ein Duplikat der Anlage vorhanden ist. |

## <a name="document-property-conditions"></a>Dokument Eigenschaftsbedingungen

In der folgenden Tabelle sind die Dokumenteigenschaften Bedingungen aufgelistet, die im Inhalts-Explorer verfügbar sind. Viele dieser Eigenschaftsbedingungen werden mit Überprüfungs Sätzen gemeinsam verwendet, die in [erweiterten eDiscovery-Fällen](document-metadata-fields-in-Advanced-eDiscovery.md)enthalten sind.

| **Bedingungs Option** | **Beschreibung** |
|:---------------------|:----------------|
| **Anwalt-Client-Berechtigungs Bewertung** | Inhalts Ergebnis des Anwalts-Client-Berechtigungsmodells. |
| **Autor** | Das Feld Autor aus Office-Dokumenten, das bleibt, wenn ein Dokument kopiert wird. Wenn ein Benutzer beispielsweise ein Dokument erstellt und die e-Mails an eine andere Person weitergeben, die es dann in SharePoint hoch lädt, behält das Dokument weiterhin den ursprünglichen Autor bei. |
| **Konformitäts Bezeichnungen** | In Office 365 angewendete Kompatibilitäts Bezeichnungen. |
| **Zusammengesetzter Pfad** | Mensch lesbarer Pfad, der die Quelle des Elements beschreibt. |
| **Unterhaltungs-ID** | Unterhaltungs-ID aus der Nachricht. |
| **Erstellungszeitpunkt** | Die Zeit, zu der die Datei oder e-Mail-Nachricht erstellt wurde. |
| **Custodian** | Name der Depotbank, der das Element zugeordnet wurde. |
| **Dominantes Design** | Dominantes Design, berechnet für Analyse. |
| **Familien-ID** | Familien-ID-Gruppen alle Elemente zusammen; für e-Mail umfasst dies die Nachricht und alle Anlagen; für Dokumente umfasst dies das Dokument und alle eingebetteten Elemente. |
| **File-Klasse** | Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: * * e-Mail oder **Anhang**. |
| **Dateitypen** | Die Erweiterung einer Datei; beispielsweise docx, 1, PPTX oder xlsx. |
| **Hat Anwalts Teilnehmer** | True, wenn mindestens einer der Teilnehmer in der anwaltsliste gefunden wird; Andernfalls ist der Wert false. |
| **Unveränderliche ID** | Unveränderliche ID wie in Office 365 gespeichert. |
| **Inklusiv-Typ** | Integrativer Typ, berechnet für Analyse: **0** -nicht inklusive; **1** – inklusive; **2** – inklusive minus; **3** -inclusive-Kopie. |
| **Elementklasse** | Von Exchange Server bereitgestellte Item-Klasse; Beispiel: **IPM. Hinweis:** |
| **Zuletzt geändert** | Das Datum, an dem ein Dokument zuletzt geändert wurde. |
| **Laden-ID** | Laden-ID, in der das Element in einen Überprüfungs Satzes geladen wurde. |
| **Speicherort Name** | Zeichenfolge, die die Quelle des Elements angibt.  Für Exchange ist dies die SMTP-Adresse des Postfachs. Für SharePoint und OneDrive die URL der Websitesammlung. |
| **Als repräsentativ gekennzeichnet** | Ein Dokument aus den einzelnen Sätzen exakter Duplikate wird als Repräsentanten markiert. |
| **Native Dateierweiterung** | Systemeigene Erweiterung des Elements. |
| **Name der systemeigenen Datei** | Name des systemeigenen Datei namens des Elements. |
| **NdEtSortExclAttach** | Verkettung von e-Mail-Sätzen und ND-Sätzen zur effizienten Sortierung zur Überprüfungszeit; D wird als Präfix zu ND-Sätzen hinzugefügt, und e wird e-Mail-Sätzen hinzugefügt. |
| **Pivot-ID** | Die ID eines Pivots. |
| **Potenziell privilegiert** | True, wenn das Dokument vom Typ "Anwalts Client-Rechte Erkennung" potenziell privilegiert wird. |
| **Verarbeitungsstatus** | Verarbeitungsstatus, nachdem das Element zu einem Überprüfungs Sätze hinzugefügt wurde. |
| **Quantil lesen** | Lesen Sie Quantil für das Dokument basierend auf Relevanz. |
| **Relevanz-Ergebnis** | Relevanz-Score eines Dokuments, das auf Relevanz basiert. |
| **Relevanz-Tag** | Relevanz-Score eines Dokuments, das auf Relevanz basiert. |
| **Vertreter-ID** | Numerischer Bezeichner der einzelnen Sätze exakter Duplikate. |
| **Tags** | In einem Überprüfungs Satzes angewendete Tags. |
| **Themenliste** | Für Analyse berechnete Themenliste. |
| **Title** | Der Titel des Dokuments. Die Title-Eigenschaft sind Metadaten, die in Office-Dokumenten angegeben sind. Er unterscheidet sich von dem Dateinamen des Dokuments. |
| **Wurde behoben** | True, wenn das Element behoben wurde, andernfalls false. |
| **Wörter zählen** | Die Anzahl der Wörter in einer Datei. |
