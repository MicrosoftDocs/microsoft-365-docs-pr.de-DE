---
title: Erstellen von DNS-Einträgen bei Cloudflare für Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Cloudflare für Microsoft einrichten.
ms.openlocfilehash: ccd629dfdec24e509144c205b748a883cb65d554
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919627"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="934d7-103">Erstellen von DNS-Einträgen bei Cloudflare für Microsoft</span><span class="sxs-lookup"><span data-stu-id="934d7-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="934d7-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="934d7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="934d7-105">[] Wenn Cloudflare Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="934d7-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="934d7-106">Nachdem Sie diese Einträge bei Cloudflare hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="934d7-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="934d7-107">Informationen zu Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="934d7-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="934d7-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="934d7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="934d7-111">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="934d7-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="934d7-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="934d7-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="934d7-113">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="934d7-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="934d7-114">Als Sie sich bei Cloudflare registriert haben, haben Sie mithilfe des **Setup**-Prozesses von Cloudflare eine Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="934d7-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="934d7-115">Die Domäne, die Sie hinzugefügt haben, wurde von Cloudflare oder einer separaten Domänenregistrierungsstelle erworben.</span><span class="sxs-lookup"><span data-stu-id="934d7-115">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="934d7-116">Um DNS-Einträge für Ihre Domäne in Microsoft 365 zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Cloudflare-Namenserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="934d7-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="934d7-117">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="934d7-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="934d7-118">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="934d7-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="934d7-119">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="934d7-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="934d7-120">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="934d7-120">First nameserver</span></span>  <br/> |<span data-ttu-id="934d7-121">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="934d7-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="934d7-122">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="934d7-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="934d7-123">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="934d7-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="934d7-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="934d7-124">You should use at least two name server records.</span></span> <span data-ttu-id="934d7-125">Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="934d7-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="934d7-126">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="934d7-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="934d7-127">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="934d7-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="934d7-128">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="934d7-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="934d7-129">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="934d7-129">Add a TXT record for verification</span></span>
<span data-ttu-id="934d7-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="934d7-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="934d7-p105">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="934d7-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="934d7-p106">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="934d7-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="934d7-135">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="934d7-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="934d7-136">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="934d7-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="934d7-137">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="934d7-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="934d7-138">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="934d7-139">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="934d7-140">**Typ**</span><span class="sxs-lookup"><span data-stu-id="934d7-140">**Type**</span></span>|<span data-ttu-id="934d7-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="934d7-141">**Name**</span></span>|<span data-ttu-id="934d7-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="934d7-142">**Automatic TTL**</span></span>|<span data-ttu-id="934d7-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="934d7-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="934d7-144">TXT</span><span class="sxs-lookup"><span data-stu-id="934d7-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="934d7-145">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-145">30 minutes</span></span>  <br/> |<span data-ttu-id="934d7-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="934d7-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="934d7-147">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="934d7-147">**Note:** This is an example.</span></span> <span data-ttu-id="934d7-148">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="934d7-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="934d7-149">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="934d7-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="934d7-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="934d7-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="934d7-151">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="934d7-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="934d7-152">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und suchen nach dem Datensatz.</span><span class="sxs-lookup"><span data-stu-id="934d7-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="934d7-153">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="934d7-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="934d7-154">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="934d7-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="934d7-155">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="934d7-156">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="934d7-157">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="934d7-p109">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="934d7-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="934d7-161">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="934d7-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="934d7-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="934d7-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="934d7-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="934d7-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="934d7-165">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="934d7-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="934d7-166">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="934d7-167">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="934d7-168">**Typ**</span><span class="sxs-lookup"><span data-stu-id="934d7-168">**Type**</span></span>|<span data-ttu-id="934d7-169">**Name**</span><span class="sxs-lookup"><span data-stu-id="934d7-169">**Name**</span></span>|<span data-ttu-id="934d7-170">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="934d7-170">**Mail server**</span></span>|<span data-ttu-id="934d7-171">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="934d7-171">**Priority**</span></span>|<span data-ttu-id="934d7-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="934d7-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="934d7-173">MX</span><span class="sxs-lookup"><span data-stu-id="934d7-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="934d7-174">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="934d7-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="934d7-175">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Microsoft 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="934d7-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="934d7-176">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="934d7-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="934d7-177">1</span><span class="sxs-lookup"><span data-stu-id="934d7-177">1</span></span>  <br/> <span data-ttu-id="934d7-178">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="934d7-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="934d7-179">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="934d7-180">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="934d7-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="934d7-181">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie einen davon durch Klicken auf das Symbol **Löschen (X)**.</span><span class="sxs-lookup"><span data-stu-id="934d7-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="934d7-182">Wählen Sie im Dialogfeld Bestätigung die Option **Löschen** aus, um die Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="934d7-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="934d7-183">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="934d7-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="934d7-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="934d7-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="934d7-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="934d7-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="934d7-187">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="934d7-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="934d7-188">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="934d7-189">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="934d7-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="934d7-190">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="934d7-191">**Typ**</span><span class="sxs-lookup"><span data-stu-id="934d7-191">**Type**</span></span>|<span data-ttu-id="934d7-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="934d7-192">**Name**</span></span>|<span data-ttu-id="934d7-193">**Target**</span><span class="sxs-lookup"><span data-stu-id="934d7-193">**Target**</span></span>|<span data-ttu-id="934d7-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="934d7-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="934d7-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="934d7-195">CNAME</span></span>  <br/> |<span data-ttu-id="934d7-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="934d7-196">autodiscover</span></span>  <br/> |<span data-ttu-id="934d7-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="934d7-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="934d7-198">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="934d7-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="934d7-199">CNAME</span></span>  <br/> |<span data-ttu-id="934d7-200">sip</span><span class="sxs-lookup"><span data-stu-id="934d7-200">sip</span></span>  <br/> |<span data-ttu-id="934d7-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="934d7-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="934d7-202">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="934d7-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="934d7-203">CNAME</span></span>  <br/> |<span data-ttu-id="934d7-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="934d7-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="934d7-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="934d7-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="934d7-206">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="934d7-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="934d7-207">CNAME</span></span>  <br/> |<span data-ttu-id="934d7-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="934d7-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="934d7-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="934d7-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="934d7-210">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="934d7-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="934d7-211">CNAME</span></span>  <br/> |<span data-ttu-id="934d7-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="934d7-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="934d7-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="934d7-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="934d7-214">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="934d7-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="934d7-215">CNAME</span></span>  <br/> |<span data-ttu-id="934d7-216">msoid</span><span class="sxs-lookup"><span data-stu-id="934d7-216">msoid</span></span>  <br/> |<span data-ttu-id="934d7-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="934d7-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="934d7-218">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="934d7-219">Wählen Sie das Symbol für den **DNS-Datenverkehr** (Orange Cloud) aus, um die Cloudflare-Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="934d7-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="934d7-220">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="934d7-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="934d7-221">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="934d7-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="934d7-222">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="934d7-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="934d7-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="934d7-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="934d7-224">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="934d7-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="934d7-225">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="934d7-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="934d7-226">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="934d7-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="934d7-227">sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="934d7-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="934d7-228">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="934d7-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="934d7-229">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="934d7-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="934d7-230">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="934d7-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="934d7-231">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="934d7-232">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="934d7-233">**Typ**</span><span class="sxs-lookup"><span data-stu-id="934d7-233">**Type**</span></span>|<span data-ttu-id="934d7-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="934d7-234">**Name**</span></span>|<span data-ttu-id="934d7-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="934d7-235">**TTL**</span></span>|<span data-ttu-id="934d7-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="934d7-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="934d7-237">TXT</span><span class="sxs-lookup"><span data-stu-id="934d7-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="934d7-238">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-238">30 minutes</span></span>  <br/> |<span data-ttu-id="934d7-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="934d7-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="934d7-240">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="934d7-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="934d7-241">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="934d7-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="934d7-242">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="934d7-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="934d7-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="934d7-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="934d7-244">Beachten Sie, dass Cloudflare für die bereitstellungdieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="934d7-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="934d7-245">Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Cloudflare-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Cloudflare-Community](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="934d7-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="934d7-246">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="934d7-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="934d7-247">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="934d7-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="934d7-248">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="934d7-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="934d7-249">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="934d7-250">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="934d7-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="934d7-251">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der ersten Zeile der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="934d7-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="934d7-252">**Type**</span><span class="sxs-lookup"><span data-stu-id="934d7-252">**Type**</span></span>|<span data-ttu-id="934d7-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="934d7-253">**Service**</span></span>|<span data-ttu-id="934d7-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="934d7-254">**Protocol**</span></span>|<span data-ttu-id="934d7-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="934d7-255">**Name**</span></span>|<span data-ttu-id="934d7-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="934d7-256">**TTL**</span></span>|<span data-ttu-id="934d7-257">**Priority**</span><span class="sxs-lookup"><span data-stu-id="934d7-257">**Priority**</span></span>|<span data-ttu-id="934d7-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="934d7-258">**Weight**</span></span>|<span data-ttu-id="934d7-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="934d7-259">**Port**</span></span>|<span data-ttu-id="934d7-260">**Target**</span><span class="sxs-lookup"><span data-stu-id="934d7-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="934d7-261">SRV</span><span class="sxs-lookup"><span data-stu-id="934d7-261">SRV</span></span>|<span data-ttu-id="934d7-262">_sip</span><span class="sxs-lookup"><span data-stu-id="934d7-262">_sip</span></span> |<span data-ttu-id="934d7-263">TLS</span><span class="sxs-lookup"><span data-stu-id="934d7-263">TLS</span></span> |<span data-ttu-id="934d7-264">Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="934d7-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="934d7-265">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-265">30 minutes</span></span> | <span data-ttu-id="934d7-266">100</span><span class="sxs-lookup"><span data-stu-id="934d7-266">100</span></span>|<span data-ttu-id="934d7-267">1</span><span class="sxs-lookup"><span data-stu-id="934d7-267">1</span></span> |<span data-ttu-id="934d7-268">443</span><span class="sxs-lookup"><span data-stu-id="934d7-268">443</span></span> |<span data-ttu-id="934d7-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="934d7-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="934d7-270">SRV</span><span class="sxs-lookup"><span data-stu-id="934d7-270">SRV</span></span>|<span data-ttu-id="934d7-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="934d7-271">_sipfederationtls</span></span> | <span data-ttu-id="934d7-272">TCP</span><span class="sxs-lookup"><span data-stu-id="934d7-272">TCP</span></span>|<span data-ttu-id="934d7-273">Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="934d7-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="934d7-274">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="934d7-274">30 minutes</span></span> |<span data-ttu-id="934d7-275">100</span><span class="sxs-lookup"><span data-stu-id="934d7-275">100</span></span> |<span data-ttu-id="934d7-276">1</span><span class="sxs-lookup"><span data-stu-id="934d7-276">1</span></span> |<span data-ttu-id="934d7-277">5061</span><span class="sxs-lookup"><span data-stu-id="934d7-277">5061</span></span> | <span data-ttu-id="934d7-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="934d7-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="934d7-279">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="934d7-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="934d7-280">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="934d7-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="934d7-p117">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="934d7-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
