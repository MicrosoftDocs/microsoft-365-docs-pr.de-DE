---
title: Erstellen von DNS-Einträgen für Microsoft bei 1&1 IONOS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei 1&1 IONOS für Microsoft einrichten.
ms.openlocfilehash: 123abd6d1d93f80eb73f187b7ff75ccd90d02980
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910558"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Erstellen von DNS-Einträgen für Microsoft bei 1&1 IONOS

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
> [!CAUTION]
> Beachten Sie, dass 1 & 1 IONOS keine Domänen zulässt, die sowohl einen MX-Eintrag als auch einen Autoermittlungs-CNAME-Eintrag der oberen Ebene aufweisen. Damit werden die Möglichkeiten eingeschränkt, Exchange Online für Microsoft zu konfigurieren. Es gibt eine Problemumgehung, die Sie jedoch **nur** anwenden sollten, wenn Sie bereits Erfahrung mit der Erstellung von Unterdomänen bei 1 & 1 IONOS haben. > Wenn Sie sich trotz der [Diensteinschränkungen](../setup/domains-faq.yml) dafür entscheiden, Ihre eigenen Microsoft-DNS-Einträge bei 1&1 IONOS zu verwalten, führen Sie die Schritte in diesem Artikel aus, um die DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten. 
  
Nachdem Sie diese Einträge bei 1&1 IONOS hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.
  
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:42)]().
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Manage domains** aus.
    
3. Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.
    
5. Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus.
    
6. Geben Sie im Bereich **Add Record** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
    |TXT  <br/> |(Dieses Feld leer lassen)  <br/> |MS=ms *XXXXXXXX*  <br/> HINWEIS: Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen **Ziel- oder Verweist auf die Adresse**-Wert aus der Tabelle. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Wählen Sie **Speichern** aus.
    
8. Wählen Sie noch mal **Speichern** aus. 
    
9. Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.
    
10. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_add_MX"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:22)]().
  
> [!NOTE]
> Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Manage domains** aus.
    
3. Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.
    
5. Wählen Sie im Abschnitt **MX-Einträge** im Bereich **Mail Exchanger (MX-Eintrag)** die Option **Anderer E-Mail-Server** aus.<br/>(Möglicherweise müssen Sie nach unten scrollen.)<br/>![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.<br/>(Wenn noch keine MX-Einträge aufgeführt sind, fahren Sie mit dem nächsten Schritt fort.)<br/>![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. Geben Sie in den Feldern für den Eintrag **MX 1** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**MX 1**|**Priorität**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  HINWEIS: Erhalten Sie Ihren \<domain-key\> über Ihr Microsoft-Konto. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml) <br/> | 
    
    ![1 und 1 – konfigurieren Sie 2 und 3.](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Wählen Sie **Speichern** aus.<br/>(Möglicherweise müssen Sie nach unten scrollen.)<br/>![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.<br/>![Im Dialogfeld "DNS-Einstellungen bearbeiten" die Option "Ja" auswählen](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen sechs CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

Für 1&1 IONOS ist eine Problemumgehung erforderlich, damit Sie einen MX-Eintrag zusammen mit den CNAME-Einträgen verwenden können, die für die Microsoft-E-Mail-Dienste erforderlich sind. Im Rahmen dieser Problemumgehung müssen Sie eine Reihe von Unterdomänen bei 1&1 IONOS erstellen und diesen die CNAME-Einträge zuweisen.
  
> [!IMPORTANT]
> Bevor Sie beginnen, sollten Sie sich vergewissern, dass Sie mindestens zwei verfügbare Unterdomänen haben. Wir empfehlen diese Lösung nur, wenn Sie bereits Erfahrung mit der Erstellung von Unterdomänen bei 1&1 IONOS haben. 
  
### <a name="basic-cname-records"></a>Einfache CNAME-Einträge

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:57)]().
  
> [!NOTE]
> Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Manage domains** aus.
    
3. Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Manage Subdomains** aus.<br/>![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Im nächsten Schritt erstellen Sie zwei Unterdomänen und legen einen **Alias** für jede davon fest.<br/>(Dies ist erforderlich, da 1&1 IONOS nur den CNAME-Eintrag auf oberster Ebene unterstützt, Microsoft erfordert jedoch mehrere CNAME-Einträge.)<br/>Zuerst erstellen Sie die Autoermittlungs-Unterdomäne.
    
4. Wählen Sie im Abschnitt **Subdomain Overview** den Befehl **Create Subdomain** aus.
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)

    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Wählen Sie **Create Subdomain** aus.<br/>![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **autodiscover**, die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für die Unterdomäne aus. <br/>![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. Wählen Sie im Bereich **Subdomain Settings** die Option **Edit DNS Settings** aus. <br/>![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. Wählen Sie im Abschnitt **A/AAAA Records (IP Addresses)** im Bereich **IP address (A Record)** die Option **CNAME** aus.<br/>![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**.<br/>![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Wählen Sie **Speichern** aus.<br/>![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Zusätzliche CNAME-Einträge

Die zusätzlichen CNAME-Einträge, die mit den folgenden Schritten erstellt werden, aktivieren die Skype for Business Online-Dienste. Führen Sie dieselben Schritte wie beim Erstellen der beiden vorherigen CNAME-Einträge durch.
  
1. Erstellen Sie die dritte Unterdomäne (Lyncdiscover).<br/>Wählen Sie im Abschnitt **Subdomain Overview** die Option **Create Subdomain** aus.
    
2. Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Wählen Sie **Create Subdomain** aus.
    
4. Wählen Sie auf der Seite **Domain Center** die Option **Manage Subdomains** aus.
    
5. Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **lyncdiscover**, die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für die Unterdomäne aus. <br/>Wählen Sie im Bereich **Subdomain Settings** die Option **Edit DNS Settings** aus.
    
6. Wählen Sie im Abschnitt **A/AAAA Records (IP Addresses)** im Bereich **IP address (A Record)** die Option **CNAME** aus.
    
7. Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen. <br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**, und wählen Sie dann **Save** aus.
    
9. Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.
    
10. Erstellen der vierten Unterdomäne (SIP): <br/>Wählen Sie im Abschnitt **Subdomain Overview** den Befehl **Create Subdomain** aus.
    
11. Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)<br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Wählen Sie **Create Subdomain** aus.
    
13. Wählen Sie auf der Seite **Domain Center** die Option **Manage Subdomains** aus.
    
14. Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **sip**, die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für die Unterdomäne aus. <br/>Wählen Sie im Bereich **Subdomain Settings** die Option **Edit DNS Settings** aus.
    
15. Wählen Sie im Abschnitt **A/AAAA Records (IP Addresses)** im Bereich **IP address (A Record)** die Option **CNAME** aus.
    
16. Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen. 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**, und wählen Sie dann **Save** aus.
    
18. Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.
    
### <a name="cname-records-needed-for-mdm"></a>Für MDM erforderliche CNAME-Einträge

> [!IMPORTANT]
> Führen Sie das gleiche Verfahren wie bei den anderen vier CNAME-Einträgen aus, doch geben Sie dabei die Werte aus der folgenden Tabelle ein. 
  
|**Create Subdomain**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](../../enterprise/external-domain-name-system-records.md). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.yml) verwenden. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:09)]().
  
> [!NOTE]
> Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Manage domains** aus.
    
3. Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** (**v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.
    
5. Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus. <br/>(Möglicherweise müssen Sie nach unten scrollen.)
    
6. Geben Sie im Bereich **Add Record** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. <br/>(Wählen Sie in der Dropdownliste den Wert für **Type** aus.) <br/>
    
    |**Type**|**Prefix**|**Name Value**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Dieses Feld leer lassen.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           | 
    
    ![TXT record (TXT-Eintrag)](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Wählen Sie **Speichern** aus.<br/>![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Wählen Sie **Speichern** aus.<br/>![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.<br/>![Im Dialogfeld "DNS-Einstellungen bearbeiten" die Option "Ja" auswählen](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:51)]().
  
> [!NOTE]
> Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Manage domains** aus.
    
3. Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.
    
5. Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus.
    
6. Fügen Sie den ersten der zwei SRV-Einträge hinzu.<br/>Geben Sie im Bereich **Eintrag hinzufügen** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. <br/>(Wählen Sie in der Dropdownliste die Werte für **Type** und **TTL** aus.) 
    
    |**Type**|**Service**|**Protocol**|**Name**|**Host**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Dieses Feld leer lassen.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (1 h)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Dieses Feld leer lassen.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (1 h)  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Wählen Sie **Speichern** aus. <br/>![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Wählen Sie **Speichern** aus. <br/>![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus. <br/>![Im Dialogfeld "DNS-Einstellungen bearbeiten" die Option "Ja" auswählen](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Fügen Sie den anderen SRV-Eintrag hinzu. <br/>Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus. <br/>Erstellen Sie im Bereich **Add New DNS Record** einen Eintrag mit den Werten der zweiten Zeile in der Tabelle. Wählen Sie dann **Add**, **Save** und **Yes** aus, um den Eintrag abzuschließen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
