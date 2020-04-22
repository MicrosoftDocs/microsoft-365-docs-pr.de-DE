---
title: Erstellen von DNS-Einträgen für Microsoft bei MyDomain
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei My Domain für Microsoft einrichten.
ms.openlocfilehash: 4f26da1e1e148307cd2b5cdf9aeed97c610ec8dd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629431"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="abe8d-103">Erstellen von DNS-Einträgen für Microsoft bei MyDomain</span><span class="sxs-lookup"><span data-stu-id="abe8d-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="abe8d-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="abe8d-p101">Die MyDomain-Website unterstützt keine SRV-Einträge. Das bedeutet, dass mehrere Features von Skype for Business Online und Outlook Web App nicht funktionieren. Unabhängig vom verwendeten Microsoft-Plan bestehen bei der Verwaltung Ihrer DNS-Einträge bei MyDomain [erhebliche Diensteinschränkungen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), und Sie sollten möglicherweise zu einem anderen DNS-Hostinganbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="abe8d-107">Wenn Sie sich trotz der Diensteinschränkungen dafür entscheiden, Ihre eigenen Microsoft-DNS-Einträge bei MyDomain zu verwalten, führen Sie die Schritte in diesem Artikel aus, um die DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="abe8d-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="abe8d-108">Nachdem Sie diese Einträge bei MyDomain hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="abe8d-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="abe8d-109">Informationen zu Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="abe8d-109">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe8d-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="abe8d-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="abe8d-113">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="abe8d-113">Add a TXT record for verification</span></span>
<span data-ttu-id="abe8d-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="abe8d-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="abe8d-p103">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="abe8d-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="abe8d-p105">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="abe8d-121">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="abe8d-122">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="abe8d-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="abe8d-123">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="abe8d-124">Wählen Sie in der Dropdownliste **Modify** den Eintrag **TXT/SPF Record** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="abe8d-125">Geben Sie unter **Content** im Feld für den neuen Eintrag den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="abe8d-126">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="abe8d-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="abe8d-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="abe8d-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="abe8d-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="abe8d-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="abe8d-131">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="abe8d-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="abe8d-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="abe8d-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="abe8d-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="abe8d-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="abe8d-134">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="abe8d-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="abe8d-135">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="abe8d-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="abe8d-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="abe8d-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="abe8d-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="abe8d-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="abe8d-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="abe8d-142">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="abe8d-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="abe8d-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="abe8d-p108">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="abe8d-146">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="abe8d-147">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="abe8d-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="abe8d-148">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="abe8d-149">Wählen Sie in der Dropdownliste **Modify** den Eintrag **MX Record** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="abe8d-151">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="abe8d-152">**Priority**</span><span class="sxs-lookup"><span data-stu-id="abe8d-152">**Priority**</span></span>|<span data-ttu-id="abe8d-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="abe8d-153">**Host**</span></span>|<span data-ttu-id="abe8d-154">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="abe8d-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="abe8d-155">0</span><span class="sxs-lookup"><span data-stu-id="abe8d-155">0</span></span>  <br/> <span data-ttu-id="abe8d-156">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="abe8d-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="abe8d-157">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="abe8d-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="abe8d-158">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="abe8d-158">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="abe8d-159"> > [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="abe8d-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="abe8d-161">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="abe8d-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="abe8d-163">Wenn andere MX-Einträge vorhanden sind, entfernen Sie diese, indem Sie **Remove** in der Spalte **Action** der einzelnen Einträge auswählen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="abe8d-165">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="abe8d-167">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="abe8d-167">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="abe8d-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="abe8d-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="abe8d-p110">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="abe8d-171">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="abe8d-172">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="abe8d-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="abe8d-173">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="abe8d-174">Wählen Sie in der Dropdownliste **Modify** den Eintrag **CNAME Alias** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="abe8d-176">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="abe8d-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="abe8d-177">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="abe8d-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="abe8d-178">**Host**</span></span>|<span data-ttu-id="abe8d-179">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="abe8d-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="abe8d-180">autodiscover</span><span class="sxs-lookup"><span data-stu-id="abe8d-180">autodiscover</span></span>  <br/> |<span data-ttu-id="abe8d-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="abe8d-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="abe8d-182">sip</span><span class="sxs-lookup"><span data-stu-id="abe8d-182">sip</span></span>  <br/> |<span data-ttu-id="abe8d-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="abe8d-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="abe8d-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="abe8d-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="abe8d-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="abe8d-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="abe8d-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="abe8d-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="abe8d-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="abe8d-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="abe8d-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="abe8d-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="abe8d-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="abe8d-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="abe8d-191">Wählen Sie **Hinzufügen** aus, um den ersten Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="abe8d-193">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="abe8d-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="abe8d-194">Verwenden Sie die Werte aus der zweiten Zeile der obigen Tabelle, und wählen Sie dann **Hinzufügen** aus, um den zweiten Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="abe8d-195">Fügen Sie die übrigen Einträge auf gleiche Weise hinzu. Verwenden Sie dabei die Werte aus der dritten, vierten, fünften und sechsten Zeile der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="abe8d-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="abe8d-196">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="abe8d-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="abe8d-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="abe8d-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="abe8d-198">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="abe8d-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="abe8d-199">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="abe8d-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="abe8d-200">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="abe8d-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="abe8d-201">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="abe8d-201">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="abe8d-202">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="abe8d-202">Need examples?</span></span> <span data-ttu-id="abe8d-203">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="abe8d-203">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="abe8d-204">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="abe8d-p112">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="abe8d-207">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="abe8d-208">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="abe8d-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="abe8d-209">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="abe8d-210">Wählen Sie in der Dropdownliste **Modify** den Eintrag **TXT/SPF Record** aus.</span><span class="sxs-lookup"><span data-stu-id="abe8d-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="abe8d-212">Geben Sie unter **Content** im Feld für den neuen Eintrag den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="abe8d-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="abe8d-213">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="abe8d-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="abe8d-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="abe8d-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="abe8d-215">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="abe8d-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="abe8d-217">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="abe8d-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="abe8d-219">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="abe8d-219">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="abe8d-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="abe8d-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="abe8d-p113">Die MyDomain-Website unterstützt keine SRV-Einträge. Das bedeutet, dass mehrere Features von Skype for Business Online und Outlook Web App nicht funktionieren. Unabhängig vom verwendeten Microsoft-Plan bestehen bei der Verwaltung Ihrer DNS-Einträge bei MyDomain [erhebliche Diensteinschränkungen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), und Sie sollten möglicherweise zu einem anderen DNS-Hostinganbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="abe8d-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="abe8d-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="abe8d-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
