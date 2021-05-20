---
title: Verwenden von DKIM für E-Mail in Ihrer benutzerdefinierten Domäne
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie DomainKeys Identified Mail (DKIM) mit Microsoft 365 verwenden können, um sicherzustellen, dass die von Ihrer benutzerdefinierten Domäne gesendeten Nachrichten von den Ziel-E-Mail-Systemen als vertrauenswürdig eingestuft werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cd04911e3663bb6b9fa00d4946b26086dc8094d
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538267"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Dieser Artikel führt die Schritte auf, um DomainKeys Identified Mail (DKIM) mit Microsoft 365 zu verwenden, um sicherzustellen, dass Ziel-E-Mail-Systeme Nachrichten vertrauen, die von Ihrer benutzerdefinierten Domäne aus gesendet werden.

Inhalt dieses Artikels:

- [So funktioniert DKIM besser als SPF, um Spoofing zu verhindern](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Schritte zum manuellen Upgrade Ihrer 1024-Bit-Schlüssel auf 2048-Bit-DKIM-Verschlüsselungsschlüssel](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Schritte zum manuellen Einrichten von DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Schritte zum Konfigurieren von DKIM für mehr als eine benutzerdefinierte Domäne](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Deaktivieren der DKIM-Signierungsrichtlinie für eine benutzerdefinierte Domäne](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Standardverhalten für DKIM und Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Einrichten von DKIM, damit ein Drittanbieterdienst E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden oder fälschen kann](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Nächste Schritte: Nach dem Einrichten von DKIM für Microsoft 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> Microsoft 365 richtet DKIM automatisch für die "onmicrosoft.com"-Anfangsdomänen ein. Das bedeutet, dass Sie keine weiteren Aktionen durchführen müssen, um DKIM für jegliche Anfangsdomänennamen einzurichten (z. B. litware.onmicrosoft.com). Weitere Informationen zu Domänen finden Sie unter [Häufig gestellte Fragen (FAQ) zu Domänen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

DKIM ist eine der drei Authentifizierungsmethoden (SPF, DKIM und DMARC), die verhindern, dass Angreifer Nachrichten senden können, die aussehen, wie wenn sie von Ihrer Domäne stammen würden.

Mit DKIM können Sie für ausgehende E-Mail-Nachrichten im Nachrichtenkopf eine digitale Signatur hinzufügen. Wenn Sie DKIM konfigurieren, autorisieren Sie Ihre Domäne, ihren Namen einer E-Mail-Nachricht mithilfe einer kryptografischen Authentifizierung zuzuordnen oder die E-Mail damit zu signieren. E-Mail-Systeme, die E-Mails von Ihrer Domäne erhalten, können diese digitale Signatur verwenden, um zu überprüfen, ob eingehende E-Mails legitim sind.

Einfach ausgedrückt verschlüsselt ein privater Schlüssel die Kopfzeile in ausgehenden E-Mails einer Domäne. Der öffentliche Schlüssel wird in den DNS-Einträgen der Domäne veröffentlicht, und empfangende Server können diesen Schlüssel verwenden, um die Signatur zu entschlüsseln. Die DKIM-Verifizierung hilft den empfangenden Servern zu bestätigen, dass die E-Mail wirklich von Ihrer Domäne kommt und nicht von jemandem, der Ihre Domäne *spooft*.

> [!TIP]
>Sie können auch entscheiden, DKIM für Ihre benutzerdefinierte Domäne nicht zu verwenden. Wenn Sie DKIM für Ihre benutzerdefinierte Domäne nicht einrichten, erstellt Microsoft 365 ein privates und öffentliches Schlüsselpaar, aktiviert die DKIM-Signierung und konfiguriert dann die Microsoft 365-Standardrichtlinie für Ihre benutzerdefinierte Domäne.

 Die eingebaute DKIM-Konfiguration von Microsoft 365 bietet den meisten Kunden genügend Abdeckung. Sie sollten jedoch DKIM in folgenden Fällen manuell für Ihre benutzerdefinierte Domäne konfigurieren:

- Sie haben mehr als eine benutzerdefinierte Domäne in Microsoft 365

- Sie werden auch DMARC einrichten (**empfohlen**)

- Sie möchten die Kontrolle über Ihren privaten Schlüssel.

- Sie möchten Ihre CNAME-Einträge anpassen.

- Sie möchten DKIM-Schlüssel für E-Mails von Drittanbieterdomänen einrichten, beispielsweise bei Verwendung eines Drittanbietermassenversenders von E-Mails.


## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>So funktioniert DKIM besser als SPF, um Spoofing zu verhindern
<a name="HowDKIMWorks"> </a>

SPF fügt Informationen zu einem Nachrichtenumschlag hinzu, aber DKIM *verschlüsselt* eine Signatur im Nachrichtenkopf. Wenn Sie eine Nachricht weiterleiten, können Teile dieses Nachrichtenumschlags vom Weiterleitungsserver entfernt werden. Da die digitale Signatur bei der E-Mail-Nachricht bleibt, da er Teil der E-Mail-Kopfzeile ist, funktioniert DKIM selbst dann, wenn eine Nachricht weitergeleitet wurde, wie im folgenden Beispiel gezeigt.

![Diagramm, in dem eine weitergeleitete Nachricht gezeigt wird, bei der die DKIM-Authentifizierung übergangen wird, wenn die SPF-Prüfung fehlschlägt.](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

Wenn Sie in diesem Beispiel nur einen SPF TXT-Eintrag für Ihre Domäne veröffentlicht hätten, könnte der E-Mail-Server des Empfängers Ihre E-Mail als Spam markiert und ein falsch positives Ergebnis generiert haben. **Das Hinzufügen von DKIM in diesem Szenario reduziert die Meldung von *falsch positivem* Spam.** Da sich DKIM zur Authentifizierung auf die Kryptografie mit öffentlichen Schlüsseln stützt und nicht nur auf IP-Adressen, wird DKIM als deutlich stärkere Form der Authentifizierung als SPF betrachtet. Wir empfehlen, SPF und DKIM sowie auch DMARC in Ihrer Bereitstellung zu verwenden.

> [!TIP]
> DKIM verwendet einen privaten Schlüssel, um eine verschlüsselte Signatur in den Nachrichtenkopf einzufügen. Die signierende (ausgehende) Domäne wird als Wert des Felds **d=** in die Kopfzeile eingefügt. Die überprüfende Domäne (Empfängerdomäne) verwendet dann das Feld **d=**, um den öffentlichen Schlüssel im DNS nachzuschlagen und die Nachricht zu authentifizieren. Wenn die Nachricht verifiziert wird, ist die DKIM-Überprüfung erfolgreich.


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Schritte zum manuellen Upgrade Ihrer 1024-Bit-Schlüssel auf 2048-Bit-DKIM-Verschlüsselungsschlüssel
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 richtet DKIM automatisch für die *onmicrosoft.com*-Domänen ein. Es sind keine Schritte erforderlich, um DKIM für anfängliche Domänennamen zu verwenden (wie z. B. litware.*onmicrosoft.com*). Weitere Informationen zu Domänen finden Sie unter [Häufig gestellte Fragen (FAQ) zu Domänen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Da sowohl 1024-Bit als auch 2048-Bit für DKIM-Schlüssel unterstützt werden, erfahren Sie in diesen Anweisungen, wie Sie Ihren 1024-Bit-Schlüssel in[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) auf 2048 aktualisieren. Die nachstehenden Schritte werden auf zwei Anwendungsfälle angewandt. Wählen Sie bitte die Variante aus, die Ihren Anforderungen am ehesten entspricht.

- Wenn Sie **DKIM bereits konfiguriert haben**, ändern Sie die Biteinstellung, indem Sie den folgenden Befehl ausführen:

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  **oder**

- Führen Sie den folgenden Befehl aus, um eine **neue Implementierung von DKIM** zu erstellen:

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

Bleiben Sie mit Exchange Online PowerShell verbunden, um *zu überprüfen, ob die* Konfiguration durch Ausführung des folgenden Befehls ausgeführt werden konnte:

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> Dieser neue 2048-Bit-Schlüssel wird zum RotateOnDate wirksam und sendet E-Mails in der Zwischenzeit mit dem 1024-Bit-Schlüssel. Nach vier Tagen können Sie einen erneuten Test mit dem 2048-Bit-Schlüssel ausführen (also, wenn der Wechsel auf den zweiten Selektor angewendet wird).

Wenn Sie zum zweiten Selektor wechseln möchten, haben Sie folgende Möglichkeiten: a) Sie lassen den Wechseln des Selektors durch den Microsoft 365-Dienst durchführen und aktualisieren auf 2048-Bit innerhalb der nächsten 6 Monate, oder b) nach 4 Tagen, und wechseln den zweiten Selektorschlüssel manuell unter Verwendung des entsprechenden, oben aufgeführten Cmdlets, nachdem Sie zuvor sichergestellt haben, dass 2048-Bit-Schlüssel verwendet werden.

Ausführliche Informationen zur Syntax und zu Parametern finden Sie in den folgenden Artikeln: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig)und [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).

## <a name="steps-to-manually-set-up-dkim"></a>Schritte zum manuellen Einrichten von DKIM
<a name="SetUpDKIMO365"> </a>

Um DKIM zu konfigurieren, müssen Sie diese Schritte ausführen:

- [Veröffentlichen von zwei CNAME-Einträgen für Ihre benutzerdefinierte Domäne in DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Aktivieren der DKIM-Signierung für Ihre benutzerdefinierte Domäne](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Veröffentlichen von zwei CNAME-Einträgen für Ihre benutzerdefinierte Domäne in DNS
<a name="Publish2CNAME"> </a>

Für jede Domäne, für die Sie eine DKIM-Signatur in DNS hinzufügen möchten, müssen Sie zwei CNAME-Einträge veröffentlichen.

> [!NOTE]
> Wenn Sie nicht den gesamten Artikel gelesen haben, haben Sie möglicherweise diese zeitsparenden Informationen zur PowerShell-Verbindung verpasst: [Herstellen einer Verbindung zu Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Führen Sie in Exchange Online PowerShell die folgenden Befehle aus, um die Selektoreinträge zu erstellen:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Wenn Sie neben der anfänglichen Domäne zusätzliche benutzerdefinierte Domänen in Microsoft 365 bereitgestellt haben, müssen Sie zwei CNAME-Einträge für jede zusätzliche Domäne veröffentlichen. Wenn Sie also zwei Domänen haben, müssen Sie vier zusätzliche CNAME-Einträge veröffentlichen usw.

Verwenden Sie für CNAME-Einträge das folgende Format.

> [!IMPORTANT]
> Wenn Sie zu unseren GCC High-Kunden gehören, berechnen wir _domainGuid_ anders! Anstatt den MX-Eintrag für Ihre _initialDomain_ zur Berechnung von _domainGuid_ zu suchen, wird diese direkt aus der angepassten Domäne heraus berechnet. Wenn Ihre benutzerdefinierte Domäne z. B. "contoso.com" lautet, wird Ihre "domainGuid" zu "contoso-com", wobei alle Punkte durch Bindestriche ersetzt werden. Unabhängig von dem MX-Eintrag, auf den Ihre „initialDomain“ verweist, verwenden Sie also immer die oben genannte Methode, um die in den CNAME-Einträgen verwendete „domainGuid“ zu berechnen.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Dabei gilt:

- Für Microsoft 365 sind die Selektoren immer „selector1“ oder „selector2“.

- _domainGUID_ ist identisch mit _domainGUID_ im angepassten MX-Eintrag für Ihre benutzerdefinierte Domäne, welche vor mail.protection.outlook.com angezeigt wird. Beispiel: Im folgenden MX-Eintrag für die Domäne contoso.com ist die _domainGUID_ contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ ist die Domäne, die Sie bei der Anmeldung für Microsoft 365 verwendet haben. Anfangsdomänen enden immer auf "onmicrosoft.com". Informationen zum Ermitteln Ihrer ersten Domäne finden Sie unter [Häufig gestellte Fragen zu Domänen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Wenn Sie beispielsweise als erste Domäne „cohovineyardandwinery.onmicrosoft.com“ und zwei benutzerdefinierte Domänen „cohovineyard.com“ und „cohowinery.com“ haben, müssten Sie zwei CNAME-Einträge für jede zusätzliche Domäne einrichten, also insgesamt vier CNAME-Einträge.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> Es ist wichtig, den zweiten Eintrag zu erstellen, aber zum Zeitpunkt der Erstellung wird möglicherweise nur einer der Selektoren verfügbar sein. Im Wesentlichen verweist der zweite Selektor möglicherweise auf eine noch nicht erstellte Adresse. Es empfiehlt sich trotzdem, den zweiten CNAME-Eintrag zu erstellen, da Ihre Schlüsselrotation dann nahtlos ausgeführt wird.


### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>Schritte zum Aktivieren der DKIM-Signatur für Ihre benutzerdefinierte Domäne
<a name="EnableDKIMinO365"> </a>

Nachdem Sie die CNAME-Einträge im DNS veröffentlicht haben, können Sie die DKIM-Signierung über Microsoft 365 aktivieren. Sie können dies über das Microsoft 365 Admin Center oder mithilfe von PowerShell durchführen.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>So aktivieren Sie die DKIM-Signierung für Ihre benutzerdefinierte Domäne über das Admin Center

1. [Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Wechseln Sie zu [protection.office.com](https://protection.office.com) oder [security.microsoft.com](https://security.microsoft.com), je nachdem, welches Portal Sie verwenden, und folgen Sie dem nachstehenden Pfad.

|protection.office.com  |security.microsoft.com  |
|---------|---------|
| Bedrohungsmanagement > Richtlinie > Zusätzliche Richtlinien > DKIM     | E-Mail und Zusammenarbeit > Richtlinien und Regeln > Bedrohungsrichtlinien > Zusätzliche Richtlinien > DKIM        | 

3. Wählen Sie die Domäne aus, für die Sie DKIM aktivieren möchten, und wählen Sie dann für **Nachrichten für diese Domäne mit DKIM-Signaturen signieren** die Option **Aktivieren** aus. Wiederholen Sie diesen Schritt für jede benutzerdefinierte Domäne.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>So aktivieren Sie die DKIM-Signierung für Ihre benutzerdefinierte Domäne mit PowerShell

> [!IMPORTANT]
>:::image type="content" source="../../media/DKIMNoKeysSavedForThisDomain.PNG" alt-text="Der Fehler „Für diese Domäne werden keine DKIM-Schlüssel gespeichert“.":::
> Wenn Sie DKIM zum ersten Mal konfigurieren und die Fehlermeldung „Für diese Domäne werden keine DKIM-Schlüssel gespeichert“ angezeigt wird, führen Sie den Befehl in Schritt 2 unten aus (z. B. *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*), um den Schlüssel anzuzeigen.

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie den folgenden Befehl aus:

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   Dabei ist _domain_ der Name der benutzerdefinierten Domäne, für die Sie die DKIM-Signierung aktivieren möchten.

   Beispiel für die Domäne „contoso.com“:

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>So bestätigen Sie, dass die DKIM-Signierung ordnungsgemäß für Microsoft 365 konfiguriert ist

Warten Sie einige Minuten, bevor Sie diese Schritte ausführen, um zu bestätigen, dass Sie DKIM ordnungsgemäß konfiguriert haben. Dadurch ist genug Zeit vorhanden, um die DKIM-Informationen zur Domäne im gesamten Netzwerk zu verteilen.

- Senden Sie eine Nachricht von einem Konto in Ihrer Microsoft 365-Domäne mit aktiviertem DKIM an ein anderes E-Mail-Konto wie „outlook.com“ oder „Hotmail.com“.

- Verwenden Sie zu Testzwecken kein „aol.com“-Konto. AOL überspringt möglicherweise die DKIM-Überprüfung, wenn die SPF-Prüfung erfolgreich ist. Dadurch hat der Test keine Relevanz.

- Öffnen Sie die Nachricht, und sehen Sie sich die Überschrift an. Anweisungen zum Anzeigen der Kopfzeile der Nachricht variieren je nach Messagingclient. Anweisungen zum Anzeigen der Kopfzeilen von Nachrichten in Outlook finden Sie unter [Anzeigen der Kopfzeilen von Internetnachrichten in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  Die mit DKIM signierte Nachricht enthält den Hostnamen und die Domäne, die Sie definiert haben, wenn Sie die CNAME-Einträge veröffentlicht haben. Die Nachricht sieht in etwa wie im folgenden Beispiel aus:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Suchen Sie nach der „Authentication-Results“-Kopfzeile. Obwohl jeder empfangende Dienst ein geringfügig anderes Format verwendet, um die eingehenden E-Mail-Nachrichten mit Zeitstempeln zu versehen, sollte das Ergebnis immer etwas wie **DKIM=pass** oder **DKIM=OK** enthalten.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>Konfigurieren von DKIM für mehrere benutzerdefinierte Domänen
<a name="DKIMMultiDomain"> </a>

Wenn Sie zu einem bestimmten Zeitpunkt in der Zukunft eine weitere benutzerdefinierte Domäne hinzufügen und DKIM für die neue Domäne aktivieren möchten, müssen Sie die Schritte in diesem Artikel für jede Domäne ausführen. Schließen Sie insbesondere alle Schritte in [Schritte zum manuellen Einrichten von DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365) ab.

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>Deaktivieren der DKIM-Signierungsrichtlinie für eine benutzerdefinierte Domäne
<a name="DisableDKIMSigningPolicy"> </a>

Durch das Deaktivieren der Signierungsrichtlinie wird DKIM nicht vollständig deaktiviert. Nach einer bestimmten Zeitspanne übernimmt Microsoft 365 automatisch die Standardrichtlinie für Ihre Domäne. Weitere Informationen finden Sie unter [Standardverhalten für DKIM und Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>So deaktivieren Sie die DKIM-Signierungsrichtlinie mithilfe von Windows PowerShell

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie einen der folgenden Befehle für jede Domäne aus, für die Sie die DKIM-Signierung deaktivieren möchten.

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Beispiel:

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Oder

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   Wobei _number_ der Index der Richtlinie ist. Beispiel:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Standardverhalten für DKIM und Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

Wenn Sie DKIM nicht aktivieren, erstellt Microsoft 365 automatisch einen öffentlichen 1024-Bit-DKIM-Schlüssel für Ihre Domäne und den zugehörigen privaten Schlüssel, der intern in unserem Rechenzentrum gespeichert wird. Standardmäßig verwendet Microsoft 365 eine standardmäßige Signierkonfiguration für Domänen, die keine Richtlinie eingerichtet haben. Dies bedeutet, dass, wenn Sie DKIM nicht selbst einrichten, Microsoft 365 seine Standardrichtlinie und Standardschlüssel verwendet, die erstellt wurden, um DKIM für Ihre Domäne zu aktivieren.

Wenn Sie die DKIM-Signatur nach der Aktivierung nach einer bestimmten Zeit wieder deaktivieren, wendet Microsoft 365 automatisch die Standardrichtlinie für Ihre Domäne an.

Im folgenden Beispiel wird angenommen, dass DKIM für fabrikam.com durch Microsoft 365 und nicht durch den Administrator der Domäne aktiviert wurde. Das bedeutet, dass die erforderlichen CNAME-Einträge nicht im DNS vorhanden sind. DKIM-Signaturen für E-Mail-Nachrichten aus dieser Domäne sehen in etwa wie folgt aus:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

In diesem Beispiel enthalten der Hostname und die Domäne die Werte, auf die der CNAME-Eintrag verweisen würden, wenn die DKIM-Signierung für „fabrikam.com“ vom Domänenadministrator aktiviert worden wäre. Schließlich wird jede einzelne Nachricht, die von Microsoft 365 gesendet wird, mit DKIM signiert. Wenn Sie DKIM selbst aktivieren, ist die Domäne identisch mit der Domäne in der „From:“-Adresse, in diesem Fall „fabrikam.com“. Andernfalls erfolgt keine Ausrichtung. Stattdessen wird die erste Domäne Ihrer Organisation verwendet. Informationen zum Ermitteln Ihrer ersten Domäne finden Sie unter [Häufig gestellte Fragen zu Domänen](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Einrichten von DKIM, damit ein Drittanbieterdienst E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden oder fälschen kann
<a name="SetUp3rdPartyspoof"> </a>

Bei einigen Massen-E-Mail-Dienstanbietern oder Software-as-a-Service-Anbietern können Sie DKIM-Schlüssel für E-Mails einrichten, die von diesem Dienst stammen. Dies erfordert eine Koordination zwischen Ihnen und dem Drittanbieter, damit die erforderlichen DNS-Einträge eingerichtet werden können. Einige Drittanbieter verfügen möglicherweise über eigene CNAME-Einträge mit anderen Selektoren. Keine zwei Organisationen führen dies auf die gleiche Weise durch. Der Prozess hängt vollständig von der Organisation ab.

Eine Beispielnachricht mit einer ordnungsgemäßen DKIM-Konfiguration für contoso.com und bulkemailprovider.com kann wie folgt aussehen:

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

In diesem Beispiel sind zu diesem Zweck die folgenden Schritte erforderlich:

1. Der Massen-E-Mail-Anbieter hat einen öffentlichen DKIM-Schlüssel für Contoso bereitgestellt.

2. Contoso hat den DKIM-Schlüssel für den DNS-Eintrag veröffentlicht.

3. Beim Senden der E-Mail signiert der Massen-E-Mail-Anbieter den Schlüssel mit dem entsprechenden privaten Schlüssel. So hat der Massen-E-Mail-Anbieter die DKIM-Signatur an die Kopfzeile der Nachricht angefügt.

4. Beim Empfangen von E-Mails führen Systeme eine DKIM-Überprüfung durch, indem der d=\<domain\>-Wert der DKIM-Signatur mit der Domäne im Feld „Von: (5322.From)" der Nachricht verglichen wird. In diesem Beispiel entsprechen die Werte den folgenden:

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>Domänen identifizieren, die keine E-Mails senden

Organisationen sollten explizit angeben, ob eine Domäne keine E-Mails sendet, indem sie `v=DKIM1; p=` im DKIM-Eintrag für diese Domänen angeben. Dies weist empfangende E-Mail-Server darauf hin, dass es keine gültigen öffentlichen Schlüssel für die Domäne gibt. Jede E-Mail, die vorgibt, von dieser Domäne zu stammen, sollte abgelehnt werden. Sie sollten dies für jede Domäne und Subdomäne mit einem Wildcard-DKIM tun.

Der DKIM-Eintrag sieht beispielsweise wie folgt aus:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>Nächste Schritte: Nach dem Einrichten von DKIM für Microsoft 365
<a name="DKIMNextSteps"> </a>

Obwohl DKIM Spoofing verhindern soll, funktioniert DKIM besser mit SPF und DMARC. Sobald Sie DKIM eingerichtet haben, sollten Sie auch SPF einrichten, falls noch nicht geschehen. Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Ausführlichere Informationen zur Verwendung von SPF durch Microsoft 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). Lesen Sie danach [Verwenden von DMARC zur Überprüfung von E-Mails](use-dmarc-to-validate-email.md). [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) umfassen die Syntax- und Kopfzeilenfelder, die von Microsoft 365 für DKIM-Überprüfungen verwendet werden.

## <a name="more-information"></a>Weitere Informationen

Schlüsselrotation über PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)
