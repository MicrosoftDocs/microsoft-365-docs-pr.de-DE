---
title: Ändern von Namenservern zum Einrichten von Office 365 bei Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Erfahren Sie, wie Sie Ihre Office 365 benutzerdefinierte Domäne mit Namecheap einrichten, wenn Office 365 Ihre DNS-Einträge verwalten soll. '
ms.openlocfilehash: 1130f8aca0f2d014d73f5a1b2e2edb2785a7c6b8
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212317"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="18bbe-103">Ändern von Namenservern zum Einrichten von Office 365 bei Namecheap</span><span class="sxs-lookup"><span data-stu-id="18bbe-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="18bbe-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="18bbe-p101">[] Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei "Namecheap" selbst verwalten](create-dns-records-at-namecheap.md).)</span><span class="sxs-lookup"><span data-stu-id="18bbe-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="18bbe-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="18bbe-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="18bbe-p102">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in") und dann den Vorgang fortzusetzen ("Continue").</span><span class="sxs-lookup"><span data-stu-id="18bbe-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="18bbe-111">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="18bbe-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="18bbe-113">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="18bbe-115">Wählen Sie **Advanced DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="18bbe-117">Wählen Sie im Abschnitt **Host Einträge** die Option **neuen Datensatz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="18bbe-119">Wählen Sie in der Dropdownliste **Type** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18bbe-120">Die Dropdownliste **Typ** wird automatisch angezeigt, wenn Sie **neuen Datensatz hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="18bbe-122">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="18bbe-123">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="18bbe-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="18bbe-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="18bbe-124">**Type**</span></span>|<span data-ttu-id="18bbe-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="18bbe-125">**Host**</span></span>|<span data-ttu-id="18bbe-126">**Wert**</span><span class="sxs-lookup"><span data-stu-id="18bbe-126">**Value**</span></span>|<span data-ttu-id="18bbe-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="18bbe-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18bbe-128">TXT</span><span class="sxs-lookup"><span data-stu-id="18bbe-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="18bbe-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="18bbe-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="18bbe-130">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="18bbe-130">**Note**: This is an example.</span></span> <span data-ttu-id="18bbe-131">Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.</span><span class="sxs-lookup"><span data-stu-id="18bbe-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="18bbe-132">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="18bbe-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="18bbe-133">30 min</span><span class="sxs-lookup"><span data-stu-id="18bbe-133">30 min</span></span>  <br/> |
   
   ![NameCheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="18bbe-135">Wählen Sie das Kontrollkästchen **Änderungen speichern** (Häkchen) aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="18bbe-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="18bbe-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="18bbe-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="18bbe-139">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="18bbe-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="18bbe-140">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="18bbe-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="18bbe-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="18bbe-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="18bbe-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="18bbe-p104">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="18bbe-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="18bbe-147">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="18bbe-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="18bbe-p105">Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="18bbe-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="18bbe-p106">Wenn Sie die Namenservereinträge Ihrer Domäne so ändern, dass sie auf die Office 365-Namenserver verweisen, hat dies Auswirkungen auf alle Dienste, die aktuell mit Ihrer Domäne verbunden sind. So gehen beispielsweise alle an Ihre Domäne (z. B. an Bernd@ *Ihre_Domäne*  .com) gesendeten E-Mail-Nachrichten bei Office 365 ein, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="18bbe-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="18bbe-153">Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, werden  *nur*  die nachstehend aufgeführten vier Namenserver aufgelistet: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  Im folgenden Verfahren wird gezeigt, wie Sie andere, unerwünschte Namenserver aus der Liste löschen können, und Sie erfahren, wie Sie die  *richtigen*  Namenserver hinzufügen, wenn sie sich nicht bereits in der Liste befinden.</span><span class="sxs-lookup"><span data-stu-id="18bbe-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="18bbe-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in") und dann den Vorgang fortzusetzen ("Continue").</span><span class="sxs-lookup"><span data-stu-id="18bbe-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="18bbe-157">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="18bbe-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="18bbe-159">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="18bbe-161">Wählen Sie **Domäne**aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="18bbe-163">Suchen Sie den Abschnitt **NAMESERVERS**, und wählen Sie in der Dropdownliste **Namecheap Default** den Eintrag **Custom** aus.</span><span class="sxs-lookup"><span data-stu-id="18bbe-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="18bbe-165">Je nachdem, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, fahren Sie mit einem der beiden folgenden Verfahren fort.</span><span class="sxs-lookup"><span data-stu-id="18bbe-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="18bbe-166">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="18bbe-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="18bbe-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="18bbe-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="18bbe-168">Wählen Sie zweimal Namen **Server hinzufügen** aus, um zwei neue Zeilen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![NameCheap-BP-redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="18bbe-170">Geben Sie in den Feldern **Nameserver** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="18bbe-171">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="18bbe-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="18bbe-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="18bbe-173">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="18bbe-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="18bbe-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="18bbe-175">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="18bbe-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="18bbe-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="18bbe-177">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="18bbe-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="18bbe-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![NameCheap-BP-redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="18bbe-180">Aktivieren Sie das Kontrollkästchensteuerelement **Speichern** (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="18bbe-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="18bbe-p108">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="18bbe-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="18bbe-184">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="18bbe-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="18bbe-p109">Folgen Sie diesen Schritten  *nur*  , wenn es andere Namenserver als die vier  *korrekten*  Namenserver gibt. (Das heißt, löschen Sie  *nur*  andere als die vier korrekten Namenserver, also  *nicht* **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** oder **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="18bbe-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="18bbe-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="18bbe-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="18bbe-189">Wählen Sie zweimal Namen **Server hinzufügen** aus, um zwei neue Zeilen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![NameCheap-BP-redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="18bbe-191">Geben Sie in den Feldern **Nameserver** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="18bbe-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="18bbe-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="18bbe-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="18bbe-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="18bbe-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="18bbe-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="18bbe-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="18bbe-196">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="18bbe-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="18bbe-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="18bbe-198">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="18bbe-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="18bbe-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="18bbe-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![NameCheap-BP-redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="18bbe-201">Aktivieren Sie das Kontrollkästchensteuerelement **Speichern** (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="18bbe-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="18bbe-p110">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="18bbe-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
