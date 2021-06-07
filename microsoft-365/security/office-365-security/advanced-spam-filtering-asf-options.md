---
title: ASF-Einstellungen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die Einstellungen für den erweiterten Spamfilter (ADVANCED Spam Filter, ASF) informieren, die in Antispamrichtlinien in Exchange Online Protection (EOP) verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 12f193ef61205e8568341c774b957ce4a9dd7988
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779422"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Erweiterte Einstellungen für den Spamfilter (ASF) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> ASF-Einstellungen, die derzeit in Antispamrichtlinien verfügbar sind, sind veraltet. Es wird empfohlen, diese Einstellungen nicht in Antispamrichtlinien zu verwenden. Die Funktionalität dieser ASF-Einstellungen wird in andere Teile des Filterstapels integriert. Weitere Informationen finden Sie unter [EOP Antispamrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

In allen Microsoft 365 Organisationen ermöglichen die AsF-Einstellungen (Advanced Spam Filter) in Antispamrichtlinien in EOP Administratoren, Nachrichten basierend auf bestimmten Nachrichteneigenschaften als Spam zu markieren. ASF zielt speziell auf diese Eigenschaften ab, da sie häufig in Spam zu finden sind. Je nach Eigenschaft markieren ASF-Erkennungen die Nachricht entweder als **Spam** oder **Spam mit hoher Spamwahrscheinlichkeit.**

> [!NOTE]
> Das Aktivieren einer oder mehrerer ASF-Einstellungen ist ein aggressiver Ansatz für die Spamfilterung. Nachrichten, die von ASF gefiltert werden, können nicht als falsch positive Ergebnisse gemeldet werden. Sie können Nachrichten identifizieren, die nach ASF gefiltert wurden:
>
> - Regelmäßige Spamquarantänebenachrichtigungen für Endbenutzer.
> - Das Vorhandensein gefilterter Nachrichten in Quarantäne.
> - Die spezifischen `X-CustomSpam:` X-Header-Felder, die Nachrichten hinzugefügt werden, wie in diesem Artikel beschrieben.

In den folgenden Abschnitten werden die ASF-Einstellungen und -Optionen beschrieben, die in Antispamrichtlinien im Microsoft 365 Security Center und in Exchange Online PowerShell oder in eigenständiger EOP PowerShell ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) und [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)) verfügbar sind. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivieren, Deaktivieren oder Testen von ASF-Einstellungen

Für jede ASF-Einstellung sind die folgenden Optionen in Antispamrichtlinien verfügbar:

- **On**: ASF adds the corresponding X-header field to the message, and either marks the message as **Spam** (SCL 5 or 6 for [Increase spam score settings](#increase-spam-score-settings)) or High confidence **spam** (SCL 9 for Mark as [spam settings](#mark-as-spam-settings)).
- **Deaktiviert:** Die ASF-Einstellung ist deaktiviert. Dies ist der Standardwert, und es wird empfohlen, ihn nicht zu ändern.
- **Test:** ASF fügt der Nachricht das entsprechende X-Header-Feld hinzu. Was mit der Nachricht geschieht, wird durch den **Testmoduswert** (*TestModeAction*) bestimmt:
  - **Keine:** Die Nachrichtenübermittlung ist von der ASF-Erkennung nicht betroffen. Die Nachricht unterliegt weiterhin anderen Arten von Filtern und Regeln in EOP.
  - **Fügen Sie standardmäßigen X-Header-Text (*AddXHeader*)** hinzu: Der X-Header-Wert `X-CustomSpam: This message was filtered by the custom spam filter option` wird der Nachricht hinzugefügt. Sie können diesen Wert in Posteingangsregeln oder Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um die Zustellung der Nachricht zu beeinflussen.
  - **Senden einer Bcc-Nachricht (*BccMessage*):** Die angegebenen E-Mail-Adressen (der *Parameterwert "TestModeBccToRecipients"* in PowerShell) werden dem Bcc-Feld der Nachricht hinzugefügt, und die Nachricht wird an die zusätzlichen Bcc-Empfänger übermittelt. Im Sicherheitscenter trennen Sie mehrere E-Mail-Adressen durch Semikolons (;). In PowerShell trennen Sie mehrere E-Mail-Adressen durch Kommas.

  **Hinweise**:

  - Der Testmodus ist für die folgenden ASF-Einstellungen nicht verfügbar:
    - **Filterung der bedingten Absender-ID: "Hard Fail"** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-Eintrag: Hard Fail** (*MarkAsSpamSpfRecordHardFail*)
  - Die gleiche Testmodusaktion wird auf *alle* ASF-Einstellungen angewendet, die auf **Test** festgelegt sind. Sie können keine verschiedenen Testmodusaktionen für unterschiedliche ASF-Einstellungen konfigurieren.

## <a name="increase-spam-score-settings"></a>Erhöhen der Spambewertungseinstellungen

Die folgenden ASF-Einstellungen legen die Spam-Konfidenzstufe (Spam Confidence Level, SCL) von erkannten Nachrichten auf 5 oder 6 fest, was dem Spamfilterbewertungs- und der entsprechenden Aktion in Antispamrichtlinien entspricht. 

<br>

****

|Antispamrichtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Bildlinks zu Remotewebsites** <p> *IncreaseScoreWithImageLinks*|Nachrichten, die `<Img>` HTML-Taglinks zu Remotewebsites enthalten (z. B. mithilfe von HTTP), werden als Spam gekennzeichnet.|`X-CustomSpam: Image links to remote sites`|
|**Numerische IP-Adresse in URL** <p> *IncreaseScoreWithNumericIps*|Nachrichten, die numerische URLs (in der Regel IP-Adressen) enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: Numeric IP in URL`|
|**URL-Umleitung zu anderem Port** <p> *IncreaseScoreWithRedirectToOtherPort*|Nachrichten, die Hyperlinks enthalten, die zu anderen TCP-Ports als 80 (HTTP), 8080 (alternative HTTP) oder 443 (HTTPS) umleiten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL redirect to other port`|
|**Links zu BIZ- oder INFO-Websites** <p> *IncreaseScoreWithBizOrInfoUrls*|Nachrichten, `.biz` die den Nachrichtentext enthalten oder `.info` links enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Als Spameinstellungen kennzeichnen

Mit den folgenden ASF-Einstellungen wird die SCL von erkannten Nachrichten auf 9 festgelegt, was dem Spamfilter-Bewertungsdiktat mit **hoher Konfidenz** und der entsprechenden Aktion in Antispamrichtlinien entspricht.

<br>

****

|Antispamrichtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Leere Nachrichten** <p> *MarkAsSpamEmptyMessages*|Nachrichten ohne Betreff, keine Inhalte im Nachrichtentext und keine Anlagen werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet.|`X-CustomSpam: Empty Message`|
|**Eingebettete Tags in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Nachrichten, die `<embed>` HTML-Tags enthalten, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Dieses Tag ermöglicht das Einbetten verschiedener Arten von Dokumenten in ein HTML-Dokument (z. B. Sounds, Videos oder Bilder).|`X-CustomSpam: Embed tag in html`|
|**JavaScript oder VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|Nachrichten, die JavaScript oder Visual Basic Script Edition in HTML verwenden, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Diese Skriptsprachen werden in E-Mail-Nachrichten verwendet, um bestimmte Aktionen automatisch auszuführen.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Form-Tags in HTML** <p> *MarkAsSpamFormTagsInHtml*|Nachrichten, die `<form>` HTML-Tags enthalten, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Dieses Tag wird zum Erstellen von Websiteformularen verwendet. Werbe-E-Mails enthalten häufig dieses Tag, um Informationen vom Empfänger zu erbitten.|`X-CustomSpam: Form tag in html`|
|**Frame- oder iframe-Tags in HTML** <p> *MarkAsSpamFramesInHtml*|Nachrichten, die `<frame>` Html-Tags enthalten, `<iframe>` werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Diese Tags werden in E-Mail-Nachrichten verwendet, um die Seite zum Anzeigen von Text oder Grafiken zu formatieren.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Web-Bugs in HTML** <p> *MarkAsSpamWebBugsInHtml*|Ein *Webfehler* (auch bekannt als *Webbeacons)* ist ein Grafikelement (häufig kleiner als ein Pixel pro Pixel), das in E-Mail-Nachrichten verwendet wird, um zu bestimmen, ob die Nachricht vom Empfänger gelesen wurde. <p> Nachrichten, die Webfehler enthalten, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Seriöse Newsletter können Webfehler verwenden, obwohl viele dies als einen Heiterkeitsschutz betrachten. |`X-CustomSpam: Web bug`|
|**Object-Tags in HTML** <p> *MarkAsSpamObjectTagsInHtml*|Nachrichten, die `<object>` HTML-Tags enthalten, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Mit diesem Tag können Plug-Ins oder Anwendungen in einem HTML-Fenster ausgeführt werden.|`X-CustomSpam: Object tag in html`|
|**Vertrauliche Wörter** <p> *MarkAsSpamSensitiveWordList*|Microsoft verwaltet eine dynamische, aber nicht bearbeitbare Liste von Wörtern, die potenziell anstößigen Nachrichten zugeordnet sind. <p> Nachrichten, die Wörter aus der Liste vertraulicher Wörter im Betreff oder Nachrichtentext enthalten, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-Eintrag: Schwerer Fehler** <p> *MarkAsSpamSpfRecordHardFail*|Nachrichten, die von einer IP-Adresse gesendet werden, die nicht im SPF Sender Policy Framework (SPF)-Eintrag im DNS für die Quell-E-Mail-Domäne angegeben ist, werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF Record Fail`|
|**Fehler beim Filtern der Absender-ID** <p> *MarkAsSpamFromAddressAuthFail*|Nachrichten, bei denen eine bedingte Absender-ID-Prüfung nicht erfolgreich ist, werden als Spam gekennzeichnet. <p> Diese Einstellung kombiniert eine SPF-Prüfung mit einer Absender-ID-Überprüfung, um den Schutz vor Nachrichtenkopfzeilen zu unterstützen, die gefälschte Absender enthalten. <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF From Record Fail`|
|**Backscatter** <p> *MarkAsSpamNdrBackscatter*|*Rückläufer* sind nutzlose Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet), die von gefälschten Absendern in E-Mail-Nachrichten verursacht werden. Weitere Informationen finden Sie unter [Backscatter-Nachrichten und EOP.](backscatter-messages-and-eop.md) <p> Sie müssen diese Einstellung in den folgenden Umgebungen nicht konfigurieren, da seriöse Unzustellbarkeitsberichte übermittelt werden und Rückläufer als Spam gekennzeichnet sind: <ul><li>Microsoft 365 Organisationen mit Exchange Online Postfächern.</li><li>Lokale E-Mail-Organisationen, in denen Sie *ausgehende* E-Mails über EOP weiterleiten.</li></ul> <p> In eigenständigen EOP-Umgebungen, die eingehende E-Mails an lokale Postfächer schützen, hat das Aktivieren oder Deaktivieren dieser Einstellung das folgende Ergebnis: <ul><li> **On**: Seriöse NDRs werden übermittelt, und Rückscatter wird als Spam gekennzeichnet.</li><li>**Aus:** Seriöse Unzustellbarkeitsberichte und Rückläufer durchlaufen die normale Spamfilterung. Die meisten seriösen Unzustellbarkeitsberichte werden an den ursprünglichen Absender der Nachricht übermittelt. Einige, aber nicht alle Rückläufer werden als Spam mit hoher Spamwahrscheinlichkeit gekennzeichnet. Per Definition kann Rückscatter nur an den gefälschten Absender übermittelt werden, nicht an den ursprünglichen Absender.</li></ul> <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: Backscatter NDR`|
|
