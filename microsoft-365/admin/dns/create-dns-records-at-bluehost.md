---
title: Erstellen von DNS-Einträgen für Office 365 bei Bluehost
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei Bluehost für Office 365 einrichten.
ms.openlocfilehash: 8d8217aa3b87e103f37063248899467d79b6cf18
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211835"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a>Erstellen von DNS-Einträgen für Office 365 bei Bluehost

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Bluehost Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Nachdem Sie diese Einträge bei Bluehost hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
3. Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.
    
4. Geben Sie auf der Seite * * DNS-Zonen-Editor * * im Bereich **DNS-Eintrag hinzufügen** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
5. Wählen Sie **Add Record**aus.
    
6. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
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

1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
3. Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/>**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Office 365-Konto ab. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Wählen Sie in der Dropdownliste Typ aus.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. Wählen Sie **Add Record**aus.
    
    ![Wählen Sie Add Record aus.](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. Wenn im Abschnitt **MX (Mail Exchanger)** weitere MX-Einträge vorhanden sind, löschen Sie die einzelnen Einträge. 
    
    Wählen Sie für einen der anderen MX-Einträge die Option **Löschen aus.**
    
    ![Wählen Sie DELETE für jeden zusätzlichen MX-Eintrag aus.](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.
    
    ![Wählen Sie OK aus.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. Gehen Sie entsprechend vor, um alle weiteren bereits aufgeführten MX-Einträge zu löschen.
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
3. Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.
    
4. Suchen Sie im Abschnitt **a (Host)** Records nach der Zeile für den **Auto Ermittlungs** Eintrag, und wählen Sie dann **Löschen** für diese Zeile aus. 
    
    > [!IMPORTANT]
    > Sie müssen den vorhandenen **AutoErmittlung** seintrag löschen,  *bevor Sie*  den **AutoErmittlung** seintrag hinzufügen, der für Office 365 erforderlich ist. Bluehost gestattet Ihnen nicht, zwei **AutoErmittlung** seinträge gleichzeitig zu pflegen. 
  
    ![Wählen Sie löschen aus.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. Wählen Sie **OK** aus.
    
    ![Wählen Sie OK aus.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. Erstellen Sie den ersten der sechs CNAME-Einträge.
    
    Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Erstellen des ersten CNAME-Eintrags](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. Wählen Sie **Add Record**aus.
    
    ![Wählen Sie Add Record aus.](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. Fügen Sie die fünf anderen CNAME-Einträge hinzu.
    
    Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der nächsten Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es bei Ihrer Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Office 365 keinen neuen, sondern fügen Sie die erforderlichen Office 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Sehen Sie sich die folgenden [Externen DNS-Einträge für Office 365 an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden. 
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
3. Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
        
    |**Host Record**|**TTL**|**Type**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
   
    ![Kopieren des txt-Werts](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. Wählen Sie **Add Record**aus.
    
    ![Wählen Sie Add Record aus.](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

1. Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
3. Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.
    
4. Erstellen Sie den ersten der zwei SRV-Einträge.
    
    Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Service**|**Protocol**|**Host**|**TTL**|**Type**|**Priority**|**Weight**|**Port**|**Points To**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Kopieren des Werts für den neuen Datensatz](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. Wählen Sie **Add Record**aus.
    
    ![Wählen Sie Add Record aus.](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. Fügen Sie den anderen SRV-Eintrag hinzu.
    
    Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der anderen Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  

