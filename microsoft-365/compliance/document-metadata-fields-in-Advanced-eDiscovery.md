---
title: Dokument-Metadatenfelder in Advanced eDiscovery
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
description: In diesem Artikel werden die Metadatenfelder für Dokumente in einem Prüfdateisatz in einem Fall in Advanced eDiscovery in Microsoft 365 definiert.
ms.openlocfilehash: 42f349bf01d5a777535dd04096b860a0165f1edf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769569"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Dokument-Metadatenfelder in Advanced eDiscovery

In der folgenden Tabelle sind die Metadatenfelder für Dokumente in einem Prüfdateisatz in einem Fall in Advanced eDiscovery aufgeführt. Die Tabelle enthält die folgenden Informationen:

- **Feldname** und **Anzeigefeldname:** Der Name des Metadatenfelds und der Name des Felds, das beim Anzeigen der Dateimetadaten eines ausgewählten Dokuments in einem Prüfdateisatz angezeigt wird. Einige Metadatenfelder sind beim Anzeigen der Dateimetadaten eines Dokuments nicht enthalten. Diese Felder werden mit einem Sternchen (*) hervorgehoben.

- **Durchsuchbarer Feldname:** Der Name der Eigenschaft, nach der Sie suchen können, wenn Sie eine [Prüfdateisatzabfrage](review-set-search.md)ausführen. Eine leere Zelle bedeutet, dass Sie in einer Prüfdateisatzabfrage nicht nach dem Feld suchen können.

- **Exportierter Feldname:** Der Name des Metadatenfelds, das beim Exportieren von Dokumenten enthalten ist.  Eine leere Zelle bedeutet, dass das Feld nicht in den exportierten Metadaten enthalten ist.

- **Beschreibung:** Eine Beschreibung des Metadatenfelds.

> [!NOTE]
> Das **Feld "Schlüsselwörter"** in der [Prüfdateisatzsuche](./review-set-search.md) verwendet Keyword Query Language (KQL). Die in der Spalte mit dem Namen des **durchsuchbaren Felds** aufgeführten Felder können im Feld **"Schlüsselwörter"** in einer Prüfdateisatzsuche verwendet werden, um komplexe Abfragen zu bilden, ohne dass Sie den Abfrage-Generator verwenden müssen. Weitere Informationen zu KQL finden Sie unter Syntaxreferenz für [keyword Query Language.](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

|**Feldname** und **Anzeigefeldname**|**Durchsuchbarer Feldname**|**Exportierter Feldname**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Anlageninhalts-ID|AttachmentContentId||Anlageninhalts-ID des Elements.|
|Bewertung der Anwaltsgeheimnisse|AttorneyClientPrivilegeScore||Bewertung der Inhalte des Anwaltsgeheimnissemodells.|
|Ursprung|Ursprung|Doc_authors|Autor aus den Dokumentmetadaten.|
|BCC|Bcc|Email_bcc|Bcc-Feld für Nachrichtentypen. Format ist **DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Cc-Feld für Nachrichtentypen. Format ist **DisplayName \<SMTPAddress>**.|
|Compliancebezeichnungen|ComplianceLabels|Compliance_labels|[Aufbewahrungsbezeichnungen,](retention.md) die auf Inhalte in Office 365 angewendet werden.|
|Zusammengesetzter Pfad|CompoundPath|Compound_path|Lesbarer Pfad, der die Quelle des Elements beschreibt.|
|Inhalt*|Inhalt||Extrahierter Text des Elements.|
|Unterhaltungstext|Unterhaltungstext||Unterhaltungstext des Elements.|
|Unterhaltungsthema|Unterhaltungsthema||Unterhaltungsthema des Elements.|
|Unterhaltungs-ID|ConversationId|Conversation_ID|Unterhaltungs-ID aus der Nachricht.|
|Unterhaltungsindex||Conversation_index|Unterhaltungsindex aus der Nachricht.|
|Pdf-Zeit der Unterhaltung|ConversationPdfTime||Datum, an dem die PDF-Version der Unterhaltung erstellt wurde.|
|Redaction-Burn-Zeit für Unterhaltungen|ConversationRedactionActionTime||Datum, an dem die PDF-Version der Unterhaltung für Chat erstellt wurde.|
|||Converted_file_path|Der Pfad der konvertierten Exportdatei. Nur für die interne Verwendung von Microsoft.|
|Erstellungsdatum des Dokuments|CreatedTime|Doc_date_created|Erstellungsdatum aus Dokumentmetadaten.|
|Verwahrer|Verwahrer|Verwahrer|Der Name des Verwalters, dem das Element zugeordnet war.|
|Datum|Datum|Datum|Datum ist ein berechnetes Feld, das vom Dateityp abhängt.<br /><br />E-Mail: Sendedatum<br />E-Mail-Anlagen: Datum der letzten Änderung des Dokuments; falls nicht verfügbar, das Sendedatum des übergeordneten Elements<br />Eingebettete Dokumente: Datum der letzten Änderung des Dokuments; wenn nicht verfügbar, das Datum der letzten Änderung des übergeordneten Elements<br />SPO-Dokumente (einschließlich moderner Anlagen): SharePoint Datum der letzten Änderung; falls nicht verfügbar, das Datum der letzten Änderung der Dokumente<br />Dokumente ohne Office 365: Datum der letzten Änderung<br />Besprechungen: Besprechungsanfangsdatum<br />VoiceMail: Sendedatum<br />Chat: Sendedatum|
|Andere Pfade|Dedupedcompoundpath|Deduped_compound_path|Liste der zusammengesetzten Pfade von Dokumenten, die genaue Duplikate sind (E-Mail: basierend auf Inhalten, Dokumente: basierend auf Hash).|
|Andere Verwahrer|DedupedCustodians|Deduped_custodians|Liste der Verwahrer von Dokumenten, die genaue Duplikate sind (für E-Mails, basierend auf Inhalten; für Dokumente, basierend auf Hash).|
|Andere Datei-IDs|DedupedFileIds|Deduped_file_IDs|Liste der Datei-IDs von Dokumenten, die genaue Duplikate sind (für E-Mails, basierend auf Inhalten; für Dokumente, basierend auf Hash).|
|Dokumentkommentare|DocComments|Doc_comments|Kommentare aus den Dokumentmetadaten.|
|Dokumentunternehmen||Doc_company|Unternehmen aus den Dokumentmetadaten.|
|DocIndex*|||Der Index in der Familie. **-1** oder **0** bedeutet, dass es sich um den Stamm handelt.|
|Dokumentschlüsselwörter||Doc_keywords|Schlüsselwörter aus den Dokumentmetadaten.|
|Dokument geändert von||Doc_modified_by|Datum der letzten Änderung anhand von Dokumentmetadaten.|
|Dokumentrevision|Doc_Version|Doc_Version|Revision aus den Dokumentmetadaten.|
|Dokumentbeantrager||Doc_subject|Betreff aus den Dokumentmetadaten.|
|Dokumentvorlage||Doc_template|Vorlage aus den Dokumentmetadaten.|
|DocLastSavedBy||Doc_last_saved_by|Der Name des Benutzers, der das Dokument zuletzt gespeichert hat.|
|Dominantes Design|DominantTheme|Dominant_theme|Dominantes Design, wie es für Analysen berechnet wird.|
|Doppelte Teilmenge||Duplicate_subset|Gruppen-ID für exakte Duplikate.|
|EmailAction*||Email_action|Werte sind **None**, **Reply** oder **Forward**; basierend auf der Betreffzeile einer Nachricht.|
|E-Mail-Zustellungsbestätigung angefordert||Email_delivery_receipt|E-Mail-Adresse, die in Internetkopfzeilen für den Übermittlungsbeleg angegeben wird.|
|Importance|EmailImportance|Email_importance|Wichtigkeit der Nachricht: **0** - Niedrig; **1** - Normal; **2** – Hoch|
|Ignorierte Verarbeitungsfehler|ErrorIgnored|Error_Ignored|Fehler wurde ignoriert und nicht behoben.|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|Der vollständige Satz von E-Mail-Kopfzeilen aus der E-Mail-Nachricht|
|EmailLevel*||Email_level|Gibt die Ebene einer Nachricht innerhalb des E-Mail-Threads an, zu dem sie gehört. Anlagen erben den Wert der übergeordneten Nachricht.|
|E-Mail-Nachrichten-ID||Email_message_ID|Internetnachrichten-ID aus der Nachricht.|
|EmailReadReceiptRequested||Email_read_receipt|E-Mail-Adresse, die in Internetkopfzeilen für Lesebestätigung angegeben wird.|
|E-Mail-Sicherheit|EmailSecurity|Email_security|Sicherheitseinstellung der Nachricht: **0** - Keine; **1** – Signiert; **2** – Verschlüsselt; **3** – Verschlüsselt und signiert.|
|E-Mail-Vertraulichkeit|EmailSensitivity|email_sensitivity|Vertraulichkeitseinstellung der Nachricht: **0** - Keine; **1** Persönlich; **2** – Privat; **3** – CompanyConfidential.|
|E-Mail-Satz|EmailSet|Email_set|Gruppen-ID für alle Nachrichten in demselben E-Mail-Satz.|
|EmailThread*||Email_thread|Position der Nachricht innerhalb des E-Mail-Satzes; besteht aus Knoten-IDs vom Stamm bis zur aktuellen Nachricht und werden durch Punkte (.) getrennt.|
|||Export_native_path|Der Pfad der exportierten Datei.|
|Extrahierter Inhaltstyp||Native_type|Extrahierter Inhaltstyp in Form eines Mime-Typs; z. B. **Bild/JPEG**|
|||Extracted_text_path|Der Pfad zur extrahierten Textdatei im Export.|
|ExtractedTextLength*||Extracted_text_length|Anzahl der Zeichen im extrahierten Text.|
|FamilyDuplicateSet*||Family_duplicate_set|Numerischer Bezeichner für Familien, bei denen es sich um genaue Duplikate voneinander handelt (gleicher Inhalt und alle gleichen Anlagen).|
|Familien-ID|FamilyId|Family_ID|Gruppiert alle Elemente für E-Mails. Dazu gehören die Nachricht und alle Anlagen und extrahierten Elemente.|
|Familiengröße||Family_size|Anzahl der Dokumente in der Familie.|
|Dateiklasse|FileClass|File_class|Für Inhalte aus SharePoint und OneDrive: **Dokument**; für Inhalte aus Exchange: **E-Mail** oder **Anlage**.|
|Datei-ID|FileId|File_id|Dokumentbezeichner innerhalb des Falls eindeutig.|
|Erstellungsdatum des Dateisystems||File_system_date_created|Erstellungsdatum aus dem Dateisystem (gilt nur für Nicht-Office 365-Daten).|
|Änderungsdatum des Dateisystems||File_system_date_modified|Änderungsdatum aus dem Dateisystem (gilt nur für Nicht-Office 365-Daten).|
|Dateityp|FileType||Dateityp des Elements basierend auf der Dateierweiterung.|
|Gruppen-ID|Gruppen-ID|Group_ID|Gruppiert alle Elemente für E-Mails und Dokumente. Für E-Mails umfasst dies die Nachricht und alle Anlagen und extrahierten Elemente. Bei Dokumenten umfasst dies das Dokument und alle eingebetteten Elemente.|
|Hat Anlage|HasAttachment|Email_has_attachment|Gibt an, ob die Nachricht Anlagen enthält.|
|Hat Anwalt|HasAttorwel||**"True",** wenn mindestens einer der Teilnehmer in der Anwaltsliste gefunden wird; andernfalls ist der Wert **False**.|
|HasText*||Has_text|Gibt an, ob das Element Text enthält. Mögliche Werte sind **True** und **False.**|
|Unveränderliche ID||Immutable_ID|Diese ID wird verwendet, um ein Dokument innerhalb eines Prüfdateisatzes eindeutig zu identifizieren. Dieses Feld kann nicht in einer Überprüfungssatzsuche verwendet werden, und die ID kann nicht für den Zugriff auf ein Dokument an seinem systemeigenen Speicherort verwendet werden.|
|Inklusiver Typ|InclusiveType|Inclusive_type|Inklusiver Typ, der für Analysen berechnet wird: **0** – nicht inklusiv; **1** – einschließlich; **2** – inklusive Minus; **3** – inklusive Kopie.|
|In Reply To Id||In_reply_to_ID|Als Antwort auf "ID" aus der Nachricht.|
|InputFileExtension||Original_file_extension|Die ursprüngliche Dateierweiterung der Datei.|
|InputFileID||Input_file_ID|Die Datei-ID des Elements der obersten Ebene im Prüfdateisatz. Bei einer Anlage ist diese ID die ID des übergeordneten Elements. Dies kann zum Gruppieren von Familien verwendet werden.|
|Ist moderne Anlage| IsModernAttachment|  |Diese Datei ist eine moderne Anlage oder verknüpfte Datei.|
|Stammt aus der Dokumentversion | IsFromDocumentVersion |  |Das aktuelle Dokument stammt aus einer anderen Version eines anderen Dokuments.|
|Ist E-Mail-Anlage? | IsEmailAttachment|  |Dieses Element stammt aus einer E-Mail-Anlage, die als angefügtes Element an die Nachricht angezeigt wird.|
|Ist Inlineanlage| IsInlineAttachment|  |Diese wurde inline angefügt und wird im Nachrichtentext angezeigt.|
|Ist repräsentativ|IsRepresentative|Is_representative|Ein Dokument in jeder Gruppe exakter Duplikate wird als repräsentativ markiert.|
|Elementklasse|ItemClass|Item_class|Vom Exchange-Server bereitgestellte Elementklasse; z. **B. IPM. Hinweis**|
|Datum der letzten Änderung|LastModifiedDate|Doc_date_modified|Datum der letzten Änderung aus Dokumentmetadaten.|
|Lade-ID|LoadId|Load_ID|Die ID des Ladesatzes, in dem das Element einem Prüfdateisatz hinzugefügt wurde.|
|Ort|Ort|Ort|Zeichenfolge, die den Typ des Speicherorts angibt, von dem Dokumente stammen.<br /><br />**Importierte Daten** – Nicht Office 365 Daten<br />**Teams** – Microsoft Teams<br />**Exchange** – Exchange Postfächer<br />**SharePoint** – SharePoint Websites<br />**OneDrive** – OneDrive Konten|
|Standortname|LocationName|Location_name|Zeichenfolge, die die Quelle des Elements identifiziert. Bei Exchange ist dies die SMTP-Adresse des Postfachs. für SharePoint und OneDrive die URL für die Websitesammlung.|
|||Marked_as_pivot|Diese Datei ist das Pivot in einem nahezu doppelten Satz.|
|Als repräsentativ markiert|MarkAsRepresentative||Ein Dokument aus jeder Gruppe exakter Duplikate wird als Vertreter gekennzeichnet.|
|Enddatum der Besprechung|MeetingEndDate|Meeting_end_date|Enddatum der Besprechung für Besprechungen.|
|Besprechungsanfangsdatum|MeetingStartDate|Meeting_start_date|Besprechungsanfangsdatum für Besprechungen.|
|Nachrichtenart|MessageKind|Message_kind|Der Typ der Nachricht, nach der gesucht werden soll. Mögliche Werte: **<br /> <br /> Kontakte <br /> dokumente <br /> E-Mail <br /> externaldata <br /> Faxe im Meetings <br /> <br /> <br /> <br /> Microsoftteams** (gibt Elemente aus Chats, Besprechungen und Anrufe in Microsoft Teams) **<br /> Notizen beiträge <br /> <br /> rssfeeds <br /> Aufgaben <br /> Voicemail**| 
|Moderne übergeordnete Anlagen-ID||ModernAttachment_ParentId|Die unveränderliche ID des übergeordneten Elements des Dokuments.|
|Native Erweiterung|NativeExtension|Native_extension|Systemeigene Erweiterung des Elements.|
|Nativer Dateiname|NativeFileName|Native_file_name|Systemeigener Dateiname des Elements.|
|NativeMD5||Native_MD5|MD5-Hash (128-Bit-Hashwert) des Dateidatenstroms.|
|NativeSHA256||Native_SHA_256|SHA256-Hash (256-Bit-Hashwert) des Dateidatenstroms.|
|ND/ET-Sortierung: Ausschließen von Anlagen|NdEtSortExclAttach|ND_ET_sort_excl_attach|Verkettung des E-Mail-Thread -Satzes (ET) und des ND-Satzes (Near-duplicate). Dieses Feld wird zur effizienten Sortierung zur Überprüfungszeit verwendet. A **D** is prefixed to ND sets and an **E** is prefixed to ET sets.|
|ND/ET-Sortierung: Einschließen von Anlagen|NdEtSortInclAttach|ND_ET_sort_incl_attach|Verkettung eines E-Mail-Thread -Satzes (ET) und eines ND-Satzes (Near-Duplicate). Dieses Feld wird zur effizienten Sortierung zur Überprüfungszeit verwendet. A **D** is prefixed to ND sets and an **E** is prefixed to ET sets. Auf jedes E-Mail-Element in einem ET-Satz folgen die entsprechenden Anlagen.|
|Near Duplicate Set||ND_set|Elemente, die dem Pivotdokument ähneln, verwenden dieselbe ND_set.|
|O365-Autoren||O365_authors|Autor aus SharePoint.|
|O365 erstellt von||O365_created_by|Erstellt von SharePoint.|
|O365-Erstellungsdatum||O365_date_created|Erstellungsdatum aus SharePoint.|
|O365-Änderungsdatum||O365_date_modified|Datum der letzten Änderung ab SharePoint.|
|O365 geändert von||O365_modified_by|Geändert von SharePoint.|
|Übergeordnete ID|ParentId|Parent_ID|ID des übergeordneten Elements.|
|ParentNode||Parent_node|Die nächste vorherige E-Mail-Nachricht im E-Mail-Thread.|
|Teilnehmerdomänen|ParticipantDomains|Email_participant_domains|Liste aller Domänen der Teilnehmer einer Nachricht.|
|Teilnehmer|Teilnehmer|Email_participants|Liste aller Teilnehmer einer Nachricht; z. B. Sender, To, Cc, Bcc.|
|Pivot-ID|PivotId|Pivot_ID|Die ID eines Pivots.|
|Potenziell privilegierte|Potenziell privilegierte|Potentially_privileged|"True", wenn das Erkennungsmodell von Anwaltsgeheimnissen das Dokument als potenziell privilegiert betrachtet|
|Verarbeitungsstatus|ProcessingStatus|Error_code|Verarbeitungsstatus nach dem Hinzufügen des Elements zu einem Prüfdateisatz.|
|Perzentil lesen|ReadPercentile||Perzentil für das Dokument basierend auf Relevanz lesen.|
|Auszahlung|Auszahlung|Email_date_received|Datum und Uhrzeit des Empfangs der E-Mail in UTC.|
|Empfängeranzahl||Recipient_count|Die Anzahl der Empfänger in der Nachricht.|
|Empfängerdomänen|RecipientDomains|Email_recipient_domains|Liste aller Domänen von Empfängern einer Nachricht.|
|Empfänger|Empfänger|Email_recipients|Liste aller Empfänger einer Nachricht (An, Cc, Bcc).|
|||Redacted_file_path|Der Pfad der bearbeiteten Ersetzungsdatei im Export.|
|||Redacted_text_path|Der Pfad des geänderten Textdateiersetzungstyps beim Export. Nur für die interne Verwendung von Microsoft.|
|Relevanztag Fall 1||Relevance_tag_case_issue_1|Relevanztag Fall 1 von Relevanz.|
|Relevanzbewertung|RelevanceScore||Relevanzbewertung eines Dokuments basierend auf Relevanz.|
|Relevanztag|RelevanceTag||Relevanzbewertung eines Dokuments basierend auf Relevanz.|
|Repräsentative ID|RepresentativeId||Numerischer Bezeichner jedes Satzes exakter Duplikate.|
|||Row_number|Die Zeilennummer des Elements in der Ladedatei.|
|Absender|Absender|Email_sender|Absenderfeld (Von) für Nachrichtentypen. Format ist **DisplayName \<SmtpAddress>**.|
|Absender/Autor|SenderAuthor||Berechnetes Feld, das aus dem Absender oder Autor des Elements besteht.|
|Absenderdomäne|SenderDomain|Email_sender_domain|Domäne des Absenders.|
|Gesendet|Gesendet|Email_date_sent|Sendedatum der Nachricht.|
|Set Order: Inclusive First|SetOrderInclusivesFirst|Set_order_inclusives_first|Sortierfeld – E-Mail und Anlagen: chronologischer Wert; documents: Pivot first then by descending similarity score.|
|Festlegen der ID||Set_ID|Dokumente mit ähnlichem Inhalt (ND_set) oder E-Mails innerhalb desselben E-Mail-Threads (Email_set) teilen sich dieselbe Set_ID.|
|SimilarityPercent||Similarity_percent|Gibt an, wie ähnlich ein Dokument dem Pivot des nahezu doppelten Satzes ist.|
|Systemeigene Dateigröße|Size|Native_size|Anzahl der Bytes des systemeigenen Elements.|
|Betreff|Betreff|Email_subject|Betreff der Nachricht.|
|Betreff/Titel|SubjectTitle||Berechnetes Feld, das aus dem Betreff oder Titel des Elements besteht.|
|Tags|Tags|Tags|Tags, die in einem Prüfdateisatz angewendet werden.|
|Designliste|ThemesList|Themes_list|Designliste wie für Analysen berechnet.|
|Titel|Titel|Doc_title|Titel aus den Dokumentmetadaten.|
|An|An|Email_to|Zum Feld für Nachrichtentypen. Format ist **DisplayName \<SmtpAddress>**|
|Eindeutig im E-Mail-Satz|UniqueInEmailSet|| False , wenn ein Duplikat der Anlage in ihrem E-Mail-Satz vorhanden ist.|
|Versionsgruppen-ID||Version_Group_Id|Gruppiert die verschiedenen Versionen desselben Dokuments.|
|Wurde behoben|WasRemediated|Was_Remediated|**True,** Wenn das Element behoben wurde, andernfalls **False**.|
|Wörter zählen|Wordcount|Word_count|Anzahl der Wörter im Element.|
|||||

> [!NOTE]
> Weitere Informationen zu durchsuchbaren Eigenschaften beim Durchsuchen Office 365 Inhaltsspeicherorten, wenn Sie Daten für einen Advanced eDiscovery Fall sammeln, finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche.](keyword-queries-and-search-conditions.md)
