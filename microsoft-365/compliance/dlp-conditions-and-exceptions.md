---
title: DLP-Richtlinienbedingungen, -Ausnahmen und -Aktionen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: Informationen zu dlp-Richtlinienbedingungen und -Ausnahmen
ms.openlocfilehash: 54c66f36e6a4b59147461ad154a4012f62bda77f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114391"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>DLP-Richtlinienbedingungen, -Ausnahmen und -Aktionen

Bedingungen und Ausnahmen in DLP-Richtlinien identifizieren vertrauliche Elemente, auf die die Richtlinie angewendet wird. Aktionen definieren, was als Folge einer Bedingung der Ausnahme erfüllt wird.

- Bedingungen definieren, was enthalten sein soll
- Ausnahmen definieren, was ausgeschlossen werden soll.
- Aktionen definieren, was als Folge der erfüllten Bedingung oder Ausnahme geschieht
 
Die meisten Bedingungen und Ausnahmen verfügen über eine Eigenschaft, die einen oder mehrere Werte unterstützt. Wenn z. B. die DLP-Richtlinie auf Exchange  angewendet wird, erfordert der Absender der Nachricht den Absender der Nachricht. Einige Bedingungen weisen zwei Eigenschaften auf. Wenn Sie beispielsweise die Bedingung **Eine Nachrichtenkopfzeile enthält mindestens eines dieser Wörter** verwenden, muss eine Eigenschaft den Nachrichtenkopf und eine zweite Eigenschaft den zu suchenden Text im Nachrichtenkopf angeben. Einige Bedingungen oder Ausnahmen haben keine Eigenschaften. Die Anlage ist beispielsweise **kennwortgeschützt** und sucht einfach nach Anlagen in Nachrichten, die kennwortgeschützt sind.

Für Aktionen sind in der Regel zusätzliche Eigenschaften erforderlich. Wenn beispielsweise die DLP-Richtlinienregel eine Nachricht umleitiert, müssen Sie angeben, an welche Stelle die Nachricht umgeleitet wird. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Bedingungen und Ausnahmen für DLP-Richtlinien

In den Tabellen in den folgenden Abschnitten werden die Bedingungen und Ausnahmen beschrieben, die in DLP verfügbar sind.

- [Absender](#senders)
- [Empfänger](#recipients)
- [Nachrichtenbetreff oder -text](#message-subject-or-body)
- [Anlagen](#attachments)
- [Nachrichtenkopfzeilen](#message-headers)
- [Nachrichteneigenschaften](#message-properties)

### <a name="senders"></a>Absender


|**Bedingung oder Ausnahme in DLP**  |**Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell** |**Eigenschaftstyp**  |**description**|
|---------|---------|---------|---------|
|Absender ist |Bedingung: *Von* <br/> Ausnahme: *ExceptIfFrom*      |Addresses |     Nachrichten, die von den angegebenen Postfächern, E-Mail-Benutzern, E-Mail-Kontakten oder Microsoft 365 in der Organisation gesendet werden.|
|IP-Adresse des Absenders lautet     |Bedingung: *SenderIPRanges*<br/> Ausnahme: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Nachrichten, in denen die IP-Adresse des Absenders der angegebenen IP-Adresse entsprecht oder innerhalb des angegebenen IP-Adressbereichs liegt.       |
|Absenderadresse enthält Wörter   | condition: *FromAddressContainsWords* <br/> Ausnahme: *ExceptIfFromAddressContainsWords*        |   Words      |   Nachrichten, die die angegebenen Wörter in der E-Mail-Adresse des Absenders enthalten.|
| Absenderadresse entspricht Mustern    | bedingung: *FromAddressMatchesPatterns* <br/> Ausnahme: *ExceptFromAddressMatchesPatterns*       |      Muster   |  Nachrichten, bei denen die E-Mail-Adresse des Absenders Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.  |
|Absenderdomäne ist  |  Bedingung: *SenderDomainIs* <br/> Ausnahme: *ExceptIfSenderDomainIs*       |DomainName         |     Nachrichten, bei denen die Domäne der E-Mail-Adresse des Absenders dem angegebenen Wert entspricht. Wenn Sie Absenderdomänen  suchen müssen, die die angegebene Domäne enthalten (z. B. eine beliebige Unterdomäne einer Domäne), verwenden Sie **die** Bedingung Absenderadresse entspricht (*FromAddressMatchesPatterns*) und geben Sie die Domäne mit der Syntax " \. domain \. com$" an.    |
|Absenderbereich    | Bedingung: *FromScope* <br/> Ausnahme: *ExceptIfFromScope*    | UserScopeFrom    |    Nachrichten, die von internen oder externen Absendern gesendet werden.    |
|Die angegebenen Eigenschaften des Absenders enthalten eines dieser Wörter|Bedingung: *SenderADAttributeContainsWords* <br/> Ausnahme: *ExceptIfSenderADAttributeContainsWords*|First-Eigenschaft: `ADAttribute` <p> Zweite Eigenschaft: `Words`|Nachrichten, bei denen das angegebene Active DirectoryAttribut des Absenders eines der angegebenen Wörter enthält.|
|Die angegebenen Eigenschaften des Absenders entsprechen diesen Textmustern|Bedingung: *SenderADAttributeMatchesPatterns* <br/> Ausnahme: *ExceptIfSenderADAttributeMatchesPatterns*|First-Eigenschaft: `ADAttribute` <p> Zweite Eigenschaft: `Patterns`|Nachrichten, bei denen das angegebene Active Directory-Attribut des Absenders Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.|

### <a name="recipients"></a>Empfänger

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell** |    **Eigenschaftstyp** | **description**|
|---------|---------|---------|---------|
|Empfänger lautet|  Bedingung: *SentTo* <br/> Ausnahme: *ExceptIfSentTo* | Addresses | Nachrichten, bei denen es sich bei einem der Empfänger um das angegebene Postfach, den E-Mail-Benutzer oder den E-Mail-Kontakt in der Organisation handelt. Die Empfänger können in den Feldern **To**, **Cc** oder **Bcc** der Nachricht angegeben werden.  |
|Empfängerdomäne lautet|   Bedingung: *RecipientDomainIs* <br/> Ausnahme: *ExceptIfRecipientDomainIs* |   DomainName |    Nachrichten, bei denen die Domäne der E-Mail-Adresse des Empfängers dem angegebenen Wert entspricht.|
|Empfängeradresse enthält Wörter|  condition: *AnyOfRecipientAddressContainsWords* <br/> Ausnahme: *ExceptIfAnyOfRecipientAddressContainsWords*|  Words|  Nachrichten, die die angegebenen Wörter in der E-Mail-Adresse des Empfängers enthalten. <br/>**Hinweis**: Diese Bedingung berücksichtigt keine Nachrichten, die an Proxyadressen des Empfängers gesendet werden. Es werden nur Nachrichten berücksichtigt, die an die primäre E-Mail-Adresse des Empfängers gesendet werden.|
|Empfängeradresse entspricht Mustern| condition: *AnyOfRecipientAddressMatchesPatterns* <br/> Ausnahme: *ExceptIfAnyOfRecipientAddressMatchesPatterns*| Muster    |Nachrichten, bei denen die E-Mail-Adresse des Empfängers Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen. <br/> **Hinweis**: Diese Bedingung berücksichtigt keine Nachrichten, die an Proxyadressen des Empfängers gesendet werden. Es werden nur Nachrichten berücksichtigt, die an die primäre E-Mail-Adresse des Empfängers gesendet werden.|
|An Mitglied von gesendet| Bedingung: *SentToMemberOf* <br/> Ausnahme: *ExceptIfSentToMemberOf*|  Addresses|  Nachrichten, die Empfänger enthalten, die Mitglieder der angegebenen Verteilergruppe, E-Mail-aktivierten Sicherheitsgruppe oder Microsoft 365 sind. Die Gruppe kann in den Feldern **To**, **Cc** oder **Bcc** der Nachricht sein.|

### <a name="message-subject-or-body"></a>Nachrichtenbetreff oder -text

|**Bedingung oder Ausnahme in DLP** | **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell** |**Eigenschaftstyp**| **description**|
|---------|---------|---------|---------|
|Betreff enthält Wörter oder Ausdrücke| Bedingung: *SubjectContainsWords* <br/> Ausnahme: *ExceptIf SubjectContainsWords*| Words   |Nachrichten, deren Feld Subject die angegebenen Wörter enthält.|
|Betreff entspricht Mustern|Bedingung: *SubjectMatchesPatterns* <br/> Ausnahme: *ExceptIf SubjectMatchesPatterns*|Muster   |Nachrichten, bei denen das Feld Subject Textmuster enthält, die den angegebenen regulären Ausdrücken entsprechen.|
|Inhalt enthält|  bedingung: *ContentContainsSensitiveInformation* <br/> Ausnahme *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Nachrichten oder Dokumente, die vertrauliche Informationen enthalten, wie durch DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) definiert.|
| Muster für Betreff- oder Textkörper-Übereinstimmungen    | Bedingung: *SubjectOrBodyMatchesPatterns* <br/> Ausnahme: *ExceptIfSubjectOrBodyMatchesPatterns*    | Muster    | Nachrichten, bei denen das Betrefffeld oder der Nachrichtentext Textmuster enthält, die den angegebenen regulären Ausdrücken entsprechen.    |
| Betreff oder Textkörper enthält Wörter    | Bedingung: *SubjectOrBodyContainsWords* <br/> Ausnahme: *ExceptIfSubjectOrBodyContainsWords*    | Words    | Nachrichten mit den angegebenen Wörtern im Betrefffeld oder Nachrichtentext    |


### <a name="attachments"></a>Anlagen

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell**| **Eigenschaftstyp**   |**description**|
|---------|---------|---------|---------|
|Anlage ist passwortgeschützt|bedingung: *DocumentIsPasswordProtected* <br/> Ausnahme: *ExceptIfDocumentIsPasswordProtected*|keine| Nachrichten, bei denen eine Anlage kennwortgeschützt ist (und daher nicht überprüft werden kann). Die Kennworterkennung funktioniert nur für Office, .zip und 7Z-Dateien.|
|Die Dateierweiterung der Anlage ist|Bedingung: *ContentExtensionMatchesWords* <br/> Ausnahme: *ExceptIfContentExtensionMatchesWords*|  Words   |Nachrichten, bei denen die Dateierweiterung einer Anlage einem der angegebenen Wörter entspricht.|
|Inhalt einer E-Mail-Anlage konnte nicht gescannt werden|condition: *DocumentIsUnsupported* <br/>Ausnahme: *ExceptIf DocumentIsUnsupported*|   N/V|    Nachrichten, für die eine Anlage von Exchange Online nicht systemintern erkannt wird.|
|Inhalt einer E-Mail-Anlage wurde nicht vollständig gescannt|   Bedingung: *ProcessingLimitExceeded* <br/> Ausnahme: *ExceptIfProcessingLimitExceeded*|    N/V |Nachrichten, bei denen das Regelmodul das Prüfen der Anlagen nicht abschließen konnte. Sie können diese Bedingung zum Erstellen von Regeln verwenden, die zusammenarbeiten, um Nachrichten zu ermitteln und zu verarbeiten, deren Inhalt nicht vollständig überprüft werden konnte.|
|Dokumentname enthält Wörter|Bedingung: *DocumentNameMatchesWords* <br/> Ausnahme: *ExceptIfDocumentNameMatchesWords* |Words  |Nachrichten, bei denen der Dateiname einer Anlage einem der angegebenen Wörter entspricht.|
|Dokumentname entspricht Mustern|bedingung: *DocumentNameMatchesPatterns* <br/> Ausnahme: *ExceptIfDocumentNameMatchesPatterns*|    Muster    |Nachrichten, bei denen der Dateiname einer Anlage Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.|
|Dokumenteigenschaft lautet|Bedingung: *ContentPropertyContainsWords* <br/> Ausnahme: *ExceptIfContentPropertyContainsWords* |Words| Nachrichten oder Dokumente, bei denen die Dateierweiterung einer Anlage einem der angegebenen Wörter entspricht.|
|Dokumentgröße gleich oder größer als| bedingung: *DocumentSizeOver* <br/> Ausnahme: *ExceptIfDocumentSizeOver*|    Size    |Nachrichten, bei denen eine Anlage größer oder gleich dem angegebenen Wert ist.|
|Der Inhalt einer Anlage enthält eines der folgenden Wörter:| Bedingung: *DocumentContainsWords* <br/> Ausnahme: *ExceptIfDocumentContainsWords* |`Words`|Nachrichten, bei denen eine Anlage die angegebenen Wörter enthält.|
|Inhalt von Anlagen entspricht diesen Textmustern|Bedingung: *DocumentMatchesPatterns* <br/> Ausnahme: *ExceptIfDocumentMatchesPatterns* |`Patterns`|Nachrichten, bei denen eine Anlage Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen. |

### <a name="message-headers"></a>Nachrichtenkopfzeilen

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell**| **Eigenschaftstyp**|  **description**|
|---------|---------|---------|---------|
|Kopfzeile enthält Wörter oder Ausdrücke|Bedingung: *HeaderContainsWords* <br/> Ausnahme: *ExceptIfHeaderContainsWords*|  #A0  |Nachrichten, die das angegebene Header-Feld enthalten, und der Wert des Header-Felds enthält die angegebenen Wörter.|
|Kopfzeile entspricht Mustern|   Bedingung: *HeaderMatchesPatterns* <br/> Ausnahme: *ExceptIfHeaderMatchesPatterns*|    #A0  |Nachrichten, die das angegebene Header-Feld enthalten, und der Wert des Header-Felds enthält die angegebenen regulären Ausdrücke.|

### <a name="message-properties"></a>Nachrichteneigenschaften

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell**| **Eigenschaftstyp**   |**description**|
|---------|---------|---------|---------|
| Mit Wichtigkeit    | bedingung: *WithImportance* <br/> Ausnahme: *ExceptIfWithImportance*    | Importance    | Nachrichten, die mit der angegebenen Wichtigkeitsstufe markiert sind.    |
| Inhaltszeichensatz enthält Wörter    | Bedingung: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Nachrichten, die beliebige der angegebenen Zeichensatznamen enthalten.    |
| Absenderüberschreibung    | Bedingung: *HasSenderOverride* <br/> Ausnahme: *ExceptIfHasSenderOverride*    | N/V    | Nachrichten, bei denen der Absender ausgewählt hat, eine Data Loss Prevention (DLP)-Richtlinie außer Kraft zu setzen. Weitere Informationen zu DLP-Richtlinien finden Sie [unter Informationen zur Verhinderung von Datenverlust](./dlp-learn-about-dlp.md) |
| Übereinstimmungen mit dem Nachrichtentyp    | bedingung: *MessageTypeMatches* <br/> Ausnahme: *ExceptIfMessageTypeMatches*    | MessageType    | Nachrichten vom angegebenen Typ.    |
|Die Nachrichtengröße ist größer als oder gleich| Bedingung: *MessageSizeOver* <br/> Ausnahme: *ExceptIfMessageSizeOver* |`Size`|Nachrichten, deren Gesamtgröße (Nachricht sowie Anlagen) größer oder gleich dem angegebenen Wert ist. **Hinweis**: Grenzwerte für die Nachrichtengröße für Postfächer werden vor E-Mail-Flussregeln ausgewertet. Eine Nachricht, die für ein Postfach zu groß ist, wird zurückgewiesen, bevor eine Regel mit dieser Bedingung auf diese Nachricht angewendet wird.|

## <a name="actions-for-dlp-policies"></a>Aktionen für DLP-Richtlinien

In dieser Tabelle werden die Aktionen beschrieben, die in DLP verfügbar sind.


|**Aktion in DLP**|**Aktionsparameter in Microsoft 365 PowerShell**|**Eigenschaftstyp**|**description**|
|---------|---------|---------|---------|
|Kopfzeile festlegen|SetHeader|First-Eigenschaft: *Headername* </br> Zweite Eigenschaft: *Header-Wert*|Der Parameter SetHeader gibt eine Aktion für die DLP-Regel an, die ein Kopfzeilenfeld und einen Wert im Nachrichtenkopf hinzufügt oder ändert. Dieser Parameter verwendet die Syntax "HeaderName:HeaderValue". Sie können mehrere Kopfzeilennamen- und Wertpaare durch Kommas getrennt angeben.|
|Header entfernen| RemoveHeader| Erste Eigenschaft: *MessageHeaderField*</br> Zweite Eigenschaft: *String*|  Der Parameter RemoveHeader gibt eine Aktion für die DLP-Regel an, die ein Kopfzeilenfeld aus dem Nachrichtenkopf entfernt. Dieser Parameter verwendet die Syntax "HeaderName" oder "HeaderName:HeaderValue". Sie können mehrere Kopfzeilennamen oder Kopfzeilennamen- und Wertpaare durch Kommas getrennt angeben.|
|Umleiten der Nachricht an bestimmte Benutzer|*RedirectMessageTo*|Addresses| Leitet die Nachricht an die angegebene Empfänger um. Die Nachricht wird nicht an die Originalempfänger übermittelt, und der Absender und die Originalempfänger werden nicht benachrichtigt.|
|Weiterleiten der Nachricht zur Genehmigung an den Vorgesetzten des Absenders| Mittel|First-Eigenschaft: *ModerateMessageByManager*</br> Zweite Eigenschaft: *Boolean*|Der Parameter Moderate gibt eine Aktion für die DLP-Regel an, die die E-Mail-Nachricht an einen Moderator sendet. Dieser Parameter verwendet die Syntax: @{ModerateMessageByManager = <$true \| $false>;|
|Weiterleiten der Nachricht zur Genehmigung an bestimmte genehmigende Benutzer| Mittel|First-Eigenschaft: *ModerateMessageByUser*</br>Zweite Eigenschaft: *Addresses*|Der Parameter Moderate gibt eine Aktion für die DLP-Regel an, die die E-Mail-Nachricht an einen Moderator sendet. Dieser Parameter verwendet die Syntax: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Empfänger hinzufügen|AddRecipients|First-Eigenschaft: *Field*</br>Zweite Eigenschaft: *Addresses*| Fügt dem Feld An/Cc/Bcc der Nachricht einen oder mehrere Empfänger hinzu. Dieser Parameter verwendet die Syntax: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Hinzufügen des Vorgesetzten des Absenders als Empfänger|AddRecipients | First-Eigenschaft: *AddedManagerAction*</br>Zweite Eigenschaft: *Field* | Fügt den Vorgesetzten des Absenders als angegebenen Empfängertyp der Nachricht hinzu ( To, Cc, Bcc ) oder leitet die Nachricht an den Vorgesetzten des Absenders ohne Benachrichtigung des Absenders oder des Empfängers um. Diese Aktion funktioniert nur, wenn das Manager -Attribut des Absenders in Active Directory definiert ist. Dieser Parameter verwendet die Syntax: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Vordefinierter Betreff    |PrependSubject    |String    |Fügt den angegebenen Text am Anfang des Felds Subject der Nachricht ein. Verwenden Sie ein Leerzeichen oder einen Doppelpunkt (:) als letztes Zeichen des angegebenen Texts, um ihn vom ursprünglichen Betrefftext zu unterscheiden.  </br>Um zu verhindern, dass nachrichten, die bereits den Text im Betreff enthalten (z. B. Antworten), dieselbe Zeichenfolge hinzugefügt werden, fügen Sie der Regel die Ausnahme "Der Betreff enthält Wörter" (ExceptIfSubjectContainsWords) hinzu.    
|Anwenden eines HTML-Haftungsausschlusses    |ApplyHtmlDisclaimer    |First-Eigenschaft: *Text*</br>Zweite Eigenschaft: *Location*</br>Dritte Eigenschaft: *Fallbackaktion*    |Wendet den angegebenen HTML-Haftungsausschluss auf den erforderlichen Speicherort der Nachricht an.</br>Dieser Parameter verwendet die Syntax: @{ Text = " " ; Location = <Append \| Prepend>; FallbackAction = <\| Wrap Ignore \| Reject> }
|Entfernen Office 365-Nachrichtenverschlüsselung- und Rechteschutz    | RemoveRMSTemplate | n/v| Entfernt Office 365 auf eine E-Mail angewendete Verschlüsselung|
