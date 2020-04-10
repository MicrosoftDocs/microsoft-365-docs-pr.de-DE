---
title: Erstellen von DNS-Einträgen für Office 365 bei Hostgator
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Hostgator für Office 365 einrichten.
ms.openlocfilehash: a5a41e5c1eba9d99d1927192472da7746277dd38
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211715"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a>Erstellen von DNS-Einträgen für Office 365 bei Hostgator

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Hostgator Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
> [!IMPORTANT]
> Sie müssen die erste procedurebelow ausführen, [Ihre Domäne auf Ihr Hostingkonto hinweisen](#point-your-domain-to-your-hosting-account), bevor Sie DNS-Einträge mithilfe eines der anderen Verfahren in diesem Artikel hinzufügen. 

Nachdem Sie all diese Änderungen bei Hostgator vorgenommen haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.
  
Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Verweisen Ihrer Domäne auf Ihr Hostingkonto
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Sie müssen diesen Vorgang vor allen anderen in diesem Artikel aufgeführten Verfahren ausführen. 
  
Führen Sie die folgenden Schritte aus, um Ihre Domäne und Hostingkonten zu verknüpfen.
  
1. Im ersten Schritt navigieren Sie über [diesen Link](https://portal.hostgator.com/) zu Ihrer Domänenverwaltungsseite bei Hostgator. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie Links die Option **Domains** aus.
  
3. Wählen Sie auf der Seite **Domänen verwalten** die Domäne aus, die Sie aktualisieren möchten. 
  
4. Wählen Sie im Popup Menü auf der linken Seite die Option **Name Servers**aus.
  
5. Wählen Sie auf der Seite **Namensserver** für Ihre Domäne in der Dropdownliste **diese Domäne automatisch auf mein Hostingkonto aufheben** das Hostingkonto aus, das Ihrer Domäne zugeordnet ist. 
  
6. Wählen Sie **Namenserver speichern**aus.
    
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Bevor Sie diesen Vorgang ausführen, müssen Sie zuerst die Schritte im ersten Abschnitt dieses Artikels ([Verweisen Ihrer Domäne auf Ihr Hostingkonto](#point-your-domain-to-your-hosting-account)) ausführen. 
  
Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Die Anmelde-e-Mail, die Sie von Hostgator erhalten haben, gibt diese Adresse an, und ein cPanel-Link ist auch auf der **Hostingseite** verfügbar.)
    
    > [!IMPORTANT]
    > Um Ihrer Domäne eine cPanel-Adresse zuzuordnen, benötigen Sie ein Hostkonto bei Hostgator. Für den Einstieg in Office 365 können Sie entweder ein Hostkonto von Hostgator erwerben oder [Ihre Nameserver auf Office 365 umdelegieren](change-nameservers-at-hostgator.md). 
  
2. Wählen Sie auf der Seite **Systemsteuerung** im Bereich **Domänen** die Option **Erweiterter Zonen-Editor**aus.
    
3. Geben Sie auf der Seite **Erweiterter Zonen-Editor** im Bereich **Hinzufügen eines Datensatzes** in den Feldern für den neuen Datensatz die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein. 
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
    |Verwenden Sie Ihre *domain_name*. (for example, fourthcoffee.com.)  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.
    
5. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
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

> [!IMPORTANT]
> Bevor Sie diesen Vorgang ausführen, müssen Sie zuerst die Schritte im ersten Abschnitt dieses Artikels ([Verweisen Ihrer Domäne auf Ihr Hostingkonto](#point-your-domain-to-your-hosting-account)) ausführen. 
  
1. Um zu beginnen, wechseln Sie zu Ihrer cPanel-Seite bei Hostgator. Sie werden aufgefordert, sich zuerst anzumelden.
    
    (Jedem gehosteten Konto bei Hostgator ist eine eindeutige cPanel-Adresse zugewiesen. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Die Anmelde-e-Mail, die Sie von Hostgator erhalten haben, gibt diese Adresse an, und ein cPanel-Link ist auch auf der **Hostingseite** verfügbar.)
    
    > [!IMPORTANT]
    > Um Ihrer Domäne eine cPanel-Adresse zuzuordnen, benötigen Sie ein Hostkonto bei Hostgator. Für den Einstieg in Office 365 können Sie entweder ein Hostkonto von Hostgator erwerben oder [Ihre Nameserver auf Office 365 umdelegieren](change-nameservers-at-hostgator.md). 
  
2. Wählen Sie auf der Seite **Systemsteuerung** im Bereich **e-Mail** die Option **MX-Eintrag**aus.
    
 
3. Wählen Sie im Bereich **Email Routing** die Option **Remote Mail Exchanger** aus.

4. Wählen Sie **ändern**aus.
  
5. Geben Sie im Bereich **neuen Daten Satz hinzufügen** in den Feldern für den neuen Datensatz die Werte aus der folgenden Tabelle ein, oder kopieren Sie Sie, und fügen Sie Sie ein. 
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<Domänenschlüssel\>*  .mail.protection.outlook.com  <br/> **Hinweis:** Rufen Sie \< Ihren *Domänenschlüssel* \> aus Ihrem Office 365-Konto ab.    [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Wählen Sie **neuen Datensatz hinzufügen**aus.
   
 
7. Wenn im Abschnitt **MX Records** weitere MX-Einträge vorhanden sind, entfernen Sie die einzelnen Einträge. 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Bevor Sie diesen Vorgang ausführen, müssen Sie zuerst die Schritte im ersten Abschnitt dieses Artikels ([Verweisen Ihrer Domäne auf Ihr Hostingkonto](#point-your-domain-to-your-hosting-account)) ausführen. 
  
1. Um zu beginnen, wechseln Sie zu Ihrer cPanel-Seite bei Hostgator. Sie werden aufgefordert, sich zuerst anzumelden.
    
    (Jedem gehosteten Konto bei Hostgator ist eine eindeutige cPanel-Adresse zugewiesen. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Die Anmelde-e-Mail, die Sie von Hostgator erhalten haben, gibt diese Adresse an, und ein cPanel-Link ist auch auf der **Hostingseite** verfügbar.)
    
    > [!IMPORTANT]
    > Um Ihrer Domäne eine cPanel-Adresse zuzuordnen, benötigen Sie ein Hostkonto bei Hostgator. Für den Einstieg in Office 365 können Sie entweder ein Hostkonto von Hostgator erwerben oder [Ihre Nameserver auf Office 365 umdelegieren](change-nameservers-at-hostgator.md). 
  
2. Wählen Sie auf der Seite **Systemsteuerung** im Bereich **Domänen** die Option **Erweiterter Zonen-Editor**aus.
    
3. Fügen Sie den ersten der sechs CNAME-Einträge hinzu.
    
    Geben Sie auf der Seite **Erweiterter Zonen-Editor** im Bereich **Hinzufügen eines Datensatzes** in den Feldern für den neuen Datensatz die Werte aus der ersten Zeile in der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein. 
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |**Name**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (Beispiel: "autodiscover.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (Beispiel: "sip.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (Beispiel: "lyncdiscover.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (Beispiel: "enterpriseregistration.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (Beispiel: "enterpriseregistration.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.

5. Fügen Sie die fünf anderen CNAME-Einträge hinzu.
    
    Erstellen Sie im Abschnitt **Hinzufügen eines Daten** Satzes einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. If you already have an SPF record for your domain, don't create a new one for Office 365. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Schauen Sie sich diese [Details und SPF-Beispieleinträge](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords) an. Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden. 
  
> [!IMPORTANT]
> Bevor Sie diesen Vorgang ausführen, müssen Sie zuerst die Schritte im ersten Abschnitt dieses Artikels ([Verweisen Ihrer Domäne auf Ihr Hostingkonto](#point-your-domain-to-your-hosting-account)) ausführen. 
  
1. Um zu beginnen, wechseln Sie zu Ihrer cPanel-Seite bei Hostgator. Sie werden aufgefordert, sich zuerst anzumelden.
    
    (Jedem gehosteten Konto bei Hostgator ist eine eindeutige cPanel-Adresse zugewiesen. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Die Anmelde-e-Mail, die Sie von Hostgator erhalten haben, gibt diese Adresse an, und ein cPanel-Link ist auch auf der **Hostingseite** verfügbar.)
    
    > [!IMPORTANT]
    > Um Ihrer Domäne eine cPanel-Adresse zuzuordnen, benötigen Sie ein Hostkonto bei Hostgator. Für den Einstieg in Office 365 können Sie entweder ein Hostkonto von Hostgator erwerben oder [Ihre Nameserver auf Office 365 umdelegieren](change-nameservers-at-hostgator.md). 
  
2. Wählen Sie auf der Seite **Systemsteuerung** im Bereich **Domänen** die Option **Erweiterter Zonen-Editor**aus.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |**Name**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Verwenden Sie Ihre *domain_name*. (for example, fourthcoffee.com.)  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
  
4. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Bevor Sie diesen Vorgang ausführen, müssen Sie zuerst die Schritte im ersten Abschnitt dieses Artikels ([Verweisen Ihrer Domäne auf Ihr Hostingkonto](#point-your-domain-to-your-hosting-account)) ausführen. 
  
1. Um zu beginnen, wechseln Sie zu Ihrer cPanel-Seite bei Hostgator. Sie werden aufgefordert, sich zuerst anzumelden.
    
    (Jedem gehosteten Konto bei Hostgator ist eine eindeutige cPanel-Adresse zugewiesen. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Die Anmelde-e-Mail, die Sie von Hostgator erhalten haben, gibt diese Adresse an, und ein cPanel-Link ist auch auf der **Hostingseite** verfügbar.)
    
    > [!IMPORTANT]
    > Um Ihrer Domäne eine cPanel-Adresse zuzuordnen, benötigen Sie ein Hostkonto bei Hostgator. Für den Einstieg in Office 365 können Sie entweder ein Hostkonto von Hostgator erwerben oder [Ihre Nameserver auf Office 365 umdelegieren](change-nameservers-at-hostgator.md). 
  
2. Wählen Sie auf der Seite **Systemsteuerung** im Bereich **Domänen** die Option **Erweiterter Zonen-Editor**aus.

    
3. Fügen Sie den ersten der zwei SRV-Einträge hinzu.
    
    Geben Sie auf der Seite **Advanced DNS Zone Editor** im Bereich **Add a Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |**Name**|**TTL**|**Type**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls. *domain_name*. (Beispiel: "_sip._tls.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp. *domain_name*. (Beispiel: "_sipfederationtls._tcp.fourthcoffee.com.")  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Wählen Sie **Add Record** (Eintrag hinzufügen) aus.

  
5. Fügen Sie den anderen SRV-Eintrag hinzu.
    
    Erstellen Sie im Abschnitt **Hinzufügen eines Daten** Satzes einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
