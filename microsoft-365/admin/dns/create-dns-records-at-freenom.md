---
title: Erstellen von DNS-Einträgen bei Freenom für Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Freenom for Microsoft einrichten.
ms.openlocfilehash: 8332d63acf34a7f999b549467494b7819cebf092
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910354"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Erstellen von DNS-Einträgen bei Freenom für Microsoft

[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml) , wenn Sie nicht finden, wonach Sie suchen. 
  
> [!CAUTION]
> Die Freenom-Website unterstützt keine SRV-Einträge, was bedeutet, dass mehrere Skype for Business Online- und Outlook Web App-Features nicht funktionieren. Unabhängig davon, welchen Microsoft-Plan Sie verwenden, gibt es erhebliche Diensteinschränkungen, und Sie können zu einem anderen DNS-Hostinganbieter wechseln. 
  
Wenn Sie trotz der Diensteinschränkungen ihre eigenen Microsoft -DNS-Einträge bei Freenom verwalten möchten, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mails und andere Dienste einrichten.
  
  
> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="bkmk_txt"> </a>

Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.
  
> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen. 
  
1. Um zu beginnen, wechseln Sie über diesen [](https://my.freenom.com/)Link zu Ihrer Domänenseite in Freenom. Sie werden aufgefordert, sich anzumelden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Wählen **Sie Dienste** aus, und wählen Sie dann Meine Domänen **aus.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Wählen Sie für die Domäne, die Sie bearbeiten möchten, **Die Option Domäne verwalten aus.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Wählen **Sie Freenom DNS verwalten aus.**
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **TXT** aus. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(leer lassen)  <br/> |TXT  <br/> |3600 (Sekunden)  <br/> |MS=msXXXXXXXX  <br/> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Wählen **Sie Änderungen speichern aus.**
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
    
  
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
    
  
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
    
  
> [!NOTE]
>  Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="bkmk_mx"> </a>

1. Um zu beginnen, wechseln Sie über diesen [](https://my.freenom.com/)Link zu Ihrer Domänenseite in Freenom. Sie werden aufgefordert, sich anzumelden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Wählen **Sie Dienste** aus, und wählen Sie dann Meine Domänen **aus.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Wählen Sie für die Domäne, die Sie bearbeiten möchten, **Die Option Domäne verwalten aus.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Legen Sie den für Ihre Domäne verwendeten Namen auf die standardmäßigen Freenom-Namenserver ein. Wählen **Sie Verwaltungstools** aus, und wählen Sie **dann Nameserver aus.**
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Stellen Sie **sicher, dass Standardnameserver** verwenden ausgewählt ist, und wählen Sie **dann Nameserver ändern aus.**
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Wählen **Sie Freenom DNS verwalten aus.**
    
    ![Freenom auswählen Freenom-DNS verwalten](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **MX** aus. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Type**|**TTL**|**Target**|**Priorität**|
    |:-----|:-----|:-----|:-----|:-----|
    |(leer lassen)  <br/> |MX (Mail Exchanger)  <br/> |3600 (Sekunden)  <br/> |\<domain-key\>.mail.protection.outlook.com  <br/> **Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.   [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml) <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Wählen **Sie Änderungen speichern aus.**
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Wenn es weitere MX-Einträge gibt, löschen Sie sie alle: Wählen Sie für jeden Eintrag Delete (Löschen) aus. Wählen Sie für jeden Datensatz **Löschen aus.** Wenn die Meldung Möchten Sie diesen Eintrag wirklich **entfernen?** angezeigt wird, wählen Sie **OK aus.**
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen CNAME-Einträge
<a name="bkmk_cname"> </a>

1. Um zu beginnen, wechseln Sie über diesen [](https://my.freenom.com/)Link zu Ihrer Domänenseite in Freenom. Sie werden aufgefordert, sich anzumelden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Wählen **Sie Dienste** aus, und wählen Sie dann Meine Domänen **aus.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Wählen Sie für die Domäne, die Sie bearbeiten möchten, **Die Option Domäne verwalten aus.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Wählen **Sie Freenom DNS verwalten aus.**
    
    ![Freenom auswählen Freenom-DNS verwalten](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **SNAME** aus. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Erstellen Sie den ersten CNAME-Eintrag. Geben Sie dann in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Eintragstyp**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (Sekunden)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Wählen **Sie Änderungen speichern aus.**
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen. 
    
    Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. 

1. Um zu beginnen, wechseln Sie über diesen [](https://my.freenom.com/)Link zu Ihrer Domänenseite in Freenom. Sie werden aufgefordert, sich anzumelden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Wählen **Sie Dienste** aus, und wählen Sie dann Meine Domänen **aus.**
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Wählen Sie für die Domäne, die Sie bearbeiten möchten, **Die Option Domäne verwalten aus.**
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Wählen **Sie Freenom DNS verwalten aus.**
    
    ![Freenom auswählen Freenom-DNS verwalten](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. Wählen Sie unter **Add Record** (Eintrag hinzufügen) in der Spalte **Type** (Typ) im Menü **TXT** aus. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen. 
    
    |**Name**|**Eintragstyp**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(leer lassen)  <br/> |TXT  <br/> |3600 (Sekunden)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Wählen **Sie Änderungen speichern aus.**
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
