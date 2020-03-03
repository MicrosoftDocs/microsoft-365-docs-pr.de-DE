---
title: Erstellen von DNS-Einträgen bei 1&1 Ionos für Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste auf 1&1 Ionos für Office 365 einrichten.
ms.openlocfilehash: d4ff6bea0d96402c34b1d1ae302510a6e718c38d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352056"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a>Erstellen von DNS-Einträgen bei 1&1 Ionos für Office 365

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
> [!CAUTION]
> Beachten Sie, dass mit 1&1 Ionos keine Domäne sowohl über einen MX-Eintrag als auch über einen CNAME-Eintrag auf oberster Ebene verfügen kann. Dadurch wird die Art und Weise eingeschränkt, in der Sie Exchange Online für Office 365 konfigurieren können. Es gibt eine Problemumgehung, aber wir empfehlen, Sie **nur** zu verwenden, wenn Sie bereits über Erfahrung mit dem Erstellen von Unterdomänen bei 1&1 Ionos verfügen. > Wenn Sie sich trotz dieser [Diensteinschränkung](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) für die Verwaltung Ihrer eigenen Office 365-DNS-Einträge mit 1&1 Ionos entscheiden, befolgen Sie die Schritte in diesem Artikel, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten. 
  
Nachdem Sie diese Einträge bei 1&1 Ionos hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Office 365 Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://my.1and1.com/)zu ihrer Domänen Seite bei 1&1 Ionos. You'll be prompted to log in.
    
2. Wählen Sie **Manage Domains**aus.
    
3. Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.
    
5. Wählen Sie im Abschnitt **txt-und SRV-Einträge** die Option **Eintrag hinzufügen**aus.
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
    |TXT  <br/> |(Lassen Sie dieses Feld leer)  <br/> |MS=ms *XXXXXXXX*  <br/> Hinweis: Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Klicken Sie auf **Speichern**.
    
8. Wählen Sie erneut **Speichern** aus. 
    
9. Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.
    
10. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.
  
Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden
<a name="BKMK_add_MX"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!NOTE]
> Wenn Sie sich bei 1und1.de registriert haben, melden Sie sich [hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://my.1and1.com/)zu ihrer Domänen Seite bei 1&1 Ionos. You'll be prompted to log in.
    
2. Wählen Sie **Manage Domains**aus.
    
3. Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.
    
5. In the **MX Records** section, in the ** Mail Exchanger (MX Record) ** area, select **Other mail server**.<br/>(Möglicherweise müssen Sie nach unten scrollen.)<br/>![1&amp;1-BP-configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.<br/>(Wenn noch keine MX-Einträge aufgeführt sind, fahren Sie mit dem nächsten Schritt fort.)<br/>![1&amp;1-BP-configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. Geben Sie in den Feldern für den Eintrag **MX 1** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**MX 1**|**Priorität**|
    |:-----|:-----|
    | *\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/>  Hinweis: Rufen Sie \<ihren Domänenschlüssel\> aus Ihrem Office 365-Konto ab. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | 
    
    ![1 und 1-configure 2 und 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Klicken Sie auf **Speichern**.<br/>(Möglicherweise müssen Sie nach unten scrollen.)<br/>![1&amp;1-BP-configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.<br/>![Auswählen von "Ja" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

1&1 Ionos erfordert eine Problemumgehung, sodass Sie einen MX-Eintrag zusammen mit den CNAME-Einträgen verwenden können, die für Office 365 e-Mail-Dienste erforderlich sind. Diese Problemumgehung erfordert, dass Sie eine Gruppe von Unterdomänen auf 1&1 Ionos erstellen und Sie CNAME-Einträgen zuweisen.
  
> [!IMPORTANT]
> Bevor Sie beginnen, sollten Sie sich vergewissern, dass Sie mindestens zwei verfügbare Unterdomänen haben. Diese Lösung wird nur empfohlen, wenn Sie bereits über Erfahrung mit dem Erstellen von Unterdomänen bei 1&1 Ionos verfügen. 
  
### <a name="basic-cname-records"></a>Einfache CNAME-Einträge

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!NOTE]
> Wenn Sie sich bei 1und1.de registriert haben, melden Sie sich [hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://my.1and1.com/)zu ihrer Domänen Seite bei 1&1 Ionos. You'll be prompted to log in.
    
2. Wählen Sie **Manage Domains**aus.
    
3. Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann unter **Domänen verwalten**aus.<br/>![1&amp;1-BP-configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Im nächsten Schritt erstellen Sie zwei Unterdomänen und legen einen **Alias** für jede hiervor fest.<br/>(Dies ist erforderlich, da 1&1 Ionos nur einen CNAME-Eintrag auf oberster Ebene unterstützt, für Office 365 jedoch mehrere CNAME-Einträge erforderlich sind.)<br/>Zuerst erstellen Sie die Autoermittlungs-Unterdomäne.
    
4. Wählen Sie im Abschnitt unter **Domänenübersicht** die Option unter **Domäne erstellen**aus.
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)

    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1&amp;1-BP-configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Wählen Sie unter **Domäne erstellen**aus.<br/>![1&amp;1-BP-configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **AutoErmittlung** , die Sie soeben erstellt haben, und wählen Sie dann das Panel-Steuerelement **(v)** für diese Unterdomäne aus. <br/>![1&amp;1-BP-configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. Wählen Sie im Bereich unter **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus. <br/>![1&amp;1-BP-configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. Wählen Sie im Abschnitt **a/AAAA Records (IP Addresses)** im Bereich **IP-Adresse (a Record)** die Option **CNAME**aus.<br/>![1&amp;1-BP-configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1&amp;1-BP-configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**.<br/>![1&amp;1-BP-configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Klicken Sie auf **Speichern**.<br/>![1&amp;1-BP-configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Zusätzliche CNAME-Einträge

Die zusätzlichen CNAME-Einträge, die mit den folgenden Schritten erstellt werden, aktivieren die Skype for Business Online-Dienste. Führen Sie dieselben Schritte wie beim Erstellen der beiden vorherigen CNAME-Einträge durch.
  
1. Erstellen Sie die dritte Unterdomäne (Lyncdiscover).<br/>Wählen Sie im Abschnitt unter **Domänenübersicht** die Option unter **Domäne erstellen**aus.
    
2. Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Wählen Sie unter **Domäne erstellen**aus.
    
4. Wählen Sie auf der Seite **Domänen Center** die Option unter **Domänen verwalten**aus.
    
5. Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **lyncdiscover** , die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für diese Unterdomäne aus. <br/>Wählen Sie im Bereich unter **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.
    
6. In the **A/AAAA Records (IP Addresses)** section, in the ** IP address (A Record) ** area, select **CNAME**.
    
7. Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen. <br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am Aware** , und wählen Sie dann **Speichern**aus.
    
9. Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.
    
10. Erstellen der vierten Unterdomäne (SIP): <br/>Wählen Sie im Abschnitt unter **Domänenübersicht** die Option unter **Domäne erstellen**aus.
    
11. Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)<br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Wählen Sie unter **Domäne erstellen**aus.
    
13. Wählen Sie auf der Seite **Domänen Center** die Option unter **Domänen verwalten**aus.
    
14. Suchen Sie im Abschnitt **Subdomain Overview** die **SIP** -Unterdomäne, die Sie soeben erstellt haben, und wählen Sie dann das Panel-Steuerelement **(v)** für diese Unterdomäne aus. <br/>Wählen Sie im Bereich unter **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.
    
15. In the **A/AAAA Records (IP Addresses)** section, in the ** IP address (A Record) ** area, select **CNAME**.
    
16. Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen. 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am Aware** , und wählen Sie dann **Speichern**aus.
    
18. Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.
    
### <a name="cname-records-needed-for-mdm"></a>Für MDM erforderliche CNAME-Einträge

> [!IMPORTANT]
> Führen Sie das gleiche Verfahren wie bei den anderen vier CNAME-Einträgen aus, doch geben Sie dabei die Werte aus der folgenden Tabelle ein. 
  
|**Create Subdomain**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es bei Ihrer Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Office 365 keinen neuen, sondern fügen Sie die erforderlichen Office 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Sehen Sie sich die folgenden [Externen DNS-Einträge für Office 365 an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!NOTE]
> Wenn Sie sich bei 1und1.de registriert haben, melden Sie sich [hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://my.1and1.com/)zu ihrer Domänen Seite bei 1&1 Ionos. You'll be prompted to log in.
    
2. Wählen Sie **Manage Domains**aus.
    
3. Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** (**v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.
    
5. Wählen Sie im Abschnitt **txt-und SRV-Einträge** die Option **Eintrag hinzufügen**aus. <br/>(Möglicherweise müssen Sie nach unten scrollen.)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(Choose the **Type** value from the drop-down list.) <br/>
    
    |**Typ**|**Prefix**|**Name Value**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Dieses Feld leer lassen.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           | 
    
    ![TXT-Eintrag](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Klicken Sie auf **Speichern**.<br/>![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Klicken Sie auf **Speichern**.<br/>![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.<br/>![Auswählen von "Ja" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!NOTE]
> Wenn Sie sich bei 1und1.de registriert haben, melden Sie sich [hier an](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://my.1and1.com/)zu ihrer Domänen Seite bei 1&1 Ionos. You'll be prompted to log in.
    
2. Wählen Sie **Manage Domains**aus.
    
3. Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.
    
4. Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.
    
5. Wählen Sie im Abschnitt **txt-und SRV-Einträge** die Option **Eintrag hinzufügen**aus.
    
6. Fügen Sie den ersten der zwei SRV-Einträge hinzu.<br/>Geben Sie im Bereich **Eintrag hinzufügen** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. <br/>(Wählen Sie in der Dropdownliste die Werte **Type** und **TTL** aus.) 
    
    |**Type**|**Service**|**Protocol**|**Name**|**Host**|**Priority**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Dieses Feld leer lassen.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (1 h)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Dieses Feld leer lassen.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (1 h)  <br/> |  
    
    ![1&amp;1-BP-configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Klicken Sie auf **Speichern**. <br/>![1&amp;1-BP-configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Klicken Sie auf **Speichern**. <br/>![1&amp;1-BP-configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus. <br/>![Auswählen von "Ja" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Fügen Sie den anderen SRV-Eintrag hinzu. <br/>Wählen Sie im Abschnitt **txt-und SRV-Einträge** die Option **Eintrag hinzufügen**aus. <br/>Erstellen Sie im Bereich **Datensatz hinzufügen** einen Datensatz mit den Werten aus der anderen Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen**, **Speichern**und **Ja** aus, um den Datensatz abzuschließen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
