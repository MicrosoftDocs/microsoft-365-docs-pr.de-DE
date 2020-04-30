---
title: Erstellen von DNS-Einträgen bei GoDaddy für Microsoft
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei GoDaddy für Microsoft einrichten.
ms.custom: okr_smb
ms.openlocfilehash: 0f71eb512b83451db8fee41b535ecc0c60d8d6bc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939215"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="2e786-103">Erstellen von DNS-Einträgen bei GoDaddy für Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e786-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="2e786-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="2e786-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="2e786-105">Wenn GoDaddy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="2e786-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="2e786-106">Nachdem Sie diese Einträge bei GoDaddy hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="2e786-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="2e786-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2e786-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2e786-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="2e786-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2e786-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2e786-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2e786-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="2e786-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="2e786-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="2e786-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="2e786-116">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-116">Follow the steps below.</span></span>

1. <span data-ttu-id="2e786-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="2e786-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="2e786-120">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2e786-120">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="2e786-122">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2e786-122">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="2e786-124">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-124">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="2e786-125">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="2e786-125">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="2e786-126">**Record type**</span><span class="sxs-lookup"><span data-stu-id="2e786-126">**Record type**</span></span> |<span data-ttu-id="2e786-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="2e786-127">**Host**</span></span>|<span data-ttu-id="2e786-128">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="2e786-128">**TXT Value**</span></span>|<span data-ttu-id="2e786-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2e786-129">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2e786-130">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="2e786-130">TXT (Text)</span></span>|@|<span data-ttu-id="2e786-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2e786-131">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="2e786-132">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2e786-132">**Note**: This is an example.</span></span> <span data-ttu-id="2e786-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2e786-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="2e786-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="2e786-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="2e786-135">1 hour</span><span class="sxs-lookup"><span data-stu-id="2e786-135">1 hour</span></span>  <br><span data-ttu-id="2e786-136">(Wählen Sie in der Dropdownliste einen Wert aus.)</span><span class="sxs-lookup"><span data-stu-id="2e786-136">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="2e786-138">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2e786-138">Select **Save**.</span></span>

6. <span data-ttu-id="2e786-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2e786-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="2e786-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="2e786-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="2e786-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="2e786-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2e786-142">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="2e786-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="2e786-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2e786-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-144">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="2e786-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-145">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="2e786-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2e786-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2e786-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2e786-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2e786-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2e786-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2e786-151">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-151">Follow the steps below.</span></span>

1. <span data-ttu-id="2e786-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="2e786-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="2e786-155">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2e786-155">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="2e786-157">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2e786-157">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="2e786-159">Wählen Sie in der Dropdownliste **MX (Mail Exchanger)** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-159">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="2e786-161">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="2e786-161">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="2e786-162">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="2e786-162">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="2e786-163">**Record type**</span><span class="sxs-lookup"><span data-stu-id="2e786-163">**Record type**</span></span>|<span data-ttu-id="2e786-164">**Host**</span><span class="sxs-lookup"><span data-stu-id="2e786-164">**Host**</span></span>|<span data-ttu-id="2e786-165">**Points to**</span><span class="sxs-lookup"><span data-stu-id="2e786-165">**Points to**</span></span>|<span data-ttu-id="2e786-166">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="2e786-166">**Priority**</span></span>|<span data-ttu-id="2e786-167">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2e786-167">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2e786-168">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="2e786-168">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="2e786-169">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2e786-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2e786-170">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="2e786-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="2e786-171">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="2e786-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="2e786-172">10  </span><span class="sxs-lookup"><span data-stu-id="2e786-172">10</span></span>  <br/> <span data-ttu-id="2e786-173">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e786-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="2e786-174">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-174">1 hour</span></span>  <br/> |

6. <span data-ttu-id="2e786-175">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2e786-175">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2e786-176">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="2e786-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2e786-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2e786-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2e786-178">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-178">Follow the steps below.</span></span>

1. <span data-ttu-id="2e786-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="2e786-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="2e786-182">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2e786-182">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="2e786-184">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2e786-184">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="2e786-186">Wählen Sie in der Dropdownliste **CNAME (Alias)** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-186">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="2e786-188">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="2e786-188">Create the first CNAME record.</span></span>

    <span data-ttu-id="2e786-189">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="2e786-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="2e786-190">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="2e786-190">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="2e786-191">**Record type**</span><span class="sxs-lookup"><span data-stu-id="2e786-191">**Record type**</span></span>|<span data-ttu-id="2e786-192">**Host**</span><span class="sxs-lookup"><span data-stu-id="2e786-192">**Host**</span></span>|<span data-ttu-id="2e786-193">**Points to**</span><span class="sxs-lookup"><span data-stu-id="2e786-193">**Points to**</span></span>|<span data-ttu-id="2e786-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2e786-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2e786-195">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="2e786-195">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2e786-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2e786-196">autodiscover</span></span>  <br/> |<span data-ttu-id="2e786-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2e786-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="2e786-198">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-198">1 hour</span></span>  <br/> |
    |<span data-ttu-id="2e786-199">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="2e786-199">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2e786-200">sip</span><span class="sxs-lookup"><span data-stu-id="2e786-200">sip</span></span>  <br/> |<span data-ttu-id="2e786-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2e786-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="2e786-202">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-202">1 hour</span></span>  <br/> |
    |<span data-ttu-id="2e786-203">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="2e786-203">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2e786-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2e786-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2e786-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2e786-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="2e786-206">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-206">1 hour</span></span>  <br/> |
    |<span data-ttu-id="2e786-207">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="2e786-207">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2e786-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2e786-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2e786-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2e786-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="2e786-210">1 hour</span><span class="sxs-lookup"><span data-stu-id="2e786-210">1 hour</span></span>  <br/> |
    |<span data-ttu-id="2e786-211">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="2e786-211">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="2e786-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2e786-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2e786-213">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2e786-213">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="2e786-214">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-214">1 hour</span></span>  <br/> |



6. <span data-ttu-id="2e786-215">Wiederholen Sie diese Schritte, um den nächsten CNAME-Eintrag hinzuzufügen, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2e786-215">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2e786-216">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="2e786-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2e786-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2e786-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e786-218">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="2e786-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2e786-219">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="2e786-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2e786-220">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="2e786-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2e786-221">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="2e786-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="2e786-222">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-222">Follow the steps below.</span></span>

1. <span data-ttu-id="2e786-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="2e786-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="2e786-226">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2e786-226">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="2e786-228">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2e786-228">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="2e786-230">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-230">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="2e786-232">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="2e786-232">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="2e786-233">(Wählen Sie in den Dropdownlisten den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="2e786-233">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="2e786-234">**Record type**</span><span class="sxs-lookup"><span data-stu-id="2e786-234">**Record type**</span></span>|<span data-ttu-id="2e786-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="2e786-235">**Host**</span></span>|<span data-ttu-id="2e786-236">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="2e786-236">**TXT Value**</span></span>|<span data-ttu-id="2e786-237">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2e786-237">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2e786-238">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="2e786-238">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="2e786-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2e786-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2e786-240">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="2e786-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="2e786-241">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-241">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="2e786-243">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2e786-243">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2e786-244">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="2e786-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2e786-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2e786-245"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2e786-246">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-246">Follow the steps below.</span></span>

1. <span data-ttu-id="2e786-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="2e786-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="2e786-250">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="2e786-250">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="2e786-252">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2e786-252">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="2e786-254">Wählen Sie in der Dropdownliste **SRV (Service)** aus.</span><span class="sxs-lookup"><span data-stu-id="2e786-254">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="2e786-256">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="2e786-256">Create the first SRV record.</span></span>

    <span data-ttu-id="2e786-257">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="2e786-257">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="2e786-258">(Wählen Sie in den Dropdownlisten die Werte für **Record Type** und **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="2e786-258">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="2e786-259">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="2e786-259">**Record type**</span></span>|<span data-ttu-id="2e786-260">**Name**</span><span class="sxs-lookup"><span data-stu-id="2e786-260">**Name**</span></span>|<span data-ttu-id="2e786-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="2e786-261">**Target**</span></span>|<span data-ttu-id="2e786-262">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="2e786-262">**Protocol**</span></span>|<span data-ttu-id="2e786-263">**Service**</span><span class="sxs-lookup"><span data-stu-id="2e786-263">**Service**</span></span>|<span data-ttu-id="2e786-264">**Priority**</span><span class="sxs-lookup"><span data-stu-id="2e786-264">**Priority**</span></span>|<span data-ttu-id="2e786-265">**Weight**</span><span class="sxs-lookup"><span data-stu-id="2e786-265">**Weight**</span></span>|<span data-ttu-id="2e786-266">**Port**</span><span class="sxs-lookup"><span data-stu-id="2e786-266">**Port**</span></span>|<span data-ttu-id="2e786-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2e786-267">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2e786-268">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="2e786-268">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="2e786-269">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2e786-269">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="2e786-270">_tls</span><span class="sxs-lookup"><span data-stu-id="2e786-270">_tls</span></span>  <br/> |<span data-ttu-id="2e786-271">_sip</span><span class="sxs-lookup"><span data-stu-id="2e786-271">_sip</span></span>  <br/> |<span data-ttu-id="2e786-272">100</span><span class="sxs-lookup"><span data-stu-id="2e786-272">100</span></span>  <br/> |<span data-ttu-id="2e786-273">1</span><span class="sxs-lookup"><span data-stu-id="2e786-273">1</span></span>  <br/> |<span data-ttu-id="2e786-274">443</span><span class="sxs-lookup"><span data-stu-id="2e786-274">443</span></span>  <br/> |<span data-ttu-id="2e786-275">1 hour</span><span class="sxs-lookup"><span data-stu-id="2e786-275">1 hour</span></span>  <br/> |
    |<span data-ttu-id="2e786-276">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="2e786-276">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="2e786-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2e786-277">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="2e786-278">_tcp</span><span class="sxs-lookup"><span data-stu-id="2e786-278">_tcp</span></span>  <br/> |<span data-ttu-id="2e786-279">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2e786-279">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="2e786-280">100</span><span class="sxs-lookup"><span data-stu-id="2e786-280">100</span></span>  <br/> |<span data-ttu-id="2e786-281">1</span><span class="sxs-lookup"><span data-stu-id="2e786-281">1</span></span>  <br/> |<span data-ttu-id="2e786-282">5061</span><span class="sxs-lookup"><span data-stu-id="2e786-282">5061</span></span>  <br/> |<span data-ttu-id="2e786-283">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="2e786-283">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="2e786-285">Wiederholen Sie **Schritt 5** , um den anderen SRV-Eintrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e786-285">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="2e786-286">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2e786-286">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e786-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2e786-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
