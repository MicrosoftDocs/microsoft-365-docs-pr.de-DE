---
title: ASF-Einstellungen in EoP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über die ASF-Einstellungen (Advanced Spam Filter) informieren, die in Anti-Spam-Richtlinien in Exchange Online Protection (EoP) zur Verfügung stehen.
ms.openlocfilehash: b314b8b2a2de72987d9acff688602df0e0947293
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653341"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Einstellungen für erweiterte Spam Filter (ASF) in EoP

> [!NOTE]
> ASF-Einstellungen, die derzeit in Anti-Spam-Richtlinien verfügbar sind, werden gerade veraltet. Es wird empfohlen, diese Einstellungen nicht in Anti-Spam-Richtlinien zu verwenden. Die Funktionalität dieser ASF-Einstellungen wird in andere Teile des Filter Stapels integriert. Weitere Informationen finden Sie unter [EoP Anti-Spam Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer ermöglichen die Einstellungen für den erweiterten Spamfilter (ASF) in Anti-Spam-Richtlinien (auch bekannt als Spamfilter-oder Inhaltsfilter Richtlinien) Administratoren das Markieren von Nachrichten als Spam basierend auf bestimmten Nachrichteneigenschaften. ASF zielt speziell auf diese Eigenschaften ab, da Sie häufig in Spam enthalten sind. Je nach Eigenschaft Kennzeichnen ASF-Erkennungen die Nachricht entweder als **Spam** oder als Spam mit **hoher Vertrauens**Würdigkeit.

> [!NOTE]
> Das Aktivieren einer oder mehrerer der ASF-Einstellungen ist ein aggressiver Ansatz für die Spamfilterung. Sie können Nachrichten, die von ASF gefiltert werden, nicht als falsch positive Ergebnisse melden. Nachrichten, die von ASF gefiltert wurden, können Sie nach folgenden Kriterien identifizieren:
> - Regelmäßige Spamquarantäne Benachrichtigungen für Endbenutzer.
>
> - Das vorhanden sein gefilterter Nachrichten in Quarantäne.
>
> - Die spezifischen `X-CustomSpam:` X-Headerfelder, die Nachrichten hinzugefügt werden, wie in diesem Thema beschrieben.

In den folgenden Abschnitten werden die ASF-Einstellungen und-Optionen beschrieben, die in den Anti-Spam-Richtlinien im Security & Compliance Center und in Exchange Online PowerShell oder eigenständigen EoP PowerShell ([New-hostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) und [sethostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)) zur Verfügung stehen. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivieren, deaktivieren oder Testen von ASF-Einstellungen

Für jede ASF-Einstellung stehen die folgenden Optionen unter Anti-Spam-Richtlinien zur Verfügung:

- **On**: ASF fügt das entsprechende X-Kopfzeilenfeld zur Nachricht hinzu und markiert die Nachricht entweder als **Spam** (SCL 5 oder 6 für die [Einstellung "Spambewertung verbessern](#increase-spam-score-settings)") oder als Spam für **hohe Zuverlässigkeit** (SCL 9 für [Markierung als Spameinstellungen](#mark-as-spam-settings)).

- **Off**: die ASF-Einstellung ist deaktiviert. Dies ist der Standardwert, und es wird empfohlen, dass Sie ihn nicht ändern.

- **Test**: ASF fügt das entsprechende X-Kopfzeilenfeld zur Nachricht hinzu. Was mit der Nachricht geschieht, wird durch den*Aktions*-Wert ( **Test Mode Options** ) bestimmt:

  - **None**: das Nachrichtenrouting und die Zustellung sind von der ASF-Erkennung nicht betroffen. Die Nachricht unterliegt weiterhin anderen Arten von Filtern und Regeln in EoP.

  - **Standard-x-Header-Text hinzufügen (*AddXHeader*)**: der Wert der x-Kopfzeile `X-CustomSpam: This message was filtered by the custom spam filter option` wird der Nachricht hinzugefügt. Sie können diesen Wert in Posteingangsregeln oder Nachrichtenfluss Regeln (auch bekannt als Transportregeln) verwenden, um das Routing und die Zustellung der Nachricht zu beeinflussen.

  - **BCC-Nachricht senden (*BccMessage*)**: die angegebenen e-Mail-Adressen (der Wert des *den testmodebcctorecipients* -Parameters in PowerShell) werden dem Feld Bcc der Nachricht hinzugefügt, und die Nachricht wird an die Bcc-Empfänger übermittelt. Im Security & Compliance Center trennen Sie mehrere e-Mail-Adressen durch Semikolons (;). In PowerShell trennen Sie mehrere e-Mail-Adressen durch Kommas.

  **Anmerkungen**:

  - Der Testmodus ist für die folgenden ASF-Einstellungen nicht verfügbar:

    - **Bedingte Sender ID-Filterung: schwerer Fehler** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR**-Rückläufer (*MarkAsSpamNdrBackscatter*)
    - **SPF-Eintrag: Hard Fail** (*MarkAsSpamSpfRecordHardFail*)

  - Die gleiche Testmodus-Aktion wird auf *alle* ASF-Einstellungen angewendet, die auf " **Test**" festgelegt sind. Sie können keine unterschiedlichen Testmodus-Aktionen für unterschiedliche ASF-Einstellungen konfigurieren.

## <a name="increase-spam-score-settings"></a>Verbessern der Spam Bewertungseinstellungen

Die folgenden ASF-Einstellungen legen die SCL-Bewertung (Spam Confidence Level) der erkannten Nachrichten auf 5 oder 6 fest, was dem **Spam** Filter Urteil und der entsprechenden Aktion in den Antispam-Richtlinien entspricht.

****

|Anti-Spam-Richtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Bildlinks zu Remotestandorten** <br/><br/> *IncreaseScoreWithImageLinks*|Nachrichten, die `<Img>` HTML-Tag-Links zu Remotestandorten enthalten (beispielsweise mit http), werden als Spam gekennzeichnet.|`X-CustomSpam: Image links to remote sites`|
|**URL-Umleitung zu anderem Port** <br/><br/> *IncreaseScoreWithRedirectToOtherPort*|Nachricht mit Hyperlinks, die andere TCP-Ports als 80 (http), 8080 (alternatives http) oder 443 (HTTPS) umleiten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL redirect to other port`|
|**Numerische IP-Adresse in URL** <br/><br/> *IncreaseScoreWithNumericIps*|Nachrichten mit numerischen URLs (in der Regel IP-Adressen) werden als Spam gekennzeichnet.|`X-CustomSpam: Numeric IP in URL`|
|**URL zu BIZ- oder INFO-Websites:** <br/><br/> *IncreaseScoreWithBizOrInfoUrls*|Nachrichten, die die Links. biz oder. info im Nachrichtentext enthalten, werden als Spam gekennzeichnet.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Als Spameinstellungen kennzeichnen

Mit den folgenden ASF-Einstellungen wird die SCL-Bewertung der erkannten Nachrichten auf 9 festgelegt, was dem Spamfilter-Urteil für **hohe Zuverlässigkeit** und der entsprechenden Aktion in den Antispam-Richtlinien entspricht.

****

|Anti-Spam-Richtlinieneinstellung|Beschreibung|X-Header hinzugefügt|
|---|---|---|
|**Leere Nachrichten** <br/><br/> *MarkAsSpamEmptyMessages*|Nachrichten ohne Betreff, ohne Inhalt im Nachrichtentext und ohne Anlagen werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet.|`X-CustomSpam: Empty Message`|
|**JavaScript oder VBScript in HTML** <br/><br/> *MarkAsSpamJavaScriptInHtml*|Nachrichten, die JavaScript oder Visual Basic Script Edition in HTML verwenden, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Diese Skriptsprachen werden in e-Mail-Nachrichten verwendet, um zu verursachen, dass bestimmte Aktionen automatisch ausgeführt werden.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Frame- oder IFrame-Tags in HTML** <br><br/> *MarkAsSpamFramesInHtml*|Nachrichten, die `<frame>` oder `<iframe>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Diese Tags werden in e-Mail-Nachrichten verwendet, um die Seite zum Anzeigen von Text oder Grafiken zu formatieren.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Object-Tags in HTML** <br><br/> *MarkAsSpamObjectTagsInHtml*|Nachrichten, die `<object>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Mit diesem Tag können Plug-ins oder Anwendungen in einem HTML-Fenster ausgeführt werden.|`X-CustomSpam: Object tag in html`|
|**Embed-Tags in HTML** <br><br/> *MarkAsSpamEmbedTagsInHtml*|Nachrichten, die `<embed>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Dieses Tag ermöglicht das Einbetten verschiedener Arten von Dokumenten unterschiedlicher Datentypen in einem HTML-Dokument (beispielsweise Sounds, Filme oder Bilder).|`X-CustomSpam: Embed tag in html`|
|**Form-Tags in HTML** <br><br/> *MarkAsSpamFormTagsInHtml*|Nachrichten, die `<form>` HTML-Tags enthalten, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Dieses Tag wird zum Erstellen von Websiteformularen verwendet. Werbe-E-Mails enthalten häufig dieses Tag, um Informationen vom Empfänger zu erbitten.|`X-CustomSpam: Form tag in html`|
|**Web-Bugs in HTML** <br><br/> *MarkAsSpamWebBugsInHtml*|Ein *Web-Bug* (auch als *Web-Beacon*bezeichnet) ist ein Grafikelement (oft nur ein Pixel um ein Pixel), das in e-Mail-Nachrichten verwendet wird, um zu bestimmen, ob die Nachricht gelesen wurde. <br/><br/> Nachrichten, die Webfehler enthalten, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Legitime Newsletter verwenden möglicherweise Webfehler, obwohl viele dies als eine Invasion der Privatsphäre ansehen. |`X-CustomSpam: Web bug`|
|**Liste mit sensiblen Begriffen anwenden** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft verwaltet eine dynamische, aber nicht bearbeitbare Liste von Wörtern, die potenziell anstößigen Nachrichten zugeordnet sind. <br/><br/> Nachrichten, die Wörter aus der Liste der vertraulichen Wörter im Betreff oder Nachrichtentext enthalten, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-Eintrag: Schwerer Fehler** <br><br/> *MarkAsSpamSpfRecordHardFail*|Nachrichten, die von einer IP-Adresse gesendet werden, die im SPF-Eintrag (SPF) in DNS für die Quell-e-Mail-Domäne nicht angegeben ist, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. <br/><br/> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF Record Fail`|
|**Bedingte Absender-ID-Filterung: Schwerer Fehler** <br><br/> *MarkAsSpamFromAddressAuthFail*|Nachrichten, für die eine bedingte Sender ID-Überprüfung schwer ausfällt, werden als Spam gekennzeichnet. <br/><br/> Diese Einstellung kombiniert eine SPF-Prüfung mit einer Sender ID-Überprüfung, um den Schutz gegen Nachrichtenkopfzeilen zu gewährleisten, die gefälschte Absender enthalten. <br/><br/> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: SPF From Record Fail`|
|**NDR-Rückläufer** <br><br/> *MarkAsSpamNdrBackscatter*|Bei *Backscatter* handelt es sich um nutzlose Unzustellbarkeitsberichte (auch als NDR oder Unzustellbarkeitsnachrichten bezeichnet), die von gefälschten Absendern in e-Mail-Nachrichten verursacht werden. Weitere Informationen finden Sie unter [Backscatter Messages and EoP](backscatter-messages-and-eop.md). <br/><br/> Sie müssen diese Einstellung in den folgenden Umgebungen nicht konfigurieren, da legitime Unzustellbarkeitsberichte zugestellt werden und Backscatter als Spam gekennzeichnet wird: <ul><li>Microsoft 365-Organisationen mit Exchange Online Postfächern.</li><li>Lokale e-Mail-Organisationen, in denen Sie *ausgehende* e-Mails über EoP weiterleiten.</li></ul><br/> In eigenständigen EoP-Umgebungen, die eingehende e-Mail an lokale Postfächer schützen, hat das Aktivieren oder Deaktivieren dieser Einstellung das folgende Ergebnis: <ul><li> **On**: legitime Unzustellbarkeitsberichte werden zugestellt, und Backscatter wird als Spam gekennzeichnet.</li><li>**Off**: legitime Unzustellbarkeitsberichte und Backscatter durchlaufen die normale Spamfilterung. Die meisten legitimen Unzustellbarkeitsberichte werden an den ursprünglichen Absender der Nachricht übermittelt. Einige, jedoch nicht alle, werden als Spam mit hoher Vertrauenswürdigkeit gekennzeichnet. Per Definition kann Backscatter nur an den gefälschten Absender und nicht an den ursprünglichen Absender zugestellt werden.</li></ul><br/> Der Testmodus ist für diese Einstellung nicht verfügbar.|`X-CustomSpam: Backscatter NDR`|
|
