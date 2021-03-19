---
title: Erstellen von DNS-Einträgen für Microsoft bei 1&1 IONOS
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei 1&1 IONOS für Microsoft einrichten.
ms.openlocfilehash: 8e2deab05b5ef8d8f22993d2bfdd032999ed9c39
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657996"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a><span data-ttu-id="b2a7d-103">Erstellen von DNS-Einträgen für Microsoft bei 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="b2a7d-103">Create DNS records at 1&1 IONOS for Microsoft</span></span>

 <span data-ttu-id="b2a7d-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b2a7d-105">Beachten Sie, dass 1 & 1 IONOS keine Domänen zulässt, die sowohl einen MX-Eintrag als auch einen Autoermittlungs-CNAME-Eintrag der oberen Ebene aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="b2a7d-106">Damit werden die Möglichkeiten eingeschränkt, Exchange Online für Microsoft zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-106">This limits the ways in which you can configure Exchange Online for Microsoft.</span></span> <span data-ttu-id="b2a7d-107">Es gibt eine Problemumgehung, die Sie jedoch **nur** anwenden sollten, wenn Sie bereits Erfahrung mit der Erstellung von Unterdomänen bei 1 & 1 IONOS haben.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="b2a7d-108">> Wenn Sie sich trotz der [Diensteinschränkungen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) dafür entscheiden, Ihre eigenen Microsoft-DNS-Einträge bei 1&1 IONOS zu verwalten, führen Sie die Schritte in diesem Artikel aus, um die DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-108">> If despite this [service limitation](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) you choose to manage your own Microsoft DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="b2a7d-109">Nachdem Sie diese Einträge bei 1&1 IONOS hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="b2a7d-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b2a7d-113">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b2a7d-113">Add a TXT record for verification</span></span>

<span data-ttu-id="b2a7d-p103">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a7d-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="b2a7d-118">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-118">Follow the steps below or [watch the video (start at 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
1. <span data-ttu-id="b2a7d-119">Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-119">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="b2a7d-120">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-120">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="b2a7d-121">Wählen Sie **Manage domains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-121">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b2a7d-122">Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-122">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b2a7d-123">Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-123">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b2a7d-124">Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-124">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="b2a7d-125">Geben Sie im Bereich **Add Record** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-125">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b2a7d-126">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="b2a7d-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-127">**Type**</span></span> <br/> |<span data-ttu-id="b2a7d-128">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-128">**Prefix**</span></span> <br/> |<span data-ttu-id="b2a7d-129">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-129">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="b2a7d-130">TXT</span><span class="sxs-lookup"><span data-stu-id="b2a7d-130">TXT</span></span>  <br/> |<span data-ttu-id="b2a7d-131">(Dieses Feld leer lassen)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-131">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="b2a7d-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b2a7d-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b2a7d-133">HINWEIS: Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-133">NOTE: This is an example.</span></span> <span data-ttu-id="b2a7d-134">Verwenden Sie hier Ihren spezifischen **Ziel- oder Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b2a7d-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b2a7d-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b2a7d-136">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-136">Select **Save**.</span></span>
    
8. <span data-ttu-id="b2a7d-137">Wählen Sie noch mal **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-137">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="b2a7d-138">Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-138">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="b2a7d-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b2a7d-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="b2a7d-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b2a7d-142">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b2a7d-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b2a7d-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b2a7d-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2a7d-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b2a7d-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b2a7d-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a7d-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="b2a7d-151">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-151">Follow the steps below or [watch the video (start at 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a7d-152">Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-152">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="b2a7d-153">Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-153">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="b2a7d-154">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-154">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="b2a7d-155">Wählen Sie **Manage domains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-155">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b2a7d-156">Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-156">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b2a7d-157">Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-157">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b2a7d-158">Wählen Sie im Abschnitt **MX-Einträge** im Bereich **Mail Exchanger (MX-Eintrag)** die Option **Anderer E-Mail-Server** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-158">In the **MX Records** section, in the **Mail Exchanger (MX Record)** area, select **Other mail server**.</span></span><br/><span data-ttu-id="b2a7d-159">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-159">(You may have to scroll down.)</span></span><br/><span data-ttu-id="b2a7d-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-160">![1&amp;1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="b2a7d-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-161">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="b2a7d-162">(Wenn noch keine MX-Einträge aufgeführt sind, fahren Sie mit dem nächsten Schritt fort.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-162">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="b2a7d-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-163">![1&amp;1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="b2a7d-164">Geben Sie in den Feldern für den Eintrag **MX 1** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-164">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="b2a7d-165">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-165">**MX 1**</span></span>|<span data-ttu-id="b2a7d-166">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-166">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="b2a7d-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="b2a7d-168">HINWEIS: Erhalten Sie Ihren \<domain-key\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-168">NOTE: Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="b2a7d-169">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b2a7d-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="b2a7d-170">10</span><span class="sxs-lookup"><span data-stu-id="b2a7d-170">10</span></span>  <br/> <span data-ttu-id="b2a7d-171">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-171">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | 
    
    ![1 und 1 – konfigurieren Sie 2 und 3.](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="b2a7d-173">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-173">Select **Save**.</span></span><br/><span data-ttu-id="b2a7d-174">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-174">(You may have to scroll down.)</span></span><br/><span data-ttu-id="b2a7d-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-175">![1&amp;1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="b2a7d-176">Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-176">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="b2a7d-177">![Im Dialogfeld "DNS-Einstellungen bearbeiten" die Option "Ja" auswählen](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-177">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b2a7d-178">Hinzufügen der für Microsoft erforderlichen sechs CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b2a7d-178">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b2a7d-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="b2a7d-179"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="b2a7d-180">Für 1&1 IONOS ist eine Problemumgehung erforderlich, damit Sie einen MX-Eintrag zusammen mit den CNAME-Einträgen verwenden können, die für die Microsoft-E-Mail-Dienste erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-180">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Microsoft email services.</span></span> <span data-ttu-id="b2a7d-181">Im Rahmen dieser Problemumgehung müssen Sie eine Reihe von Unterdomänen bei 1&1 IONOS erstellen und diesen die CNAME-Einträge zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-181">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b2a7d-182">Bevor Sie beginnen, sollten Sie sich vergewissern, dass Sie mindestens zwei verfügbare Unterdomänen haben.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-182">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="b2a7d-183">Wir empfehlen diese Lösung nur, wenn Sie bereits Erfahrung mit der Erstellung von Unterdomänen bei 1&1 IONOS haben.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-183">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="b2a7d-184">Einfache CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b2a7d-184">Basic CNAME records</span></span>

<span data-ttu-id="b2a7d-185">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-185">Follow the steps below or [watch the video (start at 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a7d-186">Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-186">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="b2a7d-187">Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-187">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="b2a7d-188">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-188">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="b2a7d-189">Wählen Sie **Manage domains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-189">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b2a7d-190">Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Manage Subdomains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-190">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="b2a7d-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-191">![1&amp;1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="b2a7d-192">Im nächsten Schritt erstellen Sie zwei Unterdomänen und legen einen **Alias** für jede davon fest.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-192">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="b2a7d-193">(Dies ist erforderlich, da 1&1 IONOS nur den CNAME-Eintrag auf oberster Ebene unterstützt, Microsoft erfordert jedoch mehrere CNAME-Einträge.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-193">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Microsoft requires several CNAME records.)</span></span><br/><span data-ttu-id="b2a7d-194">Zuerst erstellen Sie die Autoermittlungs-Unterdomäne.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-194">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="b2a7d-195">Wählen Sie im Abschnitt **Subdomain Overview** den Befehl **Create Subdomain** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-195">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="b2a7d-p113">Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="b2a7d-199">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-199">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-200">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-200">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b2a7d-201">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b2a7d-201">autodiscover</span></span>  <br/> |<span data-ttu-id="b2a7d-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-202">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="b2a7d-204">Wählen Sie **Create Subdomain** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-204">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="b2a7d-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-205">![1&amp;1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="b2a7d-206">Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **autodiscover**, die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für die Unterdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-206">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="b2a7d-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-207">![1&amp;1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="b2a7d-208">Wählen Sie im Bereich **Subdomain Settings** die Option **Edit DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-208">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="b2a7d-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-209">![1&amp;1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="b2a7d-210">Wählen Sie im Abschnitt **A/AAAA Records (IP Addresses)** im Bereich **IP address (A Record)** die Option **CNAME** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-210">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="b2a7d-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-211">![1&amp;1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="b2a7d-212">Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-212">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="b2a7d-213">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-213">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-214">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-214">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b2a7d-215">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b2a7d-215">autodiscover</span></span>  <br/> |<span data-ttu-id="b2a7d-216">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-216">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="b2a7d-218">Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-218">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="b2a7d-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-219">![1&amp;1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="b2a7d-220">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-220">Select **Save**.</span></span><br/><span data-ttu-id="b2a7d-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-221">![1&amp;1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="b2a7d-222">Zusätzliche CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b2a7d-222">Additional CNAME records</span></span>

<span data-ttu-id="b2a7d-p114">Die zusätzlichen CNAME-Einträge, die mit den folgenden Schritten erstellt werden, aktivieren die Skype for Business Online-Dienste. Führen Sie dieselben Schritte wie beim Erstellen der beiden vorherigen CNAME-Einträge durch.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="b2a7d-225">Erstellen Sie die dritte Unterdomäne (Lyncdiscover).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-225">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="b2a7d-226">Wählen Sie im Abschnitt **Subdomain Overview** die Option **Create Subdomain** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-226">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="b2a7d-p115">Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="b2a7d-229">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-229">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-230">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-230">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b2a7d-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b2a7d-231">lyncdiscover</span></span>   |<span data-ttu-id="b2a7d-232">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-232">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="b2a7d-233">Wählen Sie **Create Subdomain** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-233">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="b2a7d-234">Wählen Sie auf der Seite **Domain Center** die Option **Manage Subdomains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-234">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="b2a7d-235">Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **lyncdiscover**, die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für die Unterdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-235">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="b2a7d-236">Wählen Sie im Bereich **Subdomain Settings** die Option **Edit DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-236">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="b2a7d-237">Wählen Sie im Abschnitt **A/AAAA Records (IP Addresses)** im Bereich **IP address (A Record)** die Option **CNAME** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-237">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="b2a7d-238">Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-238">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="b2a7d-239">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-239">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-240">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-240">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b2a7d-241">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b2a7d-241">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b2a7d-242">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-242">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="b2a7d-243">Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**, und wählen Sie dann **Save** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-243">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="b2a7d-244">Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-244">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="b2a7d-245">Erstellen der vierten Unterdomäne (SIP):</span><span class="sxs-lookup"><span data-stu-id="b2a7d-245">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="b2a7d-246">Wählen Sie im Abschnitt **Subdomain Overview** den Befehl **Create Subdomain** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-246">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="b2a7d-p116">Geben Sie im Feld **Create Subdomain** der neuen Unterdomäne nur den Wert unter **Create Subdomain** aus der folgenden Tabelle ein, oder kopieren Sie ihn, damit Sie ihn einfügen können. (Der Wert für **Alias** wird in einem späteren Schritt hinzugefügt.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="b2a7d-249">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-249">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-250">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-250">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b2a7d-251">sip</span><span class="sxs-lookup"><span data-stu-id="b2a7d-251">sip</span></span>  <br/> |<span data-ttu-id="b2a7d-252">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-252">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="b2a7d-253">Wählen Sie **Create Subdomain** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-253">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="b2a7d-254">Wählen Sie auf der Seite **Domain Center** die Option **Manage Subdomains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-254">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="b2a7d-255">Suchen Sie im Abschnitt **Subdomain Overview** die Unterdomäne **sip**, die Sie soeben erstellt haben, und wählen Sie dann das Steuerelement **Panel (v)** für die Unterdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-255">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="b2a7d-256">Wählen Sie im Bereich **Subdomain Settings** die Option **Edit DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-256">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="b2a7d-257">Wählen Sie im Abschnitt **A/AAAA Records (IP Addresses)** im Bereich **IP address (A Record)** die Option **CNAME** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-257">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="b2a7d-258">Geben Sie im Feld **Alias:** nur den Wert für **Alias** aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-258">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="b2a7d-259">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-259">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-260">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="b2a7d-261">sip</span><span class="sxs-lookup"><span data-stu-id="b2a7d-261">sip</span></span>  <br/> |<span data-ttu-id="b2a7d-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-262">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="b2a7d-263">Aktivieren Sie das Kontrollkästchen für den Haftungsausschluss **I am aware**, und wählen Sie dann **Save** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-263">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="b2a7d-264">Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-264">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="b2a7d-265">Für MDM erforderliche CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b2a7d-265">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2a7d-266">Führen Sie das gleiche Verfahren wie bei den anderen vier CNAME-Einträgen aus, doch geben Sie dabei die Werte aus der folgenden Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-266">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="b2a7d-267">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-267">**Create Subdomain**</span></span>|<span data-ttu-id="b2a7d-268">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-268">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2a7d-269">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b2a7d-269">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b2a7d-270">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b2a7d-270">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="b2a7d-271">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b2a7d-271">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b2a7d-272">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-272">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b2a7d-273">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b2a7d-273">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2a7d-274">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-274">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b2a7d-275">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-275">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b2a7d-276">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="b2a7d-276">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b2a7d-277">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-277">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="b2a7d-278">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="b2a7d-278">Need examples?</span></span> <span data-ttu-id="b2a7d-279">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-279">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="b2a7d-280">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.yml) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-280">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
<span data-ttu-id="b2a7d-281">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-281">Follow the steps below or [watch the video (start at 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a7d-282">Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-282">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="b2a7d-283">Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-283">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="b2a7d-284">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-284">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="b2a7d-285">Wählen Sie **Manage domains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-285">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b2a7d-286">Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** (**v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-286">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b2a7d-287">Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-287">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b2a7d-288">Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-288">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="b2a7d-289">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-289">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="b2a7d-290">Geben Sie im Bereich **Add Record** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-290">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="b2a7d-291">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-291">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="b2a7d-292">**Type**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-292">**Type**</span></span>|<span data-ttu-id="b2a7d-293">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-293">**Prefix**</span></span>|<span data-ttu-id="b2a7d-294">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-294">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="b2a7d-295">TXT</span><span class="sxs-lookup"><span data-stu-id="b2a7d-295">TXT</span></span>  <br/> |<span data-ttu-id="b2a7d-296">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-296">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b2a7d-297">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b2a7d-297">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b2a7d-298">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-298">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT record (TXT-Eintrag)](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="b2a7d-300">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-300">Select **Save**.</span></span><br/><span data-ttu-id="b2a7d-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-301">![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="b2a7d-302">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-302">Select **Save**.</span></span><br/><span data-ttu-id="b2a7d-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-303">![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="b2a7d-304">Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-304">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="b2a7d-305">![Im Dialogfeld "DNS-Einstellungen bearbeiten" die Option "Ja" auswählen](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-305">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b2a7d-306">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="b2a7d-306">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="b2a7d-307">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-307">Follow the steps below or [watch the video (start at 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a7d-308">Hinweis: Wenn Sie sich bei 1und1.de registriert haben, [melden Sie sich hier an](https://go.microsoft.com/fwlink/?linkid=859152).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-308">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="b2a7d-309">Im ersten Schritt navigieren Sie über [diesen Link](https://my.1and1.com/) zu Ihrer Domänenseite bei 1&1 IONOS.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-309">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="b2a7d-310">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-310">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="b2a7d-311">Wählen Sie **Manage domains** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-311">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="b2a7d-312">Suchen Sie auf der Seite **Domain Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-312">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="b2a7d-313">Wählen Sie im Bereich **Domain Settings** die Option **DNS-Einstellungen bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-313">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="b2a7d-314">Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-314">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="b2a7d-315">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-315">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="b2a7d-316">Geben Sie im Bereich **Eintrag hinzufügen** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-316">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="b2a7d-317">(Wählen Sie in der Dropdownliste die Werte für **Type** und **TTL** aus.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-317">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="b2a7d-318">**Type**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-318">**Type**</span></span>|<span data-ttu-id="b2a7d-319">**Service**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-319">**Service**</span></span>|<span data-ttu-id="b2a7d-320">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-320">**Protocol**</span></span>|<span data-ttu-id="b2a7d-321">**Name**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-321">**Name**</span></span>|<span data-ttu-id="b2a7d-322">**Host**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-322">**Host**</span></span>|<span data-ttu-id="b2a7d-323">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-323">**Priority**</span></span>|<span data-ttu-id="b2a7d-324">**Weight**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-324">**Weight**</span></span>|<span data-ttu-id="b2a7d-325">**Port**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-325">**Port**</span></span>|<span data-ttu-id="b2a7d-326">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b2a7d-326">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b2a7d-327">SRV</span><span class="sxs-lookup"><span data-stu-id="b2a7d-327">SRV</span></span>  <br/> |<span data-ttu-id="b2a7d-328">sip</span><span class="sxs-lookup"><span data-stu-id="b2a7d-328">sip</span></span>  <br/> |<span data-ttu-id="b2a7d-329">tls</span><span class="sxs-lookup"><span data-stu-id="b2a7d-329">tls</span></span>  <br/> |<span data-ttu-id="b2a7d-330">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-330">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b2a7d-331">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-331">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b2a7d-332">100</span><span class="sxs-lookup"><span data-stu-id="b2a7d-332">100</span></span>  <br/> |<span data-ttu-id="b2a7d-333">1</span><span class="sxs-lookup"><span data-stu-id="b2a7d-333">1</span></span>  <br/> |<span data-ttu-id="b2a7d-334">443</span><span class="sxs-lookup"><span data-stu-id="b2a7d-334">443</span></span>  <br/> |<span data-ttu-id="b2a7d-335">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-335">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="b2a7d-336">SRV</span><span class="sxs-lookup"><span data-stu-id="b2a7d-336">SRV</span></span>  <br/> |<span data-ttu-id="b2a7d-337">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="b2a7d-337">sipfederationtls</span></span>  <br/> |<span data-ttu-id="b2a7d-338">tcp</span><span class="sxs-lookup"><span data-stu-id="b2a7d-338">tcp</span></span>  <br/> |<span data-ttu-id="b2a7d-339">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-339">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="b2a7d-340">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b2a7d-340">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="b2a7d-341">100</span><span class="sxs-lookup"><span data-stu-id="b2a7d-341">100</span></span>  <br/> |<span data-ttu-id="b2a7d-342">1</span><span class="sxs-lookup"><span data-stu-id="b2a7d-342">1</span></span>  <br/> |<span data-ttu-id="b2a7d-343">5061</span><span class="sxs-lookup"><span data-stu-id="b2a7d-343">5061</span></span>  <br/> |<span data-ttu-id="b2a7d-344">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-344">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="b2a7d-346">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-346">Select **Save**.</span></span> <br/><span data-ttu-id="b2a7d-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-347">![1&amp;1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="b2a7d-348">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-348">Select **Save**.</span></span> <br/><span data-ttu-id="b2a7d-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-349">![1&amp;1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="b2a7d-350">Wählen Sie im Dialogfeld **Edit DNS Settings** die Option **Yes** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-350">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="b2a7d-351">![Im Dialogfeld "DNS-Einstellungen bearbeiten" die Option "Ja" auswählen](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="b2a7d-351">![Selecting Yes in the Edit DNS Settings dialog box](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="b2a7d-352">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-352">Add the other SRV record.</span></span> <br/><span data-ttu-id="b2a7d-353">Wählen Sie im Abschnitt **TXT and SRV Records** die Option **Add Record** aus.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-353">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="b2a7d-354">Erstellen Sie im Bereich **Add New DNS Record** einen Eintrag mit den Werten der zweiten Zeile in der Tabelle. Wählen Sie dann **Add**, **Save** und **Yes** aus, um den Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b2a7d-354">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b2a7d-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b2a7d-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
