---
title: Erstellen von DNS-Einträgen für Office 365 bei DNSMadeEasy
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei DNSMadeEasy für Office 365 einrichten.
ms.openlocfilehash: 29bdf78e3f9993267c5f0be3b107981bb9dd3fe3
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211799"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>Erstellen von DNS-Einträgen für Office 365 bei DNSMadeEasy

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn DNSMadeEasy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Nachdem Sie diese Einträge bei DNSMadeEasy hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
> [!IMPORTANT]
> Bei DNSMadeEasy-Konten wurde die Domäne, die Sie hinzugefügt haben, bei einer anderen Domänenregistrierungsstelle gekauft. DNSMadeEasy bietet keine Domänenregistrierungsdienste. Die Möglichkeit, sich bei DNSMadeEasy anzumelden und den DNS-Eintrag zu erstellen, ist als Nachweis des Besitzes ausreichend. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten. 
    
3. Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement (**+**) (**Add new**) aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
4. Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    ||||
    |:-----|:-----|:-----|
    |**Name** <br/> |**Wert** <br/> |**TTL** <br/> |
    |(Dieses Feld leer lassen.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Wählen Sie **Submit** aus.
    
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

1. Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten. 
    
    Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten. 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. Wählen Sie auf der Seite **Managed DNS** im Bereich **MX Records** das Steuerelement **(+)** (**Add new**) aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. Geben Sie im Bereich **Add MX Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    |**Name**|**Server**|**MX Level**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Dieses Feld leer lassen.)  <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> **Hinweis:** Rufen Sie Ihren \<*Domänen-Schlüssel*\> aus Ihrem Office 365-Konto ab. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Wählen Sie **Submit** aus.
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie alle Einträge, indem Sie sie alle auswählen. 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. Wenn Sie alle Einträge markiert sind, wählen Sie **Delete selected** aus.
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. Wählen Sie im Dialogfeld **Delete MX Records** den Befehl **Delete** aus, um Ihre Änderungen zu bestätigen. 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Fügen Sie die für Office 365 erforderlichen fünf CNAME-Einträge hinzu.
<a name="BKMK_add_CNAME"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten. 
    
3. Wählen Sie auf der Seite **Managed DNS** im Bereich **CNAME Records** das Steuerelement **(+)** (**Add new**) aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Fügen Sie den ersten der fünf CNAME-Einträge hinzu.
    
    Geben Sie im Bereich **Add CNAME Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Alias für**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Wählen Sie **Submit** aus.
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Fügen Sie die vier anderen CNAME-Einträge hinzu.
    
    Wählen Sie im Abschnitt **CNAME Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es bei Ihrer Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Office 365 keinen neuen, sondern fügen Sie die erforderlichen Office 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Sehen Sie sich die folgenden [Externen DNS-Einträge für Office 365 an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden. 
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten. 
    
3. Wählen Sie auf der Seite **Managed DNS** im Bereich **TXT Records** das Steuerelement **(+)** (**Add new**) aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. Geben Sie im Bereich **Add TXT Records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Wert**|**TTL**|
    |:-----|:-----|:-----|
    |(Dieses Feld leer lassen.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Wählen Sie **Submit** aus.
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

1. Um zu beginnen, navigieren Sie über [diesen Link](https://cp.dnsmadeeasy.com/) zu Ihrer Domänenseite bei DNSMadeEasy. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie auf der Seite **Verwaltungskonsole** im Bereich **der kürzlich aktualisierten Domänen** die Domäne aus, die Sie aktualisieren möchten. 
    
3. Wählen Sie auf der Seite **Managed DNS** im Bereich **SRV Records** das Steuerelement **(+)** (**Add new**) aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Fügen Sie den ersten der zwei SRV-Einträge hinzu.
    
    Geben Sie im Bereich **Add SRV Records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Priority**|**Weight**|**Port**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Wählen Sie **Submit** aus.
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Fügen Sie den anderen SRV-Eintrag hinzu.
    
    Wählen Sie im Abschnitt **SRV Records** das Steuerelement **(+)** (**Add new**) aus, erstellen Sie einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Submit** aus, um diesen Eintrag abzuschließen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  

