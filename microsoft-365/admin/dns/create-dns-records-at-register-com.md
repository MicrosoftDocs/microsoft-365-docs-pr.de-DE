---
title: Erstellen von DNS-Einträgen bei Register.com für Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Register.com für Microsoft einrichten.
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780325"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Erstellen von DNS-Einträgen bei Register.com für Microsoft

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Register.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.
  
Das sind die wichtigsten hinzuzufügenden Einträge. Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
- [Hinzufügen eines TXT-Eintrags bei Register.com, um zu überprüfen, ob Sie der Besitzer der Domäne sind](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Hinzufügen der für Microsoft erforderlichen CNAME-Einträge](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nachdem Sie diese Einträge bei Register.com hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.
  

  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Hinzufügen eines TXT-Eintrags bei Register.com, um zu überprüfen, ob Sie der Besitzer der Domäne sind
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Domänen** aus.
    
3. Wählen Sie **Manage**aus.
    
4. Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.
    
5. Führen Sie einen Bildlauf nach unten zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **Edit TXT Records (SPF)** aus.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).          |
   
7. Wählen Sie **weiter**aus.
    
8. Wählen Sie auf der nächsten Seite erneut **Continue** aus, um Ihre Änderungen zu bestätigen. 
    
9. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.
    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_add_MX"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Domänen** aus.
    
3. Wählen Sie **Manage**aus.
    
4. Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.
    
5. Führen Sie einen Bildlauf zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **e-Mail-Exchanger-Einträge bearbeiten**aus.
    
    ![Wählen Sie Bearbeiten von e-Mail-Exchanger-Einträgen](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    (Wählen Sie in der Dropdownliste den Wert **Priority** aus.) 
    
    |****Host Name****|****Priority****|****Mail Server****|
    |:-----|:-----|:-----|
    |@  <br/> |High  <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*. Mail.Protection.Outlook.com  <br/>  <br/>**Hinweis:** Holen Sie sich Ihr \<*domain-key*\> Microsoft-Konto. <br> [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen des Werts aus der Tabelle](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Wenn bereits andere MX-Einträge aufgeführt sind, wählen Sie jeden dieser Einträge zum Löschen aus.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern. 
    
    ![Wählen Sie weiter aus.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen CNAME-Einträge
<a name="BKMK_add_CNAME"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Domänen** aus.
    
3. Wählen Sie **Manage**aus.
    
4. Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.
    
5. Scrollen Sie zum Abschnitt **Erweiterte technische Einstellungen** , und wählen Sie dann **Bearbeiten von Domänen Alias Einträgen**aus.
    
    ![Auswählen von Datensätzen zum Bearbeiten von Domänen Aliasen](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Wählen Sie **Weitere Domänenaliase hinzufügen**aus.
    
    ![Wählen Sie weitere Domänenaliase hinzufügen aus.](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. Fügen Sie die erforderlichen CNAME-Einträge hinzu.
    
    Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    |****Erstes Feld (ohne Beschriftung)****|****Points to****|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![Kopieren und Einfügen der DNS-Werte aus der Tabelle](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. Wenn Sie alle benötigten CNAME-Einträge hinzugefügt haben, wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern. 
    
    ![Wählen Sie weiter aus.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.  
  
Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Domänen** aus.
    
3. Wählen Sie **Manage**aus.
    
4. Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.
    
5. Führen Sie einen Bildlauf zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **TXT-Datensätze bearbeiten (SPF)** aus.
    
    ![Bearbeiten von TXT-Einträgen auswählen (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    |****Host Name****|****TXT Record****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.  |
   
     ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern. 
    
    ![Wählen Sie weiter aus.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.
    
2. Wählen Sie **Domänen** aus.
    
3. Wählen Sie **Manage**aus.
    
4. Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.
    
5. Führen Sie einen Bildlauf zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **SRV-Einträge bearbeiten**aus.
    
    ![Auswählen der Option zum Bearbeiten von SRV-Einträgen](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Fügen Sie den ersten der zwei SRV-Einträge hinzu:
    
    Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    (Wählen Sie in der Dropdownliste den Wert **Priority** aus.) 
    
    |****Service****|****Proto****|****Name****|****Priority****|****Weight****|****Port****|****Target****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Wählen Sie **Weitere SRV-Einträge hinzufügen**aus.
    
    ![Wählen Sie weitere SRV-Einträge hinzufügen aus.](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Fügen Sie den zweiten SRV-Eintrag hinzu:
    
    Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein. Sie können die Werte auch kopieren und einfügen.
    
9. Wenn Sie beide SRV-Einträge hinzugefügt haben, wählen Sie **weiter**aus.
    
    ![Wählen Sie weiter aus.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern. 
    
    ![Wählen Sie weiter aus.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
