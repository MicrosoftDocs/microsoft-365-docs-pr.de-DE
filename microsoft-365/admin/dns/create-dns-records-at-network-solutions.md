---
title: Erstellen von DNS-Einträgen bei Netzwerklösungen für Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Hier erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Netzwerklösungen für Microsoft einrichten.
ms.openlocfilehash: fb5fd2d2bcb263a62306617d728f08b07bb6da34
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048927"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>Erstellen von DNS-Einträgen bei Netzwerklösungen für Microsoft

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Network Solutions Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Das sind die wichtigsten hinzuzufügenden Einträge. Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
- [Hinzufügen eines TXT-Eintrags zur Überprüfung](#add-a-txt-record-for-verification)
    
- [Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Hinzufügen der für Microsoft erforderlichen CNAME-Einträge](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nachdem Sie diese Einträge bei Netzwerklösungen hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.
  

  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus. 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scrollen Sie nach unten zum Abschnitt **Text (TXT Records)** , und wählen Sie dann **TXT-Einträge bearbeiten**aus.
    
    ![Bearbeiten von TXT-Einträgen auswählen](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.  [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Eingeben oder Einfügen von Werten in die Felder für den neuen Datensatz](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_add_MX"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus. 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Führen Sie einen Bildlauf nach unten zum Abschnitt **Mail Server (MX Records)** durch, und wählen Sie dann **MX-Einträge bearbeiten**aus.
    
    ![Auswählen von "MX-Einträge bearbeiten"](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    |**Priority**|**TTL**|**Mail Server**|
    |:-----|:-----|:-----|
    |10    <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |3600  <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> **Hinweis:** Rufen Sie Ihren * \<Domänenschlüssel\> * von Ihrem Microsoft-Konto ab. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Eingeben oder Einfügen von Werten in die Felder für den neuen Datensatz](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. Wenn weitere MX-Einträge vorhanden sind, löschen Sie diese, indem Sie **Delete** für jeden Eintrag auswählen. 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. Wenn alle ausgewählt sind, wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus. 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Führen Sie einen Bildlauf nach unten zum Abschnitt **Host Aliase (CNAME Records)** durch, und wählen Sie dann **CNAME-Einträge bearbeiten**aus.
    
    ![Wählen Sie unter Host Aliase die Option CNAME-Einträge bearbeiten aus.](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. Geben Sie in die Felder für die vier neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Other Host          (Aktivieren Sie das Optionsfeld **Other Host**.)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |(keine Einstellung)  <br/> |autodiscover.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |sip  <br/> |3600  <br/> |(keine Einstellung)  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |(keine Einstellung)  <br/> |webdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |(keine Einstellung)  <br/> |enterpriseregistration.windows.net  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |(keine Einstellung)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    
    ![Eingeben oder Einfügen von Werten für die neuen Datensätze](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. Wenn Sie alle benötigten CNAME-Einträge hinzugefügt haben, wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus. 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scrollen Sie nach unten zum Abschnitt **Text (TXT Records)** , und wählen Sie dann **TXT-Einträge bearbeiten**aus.
    
    ![Auswählen von TXT-Einträgen unter Text bearbeiten](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden. |
       
    ![Eingeben oder Einfügen von Werten für den neuen Datensatz](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.
    
    > [!IMPORTANT]
    > Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus. 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Wählen Sie **DNS bearbeiten**aus.
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scrollen Sie zum Abschnitt **Service (SRV Records)** , und wählen Sie dann **SRV-Einträge bearbeiten**aus.
    
    ![Wählen Sie "SRV-Einträge unter Dienst bearbeiten" aus.](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. Geben Sie in die Felder für die zwei neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    (Wählen Sie in den Dropdownlisten die Werte **Service** und **Protocol** aus.) 
    
    |**Service**|**Protocol**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
       
    ![Eingeben oder Einfügen von Werten für die neuen Datensätze](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. Wählen Sie **Save Changes**aus.
    
    ![Wählen Sie Save Changes aus.](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
