---
title: Erstellen von DNS-Einträgen bei Namecheap für Microsoft
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Namecheap für Microsoft einrichten.
ms.openlocfilehash: 2b55e529ab4a66dbada95914f213807884b4b6c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629335"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="ac089-103">Erstellen von DNS-Einträgen bei Namecheap für Microsoft</span><span class="sxs-lookup"><span data-stu-id="ac089-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="ac089-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ac089-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ac089-105">[] Wenn Namecheap Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ac089-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ac089-106">Nachdem Sie diese Einträge bei Namecheap hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ac089-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac089-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac089-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ac089-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ac089-110">Add a TXT record for verification</span></span>
<span data-ttu-id="ac089-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ac089-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ac089-112">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="ac089-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="ac089-113">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="ac089-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac089-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="ac089-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ac089-116">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="ac089-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in") und dann den Vorgang fortzusetzen ("Continue").</span><span class="sxs-lookup"><span data-stu-id="ac089-p104">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="ac089-120">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="ac089-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ac089-122">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ac089-124">Wählen Sie **Advanced DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="ac089-126">Wählen Sie im Abschnitt **Host Einträge** die Option **neuen Datensatz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="ac089-128">Wählen Sie in der Dropdownliste **Type** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac089-129">Die Dropdownliste **Typ** wird automatisch angezeigt, wenn Sie **neuen Datensatz hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac089-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="ac089-131">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ac089-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="ac089-132">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="ac089-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ac089-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac089-133">**Type**</span></span>|<span data-ttu-id="ac089-134">**Host**</span><span class="sxs-lookup"><span data-stu-id="ac089-134">**Host**</span></span>|<span data-ttu-id="ac089-135">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ac089-135">**Value**</span></span>|<span data-ttu-id="ac089-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac089-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac089-137">TXT</span><span class="sxs-lookup"><span data-stu-id="ac089-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="ac089-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ac089-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="ac089-139">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ac089-139">**Note:** This is an example.</span></span> <span data-ttu-id="ac089-140">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ac089-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="ac089-141">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ac089-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ac089-142">30 min</span><span class="sxs-lookup"><span data-stu-id="ac089-142">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="ac089-144">Wählen Sie das Kontrollkästchen **Änderungen speichern** (Häkchen) aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="ac089-146">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac089-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ac089-147">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="ac089-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ac089-148">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="ac089-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ac089-149">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="ac089-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ac089-150">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ac089-151">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ac089-152">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="ac089-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac089-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ac089-156">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="ac089-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ac089-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ac089-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ac089-158">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="ac089-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in") und dann den Vorgang fortzusetzen ("Continue").</span><span class="sxs-lookup"><span data-stu-id="ac089-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="ac089-162">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="ac089-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ac089-164">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ac089-166">Wählen Sie **Advanced DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="ac089-168">Wählen Sie im Abschnitt **MAIL SETTINGS** in der Dropdownliste **Email Forwarding** den Eintrag **Custom MX** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="ac089-169">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="ac089-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-BP-Configure-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="ac089-171">Wählen Sie **neuen Datensatz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-171">Select **Add New Record**.</span></span>
    
    ![NameCheap-BP-configure-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="ac089-173">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ac089-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="ac089-174">(Das Feld **Priority** ist das unbenannte Feld rechts neben dem Feld **Value**.</span><span class="sxs-lookup"><span data-stu-id="ac089-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="ac089-175">Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="ac089-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ac089-176">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac089-176">**Type**</span></span>|<span data-ttu-id="ac089-177">**Host**</span><span class="sxs-lookup"><span data-stu-id="ac089-177">**Host**</span></span>|<span data-ttu-id="ac089-178">**Value**</span><span class="sxs-lookup"><span data-stu-id="ac089-178">**Value**</span></span>|<span data-ttu-id="ac089-179">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="ac089-179">**Priority**</span></span>|<span data-ttu-id="ac089-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac089-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac089-181">MX-Eintrag</span><span class="sxs-lookup"><span data-stu-id="ac089-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="ac089-182">\<*Domänenschlüssel*\>. Mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="ac089-183">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="ac089-184">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="ac089-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="ac089-185">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ac089-185">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="ac089-186">0</span><span class="sxs-lookup"><span data-stu-id="ac089-186">0</span></span>  <br/> <span data-ttu-id="ac089-187">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac089-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="ac089-188">30 min</span><span class="sxs-lookup"><span data-stu-id="ac089-188">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-configure-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="ac089-190">Wählen Sie das Kontrollkästchen **Änderungen speichern** (Häkchen) aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="ac089-192">Wenn andere MX-Einträge vorhanden sind, führen Sie die beiden folgenden Schritte aus, um diese zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ac089-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="ac089-193">Wählen Sie zuerst das **Löschsymbol** (Papierkorb) für den Datensatz aus, den Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ac089-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-BP-Configure-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="ac089-195">Klicken Sie zweitens auf **Ja** , um den Löschvorgang zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="ac089-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-BP-Configure-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="ac089-197">Entfernen Sie alle MX-Einträge mit Ausnahme des Eintrags, den Sie zuvor in diesem Verfahren hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ac089-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ac089-198">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="ac089-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ac089-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ac089-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ac089-200">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="ac089-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in") und dann den Vorgang fortzusetzen ("Continue").</span><span class="sxs-lookup"><span data-stu-id="ac089-p110">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="ac089-204">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="ac089-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ac089-206">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ac089-208">Wählen Sie **Advanced DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="ac089-210">Wählen Sie im Abschnitt **Host Einträge** die Option **neuen Datensatz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="ac089-212">Wählen Sie in der Dropdownliste **Type** den Eintrag **CNAME Record** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac089-213">Die Dropdownliste **Typ** wird automatisch angezeigt, wenn Sie **neuen Datensatz hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac089-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="ac089-215">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **CNAME** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ac089-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="ac089-216">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac089-216">**Type**</span></span>|<span data-ttu-id="ac089-217">**Host**</span><span class="sxs-lookup"><span data-stu-id="ac089-217">**Host**</span></span>|<span data-ttu-id="ac089-218">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ac089-218">**Value**</span></span>|<span data-ttu-id="ac089-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac089-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac089-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac089-220">CNAME</span></span>  <br/> |<span data-ttu-id="ac089-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ac089-221">autodiscover</span></span>  <br/> |<span data-ttu-id="ac089-222">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="ac089-223">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-224">3600</span><span class="sxs-lookup"><span data-stu-id="ac089-224">3600</span></span>  <br/> |
    |<span data-ttu-id="ac089-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac089-225">CNAME</span></span>  <br/> |<span data-ttu-id="ac089-226">sip</span><span class="sxs-lookup"><span data-stu-id="ac089-226">sip</span></span>  <br/> |<span data-ttu-id="ac089-227">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ac089-228">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-229">3600</span><span class="sxs-lookup"><span data-stu-id="ac089-229">3600</span></span>  <br/> |
    |<span data-ttu-id="ac089-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac089-230">CNAME</span></span>  <br/> |<span data-ttu-id="ac089-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ac089-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ac089-232">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ac089-233">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-234">3600</span><span class="sxs-lookup"><span data-stu-id="ac089-234">3600</span></span>  <br/> |
    |<span data-ttu-id="ac089-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac089-235">CNAME</span></span>  <br/> |<span data-ttu-id="ac089-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ac089-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ac089-237">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="ac089-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="ac089-238">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-239">3600</span><span class="sxs-lookup"><span data-stu-id="ac089-239">3600</span></span>  <br/> |
    |<span data-ttu-id="ac089-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="ac089-240">CNAME</span></span>  <br/> |<span data-ttu-id="ac089-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ac089-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ac089-242">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="ac089-243">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-244">3600</span><span class="sxs-lookup"><span data-stu-id="ac089-244">3600</span></span>  <br/> |
       
    ![NameCheap-BP-configure-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="ac089-246">Wählen Sie das Kontrollkästchen **Änderungen speichern** (Häkchen) aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="ac089-248">Verwenden Sie die vorherigen vier Schritte und die Werte aus den anderen fünf Zeilen in der Tabelle, und fügen Sie jeden der anderen fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac089-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ac089-249">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="ac089-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ac089-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ac089-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac089-251">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="ac089-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ac089-252">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="ac089-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ac089-253">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac089-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ac089-254">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="ac089-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="ac089-255">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="ac089-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in") und dann den Vorgang fortzusetzen ("Continue").</span><span class="sxs-lookup"><span data-stu-id="ac089-p112">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="ac089-258">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="ac089-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ac089-260">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ac089-262">Wählen Sie **Advanced DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="ac089-264">Wählen Sie im Abschnitt **Host Einträge** die Option **neuen Datensatz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="ac089-266">Wählen Sie in der Dropdownliste **Type** den Eintrag **TXT Record** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac089-267">Die Dropdownliste **Typ** wird automatisch angezeigt, wenn Sie **neuen Datensatz hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac089-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="ac089-269">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ac089-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="ac089-270">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="ac089-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ac089-271">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac089-271">**Type**</span></span>|<span data-ttu-id="ac089-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="ac089-272">**Host**</span></span>|<span data-ttu-id="ac089-273">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ac089-273">**Value**</span></span>|<span data-ttu-id="ac089-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac089-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac089-275">TXT</span><span class="sxs-lookup"><span data-stu-id="ac089-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="ac089-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ac089-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ac089-277">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ac089-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="ac089-278">30 min</span><span class="sxs-lookup"><span data-stu-id="ac089-278">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-configure-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="ac089-280">Wählen Sie das Kontrollkästchen **Änderungen speichern** (Häkchen) aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ac089-282">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ac089-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ac089-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ac089-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="ac089-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) zu Ihrer Domänenseite bei Namecheap. Sie werden aufgefordert, sich zuerst anzumelden ("Sign in").</span><span class="sxs-lookup"><span data-stu-id="ac089-p113">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="ac089-287">Klicken Sie auf der **Start** Seite unter **Konto**auf **Domänenliste** in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="ac089-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="ac089-289">Suchen Sie auf der Seite **Domänenliste** den Namen der Domäne, die Sie bearbeiten möchten, und wählen Sie dann **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="ac089-291">Wählen Sie **Advanced DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="ac089-293">Wählen Sie im Abschnitt **Host Einträge** die Option **neuen Datensatz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="ac089-295">Wählen Sie in der Dropdownliste **Type** den Eintrag **SRV Record** aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ac089-296">Die Dropdownliste **Typ** wird automatisch angezeigt, wenn Sie **neuen Datensatz hinzufügen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ac089-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-BP-Configure-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="ac089-298">Geben Sie in den leeren Feldern für die neuen Einträge die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ac089-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="ac089-299">**Service**</span><span class="sxs-lookup"><span data-stu-id="ac089-299">**Service**</span></span>|<span data-ttu-id="ac089-300">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="ac089-300">**Protocol**</span></span>|<span data-ttu-id="ac089-301">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ac089-301">**Priority**</span></span>|<span data-ttu-id="ac089-302">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ac089-302">**Weight**</span></span>|<span data-ttu-id="ac089-303">**Port**</span><span class="sxs-lookup"><span data-stu-id="ac089-303">**Port**</span></span>|<span data-ttu-id="ac089-304">**Target**</span><span class="sxs-lookup"><span data-stu-id="ac089-304">**Target**</span></span>|<span data-ttu-id="ac089-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ac089-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ac089-306">_sip</span><span class="sxs-lookup"><span data-stu-id="ac089-306">_sip</span></span>  <br/> |<span data-ttu-id="ac089-307">_tls</span><span class="sxs-lookup"><span data-stu-id="ac089-307">_tls</span></span>  <br/> |<span data-ttu-id="ac089-308">100</span><span class="sxs-lookup"><span data-stu-id="ac089-308">100</span></span>  <br/> |<span data-ttu-id="ac089-309">1</span><span class="sxs-lookup"><span data-stu-id="ac089-309">1</span></span>  <br/> |<span data-ttu-id="ac089-310">443</span><span class="sxs-lookup"><span data-stu-id="ac089-310">443</span></span>  <br/> |<span data-ttu-id="ac089-311">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="ac089-312">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-313">30 min</span><span class="sxs-lookup"><span data-stu-id="ac089-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="ac089-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ac089-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ac089-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="ac089-315">_tcp</span></span>  <br/> |<span data-ttu-id="ac089-316">100</span><span class="sxs-lookup"><span data-stu-id="ac089-316">100</span></span>  <br/> |<span data-ttu-id="ac089-317">1</span><span class="sxs-lookup"><span data-stu-id="ac089-317">1</span></span>  <br/> |<span data-ttu-id="ac089-318">5061</span><span class="sxs-lookup"><span data-stu-id="ac089-318">5061</span></span>  <br/> |<span data-ttu-id="ac089-319">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ac089-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="ac089-320">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="ac089-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="ac089-321">30 min</span><span class="sxs-lookup"><span data-stu-id="ac089-321">30 min</span></span>  <br/> |
       
    ![NameCheap-BP-configure-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="ac089-323">Wählen Sie das Kontrollkästchen **Änderungen speichern** (Häkchen) aus.</span><span class="sxs-lookup"><span data-stu-id="ac089-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Configure-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="ac089-325">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die vier vorherigen Schritte unter Verwendung der Werte aus der zweiten Zeile in der Tabelle ausführen.</span><span class="sxs-lookup"><span data-stu-id="ac089-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ac089-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ac089-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
