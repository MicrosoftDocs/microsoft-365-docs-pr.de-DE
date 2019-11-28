---
title: Dokumentmetadaten-Felder in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 51f242408e749e7d9bde60a9d462d4a9156f68fc
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633584"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Dokumentmetadaten-Felder in Advanced eDiscovery

In der folgenden Tabelle sind die Metadatenfelder für Dokumente in einer Überprüfungsgruppe in einem Fall in Advanced eDiscovery aufgeführt. Die Tabelle enthält die folgenden Informationen:

- Der Name des Metadatenfelds (in der Spalte **Feldname** ).

- Der Name der Eigenschaft, nach der Sie suchen können, wenn Sie eine [Überprüfungs Sätze-Abfrage](review-set-search.md) (in der Spalte **durchsuchbaren Feldnamen** ) durchführen. Eine leere Zelle bedeutet, dass Sie nicht nach dem Feld in einer Abfrage mit Überprüfungs Sätzen suchen können.

- Der Name des Metadatenfelds, das beim Exportieren von Dokumenten enthalten ist (in der Spalte **exported Field Name** ).  Eine leere Zelle bedeutet, dass das Feld Meta Data nicht in den exportierten Metadaten enthalten ist.

- Der Name des Metadatenfelds, das beim Anzeigen der Datei Metadaten eines ausgewählten Dokuments in einer Überprüfungsgruppe angezeigt wird (in der Spalte **Anzeige Feldname** ). Eine leere Zelle bedeutet, dass das Feld Meta Data beim Anzeigen der Datei Metadaten eines Dokuments nicht enthalten ist.

- Eine Beschreibung des Felds "Meta Data" (in der **Spalte "Description**").

| Feldname | Durchsuchbarer Feldname | Name des exportierten Felds | Anzeigefeld Name | Beschreibung |
| :- |  :- |  :- |  :- |  :- |
| Anlageninhalts-ID | AttachmentContentId |  | Anlageninhalts-ID | Anlageninhalts-ID des Elements. |
| Anlagennamen | AttachmentNames | Attachment_Names | Anlagennamen | Liste der Namen von Anlagen. |
| Anwalts Kunde-Berechtigungs Bewertung | AttorneyClientPrivilegeScore |  | Anwalts Kunde-Berechtigungs Bewertung | Inhalts Ergebnis des Anwalts-Client-Berechtigungsmodells. |
| Ursprung | Ursprung | Doc_authors | Ursprung | Autor aus den Dokumentmetadaten. |
| BCC | Bcc | Email_bcc | BCC | BCC-Feld für Nachrichtentypen.  Das Format **ist \<DisplayName SMTPAddress>**. |
| CC | Cc | Email_cc | CC | Feld CC für Nachrichtentypen.  Das Format **ist \<DisplayName SMTPAddress>**. |
| Konformitäts Bezeichnungen | ComplianceLabels | Compliance_labels | Konformitäts Bezeichnungen | In Office 365 angewendete Kompatibilitäts Bezeichnungen. |
| Zusammengesetzter Pfad | CompoundPath | Compound_path | Zusammengesetzter Pfad | Mensch lesbarer Pfad, der die Quelle des Elements beschreibt. |
| Inhalt | Inhalt |  |  | Extrahierter Text des Elements. |
| Unterhaltungs Text | Unterhaltungs Text |  | Unterhaltungs Text | Unterhaltungs Text des Elements. |
| Thema "Unterhaltung" | Thema "Unterhaltung" |  | Thema "Unterhaltung" | Unterhaltungsthema des Elements. |
| Unterhaltungs-ID | ConversationId | Conversation_ID | Unterhaltungs-ID | Unterhaltungs-ID aus der Nachricht. |
| Unterhaltungs Index |  | Conversation_index | Unterhaltungs Index | Unterhaltungsindex aus der Nachricht. |
| Unterhaltungs-PDF-Zeit | ConversationPdfTime |  | Unterhaltungs-PDF-Zeit | Datum, an dem die PDF-Version der Unterhaltung erstellt wurde. |
| Brennen der unter Haltungs-Zeit | ConversationRedactionBurnTime |  | Brennen der unter Haltungs-Zeit | Datum, an dem die PDF-Version der Unterhaltung für Chat erstellt wurde. |
| Erstelltes Dokumentdatum | CreatedTime | Doc_date_created | Erstelltes Dokumentdatum | Erstellungsdatum aus Dokumentmetadaten. |
| Custodian | Custodian | Custodian | Custodian | Name der Depotbank, der das Element zugeordnet wurde. |
| Datum | Datum | Datum | Datum | Date ist ein berechnetes Feld, das vom Dateityp abhängt.<br />**E-Mail**: Sendedatum<br />**E-Mail-Anlagen**: Datum der letzten Änderung des Dokuments, falls nicht verfügbar, das gesendete Datum des übergeordneten Elements<br />**Eingebettete Dokumente**: Datum der letzten Änderung des Dokuments, falls nicht verfügbar, Datum der letzten Änderung des übergeordneten Elements.<br />**SPO-Dokumente (enthält moderne Anlagen)**: Datum der letzten Änderung in SharePoint, falls nicht verfügbar, Datum der letzten Änderung der Dokumente<br />**Nicht-Office-Dokumente**: Datum der letzten Änderung<br />**Besprechungen**: Startdatum der Besprechung<br />**Voicemail**: Sendedatum<br />**Chat**: Datum gesendet. |
| Andere Pfade | Dedupedcompoundpath | Deduped_compound_path | Andere Pfade | Liste der zusammengesetzten Pfade von Dokumenten, bei denen es sich um exakte Duplikate (e-Mail: basierend auf Inhalt, Dokumente: basierend auf Hash) handelt. |
| Andere depotverwalter | DedupedCustodians | Deduped_custodians | Andere depotverwalter | Liste der Verwalter von Dokumenten, bei denen es sich um exakte Duplikate (für e-Mail: basierend auf Inhalt; für Dokumente: basierend auf Hash) handelt. |
| Andere Datei-IDs | DedupedFileIds | Deduped_file_IDs | Andere Datei-IDs | Liste der Datei-IDs von Dokumenten, bei denen es sich um exakte Duplikate (für e-Mail: basierend auf Inhalt; für Dokumente: basierend auf Hash) handelt. |
| Dokument Kommentare | DocComments | Doc_comments | Dokument Kommentare | Kommentare aus den Dokumentmetadaten. |
| Dokument Unternehmen |  | Doc_company | Dokument Unternehmen | Unternehmen aus den Dokumentmetadaten. |
| DocIndex |  |  |  | Der Index in der Familie. -1 oder 0 bedeutet, dass es sich um den Stamm handelt. |
| Dokument Schlüsselwörter |  | Doc_keywords | Dokument Schlüsselwörter | Schlüsselwörter aus den Dokumentmetadaten. |
| Dokument geändert von |  | Doc_modified_by | Dokument geändert von | Datum der letzten Änderung nach aus Dokumentmetadaten. |
| Dokument Revision |  | Doc_revision | Dokument Revision | Revision aus den Dokumentmetadaten. |
| Dokument Betreff |  | Doc_subject | Dokument Betreff | Betreff aus den Dokumentmetadaten. |
| Dokumentvorlage |  | Doc_template | Dokumentvorlage | Vorlage aus den Dokumentmetadaten. |
| Dominantes Design | DominantTheme | Dominant_theme | Dominantes Design | Dominantes Design, berechnet für Analyse. |
| Doppelte Teilmenge |  | Duplicate_subset | Doppelte Teilmenge | Gruppen-ID für exakte Duplikate. |
| E-Mail-Adresse |  | Email_action |  | Keine, Antworten, weiterleiten basierend auf der Betreffzeile einer Nachricht. |
| E-Mail-Zustellungsbestätigung |  | Email_delivery_receipt | E-Mail-Zustellungsbestätigung | In Internet Kopfzeilen angegebene e-Mail-Adresse für Übermittlungsbestätigung. |
| Importance | EmailImportance | Email_importance | Importance | Wichtigkeit der Nachricht: **0**: Low; **1**: normal; **2**: hoch |
| EmailLevel |  | Email_level |  | Gibt die Ebene einer Nachricht innerhalb des e-Mail-Threads an, zu dem Sie gehört. Anlagen erben den Wert der übergeordneten Nachricht. |
| E-Mail-Nachrichten-ID |  | Email_message_ID | E-Mail-Nachrichten-ID | Internet Nachrichten-ID aus der Nachricht. |
| EmailReadReceipt |  | Email_read_receipt |  | E-Mail-Adresse, die in Internet Kopfzeilen zur Lesebestätigung angegeben wird. |
| E-Mail-Sicherheit | EmailSecurity | Email_security | E-Mail-Sicherheit | Sicherheitseinstellung der Nachricht: **0**: None; **1**: signiert; **2**: verschlüsselt; **3**: verschlüsselt und signiert. |
| E-Mail-Empfindlichkeit | EmailSensitivity | email_sensitivity | E-Mail-Empfindlichkeit | Empfindlichkeitseinstellung der Nachricht: **0**: None; **1**: persönlich; **2**: privat; **3**: CompanyConfidential. |
| E-Mail-Gruppe | E-Mail-Set | Email_set | E-Mail-Gruppe | Gruppen-ID für alle Nachrichten in derselben e-Mail-Gruppe. |
| EmailThread |  | Email_thread |  | Position der Nachricht innerhalb des e-Mail-Satzes; besteht aus allen Knoten-IDs vom Stamm bis zur aktuellen Nachricht, Punkt getrennt. |
| Extrahierter Inhaltstyp |  | Extracted_content_type | Extrahierter Inhaltstyp | Extrahierter Inhaltstyp in Form von MIME-Typ; Beispiel: Image/JPEG. |
| ExtractedTextLength |  | Extracted_text_length |  | Anzahl der Zeichen im extrahierten Text. |
| Familien Relevanz-Ergebnis Fall Problem 1 |  | Family_relevance_score_case_issue_1 |  | Familien Relevanz-Ergebnis Fall Ausgabe 1 aus Relevanz. |
| FamilyDuplicateSet |  | Family_duplicate_set |  | Numerischer Bezeichner für Familien, die exakte Duplikate von einander (gleicher Inhalt und alle gleichen Anlagen) sind. |
| Familien-ID | FamilyID | Family_ID | Familien-ID | Familien-ID-Gruppen alle Elemente zusammen; für e-Mail umfasst dies die Nachricht und alle Anlagen; für Dokumente umfasst dies das Dokument und alle eingebetteten Elemente. |
| Familiengröße |  | Family_size | Familiengröße | Die Anzahl der Dokumente in der Familie. |
| Datei Relevanz-Ergebnis Fall Problem 1 |  | File_relevance_score_case_issue_1 |  | Datei Relevanz-Ergebnis Fall Problem 1 aus Relevanz. |
| File-Klasse | Fileclass | File_class | File-Klasse | Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: * * e-Mail oder **Anhang**. |
| Datei-ID | FileId | File_ID | Datei-ID | In der Anfrage eindeutige Dokument-ID.|
| Erstelltes Dateisystem Datum |  | File_system_date_created | Erstelltes Dateisystem Datum | Erstellungsdatum aus dem Dateisystem (gilt nur für nicht Office 365 Daten). |
| Dateisystem Datum geändert |  | File_system_date_modified | Dateisystem Datum geändert | Änderungsdatum aus dem Dateisystem (gilt nur für nicht Office 365 Daten). |
| Dateityp | FileType |  | Dateityp | Dateityp des Elements, basierend auf der Dateierweiterung. |
| Weist eine Anlage auf | HasAttachment | Email_has_attachment | Weist eine Anlage auf | Gibt an, ob die Nachricht Anlagen enthält. |
| Hat Anwalt | HasAttorney |  | Hat Anwalt | True, wenn mindestens einer der Teilnehmer in der anwaltsliste gefunden wird; Andernfalls ist der Wert false. |
| HasText |  | Has_text |  | Gibt an, ob das Element über Text verfügt, mögliche Werte sind true und false. |
| Unveränderliche ID | Unveränderlich | Immutable_ID | Unveränderliche ID | Unveränderliche ID wie in Office 365 gespeichert. |
| Inklusiv-Typ | Inklusivtype | Inclusive_type | Inklusiv-Typ | Integrativer Typ, berechnet für Analyse: **0** -nicht inklusive; **1** – inklusive; **2** – inklusive minus; **3** -inclusive-Kopie. |
| In Antwort an ID |  | In_reply_to_ID | In Antwort an ID | In Antwort an ID aus der Nachricht. |
| Ist repräsentativ | Isrepresentative | Is_representative | Ist repräsentativ | Ein Dokument in jeder Gruppe exakter Duplikate wird als repräsentativ gekennzeichnet. |
| Elementklasse | ItemClass | Item_class | Elementklasse | Von Exchange Server bereitgestellte Item-Klasse; Beispiel: **IPM. Hinweis:** |
| Datum der letzten Änderung | LastModifiedDate | Doc_date_modified | Datum der letzten Änderung | Datum der letzten Änderung aus Dokumentmetadaten. |
| Laden-ID | Lade-Nr | Load_ID | Laden-ID | Laden-ID, in der das Element in einen Überprüfungs Satzes geladen wurde. |
| Ort | Ort | Ort | Ort | Zeichenfolge, die den Typ des Speicherorts angibt, aus dem Dokumente stammen;<br />Importierte Daten nicht-O365-#a0<br />Teams – #a0 Teams<br />Exo-#a0 Exchange<br />SPO-#a0 SharePoint<br />OneDrive für Unternehmen-#a0 OneDrive |
| Speicherort Name | LocationName | Location_name | Speicherort Name | Zeichenfolge, die die Quelle des Elements angibt.  Für Exchange ist dies die SMTP-Adresse des Postfachs.  Für SharePoint und OneDrive die URL der Websitesammlung. |
| Als repräsentativ gekennzeichnet | MarkAsRepresentative |  | Als repräsentativ gekennzeichnet | Ein Dokument aus den einzelnen Sätzen exakter Duplikate wird als Repräsentanten markiert. |
| Als Pre-Tagged-Case-Problem 1 markiert |  | Marked_as_pre_tagged_Case_issue_1 |  | Als vorab markiertes Fall Problem 1 von Relevanz gekennzeichnet. |
| Markiert als Ausgangsfall Problem 1 |  | Marked_as_seed_Case_issue_1 |  | Als Ausgangsfall Problem 1 von Relevanz gekennzeichnet. |
| Enddatum der Besprechung | MeetingEndDate | Meeting_end_date | Enddatum der Besprechung | Termin für Besprechungsende für Besprechungen. |
| Besprechungs Start Datum | MeetingStartDate | Meeting_start_date | Besprechungs Start Datum | Besprechungs Starttermin für Besprechungen. |
| Nachrichten Art | MessageKind | Message_kind | Nachrichten Art | Der Typ der zu suchenden Nachricht.<br />Mögliche Werte: <br />contacts <br />docs <br />email <br />externaldata <br />faxes <br />im <br />journals <br />meetings <br />verläuft (gibt Elemente aus Chats, Besprechungen und anrufen in Microsoft Teams zurück) <br />notes <br />posts <br />rssfeeds <br />tasks <br />voicemail |
| Systemeigene Erweiterung | NativeExtension | Native_extension | Systemeigene Erweiterung | Systemeigene Erweiterung des Elements. |
| Name der systemeigenen Datei | NativeFileName | Native_file_name | Name der systemeigenen Datei | Name des systemeigenen Datei namens des Elements. |
| NativeMD5 |  | Native_MD5 |  | MD5-Hash des Dateidatenstroms. |
| ND/et Sort: Ausschließen von Anlagen | NdEtSortExclAttach | ND_ET_sort_excl_attach | ND/et Sort: Ausschließen von Anlagen | Verkettung von e-Mail-Sätzen und ND-Sätzen zur effizienten Sortierung zur Überprüfungszeit; D wird als Präfix zu ND-Sätzen hinzugefügt, und e wird e-Mail-Sätzen hinzugefügt. |
| ND/et Sort: einschließen von Anlagen | NdEtSortInclAttach | ND_ET_sort_incl_attach | ND/et Sort: einschließen von Anlagen | Verkettung von e-Mail-Sätzen und ND-Sätzen zur effizienten Sortierung zur Überprüfungszeit; D wird als Präfix zu ND-Sätzen hinzugefügt, und e wird e-Mail-Sätzen hinzugefügt. Auf jede e-Mail innerhalb einer e-Mail-Gruppe folgen die entsprechenden Anlagen. |
| Normales Relevanz-Ergebnis bei Ausgabe 1 |  | Normalized_relevance_score_case_issue_1 |  | Normalisierte Relevanz-Bewertung bei Ausgabe 1 von Relevanz. |
| O365-Autoren |  | O365_authors | O365-Autoren | Autor aus SharePoint. |
| O365 erstellt von |  | O365_created_by | O365 erstellt von | Erstellt von aus SharePoint. |
| O365-Erstellungsdatum |  | O365_date_created | O365-Erstellungsdatum | Erstellt am-Datum aus SharePoint. |
| O365-Datum geändert |  | O365_date_modified | O365-Datum geändert | Datum der letzten Änderung aus SharePoint. |
| O365 geändert von |  | O365_modified_by | O365 geändert von | Geändert von von SharePoint. |
| Übergeordnete ID | ParentId | Parent_ID | Übergeordnete ID | ID des übergeordneten Elements des Elements. |
| ParentNode |  | Parent_node |  | Die nächstgelegene vorherige e-Mail-Nachricht im e-Mail-Thread. |
| Übergeordneter Pfad | ParentPath | Parent_path | Übergeordneter Pfad | Zusammengesetzter Pfad des direkten übergeordneten Elements des Elements. |
| Teilnehmer Domänen | ParticipantDomains | Email_participant_domains | Teilnehmer Domänen | Liste aller Domänen von Teilnehmern einer Nachricht. |
| Participants | Participants | Email_participants | Participants | Liste aller Teilnehmer einer Nachricht; Beispiel: Sender, an, CC, BCC. |
| Pivot-ID | Pivot-Nr | Pivot_ID | Pivot-ID | Die ID eines Pivots. |
| Potenziell privilegiert | PotentiallyPrivileged | Potentially_privileged | Potenziell privilegiert | True, wenn das Dokument vom Typ "Anwalts Client-Rechte Erkennung" potenziell privilegiert wird |
| Verarbeitungsstatus | ProcessingStatus | Error_code | Verarbeitungsstatus | Verarbeitungsstatus, nachdem das Element zu einem Überprüfungs Sätze hinzugefügt wurde. |
| Lese Prozent Fall Problem 1 |  | Read_percent_Case_issue_1 |  | Lesen Sie Prozent Fall Problem 1 aus Relevanz. |
| Quantil lesen | ReadPercentile |  | Quantil lesen | Lesen Sie Quantil für das Dokument basierend auf Relevanz. |
| Empfängeranzahl |  | Recipient_count | Empfängeranzahl | Die Anzahl der Empfänger in der Nachricht. |
| Empfängerdomänen | RecipientDomains | Email_recipient_domains | Empfängerdomänen | Liste aller Domänen der Empfänger einer Nachricht. |
| Empfänger | Empfänger | Email_recipients | Empfänger | Liste aller Empfänger einer Nachricht (an, CC, BCC). |
| Relevanz-Ladegruppen Fall Problem 1 |  | Relevance_load_group_case_issue_1 |  | Relevanz-Ladegruppen Fall Problem 1 aus Relevanz. |
| Beschreibung des Problems mit Relevanz-Status (Fall 1) |  | Relevance_status_description_Case_issue_1 |  | Relevanz-Status Beschreibung Fall Problem 1 aus Relevanz. |
| Relevanz-Tag-Fall Problem 1 |  | Relevance_tag_case_issue_1 |  | Relevanz-Tag-Fall Problem 1 aus Relevanz. |
| Relevanz-Kommentar |  | Relevance_comment | Relevanz-Kommentar | Kommentarfeld aus Relevanz. |
| Relevanz-Ergebnis | RelevanceScore |  | Relevanz-Ergebnis | Relevanz-Score eines Dokuments, das auf Relevanz basiert. |
| Relevanz-Tag | RelevanceTag |  | Relevanz-Tag | Relevanz-Score eines Dokuments, das auf Relevanz basiert. |
| Vertreter-ID | Representative-Nr |  | Vertreter-ID | Numerischer Bezeichner der einzelnen Sätze exakter Duplikate. |
| Absender | Absender | Email_sender | Absender | Absenderfeld (von) für Nachrichtentypen.  Das Format **ist \<DisplayName SmtpAddress>**. |
| Absender/Autor | SenderAuthor |  | Absender/Autor | Berechnetes Feld, das aus dem Absender oder dem Autor des Elements besteht. |
| Absenderdomäne | SenderDomain | Email_sender_domain | Absenderdomäne | Domäne des Absenders. |
| Gesendet | Gesendet | Email_date_sent | Gesendet | Gesendet am-Datum der Nachricht. |
| Bestellung festlegen: inklusive zuerst | SetOrderInclusivesFirst | Set_order_inclusives_first | Order festlegen: inklusive zuerst. | Sortierfeld-e-Mail und Anlagen: kontra chronologisch, Dokumente: Pivot zuerst dann nach Ähnlichkeitsergebnis absteigend. |
| SimilarityPercent |  | Similarity_percent |  | Gibt an, wie ähnlich ein Dokument mit dem Drehpunkt des nahe doppelten Satzes ist. |
| Native Dateigröße | Größe | Native_size | Native Dateigröße | Die Anzahl der Bytes des systemeigenen Elements. |
| Betreff | Betreff | Email_subject | Betreff | Betreff der Nachricht. |
| Betreff/Titel | Betreff erstellt |  | Betreff/Titel | Berechnetes Feld, das aus dem Betreff oder Titel des Elements besteht. |
| Gekennzeichnet durch Fall Ausgabe 1 |  | Tagged_by_Case_issue_1 |  | Benutzer, der dieses Dokument für Fall Issue 1 relevant markiert hat. |
| Tags | Tags | Tags | Tags | In einem Überprüfungs Satzes angewendete Tags. |
| Themenliste | Themeslist | Themes_list | Themenliste | Für Analyse berechnete Themenliste. |
| Titel | Titel | Doc_title | Position | Titel aus den Dokumentmetadaten. |
| An | An | Email_to | An | An-Feld für Nachrichtentypen.  Format ist **Display\<Name SmtpAddress>** |
| Eindeutig in e-Mail-Gruppe | UniqueInEmailSet |  | Eindeutig in e-Mail-Gruppe | False, wenn in der e-Mail-Gruppe ein Duplikat der Anlage vorhanden ist. |
| Wurde behoben | WasRemediated | Was_Remediated | Wurde behoben | True, wenn das Element behoben wurde, andernfalls false. |
| Wörter zählen | WordCount | Word_count | Wörter zählen | Die Anzahl der Wörter im Element. |
||||||

  > [!NOTE]
  > Weitere Informationen zu durchsuchbaren Eigenschaften beim Durchsuchen Office 365 Inhaltsspeicher Ortes beim Erfassen von Daten für einen erweiterten eDiscovery-Fall finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).