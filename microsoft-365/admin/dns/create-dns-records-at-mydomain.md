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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei My Domain für Microsoft einrichten.
ms.openlocfilehash: 1c6edc1e3ad03b0467c70741d4097cf3a3b5e196
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400412"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a><span data-ttu-id="b427e-103">Erstellen von DNS-Einträgen für Microsoft bei MyDomain</span><span class="sxs-lookup"><span data-stu-id="b427e-103">Create DNS records at MyDomain for Microsoft</span></span>


  
 <span data-ttu-id="b427e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b427e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b427e-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="b427e-105">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="b427e-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="b427e-106">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="b427e-107">Wenn Sie sich trotz der Diensteinschränkungen dafür entscheiden, Ihre eigenen Microsoft-DNS-Einträge bei MyDomain zu verwalten, führen Sie die Schritte in diesem Artikel aus, um die DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b427e-107">If you choose to manage your own Microsoft DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="b427e-108">Nachdem Sie diese Einträge bei MyDomain hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b427e-108">After you add these records at MyDomain, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="b427e-109">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b427e-109">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b427e-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b427e-110">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b427e-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b427e-111">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b427e-112">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b427e-112">Add a TXT record for verification</span></span>
<span data-ttu-id="b427e-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b427e-113"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b427e-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="b427e-114">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b427e-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="b427e-115">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b427e-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="b427e-116">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="b427e-117">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="b427e-117">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b427e-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="b427e-118">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="b427e-119">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="b427e-119">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b427e-120">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-120">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="b427e-121">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b427e-121">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="b427e-122">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-122">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="b427e-123">Wählen Sie in der Dropdownliste **Modify** den Eintrag **TXT/SPF Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-123">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="b427e-124">Geben Sie unter **Content** im Feld für den neuen Eintrag den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b427e-124">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="b427e-125">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="b427e-125">**Content**</span></span> <br/> |
    |<span data-ttu-id="b427e-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b427e-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b427e-127">**Note:** This is an example.</span><span class="sxs-lookup"><span data-stu-id="b427e-127">**Note:** This is an example.</span></span> <span data-ttu-id="b427e-128">Use your specific **Destination or Points to Address** value here, from the table.</span><span class="sxs-lookup"><span data-stu-id="b427e-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b427e-129">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="b427e-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b427e-130">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b427e-130">Select **Add**.</span></span>
    
8. <span data-ttu-id="b427e-131">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b427e-131">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b427e-132">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="b427e-132">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b427e-133">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b427e-133">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b427e-134">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="b427e-134">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b427e-135">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-135">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b427e-136">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-136">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b427e-137">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-137">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b427e-138">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b427e-138">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b427e-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b427e-139">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b427e-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b427e-140">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b427e-141">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b427e-141">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b427e-142"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b427e-142"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b427e-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="b427e-143">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="b427e-144">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="b427e-144">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b427e-145">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-145">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="b427e-146">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b427e-146">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="b427e-147">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-147">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="b427e-148">Wählen Sie in der Dropdownliste **Modify** den Eintrag **MX Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-148">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="b427e-150">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b427e-150">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="b427e-151">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b427e-151">**Priority**</span></span>|<span data-ttu-id="b427e-152">**Host**</span><span class="sxs-lookup"><span data-stu-id="b427e-152">**Host**</span></span>|<span data-ttu-id="b427e-153">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="b427e-153">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b427e-154">0</span><span class="sxs-lookup"><span data-stu-id="b427e-154">0</span></span>  <br/> <span data-ttu-id="b427e-155">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="b427e-155">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |@  <br/> | <span data-ttu-id="b427e-156">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b427e-156">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b427e-157">**Hinweis:** Erhalten Sie Ihren \<*domain-key*\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="b427e-157">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span><span data-ttu-id="b427e-158"> > [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="b427e-158"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="b427e-160">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b427e-160">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="b427e-162">Wenn andere MX-Einträge vorhanden sind, entfernen Sie diese, indem Sie **Remove** in der Spalte **Action** der einzelnen Einträge auswählen.</span><span class="sxs-lookup"><span data-stu-id="b427e-162">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="b427e-164">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-164">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b427e-166">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b427e-166">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b427e-167"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b427e-167"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b427e-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="b427e-168">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="b427e-169">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="b427e-169">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b427e-170">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-170">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="b427e-171">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b427e-171">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="b427e-172">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-172">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="b427e-173">Wählen Sie in der Dropdownliste **Modify** den Eintrag **CNAME Alias** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-173">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="b427e-175">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="b427e-175">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="b427e-176">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b427e-176">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="b427e-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="b427e-177">**Host**</span></span>|<span data-ttu-id="b427e-178">**Points To:**</span><span class="sxs-lookup"><span data-stu-id="b427e-178">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b427e-179">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b427e-179">autodiscover</span></span>  <br/> |<span data-ttu-id="b427e-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b427e-180">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b427e-181">sip</span><span class="sxs-lookup"><span data-stu-id="b427e-181">sip</span></span>  <br/> |<span data-ttu-id="b427e-182">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b427e-182">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b427e-183">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b427e-183">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b427e-184">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b427e-184">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b427e-185">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b427e-185">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b427e-186">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b427e-186">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b427e-187">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b427e-187">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b427e-188">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b427e-188">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="b427e-190">Wählen Sie **Hinzufügen** aus, um den ersten Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b427e-190">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="b427e-192">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="b427e-192">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="b427e-193">Verwenden Sie die Werte aus der zweiten Zeile der obigen Tabelle, und wählen Sie dann **Hinzufügen** aus, um den zweiten Eintrag hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b427e-193">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="b427e-194">Fügen Sie die übrigen Einträge auf gleiche Weise hinzu. Verwenden Sie dabei die Werte aus der dritten, vierten, fünften und sechsten Zeile der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b427e-194">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b427e-195">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b427e-195">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b427e-196"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b427e-196"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b427e-197">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="b427e-197">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b427e-198">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="b427e-198">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b427e-199">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="b427e-199">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b427e-200">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b427e-200">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="b427e-201">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="b427e-201">Need examples?</span></span> <span data-ttu-id="b427e-202">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="b427e-202">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="b427e-203">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b427e-203">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="b427e-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="b427e-204">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="b427e-205">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="b427e-205">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b427e-206">Wählen Sie im Abschnitt **Meine Favorien** die Option **Domain Central** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-206">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="b427e-207">Wählen Sie unter **Domain** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b427e-207">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="b427e-208">Wählen Sie in der Zeile **Overview** die Option **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-208">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="b427e-209">Wählen Sie in der Dropdownliste **Modify** den Eintrag **TXT/SPF Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b427e-209">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="b427e-211">Geben Sie unter **Content** im Feld für den neuen Eintrag den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b427e-211">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="b427e-212">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="b427e-212">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="b427e-213">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b427e-213">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b427e-214">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="b427e-214">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="b427e-216">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b427e-216">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b427e-218">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="b427e-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b427e-219"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b427e-219"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="b427e-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span><span class="sxs-lookup"><span data-stu-id="b427e-220">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work.</span></span> <span data-ttu-id="b427e-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span><span class="sxs-lookup"><span data-stu-id="b427e-221">No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b427e-222">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b427e-222">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b427e-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b427e-223">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b427e-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b427e-224">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
