---
title: Erstellen von DNS-Einträgen für Microsoft bei Google Domains
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste bei Google Domains für Microsoft einrichten.
ms.openlocfilehash: e6b1dd1eb90957a4e7fe22bd4b66ac87b2a51d09
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400449"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Erstellen von DNS-Einträgen für Microsoft bei Google Domains

 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Wenn Google Domains Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste einzurichten.
  
Nachdem Sie diese Einträge bei Google Domains hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.
  

  
> [!NOTE]
> In der Regel dauert es etwa 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Microsoft hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Hinzufügen eines TXT-Eintrags zur Überprüfung
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. Wählen Sie **Sign In** aus.
    
2. Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.
    
2. Suchen Sie auf der Seite **My domains** die Domäne, die Sie mit Microsoft verwenden möchten, und wählen Sie den Link **MANAGE** daneben aus. Wählen Sie im linken Navigationsbereich **DNS** aus.
    
3. Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Klicken Sie auf **Hinzufügen**.
    
5. Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.
    
Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.
  
Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.
  
1. Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

    
2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus. 
    
3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.
    
4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
2. Wählen Sie **Sign In** aus.
    
3. Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.
4. Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.
    
    > [!IMPORTANT]
    > Wenn Sie über ein G Suite-E-Mail-Konto verfügen, müssen Sie zuerst die diesem Konto zugeordneten MX-Einträge löschen. Die G Suite-MX-Einträge verhindern, dass Sie andere MX-Einträge hinzufügen, einschließlich der für Microsoft erforderlichen Einträge. Beachten Sie, dass Ihr G Suite-Konto durch das Löschen der G Suite-Einträge nicht gelöscht wird. Gehen Sie folgendermaßen vor, um Ihre G Suite-MX-Einträge zu löschen. 
  
5. Wählen Sie im Abschnitt **Synthetic records** im Bereich **G Suite** die Option **Delete** aus.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    ![Im Abschnitt "Synthetic records" auf "Delete" klicken](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Wählen Sie **Löschen** aus.
    
    !["Löschen" auswählen](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |**Name**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> **Hinweis:** Erhalten Sie Ihren \<*domain-key*\> über Ihr Microsoft-Konto.  [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)          Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Wählen Sie **Add** aus.
    
    !["Add" auswählen](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Wenn es weitere benutzerdefinierte MX-Einträge gibt, entfernen Sie sie.
    
1. Wählen Sie **Edit** in der Zeile mit dem MX-Eintrag aus. 
    
    !["Edit" in der Zeile mit dem MX-Eintrag auswählen](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Wählen Sie für jeden weiteren benutzerdefinierten MX-Eintrag den Eintrag im Feld **Data** aus, und drücken Sie dann die** **ENTF-TASTE auf der Tastatur, um diesen Eintrag zu löschen. 
    
    Fahren Sie fort, bis Sie den **Data**-Eintrag für jeden anderen MX-Eintrag gelöscht haben. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Wenn Sie den **Data**-Eintrag für jeden anderen MX-Eintrag gelöscht haben, wählen Sie **Save** aus, um Ihre Änderungen zu speichern. 
    
    !["Save" auswählen](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge

1. Wechseln Sie im ersten Schritt zu Ihrer [Google Domains-Seite] (https://domains.google.com/registrar), und melden Sie sich an.
    
2. Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten. 
    
3. Fügen Sie den ersten CNAME-Eintrag hinzu.
    
    Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |**Name**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Dieser Wert MUSS mit einem Punkt (.) enden.** <br/> |
   
    ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Wählen Sie **Add** aus.
    
    !["Add" auswählen](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Fügen Sie die anderen vier CNAME-Einträge hinzu.
    
    Erstellen Sie im Abschnitt **Custom resource records** einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut die Option **Add** aus, um diesen Eintrag abzuschließen. 
    
    Wiederholen Sie diesen Vorgang, bis Sie alle erforderlichen CNAME-Einträge erstellt haben.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern

> [!IMPORTANT]
> Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen, sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden. 
  
1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. Wählen Sie **Sign In** aus.
    
2. Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.
    
3. Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten. 
    
4. Wählen Sie im Abschnitt **Custom resource records** in der Zeile mit dem TXT-Eintrag die Option **Edit** aus. 
    
    > [!IMPORTANT]
    > Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message. 
  
    !["Edit" in der Zeile mit dem TXT-Eintrag auswählen](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Wählen Sie das Steuerelement **(+)** aus. 
    
    ![Pluszeichen auswählen](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    |**Daten**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           
   
   ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Wählen Sie **Save** aus.
    
    !["Save" auswählen](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
2. Wählen Sie **Sign In** aus.
    
3. Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.
    
4. Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten. 
    
5. Fügen Sie den ersten SRV-Eintrag hinzu.
    
    Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen. 
    
    (Möglicherweise müssen Sie nach unten scrollen.)
    
    (Wählen Sie in der Dropdownliste den Wert für **Type** aus.) 
    
    |**Name**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **Dieser Wert MUSS mit einem Punkt (.) enden.** **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **Dieser Wert MUSS mit einem Punkt (.) enden.**

    Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.       
   
    ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Wählen Sie **Add** aus.
    
    !["Add" auswählen](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Fügen Sie den anderen SRV-Eintrag hinzu.
    
    Erstellen Sie im Abschnitt **Custom resource records** einen Eintrag mit den Werten aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut die Option **Add** aus, um diesen Eintrag abzuschließen. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
