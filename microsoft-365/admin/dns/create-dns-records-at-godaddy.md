---
title: Erstellen von DNS-Einträgen für Office 365 bei GoDaddy
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei GoDaddy für Office 365 einrichten.
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349236"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a><span data-ttu-id="4a949-103">Erstellen von DNS-Einträgen für Office 365 bei GoDaddy</span><span class="sxs-lookup"><span data-stu-id="4a949-103">Create DNS records at GoDaddy for Office 365</span></span>

 <span data-ttu-id="4a949-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="4a949-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="4a949-105">Wenn GoDaddy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4a949-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="4a949-106">Nachdem Sie diese Einträge bei GoDaddy hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4a949-106">After you add these records at GoDaddy, your domain will be set up to work with Office 365 services.</span></span>

<span data-ttu-id="4a949-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="4a949-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="4a949-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a949-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4a949-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="4a949-111">Add a TXT record for verification</span></span>
<span data-ttu-id="4a949-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4a949-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4a949-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="4a949-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="4a949-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="4a949-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="4a949-117">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-117">Follow the steps below.</span></span>

1. <span data-ttu-id="4a949-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a949-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4a949-121">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a949-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4a949-123">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a949-123">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4a949-125">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="4a949-126">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a949-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="4a949-127">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4a949-127">**Record type**</span></span> |<span data-ttu-id="4a949-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a949-128">**Host**</span></span>|<span data-ttu-id="4a949-129">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="4a949-129">**TXT Value**</span></span>|<span data-ttu-id="4a949-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a949-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a949-131">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="4a949-131">TXT (Text)</span></span>|@|<span data-ttu-id="4a949-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4a949-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="4a949-133">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4a949-133">**Note**: This is an example.</span></span> <span data-ttu-id="4a949-134">Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a949-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="4a949-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="4a949-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="4a949-136">1 hour</span><span class="sxs-lookup"><span data-stu-id="4a949-136">1 hour</span></span>  <br><span data-ttu-id="4a949-137">(Wählen Sie in der Dropdownliste einen Wert aus.)</span><span class="sxs-lookup"><span data-stu-id="4a949-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="4a949-139">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4a949-139">Select **Save**.</span></span>

6. <span data-ttu-id="4a949-140">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a949-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="4a949-141">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4a949-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>

<span data-ttu-id="4a949-142">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="4a949-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4a949-143">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="4a949-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4a949-144">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4a949-145">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="4a949-146">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="4a949-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a949-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="4a949-150">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="4a949-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="4a949-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4a949-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="4a949-152">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-152">Follow the steps below.</span></span>

1. <span data-ttu-id="4a949-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a949-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4a949-156">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a949-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4a949-158">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a949-158">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4a949-160">Wählen Sie in der Dropdownliste **MX (Mail Exchanger)** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="4a949-162">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a949-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="4a949-163">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="4a949-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="4a949-164">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4a949-164">**Record type**</span></span>|<span data-ttu-id="4a949-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a949-165">**Host**</span></span>|<span data-ttu-id="4a949-166">**Points to**</span><span class="sxs-lookup"><span data-stu-id="4a949-166">**Points to**</span></span>|<span data-ttu-id="4a949-167">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="4a949-167">**Priority**</span></span>|<span data-ttu-id="4a949-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a949-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a949-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="4a949-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="4a949-170">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a949-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4a949-171">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="4a949-171">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="4a949-172">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="4a949-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="4a949-173">10 </span><span class="sxs-lookup"><span data-stu-id="4a949-173">10</span></span>  <br/> <span data-ttu-id="4a949-174">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a949-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="4a949-175">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="4a949-176">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4a949-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="4a949-177">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="4a949-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="4a949-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4a949-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="4a949-179">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-179">Follow the steps below.</span></span>

1. <span data-ttu-id="4a949-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a949-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4a949-183">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a949-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4a949-185">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a949-185">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="4a949-187">Wählen Sie in der Dropdownliste **CNAME (Alias)** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="4a949-189">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="4a949-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="4a949-190">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a949-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="4a949-191">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="4a949-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="4a949-192">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4a949-192">**Record type**</span></span>|<span data-ttu-id="4a949-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a949-193">**Host**</span></span>|<span data-ttu-id="4a949-194">**Points to**</span><span class="sxs-lookup"><span data-stu-id="4a949-194">**Points to**</span></span>|<span data-ttu-id="4a949-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a949-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a949-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4a949-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4a949-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4a949-197">autodiscover</span></span>  <br/> |<span data-ttu-id="4a949-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a949-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="4a949-199">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4a949-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4a949-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4a949-201">sip</span><span class="sxs-lookup"><span data-stu-id="4a949-201">sip</span></span>  <br/> |<span data-ttu-id="4a949-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a949-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4a949-203">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4a949-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4a949-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4a949-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4a949-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4a949-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a949-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4a949-207">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4a949-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4a949-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4a949-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4a949-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4a949-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4a949-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="4a949-211">1 hour</span><span class="sxs-lookup"><span data-stu-id="4a949-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4a949-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="4a949-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="4a949-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4a949-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4a949-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4a949-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="4a949-215">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="4a949-216">Wiederholen Sie diese Schritte, um den nächsten CNAME-Eintrag hinzuzufügen, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4a949-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4a949-217">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="4a949-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4a949-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4a949-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a949-219">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="4a949-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4a949-220">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="4a949-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4a949-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a949-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4a949-222">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4a949-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="4a949-223">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-223">Follow the steps below.</span></span>

1. <span data-ttu-id="4a949-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a949-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4a949-227">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a949-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4a949-229">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a949-229">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4a949-231">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="4a949-233">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a949-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="4a949-234">(Wählen Sie in den Dropdownlisten den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="4a949-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="4a949-235">**Record type**</span><span class="sxs-lookup"><span data-stu-id="4a949-235">**Record type**</span></span>|<span data-ttu-id="4a949-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a949-236">**Host**</span></span>|<span data-ttu-id="4a949-237">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="4a949-237">**TXT Value**</span></span>|<span data-ttu-id="4a949-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a949-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a949-239">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="4a949-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="4a949-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4a949-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4a949-241">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4a949-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="4a949-242">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="4a949-244">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4a949-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="4a949-245">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="4a949-245">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="4a949-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4a949-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="4a949-247">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-247">Follow the steps below.</span></span>

1. <span data-ttu-id="4a949-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="4a949-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="4a949-251">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="4a949-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="4a949-253">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4a949-253">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="4a949-255">Wählen Sie in der Dropdownliste **SRV (Service)** aus.</span><span class="sxs-lookup"><span data-stu-id="4a949-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="4a949-257">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="4a949-257">Create the first SRV record.</span></span>

    <span data-ttu-id="4a949-258">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="4a949-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="4a949-259">(Wählen Sie in den Dropdownlisten die Werte für **Record Type** und **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="4a949-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="4a949-260">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="4a949-260">**Record type**</span></span>|<span data-ttu-id="4a949-261">**Name**</span><span class="sxs-lookup"><span data-stu-id="4a949-261">**Name**</span></span>|<span data-ttu-id="4a949-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="4a949-262">**Target**</span></span>|<span data-ttu-id="4a949-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="4a949-263">**Protocol**</span></span>|<span data-ttu-id="4a949-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="4a949-264">**Service**</span></span>|<span data-ttu-id="4a949-265">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4a949-265">**Priority**</span></span>|<span data-ttu-id="4a949-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="4a949-266">**Weight**</span></span>|<span data-ttu-id="4a949-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="4a949-267">**Port**</span></span>|<span data-ttu-id="4a949-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a949-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a949-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="4a949-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="4a949-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a949-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="4a949-271">_tls</span><span class="sxs-lookup"><span data-stu-id="4a949-271">_tls</span></span>  <br/> |<span data-ttu-id="4a949-272">_sip</span><span class="sxs-lookup"><span data-stu-id="4a949-272">_sip</span></span>  <br/> |<span data-ttu-id="4a949-273">100</span><span class="sxs-lookup"><span data-stu-id="4a949-273">100</span></span>  <br/> |<span data-ttu-id="4a949-274">1</span><span class="sxs-lookup"><span data-stu-id="4a949-274">1</span></span>  <br/> |<span data-ttu-id="4a949-275">443</span><span class="sxs-lookup"><span data-stu-id="4a949-275">443</span></span>  <br/> |<span data-ttu-id="4a949-276">1 hour</span><span class="sxs-lookup"><span data-stu-id="4a949-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="4a949-277">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="4a949-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="4a949-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a949-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="4a949-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="4a949-279">_tcp</span></span>  <br/> |<span data-ttu-id="4a949-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4a949-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="4a949-281">100</span><span class="sxs-lookup"><span data-stu-id="4a949-281">100</span></span>  <br/> |<span data-ttu-id="4a949-282">1</span><span class="sxs-lookup"><span data-stu-id="4a949-282">1</span></span>  <br/> |<span data-ttu-id="4a949-283">5061</span><span class="sxs-lookup"><span data-stu-id="4a949-283">5061</span></span>  <br/> |<span data-ttu-id="4a949-284">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="4a949-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="4a949-286">Wiederholen Sie **Schritt 5** , um den anderen SRV-Eintrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a949-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="4a949-287">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4a949-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="4a949-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a949-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
