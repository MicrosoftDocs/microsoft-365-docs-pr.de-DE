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
description: Informationen zu DLP-Richtlinienbedingungen und -Ausnahmen
ms.openlocfilehash: 4fd61e0f288ef0dfd34af1d2f4dde3dbfef9cee9
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226935"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>DLP-Richtlinienbedingungen, -Ausnahmen und -Aktionen

Bedingungen und Ausnahmen in DLP-Richtlinien identifizieren vertrauliche Elemente, auf die die Richtlinie angewendet wird. Aktionen definieren, was geschieht, wenn eine Ausnahmebedingung erfüllt ist.

- Bedingungen definieren, was eingeschlossen werden soll
- Ausnahmen definieren, was ausgeschlossen werden soll.
- Aktionen definieren, was als Folge der Erfüllung von Bedingungen oder Ausnahmen geschieht

Die meisten Bedingungen und Ausnahmen haben eine Eigenschaft, die einen oder mehrere Werte unterstützt. Wenn z. B. die DLP-Richtlinie auf Exchange E-Mails angewendet wird, erfordert die Bedingung **"Absender"** den Absender der Nachricht. Einige Bedingungen weisen zwei Eigenschaften auf. Wenn Sie beispielsweise die Bedingung **Eine Nachrichtenkopfzeile enthält mindestens eines dieser Wörter** verwenden, muss eine Eigenschaft den Nachrichtenkopf und eine zweite Eigenschaft den zu suchenden Text im Nachrichtenkopf angeben. Einige Bedingungen oder Ausnahmen haben keine Eigenschaften. Die Bedingung **"Anlage" ist beispielsweise kennwortgeschützte,** sucht einfach nach Anlagen in Nachrichten, die kennwortgeschützten sind.

Aktionen erfordern in der Regel zusätzliche Eigenschaften. Wenn die DLP-Richtlinienregel z. B. eine Nachricht umleitet, müssen Sie angeben, wohin die Nachricht umgeleitet wird.
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
|Absender ist |bedingung: *From* <br/> exception: *ExceptIfFrom*      |Addresses |     Nachrichten, die von den angegebenen Postfächern, E-Mail-Benutzern, E-Mail-Kontakten oder Microsoft 365-Gruppen in der Organisation gesendet werden.|
|IP-Adresse des Absenders lautet     |bedingung: *SenderIPRanges*<br/> exception: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Nachrichten, in denen die IP-Adresse des Absenders der angegebenen IP-Adresse entsprecht oder innerhalb des angegebenen IP-Adressbereichs liegt.       |
|Absenderadresse enthält Wörter   | bedingung: *FromAddressContainsWords* <br/> exception: *ExceptIfFromAddressContainsWords*        |   Words      |   Nachrichten, die die angegebenen Wörter in der E-Mail-Adresse des Absenders enthalten.|
| Absenderadresse stimmt mit Mustern überein    | condition: *FromAddressMatchesPatterns* <br/> exception: *ExceptFromAddressMatchesPatterns*       |      Muster   |  Nachrichten, bei denen die E-Mail-Adresse des Absenders Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.  |
|Absenderdomäne ist  |  bedingung: *SenderDomainIs* <br/> exception: *ExceptIfSenderDomainIs*       |DomainName         |     Nachrichten, bei denen die Domäne der E-Mail-Adresse des Absenders dem angegebenen Wert entspricht. Wenn Sie Absenderdomänen suchen müssen, die die angegebene Domäne *enthalten* (z. B. eine beliebige Unterdomäne einer Domäne), verwenden Sie **die Bedingung "Absenderadressenübereinstimmungen"**(*FromAddressMatchesPatterns*), und geben Sie die Domäne mithilfe der Folgenden an: \. "domain \. com$".    |
|Absenderbereich    | Bedingung: *FromScope* <br/> exception: *ExceptIfFromScope*    | UserScopeFrom    |    Nachrichten, die von internen oder externen Absendern gesendet werden.    |
|Die angegebenen Eigenschaften des Absenders enthalten eines dieser Wörter|condition: *SenderADAttributeContainsWords* <br/> exception: *ExceptIfSenderADAttributeContainsWords*|First-Eigenschaft: `ADAttribute` <p> Second-Eigenschaft: `Words`|Nachrichten, bei denen das angegebene Active DirectoryAttribut des Absenders eines der angegebenen Wörter enthält.|
|Die angegebenen Eigenschaften des Absenders entsprechen diesen Textmustern|bedingung: *SenderADAttributeMatchesPatterns* <br/> exception: *ExceptIfSenderADAttributeMatchesPatterns*|First-Eigenschaft: `ADAttribute` <p> Second-Eigenschaft: `Patterns`|Nachrichten, bei denen das angegebene Active Directory-Attribut des Absenders Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.|

### <a name="recipients"></a>Empfänger

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell** |    **Eigenschaftstyp** | **description**|
|---------|---------|---------|---------|
|Empfänger lautet|  bedingung: *SentTo* <br/> exception: *ExceptIfSentTo* | Addresses | Nachrichten, bei denen es sich bei einem der Empfänger um das angegebene Postfach, den E-Mail-Benutzer oder den E-Mail-Kontakt in der Organisation handelt. Die Empfänger können in den Feldern **To**, **Cc** oder **Bcc** der Nachricht angegeben werden.  |
|Empfängerdomäne lautet|   bedingung: *RecipientDomainIs* <br/> exception: *ExceptIfRecipientDomainIs* |   DomainName |    Nachrichten, bei denen die Domäne der E-Mail-Adresse des Empfängers mit dem angegebenen Wert übereinstimmt.|
|Empfängeradresse enthält Wörter|  bedingung: *AnyOfRecipientAddressContainsWords* <br/> exception: *ExceptIfAnyOfRecipientAddressContainsWords*|  Words|  Nachrichten, die die angegebenen Wörter in der E-Mail-Adresse des Empfängers enthalten. <br/>**Hinweis**: Diese Bedingung berücksichtigt keine Nachrichten, die an Proxyadressen des Empfängers gesendet werden. Es werden nur Nachrichten berücksichtigt, die an die primäre E-Mail-Adresse des Empfängers gesendet werden.|
|Empfängeradresse stimmt mit Mustern überein| bedingung: *AnyOfRecipientAddressMatchesPatterns* <br/> exception: *ExceptIfAnyOfRecipientAddressMatchesPatterns*| Muster    |Nachrichten, bei denen die E-Mail-Adresse des Empfängers Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen. <br/> **Hinweis**: Diese Bedingung berücksichtigt keine Nachrichten, die an Proxyadressen des Empfängers gesendet werden. Es werden nur Nachrichten berücksichtigt, die an die primäre E-Mail-Adresse des Empfängers gesendet werden.|
|Gesendet an Mitglied von| condition: *SentToMemberOf* <br/> ausnahme: *ExceptIfSentToMemberOf*|  Addresses|  Nachrichten, die Empfänger enthalten, die Mitglieder der angegebenen Verteilergruppe, E-Mail-aktivierten Sicherheitsgruppe oder Microsoft 365 Gruppe sind. Die Gruppe kann in den Feldern **To**, **Cc** oder **Bcc** der Nachricht sein.|

### <a name="message-subject-or-body"></a>Nachrichtenbetreff oder -text

|**Bedingung oder Ausnahme in DLP** | **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell** |**Eigenschaftstyp**| **description**|
|---------|---------|---------|---------|
|Betreff enthält Wörter oder Ausdrücke| bedingung: *SubjectContainsWords* <br/> exception: *ExceptIf SubjectContainsWords*| Words   |Nachrichten, deren Feld Subject die angegebenen Wörter enthält.|
|Betreff stimmt mit Mustern überein|condition: *SubjectMatchesPatterns* <br/> exception: *ExceptIf SubjectMatchesPatterns*|Muster   |Nachrichten, bei denen das Feld Betreff Textmuster enthält, die den angegebenen regulären Ausdrücken entsprechen.|
|Inhalt enthält|  condition: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Nachrichten oder Dokumente, die vertrauliche Informationen enthalten, wie durch DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) definiert.|
| Muster für Betreff- oder Textüberstimmungen    | bedingung: *SubjectOrBodyMatchesPatterns* <br/> exception: *ExceptIfSubjectOrBodyMatchesPatterns*    | Muster    | Nachrichten, bei denen das Betrefffeld oder der Nachrichtentext Textmuster enthält, die den angegebenen regulären Ausdrücken entsprechen.    |
| Betreff oder Text enthält Wörter    | condition: *SubjectOrBodyContainsWords* <br/> exception: *ExceptIfSubjectOrBodyContainsWords*    | Words    | Nachrichten mit den angegebenen Wörtern im Betrefffeld oder Nachrichtentext    |


### <a name="attachments"></a>Anlagen

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell**| **Eigenschaftstyp**   |**description**|
|---------|---------|---------|---------|
|Anlage ist passwortgeschützt|condition: *DocumentIsPasswordProtected* <br/> exception: *ExceptIfDocumentIsPasswordProtected*|keine| Nachrichten, bei denen eine Anlage kennwortgeschützt ist (und daher nicht überprüft werden kann). Die Kennworterkennung funktioniert nur für Office Dokumente, .zip-Dateien und 7z-Dateien.|
|Die Dateierweiterung der Anlage lautet|condition: *ContentExtensionMatchesWords* <br/> ausnahme: *ExceptIfContentExtensionMatchesWords*|  Words   |Nachrichten, bei denen die Dateierweiterung einer Anlage einem der angegebenen Wörter entspricht.|
|Inhalt einer E-Mail-Anlage konnte nicht gescannt werden|bedingung: *DocumentIsUnsupported* <br/>exception: *ExceptIf DocumentIsUnsupported*|   N/V|    Nachrichten, für die eine Anlage von Exchange Online nicht systemintern erkannt wird.|
|Der Inhalt einer E-Mail-Anlage wurde nicht vollständig gescannt.|   bedingung: *ProcessingLimitExceeded* <br/> exception: *ExceptIfProcessingLimitExceeded*|    N/V |Nachrichten, bei denen das Regelmodul das Prüfen der Anlagen nicht abschließen konnte. Sie können diese Bedingung zum Erstellen von Regeln verwenden, die zusammenarbeiten, um Nachrichten zu ermitteln und zu verarbeiten, deren Inhalt nicht vollständig überprüft werden konnte.|
|Dokumentname enthält Wörter|bedingung: *DocumentNameMatchesWords* <br/> exception: *ExceptIfDocumentNameMatchesWords* |Words  |Nachrichten, bei denen der Dateiname einer Anlage mit einem der angegebenen Wörter übereinstimmt.|
|Übereinstimmungsmuster für Dokumentnamen|condition: *DocumentNameMatchesPatterns* <br/> exception: *ExceptIfDocumentNameMatchesPatterns*|    Muster    |Nachrichten, bei denen der Dateiname einer Anlage Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.|
|Dokumenteigenschaft lautet|bedingung: *ContentPropertyContainsWords* <br/> ausnahme: *ExceptIfContentPropertyContainsWords* |Words| Nachrichten oder Dokumente, bei denen die Dateierweiterung einer Anlage mit einem der angegebenen Wörter übereinstimmt.|
|Dokumentgröße gleich oder größer als| condition: *DocumentSizeOver* <br/> exception: *ExceptIfDocumentSizeOver*|    Size    |Nachrichten, bei denen eine Anlage größer oder gleich dem angegebenen Wert ist.|
|Der Inhalt einer Anlage enthält eines dieser Wörter.| bedingung: *DocumentContainsWords* <br/> exception: *ExceptIfDocumentContainsWords* |`Words`|Nachrichten, bei denen eine Anlage die angegebenen Wörter enthält.|
|Alle Anlageninhalte entsprechen diesen Textmustern|condition: *DocumentMatchesPatterns* <br/> exception: *ExceptIfDocumentMatchesPatterns* |`Patterns`|Nachrichten, bei denen eine Anlage Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen. |

### <a name="message-headers"></a>Nachrichtenkopfzeilen

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell**| **Eigenschaftstyp**|  **description**|
|---------|---------|---------|---------|
|Kopfzeile enthält Wörter oder Ausdrücke|bedingung: *HeaderContainsWords* <br/> exception: *ExceptIfHeaderContainsWords*|  Hashtabelle  |Nachrichten, die das angegebene Header-Feld enthalten, und der Wert des Header-Felds enthält die angegebenen Wörter.|
|Kopfzeile stimmt mit Mustern überein|   condition: *HeaderMatchesPatterns* <br/> exception: *ExceptIfHeaderMatchesPatterns*|    Hashtabelle  |Nachrichten, die das angegebene Header-Feld enthalten, und der Wert des Header-Felds enthält die angegebenen regulären Ausdrücke.|

### <a name="message-properties"></a>Nachrichteneigenschaften

|**Bedingung oder Ausnahme in DLP**| **Bedingungs-/Ausnahmeparameter in Microsoft 365 PowerShell**| **Eigenschaftstyp**   |**description**|
|---------|---------|---------|---------|
| Mit Wichtigkeit    | condition: *WithImportance* <br/> exception: *ExceptIfWithImportance*    | Importance    | Nachrichten, die mit der angegebenen Wichtigkeitsstufe gekennzeichnet sind.    |
| Inhaltszeichensatz enthält Wörter    | condition: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Nachrichten, die beliebige der angegebenen Zeichensatznamen enthalten.    |
| Hat Absenderüberschreibung    | condition: *HasSenderOverride* <br/> exception: *ExceptIfHasSenderOverride*    | N/V    | Nachrichten, bei denen der Absender ausgewählt hat, eine Data Loss Prevention (DLP)-Richtlinie außer Kraft zu setzen. Weitere Informationen zu DLP-Richtlinien finden Sie unter [Informationen zur Verhinderung von Datenverlust](./dlp-learn-about-dlp.md) |
| Übereinstimmungen mit dem Nachrichtentyp    | bedingung: *MessageTypeMatches* <br/> ausnahme: *ExceptIfMessageTypeMatches*    | MessageType    | Nachrichten vom angegebenen Typ.    |
|Die Nachrichtengröße ist größer als oder gleich| bedingung: *MessageSizeOver* <br/> exception: *ExceptIfMessageSizeOver* |`Size`|Nachrichten, deren Gesamtgröße (Nachricht sowie Anlagen) größer oder gleich dem angegebenen Wert ist. **Hinweis**: Grenzwerte für die Nachrichtengröße für Postfächer werden vor E-Mail-Flussregeln ausgewertet. Eine Nachricht, die für ein Postfach zu groß ist, wird zurückgewiesen, bevor eine Regel mit dieser Bedingung auf diese Nachricht angewendet wird.|

## <a name="actions-for-dlp-policies"></a>Aktionen für DLP-Richtlinien

In dieser Tabelle werden die aktionen beschrieben, die in DLP verfügbar sind.


|**-Aktion in DLP**|**Aktionsparameter in Microsoft 365 PowerShell**|**Eigenschaftstyp**|**description**|
|---------|---------|---------|---------|
|Kopfzeile festlegen|SetHeader|First-Eigenschaft: *Headername* </br> Second property: *Header Value*|Der SetHeader-Parameter gibt eine Aktion für die DLP-Regel an, die ein Kopfzeilenfeld und einen Wert in der Nachrichtenkopfzeile hinzufügt oder ändert. Dieser Parameter verwendet die Syntax "HeaderName:HeaderValue". Sie können mehrere Headernamen- und Wertpaare durch Kommas getrennt angeben.|
|Header entfernen| RemoveHeader| Erste Eigenschaft: *MessageHeaderField*</br> Zweite Eigenschaft: *String*|  Der Parameter RemoveHeader gibt eine Aktion für die DLP-Regel an, die ein Kopfzeilenfeld aus dem Nachrichtenkopf entfernt. Dieser Parameter verwendet die Syntax "HeaderName" oder "HeaderName:HeaderValue". Sie können mehrere Kopfzeilennamen oder Headernamen- und Wertpaare durch Kommas getrennt angeben.|
|Umleiten der Nachricht an bestimmte Benutzer|*RedirectMessageTo*|Addresses| Leitet die Nachricht an die angegebene Empfänger um. Die Nachricht wird nicht an die Originalempfänger übermittelt, und der Absender und die Originalempfänger werden nicht benachrichtigt.|
|Weiterleiten der Nachricht zur Genehmigung an den Vorgesetzten des Absenders| Mittel|First-Eigenschaft: *ModerateMessageByManager*</br> Second-Eigenschaft: *Boolean*|Der Parameter Moderate gibt eine Aktion für die DLP-Regel an, die die E-Mail-Nachricht an einen Moderator sendet. Dieser Parameter verwendet die Folgende Syntax: @{ModerateMessageByManager = <$true \| $false>;|
|Weiterleiten der Nachricht zur Genehmigung an bestimmte Genehmiger| Mittel|First-Eigenschaft: *ModerateMessageByUser*</br>Zweite Eigenschaft: *Addresses*|Der Parameter Moderate gibt eine Aktion für die DLP-Regel an, die die E-Mail-Nachricht an einen Moderator sendet. Dieser Parameter verwendet die Syntax: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Empfänger hinzufügen|AddRecipients|First-Eigenschaft: *Field*</br>Zweite Eigenschaft: *Addresses*| Fügt dem Feld "An/Cc/Bcc" der Nachricht einen oder mehrere Empfänger hinzu. Dieser Parameter verwendet die Syntax: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Hinzufügen des Vorgesetzten des Absenders als Empfänger|AddRecipients | First-Eigenschaft: *AddedManagerAction*</br>Second-Eigenschaft: *Field* | Fügt den Vorgesetzten des Absenders als angegebenen Empfängertyp der Nachricht hinzu (To, Cc, Bcc) oder leitet die Nachricht an den Vorgesetzten des Absenders ohne Benachrichtigung des Absenders oder des Empfängers um. Diese Aktion funktioniert nur, wenn das Manager -Attribut des Absenders in Active Directory definiert ist. Dieser Parameter verwendet die Folgende Syntax: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|
Vorangestellter Betreff    |PrependSubject    |Zeichenfolge    |Fügt den angegebenen Text am Anfang des Felds Subject der Nachricht ein. Verwenden Sie ein Leerzeichen oder einen Doppelpunkt (:) als letztes Zeichen des angegebenen Texts, um ihn vom ursprünglichen Betrefftext zu unterscheiden.  </br>Um zu verhindern, dass nachrichten, die bereits den Text im Betreff enthalten (z. B. Antworten), dieselbe Zeichenfolge hinzugefügt wird, fügen Sie der Regel die Ausnahme "Der Betreff enthält Wörter" (ExceptIfSubjectContainsWords) hinzu.|
|HTML-Haftungsausschluss anwenden    |ApplyHtmlDisclaimer    |First-Eigenschaft: *Text*</br>Second-Eigenschaft: *Location*</br>Dritte Eigenschaft: *Fallbackaktion*    |Wendet den angegebenen HTML-Haftungsausschluss auf den erforderlichen Speicherort der Nachricht an.</br>Dieser Parameter verwendet die Syntax: @{ Text = " " ; Location = <\| Append Prepend>; FallbackAction = <Wrap \| Ignore Reject> \| }|
|Entfernen des Office 365-Nachrichtenverschlüsselung- und Rechteschutzes    | RemoveRMSTemplate | n/v| Entfernt Office 365 Verschlüsselung, die auf eine E-Mail angewendet wird|
