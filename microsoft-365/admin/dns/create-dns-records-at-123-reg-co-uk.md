---
title: Erstellen von DNS-Einträgen bei 123-reg.co.uk für Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter 123-reg.co.uk für Office 365 einrichten.
ms.openlocfilehash: 327f55dcedfda6eef31d56af1833a5c5438af2a6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351376"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a><span data-ttu-id="80a80-103">Erstellen von DNS-Einträgen bei 123-reg.co.uk für Office 365</span><span class="sxs-lookup"><span data-stu-id="80a80-103">Create DNS records at 123-reg.co.uk for Office 365</span></span>

 <span data-ttu-id="80a80-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="80a80-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="80a80-105">Wenn 123-reg.co.uk Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="80a80-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="80a80-106">Nachdem Sie diese Einträge bei 123-reg.co.uk hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="80a80-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="80a80-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="80a80-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="80a80-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="80a80-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="80a80-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="80a80-111">Add a TXT record for verification</span></span>
<span data-ttu-id="80a80-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="80a80-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="80a80-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="80a80-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80a80-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="80a80-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="80a80-117">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk.</span><span class="sxs-lookup"><span data-stu-id="80a80-117">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="80a80-118">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="80a80-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="80a80-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="80a80-119">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="80a80-120">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="80a80-120">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="80a80-121">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-121">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="80a80-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80a80-122">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80a80-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80a80-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="80a80-124">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="80a80-124">**Hostname**</span></span> <br/> |<span data-ttu-id="80a80-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="80a80-125">**Type**</span></span> <br/> |<span data-ttu-id="80a80-126">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="80a80-126">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="80a80-127">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="80a80-127">TXT/SPF</span></span>  <br/> |<span data-ttu-id="80a80-128">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="80a80-128">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="80a80-p105">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="80a80-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
6. <span data-ttu-id="80a80-132">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80a80-132">Select **Add**.</span></span>
    
7. <span data-ttu-id="80a80-133">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="80a80-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="80a80-134">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="80a80-134">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="80a80-135">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="80a80-135">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="80a80-136">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="80a80-136">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="80a80-137">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="80a80-138">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-138">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="80a80-139">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-139">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80a80-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="80a80-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="80a80-143">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="80a80-143">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="80a80-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="80a80-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="80a80-p107">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="80a80-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="80a80-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="80a80-147">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="80a80-148">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="80a80-148">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="80a80-149">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-149">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="80a80-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80a80-150">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80a80-151">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80a80-151">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="80a80-152">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="80a80-152">**Hostname**</span></span>|<span data-ttu-id="80a80-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="80a80-153">**Type**</span></span>|<span data-ttu-id="80a80-154">**Priority**</span><span class="sxs-lookup"><span data-stu-id="80a80-154">**Priority**</span></span>|<span data-ttu-id="80a80-155">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="80a80-155">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="80a80-156">MX</span><span class="sxs-lookup"><span data-stu-id="80a80-156">MX</span></span>  <br/> |<span data-ttu-id="80a80-157">1</span><span class="sxs-lookup"><span data-stu-id="80a80-157">1</span></span>  <br/> <span data-ttu-id="80a80-158">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="80a80-158">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="80a80-159">*\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-159">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="80a80-160">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-160">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="80a80-161">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<domain-key\>) aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="80a80-161">**Note:** Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="80a80-162">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="80a80-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen von Werten aus der Tabelle](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="80a80-164">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80a80-164">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="80a80-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span><span class="sxs-lookup"><span data-stu-id="80a80-166">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Wählen Sie löschen (das Papierkorbsymbol)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="80a80-168">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="80a80-168">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="80a80-169"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="80a80-169"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="80a80-p109">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="80a80-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="80a80-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="80a80-172">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="80a80-173">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="80a80-173">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="80a80-174">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-174">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="80a80-175">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="80a80-175">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="80a80-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80a80-176">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80a80-177">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80a80-177">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="80a80-178">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="80a80-178">**Hostname**</span></span>|<span data-ttu-id="80a80-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="80a80-179">**Type**</span></span>|<span data-ttu-id="80a80-180">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="80a80-180">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="80a80-181">autodiscover</span><span class="sxs-lookup"><span data-stu-id="80a80-181">autodiscover</span></span>  <br/> |<span data-ttu-id="80a80-182">CNAME</span><span class="sxs-lookup"><span data-stu-id="80a80-182">CNAME</span></span>  <br/> |<span data-ttu-id="80a80-183">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-183">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="80a80-184">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-184">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80a80-185">sip</span><span class="sxs-lookup"><span data-stu-id="80a80-185">sip</span></span>  <br/> |<span data-ttu-id="80a80-186">CNAME</span><span class="sxs-lookup"><span data-stu-id="80a80-186">CNAME</span></span>  <br/> |<span data-ttu-id="80a80-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-187">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="80a80-188">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-188">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80a80-189">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="80a80-189">lyncdiscover</span></span>  <br/> |<span data-ttu-id="80a80-190">CNAME</span><span class="sxs-lookup"><span data-stu-id="80a80-190">CNAME</span></span>  <br/> |<span data-ttu-id="80a80-191">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-191">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="80a80-192">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-192">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80a80-193">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="80a80-193">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="80a80-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="80a80-194">CNAME</span></span>  <br/> |<span data-ttu-id="80a80-195">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="80a80-195">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="80a80-196">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-196">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="80a80-197">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="80a80-197">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="80a80-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="80a80-198">CNAME</span></span>  <br/> |<span data-ttu-id="80a80-199">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-199">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="80a80-200">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-200">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="80a80-202">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80a80-202">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="80a80-204">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="80a80-204">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="80a80-205">Erstellen Sie im Abschnitt **Advanced DNS** einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="80a80-205">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="80a80-206">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="80a80-206">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="80a80-207">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="80a80-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="80a80-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="80a80-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="80a80-209">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="80a80-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="80a80-210">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="80a80-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="80a80-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="80a80-211">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="80a80-212">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="80a80-212">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="80a80-213">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="80a80-213">Need examples?</span></span> <span data-ttu-id="80a80-214">Schauen Sie sich diese [Details und SPF-Beispieleinträge](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords) an.</span><span class="sxs-lookup"><span data-stu-id="80a80-214">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="80a80-215">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="80a80-215">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="80a80-216">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk.</span><span class="sxs-lookup"><span data-stu-id="80a80-216">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="80a80-217">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="80a80-217">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="80a80-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="80a80-218">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="80a80-219">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="80a80-219">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="80a80-220">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-220">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="80a80-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80a80-221">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80a80-222">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80a80-222">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="80a80-223">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="80a80-223">**Hostname**</span></span>|<span data-ttu-id="80a80-224">**Type**</span><span class="sxs-lookup"><span data-stu-id="80a80-224">**Type**</span></span>|<span data-ttu-id="80a80-225">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="80a80-225">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="80a80-226">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="80a80-226">TXT/SPF</span></span>  <br/> |<span data-ttu-id="80a80-227">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="80a80-227">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="80a80-228">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="80a80-228">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123reg wußte-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="80a80-230">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80a80-230">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="80a80-232">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="80a80-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="80a80-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="80a80-233"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="80a80-p112">Navigieren Sie im ersten Schritt über [diesen Link](https://www.123-reg.co.uk/secure/cpanel/domain/overview) zu Ihrer Domänenseite bei 123-reg.co.uk. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="80a80-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="80a80-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="80a80-236">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="80a80-237">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="80a80-237">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="80a80-238">Wählen Sie auf der Seite **Manage Your DNS** die Registerkarte **Advanced DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="80a80-238">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="80a80-239">Fügen Sie den ersten der zwei SRV-Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="80a80-239">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="80a80-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="80a80-240">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="80a80-241">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="80a80-241">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="80a80-242">Hostname</span><span class="sxs-lookup"><span data-stu-id="80a80-242">Hostname</span></span>|<span data-ttu-id="80a80-243">Type</span><span class="sxs-lookup"><span data-stu-id="80a80-243">Type</span></span>|<span data-ttu-id="80a80-244">Priority</span><span class="sxs-lookup"><span data-stu-id="80a80-244">Priority</span></span>|<span data-ttu-id="80a80-245">TTL</span><span class="sxs-lookup"><span data-stu-id="80a80-245">TTL</span></span>|<span data-ttu-id="80a80-246">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="80a80-246">Destination SRV</span></span>|
    |<span data-ttu-id="80a80-247">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="80a80-247">_sip._tls</span></span>|<span data-ttu-id="80a80-248">SRV</span><span class="sxs-lookup"><span data-stu-id="80a80-248">SRV</span></span>|<span data-ttu-id="80a80-249">100</span><span class="sxs-lookup"><span data-stu-id="80a80-249">100</span></span>|<span data-ttu-id="80a80-250">3600</span><span class="sxs-lookup"><span data-stu-id="80a80-250">3600</span></span>|<span data-ttu-id="80a80-251">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-251">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="80a80-252">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-252">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="80a80-253">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="80a80-253">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="80a80-254">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="80a80-254">_sipfederationtls._tcp</span></span>|<span data-ttu-id="80a80-255">SRV</span><span class="sxs-lookup"><span data-stu-id="80a80-255">SRV</span></span>|<span data-ttu-id="80a80-256">100</span><span class="sxs-lookup"><span data-stu-id="80a80-256">100</span></span>|<span data-ttu-id="80a80-257">3600</span><span class="sxs-lookup"><span data-stu-id="80a80-257">3600</span></span>|<span data-ttu-id="80a80-258">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="80a80-258">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="80a80-259">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="80a80-259">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="80a80-260">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="80a80-260">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="80a80-262">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80a80-262">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="80a80-264">Fügen Sie den anderen SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="80a80-264">To add the other SRV record:</span></span>
    
    <span data-ttu-id="80a80-265">Erstellen Sie im Abschnitt **Advanced DNS** einen Datensatz unter Verwendung der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="80a80-265">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="80a80-p115">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="80a80-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
