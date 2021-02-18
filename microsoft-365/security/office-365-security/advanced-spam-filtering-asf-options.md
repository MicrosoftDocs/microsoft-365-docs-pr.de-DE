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
description: Administratoren können sich über die Einstellungen für den erweiterten Spamfilter (Advanced Spam Filter, ASF) informieren, die in den Antispamrichtlinien in Exchange Online Protection (EOP) verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b6db02815f5b50d199e10685e2895a174997fd2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288681"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Erweiterte Spamfiltereinstellungen (Advanced Spam Filter, ASF) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> AsF-Einstellungen, die derzeit in Antispamrichtlinien verfügbar sind, sind derzeit veraltet. Es wird empfohlen, diese Einstellungen nicht in Antispamrichtlinien zu verwenden. Die Funktionalität dieser ASF-Einstellungen wird in andere Teile des Filterstapels integriert. Weitere Informationen finden Sie unter [EOP Antispamrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

In allen Microsoft 365-Organisationen können Administratoren mit den Einstellungen für den erweiterten Spamfilter (Advanced Spam Filter, ASF) in Antispamrichtlinien in EOP Nachrichten basierend auf bestimmten Nachrichteneigenschaften als Spam markieren. ASF zielt speziell auf diese Eigenschaften ab, da sie häufig in Spam gefunden werden. Je nach Eigenschaft markieren die ASF-Erkennungen die Nachricht entweder als **Spam** oder als Spam **mit hoher Confidence.**

> [!NOTE]
> Das Aktivieren einer oder mehrerer der ASF-Einstellungen ist ein aggressiver Ansatz für die Spamfilterung. Sie können Nachrichten, die von ASF gefiltert werden, nicht als falsch positive Ergebnisse melden. Sie können Nachrichten identifizieren, die von ASF gefiltert wurden, indem Sie:
>
> - Regelmäßige Spamquarantänebenachrichtigungen für Endbenutzer.
>
> - Das Vorhandensein gefilterter Nachrichten in Quarantäne.
>
> - Die spezifischen `X-CustomSpam:` X-Kopfzeilenfelder, die Nachrichten hinzugefügt werden, wie in diesem Artikel beschrieben.

In den folgenden Abschnitten werden die ASF-Einstellungen und -Optionen beschrieben, die in Antispamrichtlinien im Security & Compliance Center und in Exchange Online PowerShell oder in eigenständiger EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) und [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)) verfügbar sind. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivieren, Deaktivieren oder Testen von ASF-Einstellungen

Für jede ASF-Einstellung sind die folgenden Optionen in Antispamrichtlinien verfügbar:

- **On:** ASF fügt der Nachricht das entsprechende X-Kopfzeilenfeld hinzu und markiert die Nachricht entweder als **Spam** (SCL 5 oder 6 für erhöhen der Spamwerteinstellungen) [](#increase-spam-score-settings)oder als Spam mit hoher Treffsicherheit **(SCL** 9 für [Spameinstellungen).](#mark-as-spam-settings)

- **Aus:** Die Einstellung "ASF" ist deaktiviert. Dies ist der Standardwert, und es wird empfohlen, ihn nicht zu ändern.

- **Test:** ASF fügt der Nachricht das entsprechende X-Kopfzeilenfeld hinzu. Was mit der Nachricht geschieht, wird durch den **Testmodusoptionen** (*TestModeAction )-Wert* bestimmt:

  - **Keine:** Die Nachrichtenzustellung ist von der ASF-Erkennung nicht betroffen. Die Nachricht unterliegt weiterhin anderen Arten von Filterung und Regeln in EOP.

  - **Add default X-header text (*AddXHeader*)**: The X-header value `X-CustomSpam: This message was filtered by the custom spam filter option` is added to the message. Sie können diesen Wert in Posteingangsregeln oder Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um die Zustellung der Nachricht zu beeinflussen.

  - **Send Bcc message (*BccMessage*)**: The specified email addresses (the *TestModeBccToRecipients* parameter value in PowerShell) are added to the Bcc field of the message, and the message is delivered to the additional Bcc recipients. Im Security & Compliance Center trennen Sie mehrere E-Mail-Adressen durch Semikolons (;). In PowerShell trennen Sie mehrere E-Mail-Adressen durch Kommas.

  **Hinweise**:

  - Der Testmodus ist für die folgenden ASF-Einstellungen nicht verfügbar:

    - **Bedingte Sender ID-Filterung: Hard fail** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR-Rückscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-Eintrag: Hard fail** (*MarkAsSpamSpfRecordHardFail*)

  - Die gleiche Testmodusaktion wird auf *alle* ASF-Einstellungen angewendet, die auf **"Test" festgelegt sind.** Sie können keine verschiedenen Testmodusaktionen für unterschiedliche ASF-Einstellungen konfigurieren.

## <a name="increase-spam-score-settings"></a>Erhöhen der Einstellungen für die Spampunktzahl

Mit den folgenden Einstellungen für den Spamfilter wird der SCL (Spam Confidence Level) erkannter Nachrichten auf 5 oder 6 festgelegt. Dies entspricht der Spamfilter-Filter-Bewkung und der entsprechenden Aktion in Antispamrichtlinien. 

****

|Antispamrichtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Bildlinks zu Remotestandorten** <p> *IncreaseScoreWithImageLinks*|Nachrichten, die `<Img>` HTML-Tag-Links zu Remotewebsites (z. B. http) enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: Image links to remote sites`|
|**URL-Umleitung zu anderem Port** <p> *IncreaseScoreWithRedirectToOtherPort*|Nachrichten, die Links enthalten, die an andere TCP-Ports als 80 (HTTP), 8080 (alternatives HTTP) oder 443 (HTTPS) umleiten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL redirect to other port`|
|**Numerische IP-Adresse in URL** <p> *IncreaseScoreWithNumericIps*|Nachrichten, die numerische URLs (in der Regel IP-Adressen) enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: Numeric IP in URL`|
|**URL zu BIZ- oder INFO-Websites:** <p> *IncreaseScoreWithBizOrInfoUrls*|Nachrichten, die Im Nachrichtentext enthalten oder Links `.biz` `.info` enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Als Spameinstellungen markieren

Mit den folgenden Einstellungen für den Spamfilter wird der SCL der erkannten Nachrichten auf 9 festgelegt. Dies entspricht der Spamfilterauswertung mit hoher Confidence und der entsprechenden Aktion in Antispamrichtlinien. 

****

|Antispamrichtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Leere Nachrichten** <p> *MarkAsSpamEmptyMessages*|Nachrichten ohne Betreff, ohne Inhalt im Nachrichtentext und keine Anlagen werden als Spam mit hoher Confidence gekennzeichnet.|`X-CustomSpam: Empty Message`|
|**JavaScript oder VBScript in HTML** <p> *MarkAsSpamJavaScriptInHtml*|Nachrichten, die JavaScript oder Visual Basic Script Edition in HTML verwenden, werden als Spam mit hoher Spamsicherheit gekennzeichnet. <p> Diese Skriptsprachen werden in E-Mail-Nachrichten verwendet, um bestimmte Aktionen automatisch auszuführen.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Frame- oder IFrame-Tags in HTML** <p> *MarkAsSpamFramesInHtml*|Nachrichten, die `<frame>` oder `<iframe>` HTML-Tags enthalten, werden als Spam mit hoher Spamsicherheit gekennzeichnet. <p> Diese Tags werden in E-Mail-Nachrichten verwendet, um die Seite zum Anzeigen von Text oder Grafiken zu formatieren.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Object-Tags in HTML** <p> *MarkAsSpamObjectTagsInHtml*|Nachrichten, die `<object>` HTML-Tags enthalten, werden als Spam mit hoher Spamsicherheit gekennzeichnet. <p> Dieses Tag ermöglicht die Ausführung von Plug-Ins oder Anwendungen in einem HTML-Fenster.|`X-CustomSpam: Object tag in html`|
|**Embed-Tags in HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Nachrichten mit `<embed>` HTML-Tags werden als Spam mit hoher Spamsicherheit gekennzeichnet. <p> Dieses Tag ermöglicht das Einbetten verschiedener Arten von Dokumenten in ein HTML-Dokument (z. B. Sounds, Videos oder Bilder).|`X-CustomSpam: Embed tag in html`|
|**Form-Tags in HTML** <p> *MarkAsSpamFormTagsInHtml*|Nachrichten, die `<form>` HTML-Tags enthalten, werden als Spam mit hoher Spamsicherheit gekennzeichnet. <p> Dieses Tag wird zum Erstellen von Websiteformularen verwendet. Werbe-E-Mails enthalten häufig dieses Tag, um Informationen vom Empfänger zu erbitten.|`X-CustomSpam: Form tag in html`|
|**Web-Bugs in HTML** <p> *MarkAsSpamWebBugsInHtml*|Ein *Webfehler* (auch bekannt als Webbeacons) ist ein Grafikelement (oft so klein wie ein Pixel um ein Pixel), das in E-Mail-Nachrichten verwendet wird, um zu bestimmen, ob die Nachricht vom Empfänger gelesen wurde. <p> Nachrichten, die Webfehler enthalten, werden als Spam mit hoher Spamsicherheit gekennzeichnet. <p> Legitime Newsletter verwenden möglicherweise Webfehler, obwohl viele dies als Datenschutz betrachten. |`X-CustomSpam: Web bug`|
|**Liste mit sensiblen Begriffen anwenden** <p> *MarkAsSpamSensitiveWordList*|Microsoft verwaltet eine dynamische, aber nicht bearbeitbare Liste von Wörtern, die potenziell anstößigen Nachrichten zugeordnet sind. <p> Nachrichten, die Wörter aus der Liste vertraulicher Wörter im Betreff oder Nachrichtentext enthalten, werden als Spam mit hoher Confidence gekennzeichnet.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-Eintrag: Schwerer Fehler** <p> *MarkAsSpamSpfRecordHardFail*|Nachrichten, die von einer IP-Adresse gesendet werden, die nicht im SPF Sender Policy Framework (SPF)-Eintrag im DNS für die Quell-E-Mail-Domäne angegeben ist, werden als Spam mit hoher Confidence gekennzeichnet. <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF Record Fail`|
|**Bedingte Absender-ID-Filterung: Schwerer Fehler** <p> *MarkAsSpamFromAddressAuthFail*|Nachrichten, bei der eine bedingte Absender-ID-Überprüfung nicht möglich ist, werden als Spam gekennzeichnet. <p> Diese Einstellung kombiniert eine SPF-Überprüfung mit einer Sender ID-Überprüfung, um den Schutz vor Nachrichtenkopfzeilen zu unterstützen, die gefälschte Absender enthalten. <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF From Record Fail`|
|**NDR-Rückläufer** <p> *MarkAsSpamNdrBackscatter*|*Rückläufer sind* nutzlose Unzustellbarkeitsberichte (auch NDRs oder Unzustellbarkeitsnachrichten bezeichnet), die von gefälschten Absendern in E-Mail-Nachrichten verursacht werden. Weitere Informationen finden Sie unter [Rückscatternachrichten und EOP](backscatter-messages-and-eop.md). <p> Sie müssen diese Einstellung nicht in den folgenden Umgebungen konfigurieren, da legitime NDRs zugestellt werden und der Rückläufer als Spam gekennzeichnet ist: <ul><li>Microsoft 365-Organisationen mit Exchange Online-Postfächern.</li><li>Lokale E-Mail-Organisationen, in denen Sie *ausgehende* E-Mails über EOP routen.</li></ul> <p> In eigenständigen EOP-Umgebungen, die eingehende E-Mails an lokale Postfächer schützen, hat das Aktivieren oder Deaktivieren dieser Einstellung folgendes Ergebnis: <ul><li> **On:** Legitime NDRs werden zugestellt, und der Rückläufer wird als Spam gekennzeichnet.</li><li>**Aus:** Legitime NDRs und Rückläufer durchgehen die normale Spamfilterung. Die meisten legitimen NDRs werden an den ursprünglichen Absender der Nachricht zugestellt. Einige, aber nicht alle Rückscatter werden als Spam mit hoher Confidence gekennzeichnet. Per Definition kann der Rückscatter nur an den gefälschten Absender und nicht an den ursprünglichen Absender zugestellt werden.</li></ul> <p> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: Backscatter NDR`|
|
