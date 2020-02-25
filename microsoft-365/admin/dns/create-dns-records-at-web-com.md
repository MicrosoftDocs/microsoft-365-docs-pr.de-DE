---
title: Erstellen von DNS-Einträgen bei Web.com für Office 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Web.com für Office 365 einrichten.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249455"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="4a987-103">Erstellen von DNS-Einträgen bei Web.com für Office 365</span><span class="sxs-lookup"><span data-stu-id="4a987-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="4a987-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="4a987-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="4a987-105">Wenn Web.com Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4a987-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="4a987-106">Nachdem Sie diese Einträge bei Web.com hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365 Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4a987-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="4a987-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a987-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="4a987-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a987-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="4a987-111">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="4a987-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="4a987-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="4a987-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a987-113">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="4a987-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="4a987-114">Wenn Sie sich für Web.com registriert haben, haben Sie eine Domäne mithilfe des Web.com- **Setup** Prozesses hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4a987-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="4a987-115">Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Office 365 müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Namenserver von "Internet. com" verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a987-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="4a987-116">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4a987-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="4a987-117">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="4a987-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="4a987-118">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4a987-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="4a987-119">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="4a987-119">First nameserver</span></span>  <br/> |<span data-ttu-id="4a987-120">Verwenden Sie den von Web.com bereitgestellten Nameserver-Wert.</span><span class="sxs-lookup"><span data-stu-id="4a987-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="4a987-121">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="4a987-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="4a987-122">Verwenden Sie den von Web.com bereitgestellten Nameserver-Wert.</span><span class="sxs-lookup"><span data-stu-id="4a987-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="4a987-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="4a987-123">You should use at least two name server records.</span></span> <span data-ttu-id="4a987-124">Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="4a987-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="4a987-125">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="4a987-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4a987-p103">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4a987-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="4a987-128">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="4a987-128">Add a TXT record for verification</span></span>
<span data-ttu-id="4a987-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="4a987-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="4a987-p104">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="4a987-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a987-p105">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="4a987-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="4a987-134">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="4a987-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4a987-135">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="4a987-135">Log in first.</span></span>
  
2. <span data-ttu-id="4a987-136">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4a987-137">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="4a987-138">Klicken Sie auf der Seite **Domänennamen** unter **Text (TXT-Einträge)** auf **TXT-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="4a987-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a987-139">**Host**</span></span>|<span data-ttu-id="4a987-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a987-140">**TTL**</span></span>|<span data-ttu-id="4a987-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="4a987-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="4a987-142">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-142">3600</span></span>  <br/> |<span data-ttu-id="4a987-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="4a987-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="4a987-p107">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="4a987-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="4a987-147">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="4a987-148">Warten Sie einige Minuten, bevor Sie den neuen TXT-Eintrag überprüfen, damit der soeben erstellte Eintrag über das Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a987-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="4a987-149">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4a987-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="4a987-150">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="4a987-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="4a987-151">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="4a987-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="4a987-152">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="4a987-153">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="4a987-154">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="4a987-p108">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a987-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="4a987-158">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="4a987-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="4a987-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="4a987-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="4a987-160">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="4a987-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4a987-161">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="4a987-161">Log in first.</span></span>
  
2. <span data-ttu-id="4a987-162">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4a987-163">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="4a987-164">Klicken Sie unter **e-Mail-Server (MX Records)** auf **MX-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="4a987-165">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4a987-165">**Priority**</span></span>|<span data-ttu-id="4a987-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a987-166">**TTL**</span></span>|<span data-ttu-id="4a987-167">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="4a987-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="4a987-168">1</span><span class="sxs-lookup"><span data-stu-id="4a987-168">1</span></span>  <br/> <span data-ttu-id="4a987-169">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a987-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="4a987-170">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-170">3600</span></span>  <br/> |<span data-ttu-id="4a987-171">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a987-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="4a987-172">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="4a987-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="4a987-173">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="4a987-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="4a987-174">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4a987-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="4a987-175">Wenn im Abschnitt **MX Records** weitere MX-Einträge aufgeführt sind, aktivieren Sie das Kontrollkästchen neben dem Eintrag unter **Löschen**, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="4a987-176">Wählen Sie auf dem Bestätigungsbildschirm die Option **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="4a987-177">Fügen Sie die sechs CNAME-Einträge hinzu, die für Office 365 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4a987-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="4a987-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="4a987-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="4a987-179">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="4a987-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4a987-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="4a987-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="4a987-181">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4a987-182">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="4a987-183">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a987-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="4a987-184">Klicken Sie unter **Host Aliase (CNAME Records)** auf **CNAME-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="4a987-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="4a987-185">**Alias**</span></span>|<span data-ttu-id="4a987-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a987-186">**TTL**</span></span>|<span data-ttu-id="4a987-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="4a987-187">**Refers to Host Name**</span></span>|<span data-ttu-id="4a987-188">**Anderer Host**</span><span class="sxs-lookup"><span data-stu-id="4a987-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a987-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="4a987-189">autodiscover</span></span>  <br/> |<span data-ttu-id="4a987-190">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-190">3600</span></span>  <br/> |<span data-ttu-id="4a987-191">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="4a987-191">@ (none)</span></span>  <br/> |<span data-ttu-id="4a987-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a987-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="4a987-193">sip</span><span class="sxs-lookup"><span data-stu-id="4a987-193">sip</span></span>  <br/> |<span data-ttu-id="4a987-194">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-194">3600</span></span>  <br/> |<span data-ttu-id="4a987-195">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="4a987-195">@ (none)</span></span>  <br/> |<span data-ttu-id="4a987-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a987-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4a987-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4a987-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="4a987-198">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-198">3600</span></span>  <br/> |<span data-ttu-id="4a987-199">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="4a987-199">@ (none)</span></span>  <br/> | <span data-ttu-id="4a987-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a987-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="4a987-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="4a987-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="4a987-202">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-202">3600</span></span>  <br/> |<span data-ttu-id="4a987-203">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="4a987-203">@ (none)</span></span>  <br/> |<span data-ttu-id="4a987-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="4a987-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="4a987-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="4a987-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="4a987-206">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-206">3600</span></span>  <br/> |<span data-ttu-id="4a987-207">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="4a987-207">@ (none)</span></span>  <br/> |<span data-ttu-id="4a987-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4a987-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="4a987-209">msoid</span><span class="sxs-lookup"><span data-stu-id="4a987-209">msoid</span></span>  <br/> |<span data-ttu-id="4a987-210">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-210">3600</span></span>  <br/> |<span data-ttu-id="4a987-211">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="4a987-211">@ (none)</span></span>  <br/> |<span data-ttu-id="4a987-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="4a987-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="4a987-213">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="4a987-214">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a987-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="4a987-215">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="4a987-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="4a987-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="4a987-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a987-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="4a987-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="4a987-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="4a987-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="4a987-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a987-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="4a987-220">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4a987-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="4a987-221">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="4a987-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4a987-222">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="4a987-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="4a987-223">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4a987-224">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="4a987-225">Klicken Sie auf der Seite **Domänennamen** unter **Text (TXT-Einträge)** auf **TXT-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="4a987-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="4a987-226">**Host**</span></span>|<span data-ttu-id="4a987-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a987-227">**TTL**</span></span>|<span data-ttu-id="4a987-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="4a987-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="4a987-229">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-229">3600</span></span>  <br/> |<span data-ttu-id="4a987-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="4a987-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="4a987-231">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="4a987-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="4a987-232">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-232">Select **Continue**.</span></span>

6. <span data-ttu-id="4a987-233">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="4a987-234">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="4a987-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="4a987-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="4a987-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a987-236">Beachten Sie, dass Web.com für die bereitstellungdieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="4a987-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="4a987-237">Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Web.com-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Web.com-Community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="4a987-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="4a987-238">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="4a987-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="4a987-239">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="4a987-239">Log in first.</span></span>
      
2. <span data-ttu-id="4a987-240">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="4a987-241">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="4a987-242">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a987-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="4a987-243">Klicken Sie unter **Dienst (SRV-Einträge)** auf **SRV-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="4a987-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="4a987-244">**Service**</span></span>|<span data-ttu-id="4a987-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="4a987-245">**Protocol**</span></span>|<span data-ttu-id="4a987-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="4a987-246">**TTL**</span></span>|<span data-ttu-id="4a987-247">**Priority**</span><span class="sxs-lookup"><span data-stu-id="4a987-247">**Priority**</span></span>|<span data-ttu-id="4a987-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="4a987-248">**Weight**</span></span>|<span data-ttu-id="4a987-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="4a987-249">**Port**</span></span>|<span data-ttu-id="4a987-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="4a987-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="4a987-251">_sip</span><span class="sxs-lookup"><span data-stu-id="4a987-251">_sip</span></span> |<span data-ttu-id="4a987-252">_tls</span><span class="sxs-lookup"><span data-stu-id="4a987-252">_tls</span></span> |<span data-ttu-id="4a987-253">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-253">3600</span></span> | <span data-ttu-id="4a987-254">100</span><span class="sxs-lookup"><span data-stu-id="4a987-254">100</span></span>|<span data-ttu-id="4a987-255">1</span><span class="sxs-lookup"><span data-stu-id="4a987-255">1</span></span> |<span data-ttu-id="4a987-256">443</span><span class="sxs-lookup"><span data-stu-id="4a987-256">443</span></span> |<span data-ttu-id="4a987-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a987-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="4a987-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="4a987-258">_sipfederationtls</span></span> |<span data-ttu-id="4a987-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="4a987-259">_tcp</span></span> |<span data-ttu-id="4a987-260">3600</span><span class="sxs-lookup"><span data-stu-id="4a987-260">3600</span></span> |<span data-ttu-id="4a987-261">100</span><span class="sxs-lookup"><span data-stu-id="4a987-261">100</span></span> |<span data-ttu-id="4a987-262">1</span><span class="sxs-lookup"><span data-stu-id="4a987-262">1</span></span> |<span data-ttu-id="4a987-263">5061</span><span class="sxs-lookup"><span data-stu-id="4a987-263">5061</span></span> | <span data-ttu-id="4a987-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="4a987-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="4a987-265">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="4a987-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="4a987-266">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-266">Select **Continue**.</span></span>

7. <span data-ttu-id="4a987-267">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="4a987-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="4a987-p116">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a987-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
