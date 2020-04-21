---
title: Erstellen von DNS-Einträgen bei Web.com für Microsoft
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Web.com für Microsoft einrichten.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629251"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="a929c-103">Erstellen von DNS-Einträgen bei Web.com für Microsoft</span><span class="sxs-lookup"><span data-stu-id="a929c-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="a929c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a929c-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a929c-105">Wenn Web.com Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a929c-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a929c-106">Nachdem Sie diese Einträge bei Web.com hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a929c-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="a929c-107">Informationen über Webhosting und DNS für Websites mit Microsoft finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="a929c-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a929c-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a929c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a929c-111">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="a929c-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a929c-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="a929c-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a929c-113">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="a929c-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a929c-114">Wenn Sie sich für Web.com registriert haben, haben Sie eine Domäne mithilfe des Web.com- **Setup** Prozesses hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a929c-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="a929c-115">Um DNS-Einträge für Ihre Domäne in Microsoft zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Namenserver von "Internet. com" verwenden.</span><span class="sxs-lookup"><span data-stu-id="a929c-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="a929c-116">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a929c-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a929c-117">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="a929c-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a929c-118">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a929c-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a929c-119">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="a929c-119">First nameserver</span></span>  <br/> |<span data-ttu-id="a929c-120">Verwenden Sie den von Web.com bereitgestellten Nameserver-Wert.</span><span class="sxs-lookup"><span data-stu-id="a929c-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="a929c-121">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="a929c-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="a929c-122">Verwenden Sie den von Web.com bereitgestellten Nameserver-Wert.</span><span class="sxs-lookup"><span data-stu-id="a929c-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="a929c-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="a929c-123">You should use at least two name server records.</span></span> <span data-ttu-id="a929c-124">Wenn andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="a929c-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="a929c-125">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a929c-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a929c-126">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a929c-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a929c-127">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a929c-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a929c-128">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a929c-128">Add a TXT record for verification</span></span>
<span data-ttu-id="a929c-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a929c-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a929c-130">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="a929c-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="a929c-131">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="a929c-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a929c-p105">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="a929c-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a929c-134">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="a929c-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a929c-135">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="a929c-135">Log in first.</span></span>
  
2. <span data-ttu-id="a929c-136">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a929c-137">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="a929c-138">Klicken Sie auf der Seite **Domänennamen** unter **Text (TXT-Einträge)** auf **TXT-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a929c-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="a929c-139">**Host**</span></span>|<span data-ttu-id="a929c-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a929c-140">**TTL**</span></span>|<span data-ttu-id="a929c-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="a929c-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="a929c-142">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-142">3600</span></span>  <br/> |<span data-ttu-id="a929c-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a929c-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a929c-144">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a929c-144">**Note:** This is an example.</span></span> <span data-ttu-id="a929c-145">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a929c-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a929c-146">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="a929c-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="a929c-147">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="a929c-148">Warten Sie einige Minuten, bevor Sie den neuen TXT-Eintrag überprüfen, damit der soeben erstellte Eintrag über das Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a929c-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a929c-149">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="a929c-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a929c-150">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="a929c-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a929c-151">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="a929c-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a929c-152">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a929c-153">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a929c-154">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a929c-p108">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a929c-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a929c-158">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft gelangen</span><span class="sxs-lookup"><span data-stu-id="a929c-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a929c-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a929c-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a929c-160">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="a929c-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a929c-161">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="a929c-161">Log in first.</span></span>
  
2. <span data-ttu-id="a929c-162">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a929c-163">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="a929c-164">Klicken Sie unter **e-Mail-Server (MX Records)** auf **MX-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a929c-165">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="a929c-165">**Priority**</span></span>|<span data-ttu-id="a929c-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a929c-166">**TTL**</span></span>|<span data-ttu-id="a929c-167">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="a929c-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a929c-168">1</span><span class="sxs-lookup"><span data-stu-id="a929c-168">1</span></span>  <br/> <span data-ttu-id="a929c-169">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a929c-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="a929c-170">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-170">3600</span></span>  <br/> |<span data-ttu-id="a929c-171">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a929c-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a929c-172">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="a929c-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="a929c-173">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="a929c-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="a929c-174">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a929c-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="a929c-175">Wenn im Abschnitt **MX Records** weitere MX-Einträge aufgeführt sind, aktivieren Sie das Kontrollkästchen neben dem Eintrag unter **Löschen**, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="a929c-176">Wählen Sie auf dem Bestätigungsbildschirm die Option **Änderungen speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a929c-177">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="a929c-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a929c-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a929c-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a929c-179">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="a929c-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a929c-180">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a929c-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="a929c-181">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a929c-182">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="a929c-183">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a929c-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a929c-184">Klicken Sie unter **Host Aliase (CNAME Records)** auf **CNAME-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="a929c-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a929c-185">**Alias**</span></span>|<span data-ttu-id="a929c-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a929c-186">**TTL**</span></span>|<span data-ttu-id="a929c-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="a929c-187">**Refers to Host Name**</span></span>|<span data-ttu-id="a929c-188">**Anderer Host**</span><span class="sxs-lookup"><span data-stu-id="a929c-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a929c-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a929c-189">autodiscover</span></span>  <br/> |<span data-ttu-id="a929c-190">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-190">3600</span></span>  <br/> |<span data-ttu-id="a929c-191">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="a929c-191">@ (none)</span></span>  <br/> |<span data-ttu-id="a929c-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a929c-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a929c-193">sip</span><span class="sxs-lookup"><span data-stu-id="a929c-193">sip</span></span>  <br/> |<span data-ttu-id="a929c-194">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-194">3600</span></span>  <br/> |<span data-ttu-id="a929c-195">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="a929c-195">@ (none)</span></span>  <br/> |<span data-ttu-id="a929c-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a929c-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a929c-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a929c-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a929c-198">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-198">3600</span></span>  <br/> |<span data-ttu-id="a929c-199">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="a929c-199">@ (none)</span></span>  <br/> | <span data-ttu-id="a929c-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a929c-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a929c-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a929c-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a929c-202">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-202">3600</span></span>  <br/> |<span data-ttu-id="a929c-203">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="a929c-203">@ (none)</span></span>  <br/> |<span data-ttu-id="a929c-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a929c-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a929c-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a929c-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a929c-206">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-206">3600</span></span>  <br/> |<span data-ttu-id="a929c-207">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="a929c-207">@ (none)</span></span>  <br/> |<span data-ttu-id="a929c-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a929c-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="a929c-209">msoid</span><span class="sxs-lookup"><span data-stu-id="a929c-209">msoid</span></span>  <br/> |<span data-ttu-id="a929c-210">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-210">3600</span></span>  <br/> |<span data-ttu-id="a929c-211">@ (keine)</span><span class="sxs-lookup"><span data-stu-id="a929c-211">@ (none)</span></span>  <br/> |<span data-ttu-id="a929c-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="a929c-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="a929c-213">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="a929c-214">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a929c-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a929c-215">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="a929c-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a929c-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a929c-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a929c-217">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="a929c-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a929c-218">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="a929c-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a929c-219">Wenn Sie bereits einen SPF-Eintrag für Ihre Domäne haben, erstellen Sie keinen neuen für Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a929c-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a929c-220">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="a929c-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a929c-221">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="a929c-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a929c-222">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="a929c-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="a929c-223">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a929c-224">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="a929c-225">Klicken Sie auf der Seite **Domänennamen** unter **Text (TXT-Einträge)** auf **TXT-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="a929c-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="a929c-226">**Host**</span></span>|<span data-ttu-id="a929c-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a929c-227">**TTL**</span></span>|<span data-ttu-id="a929c-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="a929c-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a929c-229">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-229">3600</span></span>  <br/> |<span data-ttu-id="a929c-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a929c-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a929c-231">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="a929c-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="a929c-232">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-232">Select **Continue**.</span></span>

6. <span data-ttu-id="a929c-233">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a929c-234">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a929c-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a929c-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a929c-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a929c-236">Beachten Sie, dass Web.com für die bereitstellungdieser Funktionalität verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="a929c-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="a929c-237">Wenn Sie Diskrepanzen zwischen den folgenden Schritten und der aktuellen Web.com-GUI (grafische Benutzeroberfläche) sehen, nutzen Sie die [Web.com-Community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="a929c-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="a929c-238">Um zu beginnen, navigieren Sie über [diesen Link](https://checkout.web.com/manage-it/index.jsp)zu ihrer Domänen Seite bei Web.com.</span><span class="sxs-lookup"><span data-stu-id="a929c-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a929c-239">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="a929c-239">Log in first.</span></span>
      
2. <span data-ttu-id="a929c-240">Wählen Sie auf der Seite **Konto-Manager** die Option **meine Domänennamen**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a929c-241">Wählen Sie unter \* \* Manage \* My Domain \* \* \* die Option **Erweiterte DNS-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="a929c-242">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="a929c-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="a929c-243">Klicken Sie unter **Dienst (SRV-Einträge)** auf **SRV-Einträge bearbeiten**, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="a929c-244">**Service**</span><span class="sxs-lookup"><span data-stu-id="a929c-244">**Service**</span></span>|<span data-ttu-id="a929c-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="a929c-245">**Protocol**</span></span>|<span data-ttu-id="a929c-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a929c-246">**TTL**</span></span>|<span data-ttu-id="a929c-247">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a929c-247">**Priority**</span></span>|<span data-ttu-id="a929c-248">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a929c-248">**Weight**</span></span>|<span data-ttu-id="a929c-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="a929c-249">**Port**</span></span>|<span data-ttu-id="a929c-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="a929c-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a929c-251">_sip</span><span class="sxs-lookup"><span data-stu-id="a929c-251">_sip</span></span> |<span data-ttu-id="a929c-252">_tls</span><span class="sxs-lookup"><span data-stu-id="a929c-252">_tls</span></span> |<span data-ttu-id="a929c-253">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-253">3600</span></span> | <span data-ttu-id="a929c-254">100</span><span class="sxs-lookup"><span data-stu-id="a929c-254">100</span></span>|<span data-ttu-id="a929c-255">1</span><span class="sxs-lookup"><span data-stu-id="a929c-255">1</span></span> |<span data-ttu-id="a929c-256">443</span><span class="sxs-lookup"><span data-stu-id="a929c-256">443</span></span> |<span data-ttu-id="a929c-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a929c-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="a929c-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a929c-258">_sipfederationtls</span></span> |<span data-ttu-id="a929c-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="a929c-259">_tcp</span></span> |<span data-ttu-id="a929c-260">3600</span><span class="sxs-lookup"><span data-stu-id="a929c-260">3600</span></span> |<span data-ttu-id="a929c-261">100</span><span class="sxs-lookup"><span data-stu-id="a929c-261">100</span></span> |<span data-ttu-id="a929c-262">1</span><span class="sxs-lookup"><span data-stu-id="a929c-262">1</span></span> |<span data-ttu-id="a929c-263">5061</span><span class="sxs-lookup"><span data-stu-id="a929c-263">5061</span></span> | <span data-ttu-id="a929c-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a929c-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="a929c-265">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="a929c-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="a929c-266">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-266">Select **Continue**.</span></span>

7. <span data-ttu-id="a929c-267">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a929c-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="a929c-p116">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a929c-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
