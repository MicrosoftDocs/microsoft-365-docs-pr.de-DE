---
title: Verwenden von DKIM für E-Mail in Ihrer benutzerdefinierten Domäne in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Zusammenfassung: Dieser Artikel beschreibt, wie Sie DomainKeys Identified Mail (DKIM) mit Office 365 verwenden, um sicherzustellen, dass Ziel-E-Mail-Systeme Nachrichten vertrauen, die von Ihrer benutzerdefinierten Domäne gesendet werden.'
ms.openlocfilehash: e672556448774798f5746207ff578ff18059573c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080586"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden

 **Zusammenfassung:** In diesem Artikel wird erläutert, wie Sie DomainKeys Identified Mail (DKIM) mit Office 365 verwenden, um sicherzustellen, dass Ziel-E-Mail-Systeme ausgehenden Nachrichten vertrauen, die von Ihrer benutzerdefinierten Domäne gesendet werden.
  
Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Spoofers Nachrichten senden, die aussehen, als würden sie von Ihrer Domäne stammen. Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen. Klingt kompliziert, ist es aber nicht. Wenn Sie DKIM konfigurieren, autorisieren Sie Ihre Domäne mithilfe der kryptografischen Authentifizierung, ihren Namen mit einer E-Mail-Nachricht zu verknüpfen oder zu signieren. E-Mail-Systeme, die E-Mails von Ihrer Domäne empfangen, können diese digitale Signatur verwenden, um zu ermitteln, ob eingehende E-Mails legitim sind.
  
Im Wesentlichen verwenden Sie einen privaten Schlüssel zum Verschlüsseln der Kopfzeile in ausgehenden E-Mails Ihrer Domäne. Sie veröffentlichen einen öffentlichen Schlüssel für die DNS-Einträge Ihrer Domäne, die empfangende Server verwenden können, um die Signatur zu entschlüsseln. Sie verwenden den öffentlichen Schlüssel, um sicherzustellen, dass die Nachrichten wirklich von Ihnen und nicht von einer Person kommen, die Ihre Domäne mit Spoofing beschädigen möchte.
  
Office 365 richtet DKIM automatisch für erste Domänen ein. Erste Domänen sind Domänen, die Office 365 für Sie erstellt, wenn Sie sich für den Dienst registrieren, z. B. „contoso.onmicrosoft.com". Sie müssen keine weiteren Aktionen durchführen, um DKIM für Ihre erste Domäne einzurichten. Weitere Informationen zu ersten Domänen finden Sie unter [Häufig gestellte Fragen zu Domänen](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).
  
Für DKIM für Ihre benutzerdefinierte Domäne müssen Sie ebenfalls nichts weiter unternehmen. Wenn Sie DKIM nicht für Ihre benutzerdefinierte Domäne einrichten, erstellt Office 365 ein Paar aus privatem und öffentlichem Schlüssel, aktiviert die DKIM-Signierung und konfiguriert die Office 365-Standardrichtlinie für Ihre benutzerdefinierte Domäne. Obwohl dies für die meisten Office 365-Kunden ausreicht, sollten Sie DKIM unter folgenden Umständen manuell für Ihre benutzerdefinierte Domäne konfigurieren:
  
- Sie haben mehr als eine benutzerdefinierte Domäne in Office 365.

- Sie richten auch DMARC ein (empfohlen).

- Sie möchten die Kontrolle über Ihren privaten Schlüssel.

- Sie möchten Ihre CNAME-Einträge anpassen.

- Sie möchten DKIM-Schlüssel für E-Mails von Drittanbieterdomänen einrichten, beispielsweise bei Verwendung eines Drittanbietermassenversenders von E-Mails.

Inhalt dieses Artikels:
  
- [So funktioniert DKIM besser als SPF, um Spoofing in Office 365 zu verhindern](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Schritte zum manuellen Einrichten von DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Konfigurieren von DKIM für mehrere benutzerdefinierte Domänen in Office 365](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Deaktivieren der DKIM-Signierungsrichtlinie für eine benutzerdefinierte Domäne in Office 365](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Standardverhalten für DKIM und Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Einrichten von DKIM, damit ein Drittanbieterdienst E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden oder fälschen kann](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Nächste Schritte: Nach dem Einrichten von DKIM für Office 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>So funktioniert DKIM besser als SPF, um Spoofing in Office 365 zu verhindern
<a name="HowDKIMWorks"> </a>

SPF fügt Informationen einem Nachrichtenumschlag hinzu, aber DKIM verschlüsselt tatsächlich eine Signatur in der Nachrichtenkopfzeile. Wenn Sie eine Nachricht weiterleiten, können Teile dieses Nachrichtenumschlags vom Weiterleitungsserver entfernt werden. Da die digitale Signatur bei der E-Mail-Nachricht bleibt, da er Teil der E-Mail-Kopfzeile ist, funktioniert DKIM selbst dann, wenn eine Nachricht weitergeleitet wurde, wie im folgenden Beispiel gezeigt.
  
![Diagramm, in dem eine weitergeleitete Nachricht gezeigt wird, bei der die DKIM-Authentifizierung übergangen wird, wenn die SPF-Prüfung fehlschlägt.](../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
Wenn Sie in diesem Beispiel nur einen SPF TXT-Eintrag für Ihre Domäne veröffentlicht hätten, könnte der E-Mail-Server des Empfängers Ihre E-Mail als Spam markiert und ein falsch positives Ergebnis generiert haben. Das Hinzufügen von DKIM in diesem Szenario reduziert die Meldung von falsch positivem Spam. Da DKIM die Verschlüsselung öffentlicher Schlüssel und nicht nur IP-Adressen zur Authentifizierung benötigt, wird DKIM als deutlich stärkere Form der Authentifizierung als SPF betrachtet. Wir empfehlen, SPF und DKIM sowie DMARC in Ihrer Bereitstellung zu verwenden.
  
Das Wesentliche: DKIM verwendet einen privaten Schlüssel, um eine verschlüsselte Signatur in die Nachrichtenkopfzeile einzufügen. Sie signierende oder ausgehende Domäne wird als Wert des Felds **d=** in die Kopfzeile eingefügt. Die überprüfende Domäne oder Empfängerdomäne verwendet dann das Feld **d=**, um den öffentlichen Schlüssel in DNS nachzuschlagen und die Nachricht zu authentifizieren. Wenn die Nachricht verifiziert wird, ist die DKIM-Überprüfung erfolgreich. 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>Schritte zum manuellen Einrichten von DKIM in Office 365
<a name="SetUpDKIMO365"> </a>

Um DKIM zu konfigurieren, müssen Sie diese Schritte ausführen:
  
- [Veröffentlichen von zwei CNAME-Einträgen für Ihre benutzerdefinierte Domäne in DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Aktivieren der DKIM-Signierung für Ihre benutzerdefinierte Domäne in Office 365](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Veröffentlichen von zwei CNAME-Einträgen für Ihre benutzerdefinierte Domäne in DNS
<a name="Publish2CNAME"> </a>

Für jede Domäne, für die Sie eine DKIM-Signatur in DNS hinzufügen möchten, müssen Sie zwei CNAME-Einträge veröffentlichen. 

Führen Sie die folgenden Befehle aus:

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false   
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

Erstellen von CNAMEs, auf die in der Get-DkimSigningConfig-Ausgabe verwiesen wird

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```
Die CNAME-Einträge in Ihrem DNS verweisen auf bereits erstellte A-Datensätze, die im DNS auf den Microsoft-DNS-Servern für Office 365 vorhanden sind.
  
Office 365 führt die automatische Schlüsselrotation unter Verwendung der beiden eingerichteten Datensätze durch. Wenn Sie neben der ersten Domäne zusätzliche benutzerdefinierte Domänen in Office 365 bereitgestellt haben, müssen Sie zwei CNAME-Einträge für jede zusätzliche Domäne veröffentlichen. Wenn Sie also zwei Domänen haben, müssen Sie zwei zusätzliche CNAME-Einträge veröffentlichen usw.
  
Verwenden Sie für CNAME-Einträge das folgende Format.

> [!IMPORTANT]
> Wenn Sie zu unseren GCC High-Kunden gehören, berechnen wir _domainGuid_ anders! Anstatt den MX-Eintrag für Ihre _initialDomain_ zur Berechnung von _domainGuid_ zu suchen, wird diese direkt aus der angepassten Domäne heraus berechnet. Wenn Ihre benutzerdefinierte Domäne z. B. "contoso.com" lautet, wird Ihre "domainGuid" zu "contoso-com", wobei alle Punkte durch Bindestriche ersetzt werden. Unabhängig von dem MX-Eintrag, auf den Ihre "initialDomain" verweist, verwenden Sie also immer die oben genannte Methode, um die in den CNAME-Einträgen verwendete "domainGuid" zu berechnen.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

Dabei gilt:
  
- Für Office 365 sind die Selektoren immer „selector1“ oder „selector2“.

- _domainGUID_ ist identisch mit _domainGUID_ im angepassten MX-Eintrag für Ihre benutzerdefinierte Domäne, der vor „mail.protection.outlook.com“ angezeigt wird. Im folgenden MX-Eintrag für die Domäne "contoso.com" ist die _domainGUID_ z. B. "contoso-com": 
    
    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_ ist die Domäne, die Sie bei der Anmeldung für Office 365 verwendet haben. Anfangsdomänen enden immer auf "onmicrosoft.com". Informationen zum Ermitteln Ihrer ersten Domäne finden Sie unter [Häufig gestellte Fragen zu Domänen](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).

Wenn Sie beispielsweise als erste Domäne „cohovineyardandwinery.onmicrosoft.com“ und zwei benutzerdefinierte Domänen „cohovineyard.com“ und „cohowinery.com“ haben, müssten Sie zwei CNAME-Einträge für jede zusätzliche Domäne einrichten, also insgesamt vier CNAME-Einträge.
  
```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>Aktivieren der DKIM-Signierung für Ihre benutzerdefinierte Domäne in Office 365
<a name="EnableDKIMinO365"> </a>

Nachdem Sie die CNAME-Einträge im DNS veröffentlicht haben, können Sie die DKIM-Signierung über Office 365 aktivieren. Sie können dies über das Microsoft 365 Admin Center oder mithilfe von PowerShell durchführen.
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>So aktivieren Sie die DKIM-Signierung für Ihre benutzerdefinierte Domäne über das Admin Center

1. [Melden Sie sich bei Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) mit Ihrem Geschäfts-, Schul- oder Unikonto an. 

2. Klicken Sie oben links auf das App-Startsymbol, und wählen Sie **Admin** aus.

3. Erweitern Sie im unteren linken Navigationsbereich **Admin**, und klicken Sie dann auf **Exchange**.

4. Wechseln Sie zu **Schutz** \> **dkim**.

5. Wählen Sie die Domäne aus, für die Sie DKIM aktivieren möchten, und wählen Sie dann für **Nachrichten für diese Domäne mit DKIM-Signaturen signieren** die Option **Aktivieren** aus. Wiederholen Sie diesen Schritt für jede benutzerdefinierte Domäne.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>So aktivieren Sie die DKIM-Signierung für Ihre benutzerdefinierte Domäne mit PowerShell

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://technet.microsoft.com/library/jj984289.aspx).

2. Führen Sie den folgenden Befehl aus:

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   Dabei ist _domain_ der Name der benutzerdefinierten Domäne, für die Sie die DKIM-Signierung aktivieren möchten. 

   Beispiel für die Domäne „contoso.com“:
   
   ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>So bestätigen Sie, dass die DKIM-Signierung ordnungsgemäß für Office 365 konfiguriert ist

Warten Sie einige Minuten, bevor Sie diese Schritte ausführen, um zu bestätigen, dass Sie DKIM ordnungsgemäß konfiguriert haben. Dadurch ist genug Zeit vorhanden, um die DKIM-Informationen zur Domäne im gesamten Netzwerk zu verteilen.
  
- Senden Sie eine Nachricht von einem Konto in Ihrer Office 365-Domäne mit aktiviertem DKIM an ein anderes E-Mail-Konto wie „outlook.com“ oder „Hotmail.com“.

- Verwenden Sie zu Testzwecken kein „aol.com“-Konto. AOL überspringt möglicherweise die DKIM-Überprüfung, wenn die SPF-Prüfung erfolgreich ist. Dadurch hat der Test keine Relevanz.

- Öffnen Sie die Nachricht, und sehen Sie sich die Überschrift an. Anweisungen zum Anzeigen der Kopfzeile der Nachricht variieren je nach Messagingclient. Anweisungen zum Anzeigen der Kopfzeilen von Nachrichten in Outlook finden Sie unter [Anzeigen der Kopfzeilen von E-Mail-Nachrichten](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).

  Die mit DKIM signierte Nachricht enthält den Hostnamen und die Domäne, die Sie definiert haben, wenn Sie die CNAME-Einträge veröffentlicht haben. Die Nachricht sieht in etwa wie im folgenden Beispiel aus:
    
    ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
    ```

- Suchen Sie nach der „Authentication-Results“-Kopfzeile. Obwohl jeder empfangende Dienst ein geringfügig anderes Format verwendet, um die eingehenden E-Mail-Nachrichten mit Zeitstempeln zu versehen, sollte das Ergebnis immer etwas wie **DKIM=pass** oder **DKIM=OK** enthalten.

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>Konfigurieren von DKIM für mehrere benutzerdefinierte Domänen in Office 365
<a name="DKIMMultiDomain"> </a>

Wenn Sie zu einem bestimmten Zeitpunkt in der Zukunft eine weitere benutzerdefinierte Domäne hinzufügen und DKIM für die neue Domäne aktivieren möchten, müssen Sie die Schritte in diesem Artikel für jede Domäne ausführen. Schließen Sie insbesondere alle Schritte in [Schritte zum manuellen Einrichten von DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365) ab.
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Deaktivieren der DKIM-Signierungsrichtlinie für eine benutzerdefinierte Domäne in Office 365
<a name="DisableDKIMSigningPolicy"> </a>

Durch das Deaktivieren der Signierungsrichtlinie wird DKIM nicht vollständig deaktiviert. Nach einer bestimmten Zeitspanne übernimmt Office 365 automatisch die Office 365- Standardrichtlinie für Ihre Domäne. Weitere Informationen finden Sie unter [Standardverhalten für DKIM und Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>So deaktivieren Sie die DKIM-Signierungsrichtlinie mithilfe von Windows PowerShell

1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://technet.microsoft.com/library/jj984289.aspx).

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

## <a name="default-behavior-for-dkim-and-office-365"></a>Standardverhalten für DKIM und Office 365
<a name="DefaultDKIMbehavior"> </a>

Wenn Sie DKIM nicht aktivieren, erstellt Office 365 automatisch einen öffentlichen 1024-Bit-DKIM-Schlüssel für Ihre Standarddomäne und den zugehörigen privaten Schlüssel, der intern in unserem Rechenzentrum gespeichert wird. Standardmäßig verwendet Office 365 eine standardmäßige Signierkonfiguration für Domänen, die keine Richtlinie eingerichtet haben. Dies bedeutet, dass, wenn Sie DKIM nicht selbst einrichten, Office 365 seine Standardrichtlinie und Standardschlüssel verwendet, die erstellt wurden, um DKIM für Ihre Domäne zu aktivieren.
  
Wenn Sie die DKIM-Signatur nach der Aktivierung nach einer bestimmten Zeit wieder deaktivieren, wendet Office 365 automatisch die Office 365-Standardrichtlinie für Ihre Domäne an.
  
Im folgenden Beispiel wird angenommen, dass DKIM für „fabrikam.com“ durch Office 365 und nicht durch den Administrator der Domäne aktiviert wurde. Das bedeutet, dass die erforderlichen CNAME-Einträge nicht in DNS vorhanden sind. DKIM-Signaturen für E-Mail-Nachrichten aus dieser Domäne sehen in etwa wie folgt aus:
  
```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator. Eventually, every single message sent from Office 365 will be DKIM-signed. If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com. If you don't, it will not align and instead will use your organization's initial domain. For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Einrichten von DKIM, damit ein Drittanbieterdienst E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden oder fälschen kann
<a name="SetUp3rdPartyspoof"> </a>

Bei einigen Massen-E-Mail-Dienstanbietern oder Software-as-a-Service-Anbietern können Sie DKIM-Schlüssel für E-Mails einrichten, die von diesem Dienst stammen. Dies erfordert eine Koordination zwischen Ihnen und dem Drittanbieter, damit die erforderlichen DNS-Einträge eingerichtet werden können. Keine zwei Organisationen führen dies auf die gleiche Weise durch. Der Prozess hängt vollständig von der Organisation ab.
  
Eine Beispielnachricht mit einer ordnungsgemäßen DKIM-Konfiguration für contoso.com und bulkemailprovider.com kann wie folgt aussehen:
  
```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

In diesem Beispiel sind zu diesem Zweck die folgenden Schritte erforderlich:
  
1. Der Massen-E-Mail-Anbieter hat einen öffentlichen DKIM-Schlüssel für Contoso bereitgestellt.

2. Contoso hat den DKIM-Schlüssel für den DNS-Eintrag veröffentlicht.

3. Beim Senden der E-Mail signiert der Massen-E-Mail-Anbieter den Schlüssel mit dem entsprechenden privaten Schlüssel. So hat der Massen-E-Mail-Anbieter die DKIM-Signatur an die Kopfzeile der Nachricht angefügt.

4. Beim Empfangen von E-Mails führen Systeme eine DKIM-Überprüfung durch, indem der d=\<Domäne\>-Wert der DKIM-Signatur mit der Domäne im Feld „Von: (5322.From)" der Nachricht verglichen wird. In diesem Beispiel entsprechen die Werte den folgenden:

    sender@**contoso.com**

    d=**contoso.com**

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>Nächste Schritte: Nach dem Einrichten von DKIM für Office 365
<a name="DKIMNextSteps"> </a>

Obwohl DKIM Spoofing verhindern soll, funktioniert DKIM besser mit SPF und DMARC. Sobald Sie DKIM eingerichtet haben, sollten Sie auch SPF einrichten, falls noch nicht geschehen. Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Office 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). Lesen Sie danach [Verwenden von DMARC zur Überprüfung von E-Mails in Office 365](use-dmarc-to-validate-email.md). [Anti-Spam Message Headers](anti-spam-message-headers.md) umfasst die Syntax- und Kopfzeilenfelder, die von Office 365 für DKIM-Überprüfungen verwendet werden.
