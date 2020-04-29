---
title: Erstellen von DNS-Einträgen bei Bluehost für Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste auf Bluehost für Microsoft einrichten.
ms.openlocfilehash: 1608aebdf984e22e45d7a2469acb0a8002fca2a1
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919551"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="0360e-103">Erstellen von DNS-Einträgen bei Bluehost für Microsoft</span><span class="sxs-lookup"><span data-stu-id="0360e-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="0360e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="0360e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0360e-105">Wenn Bluehost Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="0360e-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0360e-106">Nachdem Sie diese Einträge bei Bluehost hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="0360e-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="0360e-107">Informationen zu Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="0360e-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0360e-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0360e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="0360e-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="0360e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="0360e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0360e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0360e-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="0360e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0360e-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="0360e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="0360e-117">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="0360e-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="0360e-118">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="0360e-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0360e-119">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="0360e-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="0360e-120">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="0360e-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="0360e-121">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="0360e-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0360e-122">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0360e-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0360e-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0360e-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="0360e-124">**Host Record**</span></span> <br/> |<span data-ttu-id="0360e-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0360e-125">**TTL**</span></span> <br/> |<span data-ttu-id="0360e-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="0360e-126">**Type**</span></span> <br/> |<span data-ttu-id="0360e-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="0360e-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0360e-128">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-128">14400</span></span>  <br/> |<span data-ttu-id="0360e-129">TXT</span><span class="sxs-lookup"><span data-stu-id="0360e-129">TXT</span></span>  <br/> |<span data-ttu-id="0360e-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0360e-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0360e-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="0360e-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
5. <span data-ttu-id="0360e-134">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="0360e-135">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0360e-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0360e-136">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="0360e-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="0360e-137">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="0360e-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0360e-138">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="0360e-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="0360e-139">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0360e-140">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0360e-141">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0360e-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0360e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="0360e-145">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0360e-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="0360e-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0360e-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="0360e-147">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="0360e-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="0360e-148">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="0360e-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0360e-149">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="0360e-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="0360e-150">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="0360e-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="0360e-151">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="0360e-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0360e-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0360e-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0360e-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0360e-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="0360e-154">**Host Record**</span></span>|<span data-ttu-id="0360e-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0360e-155">**TTL**</span></span>|<span data-ttu-id="0360e-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="0360e-156">**Type**</span></span>|<span data-ttu-id="0360e-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="0360e-157">**Points To**</span></span>|<span data-ttu-id="0360e-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="0360e-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0360e-159">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-159">14400</span></span>  <br/> |<span data-ttu-id="0360e-160">MX</span><span class="sxs-lookup"><span data-stu-id="0360e-160">MX</span></span>  <br/> | <span data-ttu-id="0360e-161">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0360e-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="0360e-162">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="0360e-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="0360e-163">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="0360e-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="0360e-164">0</span><span class="sxs-lookup"><span data-stu-id="0360e-164">0</span></span>  <br/> <span data-ttu-id="0360e-165">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="0360e-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Wählen Sie in der Dropdownliste Typ aus.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="0360e-167">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-167">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="0360e-169">Wenn im Abschnitt **MX (Mail Exchanger)** weitere MX-Einträge vorhanden sind, löschen Sie die einzelnen Einträge.</span><span class="sxs-lookup"><span data-stu-id="0360e-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="0360e-170">Wählen Sie für einen der anderen MX-Einträge die Option **Löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="0360e-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Wählen Sie DELETE für jeden zusätzlichen MX-Eintrag aus.](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="0360e-172">Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Wählen Sie OK aus.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="0360e-174">Gehen Sie entsprechend vor, um alle weiteren bereits aufgeführten MX-Einträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0360e-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="0360e-175">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="0360e-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="0360e-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0360e-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="0360e-177">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="0360e-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="0360e-178">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="0360e-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0360e-179">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="0360e-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="0360e-180">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="0360e-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="0360e-181">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="0360e-182">Suchen Sie im Abschnitt **a (Host)** Records nach der Zeile für den **Auto Ermittlungs** Eintrag, und wählen Sie dann **Löschen** für diese Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0360e-183">Sie müssen den vorhandenen **Auto Ermittlungs** Daten Satz löschen, *bevor* Sie den von Microsoft benötigten **Auto Ermittlungs** Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0360e-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="0360e-184">Bluehost gestattet Ihnen nicht, zwei **AutoErmittlung** seinträge gleichzeitig zu pflegen.</span><span class="sxs-lookup"><span data-stu-id="0360e-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Wählen Sie löschen aus.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="0360e-186">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-186">Select **OK**.</span></span>
    
    ![Wählen Sie OK aus.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="0360e-188">Erstellen Sie den ersten der sechs CNAME-Einträge.</span><span class="sxs-lookup"><span data-stu-id="0360e-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="0360e-189">Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="0360e-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="0360e-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0360e-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0360e-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="0360e-191">**Host Record**</span></span>|<span data-ttu-id="0360e-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0360e-192">**TTL**</span></span>|<span data-ttu-id="0360e-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="0360e-193">**Type**</span></span>|<span data-ttu-id="0360e-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="0360e-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0360e-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0360e-195">autodiscover</span></span>  <br/> |<span data-ttu-id="0360e-196">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-196">14400</span></span>  <br/> |<span data-ttu-id="0360e-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="0360e-197">CNAME</span></span>  <br/> |<span data-ttu-id="0360e-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0360e-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="0360e-199">sip</span><span class="sxs-lookup"><span data-stu-id="0360e-199">sip</span></span>  <br/> |<span data-ttu-id="0360e-200">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-200">14400</span></span>  <br/> |<span data-ttu-id="0360e-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="0360e-201">CNAME</span></span>  <br/> |<span data-ttu-id="0360e-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0360e-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0360e-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0360e-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0360e-204">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-204">14400</span></span>  <br/> |<span data-ttu-id="0360e-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="0360e-205">CNAME</span></span>  <br/> |<span data-ttu-id="0360e-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0360e-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0360e-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0360e-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0360e-208">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-208">14400</span></span>  <br/> |<span data-ttu-id="0360e-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="0360e-209">CNAME</span></span>  <br/> |<span data-ttu-id="0360e-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0360e-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="0360e-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0360e-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0360e-212">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-212">14400</span></span>  <br/> |<span data-ttu-id="0360e-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="0360e-213">CNAME</span></span>  <br/> |<span data-ttu-id="0360e-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0360e-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Erstellen des ersten CNAME-Eintrags](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="0360e-216">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-216">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="0360e-218">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="0360e-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="0360e-219">Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der nächsten Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0360e-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="0360e-220">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0360e-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0360e-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="0360e-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0360e-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0360e-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0360e-223">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="0360e-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0360e-224">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="0360e-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0360e-225">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="0360e-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="0360e-226">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="0360e-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="0360e-227">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="0360e-227">Need examples?</span></span> <span data-ttu-id="0360e-228">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="0360e-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="0360e-229">Zum Überprüfen des SPF-Eintrags können Sie eines dieser[SPF-Überprüfungstools](../setup/domains-faq.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="0360e-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="0360e-230">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="0360e-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="0360e-231">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="0360e-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0360e-232">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="0360e-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="0360e-233">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="0360e-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="0360e-234">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="0360e-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="0360e-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="0360e-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0360e-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="0360e-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="0360e-237">**Host Record**</span></span>|<span data-ttu-id="0360e-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0360e-238">**TTL**</span></span>|<span data-ttu-id="0360e-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="0360e-239">**Type**</span></span>|<span data-ttu-id="0360e-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="0360e-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0360e-241">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-241">14400</span></span>  <br/> |<span data-ttu-id="0360e-242">TXT</span><span class="sxs-lookup"><span data-stu-id="0360e-242">TXT</span></span>  <br/> |<span data-ttu-id="0360e-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0360e-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="0360e-244">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="0360e-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopieren des txt-Werts](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="0360e-246">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-246">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="0360e-248">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="0360e-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="0360e-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0360e-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="0360e-250">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="0360e-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="0360e-251">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="0360e-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="0360e-252">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="0360e-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="0360e-253">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="0360e-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="0360e-254">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="0360e-255">Erstellen Sie den ersten der zwei SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="0360e-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="0360e-256">Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="0360e-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="0360e-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="0360e-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0360e-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="0360e-258">**Service**</span></span>|<span data-ttu-id="0360e-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="0360e-259">**Protocol**</span></span>|<span data-ttu-id="0360e-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="0360e-260">**Host**</span></span>|<span data-ttu-id="0360e-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="0360e-261">**TTL**</span></span>|<span data-ttu-id="0360e-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="0360e-262">**Type**</span></span>|<span data-ttu-id="0360e-263">**Priority**</span><span class="sxs-lookup"><span data-stu-id="0360e-263">**Priority**</span></span>|<span data-ttu-id="0360e-264">**Weight**</span><span class="sxs-lookup"><span data-stu-id="0360e-264">**Weight**</span></span>|<span data-ttu-id="0360e-265">**Port**</span><span class="sxs-lookup"><span data-stu-id="0360e-265">**Port**</span></span>|<span data-ttu-id="0360e-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="0360e-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0360e-267">_sip</span><span class="sxs-lookup"><span data-stu-id="0360e-267">_sip</span></span>  <br/> |<span data-ttu-id="0360e-268">_tls</span><span class="sxs-lookup"><span data-stu-id="0360e-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="0360e-269">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-269">14400</span></span>  <br/> |<span data-ttu-id="0360e-270">SRV</span><span class="sxs-lookup"><span data-stu-id="0360e-270">SRV</span></span>  <br/> |<span data-ttu-id="0360e-271">100</span><span class="sxs-lookup"><span data-stu-id="0360e-271">100</span></span>  <br/> |<span data-ttu-id="0360e-272">1</span><span class="sxs-lookup"><span data-stu-id="0360e-272">1</span></span>  <br/> |<span data-ttu-id="0360e-273">443</span><span class="sxs-lookup"><span data-stu-id="0360e-273">443</span></span>  <br/> |<span data-ttu-id="0360e-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0360e-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="0360e-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0360e-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="0360e-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="0360e-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="0360e-277">14400</span><span class="sxs-lookup"><span data-stu-id="0360e-277">14400</span></span>  <br/> |<span data-ttu-id="0360e-278">SRV</span><span class="sxs-lookup"><span data-stu-id="0360e-278">SRV</span></span>  <br/> |<span data-ttu-id="0360e-279">100</span><span class="sxs-lookup"><span data-stu-id="0360e-279">100</span></span>  <br/> |<span data-ttu-id="0360e-280">1</span><span class="sxs-lookup"><span data-stu-id="0360e-280">1</span></span>  <br/> |<span data-ttu-id="0360e-281">5061</span><span class="sxs-lookup"><span data-stu-id="0360e-281">5061</span></span>  <br/> |<span data-ttu-id="0360e-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0360e-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Kopieren des Werts für den neuen Datensatz](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="0360e-284">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="0360e-284">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="0360e-286">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="0360e-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="0360e-287">Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der anderen Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0360e-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0360e-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0360e-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

