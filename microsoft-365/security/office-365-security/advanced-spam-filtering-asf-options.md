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
description: Administratoren können sich über die Erweiterten Spamfiltereinstellungen (Advanced Spam Filter, ASF) informieren, die in Antispamrichtlinien in Exchange Online Protection (EOP) verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ade36086d1503b89b506730b98ac7965845e86b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206724"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Erweiterte Spamfiltereinstellungen (Advanced Spam Filter, ASF) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> AsF-Einstellungen, die derzeit in Antispamrichtlinien verfügbar sind, sind derzeit veraltet. Es wird empfohlen, diese Einstellungen nicht in Antispamrichtlinien zu verwenden. Die Funktionalität dieser ASF-Einstellungen wird in andere Teile des Filterstapels integriert. Weitere Informationen finden Sie unter [EOP Antispamrichtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

In allen Microsoft 365-Organisationen können Administratoren mit den Einstellungen für den erweiterten Spamfilter (Advanced Spam Filter, ASF) in Antispamrichtlinien in EOP Nachrichten basierend auf bestimmten Nachrichteneigenschaften als Spam markieren. ASF zielt speziell auf diese Eigenschaften ab, da sie häufig in Spam gefunden werden. Je nach Eigenschaft markieren ASF-Erkennungen die Nachricht entweder als **Spam oder** Als Spam mit **hoher Vertrauen.**

> [!NOTE]
> Das Aktivieren einer oder mehrerer der ASF-Einstellungen ist ein aggressiver Ansatz für die Spamfilterung. Nachrichten, die von ASF gefiltert werden, können nicht als falsch positive Ergebnisse angezeigt werden. Sie können Nachrichten identifizieren, die von ASF gefiltert wurden:
>
> - Regelmäßige Spamquarantänebenachrichtigungen für Endbenutzer.
>
> - Das Vorhandensein gefilterter Nachrichten in Quarantäne.
>
> - Die spezifischen `X-CustomSpam:` X-Header-Felder, die Nachrichten wie in diesem Artikel beschrieben hinzugefügt werden.

In den folgenden Abschnitten werden die ASF-Einstellungen und -Optionen beschrieben, die in Antispamrichtlinien im Security & Compliance Center und in Exchange Online PowerShell oder eigenständigem EOP PowerShell ([New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) und [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)) verfügbar sind. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivieren, Deaktivieren oder Testen von ASF-Einstellungen

Für jede ASF-Einstellung stehen die folgenden Optionen in Antispamrichtlinien zur Verfügung:

- **On**: ASF fügt der Nachricht das entsprechende X-Kopfzeilenfeld hinzu und markiert die Nachricht entweder als **Spam** (SCL 5 oder 6 für Spampunktzahl [erhöhen)](#increase-spam-score-settings)oder Als Spam mit hoher Sicherheit **(SCL** 9 für [Spameinstellungen](#mark-as-spam-settings)markieren).

- **Off**: Die ASF-Einstellung ist deaktiviert. Dies ist der Standardwert, und es wird empfohlen, ihn nicht zu ändern.

- **Test:** ASF fügt der Nachricht das entsprechende X-Headerfeld hinzu. Was mit der Nachricht geschieht, wird durch den **Testmodusoptionen** (*TestModeAction*) -Wert bestimmt:

  - **None:** Die Nachrichtenzustellung ist von der ASF-Erkennung nicht betroffen. Die Nachricht unterliegt weiterhin anderen Filter- und Regeltypen in EOP.

  - **Add default X-header text (*AddXHeader*)**: Der X-Header-Wert `X-CustomSpam: This message was filtered by the custom spam filter option` wird der Nachricht hinzugefügt. Sie können diesen Wert in Posteingangsregeln oder Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um die Zustellung der Nachricht zu beeinflussen.

  - **Send Bcc message (*BccMessage*)**: Die angegebenen E-Mail-Adressen (der *Parameterwert TestModeBccToRecipients* in PowerShell) werden dem Feld Bcc der Nachricht hinzugefügt, und die Nachricht wird an die zusätzlichen Bcc-Empfänger zugestellt. Im Security & Compliance Center trennen Sie mehrere E-Mail-Adressen durch Semikolons (;). In PowerShell trennen Sie mehrere E-Mail-Adressen durch Kommas.

  **Hinweise**:

  - Der Testmodus ist für die folgenden ASF-Einstellungen nicht verfügbar:

    - **Bedingte Absender-ID-Filterung: Harter Fehler** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-Eintrag: harter Fehler** (*MarkAsSpamSpfRecordHardFail*)

  - Die gleiche Testmodusaktion wird auf *alle* ASF-Einstellungen angewendet, die auf Test **festgelegt sind.** Sie können keine verschiedenen Testmodusaktionen für verschiedene ASF-Einstellungen konfigurieren.

## <a name="increase-spam-score-settings"></a>Erhöhen der Spam-Bewertungseinstellungen

Die folgenden ASF-Einstellungen legen die Spamsicherheitsstufe (Spam Confidence Level, SCL)  der erkannten Nachrichten auf 5 oder 6, was dem Spamfilter-Urteil und der entsprechenden Aktion in Antispamrichtlinien entspricht.

****

|Antispamrichtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Bildlinks zu Remotestandorten** <p> *IncreaseScoreWithImageLinks*|Nachrichten, die `<Img>` HTML-Tag-Links zu Remotewebsites enthalten (z. B. mithilfe von http), werden als Spam gekennzeichnet.|`X-CustomSpam: Image links to remote sites`|
|**URL-Umleitung zu anderem Port** <p> *IncreaseScoreWithRedirectToOtherPort*|Nachrichten, die Hyperlinks enthalten, die zu anderen TCP-Ports als 80 (HTTP), 8080 (alternativem HTTP) oder 443 (HTTPS) umleiten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL redirect to other port`|
|**Numerische IP-Adresse in URL** <p> *IncreaseScoreWithNumericIps*|Nachrichten mit numerischen URLs (in der Regel IP-Adressen) werden als Spam gekennzeichnet.|`X-CustomSpam: Numeric IP in URL`|
|**URL zu BIZ- oder INFO-Websites:** <p> *IncreaseScoreWithBizOrInfoUrls*|Nachrichten, die im Nachrichtentext enthalten oder Links `.biz` `.info` enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Als Spameinstellungen markieren

Mit den folgenden ASF-Einstellungen wird die SCL der  erkannten Nachrichten auf 9 festgelegt, was dem Spamfilter-Filter-Urteil mit hoher Sicherheit und der entsprechenden Aktion in Antispamrichtlinien entspricht.

****

|Antispamrichtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Leere Nachrichten** <p> *MarkAsSpamEmptyMessages*|Nachrichten ohne Betreff, keine Inhalte im Nachrichtentext und keine Anlagen werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet.|`X-CustomSpam: Empty Message`|
|**JavaScript oder VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|Nachrichten, die JavaScript oder Visual Basic Script Edition in HTML verwenden, werden als Spam mit hoher Sicherheit gekennzeichnet. <p> Diese Skriptsprachen werden in E-Mail-Nachrichten verwendet, um bestimmte Aktionen automatisch auszuführen.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Frame- oder IFrame-Tags in HTML** <p> *MarkAsSpamFramesInHtml*|Nachrichten, die `<frame>` `<iframe>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet. <p> Diese Tags werden in E-Mail-Nachrichten verwendet, um die Seite zum Anzeigen von Text oder Grafiken zu formatieren.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Object-Tags in HTML** <p> *MarkAsSpamObjectTagsInHtml*|Nachrichten, die `<object>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet. <p> Mit diesem Tag können Plug-Ins oder Anwendungen in einem HTML-Fenster ausgeführt werden.|`X-CustomSpam: Object tag in html`|
|**Embed-Tags in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Nachrichten, die `<embed>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet. <p> Dieses Tag ermöglicht das Einbetten verschiedener Arten von Dokumenten in ein HTML-Dokument (z. B. Sounds, Videos oder Bilder).|`X-CustomSpam: Embed tag in html`|
|**Form-Tags in HTML** <p> *MarkAsSpamFormTagsInHtml*|Nachrichten, die `<form>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet. <p> Dieses Tag wird zum Erstellen von Websiteformularen verwendet. Werbe-E-Mails enthalten häufig dieses Tag, um Informationen vom Empfänger zu erbitten.|`X-CustomSpam: Form tag in html`|
|**Web-Bugs in HTML** <p> *MarkAsSpamWebBugsInHtml*|Ein *Webfehler* (auch als Webbeacons *bezeichnet)* ist ein Grafikelement (oft so klein wie ein Pixel um ein Pixel), das in E-Mail-Nachrichten verwendet wird, um zu bestimmen, ob die Nachricht vom Empfänger gelesen wurde. <p> Nachrichten, die Webfehler enthalten, werden als Spam mit hoher Sicherheit gekennzeichnet. <p> Legitime Newsletter verwenden möglicherweise Webfehler, obwohl viele dies als Angriff auf den Datenschutz betrachten. |`X-CustomSpam: Web bug`|
|**Liste mit sensiblen Begriffen anwenden** <p> *MarkAsSpamSensitiveWordList*|Microsoft verwaltet eine dynamische, aber nicht bearbeitbare Liste von Wörtern, die potenziell anstößigen Nachrichten zugeordnet sind. <p> Nachrichten, die Wörter aus der Liste vertraulicher Wörter im Betreff oder Nachrichtentext enthalten, werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-Eintrag: Schwerer Fehler** <p> *MarkAsSpamSpfRecordHardFail*|Nachrichten, die von einer IP-Adresse gesendet werden, die nicht im SPF Sender Policy Framework (SPF)-Eintrag in DNS für die Quell-E-Mail-Domäne angegeben ist, werden als Spam mit hoher Sicherheit gekennzeichnet. <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF Record Fail`|
|**Bedingte Absender-ID-Filterung: Schwerer Fehler** <p> *MarkAsSpamFromAddressAuthFail*|Nachrichten, bei der eine bedingte Absender-ID-Prüfung nicht möglich ist, werden als Spam gekennzeichnet. <p> Diese Einstellung kombiniert eine SPF-Prüfung mit einer Absender-ID-Prüfung, um sich vor Nachrichtenkopfzeilen zu schützen, die gefälschte Absender enthalten. <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF From Record Fail`|
|**NDR-Rückläufer** <p> *MarkAsSpamNdrBackscatter*|*Backscatter* ist nutzlose Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte oder Unzustellbarkeitsnachrichten bezeichnet), die von gefälschten Absendern in E-Mail-Nachrichten verursacht werden. Weitere Informationen finden Sie unter [Backscatter messages und EOP](backscatter-messages-and-eop.md). <p> Sie müssen diese Einstellung nicht in den folgenden Umgebungen konfigurieren, da legitime Unntsprechungsnachrichten übermittelt werden und der Rückscatter als Spam gekennzeichnet ist: <ul><li>Microsoft 365-Organisationen mit Exchange Online-Postfächern.</li><li>Lokale E-Mail-Organisationen, in denen Sie ausgehende *E-Mails* über EOP routen.</li></ul> <p> In eigenständigen EOP-Umgebungen, die eingehende E-Mails an lokale Postfächer schützen, hat das Aktivieren oder Deaktivieren dieser Einstellung folgendes Ergebnis: <ul><li> **On**: Legitime Unntsprechungsnachrichten werden zugestellt, und der Rückscatter wird als Spam gekennzeichnet.</li><li>**Off**: Legitime Unerklingsnachrichten und Rückläufer durchgehen die normale Spamfilterung. Die meisten legitimen Unerreichungsnachrichten werden an den ursprünglichen Nachrichtensender übermittelt. Einige, aber nicht alle Rückscatter werden als Spam mit hoher Vertrauenssicherheit gekennzeichnet. Der Rückscatter kann definitionsgemäß nur an den spoofierten Absender und nicht an den ursprünglichen Absender zugestellt werden.</li></ul> <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: Backscatter NDR`|
|