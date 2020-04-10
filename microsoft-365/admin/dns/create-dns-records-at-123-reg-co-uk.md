---
title: Erstellen von DNS-Einträgen bei 123-reg.co.uk für Office 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter 123-reg.co.uk für Office 365 einrichten.
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211859"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a>Erstellen von DNS-Einträgen bei 123-reg.co.uk für Office 365

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn 123-reg.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Nachdem Sie diese Einträge bei 123-reg.co.uk hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Klicken Sie auf **Hinzufügen**.
    
7. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
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

1. Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Priority**|**Destination MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> **Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<domain-key\>) aus Ihrem Office 365-Konto ab. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen von Werten aus der Tabelle](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Klicken Sie auf **Hinzufügen**.
    
    ![Wählen Sie hinzufügen aus.](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record. 
    
    ![Wählen Sie löschen (das Papierkorbsymbol)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

1. Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus. 
    
5. Fügen Sie den ersten der sechs CNAME-Einträge hinzu.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Klicken Sie auf **Hinzufügen**.
    
    ![Wählen Sie hinzufügen aus.](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Fügen Sie die fünf anderen CNAME-Einträge hinzu.
    
    Erstellen Sie im Abschnitt **Advanced DNS** einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. If you already have an SPF record for your domain, don't create a new one for Office 365. Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Schauen Sie sich diese [Details und SPF-Beispieleinträge](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords) an. Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden. 
  
1. Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus. 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
   
    ![123reg wußte-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Klicken Sie auf **Hinzufügen**.
    
    ![Wählen Sie hinzufügen aus.](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

1. Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus. 
    
5. Fügen Sie den ersten der zwei SRV-Einträge hinzu:
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Hostname|Type|Priority|TTL|Destination SRV|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **Dieser Wert MUSS mit einem Punkt (.) enden.**<br> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **Dieser Wert MUSS mit einem Punkt (.) enden.** <br> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Klicken Sie auf **Hinzufügen**.
    
    ![Wählen Sie hinzufügen aus.](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. Fügen Sie den anderen SRV-Eintrag hinzu:
    
    Erstellen Sie im Abschnitt **Advanced DNS** einen Datensatz unter Verwendung der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
