---
title: Erstellen von DNS-Einträgen bei Amazon Web Services (AWS) für Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Amazon Web Services (AWS) für Microsoft einrichten.
ms.openlocfilehash: 12f9341ab381324266cf2da1ca6b5423df9973dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910414"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Erstellen von DNS-Einträgen bei Amazon Web Services (AWS) für Microsoft

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn AWS Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype Online for Business und so weiter zu erstellen.
  
Nachdem Sie diese Datensätze bei AWS hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.
  

  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der Seite** Ressourcen **gehostete Zonen aus.**
    
3. Wählen Sie **auf der** Seite Gehostete Zonen in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen **Sie Datensatzsatz erstellen aus.**
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
    |(Leave this field empty.)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |Simple  <br/> |
   
6. Wählen Sie **Erstellen** aus.
    
7. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag nun an der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, wechseln Sie zurück zu Microsoft und fordern eine Suche nach dem Datensatz an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Microsoft 365 gesendet werden
<a name="BKMK_add_MX"> </a>

1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der Seite** Ressourcen **gehostete Zonen aus.**
    
3. Wählen Sie **auf der** Seite Gehostete Zonen in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen **Sie Datensatzsatz erstellen aus.**
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**Name**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(Dieses Feld leer lassen.)  <br/> |MX - Mail exchange  <br/> |No  <br/> |300  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> Die 0 ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> **Hinweis:** Holen Sie \<*domain-key*\> sich Ihre von Ihrem Microsoft 365-Konto. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |Simple  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. Wählen Sie **Erstellen** aus.
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. Wenn es weitere MX-Einträge gibt, entfernen Sie sie.
    
    > [!IMPORTANT]
    > AWS speichert MX-Einträge als Satz, der mehrere Datensätze enthalten kann. **WÄHLEN Sie Datensatzsatz** **nicht löschen** aus, da dadurch alle Ihre MX-Einträge gelöscht werden, einschließlich der gerade hinzugefügten Einträge. Verwenden Sie stattdessen die folgenden Anweisungen. 
  
    Wählen Sie zunächst den MX-Eintragssatz aus.
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    Löschen Sie als nächstes im Bereich **Edit Record Set** die einzelnen überflüssigen MX-Einträge, indem Sie den Eintrag im Feld **Value** auswählen und dann **ENTF** auf der Tastatur drücken. 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. Wählen **Sie Datensatzsatz speichern aus.**
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Hinzufügen der fünf CNAME-Datensätze, die für Microsoft 365 erforderlich sind
<a name="BKMK_add_CNAME"> </a>

1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der Seite** Ressourcen **gehostete Zonen aus.**
    
3. Wählen Sie **auf der** Seite Gehostete Zonen in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen **Sie Datensatzsatz erstellen aus.**
    
5. Fügen Sie den ersten CNAME-Eintrag hinzu.
    
    Geben Sie im Bereich **Create Record Set** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Wählen Sie die Werte für **Type** und **Routing Policy** aus den Dropdownlisten aus.) 
    
    |**Name**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |autodiscover.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |Simple  <br/> |
    |sip  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |Simple  <br/> |
    |lyncdiscover  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |webdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |Einfach  <br/> |
    |enterpriseregistration  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |enterpriseregistration.windows.net.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |Simple  <br/> |
    |enterpriseenrollment  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |Simple  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. Wählen Sie **Erstellen** aus.
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. Fügen Sie die anderen vier CNAME-Einträge hinzu.
    
    Wählen Sie **auf** der Seite Gehostete Zonen die Option **Datensatzsatz** erstellen aus, erstellen Sie einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Erstellen** aus, um den Datensatz zu vervollständigen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](../../enterprise/external-domain-name-system-records.md). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.yml) verwenden. 
  
1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der Seite** Ressourcen **gehostete Zonen aus.**
    
3. Wählen Sie **auf der** Seite Gehostete Zonen in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen Sie den **TXT-Datensatzsatz** aus. 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. Drücken Sie im Bereich **Edit Record Set** am Ende des aktuellen Eintrags im Feld **Value:** für den vorhandenen Eintrag die EINGABETASTE auf der Tastatur, um eine neue Zeile zu erstellen. Geben Sie dann in diese neue Zeile (unter dem vorhandenen Wert) direkt oder durch Kopieren und Einfügen den Wert aus der folgenden Tabelle ein. (Ein Beispiel können Sie in der Abbildung unter der Tabelle sehen.) 
    
    |**Wert:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (Die in der Bildschirmanleitung angezeigten Anführungszeichen werden automatisch eingefügt. Sie müssen Sie nicht manuell eingeben.)  <br/> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. Wählen **Sie Datensatzsatz speichern aus.**
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Hinzufügen der beiden für Microsoft 365 erforderlichen SRV-Einträge
<a name="BKMK_add_SRV"> </a>

1. Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.
    
2. Wählen Sie **auf der Seite** Ressourcen **gehostete Zonen aus.**
    
3. Wählen Sie **auf der** Seite Gehostete Zonen in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen **Sie Datensatzsatz erstellen aus.**
    
5. Fügen Sie den ersten SRV-Eintrag hinzu:
    
    Geben Sie im Bereich **Create Record Set** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Wählen Sie die Werte für **Type** und **Routing Policy** aus den Dropdownlisten aus.) 
    
    |**Name**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - Service locator|No|300|100 1 443 sipdir.online.lync.com. **Dieser Wert MUSS mit einem Zeitraum (.) enden.**><br> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |Simple|
    |_sipfederationtls._tcp|SRV - Service locator|No|300|100 1 5061 sipfed.online.lync.com. **Dieser Wert MUSS mit einem Punkt (.) enden.**<br> **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |Einfach|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. Wählen Sie **Erstellen** aus.
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. Fügen Sie den anderen SRV-Eintrag hinzu:
    
    Wählen Sie **auf** der Seite Gehostete Zonen die Option **Datensatzsatz** erstellen aus, erstellen Sie einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Erstellen** aus, um den Datensatz zu vervollständigen. 
    
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
