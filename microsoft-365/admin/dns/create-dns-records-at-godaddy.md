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
ms.openlocfilehash: 0e9b75bcd4aa93270efd9b2d94fa2ceeb6e55f75
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629551"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a><span data-ttu-id="cdc25-103">Erstellen von DNS-Einträgen bei GoDaddy für Microsoft</span><span class="sxs-lookup"><span data-stu-id="cdc25-103">Create DNS records at GoDaddy for Microsoft</span></span>

 <span data-ttu-id="cdc25-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="cdc25-105">Wenn GoDaddy Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cdc25-105">If GoDaddy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="cdc25-106">Nachdem Sie diese Einträge bei GoDaddy hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="cdc25-106">After you add these records at GoDaddy, your domain will be set up to work with Microsoft services.</span></span>

<span data-ttu-id="cdc25-107">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="cdc25-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>

> [!NOTE]
> <span data-ttu-id="cdc25-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cdc25-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cdc25-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="cdc25-111">Add a TXT record for verification</span></span>
<span data-ttu-id="cdc25-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cdc25-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cdc25-113">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="cdc25-114">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc25-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="cdc25-117">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-117">Follow the steps below.</span></span>

1. <span data-ttu-id="cdc25-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cdc25-p104">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cdc25-121">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdc25-121">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cdc25-123">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-123">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cdc25-125">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-125">Choose **TXT (Text)** from the drop-down list.</span></span> <span data-ttu-id="cdc25-126">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    |<span data-ttu-id="cdc25-127">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cdc25-127">**Record type**</span></span> |<span data-ttu-id="cdc25-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="cdc25-128">**Host**</span></span>|<span data-ttu-id="cdc25-129">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="cdc25-129">**TXT Value**</span></span>|<span data-ttu-id="cdc25-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdc25-130">**TTL**</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdc25-131">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="cdc25-131">TXT (Text)</span></span>|@|<span data-ttu-id="cdc25-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cdc25-132">MS=ms *XXXXXXXX*</span></span><br><span data-ttu-id="cdc25-133">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cdc25-133">**Note**: This is an example.</span></span> <span data-ttu-id="cdc25-134">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cdc25-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="cdc25-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="cdc25-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="cdc25-136">1 hour</span><span class="sxs-lookup"><span data-stu-id="cdc25-136">1 hour</span></span>  <br><span data-ttu-id="cdc25-137">(Wählen Sie in der Dropdownliste einen Wert aus.)</span><span class="sxs-lookup"><span data-stu-id="cdc25-137">(Select a value from the drop-down list.)</span></span>|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. <span data-ttu-id="cdc25-139">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-139">Select **Save**.</span></span>

6. <span data-ttu-id="cdc25-140">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cdc25-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="cdc25-141">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="cdc25-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>

<span data-ttu-id="cdc25-142">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="cdc25-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cdc25-143">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="cdc25-143">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cdc25-144">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cdc25-145">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-145">On the **Setup** page, select **Start setup**.</span></span>



4. <span data-ttu-id="cdc25-146">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-146">On the **Verify domain** page, select **Verify**.</span></span>



> [!NOTE]
>  <span data-ttu-id="cdc25-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cdc25-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cdc25-150">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="cdc25-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cdc25-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cdc25-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="cdc25-152">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-152">Follow the steps below.</span></span>

1. <span data-ttu-id="cdc25-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cdc25-p108">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cdc25-156">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdc25-156">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cdc25-158">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-158">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cdc25-160">Wählen Sie in der Dropdownliste **MX (Mail Exchanger)** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-160">Choose **MX (Mail Exchanger)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. <span data-ttu-id="cdc25-162">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-162">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

    <span data-ttu-id="cdc25-163">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="cdc25-163">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="cdc25-164">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cdc25-164">**Record type**</span></span>|<span data-ttu-id="cdc25-165">**Host**</span><span class="sxs-lookup"><span data-stu-id="cdc25-165">**Host**</span></span>|<span data-ttu-id="cdc25-166">**Points to**</span><span class="sxs-lookup"><span data-stu-id="cdc25-166">**Points to**</span></span>|<span data-ttu-id="cdc25-167">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="cdc25-167">**Priority**</span></span>|<span data-ttu-id="cdc25-168">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdc25-168">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdc25-169">MX (Mail Exchanger)</span><span class="sxs-lookup"><span data-stu-id="cdc25-169">MX (Mail Exchanger)</span></span>  <br/> |@  <br/> | <span data-ttu-id="cdc25-170">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cdc25-171">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="cdc25-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="cdc25-172">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="cdc25-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cdc25-173">10  </span><span class="sxs-lookup"><span data-stu-id="cdc25-173">10</span></span>  <br/> <span data-ttu-id="cdc25-174">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="cdc25-174">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="cdc25-175">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-175">1 hour</span></span>  <br/> |

6. <span data-ttu-id="cdc25-176">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-176">Select **Save**.</span></span>

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cdc25-177">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="cdc25-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cdc25-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cdc25-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="cdc25-179">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-179">Follow the steps below.</span></span>

1. <span data-ttu-id="cdc25-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cdc25-p110">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cdc25-183">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdc25-183">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cdc25-185">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-185">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. <span data-ttu-id="cdc25-187">Wählen Sie in der Dropdownliste **CNAME (Alias)** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-187">Choose **CNAME (Alias)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. <span data-ttu-id="cdc25-189">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="cdc25-189">Create the first CNAME record.</span></span>

    <span data-ttu-id="cdc25-190">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="cdc25-191">(Wählen Sie in der Dropdownliste den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="cdc25-191">(Choose the **TTL** value from the drop-down list.)</span></span>

    |<span data-ttu-id="cdc25-192">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cdc25-192">**Record type**</span></span>|<span data-ttu-id="cdc25-193">**Host**</span><span class="sxs-lookup"><span data-stu-id="cdc25-193">**Host**</span></span>|<span data-ttu-id="cdc25-194">**Points to**</span><span class="sxs-lookup"><span data-stu-id="cdc25-194">**Points to**</span></span>|<span data-ttu-id="cdc25-195">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdc25-195">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdc25-196">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cdc25-196">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cdc25-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cdc25-197">autodiscover</span></span>  <br/> |<span data-ttu-id="cdc25-198">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-198">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="cdc25-199">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-199">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cdc25-200">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cdc25-200">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cdc25-201">sip</span><span class="sxs-lookup"><span data-stu-id="cdc25-201">sip</span></span>  <br/> |<span data-ttu-id="cdc25-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-202">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cdc25-203">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-203">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cdc25-204">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cdc25-204">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cdc25-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cdc25-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cdc25-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-206">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cdc25-207">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-207">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cdc25-208">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cdc25-208">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cdc25-209">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cdc25-209">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cdc25-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cdc25-210">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="cdc25-211">1 hour</span><span class="sxs-lookup"><span data-stu-id="cdc25-211">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cdc25-212">CNAME (Alias)</span><span class="sxs-lookup"><span data-stu-id="cdc25-212">CNAME (Alias)</span></span>  <br/> |<span data-ttu-id="cdc25-213">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cdc25-213">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cdc25-214">enterpriseenrollment.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-214">enterpriseenrollment.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="cdc25-215">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-215">1 hour</span></span>  <br/> |



6. <span data-ttu-id="cdc25-216">Wiederholen Sie diese Schritte, um den nächsten CNAME-Eintrag hinzuzufügen, bis Sie alle sechs CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cdc25-216">Repeat these steps to add the next CNAME record until you have created all six of the CNAME records.</span></span>

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cdc25-217">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="cdc25-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cdc25-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cdc25-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdc25-219">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="cdc25-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cdc25-220">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="cdc25-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cdc25-221">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cdc25-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cdc25-222">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="cdc25-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="cdc25-223">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-223">Follow the steps below.</span></span>

1. <span data-ttu-id="cdc25-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cdc25-p112">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cdc25-227">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdc25-227">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cdc25-229">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-229">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cdc25-231">Wählen Sie in der Dropdownliste **TXT (Text)** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-231">Choose **TXT (Text)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. <span data-ttu-id="cdc25-233">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-233">In the boxes for the new record, type or copy and paste the following values.</span></span>

    <span data-ttu-id="cdc25-234">(Wählen Sie in den Dropdownlisten den Wert **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="cdc25-234">(Choose the **TTL** value from the drop-down lists.)</span></span>

    |<span data-ttu-id="cdc25-235">**Record type**</span><span class="sxs-lookup"><span data-stu-id="cdc25-235">**Record type**</span></span>|<span data-ttu-id="cdc25-236">**Host**</span><span class="sxs-lookup"><span data-stu-id="cdc25-236">**Host**</span></span>|<span data-ttu-id="cdc25-237">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="cdc25-237">**TXT Value**</span></span>|<span data-ttu-id="cdc25-238">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdc25-238">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdc25-239">TXT (Text)</span><span class="sxs-lookup"><span data-stu-id="cdc25-239">TXT (Text)</span></span>  <br/> |@  <br/> |<span data-ttu-id="cdc25-240">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cdc25-240">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cdc25-241">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="cdc25-241">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cdc25-242">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-242">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. <span data-ttu-id="cdc25-244">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-244">Select **Save**.</span></span>


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cdc25-245">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cdc25-245">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cdc25-246"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cdc25-246"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="cdc25-247">Führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-247">Follow the steps below.</span></span>

1. <span data-ttu-id="cdc25-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://account.godaddy.com/products/?go_redirect=disabled) zu Ihrer Domänenseite bei GoDaddy. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cdc25-p113">To get started, go to your domains page at GoDaddy by using [this link](https://account.godaddy.com/products/?go_redirect=disabled). You'll be prompted to log in.</span></span>

    ![GoDaddy-BP-configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. <span data-ttu-id="cdc25-251">Wählen Sie unter **Domänen**die Option DNS unter der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdc25-251">Under **Domains**, select DNS under the domain that you want to edit.</span></span>

    ![GoDaddy-BP-configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. <span data-ttu-id="cdc25-253">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-253">Select **Add**.</span></span>

    ![GoDaddy-BP-configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. <span data-ttu-id="cdc25-255">Wählen Sie in der Dropdownliste **SRV (Service)** aus.</span><span class="sxs-lookup"><span data-stu-id="cdc25-255">Choose **SRV (Service)** from the drop-down list.</span></span>

    ![GoDaddy-BP-configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. <span data-ttu-id="cdc25-257">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="cdc25-257">Create the first SRV record.</span></span>

    <span data-ttu-id="cdc25-258">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-258">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>

    <span data-ttu-id="cdc25-259">(Wählen Sie in den Dropdownlisten die Werte für **Record Type** und **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="cdc25-259">(Choose the **Record type** and **TTL** values from the drop-down lists.)</span></span>

    |<span data-ttu-id="cdc25-260">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="cdc25-260">**Record type**</span></span>|<span data-ttu-id="cdc25-261">**Name**</span><span class="sxs-lookup"><span data-stu-id="cdc25-261">**Name**</span></span>|<span data-ttu-id="cdc25-262">**Target**</span><span class="sxs-lookup"><span data-stu-id="cdc25-262">**Target**</span></span>|<span data-ttu-id="cdc25-263">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="cdc25-263">**Protocol**</span></span>|<span data-ttu-id="cdc25-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="cdc25-264">**Service**</span></span>|<span data-ttu-id="cdc25-265">**Priority**</span><span class="sxs-lookup"><span data-stu-id="cdc25-265">**Priority**</span></span>|<span data-ttu-id="cdc25-266">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cdc25-266">**Weight**</span></span>|<span data-ttu-id="cdc25-267">**Port**</span><span class="sxs-lookup"><span data-stu-id="cdc25-267">**Port**</span></span>|<span data-ttu-id="cdc25-268">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cdc25-268">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cdc25-269">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="cdc25-269">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="cdc25-270">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-270">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cdc25-271">_tls</span><span class="sxs-lookup"><span data-stu-id="cdc25-271">_tls</span></span>  <br/> |<span data-ttu-id="cdc25-272">_sip</span><span class="sxs-lookup"><span data-stu-id="cdc25-272">_sip</span></span>  <br/> |<span data-ttu-id="cdc25-273">100</span><span class="sxs-lookup"><span data-stu-id="cdc25-273">100</span></span>  <br/> |<span data-ttu-id="cdc25-274">1</span><span class="sxs-lookup"><span data-stu-id="cdc25-274">1</span></span>  <br/> |<span data-ttu-id="cdc25-275">443</span><span class="sxs-lookup"><span data-stu-id="cdc25-275">443</span></span>  <br/> |<span data-ttu-id="cdc25-276">1 hour</span><span class="sxs-lookup"><span data-stu-id="cdc25-276">1 hour</span></span>  <br/> |
    |<span data-ttu-id="cdc25-277">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="cdc25-277">SRV (Service)</span></span>  <br/> |@  <br/> |<span data-ttu-id="cdc25-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdc25-278">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="cdc25-279">_tcp</span><span class="sxs-lookup"><span data-stu-id="cdc25-279">_tcp</span></span>  <br/> |<span data-ttu-id="cdc25-280">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cdc25-280">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="cdc25-281">100</span><span class="sxs-lookup"><span data-stu-id="cdc25-281">100</span></span>  <br/> |<span data-ttu-id="cdc25-282">1</span><span class="sxs-lookup"><span data-stu-id="cdc25-282">1</span></span>  <br/> |<span data-ttu-id="cdc25-283">5061</span><span class="sxs-lookup"><span data-stu-id="cdc25-283">5061</span></span>  <br/> |<span data-ttu-id="cdc25-284">1 Stunde</span><span class="sxs-lookup"><span data-stu-id="cdc25-284">1 hour</span></span>  <br/> |

    ![GoDaddy-BP-configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. <span data-ttu-id="cdc25-286">Wiederholen Sie **Schritt 5** , um den anderen SRV-Eintrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cdc25-286">Repeat **Step 5** to Create the other SRV record.</span></span>

7. <span data-ttu-id="cdc25-287">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cdc25-287">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc25-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cdc25-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
