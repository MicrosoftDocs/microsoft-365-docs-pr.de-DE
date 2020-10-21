---
title: Erstellen von DNS-Einträgen bei Cloudflare für Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Cloudflare für Microsoft einrichten.
ms.openlocfilehash: 301ed156584d9a9a2b84b88db7d6969ade5b34a2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646151"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="94683-103">Erstellen von DNS-Einträgen bei Cloudflare für Microsoft</span><span class="sxs-lookup"><span data-stu-id="94683-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="94683-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="94683-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="94683-105">[] Wenn Cloudflare Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="94683-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="94683-106">Nachdem Sie diese Einträge bei Cloudflare hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="94683-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="94683-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94683-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="94683-110">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="94683-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="94683-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="94683-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="94683-112">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="94683-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="94683-113">Als Sie sich bei Cloudflare registriert haben, haben Sie mithilfe des **Setup**-Prozesses von Cloudflare eine Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="94683-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="94683-114">Die Domäne, die Sie hinzugefügt haben, wurde von Cloudflare oder einer separaten Domänenregistrierungsstelle erworben.</span><span class="sxs-lookup"><span data-stu-id="94683-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="94683-115">Um DNS-Einträge für Ihre Domäne in Microsoft 365 zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Cloudflare-Namenserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="94683-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="94683-116">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="94683-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="94683-117">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="94683-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="94683-118">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="94683-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="94683-119">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="94683-119">First nameserver</span></span>  <br/> |<span data-ttu-id="94683-120">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="94683-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="94683-121">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="94683-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="94683-122">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="94683-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="94683-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="94683-123">You should use at least two name server records.</span></span> <span data-ttu-id="94683-124">Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="94683-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="94683-125">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="94683-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="94683-126">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="94683-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="94683-127">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="94683-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="94683-128">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="94683-128">Add a TXT record for verification</span></span>
<span data-ttu-id="94683-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="94683-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="94683-p105">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="94683-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94683-p106">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="94683-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="94683-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="94683-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="94683-136">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94683-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="94683-137">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="94683-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="94683-138">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="94683-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="94683-139">**Typ**</span><span class="sxs-lookup"><span data-stu-id="94683-139">**Type**</span></span>|<span data-ttu-id="94683-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="94683-140">**Name**</span></span>|<span data-ttu-id="94683-141">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="94683-141">**Automatic TTL**</span></span>|<span data-ttu-id="94683-142">**Content**</span><span class="sxs-lookup"><span data-stu-id="94683-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="94683-143">TXT</span><span class="sxs-lookup"><span data-stu-id="94683-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="94683-144">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-144">30 minutes</span></span>  <br/> |<span data-ttu-id="94683-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="94683-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="94683-146">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="94683-146">**Note:** This is an example.</span></span> <span data-ttu-id="94683-147">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="94683-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="94683-148">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="94683-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="94683-149">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94683-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="94683-150">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="94683-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="94683-151">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und suchen nach dem Datensatz.</span><span class="sxs-lookup"><span data-stu-id="94683-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="94683-152">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="94683-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="94683-153">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="94683-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="94683-154">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="94683-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="94683-155">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="94683-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="94683-156">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="94683-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="94683-p109">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94683-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="94683-160">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="94683-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="94683-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="94683-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="94683-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="94683-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="94683-164">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94683-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="94683-165">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="94683-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="94683-166">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="94683-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="94683-167">**Typ**</span><span class="sxs-lookup"><span data-stu-id="94683-167">**Type**</span></span>|<span data-ttu-id="94683-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="94683-168">**Name**</span></span>|<span data-ttu-id="94683-169">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="94683-169">**Mail server**</span></span>|<span data-ttu-id="94683-170">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="94683-170">**Priority**</span></span>|<span data-ttu-id="94683-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="94683-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94683-172">MX</span><span class="sxs-lookup"><span data-stu-id="94683-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="94683-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="94683-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="94683-174">**Hinweis:** Holen Sie sich Ihr  *\<domain-key\>*  Microsoft 365-Konto.</span><span class="sxs-lookup"><span data-stu-id="94683-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="94683-175">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="94683-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="94683-176">1</span><span class="sxs-lookup"><span data-stu-id="94683-176">1</span></span>  <br/> <span data-ttu-id="94683-177">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="94683-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="94683-178">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="94683-179">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94683-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="94683-180">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie einen davon durch Klicken auf das Symbol **Löschen (X)**.</span><span class="sxs-lookup"><span data-stu-id="94683-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="94683-181">Wählen Sie im Dialogfeld Bestätigung die Option **Löschen** aus, um die Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="94683-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="94683-182">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="94683-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="94683-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="94683-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="94683-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="94683-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="94683-186">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94683-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="94683-187">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="94683-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="94683-188">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="94683-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="94683-189">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="94683-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="94683-190">**Typ**</span><span class="sxs-lookup"><span data-stu-id="94683-190">**Type**</span></span>|<span data-ttu-id="94683-191">**Name**</span><span class="sxs-lookup"><span data-stu-id="94683-191">**Name**</span></span>|<span data-ttu-id="94683-192">**Target**</span><span class="sxs-lookup"><span data-stu-id="94683-192">**Target**</span></span>|<span data-ttu-id="94683-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="94683-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94683-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="94683-194">CNAME</span></span>  <br/> |<span data-ttu-id="94683-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="94683-195">autodiscover</span></span>  <br/> |<span data-ttu-id="94683-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="94683-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="94683-197">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="94683-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="94683-198">CNAME</span></span>  <br/> |<span data-ttu-id="94683-199">sip</span><span class="sxs-lookup"><span data-stu-id="94683-199">sip</span></span>  <br/> |<span data-ttu-id="94683-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94683-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="94683-201">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="94683-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="94683-202">CNAME</span></span>  <br/> |<span data-ttu-id="94683-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="94683-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="94683-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94683-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="94683-205">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="94683-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="94683-206">CNAME</span></span>  <br/> |<span data-ttu-id="94683-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="94683-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="94683-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="94683-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="94683-209">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="94683-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="94683-210">CNAME</span></span>  <br/> |<span data-ttu-id="94683-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="94683-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="94683-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="94683-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="94683-213">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="94683-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="94683-214">CNAME</span></span>  <br/> |<span data-ttu-id="94683-215">msoid</span><span class="sxs-lookup"><span data-stu-id="94683-215">msoid</span></span>  <br/> |<span data-ttu-id="94683-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="94683-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="94683-217">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="94683-218">Wählen Sie das Symbol für den **DNS-Datenverkehr** (Orange Cloud) aus, um die Cloudflare-Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="94683-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="94683-219">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94683-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="94683-220">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="94683-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="94683-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="94683-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="94683-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="94683-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="94683-223">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="94683-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="94683-224">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="94683-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="94683-225">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="94683-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="94683-226">sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="94683-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="94683-227">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="94683-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="94683-228">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="94683-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="94683-229">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94683-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="94683-230">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="94683-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="94683-231">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="94683-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="94683-232">**Typ**</span><span class="sxs-lookup"><span data-stu-id="94683-232">**Type**</span></span>|<span data-ttu-id="94683-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="94683-233">**Name**</span></span>|<span data-ttu-id="94683-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="94683-234">**TTL**</span></span>|<span data-ttu-id="94683-235">**Content**</span><span class="sxs-lookup"><span data-stu-id="94683-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94683-236">TXT</span><span class="sxs-lookup"><span data-stu-id="94683-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="94683-237">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-237">30 minutes</span></span>  <br/> |<span data-ttu-id="94683-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="94683-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="94683-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="94683-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="94683-240">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94683-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="94683-241">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="94683-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="94683-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="94683-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="94683-243">Beachten Sie, dass Cloudflare für die bereitstellungdieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="94683-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="94683-244">Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Cloudflare-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Cloudflare-Community](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="94683-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="94683-245">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="94683-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="94683-246">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="94683-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="94683-247">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94683-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="94683-248">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="94683-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="94683-249">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="94683-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="94683-250">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der ersten Zeile der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="94683-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="94683-251">**Type**</span><span class="sxs-lookup"><span data-stu-id="94683-251">**Type**</span></span>|<span data-ttu-id="94683-252">**Service**</span><span class="sxs-lookup"><span data-stu-id="94683-252">**Service**</span></span>|<span data-ttu-id="94683-253">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="94683-253">**Protocol**</span></span>|<span data-ttu-id="94683-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="94683-254">**Name**</span></span>|<span data-ttu-id="94683-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="94683-255">**TTL**</span></span>|<span data-ttu-id="94683-256">**Priority**</span><span class="sxs-lookup"><span data-stu-id="94683-256">**Priority**</span></span>|<span data-ttu-id="94683-257">**Weight**</span><span class="sxs-lookup"><span data-stu-id="94683-257">**Weight**</span></span>|<span data-ttu-id="94683-258">**Port**</span><span class="sxs-lookup"><span data-stu-id="94683-258">**Port**</span></span>|<span data-ttu-id="94683-259">**Target**</span><span class="sxs-lookup"><span data-stu-id="94683-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="94683-260">SRV</span><span class="sxs-lookup"><span data-stu-id="94683-260">SRV</span></span>|<span data-ttu-id="94683-261">_sip</span><span class="sxs-lookup"><span data-stu-id="94683-261">_sip</span></span> |<span data-ttu-id="94683-262">TLS</span><span class="sxs-lookup"><span data-stu-id="94683-262">TLS</span></span> |<span data-ttu-id="94683-263">Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="94683-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="94683-264">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-264">30 minutes</span></span> | <span data-ttu-id="94683-265">100</span><span class="sxs-lookup"><span data-stu-id="94683-265">100</span></span>|<span data-ttu-id="94683-266">1</span><span class="sxs-lookup"><span data-stu-id="94683-266">1</span></span> |<span data-ttu-id="94683-267">443</span><span class="sxs-lookup"><span data-stu-id="94683-267">443</span></span> |<span data-ttu-id="94683-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94683-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="94683-269">SRV</span><span class="sxs-lookup"><span data-stu-id="94683-269">SRV</span></span>|<span data-ttu-id="94683-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="94683-270">_sipfederationtls</span></span> | <span data-ttu-id="94683-271">TCP</span><span class="sxs-lookup"><span data-stu-id="94683-271">TCP</span></span>|<span data-ttu-id="94683-272">Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="94683-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="94683-273">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="94683-273">30 minutes</span></span> |<span data-ttu-id="94683-274">100</span><span class="sxs-lookup"><span data-stu-id="94683-274">100</span></span> |<span data-ttu-id="94683-275">1</span><span class="sxs-lookup"><span data-stu-id="94683-275">1</span></span> |<span data-ttu-id="94683-276">5061</span><span class="sxs-lookup"><span data-stu-id="94683-276">5061</span></span> | <span data-ttu-id="94683-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="94683-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="94683-278">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="94683-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="94683-279">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="94683-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="94683-p117">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="94683-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
