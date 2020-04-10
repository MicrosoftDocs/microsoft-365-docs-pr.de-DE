---
title: Erstellen von DNS-Einträgen bei Web.com für Office 365
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Web.com für Office 365 einrichten.
ms.openlocfilehash: d5546b55392849aac9049613bd860f937ffb7618
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211074"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="76e95-103">Erstellen von DNS-Einträgen bei Web.com für Office 365</span><span class="sxs-lookup"><span data-stu-id="76e95-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="76e95-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="76e95-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="76e95-105">Wenn Web.com Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten.</span><span class="sxs-lookup"><span data-stu-id="76e95-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="76e95-106">Nachdem Sie diese Einträge bei Web.com hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365 Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="76e95-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="76e95-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="76e95-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="76e95-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="76e95-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="76e95-111">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="76e95-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="76e95-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="76e95-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="76e95-113">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="76e95-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="76e95-114">Wenn Sie sich für Web.com registriert haben, haben Sie eine Domäne mithilfe des Web.com- **Setup** Prozesses hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="76e95-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="76e95-115">Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Office 365 müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Namenserver von "Internet. com" verwenden.</span><span class="sxs-lookup"><span data-stu-id="76e95-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="76e95-116">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="76e95-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="76e95-117">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="76e95-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="76e95-118">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="76e95-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="76e95-119">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="76e95-119">First nameserver</span></span>  <br/> |<span data-ttu-id="76e95-120">Verwenden Sie den von Web.com bereitgestellten Nameserver-Wert.</span><span class="sxs-lookup"><span data-stu-id="76e95-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="76e95-121">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="76e95-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="76e95-122">Verwenden Sie den von Web.com bereitgestellten Nameserver-Wert.</span><span class="sxs-lookup"><span data-stu-id="76e95-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="76e95-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="76e95-123">You should use at least two name server records.</span></span> <span data-ttu-id="76e95-124">Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="76e95-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="76e95-125">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="76e95-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="76e95-p103">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="76e95-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="76e95-128">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="76e95-128">Add a TXT record for verification</span></span>
<span data-ttu-id="76e95-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="76e95-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="76e95-p104">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="76e95-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76e95-p105">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="76e95-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="76e95-134">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="76e95-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="76e95-135">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="76e95-135">Log in first.</span></span>
  
2. <span data-ttu-id="76e95-136">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="76e95-137">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="76e95-138">Klicken Sie auf der Seite **Domänennamen** unter **Text (TXT-Einträge)** auf **TXT-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="76e95-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="76e95-139">**Host**</span></span>|<span data-ttu-id="76e95-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76e95-140">**TTL**</span></span>|<span data-ttu-id="76e95-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="76e95-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="76e95-142">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-142">3600</span></span>  <br/> |<span data-ttu-id="76e95-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="76e95-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="76e95-p107">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="76e95-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="76e95-147">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="76e95-148">Warten Sie einige Minuten, bevor Sie den neuen TXT-Eintrag überprüfen, damit der soeben erstellte Eintrag über das Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="76e95-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="76e95-149">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="76e95-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="76e95-150">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="76e95-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="76e95-151">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="76e95-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="76e95-152">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="76e95-153">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="76e95-154">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="76e95-p108">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="76e95-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="76e95-158">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="76e95-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="76e95-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="76e95-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="76e95-160">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="76e95-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="76e95-161">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="76e95-161">Log in first.</span></span>
  
2. <span data-ttu-id="76e95-162">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="76e95-163">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="76e95-164">Klicken Sie unter **e-Mail-Server (MX Records)** auf **MX-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="76e95-165">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="76e95-165">**Priority**</span></span>|<span data-ttu-id="76e95-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76e95-166">**TTL**</span></span>|<span data-ttu-id="76e95-167">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="76e95-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="76e95-168">1</span><span class="sxs-lookup"><span data-stu-id="76e95-168">1</span></span>  <br/> <span data-ttu-id="76e95-169">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="76e95-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="76e95-170">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-170">3600</span></span>  <br/> |<span data-ttu-id="76e95-171">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="76e95-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="76e95-172">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="76e95-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="76e95-173">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="76e95-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="76e95-174">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="76e95-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="76e95-175">Wenn im Abschnitt **MX Records** weitere MX-Einträge aufgeführt sind, aktivieren Sie das Kontrollkästchen neben dem Eintrag unter **Löschen**, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="76e95-176">Wählen Sie auf dem Bestätigungsbildschirm die Option **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="76e95-177">Fügen Sie die sechs CNAME-Einträge hinzu, die für Office 365 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="76e95-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="76e95-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="76e95-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="76e95-179">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="76e95-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="76e95-180">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="76e95-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="76e95-181">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="76e95-182">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="76e95-183">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="76e95-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="76e95-184">Klicken Sie unter **Host Aliase (CNAME Records)** auf **CNAME-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="76e95-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="76e95-185">**Alias**</span></span>|<span data-ttu-id="76e95-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76e95-186">**TTL**</span></span>|<span data-ttu-id="76e95-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="76e95-187">**Refers to Host Name**</span></span>|<span data-ttu-id="76e95-188">**Anderer Host**</span><span class="sxs-lookup"><span data-stu-id="76e95-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="76e95-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="76e95-189">autodiscover</span></span>  <br/> |<span data-ttu-id="76e95-190">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-190">3600</span></span>  <br/> |<span data-ttu-id="76e95-191">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="76e95-191">@ (none)</span></span>  <br/> |<span data-ttu-id="76e95-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="76e95-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="76e95-193">sip</span><span class="sxs-lookup"><span data-stu-id="76e95-193">sip</span></span>  <br/> |<span data-ttu-id="76e95-194">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-194">3600</span></span>  <br/> |<span data-ttu-id="76e95-195">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="76e95-195">@ (none)</span></span>  <br/> |<span data-ttu-id="76e95-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="76e95-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="76e95-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="76e95-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="76e95-198">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-198">3600</span></span>  <br/> |<span data-ttu-id="76e95-199">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="76e95-199">@ (none)</span></span>  <br/> | <span data-ttu-id="76e95-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="76e95-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="76e95-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="76e95-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="76e95-202">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-202">3600</span></span>  <br/> |<span data-ttu-id="76e95-203">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="76e95-203">@ (none)</span></span>  <br/> |<span data-ttu-id="76e95-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="76e95-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="76e95-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="76e95-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="76e95-206">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-206">3600</span></span>  <br/> |<span data-ttu-id="76e95-207">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="76e95-207">@ (none)</span></span>  <br/> |<span data-ttu-id="76e95-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="76e95-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="76e95-209">msoid</span><span class="sxs-lookup"><span data-stu-id="76e95-209">msoid</span></span>  <br/> |<span data-ttu-id="76e95-210">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-210">3600</span></span>  <br/> |<span data-ttu-id="76e95-211">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="76e95-211">@ (none)</span></span>  <br/> |<span data-ttu-id="76e95-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="76e95-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="76e95-213">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="76e95-214">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="76e95-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="76e95-215">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="76e95-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="76e95-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="76e95-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="76e95-217">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="76e95-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="76e95-218">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="76e95-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="76e95-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="76e95-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="76e95-220">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="76e95-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="76e95-221">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="76e95-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="76e95-222">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="76e95-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="76e95-223">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="76e95-224">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="76e95-225">Klicken Sie auf der Seite **Domänennamen** unter **Text (TXT-Einträge)** auf **TXT-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="76e95-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="76e95-226">**Host**</span></span>|<span data-ttu-id="76e95-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76e95-227">**TTL**</span></span>|<span data-ttu-id="76e95-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="76e95-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="76e95-229">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-229">3600</span></span>  <br/> |<span data-ttu-id="76e95-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="76e95-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="76e95-231">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="76e95-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="76e95-232">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-232">Select **Continue**.</span></span>

6. <span data-ttu-id="76e95-233">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="76e95-234">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="76e95-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="76e95-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="76e95-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="76e95-236">Beachten Sie, dass Web.com für die bereitstellungdieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="76e95-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="76e95-237">Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Web.com-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Web.com-Community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="76e95-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="76e95-238">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="76e95-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="76e95-239">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="76e95-239">Log in first.</span></span>
      
2. <span data-ttu-id="76e95-240">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="76e95-241">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="76e95-242">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="76e95-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="76e95-243">Klicken Sie unter **Dienst (SRV-Einträge)** auf **SRV-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="76e95-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="76e95-244">**Service**</span></span>|<span data-ttu-id="76e95-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="76e95-245">**Protocol**</span></span>|<span data-ttu-id="76e95-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76e95-246">**TTL**</span></span>|<span data-ttu-id="76e95-247">**Priority**</span><span class="sxs-lookup"><span data-stu-id="76e95-247">**Priority**</span></span>|<span data-ttu-id="76e95-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="76e95-248">**Weight**</span></span>|<span data-ttu-id="76e95-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="76e95-249">**Port**</span></span>|<span data-ttu-id="76e95-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="76e95-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="76e95-251">_sip</span><span class="sxs-lookup"><span data-stu-id="76e95-251">_sip</span></span> |<span data-ttu-id="76e95-252">_tls</span><span class="sxs-lookup"><span data-stu-id="76e95-252">_tls</span></span> |<span data-ttu-id="76e95-253">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-253">3600</span></span> | <span data-ttu-id="76e95-254">100</span><span class="sxs-lookup"><span data-stu-id="76e95-254">100</span></span>|<span data-ttu-id="76e95-255">1</span><span class="sxs-lookup"><span data-stu-id="76e95-255">1</span></span> |<span data-ttu-id="76e95-256">443</span><span class="sxs-lookup"><span data-stu-id="76e95-256">443</span></span> |<span data-ttu-id="76e95-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="76e95-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="76e95-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="76e95-258">_sipfederationtls</span></span> |<span data-ttu-id="76e95-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="76e95-259">_tcp</span></span> |<span data-ttu-id="76e95-260">3600</span><span class="sxs-lookup"><span data-stu-id="76e95-260">3600</span></span> |<span data-ttu-id="76e95-261">100</span><span class="sxs-lookup"><span data-stu-id="76e95-261">100</span></span> |<span data-ttu-id="76e95-262">1</span><span class="sxs-lookup"><span data-stu-id="76e95-262">1</span></span> |<span data-ttu-id="76e95-263">5061</span><span class="sxs-lookup"><span data-stu-id="76e95-263">5061</span></span> | <span data-ttu-id="76e95-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="76e95-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="76e95-265">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="76e95-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="76e95-266">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-266">Select **Continue**.</span></span>

7. <span data-ttu-id="76e95-267">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="76e95-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="76e95-p116">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="76e95-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
