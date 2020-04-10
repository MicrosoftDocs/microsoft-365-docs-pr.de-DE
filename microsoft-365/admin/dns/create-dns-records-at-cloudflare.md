---
title: Erstellen von DNS-Einträgen für Office 365 bei Cloudflare
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Cloudflare für Office 365 einrichten.
ms.openlocfilehash: 8d64824f880bab9e6691ebf47c9508c555562fe4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211811"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="655e9-103">Erstellen von DNS-Einträgen für Office 365 bei Cloudflare</span><span class="sxs-lookup"><span data-stu-id="655e9-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="655e9-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="655e9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="655e9-105">[] Wenn Cloudflare Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="655e9-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="655e9-106">Nachdem Sie diese Einträge bei Cloudflare hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="655e9-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="655e9-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="655e9-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="655e9-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="655e9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="655e9-111">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="655e9-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="655e9-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="655e9-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="655e9-113">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="655e9-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="655e9-114">Als Sie sich bei Cloudflare registriert haben, haben Sie mithilfe des **Setup**-Prozesses von Cloudflare eine Domäne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="655e9-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="655e9-p102">Die von Ihnen hinzugefügte Domäne wurde bei einer separaten Domänenregistrierungsstelle erworben. Cloudflare bietet keine Domänenregistrierungsdienste an. Um DNS-Einträge für Ihre Domäne in Office 365 zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle so ändern, dass Namenserver von Cloudflare verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="655e9-p102">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services. To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="655e9-117">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="655e9-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="655e9-118">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="655e9-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="655e9-119">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="655e9-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="655e9-120">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="655e9-120">First nameserver</span></span>  <br/> |<span data-ttu-id="655e9-121">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="655e9-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="655e9-122">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="655e9-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="655e9-123">Verwenden Sie den von Cloudflare bereitgestellten Wert für den Namenserver.</span><span class="sxs-lookup"><span data-stu-id="655e9-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="655e9-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="655e9-124">You should use at least two name server records.</span></span> <span data-ttu-id="655e9-125">Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="655e9-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="655e9-126">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="655e9-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="655e9-p104">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="655e9-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="655e9-129">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="655e9-129">Add a TXT record for verification</span></span>
<span data-ttu-id="655e9-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="655e9-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="655e9-p105">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="655e9-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="655e9-p106">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="655e9-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="655e9-135">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="655e9-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="655e9-136">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="655e9-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="655e9-137">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="655e9-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="655e9-138">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="655e9-139">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="655e9-140">**Typ**</span><span class="sxs-lookup"><span data-stu-id="655e9-140">**Type**</span></span>|<span data-ttu-id="655e9-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="655e9-141">**Name**</span></span>|<span data-ttu-id="655e9-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="655e9-142">**Automatic TTL**</span></span>|<span data-ttu-id="655e9-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="655e9-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="655e9-144">TXT</span><span class="sxs-lookup"><span data-stu-id="655e9-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="655e9-145">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-145">30 minutes</span></span>  <br/> |<span data-ttu-id="655e9-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="655e9-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="655e9-p108">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="655e9-p108">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="655e9-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="655e9-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="655e9-151">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="655e9-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="655e9-152">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="655e9-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="655e9-153">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="655e9-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="655e9-154">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="655e9-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="655e9-155">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="655e9-156">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="655e9-157">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="655e9-p109">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="655e9-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="655e9-161">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="655e9-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="655e9-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="655e9-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="655e9-p110">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="655e9-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="655e9-165">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="655e9-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="655e9-166">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="655e9-167">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="655e9-168">**Typ**</span><span class="sxs-lookup"><span data-stu-id="655e9-168">**Type**</span></span>|<span data-ttu-id="655e9-169">**Name**</span><span class="sxs-lookup"><span data-stu-id="655e9-169">**Name**</span></span>|<span data-ttu-id="655e9-170">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="655e9-170">**Mail server**</span></span>|<span data-ttu-id="655e9-171">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="655e9-171">**Priority**</span></span>|<span data-ttu-id="655e9-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="655e9-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="655e9-173">MX</span><span class="sxs-lookup"><span data-stu-id="655e9-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="655e9-174">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="655e9-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="655e9-175">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="655e9-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="655e9-176">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="655e9-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="655e9-177">1</span><span class="sxs-lookup"><span data-stu-id="655e9-177">1</span></span>  <br/> <span data-ttu-id="655e9-178">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="655e9-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="655e9-179">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="655e9-180">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="655e9-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="655e9-181">Wenn es im Abschnitt **MX Records** andere MX-Einträge gibt, löschen Sie einen davon durch Klicken auf das Symbol **Löschen (X)**.</span><span class="sxs-lookup"><span data-stu-id="655e9-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="655e9-182">Wählen Sie im Dialogfeld Bestätigung die Option **Löschen** aus, um die Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="655e9-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="655e9-183">Fügen Sie die sechs CNAME-Einträge hinzu, die für Office 365 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="655e9-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="655e9-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="655e9-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="655e9-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="655e9-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="655e9-187">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="655e9-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="655e9-188">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="655e9-189">Fügen Sie den ersten der fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="655e9-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="655e9-190">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="655e9-191">**Typ**</span><span class="sxs-lookup"><span data-stu-id="655e9-191">**Type**</span></span>|<span data-ttu-id="655e9-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="655e9-192">**Name**</span></span>|<span data-ttu-id="655e9-193">**Target**</span><span class="sxs-lookup"><span data-stu-id="655e9-193">**Target**</span></span>|<span data-ttu-id="655e9-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="655e9-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="655e9-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="655e9-195">CNAME</span></span>  <br/> |<span data-ttu-id="655e9-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="655e9-196">autodiscover</span></span>  <br/> |<span data-ttu-id="655e9-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="655e9-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="655e9-198">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="655e9-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="655e9-199">CNAME</span></span>  <br/> |<span data-ttu-id="655e9-200">sip</span><span class="sxs-lookup"><span data-stu-id="655e9-200">sip</span></span>  <br/> |<span data-ttu-id="655e9-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="655e9-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="655e9-202">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="655e9-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="655e9-203">CNAME</span></span>  <br/> |<span data-ttu-id="655e9-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="655e9-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="655e9-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="655e9-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="655e9-206">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="655e9-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="655e9-207">CNAME</span></span>  <br/> |<span data-ttu-id="655e9-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="655e9-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="655e9-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="655e9-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="655e9-210">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="655e9-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="655e9-211">CNAME</span></span>  <br/> |<span data-ttu-id="655e9-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="655e9-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="655e9-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="655e9-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="655e9-214">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="655e9-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="655e9-215">CNAME</span></span>  <br/> |<span data-ttu-id="655e9-216">msoid</span><span class="sxs-lookup"><span data-stu-id="655e9-216">msoid</span></span>  <br/> |<span data-ttu-id="655e9-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="655e9-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="655e9-218">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="655e9-219">Wählen Sie das Symbol für den **DNS-Datenverkehr** (Orange Cloud) aus, um die Cloudflare-Server zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="655e9-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="655e9-220">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="655e9-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="655e9-221">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="655e9-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="655e9-222">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="655e9-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="655e9-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="655e9-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="655e9-224">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="655e9-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="655e9-225">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="655e9-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="655e9-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="655e9-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="655e9-227">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="655e9-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="655e9-228">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="655e9-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="655e9-229">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="655e9-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="655e9-230">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="655e9-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="655e9-231">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="655e9-232">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="655e9-233">**Typ**</span><span class="sxs-lookup"><span data-stu-id="655e9-233">**Type**</span></span>|<span data-ttu-id="655e9-234">**Name**</span><span class="sxs-lookup"><span data-stu-id="655e9-234">**Name**</span></span>|<span data-ttu-id="655e9-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="655e9-235">**TTL**</span></span>|<span data-ttu-id="655e9-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="655e9-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="655e9-237">TXT</span><span class="sxs-lookup"><span data-stu-id="655e9-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="655e9-238">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-238">30 minutes</span></span>  <br/> |<span data-ttu-id="655e9-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="655e9-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="655e9-240">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="655e9-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="655e9-241">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="655e9-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="655e9-242">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="655e9-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="655e9-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="655e9-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="655e9-244">Beachten Sie, dass Cloudflare für die bereitstellungdieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="655e9-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="655e9-245">Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Cloudflare-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Cloudflare-Community](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="655e9-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="655e9-246">Um zu beginnen, navigieren Sie über [diesen Link](https://www.cloudflare.com/a/login) zu Ihrer Domänenseite bei Cloudflare.</span><span class="sxs-lookup"><span data-stu-id="655e9-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="655e9-247">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="655e9-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="655e9-248">Wählen Sie auf der **Start** Seite die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="655e9-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="655e9-249">Wählen Sie auf der Seite **Übersicht** für Ihre Domäne **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="655e9-250">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="655e9-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="655e9-251">Klicken Sie auf der Seite **DNS-Verwaltung** auf **Datensatz hinzufügen**, und wählen Sie dann die Werte aus der ersten Zeile der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="655e9-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="655e9-252">**Type**</span><span class="sxs-lookup"><span data-stu-id="655e9-252">**Type**</span></span>|<span data-ttu-id="655e9-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="655e9-253">**Service**</span></span>|<span data-ttu-id="655e9-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="655e9-254">**Protocol**</span></span>|<span data-ttu-id="655e9-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="655e9-255">**Name**</span></span>|<span data-ttu-id="655e9-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="655e9-256">**TTL**</span></span>|<span data-ttu-id="655e9-257">**Priority**</span><span class="sxs-lookup"><span data-stu-id="655e9-257">**Priority**</span></span>|<span data-ttu-id="655e9-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="655e9-258">**Weight**</span></span>|<span data-ttu-id="655e9-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="655e9-259">**Port**</span></span>|<span data-ttu-id="655e9-260">**Target**</span><span class="sxs-lookup"><span data-stu-id="655e9-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="655e9-261">SRV</span><span class="sxs-lookup"><span data-stu-id="655e9-261">SRV</span></span>|<span data-ttu-id="655e9-262">_sip</span><span class="sxs-lookup"><span data-stu-id="655e9-262">_sip</span></span> |<span data-ttu-id="655e9-263">TLS</span><span class="sxs-lookup"><span data-stu-id="655e9-263">TLS</span></span> |<span data-ttu-id="655e9-264">Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="655e9-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="655e9-265">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-265">30 minutes</span></span> | <span data-ttu-id="655e9-266">100</span><span class="sxs-lookup"><span data-stu-id="655e9-266">100</span></span>|<span data-ttu-id="655e9-267">1</span><span class="sxs-lookup"><span data-stu-id="655e9-267">1</span></span> |<span data-ttu-id="655e9-268">443</span><span class="sxs-lookup"><span data-stu-id="655e9-268">443</span></span> |<span data-ttu-id="655e9-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="655e9-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="655e9-270">SRV</span><span class="sxs-lookup"><span data-stu-id="655e9-270">SRV</span></span>|<span data-ttu-id="655e9-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="655e9-271">_sipfederationtls</span></span> | <span data-ttu-id="655e9-272">TCP</span><span class="sxs-lookup"><span data-stu-id="655e9-272">TCP</span></span>|<span data-ttu-id="655e9-273">Verwenden Sie Ihre *domain_name*; Beispiel: contoso.com</span><span class="sxs-lookup"><span data-stu-id="655e9-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="655e9-274">30 Minuten</span><span class="sxs-lookup"><span data-stu-id="655e9-274">30 minutes</span></span> |<span data-ttu-id="655e9-275">100</span><span class="sxs-lookup"><span data-stu-id="655e9-275">100</span></span> |<span data-ttu-id="655e9-276">1</span><span class="sxs-lookup"><span data-stu-id="655e9-276">1</span></span> |<span data-ttu-id="655e9-277">5061</span><span class="sxs-lookup"><span data-stu-id="655e9-277">5061</span></span> | <span data-ttu-id="655e9-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="655e9-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="655e9-279">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="655e9-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="655e9-280">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="655e9-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="655e9-p117">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="655e9-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
