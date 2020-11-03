---
title: DLP-Richtlinienbedingungen und-Ausnahmen (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informationen zu DLP-Richtlinienbedingungen und-Ausnahmen
ms.openlocfilehash: 2ce49b15bdb13035a37f6895b4b8865b55a62f78
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841471"
---
# <a name="dlp-policy-conditions-and-exceptions-preview"></a>DLP-Richtlinienbedingungen und-Ausnahmen (Vorschau)

Bedingungen und Ausnahmen in DLP-Richtlinien identifizieren vertrauliche Elemente, auf die die Richtlinie angewendet wird. Bedingungen definieren, was eingeschlossen werden soll, und Ausnahmen definieren, was ausgeschlossen werden soll. Für jede Bedingung gibt es eine entsprechende Ausnahme, und Sie verwenden genau die gleiche Syntax.

 Die meisten Bedingungen und Ausnahmen haben eine Eigenschaft, die einen oder mehrere Werte unterstützt. Wenn beispielsweise die DLP-Richtlinie auf Exchange-e-Mails angewendet wird, erfordert **der Absender der** Bedingung den Absender der Nachricht. Einige Bedingungen weisen zwei Eigenschaften auf. Wenn Sie beispielsweise die Bedingung **Eine Nachrichtenkopfzeile enthält mindestens eines dieser Wörter** verwenden, muss eine Eigenschaft den Nachrichtenkopf und eine zweite Eigenschaft den zu suchenden Text im Nachrichtenkopf angeben. Einige Bedingungen oder Ausnahmen haben keine Eigenschaften. Wenn beispielsweise die Anlage **kennwortgeschützt ist** , sucht die Bedingung einfach nach Anlagen in Nachrichten, die kennwortgeschützt sind.

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Bedingungen und Ausnahmen für DLP-Richtlinien

Die Tabellen in den folgenden Abschnitten beschreiben die Bedingungen und Ausnahmen, die in DLP zur Verfügung stehen.

- [Absender](#senders)
- [Empfänger](#recipients)
- [Nachrichtenbetreff oder -text](#message-subject-or-body)
- [Anlagen](#attachments)
- [Nachrichtenkopfzeilen](#message-headers)
- [Nachrichteneigenschaften](#message-properties)

## <a name="senders"></a>Absender


|**Bedingung oder Ausnahme in DLP**  |**Bedingung/Ausnahmeparameter in Microsoft 365 PowerShell** |**Typ der Eigenschaft**  |**description**|
|---------|---------|---------|---------|
|Absender ist |Bedingung: *from* <br/> Ausnahme: *ExceptIfFrom*      |Addresses |     Nachrichten, die von den angegebenen Postfächern, e-Mail-Benutzern, e-Mail-Kontakten oder Microsoft 365-Gruppen in der Organisation gesendet werden.|
|IP-Adresse des Absenders lautet     |Bedingung: *senderipranges dieses Prädikat*<br/> Ausnahme: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Nachrichten, in denen die IP-Adresse des Absenders der angegebenen IP-Adresse entsprecht oder innerhalb des angegebenen IP-Adressbereichs liegt.       |
|Absenderadresse enthält Wörter   | Bedingung: *FromAddressContainsWords* <br/> Ausnahme: *ExceptIfFromAddressContainsWords*        |   Words      |   Nachrichten, die die angegebenen Wörter in der E-Mail-Adresse des Absenders enthalten.|
| Absenderadresse stimmt mit Mustern überein    | Bedingung: *FromAddressMatchesPatterns* <br/> Ausnahme: *ExceptFromAddressMatchesPatterns*       |      Muster   |  Nachrichten, bei denen die E-Mail-Adresse des Absenders Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.  |
|Absenderdomäne ist  |  Bedingung: *SenderDomainIs* <br/> Ausnahme: *ExceptIfSenderDomainIs*       |DomainName         |     Nachrichten, bei denen die Domäne der E-Mail-Adresse des Absenders dem angegebenen Wert entspricht. Wenn Sie Absenderdomänen suchen müssen, die die angegebene Domäne *enthalten* (beispielsweise eine beliebige Unterdomäne einer Domäne), verwenden Sie die *FromAddressMatchesPatterns* -Bedingung ( **sender address Matches** ), und geben Sie die Domäne mithilfe der folgenden Syntax an: " \. Domain \. com $".    |

## <a name="recipients"></a>Empfänger

|**Bedingung oder Ausnahme in DLP**| **Bedingung/Ausnahmeparameter in Microsoft 365 PowerShell** |    **Typ der Eigenschaft** | **description**|
|---------|---------|---------|---------|
|Empfänger lautet|  Bedingung: *SentTo* <br/> Ausnahme: *Parameter ExceptIfSentTo* | Addresses | Nachrichten, bei denen es sich bei einem der Empfänger um das angegebene Postfach, den E-Mail-Benutzer oder den E-Mail-Kontakt in der Organisation handelt. Die Empfänger können in den Feldern **To** , **Cc** oder **Bcc** der Nachricht angegeben werden.  |
|Empfängerdomäne lautet|   Bedingung: *RecipientDomainIs* <br/> Ausnahme: *ExceptIfRecipientDomainIs* |   DomainName |    Nachrichten, bei denen die Domäne der E-Mail-Adresse des Absenders dem angegebenen Wert entspricht.|
|Empfängeradresse enthält Wörter|  Bedingung: *RecipientAddressContainsWords* <br/> Ausnahme: *ExceptIfRecipientAddressContainsWords*|    Words|  Nachrichten, die die angegebenen Wörter in der E-Mail-Adresse des Empfängers enthalten. <br/>**Hinweis** : Diese Bedingung berücksichtigt keine Nachrichten, die an Proxyadressen des Empfängers gesendet werden. Es werden nur Nachrichten berücksichtigt, die an die primäre E-Mail-Adresse des Empfängers gesendet werden.|
|Empfängeradresse stimmt mit Mustern überein| Bedingung: *RecipientAddressMatchesPatterns* <br/> Ausnahme: *ExceptIfRecipientAddressMatchesPatterns*|   Muster    |Nachrichten, bei denen die E-Mail-Adresse des Empfängers Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen. <br/> **Hinweis** : Diese Bedingung berücksichtigt keine Nachrichten, die an Proxyadressen des Empfängers gesendet werden. Es werden nur Nachrichten berücksichtigt, die an die primäre E-Mail-Adresse des Empfängers gesendet werden.|
|Gesendet an Mitglied von| Bedingung: *SentToMemberOf* <br/> Ausnahme: *ExceptIfSentToMemberOf*|  Addresses|  Nachrichten, die Empfänger enthalten, die Mitglieder der angegebenen Verteilergruppe, der e-Mail-aktivierten Sicherheitsgruppe oder der Microsoft 365-Gruppe sind. Die Gruppe kann in den Feldern **To** , **Cc** oder **Bcc** der Nachricht sein.|

## <a name="message-subject-or-body"></a>Nachrichtenbetreff oder -text

|**Bedingung oder Ausnahme in DLP** | **Bedingung/Ausnahmeparameter in Microsoft 365 PowerShell** |**Typ der Eigenschaft**| **description**|
|---------|---------|---------|---------|
|Betreff enthält Wörter oder Ausdrücke| Bedingung: *SubjectContainsWords* <br/> Ausnahme: *ExceptIf SubjectContainsWords*| Words   |Nachrichten, deren Feld Subject die angegebenen Wörter enthält.|
|Muster für Betreff-Übereinstimmungen|Bedingung: *SubjectMatchesPatterns* <br/> Ausnahme: *ExceptIf SubjectMatchesPatterns*|Muster   |Nachrichten, bei denen das Feld Subject Textmuster enthält, die mit den angegebenen regulären Ausdrücken übereinstimmen.|
|Inhalt enthält|  Bedingung: *ContentContainsSensitiveInformation* <br/> Ausnahme *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Nachrichten oder Dokumente, die vertrauliche Informationen enthalten, wie durch Datenverlust Verhinderung (DLP)-Richtlinien definiert.|


## <a name="attachments"></a>Anlagen

|**Bedingung oder Ausnahme in DLP**| **Bedingung/Ausnahmeparameter in Microsoft 365 PowerShell**| **Typ der Eigenschaft**   |**description**|
|---------|---------|---------|---------|
|Anlage ist passwortgeschützt|Bedingung: *DocumentIsPasswordProtected* <br/> Ausnahme: *ExceptIfDocumentIsPasswordProtected*|Keine| Nachrichten, bei denen eine Anlage kennwortgeschützt ist (und daher nicht überprüft werden kann). Die Kennworterkennung funktioniert nur bei Office-Dokumenten und ZIP-Dateien.|
|Dateierweiterung der Anlage ist|Bedingung: *ContentExtensionMatchesWords* <br/> Ausnahme: *ExceptIfContentExtensionMatchesWords*|  Words   |Nachrichten, bei denen die Dateierweiterung einer Anlage einem der angegebenen Wörter entspricht.|
|Der Inhalt einer e-Mail-Anlage konnte nicht überprüft werden|Bedingung: *DocumentIsUnsupported* <br/>Ausnahme: *ExceptIf DocumentIsUnsupported*|   N/V|    Nachrichten, für die eine Anlage von Exchange Online nicht systemintern erkannt wird.|
|Der Inhalt einer e-Mail-Anlage hat die Überprüfung nicht abgeschlossen|   Bedingung: *ProcessingLimitExceeded* <br/> Ausnahme: *ExceptIfProcessingLimitExceeded*|    N/V |Nachrichten, bei denen das Regelmodul das Prüfen der Anlagen nicht abschließen konnte. Sie können diese Bedingung zum Erstellen von Regeln verwenden, die zusammenarbeiten, um Nachrichten zu ermitteln und zu verarbeiten, deren Inhalt nicht vollständig überprüft werden konnte.|
|Dokumentname enthält Wörter|Bedingung: *DocumentNameMatchesWords* <br/> Ausnahme: *ExceptIfDocumentNameMatchesWords* |Words  |Nachrichten, bei denen die Dateinamen einer Anlage mit einem der angegebenen Wörter übereinstimmen.|
|Dokumentname stimmt mit Mustern überein|Bedingung: *DocumentNameMatchesPatterns* <br/> Ausnahme: *ExceptIfDocumentNameMatchesPatterns*|    Muster    |Nachrichten, bei denen der Dateiname einer Anlage Textmuster enthält, die mit dem angegebenen regulären Ausdruck übereinstimmen.|
|Dokumenteigenschaft lautet|Bedingung: *ContentPropertyContainsWords* <br/> Ausnahme: *ExceptIfContentPropertyContainsWords* |Words| Nachrichten oder Dokumente, bei denen die Dateierweiterung einer Anlage mit einem der angegebenen Wörter übereinstimmt.|
|Die Dokumentgröße ist gleich oder größer als| Bedingung: *DocumentSizeOver* <br/> Ausnahme: *ExceptIfDocumentSizeOver*|    Größe    |Nachrichten, bei denen eine Anlage größer oder gleich dem angegebenen Wert ist.|

## <a name="message-headers"></a>Nachrichtenkopfzeilen

|**Bedingung oder Ausnahme in DLP**| **Bedingung/Ausnahmeparameter in Microsoft 365 PowerShell**| **Typ der Eigenschaft**|  **description**|
|---------|---------|---------|---------|
|Kopfzeile enthält Wörter oder Ausdrücke|Bedingung: *HeaderContainsWords* <br/> Ausnahme: *ExceptIfHeaderContainsWords*|  Hash Tabelle  |Nachrichten, die das angegebene Header-Feld enthalten, und der Wert des Header-Felds enthält die angegebenen Wörter.|
|Header entspricht Mustern|   Bedingung: *HeaderMatchesPatterns* <br/> Ausnahme: *ExceptIfHeaderMatchesPatterns*|    Hash Tabelle  |Nachrichten, die das angegebene Header-Feld enthalten, und der Wert des Header-Felds enthält die angegebenen regulären Ausdrücke.|

## <a name="message-properties"></a>Nachrichteneigenschaften

|**Bedingung oder Ausnahme in DLP**| **Bedingung/Ausnahmeparameter in Microsoft 365 PowerShell**| **Typ der Eigenschaft**   |**description**|
|---------|---------|---------|---------|
|Nachrichtengröße über|Bedingung: *MessageSizeOver* <br/> Ausnahme: *ExceptIfMessageSizeOver*| Größe    |Nachrichten, deren Gesamtgröße (Nachricht sowie Anlagen) größer oder gleich dem angegebenen Wert ist. <br/>**Hinweis** : Grenzwerte für die Nachrichtengröße für Postfächer werden vor E-Mail-Flussregeln ausgewertet. Eine Nachricht, die für ein Postfach zu groß ist, wird zurückgewiesen, bevor eine Regel mit dieser Bedingung auf diese Nachricht angewendet wird.  |

