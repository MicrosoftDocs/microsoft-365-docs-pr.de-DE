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
ms.openlocfilehash: a39e44794ad0d8c66cd0786f88642541c6978a8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629719"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a><span data-ttu-id="ec30a-103">Erstellen von DNS-Einträgen bei Bluehost für Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec30a-103">Create DNS records at Bluehost for Microsoft</span></span>

 <span data-ttu-id="ec30a-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ec30a-105">Wenn Bluehost Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ec30a-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ec30a-106">Nachdem Sie diese Einträge bei Bluehost hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ec30a-106">After you add these records at Bluehost, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="ec30a-107">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="ec30a-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec30a-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ec30a-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ec30a-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ec30a-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ec30a-110">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ec30a-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ec30a-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ec30a-111">Add a TXT record for verification</span></span>
<span data-ttu-id="ec30a-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ec30a-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ec30a-113">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="ec30a-114">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec30a-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ec30a-117">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="ec30a-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ec30a-118">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ec30a-119">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="ec30a-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ec30a-120">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ec30a-121">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ec30a-122">Geben Sie auf der Seite \* \* DNS-Zonen-Editor \* \* im Bereich **DNS-Eintrag hinzufügen** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="ec30a-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ec30a-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ec30a-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ec30a-124">**Host Record**</span></span> <br/> |<span data-ttu-id="ec30a-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ec30a-125">**TTL**</span></span> <br/> |<span data-ttu-id="ec30a-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="ec30a-126">**Type**</span></span> <br/> |<span data-ttu-id="ec30a-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="ec30a-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="ec30a-128">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-128">14400</span></span>  <br/> |<span data-ttu-id="ec30a-129">TXT</span><span class="sxs-lookup"><span data-stu-id="ec30a-129">TXT</span></span>  <br/> |<span data-ttu-id="ec30a-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ec30a-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ec30a-131">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ec30a-131">**Note:** This is an example.</span></span> <span data-ttu-id="ec30a-132">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ec30a-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ec30a-133">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ec30a-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
5. <span data-ttu-id="ec30a-134">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="ec30a-135">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec30a-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ec30a-136">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="ec30a-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="ec30a-137">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="ec30a-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ec30a-138">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="ec30a-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ec30a-139">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ec30a-140">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ec30a-141">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ec30a-142">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ec30a-142">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ec30a-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ec30a-143">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ec30a-144">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ec30a-144">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ec30a-145">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="ec30a-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ec30a-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ec30a-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="ec30a-147">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="ec30a-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ec30a-148">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ec30a-149">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="ec30a-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ec30a-150">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ec30a-151">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ec30a-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ec30a-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ec30a-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ec30a-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ec30a-154">**Host Record**</span></span>|<span data-ttu-id="ec30a-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ec30a-155">**TTL**</span></span>|<span data-ttu-id="ec30a-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="ec30a-156">**Type**</span></span>|<span data-ttu-id="ec30a-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="ec30a-157">**Points To**</span></span>|<span data-ttu-id="ec30a-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ec30a-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ec30a-159">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-159">14400</span></span>  <br/> |<span data-ttu-id="ec30a-160">MX</span><span class="sxs-lookup"><span data-stu-id="ec30a-160">MX</span></span>  <br/> | <span data-ttu-id="ec30a-161">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="ec30a-162">**Hinweis:** Rufen Sie \<Ihren *Domänenschlüssel* \> von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="ec30a-162">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="ec30a-163">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ec30a-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ec30a-164">0</span><span class="sxs-lookup"><span data-stu-id="ec30a-164">0</span></span>  <br/> <span data-ttu-id="ec30a-165">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec30a-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Wählen Sie in der Dropdownliste Typ aus.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="ec30a-167">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-167">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="ec30a-169">Wenn im Abschnitt **MX (Mail Exchanger)** weitere MX-Einträge vorhanden sind, löschen Sie die einzelnen Einträge.</span><span class="sxs-lookup"><span data-stu-id="ec30a-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="ec30a-170">Wählen Sie für einen der anderen MX-Einträge die Option **Löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="ec30a-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Wählen Sie DELETE für jeden zusätzlichen MX-Eintrag aus.](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="ec30a-172">Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Wählen Sie OK aus.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="ec30a-174">Gehen Sie entsprechend vor, um alle weiteren bereits aufgeführten MX-Einträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ec30a-175">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="ec30a-175">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ec30a-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ec30a-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="ec30a-177">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="ec30a-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ec30a-178">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ec30a-179">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="ec30a-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ec30a-180">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ec30a-181">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ec30a-182">Suchen Sie im Abschnitt **a (Host)** Records nach der Zeile für den **Auto Ermittlungs** Eintrag, und wählen Sie dann **Löschen** für diese Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ec30a-183">Sie müssen den vorhandenen **Auto Ermittlungs** Daten Satz löschen, *bevor* Sie den von Microsoft benötigten **Auto Ermittlungs** Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-183">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Microsoft.</span></span> <span data-ttu-id="ec30a-184">Bluehost gestattet Ihnen nicht, zwei **AutoErmittlung** seinträge gleichzeitig zu pflegen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-184">Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Wählen Sie löschen aus.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="ec30a-186">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-186">Select **OK**.</span></span>
    
    ![Wählen Sie OK aus.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="ec30a-188">Erstellen Sie den ersten der sechs CNAME-Einträge.</span><span class="sxs-lookup"><span data-stu-id="ec30a-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="ec30a-189">Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ec30a-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ec30a-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ec30a-191">**Host Record**</span></span>|<span data-ttu-id="ec30a-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ec30a-192">**TTL**</span></span>|<span data-ttu-id="ec30a-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="ec30a-193">**Type**</span></span>|<span data-ttu-id="ec30a-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="ec30a-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ec30a-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ec30a-195">autodiscover</span></span>  <br/> |<span data-ttu-id="ec30a-196">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-196">14400</span></span>  <br/> |<span data-ttu-id="ec30a-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="ec30a-197">CNAME</span></span>  <br/> |<span data-ttu-id="ec30a-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ec30a-199">sip</span><span class="sxs-lookup"><span data-stu-id="ec30a-199">sip</span></span>  <br/> |<span data-ttu-id="ec30a-200">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-200">14400</span></span>  <br/> |<span data-ttu-id="ec30a-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="ec30a-201">CNAME</span></span>  <br/> |<span data-ttu-id="ec30a-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ec30a-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ec30a-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ec30a-204">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-204">14400</span></span>  <br/> |<span data-ttu-id="ec30a-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="ec30a-205">CNAME</span></span>  <br/> |<span data-ttu-id="ec30a-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ec30a-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ec30a-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ec30a-208">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-208">14400</span></span>  <br/> |<span data-ttu-id="ec30a-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="ec30a-209">CNAME</span></span>  <br/> |<span data-ttu-id="ec30a-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ec30a-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ec30a-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ec30a-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ec30a-212">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-212">14400</span></span>  <br/> |<span data-ttu-id="ec30a-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="ec30a-213">CNAME</span></span>  <br/> |<span data-ttu-id="ec30a-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Erstellen des ersten CNAME-Eintrags](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="ec30a-216">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-216">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="ec30a-218">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec30a-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="ec30a-219">Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der nächsten Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="ec30a-220">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ec30a-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ec30a-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="ec30a-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ec30a-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ec30a-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec30a-223">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="ec30a-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ec30a-224">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="ec30a-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ec30a-225">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec30a-225">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ec30a-226">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="ec30a-226">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="ec30a-227">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="ec30a-227">Need examples?</span></span> <span data-ttu-id="ec30a-228">Sehen Sie sich diese [externen Domänennamen-System Einträge für Microsoft an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="ec30a-228">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="ec30a-229">Zum Überprüfen des SPF-Eintrags können Sie eines dieser[SPF-Überprüfungstools](../setup/domains-faq.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-229">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="ec30a-230">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="ec30a-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ec30a-231">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ec30a-232">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="ec30a-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ec30a-233">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ec30a-234">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ec30a-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ec30a-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ec30a-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="ec30a-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="ec30a-237">**Host Record**</span></span>|<span data-ttu-id="ec30a-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ec30a-238">**TTL**</span></span>|<span data-ttu-id="ec30a-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="ec30a-239">**Type**</span></span>|<span data-ttu-id="ec30a-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="ec30a-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ec30a-241">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-241">14400</span></span>  <br/> |<span data-ttu-id="ec30a-242">TXT</span><span class="sxs-lookup"><span data-stu-id="ec30a-242">TXT</span></span>  <br/> |<span data-ttu-id="ec30a-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ec30a-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="ec30a-244">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopieren des txt-Werts](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="ec30a-246">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-246">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ec30a-248">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ec30a-248">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ec30a-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ec30a-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ec30a-250">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="ec30a-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="ec30a-251">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ec30a-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="ec30a-252">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="ec30a-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="ec30a-253">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="ec30a-254">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="ec30a-255">Erstellen Sie den ersten der zwei SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="ec30a-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="ec30a-256">Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="ec30a-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ec30a-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ec30a-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="ec30a-258">**Service**</span></span>|<span data-ttu-id="ec30a-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="ec30a-259">**Protocol**</span></span>|<span data-ttu-id="ec30a-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="ec30a-260">**Host**</span></span>|<span data-ttu-id="ec30a-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ec30a-261">**TTL**</span></span>|<span data-ttu-id="ec30a-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="ec30a-262">**Type**</span></span>|<span data-ttu-id="ec30a-263">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ec30a-263">**Priority**</span></span>|<span data-ttu-id="ec30a-264">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ec30a-264">**Weight**</span></span>|<span data-ttu-id="ec30a-265">**Port**</span><span class="sxs-lookup"><span data-stu-id="ec30a-265">**Port**</span></span>|<span data-ttu-id="ec30a-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="ec30a-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ec30a-267">_sip</span><span class="sxs-lookup"><span data-stu-id="ec30a-267">_sip</span></span>  <br/> |<span data-ttu-id="ec30a-268">_tls</span><span class="sxs-lookup"><span data-stu-id="ec30a-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="ec30a-269">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-269">14400</span></span>  <br/> |<span data-ttu-id="ec30a-270">SRV</span><span class="sxs-lookup"><span data-stu-id="ec30a-270">SRV</span></span>  <br/> |<span data-ttu-id="ec30a-271">100</span><span class="sxs-lookup"><span data-stu-id="ec30a-271">100</span></span>  <br/> |<span data-ttu-id="ec30a-272">1</span><span class="sxs-lookup"><span data-stu-id="ec30a-272">1</span></span>  <br/> |<span data-ttu-id="ec30a-273">443</span><span class="sxs-lookup"><span data-stu-id="ec30a-273">443</span></span>  <br/> |<span data-ttu-id="ec30a-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ec30a-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ec30a-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ec30a-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="ec30a-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="ec30a-277">14400</span><span class="sxs-lookup"><span data-stu-id="ec30a-277">14400</span></span>  <br/> |<span data-ttu-id="ec30a-278">SRV</span><span class="sxs-lookup"><span data-stu-id="ec30a-278">SRV</span></span>  <br/> |<span data-ttu-id="ec30a-279">100</span><span class="sxs-lookup"><span data-stu-id="ec30a-279">100</span></span>  <br/> |<span data-ttu-id="ec30a-280">1</span><span class="sxs-lookup"><span data-stu-id="ec30a-280">1</span></span>  <br/> |<span data-ttu-id="ec30a-281">5061</span><span class="sxs-lookup"><span data-stu-id="ec30a-281">5061</span></span>  <br/> |<span data-ttu-id="ec30a-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ec30a-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Kopieren des Werts für den neuen Datensatz](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="ec30a-284">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ec30a-284">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="ec30a-286">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec30a-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="ec30a-287">Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der anderen Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ec30a-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ec30a-288">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ec30a-288">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ec30a-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="ec30a-289">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ec30a-290">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ec30a-290">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

