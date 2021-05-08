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
description: In diesem Artikel werden die Metadatenfelder für Dokumente in einem Überprüfungssatz in einem Fall in Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 77df40f4922718a7ed30431b0c1bd91f5c075425
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244600"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Dokument-Metadatenfelder in Advanced eDiscovery

In der folgenden Tabelle sind die Metadatenfelder für Dokumente in einem Überprüfungssatz in einem Fall in Advanced eDiscovery. Die Tabelle enthält die folgenden Informationen:

- **Feldname** und **Anzeigefeldname:** Der Name des Metadatenfelds und der Name des Felds, das angezeigt wird, wenn die Dateimetadaten eines ausgewählten Dokuments in einem Überprüfungssatz angezeigt werden. Einige Metadatenfelder sind beim Anzeigen der Dateimetadaten eines Dokuments nicht enthalten. Diese Felder werden mit einem Sternchen (*) hervorgehoben.

- **Durchsuchbarer Feldname:** Der Name der Eigenschaft, nach der Sie beim Ausführen einer Überprüfungssatzabfrage [suchen können.](review-set-search.md) Eine leere Zelle bedeutet, dass Sie in einer Überprüfungssatzabfrage nicht nach dem Feld suchen können.

- **Exportierter Feldname:** Der Name des Metadatenfelds, das beim Exportieren von Dokumenten enthalten war.  Eine leere Zelle bedeutet, dass das Feld nicht in den exportierten Metadaten enthalten ist.

- **Beschreibung:** Eine Beschreibung des Metadatenfelds.

> [!NOTE]
> Das **Feld Schlüsselwörter** in der [Überprüfungssatzsuche verwendet](./review-set-search.md) Keyword Query Language (KQL). Die in der  Spalte Name des Durchsuchbaren Felds aufgeführten Felder können im Feld Schlüsselwörter in einer Überprüfungssatzsuche verwendet werden, um komplexe Abfragen zu bilden, ohne dass Sie den Abfrage-Generator verwenden müssen.  Weitere Informationen zu KQL finden Sie unter [Keyword Query Language syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

|**Feldname** und **Anzeigefeldname**|**Durchsuchbarer Feldname**|**Exportierter Feldname**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Anlageninhalts-ID|AttachmentContentId||Anlageninhalts-ID des Elements.|
|Bewertung von Anwalts-Clientrechten|AttorneyClientPrivilegeScore||Bewertung der Inhalte des Anwalts-Client-Berechtigungsmodells.|
|Ursprung|Ursprung|Doc_authors|Autor aus den Dokumentmetadaten.|
|BCC|Bcc|Email_bcc|Bcc-Feld für Nachrichtentypen. Format ist **DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Cc-Feld für Nachrichtentypen. Format ist **DisplayName \<SMTPAddress>**.|
|Konformitätsbezeichnungen|ComplianceLabels|Compliance_labels|[Aufbewahrungsbezeichnungen,](retention.md) die auf Inhalte in einem Office 365.|
|Zusammengesetzter Pfad|CompoundPath|Compound_path|Vom Menschen lesbarer Pfad, der die Quelle des Elements beschreibt.|
|Inhalt*|Inhalt||Extrahierter Text des Elements.|
|Unterhaltungstext|Unterhaltungstext||Unterhaltungstext des Elements.|
|Unterhaltungsthema|Unterhaltungsthema||Unterhaltungsthema des Elements.|
|Unterhaltungs-ID|ConversationId|Email_conversation_ID|Unterhaltungs-ID aus der Nachricht.|
|Unterhaltungsindex||Conversation_index|Unterhaltungsindex aus der Nachricht.|
|Unterhaltungs-PDF-Zeit|ConversationPdfTime||Datum, an dem die PDF-Version der Unterhaltung erstellt wurde.|
|Unterhaltung Redaction Burn Time|ConversationRedactionBurnTime||Datum, an dem die PDF-Version der Unterhaltung für Chat erstellt wurde.|
|||Converted_file_path|Der Pfad der konvertierten Exportdatei. Nur für interne Verwendung durch Microsoft.|
|Dokumentdatum erstellt|CreatedTime|Doc_date_created|Erstellen sie Datum aus Dokumentmetadaten.|
|Verwahrer|Verwahrer|Verwahrer|Name des Verwahrers, dem das Element zugeordnet war.|
|Datum|Datum|Datum|Date ist ein berechnetes Feld, das vom Dateityp abhängt.<br /><br />E-Mail: Gesendetes Datum<br />E-Mail-Anlagen: Datum der letzten Änderung des Dokuments;wenn nicht verfügbar, das Gesendete Datum des übergeordneten Elements<br />Eingebettete Dokumente: Datum der letzten Änderung des Dokuments; Falls nicht verfügbar, wird das datum der letzten Änderung des übergeordneten Elements<br />SPO-Dokumente (einschließlich moderner Anlagen): SharePoint Datum der letzten Änderung; Falls nicht verfügbar, wird das Datum der letzten Änderung der Dokumente<br />Nicht-Office 365: Datum der letzten Änderung<br />Besprechungen: Anfangsdatum der Besprechung<br />VoiceMail: Gesendetes Datum<br />IM: Gesendetes Datum|
|Andere Pfade|Dedupedcompoundpath|Deduped_compound_path|Liste der zusammengesetzten Pfade von Dokumenten, die genaue Duplikate sind (E-Mail: basierend auf Inhalt, Dokumente: basierend auf Hash).|
|Andere Verwahrer|DedupedCustodians|Deduped_custodians|Liste der Verwahrer von Dokumenten, die genaue Duplikate sind (für E-Mails, basierend auf Inhalten, für Dokumente, basierend auf Hash).|
|Andere Datei-IDs|DedupedFileIds|Deduped_file_IDs|Liste der Datei-IDs von Dokumenten, die genaue Duplikate sind (für E-Mails, basierend auf Inhalten, für Dokumente, basierend auf Hash).|
|Dokumentkommentare|DocComments|Doc_comments|Kommentare aus den Dokumentmetadaten.|
|Dokumentunternehmen||Doc_company|Unternehmen aus den Dokumentmetadaten.|
|DocIndex*|||Der Index in der Familie. **-1** oder **0** bedeutet, dass es sich um den Stamm handelt.|
|Dokumentschlüsselwörter||Doc_keywords|Schlüsselwörter aus den Dokumentmetadaten.|
|Dokument, das von geändert wurde||Doc_modified_by|Datum der letzten Änderung aus Dokumentmetadaten.|
|Dokumentrevision|Doc_Version|Doc_Version|Überarbeitung aus den Dokumentmetadaten.|
|Dokumentsubjekt||Doc_subject|Betreff aus den Dokumentmetadaten.|
|Dokumentvorlage||Doc_template|Vorlage aus den Dokumentmetadaten.|
|DocLastSavedBy||Doc_last_saved_by|Der Name des Benutzers, der das Dokument zuletzt gespeichert hat.|
|Dominantes Design|DominantTheme|Dominant_theme|Dominantes Design, wie für analysen berechnet.|
|Doppelte Teilmenge||Duplicate_subset|Gruppen-ID für exakte Duplikate.|
|EmailAction*||Email_action|Die Werte sind **None**, **Reply** oder **Forward**; basierend auf der Betreffzeile einer Nachricht.|
|Angeforderter E-Mail-Zustellungsbeleg||Email_delivery_receipt_requested|E-Mail-Adresse, die in Internetheadern für den Zustellungsbeleg bereitgestellt wird.|
|Importance|EmailImportance|Email_importance|Wichtigkeit der Nachricht: **0** – Niedrig; **1** – Normal; **2** – Hoch|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|Der vollständige Satz von E-Mail-Headern aus der E-Mail-Nachricht|
|EmailLevel*||Email_level|Gibt die Ebene einer Nachricht innerhalb des E-Mail-Threads an, zu dem sie gehört. Anlagen erben den Wert der übergeordneten Nachricht.|
|E-Mail-Nachrichten-ID||Email_message_ID|Internetnachrichten-ID aus der Nachricht.|
|EmailReadReceiptRequested||Email_read_receipt_requested|E-Mail-Adresse, die in Internetheadern für lesebestätigung bereitgestellt wird.|
|E-Mail-Sicherheit|EmailSecurity|Email_security|Sicherheitseinstellung der Nachricht: **0** – Keine; **1** – Signiert; **2** – Verschlüsselt; **3** – Verschlüsselt und signiert.|
|E-Mail-Vertraulichkeit|EmailSensitivity|email_sensitivity|Vertraulichkeitseinstellung der Nachricht: **0** – Keine; **1** Persönlich; **2** – Privat; **3** - CompanyConfidential.|
|E-Mail-Satz|EmailSet|Email_set|Gruppen-ID für alle Nachrichten im gleichen E-Mail-Satz.|
|EmailThread*||Email_thread|Position der Nachricht innerhalb des E-Mail-Satz; besteht aus Knoten-IDs vom Stamm bis zur aktuellen Nachricht und wird durch Punkte (.) getrennt.|
|||Export_native_path|Der Pfad der exportierten Datei.|
|Extrahierter Inhaltstyp||Native_type|Extrahierter Inhaltstyp in Form eines Mimetyps; beispiel: **image/jpeg**|
|||Extracted_text_path|Der Pfad zur extrahierten Textdatei im Export.|
|ExtractedTextLength*||Extracted_text_length|Anzahl der Zeichen im extrahierten Text.|
|FamilyDuplicateSet*||Family_duplicate_set|Numerischer Bezeichner für Familien, die genaue Duplikate voneinander sind (derselbe Inhalt und alle gleichen Anlagen).|
|Familien-ID|FamilyId|Family_ID|Familien-ID-Gruppen alle Elemente; Für E-Mails umfasst dies die Nachricht und alle Anlagen. für Dokumente umfasst dies das Dokument und alle eingebetteten Elemente.|
|Familiengröße||Family_size|Die Anzahl der Dokumente in der Familie.|
|Dateiklasse|FileClass|File_class|Für Inhalte aus SharePoint und OneDrive: **Document**; für Inhalte aus Exchange: **E-Mail** oder **Anlage**.|
|Datei-ID|FileId|File_ID|Dokument-ID innerhalb des Falls eindeutig.|
|Dateisystemdatum erstellt||File_system_date_created|Erstelltes Datum aus dem Dateisystem (gilt nur für nicht Office 365 Daten).|
|Dateisystemdatum geändert||File_system_date_modified|Änderungsdatum aus dem Dateisystem (gilt nur für nicht Office 365 Daten).|
|Dateityp|FileType||Dateityp des Elements basierend auf der Dateierweiterung.|
|Gruppen-ID|GroupID||Gruppen-ID für gruppierende Inhalte.|
|Verfügt über Eine Anlage|HasAttachment|Email_has_attachment|Gibt an, ob die Nachricht Anlagen enthält.|
|Hat Anwalt|HasAttorney||**True,** wenn mindestens einer der Teilnehmer in der Anwaltsliste gefunden wird. Andernfalls ist der Wert **False**.|
|HasText*||Has_text|Gibt an, ob das Element Text enthält. mögliche Werte sind **True** und **False**.|
|Unveränderliche ID||Immutable_ID|Diese ID wird verwendet, um ein Dokument innerhalb eines Überprüfungssatzs eindeutig zu identifizieren. Dieses Feld kann nicht in einer Überprüfungssatzsuche verwendet werden, und die ID kann nicht für den Zugriff auf ein Dokument am systemeigenen Speicherort verwendet werden.|
|Inklusiver Typ|InclusiveType|Inclusive_type|Inklusiver Typ, der für die Analyse berechnet wird: **0** – nicht einschließlich; **1** – einschließlich; **2** – inklusives Minus; **3** – inklusive Kopie.|
|In Reply To Id||In_reply_to_ID|In reply to ID from the message.|
|InputFileExtension||Original_file_extension|Die ursprüngliche Dateierweiterung der Datei.|
|InputFileID||Input_file_ID|Die Datei-ID des Elements der obersten Ebene im Überprüfungssatz. Bei einer Anlage ist diese ID die ID des übergeordneten Elements. Dies kann zum Gruppieren von Familien verwendet werden.|
|Ist moderne Anlage| IsModernAttachment|  |Diese Datei ist eine moderne Anlage oder verknüpfte Datei.|
|Is from document version | IsFromDocumentVersion |  |Das aktuelle Dokument ist aus einer anderen Version eines anderen Dokuments.|
|Ist E-Mail-Anlage | IsEmailAttachment|  |Dieses Element ist aus einer E-Mail-Anlage, die als angefügtes Element der Nachricht angezeigt wird.|
|Is inline attachment| IsInlineAttachment|  |Dies wurde inline angefügt und wird im Textkörper der Nachricht angezeigt.|
|Ist repräsentativ|IsRepresentative|Is_representative|Ein Dokument in jedem Satz exakter Duplikate wird als repräsentativ gekennzeichnet.|
|Elementklasse|ItemClass|Item_class|Vom #A0 bereitgestellte Elementklasse; z. **B. IPM. Hinweis**|
|Datum der letzten Änderung|LastModifiedDate|Doc_date_modified|Datum der letzten Änderung aus Dokumentmetadaten.|
|Lade-ID|LoadId|Load_ID|Die ID des Lastensatz, in dem das Element einem Überprüfungssatz hinzugefügt wurde.|
|Speicherort|Speicherort|Speicherort|Zeichenfolge, die den Speicherort angibt, von dem Dokumente stammen.<br /><br />**Importierte Daten** – nicht Office 365 Daten<br />**Teams** – Microsoft Teams<br />**Exchange** - Exchange Postfächer<br />**SharePoint** - SharePoint Websites<br />**OneDrive** - OneDrive Konten|
|Ortsname|LocationName|Location_name|Zeichenfolge, die die Quelle des Elements identifiziert. Für Exchange ist dies die #A0 des Postfachs. für SharePoint und OneDrive die URL für die Websitesammlung.|
|||Marked_as_pivot|Diese Datei ist der Pivot in einem nahezu doppelten Satz.|
|Als repräsentativ gekennzeichnet|MarkAsRepresentative||Ein Dokument aus jedem Satz exakter Duplikate wird als Vertreter gekennzeichnet.|
|Enddatum der Besprechung|MeetingEndDate|Meeting_end_date|Enddatum der Besprechung für Besprechungen.|
|Anfangsdatum der Besprechung|MeetingStartDate|Meeting_start_date|Besprechungsanfangsdatum für Besprechungen.|
|Nachrichten art|MessageKind|Message_kind|Der Typ der Nachricht, nach der gesucht werden soll. Mögliche Werte: Kontakte docs email **<br /> <br /> <br /> <br /> <br /> externaldata <br /> faxes <br /> in <br /> journals <br /> meetings <br /> microsoftteams** (returns items from chats, meetings, and calls in Microsoft Teams) **<br /> notes posts <br /> <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|ModernAttachment_ParentId||ModernAttachment_ParentId||
|Native Erweiterung|NativeExtension|Native_extension|Native Erweiterung des Elements.|
|Systemeigener Dateiname|NativeFileName|Native_file_name|Systemeigener Dateiname des Elements.|
|NativeMD5||Native_MD5|#A0 (128-Bit-Hashwert) des Dateidatenstroms.|
|NativeSHA256||Native_SHA_256|SHA256-Hashwert (256-Bit-Hashwert) des Dateidatenstroms.|
|ND/ET-Sortierung: Ausschließen von Anlagen|NdEtSortExclAttach|ND_ET_sort_excl_attach|Verkettung des E-Mail-Threads (ET) und des ND(Near-Duplicate)-Satz. Dieses Feld wird zur effizienten Sortierung zur Überprüfungszeit verwendet. Ein **D-Präfix** wird ND-Sätzen vorangestellt, und ein **E-Präfix** wird ET-Sätzen vorangestellt.|
|ND/ET-Sortierung: Einschließlich Anlagen|NdEtSortInclAttach|ND_ET_sort_incl_attach|Verkettung eines E-Mail-Thread(ET)-Satz und einer ND-Gruppe (Near-Duplicate). Dieses Feld wird zur effizienten Sortierung zur Überprüfungszeit verwendet. Ein **D-Präfix** wird ND-Sätzen vorangestellt, und ein **E-Präfix** wird ET-Sätzen vorangestellt. Jedem E-Mail-Element in einem ET-Satz folgen die entsprechenden Anlagen.|
|O365-Autoren||O365_authors|Autor aus SharePoint.|
|O365 erstellt von||O365_created_by|Erstellt von SharePoint.|
|O365-Datum erstellt||O365_date_created|Erstelltes Datum aus SharePoint.|
|O365-Datum geändert||O365_date_modified|Datum der letzten Änderung aus SharePoint.|
|O365 geändert von||O365_modified_by|Geändert von von SharePoint.|
|Übergeordnete ID|ParentId|Container_ID|Id des übergeordneten Elements.|
|ParentNode||Parent_node|Die nächste vorangehende E-Mail-Nachricht im E-Mail-Thread.|
|Teilnehmerdomänen|ParticipantDomains|Email_participant_domains|Liste aller Domänen der Teilnehmer einer Nachricht.|
|Teilnehmer|Teilnehmer|Email_participants|Liste aller Teilnehmer einer Nachricht; z. B. Sender, An, Cc, Bcc.|
|Pivot-ID|PivotId|Pivot_ID|Die ID eines Pivots.|
|Potenziell privilegiert|PotentiallyPrivileged|Potentially_privileged|True, wenn das Erkennungsmodell der Anwalts-Client-Rechte das Dokument als potenziell privilegiert betrachtet|
|Verarbeitungsstatus|ProcessingStatus|Error_code|Verarbeitungsstatus, nachdem das Element einem Überprüfungssatz hinzugefügt wurde.|
|Perzentil lesen|ReadPercentile||Lesen Sie perzentil für das Dokument basierend auf Relevanz.|
|Auszahlung|Auszahlung|Email_date_received|Das Datum und die Uhrzeit, zu der die E-Mail in UTC empfangen wurde.|
|Anzahl der Empfänger||Recipient_count|Anzahl der Empfänger in der Nachricht.|
|Empfängerdomänen|RecipientDomains|Email_recipient_domains|Liste aller Domänen von Empfängern einer Nachricht.|
|Empfänger|Empfänger|Email_recipients|Liste aller Empfänger einer Nachricht (An, Cc, Bcc).|
|||Redacted_file_path|Der Pfad der rotierten Ersetzungsdatei im Export.|
|||Redacted_text_path|Der Pfad des ersetzungsaktivierten Textdateis im Export. Nur für interne Verwendung durch Microsoft.|
|Relevanztag Fallproblem 1||Relevance_tag_case_issue_1|Relevanztag Fall 1 aus Relevanz.|
|Relevanzpunktzahl|RelevanceScore||Relevanzpunktzahl eines Dokuments basierend auf Relevanz.|
|Relevanztag|RelevanceTag||Relevanzpunktzahl eines Dokuments basierend auf Relevanz.|
|Repräsentative ID|RepresentativeId||Numerischer Bezeichner für jeden Satz exakter Duplikate.|
|||Row_number|Die Zeilennummer des Elements in der Ladedatei.|
|Absender|Absender|Email_sender|Absenderfeld (Von) für Nachrichtentypen. Format ist **DisplayName \<SmtpAddress>**.|
|Absender/Autor|SenderAuthor||Berechnetes Feld, das aus dem Absender oder Autor des Elements besteht.|
|Absenderdomäne|SenderDomain|Email_sender_domain|Domäne des Absenders.|
|Gesendet|Gesendet|Email_date_sent|Gesendetes Datum der Nachricht.|
|Set Order: Inclusive First|SetOrderInclusivesFirst|Set_order_inclusives_first|Sortierfeld – E-Mail und Anlagen: counterchronologisch; documents: pivot first then by descending similarity score.|
|SimilarityPercent||Similarity_percent|Gibt an, wie ähnlich ein Dokument dem Pivot des beinahe doppelten Satz ist.|
|Native Dateigröße|Size|Native_size|Die Anzahl der Bytes des systemeigenen Elements.|
|Betreff|Betreff|Email_subject|Betreff der Nachricht.|
|Betreff/Titel|SubjectTitle||Berechnetes Feld, das aus dem Betreff oder Titel des Elements besteht.|
|Tags|Tags|Tags|Tags, die in einem Überprüfungssatz angewendet werden.|
|Liste der Designs|ThemesList|Themes_list|Designs list as calculated for analytics.|
|Titel|Titel|Doc_title|Titel aus den Dokumentmetadaten.|
|An|An|Email_to|To-Feld für Nachrichtentypen. Format ist **DisplayName \<SmtpAddress>**|
|Eindeutig in E-Mail-Satz|UniqueInEmailSet||**False,** wenn ein Duplikat der Anlage im E-Mail-Satz vorhanden ist.|
|Wurde behoben|WasRemediated|Was_Remediated|**True,** wenn das Element behoben wurde, andernfalls **False**.|
|Wörter zählen|WordCount|Word_count|Anzahl der Wörter im Element.|
|||||

> [!NOTE]
> Weitere Informationen zu durchsuchbaren Eigenschaften beim Durchsuchen Office 365 Inhaltsspeicherorten beim Sammeln von Daten für einen Advanced eDiscovery-Fall finden Sie unter [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).