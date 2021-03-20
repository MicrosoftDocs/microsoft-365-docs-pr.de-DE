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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste bei Cloudflare für Microsoft einrichten.
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910378"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="9933d-103">Erstellen von DNS-Einträgen bei Cloudflare für Microsoft</span><span class="sxs-lookup"><span data-stu-id="9933d-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="9933d-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="9933d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9933d-105">[] Wenn Cloudflare Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="9933d-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9933d-106">Nachdem Sie diese Datensätze bei Cloudflare hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9933d-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="9933d-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9933d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9933d-110">Ändern der Nameservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="9933d-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9933d-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9933d-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9933d-112">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="9933d-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9933d-113">Als Sie sich bei Cloudflare registriert haben, haben Sie mithilfe des **Setup**-Prozesses von Cloudflare eine Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9933d-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="9933d-114">Die hinzugefügte Domäne wurde von Cloudflare oder einer separaten Domänenregistrierungsstelle erworben.</span><span class="sxs-lookup"><span data-stu-id="9933d-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="9933d-115">Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Microsoft 365 müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle so ändern, dass sie die Namenserver von Cloudflare verwenden.</span><span class="sxs-lookup"><span data-stu-id="9933d-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="9933d-116">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9933d-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9933d-117">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="9933d-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9933d-118">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9933d-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9933d-119">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="9933d-119">First nameserver</span></span>  <br/> |<span data-ttu-id="9933d-120">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="9933d-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="9933d-121">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="9933d-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="9933d-122">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="9933d-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="9933d-123">Verwenden Sie mindestens zwei Nameservereinträge.</span><span class="sxs-lookup"><span data-stu-id="9933d-123">You should use at least two name server records.</span></span> <span data-ttu-id="9933d-124">Wenn andere Namenserver aufgelistet sind, sollten Sie sie löschen.</span><span class="sxs-lookup"><span data-stu-id="9933d-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="9933d-125">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="9933d-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9933d-126">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9933d-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="9933d-127">Dann sind Ihre Microsoft-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9933d-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9933d-128">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="9933d-128">Add a TXT record for verification</span></span>
<span data-ttu-id="9933d-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9933d-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9933d-p105">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="9933d-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9933d-p106">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="9933d-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9933d-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="9933d-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9933d-136">Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9933d-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9933d-137">Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**</span><span class="sxs-lookup"><span data-stu-id="9933d-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9933d-138">Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="9933d-139">Typ</span><span class="sxs-lookup"><span data-stu-id="9933d-139">Type</span></span> | <span data-ttu-id="9933d-140">Name</span><span class="sxs-lookup"><span data-stu-id="9933d-140">Name</span></span> | <span data-ttu-id="9933d-141">Automatic TTL</span><span class="sxs-lookup"><span data-stu-id="9933d-141">Automatic TTL</span></span> | <span data-ttu-id="9933d-142">Inhalt</span><span class="sxs-lookup"><span data-stu-id="9933d-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="9933d-143">TXT</span><span class="sxs-lookup"><span data-stu-id="9933d-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9933d-144">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-144">30 minutes</span></span>  <br/> |<span data-ttu-id="9933d-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9933d-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9933d-146">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="9933d-146">**Note:** This is an example.</span></span> <span data-ttu-id="9933d-147">Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9933d-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="9933d-148">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="9933d-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="9933d-149">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="9933d-150">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9933d-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9933d-151">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, wechseln Sie zu Microsoft und suchen nach dem Datensatz.</span><span class="sxs-lookup"><span data-stu-id="9933d-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="9933d-152">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="9933d-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9933d-153">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="9933d-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9933d-154">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9933d-155">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9933d-156">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9933d-p109">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9933d-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9933d-160">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9933d-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9933d-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9933d-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9933d-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="9933d-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9933d-164">Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9933d-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9933d-165">Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**</span><span class="sxs-lookup"><span data-stu-id="9933d-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9933d-166">Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="9933d-167">Typ</span><span class="sxs-lookup"><span data-stu-id="9933d-167">Type</span></span> | <span data-ttu-id="9933d-168">Name</span><span class="sxs-lookup"><span data-stu-id="9933d-168">Name</span></span> | <span data-ttu-id="9933d-169">Mail server</span><span class="sxs-lookup"><span data-stu-id="9933d-169">Mail server</span></span> | <span data-ttu-id="9933d-170">Priority</span><span class="sxs-lookup"><span data-stu-id="9933d-170">Priority</span></span> | <span data-ttu-id="9933d-171">TTL</span><span class="sxs-lookup"><span data-stu-id="9933d-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9933d-172">MX</span><span class="sxs-lookup"><span data-stu-id="9933d-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="9933d-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9933d-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9933d-174">**Hinweis:** Holen Sie  *\<domain-key\>*  sich Ihre von Ihrem Microsoft 365-Konto.</span><span class="sxs-lookup"><span data-stu-id="9933d-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="9933d-175">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="9933d-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="9933d-176">1</span><span class="sxs-lookup"><span data-stu-id="9933d-176">1</span></span>  <br/> <span data-ttu-id="9933d-177">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="9933d-177">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/>|<span data-ttu-id="9933d-178">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="9933d-179">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="9933d-180">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie einen davon durch Klicken auf das Symbol **Löschen (X)**.</span><span class="sxs-lookup"><span data-stu-id="9933d-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="9933d-181">Wählen Sie im Bestätigungsdialogfeld **Löschen** aus, um Ihre Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9933d-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9933d-182">Hinzufügen der sechs CNAME-Datensätze, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="9933d-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9933d-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9933d-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9933d-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="9933d-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9933d-186">Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9933d-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9933d-187">Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**</span><span class="sxs-lookup"><span data-stu-id="9933d-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9933d-188">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="9933d-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="9933d-189">Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="9933d-190">Typ</span><span class="sxs-lookup"><span data-stu-id="9933d-190">Type</span></span> | <span data-ttu-id="9933d-191">Name</span><span class="sxs-lookup"><span data-stu-id="9933d-191">Name</span></span> | <span data-ttu-id="9933d-192">Ziel</span><span class="sxs-lookup"><span data-stu-id="9933d-192">Target</span></span> | <span data-ttu-id="9933d-193">TTL</span><span class="sxs-lookup"><span data-stu-id="9933d-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9933d-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="9933d-194">CNAME</span></span>  <br/> |<span data-ttu-id="9933d-195">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9933d-195">autodiscover</span></span>  <br/> |<span data-ttu-id="9933d-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9933d-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="9933d-197">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9933d-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="9933d-198">CNAME</span></span>  <br/> |<span data-ttu-id="9933d-199">sip</span><span class="sxs-lookup"><span data-stu-id="9933d-199">sip</span></span>  <br/> |<span data-ttu-id="9933d-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9933d-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9933d-201">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9933d-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="9933d-202">CNAME</span></span>  <br/> |<span data-ttu-id="9933d-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9933d-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9933d-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9933d-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9933d-205">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9933d-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="9933d-206">CNAME</span></span>  <br/> |<span data-ttu-id="9933d-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9933d-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9933d-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9933d-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="9933d-209">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9933d-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="9933d-210">CNAME</span></span>  <br/> |<span data-ttu-id="9933d-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9933d-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9933d-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9933d-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="9933d-213">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9933d-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="9933d-214">CNAME</span></span>  <br/> |<span data-ttu-id="9933d-215">msoid</span><span class="sxs-lookup"><span data-stu-id="9933d-215">msoid</span></span>  <br/> |<span data-ttu-id="9933d-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="9933d-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="9933d-217">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="9933d-218">Wählen Sie das **SYMBOL FÜR DNS-Datenverkehr** (Orange Cloud in Grau ändern), um die Cloudflare-Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="9933d-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="9933d-219">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="9933d-220">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="9933d-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9933d-221">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="9933d-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9933d-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9933d-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9933d-223">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="9933d-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9933d-224">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="9933d-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9933d-225">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="9933d-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="9933d-226">sondern fügen Sie die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9933d-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9933d-227">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9933d-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9933d-228">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="9933d-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9933d-229">Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9933d-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9933d-230">Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**</span><span class="sxs-lookup"><span data-stu-id="9933d-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9933d-231">Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="9933d-232">Typ</span><span class="sxs-lookup"><span data-stu-id="9933d-232">Type</span></span> | <span data-ttu-id="9933d-233">Name</span><span class="sxs-lookup"><span data-stu-id="9933d-233">Name</span></span> | <span data-ttu-id="9933d-234">TTL</span><span class="sxs-lookup"><span data-stu-id="9933d-234">TTL</span></span> | <span data-ttu-id="9933d-235">Inhalt</span><span class="sxs-lookup"><span data-stu-id="9933d-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9933d-236">TXT</span><span class="sxs-lookup"><span data-stu-id="9933d-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9933d-237">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-237">30 minutes</span></span>  <br/> |<span data-ttu-id="9933d-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9933d-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9933d-239">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="9933d-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="9933d-240">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9933d-241">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="9933d-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9933d-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9933d-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9933d-243">Beachten Sie, dass Cloudflare für die Verfügbarkeit dieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="9933d-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="9933d-244">Falls Unterschiede zwischen den unten aufgeführten Schritten und der aktuellen Cloudflare-GUI (Grafische Benutzeroberfläche) auftreten, verwenden Sie bitte die [Cloudflare Community](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="9933d-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="9933d-245">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="9933d-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9933d-246">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="9933d-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="9933d-247">Wählen Sie **auf der** Startseite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9933d-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9933d-248">Wählen Sie **auf der Seite** Übersicht für Ihre Domäne DNS **aus.**</span><span class="sxs-lookup"><span data-stu-id="9933d-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="9933d-249">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="9933d-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="9933d-250">Klicken Sie **auf der** Seite DNS-Verwaltung auf Eintrag **hinzufügen,** und wählen Sie dann die Werte aus der ersten Zeile der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="9933d-251">Typ</span><span class="sxs-lookup"><span data-stu-id="9933d-251">Type</span></span> | <span data-ttu-id="9933d-252">Dienst</span><span class="sxs-lookup"><span data-stu-id="9933d-252">Service</span></span> | <span data-ttu-id="9933d-253">Protokoll</span><span class="sxs-lookup"><span data-stu-id="9933d-253">Protocol</span></span> | <span data-ttu-id="9933d-254">Name</span><span class="sxs-lookup"><span data-stu-id="9933d-254">Name</span></span> | <span data-ttu-id="9933d-255">TTL</span><span class="sxs-lookup"><span data-stu-id="9933d-255">TTL</span></span> | <span data-ttu-id="9933d-256">Priorität</span><span class="sxs-lookup"><span data-stu-id="9933d-256">Priority</span></span> | <span data-ttu-id="9933d-257">Schriftbreite</span><span class="sxs-lookup"><span data-stu-id="9933d-257">Weight</span></span> | <span data-ttu-id="9933d-258">Port</span><span class="sxs-lookup"><span data-stu-id="9933d-258">Port</span></span> | <span data-ttu-id="9933d-259">Ziel</span><span class="sxs-lookup"><span data-stu-id="9933d-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9933d-260">SRV</span><span class="sxs-lookup"><span data-stu-id="9933d-260">SRV</span></span>|<span data-ttu-id="9933d-261">_sip</span><span class="sxs-lookup"><span data-stu-id="9933d-261">_sip</span></span> |<span data-ttu-id="9933d-262">TLS</span><span class="sxs-lookup"><span data-stu-id="9933d-262">TLS</span></span> |<span data-ttu-id="9933d-263">Verwenden Sie *Domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9933d-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="9933d-264">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-264">30 minutes</span></span> | <span data-ttu-id="9933d-265">100</span><span class="sxs-lookup"><span data-stu-id="9933d-265">100</span></span>|<span data-ttu-id="9933d-266">1</span><span class="sxs-lookup"><span data-stu-id="9933d-266">1</span></span> |<span data-ttu-id="9933d-267">443</span><span class="sxs-lookup"><span data-stu-id="9933d-267">443</span></span> |<span data-ttu-id="9933d-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9933d-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="9933d-269">SRV</span><span class="sxs-lookup"><span data-stu-id="9933d-269">SRV</span></span>|<span data-ttu-id="9933d-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9933d-270">_sipfederationtls</span></span> | <span data-ttu-id="9933d-271">TCP</span><span class="sxs-lookup"><span data-stu-id="9933d-271">TCP</span></span>|<span data-ttu-id="9933d-272">Verwenden Sie *Domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9933d-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="9933d-273">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="9933d-273">30 minutes</span></span> |<span data-ttu-id="9933d-274">100</span><span class="sxs-lookup"><span data-stu-id="9933d-274">100</span></span> |<span data-ttu-id="9933d-275">1</span><span class="sxs-lookup"><span data-stu-id="9933d-275">1</span></span> |<span data-ttu-id="9933d-276">5061</span><span class="sxs-lookup"><span data-stu-id="9933d-276">5061</span></span> | <span data-ttu-id="9933d-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9933d-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="9933d-278">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9933d-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="9933d-279">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="9933d-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="9933d-p117">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9933d-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
