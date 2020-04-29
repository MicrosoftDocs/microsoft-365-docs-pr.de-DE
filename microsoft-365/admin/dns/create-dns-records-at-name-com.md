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
ms.openlocfilehash: 9183d27641ee22d9e49be2ca04832ab68bc20ace
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919736"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="10e56-103">Erstellen von DNS-Einträgen bei Name.com für Microsoft</span><span class="sxs-lookup"><span data-stu-id="10e56-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="10e56-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="10e56-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="10e56-105">Wenn name.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="10e56-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="10e56-106">Nachdem Sie diese Einträge bei Name.com hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="10e56-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="10e56-107">Informationen zu Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="10e56-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="10e56-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10e56-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="10e56-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="10e56-111">Add a TXT record for verification</span></span>
<span data-ttu-id="10e56-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="10e56-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="10e56-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="10e56-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10e56-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="10e56-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="10e56-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10e56-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10e56-120">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="10e56-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10e56-122">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-122">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10e56-124">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="10e56-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="10e56-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10e56-126">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10e56-126">**Type**</span></span> <br/> |<span data-ttu-id="10e56-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="10e56-127">**Host**</span></span> <br/> |<span data-ttu-id="10e56-128">**Answer**</span><span class="sxs-lookup"><span data-stu-id="10e56-128">**Answer**</span></span> <br/> |<span data-ttu-id="10e56-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10e56-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="10e56-130">TXT</span><span class="sxs-lookup"><span data-stu-id="10e56-130">TXT</span></span>  <br/> |<span data-ttu-id="10e56-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="10e56-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10e56-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="10e56-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="10e56-133">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="10e56-133">**Note:** This is an example.</span></span> <span data-ttu-id="10e56-134">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="10e56-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="10e56-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="10e56-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="10e56-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-136">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="10e56-138">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="10e56-140">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="10e56-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="10e56-141">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="10e56-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="10e56-142">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="10e56-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="10e56-143">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="10e56-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="10e56-144">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="10e56-145">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="10e56-146">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="10e56-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10e56-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="10e56-150">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="10e56-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="10e56-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="10e56-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="10e56-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10e56-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10e56-155">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="10e56-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10e56-157">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10e56-159">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="10e56-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="10e56-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10e56-161">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10e56-161">**Type**</span></span>|<span data-ttu-id="10e56-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="10e56-162">**Host**</span></span>|<span data-ttu-id="10e56-163">**Answer**</span><span class="sxs-lookup"><span data-stu-id="10e56-163">**Answer**</span></span>|<span data-ttu-id="10e56-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10e56-164">**TTL**</span></span>|<span data-ttu-id="10e56-165">**Prio**</span><span class="sxs-lookup"><span data-stu-id="10e56-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10e56-166">MX</span><span class="sxs-lookup"><span data-stu-id="10e56-166">MX</span></span>  <br/> |<span data-ttu-id="10e56-167">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="10e56-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="10e56-168">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="10e56-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="10e56-169">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="10e56-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="10e56-170">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="10e56-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="10e56-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="10e56-172">0</span><span class="sxs-lookup"><span data-stu-id="10e56-172">0</span></span>  <br/> <span data-ttu-id="10e56-173">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="10e56-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="10e56-175">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="10e56-177">Wenn andere MX-Einträge vorhanden sind, löschen Sie diese, indem Sie die beiden folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="10e56-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="10e56-178">Wählen Sie für jeden anderen MX-Eintrag in der Spalte **Aktionen** die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="10e56-180">Um die Löschung zu bestätigen, wählen Sie erneut in der Spalte **Aktionen** die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="10e56-182">Wiederholen Sie diese beiden Schritte, bis Sie alle anderen MX-Einträge gelöscht haben.</span><span class="sxs-lookup"><span data-stu-id="10e56-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="10e56-183">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="10e56-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="10e56-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="10e56-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="10e56-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10e56-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10e56-188">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="10e56-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10e56-190">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10e56-192">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="10e56-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="10e56-193">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="10e56-194">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="10e56-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10e56-195">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10e56-195">**Type**</span></span>|<span data-ttu-id="10e56-196">**Host**</span><span class="sxs-lookup"><span data-stu-id="10e56-196">**Host**</span></span>|<span data-ttu-id="10e56-197">**Answer**</span><span class="sxs-lookup"><span data-stu-id="10e56-197">**Answer**</span></span>|<span data-ttu-id="10e56-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10e56-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10e56-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="10e56-199">CNAME</span></span>  <br/> |<span data-ttu-id="10e56-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="10e56-200">autodiscover</span></span>  <br/> |<span data-ttu-id="10e56-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="10e56-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="10e56-202">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10e56-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="10e56-203">CNAME</span></span>  <br/> |<span data-ttu-id="10e56-204">sip</span><span class="sxs-lookup"><span data-stu-id="10e56-204">sip</span></span>  <br/> |<span data-ttu-id="10e56-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10e56-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="10e56-206">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10e56-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="10e56-207">CNAME</span></span>  <br/> |<span data-ttu-id="10e56-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="10e56-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="10e56-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10e56-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="10e56-210">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10e56-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="10e56-211">CNAME</span></span>  <br/> |<span data-ttu-id="10e56-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="10e56-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="10e56-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="10e56-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="10e56-214">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="10e56-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="10e56-215">CNAME</span></span>  <br/> |<span data-ttu-id="10e56-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="10e56-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="10e56-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="10e56-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="10e56-218">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="10e56-220">Wählen Sie **Add Record** aus, um den ersten Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="10e56-222">Fügen Sie den zweiten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="10e56-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="10e56-223">Verwenden Sie die Werte aus der zweiten Zeile der obigen Tabelle, und wählen Sie dann **Add Record** aus, um den zweiten Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="10e56-224">Fügen Sie die übrigen Einträge auf gleiche Weise hinzu. Verwenden Sie dabei die Werte aus der dritten, vierten, fünften und sechsten Zeile der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="10e56-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="10e56-225">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="10e56-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="10e56-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="10e56-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="10e56-227">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="10e56-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="10e56-228">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="10e56-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="10e56-229">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="10e56-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="10e56-230">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="10e56-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="10e56-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10e56-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10e56-234">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="10e56-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10e56-236">Wählen Sie in der Spalte **Details** die Option **DNS Records**aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10e56-238">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="10e56-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="10e56-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10e56-240">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10e56-240">**Type**</span></span>|<span data-ttu-id="10e56-241">**Host**</span><span class="sxs-lookup"><span data-stu-id="10e56-241">**Host**</span></span>|<span data-ttu-id="10e56-242">**Answer**</span><span class="sxs-lookup"><span data-stu-id="10e56-242">**Answer**</span></span>|<span data-ttu-id="10e56-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10e56-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10e56-244">TXT</span><span class="sxs-lookup"><span data-stu-id="10e56-244">TXT</span></span>  <br/> |<span data-ttu-id="10e56-245">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="10e56-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="10e56-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="10e56-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="10e56-247">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="10e56-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="10e56-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="10e56-250">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="10e56-252">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="10e56-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="10e56-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="10e56-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="10e56-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.name.com/account/domain) zu Ihrer Domänenseite bei name.com. Sie werden zuerst aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="10e56-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="10e56-257">Wählen Sie unter **Meine Domänen**den Namen der Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="10e56-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="10e56-259">Wählen Sie in der Spalte **Details** die Option **DNS Records +** aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="10e56-261">Fügen Sie den ersten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="10e56-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="10e56-262">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="10e56-263">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="10e56-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="10e56-264">**Type**</span><span class="sxs-lookup"><span data-stu-id="10e56-264">**Type**</span></span>|<span data-ttu-id="10e56-265">**Service**</span><span class="sxs-lookup"><span data-stu-id="10e56-265">**Service**</span></span>|<span data-ttu-id="10e56-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="10e56-266">**Weight**</span></span>|<span data-ttu-id="10e56-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="10e56-267">**TTL**</span></span>|<span data-ttu-id="10e56-268">**Prio**</span><span class="sxs-lookup"><span data-stu-id="10e56-268">**Prio**</span></span>|<span data-ttu-id="10e56-269">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="10e56-269">**Protocol**</span></span>|<span data-ttu-id="10e56-270">**Port**</span><span class="sxs-lookup"><span data-stu-id="10e56-270">**Port**</span></span>|<span data-ttu-id="10e56-271">**Target**</span><span class="sxs-lookup"><span data-stu-id="10e56-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="10e56-272">SRV</span><span class="sxs-lookup"><span data-stu-id="10e56-272">SRV</span></span>|<span data-ttu-id="10e56-273">sip</span><span class="sxs-lookup"><span data-stu-id="10e56-273">sip</span></span>|<span data-ttu-id="10e56-274">1</span><span class="sxs-lookup"><span data-stu-id="10e56-274">1</span></span>|<span data-ttu-id="10e56-275">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-275">Use the default value (300).</span></span>|<span data-ttu-id="10e56-276">100</span><span class="sxs-lookup"><span data-stu-id="10e56-276">100</span></span>|<span data-ttu-id="10e56-277">tls</span><span class="sxs-lookup"><span data-stu-id="10e56-277">tls</span></span>|<span data-ttu-id="10e56-278">443</span><span class="sxs-lookup"><span data-stu-id="10e56-278">443</span></span>|<span data-ttu-id="10e56-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10e56-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="10e56-280">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="10e56-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="10e56-281">SRV</span><span class="sxs-lookup"><span data-stu-id="10e56-281">SRV</span></span>|<span data-ttu-id="10e56-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="10e56-282">sipfederationtls</span></span>|<span data-ttu-id="10e56-283">1</span><span class="sxs-lookup"><span data-stu-id="10e56-283">1</span></span>|<span data-ttu-id="10e56-284">Verwenden Sie den Standardwert (300).</span><span class="sxs-lookup"><span data-stu-id="10e56-284">Use the default value (300).</span></span>|<span data-ttu-id="10e56-285">100</span><span class="sxs-lookup"><span data-stu-id="10e56-285">100</span></span>|<span data-ttu-id="10e56-286">tcp</span><span class="sxs-lookup"><span data-stu-id="10e56-286">tcp</span></span>|<span data-ttu-id="10e56-287">5061</span><span class="sxs-lookup"><span data-stu-id="10e56-287">5061</span></span>|<span data-ttu-id="10e56-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="10e56-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="10e56-289">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="10e56-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="10e56-291">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="10e56-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="10e56-293">Fügen Sie den zweiten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="10e56-293">Add the second SRV record:</span></span>

<span data-ttu-id="10e56-294">Verwenden Sie die Werte aus der nächsten Zeile der obigen Tabelle, und wählen Sie dann **Add Record** aus, um den zweiten Datensatz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="10e56-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="10e56-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="10e56-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
