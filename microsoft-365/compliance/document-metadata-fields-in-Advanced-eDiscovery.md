---
title: Dokumentmetadaten-Felder in Advanced eDiscovery
f1.keywords:
- NOCSH
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
description: In diesem Artikel werden die Metadatenfelder für Dokumente in einem Überprüfungs Satz in einem Fall in Advanced eDiscovery in Microsoft 365 definiert.
ms.openlocfilehash: e419cb14d1b0adbebd6d45aaa5120933b060bdf9
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126952"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Dokumentmetadaten-Felder in Advanced eDiscovery

In der folgenden Tabelle sind die Metadatenfelder für Dokumente in einer Überprüfungsgruppe in einem Fall in Advanced eDiscovery aufgeführt. Die Tabelle enthält die folgenden Informationen:

- **Feldname und** **Anzeige Feldname:** der Name des Metadatenfelds und der Name des Felds, das angezeigt wird, wenn Sie die Datei Metadaten eines ausgewählten Dokuments in einem Überprüfungs Satzes anzeigen. Einige Metadatenfelder werden beim Anzeigen der Datei Metadaten eines Dokuments nicht berücksichtigt. Diese Felder sind mit einem Sternchen (*) markiert.

- **Durchsuchbarer Feldname:** Der Name der Eigenschaft, nach der Sie suchen können, wenn Sie eine [Überprüfungs Sätze-Abfrage](review-set-search.md)durchführen. Eine leere Zelle bedeutet, dass Sie nicht nach dem Feld in einer Abfrage mit Überprüfungs Sätzen suchen können.

- **Name des exportierten Felds:** Der Name des Metadatenfelds, das beim Exportieren von Dokumenten enthalten ist.  Eine leere Zelle bedeutet, dass das Feld nicht in den exportierten Metadaten enthalten ist.

- **Beschreibung:** Eine Beschreibung des Metadatenfelds.

> [!NOTE]
> Das Feld **Schlüsselwörter** in [Review Sets Search](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) verwendet Keyword Query Language (KQL). Die Felder, die in der Spalte **durchsuchbaren Feldnamen** aufgeführt sind, können im Feld **Schlüsselwörter** in einer Überprüfungs Satzes-Suche verwendet werden, um komplexe Abfragen zu bilden, ohne dass Sie den Abfrage-Generator verwenden müssen. Weitere Informationen zu KQL finden Sie unter [Keyword Query Language Syntax Reference](https://go.microsoft.com/fwlink/?LinkId=269603).

|Name des **Felds** und **Anzeige Feldname**|**Durchsuchbarer Feldname**|**Name des exportierten Felds**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Anlageninhalts-ID|AttachmentContentId||Anlageninhalts-ID des Elements.|
|Anlagennamen|AttachmentNames|Attachment_Names|Liste der Namen von Anlagen.|
|Anwalts Kunde-Berechtigungs Bewertung|AttorneyClientPrivilegeScore||Inhalts Ergebnis des Anwalts-Client-Berechtigungsmodells.|
|Ursprung|Ursprung|Doc_authors|Autor aus den Dokumentmetadaten.|
|BCC|Bcc|Email_bcc|BCC-Feld für Nachrichtentypen. Format ist **Display \<SMTPAddress> Name **.|
|CC|Cc|Email_cc|Feld CC für Nachrichtentypen. Format ist **Display \<SMTPAddress> Name **.|
|Konformitäts Bezeichnungen|ComplianceLabels|Compliance_labels|[Aufbewahrungs Bezeichnungen](retention.md) , die auf Inhalte in Office 365 angewendet werden.|
|Zusammengesetzter Pfad|CompoundPath|Compound_path|Mensch lesbarer Pfad, der die Quelle des Elements beschreibt.|
|Inhalts|Inhalt||Extrahierter Text des Elements.|
|Unterhaltungs Text|Unterhaltungs Text||Unterhaltungs Text des Elements.|
|Thema "Unterhaltung"|Thema "Unterhaltung"||Unterhaltungsthema des Elements.|
|Unterhaltungs-ID|ConversationId|Conversation_ID|Unterhaltungs-ID aus der Nachricht.|
|Unterhaltungs Index||Conversation_index|Unterhaltungsindex aus der Nachricht.|
|Unterhaltungs-PDF-Zeit|ConversationPdfTime||Datum, an dem die PDF-Version der Unterhaltung erstellt wurde.|
|Brennen der unter Haltungs-Zeit|ConversationRedactionBurnTime||Datum, an dem die PDF-Version der Unterhaltung für Chat erstellt wurde.|
|Erstelltes Dokumentdatum|CreatedTime|Doc_date_created|Erstellungsdatum aus Dokumentmetadaten.|
|Custodian|Custodian|Custodian|Name der Depotbank, der das Element zugeordnet wurde.|
|Datum|Datum|Datum|Date ist ein berechnetes Feld, das vom Dateityp abhängt.<br /><br />E-Mail: Sendedatum<br />E-Mail-Anlagen: Datum der letzten Änderung des Dokuments, wenn nicht verfügbar, das übergeordnete Datum gesendet<br />Eingebettete Dokumente: Datum der letzten Änderung des Dokuments; Wenn nicht verfügbar, Datum der letzten Änderung des übergeordneten Elements<br />SPO-Dokumente (enthält moderne Anlagen): Datum der letzten Änderung in SharePoint; Wenn nicht verfügbar, Datum der letzten Änderung der Dokumente<br />Nicht Office 365 Dokumente: Datum der letzten Änderung<br />Besprechungen: Startdatum der Besprechung<br />Voicemail: Sendedatum<br />Chat: Datum gesendet|
|Andere Pfade|Dedupedcompoundpath|Deduped_compound_path|Liste der zusammengesetzten Pfade von Dokumenten, bei denen es sich um exakte Duplikate (e-Mail: basierend auf Inhalt, Dokumente: basierend auf Hash) handelt.|
|Andere depotverwalter|DedupedCustodians|Deduped_custodians|Liste der Verwalter von Dokumenten, bei denen es sich um exakte Duplikate handelt (für e-Mails, basierend auf dem Inhalt, für Dokumente, basierend auf Hash).|
|Andere Datei-IDs|DedupedFileIds|Deduped_file_IDs|Liste der Datei-IDs von Dokumenten, bei denen es sich um exakte Duplikate handelt (für e-Mails basierend auf Inhalt; für Dokumente, die auf Hash basieren).|
|Dokument Kommentare|DocComments|Doc_comments|Kommentare aus den Dokumentmetadaten.|
|Dokument Unternehmen||Doc_company|Unternehmen aus den Dokumentmetadaten.|
|DocIndex*|||Der Index in der Familie. **-1** oder **0** bedeutet, dass es sich um den Stamm handelt.|
|Dokument Schlüsselwörter||Doc_keywords|Schlüsselwörter aus den Dokumentmetadaten.|
|Dokument geändert von||Doc_modified_by|Datum der letzten Änderung nach aus Dokumentmetadaten.|
|Dokument Revision||Doc_revision|Revision aus den Dokumentmetadaten.|
|Dokument Betreff||Doc_subject|Betreff aus den Dokumentmetadaten.|
|Dokumentvorlage||Doc_template|Vorlage aus den Dokumentmetadaten.|
|Dominantes Design|DominantTheme|Dominant_theme|Dominantes Design, berechnet für Analyse.|
|Doppelte Teilmenge||Duplicate_subset|Gruppen-ID für exakte Duplikate.|
|E-Mail-Adresse *||Email_action|Werte sind **None**, **Reply**oder **Forward**; basierend auf der Betreffzeile einer Nachricht.|
|E-Mail-Zustellungsbestätigung||Email_delivery_receipt|In Internet Kopfzeilen angegebene e-Mail-Adresse für Übermittlungsbestätigung.|
|Importance|EmailImportance|Email_importance|Wichtigkeit der Nachricht: **0** -niedrig; **1** -normal; **2** -hoch|
|EmailLevel||Email_level|Gibt die Ebene einer Nachricht innerhalb des e-Mail-Threads an, zu dem Sie gehört. Anlagen erben den Wert der übergeordneten Nachricht.|
|E-Mail-Nachrichten-ID||Email_message_ID|Internet Nachrichten-ID aus der Nachricht.|
|EmailReadReceipt*||Email_read_receipt|E-Mail-Adresse, die in Internet Kopfzeilen zur Lesebestätigung angegeben wird.|
|E-Mail-Sicherheit|EmailSecurity|Email_security|Sicherheitseinstellung der Nachricht: **0** -None; **1** – signiert; **2** – verschlüsselt; **3** -verschlüsselt und signiert.|
|E-Mail-Empfindlichkeit|EmailSensitivity|email_sensitivity|Empfindlichkeitseinstellung der Nachricht: **0** -None; **1** persönlich; **2** – privat; **3** -CompanyConfidential.|
|E-Mail-Gruppe|E-Mail-Set|Email_set|Gruppen-ID für alle Nachrichten in derselben e-Mail-Gruppe.|
|EmailThread*||Email_thread|Position der Nachricht innerhalb des e-Mail-Satzes; besteht aus Knoten-IDs vom Stamm bis zur aktuellen Nachricht und werden durch Punkte (.) getrennt.|
|Extrahierter Inhaltstyp||Extracted_content_type|Extrahierter Inhaltstyp in Form von MIME-Typ; Beispiel: **Image/JPEG**|
|ExtractedTextLength*||Extracted_text_length|Anzahl der Zeichen im extrahierten Text.|
|Familien Relevanz-Score-Fall Ausgabe 1 *||Family_relevance_score_case_issue_1|Familien Relevanz-Ergebnis Fall Ausgabe 1 aus Relevanz.|
|FamilyDuplicateSet*||Family_duplicate_set|Numerischer Bezeichner für Familien, die exakte Duplikate von einander (gleicher Inhalt und alle gleichen Anlagen) sind.|
|Familien-ID|FamilyID|Family_ID|Familien-ID-Gruppen alle Elemente zusammen; für e-Mail umfasst dies die Nachricht und alle Anlagen; für Dokumente umfasst dies das Dokument und alle eingebetteten Elemente.|
|Familiengröße||Family_size|Die Anzahl der Dokumente in der Familie.|
|Datei Relevanz-Ergebnis Fall Problem 1 *||File_relevance_score_case_issue_1|Datei Relevanz-Ergebnis Fall Problem 1 aus Relevanz.|
|File-Klasse|Fileclass|File_class|Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: **e-Mail** oder **Anhang**.|
|Datei-ID|FileId|File_ID|In der Anfrage eindeutige Dokument-ID.|
|Erstelltes Dateisystem Datum||File_system_date_created|Erstellungsdatum aus dem Dateisystem (gilt nur für nicht Office 365 Daten).|
|Dateisystem Datum geändert||File_system_date_modified|Änderungsdatum aus dem Dateisystem (gilt nur für nicht Office 365 Daten).|
|Dateityp|FileType||Dateityp des Elements basierend auf der Dateierweiterung.|
|Weist eine Anlage auf|HasAttachment|Email_has_attachment|Gibt an, ob die Nachricht Anlagen enthält.|
|Hat Anwalt|HasAttorney||**True** , wenn mindestens einer der Teilnehmer in der anwaltsliste gefunden wird; Andernfalls ist der Wert **false**.|
|HasText||Has_text|Gibt an, ob das Element über Text verfügt oder nicht. mögliche Werte sind **true** und **false**.|
|Unveränderliche ID||Immutable_ID|Diese ID wird verwendet, um ein Dokument innerhalb eines Überprüfungs Satzes eindeutig zu identifizieren. Dieses Feld kann nicht in einer Überprüfung festgelegten Suche verwendet werden, und die ID kann nicht für den Zugriff auf ein Dokument an seinem systemeigenen Speicherort verwendet werden.|
|Inklusiv-Typ|Inklusivtype|Inclusive_type|Integrativer Typ, berechnet für Analyse: **0** -nicht inklusive; **1** – inklusive; **2** – inklusive minus; **3** -inclusive-Kopie.|
|In Antwort an ID||In_reply_to_ID|In Antwort an ID aus der Nachricht.|
|Ist repräsentativ|Isrepresentative|Is_representative|Ein Dokument in jeder Gruppe exakter Duplikate wird als repräsentativ gekennzeichnet.|
|Elementklasse|ItemClass|Item_class|Von Exchange Server bereitgestellte Item-Klasse; Beispiel: **IPM. Hinweis:**|
|Datum der letzten Änderung|LastModifiedDate|Doc_date_modified|Datum der letzten Änderung aus Dokumentmetadaten.|
|Laden-ID|Lade-Nr|Load_ID|Die ID des Lade Satzes, in dem das Element einem Überprüfungs Satzes hinzugefügt wurde.|
|Speicherort|Speicherort|Speicherort|Zeichenfolge, die den Typ des Speicherorts angibt, aus dem Dokumente stammen.<br /><br />**Importierte Daten** – nicht Office 365 Daten<br />**Teams** – Microsoft Teams<br />**Exchange** -Exchange-Postfächer<br />**SharePoint** -SharePoint-Websites<br />**OneDrive** -OneDrive-Konten|
|Speicherort Name|LocationName|Location_name|Zeichenfolge, die die Quelle des Elements angibt. Für Exchange ist dies die SMTP-Adresse des Postfachs. für SharePoint und OneDrive die URL für die Websitesammlung.|
|Als repräsentativ gekennzeichnet|MarkAsRepresentative||Ein Dokument aus den einzelnen Sätzen exakter Duplikate wird als Repräsentanten markiert.|
|Als Pre-Tagged-Case-Problem 1 * markiert||Marked_as_pre_tagged_Case_issue_1|Als vorab markiertes Fall Problem 1 von Relevanz gekennzeichnet.|
|Markiert als Ausgangsfall Problem 1 *||Marked_as_seed_Case_issue_1|Als Ausgangsfall Problem 1 von Relevanz gekennzeichnet.|
|Enddatum der Besprechung|MeetingEndDate|Meeting_end_date|Termin für Besprechungsende für Besprechungen.|
|Besprechungs Start Datum|MeetingStartDate|Meeting_start_date|Besprechungs Starttermin für Besprechungen.|
|Nachrichten Art|MessageKind|Message_kind|Der Typ der zu suchenden Nachricht. Mögliche Werte: ** <br /> <br /> Kontakte <br /> docs <br /> e-Mail <br /> externaldata <br /> Faxe <br /> Chat <br /> Journals <br /> Meetings <br /> verläuft** (gibt Elemente aus Chats, Besprechungen und Anrufe in Microsoft Teams zurück) ** <br /> Notizen <br /> Beiträge <br /> RSSfeeds <br /> Aufgaben <br /> Voicemail**| 
|Systemeigene Erweiterung|NativeExtension|Native_extension|Systemeigene Erweiterung des Elements.|
|Name der systemeigenen Datei|NativeFileName|Native_file_name|Name des systemeigenen Datei namens des Elements.|
|NativeMD5||Native_MD5|MD5-Hash (128-Bit-Hashwert) des Dateidatenstroms.|
|NativeSHA256||Native_SHA_256|SHA256-Hash (256-Bit-Hashwert) des Dateidatenstroms.|
|ND/et Sort: Ausschließen von Anlagen|NdEtSortExclAttach|ND_ET_sort_excl_attach|Verkettung von e-Mail-Thread (et) und Near-Duplicate (ND) festgelegt. Dieses Feld wird zur effizienten Sortierung zur Überprüfungszeit verwendet. A **D** wird auf ND gesetzt, und **E** wird auf et-Sätzen fixiert.|
|ND/et Sort: einschließen von Anlagen|NdEtSortInclAttach|ND_ET_sort_incl_attach|Verkettung eines e-Mail-Threads (et) und eines near-Duplicate (ND)-Satzes. Dieses Feld wird zur effizienten Sortierung zur Überprüfungszeit verwendet. A **D** wird auf ND gesetzt, und **E** wird auf et-Sätzen fixiert. Auf jedes e-Mail-Element in einem et-Satz folgen die entsprechenden Anlagen.|
|Normales Relevanz-Ergebnis bei Ausgabe 1||Normalized_relevance_score_case_issue_1|Normalisierte Relevanz-Bewertung bei Ausgabe 1 von Relevanz.|
|O365-Autoren||O365_authors|Autor aus SharePoint.|
|O365 erstellt von||O365_created_by|Erstellt von aus SharePoint.|
|O365-Erstellungsdatum||O365_date_created|Erstellt am-Datum aus SharePoint.|
|O365-Datum geändert||O365_date_modified|Datum der letzten Änderung aus SharePoint.|
|O365 geändert von||O365_modified_by|Geändert von von SharePoint.|
|Übergeordnete ID|ParentId|Parent_ID|ID des übergeordneten Elements des Elements.|
|ParentNode||Parent_node|Die nächstgelegene vorherige e-Mail-Nachricht im e-Mail-Thread.|
|Übergeordneter Pfad|ParentPath|Parent_path|Zusammengesetzter Pfad des direkten übergeordneten Elements des Elements.|
|Teilnehmer Domänen|ParticipantDomains|Email_participant_domains|Liste aller Domänen von Teilnehmern einer Nachricht.|
|Participants|Participants|Email_participants|Liste aller Teilnehmer einer Nachricht; Beispiel: Sender, an, CC, BCC.|
|Pivot-ID|Pivot-Nr|Pivot_ID|Die ID eines Pivots.|
|Potenziell privilegiert|PotentiallyPrivileged|Potentially_privileged|True, wenn das Dokument vom Typ "Anwalts Client-Rechte Erkennung" potenziell privilegiert wird|
|Verarbeitungsstatus|ProcessingStatus|Error_code|Verarbeitungsstatus, nachdem das Element zu einem Überprüfungs Sätze hinzugefügt wurde.|
|Lese Prozent Fall Problem 1||Read_percent_Case_issue_1|Lesen Sie Prozent Fall Problem 1 aus Relevanz.|
|Quantil lesen|ReadPercentile||Lesen Sie Quantil für das Dokument basierend auf Relevanz.|
|Empfängeranzahl||Recipient_count|Die Anzahl der Empfänger in der Nachricht.|
|Empfängerdomänen|RecipientDomains|Email_recipient_domains|Liste aller Domänen der Empfänger einer Nachricht.|
|Empfänger|Empfänger|Email_recipients|Liste aller Empfänger einer Nachricht (an, CC, BCC).|
|Relevanz-Ladegruppen Fall Problem 1||Relevance_load_group_case_issue_1|Relevanz-Ladegruppen Fall Problem 1 aus Relevanz.|
|Beschreibung des Problems mit Relevanz-Status (Fall 1)||Relevance_status_description_Case_issue_1|Relevanz-Status Beschreibung Fall Problem 1 aus Relevanz.|
|Relevanz-Tag-Fall Problem 1||Relevance_tag_case_issue_1|Relevanz-Tag-Fall Problem 1 aus Relevanz.|
|Relevanz-Kommentar||Relevance_comment|Kommentarfeld aus Relevanz.|
|Relevanz-Ergebnis|RelevanceScore||Relevanz-Score eines Dokuments, das auf Relevanz basiert.|
|Relevanz-Tag|RelevanceTag||Relevanz-Score eines Dokuments, das auf Relevanz basiert.|
|Vertreter-ID|Representative-Nr||Numerischer Bezeichner der einzelnen Sätze exakter Duplikate.|
|Absender|Absender|Email_sender|Absenderfeld (von) für Nachrichtentypen. Format ist **Display \<SmtpAddress> Name **.|
|Absender/Autor|SenderAuthor||Berechnetes Feld, das aus dem Absender oder dem Autor des Elements besteht.|
|Absenderdomäne|SenderDomain|Email_sender_domain|Domäne des Absenders.|
|Gesendet|Gesendet|Email_date_sent|Gesendet am-Datum der Nachricht.|
|Bestellung festlegen: inklusive zuerst|SetOrderInclusivesFirst|Set_order_inclusives_first|Sortierfeld-e-Mail und Anlagen: kontra chronologisch; Documents: Pivot zuerst dann nach absteigender Ähnlichkeits Bewertung.|
|SimilarityPercent||Similarity_percent|Gibt an, wie ähnlich ein Dokument mit dem Drehpunkt des nahe doppelten Satzes ist.|
|Native Dateigröße|Größe|Native_size|Die Anzahl der Bytes des systemeigenen Elements.|
|Betreff|Betreff|Email_subject|Betreff der Nachricht.|
|Betreff/Titel|Betreff erstellt||Berechnetes Feld, das aus dem Betreff oder Titel des Elements besteht.|
|Gekennzeichnet durch Fall Ausgabe 1||Tagged_by_Case_issue_1|Benutzer, der dieses Dokument für Fall Issue 1 relevant markiert hat.|
|Tags|Tags|Tags|In einem Überprüfungs Satzes angewendete Tags.|
|Themenliste|Themeslist|Themes_list|Für Analyse berechnete Themenliste.|
|Titel|Titel|Doc_title|Titel aus den Dokumentmetadaten.|
|An|An|Email_to|An-Feld für Nachrichtentypen. Format ist **Display \<SmtpAddress> Name**|
|Eindeutig in e-Mail-Gruppe|UniqueInEmailSet||**False** , wenn in der e-Mail-Gruppe ein Duplikat der Anlage vorhanden ist.|
|Wurde behoben|WasRemediated|Was_Remediated|**True** , wenn das Element behoben wurde, andernfalls **false**.|
|Wörter zählen|WordCount|Word_count|Die Anzahl der Wörter im Element.|
|||||

> [!NOTE]
> Weitere Informationen zu durchsuchbaren Eigenschaften beim Durchsuchen Office 365 Inhaltsspeicher Ortes beim Erfassen von Daten für einen erweiterten eDiscovery-Fall finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
