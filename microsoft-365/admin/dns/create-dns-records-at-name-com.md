---
title: Erstellen von DNS-Einträgen bei Name.com für Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Name.com für Microsoft einrichten.
ms.openlocfilehash: 8518ca2570b3be1cb3abcd5c57b8309e989481cb
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938660"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="c2e36-103">Erstellen von DNS-Einträgen bei Name.com für Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2e36-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="c2e36-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c2e36-105">Wenn name.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c2e36-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c2e36-106">Nachdem Sie diese Einträge bei Name.com hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="c2e36-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="c2e36-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c2e36-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c2e36-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="c2e36-110">Add a TXT record for verification</span></span>
<span data-ttu-id="c2e36-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c2e36-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c2e36-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2e36-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c2e36-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c2e36-119">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c2e36-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c2e36-121">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c2e36-123">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c2e36-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2e36-125">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c2e36-125">**Type**</span></span> <br/> |<span data-ttu-id="c2e36-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="c2e36-126">**Host**</span></span> <br/> |<span data-ttu-id="c2e36-127">**Answer**</span><span class="sxs-lookup"><span data-stu-id="c2e36-127">**Answer**</span></span> <br/> |<span data-ttu-id="c2e36-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2e36-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="c2e36-129">TXT</span><span class="sxs-lookup"><span data-stu-id="c2e36-129">TXT</span></span>  <br/> |<span data-ttu-id="c2e36-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c2e36-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c2e36-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c2e36-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c2e36-132">**Note:** This is an example.</span></span> <span data-ttu-id="c2e36-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c2e36-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="c2e36-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="c2e36-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c2e36-135">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="c2e36-137">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="c2e36-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2e36-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c2e36-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="c2e36-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="c2e36-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="c2e36-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c2e36-142">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="c2e36-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c2e36-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="c2e36-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="c2e36-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="c2e36-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c2e36-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="c2e36-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="c2e36-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c2e36-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="c2e36-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c2e36-154">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c2e36-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c2e36-156">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c2e36-158">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c2e36-159">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c2e36-160">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c2e36-160">**Type**</span></span>|<span data-ttu-id="c2e36-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="c2e36-161">**Host**</span></span>|<span data-ttu-id="c2e36-162">**Answer**</span><span class="sxs-lookup"><span data-stu-id="c2e36-162">**Answer**</span></span>|<span data-ttu-id="c2e36-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2e36-163">**TTL**</span></span>|<span data-ttu-id="c2e36-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="c2e36-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2e36-165">MX</span><span class="sxs-lookup"><span data-stu-id="c2e36-165">MX</span></span>  <br/> |<span data-ttu-id="c2e36-166">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="c2e36-167">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="c2e36-168">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="c2e36-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="c2e36-169">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="c2e36-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="c2e36-170">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="c2e36-171">0</span><span class="sxs-lookup"><span data-stu-id="c2e36-171">0</span></span>  <br/> <span data-ttu-id="c2e36-172">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="c2e36-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="c2e36-174">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="c2e36-176">Wenn andere MX-Einträge vorhanden sind, löschen Sie diese, indem Sie die beiden folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c2e36-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="c2e36-177">Wählen Sie für jeden anderen MX-Eintrag in der Spalte **Aktionen** die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="c2e36-179">Um die Löschung zu bestätigen, wählen Sie erneut in der Spalte **Aktionen** die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="c2e36-181">Wiederholen Sie diese beiden Schritte, bis Sie alle anderen MX-Einträge gelöscht haben.</span><span class="sxs-lookup"><span data-stu-id="c2e36-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2e36-182">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="c2e36-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="c2e36-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c2e36-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="c2e36-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c2e36-187">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c2e36-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c2e36-189">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c2e36-191">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2e36-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="c2e36-192">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c2e36-193">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c2e36-194">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c2e36-194">**Type**</span></span>|<span data-ttu-id="c2e36-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="c2e36-195">**Host**</span></span>|<span data-ttu-id="c2e36-196">**Answer**</span><span class="sxs-lookup"><span data-stu-id="c2e36-196">**Answer**</span></span>|<span data-ttu-id="c2e36-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2e36-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2e36-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="c2e36-198">CNAME</span></span>  <br/> |<span data-ttu-id="c2e36-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="c2e36-199">autodiscover</span></span>  <br/> |<span data-ttu-id="c2e36-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="c2e36-201">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c2e36-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="c2e36-202">CNAME</span></span>  <br/> |<span data-ttu-id="c2e36-203">sip</span><span class="sxs-lookup"><span data-stu-id="c2e36-203">sip</span></span>  <br/> |<span data-ttu-id="c2e36-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2e36-205">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c2e36-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="c2e36-206">CNAME</span></span>  <br/> |<span data-ttu-id="c2e36-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c2e36-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c2e36-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="c2e36-209">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c2e36-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="c2e36-210">CNAME</span></span>  <br/> |<span data-ttu-id="c2e36-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c2e36-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c2e36-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c2e36-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="c2e36-213">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="c2e36-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="c2e36-214">CNAME</span></span>  <br/> |<span data-ttu-id="c2e36-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c2e36-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c2e36-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="c2e36-217">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="c2e36-219">Wählen Sie **Add Record** aus, um den ersten Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="c2e36-221">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2e36-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="c2e36-222">Verwenden Sie die Werte aus der zweiten Zeile der obigen Tabelle, und wählen Sie dann **Add Record** aus, um den zweiten Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="c2e36-223">Fügen Sie die übrigen Einträge auf gleiche Weise hinzu. Verwenden Sie dabei die Werte aus der dritten, vierten, fünften und sechsten Zeile der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c2e36-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c2e36-224">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="c2e36-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c2e36-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c2e36-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2e36-226">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="c2e36-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c2e36-227">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="c2e36-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c2e36-228">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="c2e36-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="c2e36-229">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="c2e36-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="c2e36-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c2e36-233">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c2e36-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c2e36-235">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c2e36-237">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c2e36-238">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c2e36-239">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c2e36-239">**Type**</span></span>|<span data-ttu-id="c2e36-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="c2e36-240">**Host**</span></span>|<span data-ttu-id="c2e36-241">**Answer**</span><span class="sxs-lookup"><span data-stu-id="c2e36-241">**Answer**</span></span>|<span data-ttu-id="c2e36-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2e36-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2e36-243">TXT</span><span class="sxs-lookup"><span data-stu-id="c2e36-243">TXT</span></span>  <br/> |<span data-ttu-id="c2e36-244">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="c2e36-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c2e36-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c2e36-246">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="c2e36-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="c2e36-249">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="c2e36-251">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="c2e36-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="c2e36-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c2e36-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="c2e36-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="c2e36-256">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c2e36-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="c2e36-258">Wählen Sie in der Spalte **Details** die Option **DNS Records +** aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="c2e36-260">Fügen Sie den ersten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="c2e36-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="c2e36-261">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c2e36-262">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="c2e36-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c2e36-263">**Type**</span><span class="sxs-lookup"><span data-stu-id="c2e36-263">**Type**</span></span>|<span data-ttu-id="c2e36-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="c2e36-264">**Service**</span></span>|<span data-ttu-id="c2e36-265">**Weight**</span><span class="sxs-lookup"><span data-stu-id="c2e36-265">**Weight**</span></span>|<span data-ttu-id="c2e36-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c2e36-266">**TTL**</span></span>|<span data-ttu-id="c2e36-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="c2e36-267">**Prio**</span></span>|<span data-ttu-id="c2e36-268">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="c2e36-268">**Protocol**</span></span>|<span data-ttu-id="c2e36-269">**Port**</span><span class="sxs-lookup"><span data-stu-id="c2e36-269">**Port**</span></span>|<span data-ttu-id="c2e36-270">**Target**</span><span class="sxs-lookup"><span data-stu-id="c2e36-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c2e36-271">SRV</span><span class="sxs-lookup"><span data-stu-id="c2e36-271">SRV</span></span>|<span data-ttu-id="c2e36-272">sip</span><span class="sxs-lookup"><span data-stu-id="c2e36-272">sip</span></span>|<span data-ttu-id="c2e36-273">1</span><span class="sxs-lookup"><span data-stu-id="c2e36-273">1</span></span>|<span data-ttu-id="c2e36-274">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-274">Use the default value (300).</span></span>|<span data-ttu-id="c2e36-275">100</span><span class="sxs-lookup"><span data-stu-id="c2e36-275">100</span></span>|<span data-ttu-id="c2e36-276">tls</span><span class="sxs-lookup"><span data-stu-id="c2e36-276">tls</span></span>|<span data-ttu-id="c2e36-277">443</span><span class="sxs-lookup"><span data-stu-id="c2e36-277">443</span></span>|<span data-ttu-id="c2e36-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="c2e36-279">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="c2e36-280">SRV</span><span class="sxs-lookup"><span data-stu-id="c2e36-280">SRV</span></span>|<span data-ttu-id="c2e36-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c2e36-281">sipfederationtls</span></span>|<span data-ttu-id="c2e36-282">1</span><span class="sxs-lookup"><span data-stu-id="c2e36-282">1</span></span>|<span data-ttu-id="c2e36-283">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="c2e36-283">Use the default value (300).</span></span>|<span data-ttu-id="c2e36-284">100</span><span class="sxs-lookup"><span data-stu-id="c2e36-284">100</span></span>|<span data-ttu-id="c2e36-285">tcp</span><span class="sxs-lookup"><span data-stu-id="c2e36-285">tcp</span></span>|<span data-ttu-id="c2e36-286">5061</span><span class="sxs-lookup"><span data-stu-id="c2e36-286">5061</span></span>|<span data-ttu-id="c2e36-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c2e36-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="c2e36-288">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="c2e36-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="c2e36-290">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="c2e36-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="c2e36-292">Fügen Sie den zweiten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="c2e36-292">Add the second SRV record:</span></span>

<span data-ttu-id="c2e36-293">Verwenden Sie die Werte aus der nächsten Zeile der obigen Tabelle, und wählen Sie dann **Add Record** aus, um den zweiten Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2e36-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="c2e36-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c2e36-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
