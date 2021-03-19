---
title: Erstellen von DNS-Einträgen für Microsoft bei GoDaddy
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei GoDaddy für Microsoft einrichten.
ms.openlocfilehash: 2b53985dc17f3d124ec2b37dbf0047bce229385c
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126449"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="3c856-103">Erstellen von DNS-Einträgen für Microsoft bei GoDaddy</span><span class="sxs-lookup"><span data-stu-id="3c856-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="3c856-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="3c856-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="3c856-105">Wenn GoDaddy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="3c856-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="3c856-106">Nachdem Sie diese Einträge bei GoDaddy hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="3c856-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="3c856-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c856-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3c856-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="3c856-110">Add a TXT record for verification</span></span>
<span data-ttu-id="3c856-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3c856-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3c856-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="3c856-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="3c856-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="3c856-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="3c856-116">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-116">Follow the steps below.</span></span>

1. <span data-ttu-id="3c856-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3c856-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="3c856-120">Wählen Sie unter **Domänen** unter der Domäne DNS aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3c856-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="3c856-122">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c856-122">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="3c856-124">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="3c856-125">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c856-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="3c856-126">**Record type**</span><span class="sxs-lookup"><span data-stu-id="3c856-126">**Record type**</span></span> |<span data-ttu-id="3c856-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c856-127">**Host**</span></span>|<span data-ttu-id="3c856-128">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="3c856-128">**TXT Value**</span></span>|<span data-ttu-id="3c856-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c856-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c856-130">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="3c856-130">TXT (Text)</span></span>|@|<span data-ttu-id="3c856-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3c856-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="3c856-132">**Hinweis**: Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3c856-132">**Note**: This is an example.</span></span> <span data-ttu-id="3c856-133">Verwenden Sie hier Ihren spezifischen **Ziel- oder Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3c856-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="3c856-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="3c856-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="3c856-135">1 hour</span><span class="sxs-lookup"><span data-stu-id="3c856-135">1 hour</span></span>  <br><span data-ttu-id="3c856-136">(Wählen Sie einen Wert aus der Dropdownliste aus.)</span><span class="sxs-lookup"><span data-stu-id="3c856-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="3c856-138">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-138">Select **Save**.</span></span>

6. <span data-ttu-id="3c856-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c856-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="3c856-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="3c856-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="3c856-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="3c856-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3c856-142">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="3c856-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3c856-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="3c856-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="3c856-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="3c856-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c856-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3c856-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3c856-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3c856-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3c856-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="3c856-151">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-151">Follow the steps below.</span></span>

1. <span data-ttu-id="3c856-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3c856-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="3c856-155">Wählen Sie unter **Domänen** unter der Domäne DNS aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3c856-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="3c856-157">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c856-157">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="3c856-159">Wählen Sie in der Dropdownliste **MX (Mail Exchanger)** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="3c856-161">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c856-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="3c856-162">(Wählen Sie in der Dropdownliste den Wert für **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="3c856-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="3c856-163">**Record type**</span><span class="sxs-lookup"><span data-stu-id="3c856-163">**Record type**</span></span>|<span data-ttu-id="3c856-164">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c856-164">**Host**</span></span>|<span data-ttu-id="3c856-165">**Points to**</span><span class="sxs-lookup"><span data-stu-id="3c856-165">**Points to**</span></span>|<span data-ttu-id="3c856-166">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="3c856-166">**Priority**</span></span>|<span data-ttu-id="3c856-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c856-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c856-168">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="3c856-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="3c856-169">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3c856-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="3c856-170">**Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="3c856-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="3c856-171">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="3c856-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="3c856-172">10</span><span class="sxs-lookup"><span data-stu-id="3c856-172">10</span></span>  <br/> <span data-ttu-id="3c856-173">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="3c856-173">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="3c856-174">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="3c856-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="3c856-175">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c856-176">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="3c856-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3c856-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3c856-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="3c856-178">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-178">Follow the steps below.</span></span>

1. <span data-ttu-id="3c856-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3c856-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="3c856-182">Wählen Sie unter **Domänen** unter der Domäne DNS aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3c856-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="3c856-184">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c856-184">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="3c856-186">Wählen Sie in der Dropdownliste **CNAME (Alias)** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="3c856-188">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="3c856-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="3c856-189">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c856-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="3c856-190">(Wählen Sie in der Dropdownliste den Wert für **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="3c856-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="3c856-191">**Record type**</span><span class="sxs-lookup"><span data-stu-id="3c856-191">**Record type**</span></span>|<span data-ttu-id="3c856-192">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c856-192">**Host**</span></span>|<span data-ttu-id="3c856-193">**Points to**</span><span class="sxs-lookup"><span data-stu-id="3c856-193">**Points to**</span></span>|<span data-ttu-id="3c856-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c856-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c856-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3c856-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3c856-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="3c856-196">autodiscover</span></span>  <br/> |<span data-ttu-id="3c856-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3c856-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="3c856-198">1 hour</span><span class="sxs-lookup"><span data-stu-id="3c856-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="3c856-199">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3c856-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3c856-200">sip</span><span class="sxs-lookup"><span data-stu-id="3c856-200">sip</span></span>  <br/> |<span data-ttu-id="3c856-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c856-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="3c856-202">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="3c856-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="3c856-203">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3c856-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3c856-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3c856-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3c856-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c856-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="3c856-206">1 hour</span><span class="sxs-lookup"><span data-stu-id="3c856-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="3c856-207">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3c856-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3c856-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3c856-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3c856-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="3c856-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="3c856-210">1 hour</span><span class="sxs-lookup"><span data-stu-id="3c856-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="3c856-211">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="3c856-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="3c856-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3c856-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3c856-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3c856-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="3c856-214">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="3c856-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="3c856-215">Wiederholen Sie diese Schritte zum Hinzufügen des nächsten CNAME-Eintrags, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3c856-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3c856-216">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="3c856-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3c856-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3c856-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c856-218">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="3c856-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3c856-219">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="3c856-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3c856-220">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="3c856-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="3c856-221">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3c856-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="3c856-222">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-222">Follow the steps below.</span></span>

1. <span data-ttu-id="3c856-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3c856-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="3c856-226">Wählen Sie unter **Domänen** unter der Domäne DNS aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3c856-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="3c856-228">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c856-228">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="3c856-230">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="3c856-232">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c856-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="3c856-233">(Wählen Sie in den Dropdownlisten den Wert für **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="3c856-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="3c856-234">**Record type**</span><span class="sxs-lookup"><span data-stu-id="3c856-234">**Record type**</span></span>|<span data-ttu-id="3c856-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="3c856-235">**Host**</span></span>|<span data-ttu-id="3c856-236">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="3c856-236">**TXT Value**</span></span>|<span data-ttu-id="3c856-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c856-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c856-238">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="3c856-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="3c856-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3c856-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3c856-240">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="3c856-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="3c856-241">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="3c856-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="3c856-243">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3c856-244">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="3c856-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3c856-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3c856-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="3c856-246">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-246">Follow the steps below.</span></span>

1. <span data-ttu-id="3c856-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="3c856-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="3c856-250">Wählen Sie unter **Domänen** unter der Domäne DNS aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3c856-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="3c856-252">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c856-252">Select **Add**.</span></span>

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="3c856-254">Wählen Sie in der Dropdownliste **SRV (Service)** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="3c856-256">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="3c856-256">Create the first SRV record.</span></span>

    <span data-ttu-id="3c856-257">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c856-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="3c856-258">(Wählen Sie in den Dropdownlisten die Werte für **Record type** und **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="3c856-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="3c856-259">**Record type**</span><span class="sxs-lookup"><span data-stu-id="3c856-259">**Record type**</span></span>|<span data-ttu-id="3c856-260">**Name**</span><span class="sxs-lookup"><span data-stu-id="3c856-260">**Name**</span></span>|<span data-ttu-id="3c856-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="3c856-261">**Target**</span></span>|<span data-ttu-id="3c856-262">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="3c856-262">**Protocol**</span></span>|<span data-ttu-id="3c856-263">**Service**</span><span class="sxs-lookup"><span data-stu-id="3c856-263">**Service**</span></span>|<span data-ttu-id="3c856-264">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3c856-264">**Priority**</span></span>|<span data-ttu-id="3c856-265">**Weight**</span><span class="sxs-lookup"><span data-stu-id="3c856-265">**Weight**</span></span>|<span data-ttu-id="3c856-266">**Port**</span><span class="sxs-lookup"><span data-stu-id="3c856-266">**Port**</span></span>|<span data-ttu-id="3c856-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="3c856-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3c856-268">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="3c856-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="3c856-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c856-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="3c856-270">_tls</span><span class="sxs-lookup"><span data-stu-id="3c856-270">_tls</span></span>  <br/> |<span data-ttu-id="3c856-271">_sip</span><span class="sxs-lookup"><span data-stu-id="3c856-271">_sip</span></span>  <br/> |<span data-ttu-id="3c856-272">100</span><span class="sxs-lookup"><span data-stu-id="3c856-272">100</span></span>  <br/> |<span data-ttu-id="3c856-273">1</span><span class="sxs-lookup"><span data-stu-id="3c856-273">1</span></span>  <br/> |<span data-ttu-id="3c856-274">443</span><span class="sxs-lookup"><span data-stu-id="3c856-274">443</span></span>  <br/> |<span data-ttu-id="3c856-275">1 hour</span><span class="sxs-lookup"><span data-stu-id="3c856-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="3c856-276">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="3c856-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="3c856-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="3c856-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="3c856-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="3c856-278">_tcp</span></span>  <br/> |<span data-ttu-id="3c856-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="3c856-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="3c856-280">100</span><span class="sxs-lookup"><span data-stu-id="3c856-280">100</span></span>  <br/> |<span data-ttu-id="3c856-281">1</span><span class="sxs-lookup"><span data-stu-id="3c856-281">1</span></span>  <br/> |<span data-ttu-id="3c856-282">5061</span><span class="sxs-lookup"><span data-stu-id="3c856-282">5061</span></span>  <br/> |<span data-ttu-id="3c856-283">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="3c856-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="3c856-285">Wiederholen Sie **Schritt 5**, um den anderen SRV-Eintrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c856-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="3c856-286">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="3c856-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3c856-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3c856-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
