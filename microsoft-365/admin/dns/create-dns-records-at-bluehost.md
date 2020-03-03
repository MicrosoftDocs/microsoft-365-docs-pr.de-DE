---
title: Erstellen von DNS-Einträgen für Office 365 bei Bluehost
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei Bluehost für Office 365 einrichten.
ms.openlocfilehash: 0e64ed8787dca9822e71a63c57de7a7a3e2b3fe4
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350956"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a><span data-ttu-id="b3f30-103">Erstellen von DNS-Einträgen für Office 365 bei Bluehost</span><span class="sxs-lookup"><span data-stu-id="b3f30-103">Create DNS records at Bluehost for Office 365</span></span>

 <span data-ttu-id="b3f30-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b3f30-105">Wenn Bluehost Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b3f30-105">If Bluehost is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b3f30-106">Nachdem Sie diese Einträge bei Bluehost hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b3f30-106">After you add these records at Bluehost, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="b3f30-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="b3f30-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3f30-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b3f30-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b3f30-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b3f30-111">Add a TXT record for verification</span></span>
<span data-ttu-id="b3f30-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f30-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="b3f30-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="b3f30-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3f30-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b3f30-117">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="b3f30-117">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b3f30-118">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b3f30-119">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="b3f30-119">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b3f30-120">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-120">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b3f30-121">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-121">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b3f30-122">Geben Sie auf der Seite \* \* DNS-Zonen-Editor \* \* im Bereich **DNS-Eintrag hinzufügen** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="b3f30-122">On the \*\* DNS Zone Editor \*\* page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b3f30-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b3f30-124">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b3f30-124">**Host Record**</span></span> <br/> |<span data-ttu-id="b3f30-125">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b3f30-125">**TTL**</span></span> <br/> |<span data-ttu-id="b3f30-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3f30-126">**Type**</span></span> <br/> |<span data-ttu-id="b3f30-127">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b3f30-127">**TXT Value**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="b3f30-128">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-128">14400</span></span>  <br/> |<span data-ttu-id="b3f30-129">TXT</span><span class="sxs-lookup"><span data-stu-id="b3f30-129">TXT</span></span>  <br/> |<span data-ttu-id="b3f30-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b3f30-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b3f30-p105">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="b3f30-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
5. <span data-ttu-id="b3f30-134">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-134">Select **add record**.</span></span>
    
6. <span data-ttu-id="b3f30-135">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3f30-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b3f30-136">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-136">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="b3f30-137">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b3f30-137">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b3f30-138">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="b3f30-138">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b3f30-139">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b3f30-140">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b3f30-141">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b3f30-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b3f30-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="b3f30-145">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="b3f30-145">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="b3f30-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f30-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="b3f30-147">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="b3f30-147">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b3f30-148">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-148">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b3f30-149">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="b3f30-149">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b3f30-150">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-150">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b3f30-151">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-151">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b3f30-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b3f30-152">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b3f30-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b3f30-154">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b3f30-154">**Host Record**</span></span>|<span data-ttu-id="b3f30-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b3f30-155">**TTL**</span></span>|<span data-ttu-id="b3f30-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3f30-156">**Type**</span></span>|<span data-ttu-id="b3f30-157">**Points To**</span><span class="sxs-lookup"><span data-stu-id="b3f30-157">**Points To**</span></span>|<span data-ttu-id="b3f30-158">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b3f30-158">**Priority**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b3f30-159">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-159">14400</span></span>  <br/> |<span data-ttu-id="b3f30-160">MX</span><span class="sxs-lookup"><span data-stu-id="b3f30-160">MX</span></span>  <br/> | <span data-ttu-id="b3f30-161">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/><span data-ttu-id="b3f30-162">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="b3f30-162">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="b3f30-163">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b3f30-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b3f30-164">0</span><span class="sxs-lookup"><span data-stu-id="b3f30-164">0</span></span>  <br/> <span data-ttu-id="b3f30-165">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3f30-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Wählen Sie in der Dropdownliste Typ aus.](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. <span data-ttu-id="b3f30-167">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-167">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. <span data-ttu-id="b3f30-169">Wenn im Abschnitt **MX (Mail Exchanger)** weitere MX-Einträge vorhanden sind, löschen Sie die einzelnen Einträge.</span><span class="sxs-lookup"><span data-stu-id="b3f30-169">If there are any other MX records in the **MX (Mail Exchanger)** section, delete each of them.</span></span> 
    
    <span data-ttu-id="b3f30-170">Wählen Sie für einen der anderen MX-Einträge die Option **Löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="b3f30-170">For one of the other MX records, select **Delete.**</span></span>
    
    ![Wählen Sie DELETE für jeden zusätzlichen MX-Eintrag aus.](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. <span data-ttu-id="b3f30-172">Wählen Sie im Dialogfeld Bestätigung die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-172">In the confirmation dialog box, select **OK**.</span></span>
    
    ![Wählen Sie OK aus.](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. <span data-ttu-id="b3f30-174">Gehen Sie entsprechend vor, um alle weiteren bereits aufgeführten MX-Einträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-174">Use the same process to delete any other MX records that were already listed.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="b3f30-175">Hinzufügen der für Office 365 erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b3f30-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="b3f30-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f30-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="b3f30-177">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="b3f30-177">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b3f30-178">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-178">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b3f30-179">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="b3f30-179">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b3f30-180">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-180">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b3f30-181">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-181">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b3f30-182">Suchen Sie im Abschnitt **a (Host)** Records nach der Zeile für den **Auto Ermittlungs** Eintrag, und wählen Sie dann **Löschen** für diese Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-182">In the **A (Host)** records section, find the row for the **autodiscover** record, and then select **delete** for that row.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b3f30-p110">Sie müssen den vorhandenen **AutoErmittlung** seintrag löschen,  *bevor Sie*  den **AutoErmittlung** seintrag hinzufügen, der für Office 365 erforderlich ist. Bluehost gestattet Ihnen nicht, zwei **AutoErmittlung** seinträge gleichzeitig zu pflegen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-p110">You must delete the existing **autodiscover** record  *before*  adding the **autodiscover** record that is required by Office 365. Bluehost does not allow you to maintain two **autodiscover** records simultaneously.</span></span> 
  
    ![Wählen Sie löschen aus.](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. <span data-ttu-id="b3f30-186">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-186">Select **OK**.</span></span>
    
    ![Wählen Sie OK aus.](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. <span data-ttu-id="b3f30-188">Erstellen Sie den ersten der sechs CNAME-Einträge.</span><span class="sxs-lookup"><span data-stu-id="b3f30-188">Create the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="b3f30-189">Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-189">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="b3f30-190">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-190">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b3f30-191">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b3f30-191">**Host Record**</span></span>|<span data-ttu-id="b3f30-192">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b3f30-192">**TTL**</span></span>|<span data-ttu-id="b3f30-193">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3f30-193">**Type**</span></span>|<span data-ttu-id="b3f30-194">**Points To**</span><span class="sxs-lookup"><span data-stu-id="b3f30-194">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b3f30-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b3f30-195">autodiscover</span></span>  <br/> |<span data-ttu-id="b3f30-196">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-196">14400</span></span>  <br/> |<span data-ttu-id="b3f30-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="b3f30-197">CNAME</span></span>  <br/> |<span data-ttu-id="b3f30-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-198">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="b3f30-199">sip</span><span class="sxs-lookup"><span data-stu-id="b3f30-199">sip</span></span>  <br/> |<span data-ttu-id="b3f30-200">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-200">14400</span></span>  <br/> |<span data-ttu-id="b3f30-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="b3f30-201">CNAME</span></span>  <br/> |<span data-ttu-id="b3f30-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b3f30-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b3f30-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b3f30-204">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-204">14400</span></span>  <br/> |<span data-ttu-id="b3f30-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="b3f30-205">CNAME</span></span>  <br/> |<span data-ttu-id="b3f30-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b3f30-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b3f30-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b3f30-208">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-208">14400</span></span>  <br/> |<span data-ttu-id="b3f30-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="b3f30-209">CNAME</span></span>  <br/> |<span data-ttu-id="b3f30-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b3f30-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="b3f30-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b3f30-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b3f30-212">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-212">14400</span></span>  <br/> |<span data-ttu-id="b3f30-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="b3f30-213">CNAME</span></span>  <br/> |<span data-ttu-id="b3f30-214">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-214">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Erstellen des ersten CNAME-Eintrags](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. <span data-ttu-id="b3f30-216">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-216">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. <span data-ttu-id="b3f30-218">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3f30-218">Add each of the other five CNAME records.</span></span>
    
    <span data-ttu-id="b3f30-219">Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der nächsten Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-219">Still in the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **add record** to complete that record.</span></span> 
    
    <span data-ttu-id="b3f30-220">Wiederholen Sie diesen Vorgang, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b3f30-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b3f30-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b3f30-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b3f30-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f30-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3f30-p111">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben. Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf. Wenn es bei Ihrer Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Office 365 keinen neuen, sondern fügen Sie die erforderlichen Office 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind. Benötigen Sie Beispiele? Sehen Sie sich die folgenden [Externen DNS-Einträge für Office 365 an](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-p111">You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="b3f30-230">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="b3f30-230">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b3f30-231">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-231">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b3f30-232">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="b3f30-232">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b3f30-233">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-233">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b3f30-234">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-234">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b3f30-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b3f30-235">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b3f30-236">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-236">(Choose the **Type** value from the drop-down list.)</span></span> 
        
    |<span data-ttu-id="b3f30-237">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="b3f30-237">**Host Record**</span></span>|<span data-ttu-id="b3f30-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b3f30-238">**TTL**</span></span>|<span data-ttu-id="b3f30-239">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3f30-239">**Type**</span></span>|<span data-ttu-id="b3f30-240">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="b3f30-240">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="b3f30-241">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-241">14400</span></span>  <br/> |<span data-ttu-id="b3f30-242">TXT</span><span class="sxs-lookup"><span data-stu-id="b3f30-242">TXT</span></span>  <br/> |<span data-ttu-id="b3f30-243">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b3f30-243">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="b3f30-244">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-244">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Kopieren des txt-Werts](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. <span data-ttu-id="b3f30-246">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-246">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="b3f30-248">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="b3f30-248">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="b3f30-249"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="b3f30-249"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="b3f30-250">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="b3f30-250">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="b3f30-251">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b3f30-251">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b3f30-252">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="b3f30-252">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="b3f30-253">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-253">(You may have to scroll down.)</span></span>
    
3. <span data-ttu-id="b3f30-254">Wählen Sie im Bereich ***domain_name*** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-254">In the ***domain_name*** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="b3f30-255">Erstellen Sie den ersten der zwei SRV-Einträge.</span><span class="sxs-lookup"><span data-stu-id="b3f30-255">Create the first of the two SRV records.</span></span>
    
    <span data-ttu-id="b3f30-256">Geben Sie auf der Seite **DNS Zone Editor** im Bereich **Add DNS Record** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-256">On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="b3f30-257">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="b3f30-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b3f30-258">**Service**</span><span class="sxs-lookup"><span data-stu-id="b3f30-258">**Service**</span></span>|<span data-ttu-id="b3f30-259">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="b3f30-259">**Protocol**</span></span>|<span data-ttu-id="b3f30-260">**Host**</span><span class="sxs-lookup"><span data-stu-id="b3f30-260">**Host**</span></span>|<span data-ttu-id="b3f30-261">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b3f30-261">**TTL**</span></span>|<span data-ttu-id="b3f30-262">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3f30-262">**Type**</span></span>|<span data-ttu-id="b3f30-263">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b3f30-263">**Priority**</span></span>|<span data-ttu-id="b3f30-264">**Weight**</span><span class="sxs-lookup"><span data-stu-id="b3f30-264">**Weight**</span></span>|<span data-ttu-id="b3f30-265">**Port**</span><span class="sxs-lookup"><span data-stu-id="b3f30-265">**Port**</span></span>|<span data-ttu-id="b3f30-266">**Points To**</span><span class="sxs-lookup"><span data-stu-id="b3f30-266">**Points To**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b3f30-267">_sip</span><span class="sxs-lookup"><span data-stu-id="b3f30-267">_sip</span></span>  <br/> |<span data-ttu-id="b3f30-268">_tls</span><span class="sxs-lookup"><span data-stu-id="b3f30-268">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="b3f30-269">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-269">14400</span></span>  <br/> |<span data-ttu-id="b3f30-270">SRV</span><span class="sxs-lookup"><span data-stu-id="b3f30-270">SRV</span></span>  <br/> |<span data-ttu-id="b3f30-271">100</span><span class="sxs-lookup"><span data-stu-id="b3f30-271">100</span></span>  <br/> |<span data-ttu-id="b3f30-272">1</span><span class="sxs-lookup"><span data-stu-id="b3f30-272">1</span></span>  <br/> |<span data-ttu-id="b3f30-273">443</span><span class="sxs-lookup"><span data-stu-id="b3f30-273">443</span></span>  <br/> |<span data-ttu-id="b3f30-274">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-274">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="b3f30-275">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b3f30-275">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="b3f30-276">_tcp</span><span class="sxs-lookup"><span data-stu-id="b3f30-276">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="b3f30-277">14400</span><span class="sxs-lookup"><span data-stu-id="b3f30-277">14400</span></span>  <br/> |<span data-ttu-id="b3f30-278">SRV</span><span class="sxs-lookup"><span data-stu-id="b3f30-278">SRV</span></span>  <br/> |<span data-ttu-id="b3f30-279">100</span><span class="sxs-lookup"><span data-stu-id="b3f30-279">100</span></span>  <br/> |<span data-ttu-id="b3f30-280">1</span><span class="sxs-lookup"><span data-stu-id="b3f30-280">1</span></span>  <br/> |<span data-ttu-id="b3f30-281">5061</span><span class="sxs-lookup"><span data-stu-id="b3f30-281">5061</span></span>  <br/> |<span data-ttu-id="b3f30-282">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b3f30-282">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Kopieren des Werts für den neuen Datensatz](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. <span data-ttu-id="b3f30-284">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="b3f30-284">Select **add record**.</span></span>
    
    ![Wählen Sie Add Record aus.](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. <span data-ttu-id="b3f30-286">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3f30-286">Add the other SRV record.</span></span>
    
    <span data-ttu-id="b3f30-287">Erstellen Sie weiterhin im Abschnitt **Hinzufügen von DNS-Einträgen** mithilfe der Werte aus der anderen Zeile in der Tabelle einen Datensatz, und wählen Sie dann erneut **Datensatz hinzufügen** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b3f30-287">Still in the **Add DNS Record** section, create a record by using the values from the other row in the table, and then again select **add record** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b3f30-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b3f30-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

