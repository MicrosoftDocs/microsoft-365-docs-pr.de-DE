---
title: Erstellen von DNS-Einträgen für Office 365 bei MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei My Domain für Office 365 einrichten.
ms.openlocfilehash: 1a75c2ab0077cac07781e5102c43e53ed965b1df
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211691"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="4a848-103">Erstellen von DNS-Einträgen für Office 365 bei MyDomain</span><span class="sxs-lookup"><span data-stu-id="4a848-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="4a848-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="4a848-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="4a848-p101">Die MyDomain-Website unterstützt keine SRV-Einträge. Das bedeutet, dass mehrere Features von Skype for Business Online und Outlook Web App nicht funktionieren. Unabhängig vom verwendeten Office 365-Plan bestehen bei der Verwaltung Ihrer DNS-Einträge bei MyDomain [erhebliche Diensteinschränkungen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), und Sie sollten möglicherweise zu einem anderen DNS-Hostinganbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="4a848-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="4a848-107">Wenn Sie sich trotz der Diensteinschränkungen dafür entscheiden, Ihre eigenen DNS-Einträge für Office 365 bei MyDomain zu verwalten, führen Sie die Schritte in diesem Artikel aus, um die DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4a848-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="4a848-108">Nachdem Sie diese Einträge bei MyDomain hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4a848-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="4a848-109">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="4a848-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a848-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a848-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4a848-113">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="4a848-113">Add a TXT record for verification</span></span>
<span data-ttu-id="4a848-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4a848-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4a848-p103">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="4a848-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a848-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="4a848-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4a848-p105">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a848-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a848-121">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="4a848-122">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a848-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="4a848-123">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="4a848-124">Wählen Sie in der Dropdownliste **Modify** den Eintrag **TXT/SPF Record** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="4a848-125">Geben Sie unter **Content** im Feld für den neuen Eintrag den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a848-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="4a848-126">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="4a848-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="4a848-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4a848-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4a848-p106">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="4a848-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="4a848-131">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a848-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="4a848-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a848-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4a848-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4a848-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4a848-134">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="4a848-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4a848-135">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="4a848-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="4a848-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="4a848-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="4a848-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4a848-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a848-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="4a848-142">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="4a848-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="4a848-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4a848-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4a848-p108">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a848-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a848-146">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="4a848-147">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a848-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="4a848-148">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="4a848-149">Wählen Sie in der Dropdownliste **Modify** den Eintrag **MX Record** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="4a848-151">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a848-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="4a848-152">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4a848-152">**Priority**</span></span>|<span data-ttu-id="4a848-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a848-153">**Host**</span></span>|<span data-ttu-id="4a848-154">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="4a848-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4a848-155">0</span><span class="sxs-lookup"><span data-stu-id="4a848-155">0</span></span>  <br/> <span data-ttu-id="4a848-156">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a848-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="4a848-157">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a848-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4a848-158">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="4a848-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="4a848-159"> > [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="4a848-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="4a848-161">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a848-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="4a848-163">Wenn andere MX-Einträge vorhanden sind, entfernen Sie diese, indem Sie **Remove** in der Spalte **Action** der einzelnen Einträge auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a848-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="4a848-165">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="4a848-167">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="4a848-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="4a848-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4a848-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4a848-p110">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a848-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a848-171">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="4a848-172">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a848-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="4a848-173">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="4a848-174">Wählen Sie in der Dropdownliste **Modify** den Eintrag **CNAME Alias** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="4a848-176">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a848-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="4a848-177">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a848-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="4a848-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a848-178">**Host**</span></span>|<span data-ttu-id="4a848-179">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="4a848-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4a848-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4a848-180">autodiscover</span></span>  <br/> |<span data-ttu-id="4a848-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a848-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="4a848-182">sip</span><span class="sxs-lookup"><span data-stu-id="4a848-182">sip</span></span>  <br/> |<span data-ttu-id="4a848-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a848-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4a848-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4a848-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4a848-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a848-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4a848-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4a848-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4a848-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4a848-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="4a848-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4a848-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4a848-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4a848-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="4a848-191">Wählen Sie **Hinzufügen** aus, um den ersten Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4a848-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="4a848-193">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a848-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="4a848-194">Verwenden Sie die Werte aus der zweiten Zeile der obigen Tabelle, und wählen Sie dann **Hinzufügen** aus, um den zweiten Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4a848-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="4a848-195">Fügen Sie die übrigen Einträge auf gleiche Weise hinzu. Verwenden Sie dabei die Werte aus der dritten, vierten, fünften und sechsten Zeile der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4a848-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4a848-196">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="4a848-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4a848-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4a848-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a848-198">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="4a848-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4a848-199">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="4a848-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4a848-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a848-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4a848-201">Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4a848-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="4a848-202">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="4a848-202">Need examples?</span></span> <span data-ttu-id="4a848-203">Schauen Sie sich diese [Details und SPF-Beispieleinträge](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords) an.</span><span class="sxs-lookup"><span data-stu-id="4a848-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="4a848-204">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a848-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="4a848-p112">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a848-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="4a848-207">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="4a848-208">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a848-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="4a848-209">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="4a848-210">Wählen Sie in der Dropdownliste **Modify** den Eintrag **TXT/SPF Record** aus.</span><span class="sxs-lookup"><span data-stu-id="4a848-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="4a848-212">Geben Sie unter **Content** im Feld für den neuen Eintrag den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a848-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="4a848-213">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="4a848-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="4a848-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4a848-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4a848-215">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4a848-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="4a848-217">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a848-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="4a848-219">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="4a848-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="4a848-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4a848-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="4a848-p113">Die MyDomain-Website unterstützt keine SRV-Einträge. Das bedeutet, dass mehrere Features von Skype for Business Online und Outlook Web App nicht funktionieren. Unabhängig vom verwendeten Office 365-Plan bestehen bei der Verwaltung Ihrer DNS-Einträge bei MyDomain [erhebliche Diensteinschränkungen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), und Sie sollten möglicherweise zu einem anderen DNS-Hostinganbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="4a848-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4a848-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a848-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
