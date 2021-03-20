---
title: Erstellen von DNS-Einträgen web.com Microsoft
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste unter web.com Microsoft einrichten.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909982"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="07d15-103">Erstellen von DNS-Einträgen web.com Microsoft</span><span class="sxs-lookup"><span data-stu-id="07d15-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="07d15-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="07d15-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="07d15-105">Wenn web.com Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und so weiter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="07d15-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="07d15-106">Nachdem Sie diese Datensätze unter web.com hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="07d15-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="07d15-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07d15-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="07d15-110">Ändern der Nameservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="07d15-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="07d15-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="07d15-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="07d15-112">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="07d15-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="07d15-113">Wenn Sie sich für web.com angemeldet haben, haben Sie mithilfe des Setupprozesses web.com **hinzugefügt.**</span><span class="sxs-lookup"><span data-stu-id="07d15-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="07d15-114">Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Microsoft müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle so ändern, dass sie die Namenserver von web.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="07d15-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="07d15-115">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="07d15-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="07d15-116">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="07d15-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="07d15-117">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="07d15-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="07d15-118">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="07d15-118">First nameserver</span></span>  <br/> |<span data-ttu-id="07d15-119">Verwenden Sie den nameserver-Wert, der von web.com.</span><span class="sxs-lookup"><span data-stu-id="07d15-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="07d15-120">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="07d15-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="07d15-121">Verwenden Sie den nameserver-Wert, der von web.com.</span><span class="sxs-lookup"><span data-stu-id="07d15-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="07d15-122">Verwenden Sie mindestens zwei Nameservereinträge.</span><span class="sxs-lookup"><span data-stu-id="07d15-122">You should use at least two name server records.</span></span> <span data-ttu-id="07d15-123">Wenn andere Namenserver aufgelistet sind, sollten Sie sie löschen.</span><span class="sxs-lookup"><span data-stu-id="07d15-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="07d15-124">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="07d15-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="07d15-125">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="07d15-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="07d15-126">Dann sind Ihre Microsoft-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="07d15-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="07d15-127">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="07d15-127">Add a TXT record for verification</span></span>
<span data-ttu-id="07d15-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="07d15-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="07d15-p104">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="07d15-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07d15-p105">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="07d15-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="07d15-133">Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="07d15-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="07d15-134">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="07d15-134">Log in first.</span></span>
  
2. <span data-ttu-id="07d15-135">Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="07d15-136">Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="07d15-137">Klicken Sie **auf der** Seite Domänennamen unter **Text (TXT-Einträge)** auf **TXT-Einträge** bearbeiten, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="07d15-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="07d15-138">**Host**</span></span>|<span data-ttu-id="07d15-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07d15-139">**TTL**</span></span>|<span data-ttu-id="07d15-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="07d15-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="07d15-141">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-141">3600</span></span>  <br/> |<span data-ttu-id="07d15-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="07d15-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="07d15-143">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="07d15-143">**Note:** This is an example.</span></span> <span data-ttu-id="07d15-144">Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="07d15-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="07d15-145">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="07d15-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="07d15-146">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="07d15-147">Warten Sie einige Minuten, bevor Sie ihren neuen TXT-Eintrag überprüfen, damit der gerade erstellte Datensatz über das Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="07d15-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="07d15-148">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="07d15-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="07d15-149">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="07d15-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="07d15-150">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="07d15-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="07d15-151">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="07d15-152">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="07d15-153">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="07d15-p108">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07d15-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="07d15-157">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="07d15-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="07d15-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="07d15-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="07d15-159">Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="07d15-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="07d15-160">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="07d15-160">Log in first.</span></span>
  
2. <span data-ttu-id="07d15-161">Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="07d15-162">Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="07d15-163">Klicken **Sie unter E-Mail-Server (MX-Einträge)** auf **MX-Einträge bearbeiten,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="07d15-164">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="07d15-164">**Priority**</span></span>|<span data-ttu-id="07d15-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07d15-165">**TTL**</span></span>|<span data-ttu-id="07d15-166">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="07d15-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="07d15-167">1</span><span class="sxs-lookup"><span data-stu-id="07d15-167">1</span></span>  <br/> <span data-ttu-id="07d15-168">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="07d15-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="07d15-169">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-169">3600</span></span>  <br/> |<span data-ttu-id="07d15-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="07d15-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="07d15-171">**Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="07d15-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="07d15-172">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="07d15-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="07d15-173">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="07d15-174">Wenn im Abschnitt MX Records  weitere MX-Einträge aufgeführt sind, aktivieren Sie das Kontrollkästchen neben dem Eintrag unter **Löschen**, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="07d15-175">Wählen Sie auf dem Bestätigungsbildschirm Änderungen **speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="07d15-176">Hinzufügen der sechs CNAME-Datensätze, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="07d15-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="07d15-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="07d15-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="07d15-178">Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="07d15-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="07d15-179">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="07d15-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="07d15-180">Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="07d15-181">Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="07d15-182">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="07d15-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="07d15-183">Klicken **Sie unter Hostaliases (CNAME Records)** auf **CNAME-Datensätze** bearbeiten, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="07d15-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="07d15-184">**Alias**</span></span>|<span data-ttu-id="07d15-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07d15-185">**TTL**</span></span>|<span data-ttu-id="07d15-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="07d15-186">**Refers to Host Name**</span></span>|<span data-ttu-id="07d15-187">**Anderer Host**</span><span class="sxs-lookup"><span data-stu-id="07d15-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07d15-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="07d15-188">autodiscover</span></span>  <br/> |<span data-ttu-id="07d15-189">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-189">3600</span></span>  <br/> |<span data-ttu-id="07d15-190">@ (none)</span><span class="sxs-lookup"><span data-stu-id="07d15-190">@ (none)</span></span>  <br/> |<span data-ttu-id="07d15-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="07d15-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="07d15-192">sip</span><span class="sxs-lookup"><span data-stu-id="07d15-192">sip</span></span>  <br/> |<span data-ttu-id="07d15-193">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-193">3600</span></span>  <br/> |<span data-ttu-id="07d15-194">@ (none)</span><span class="sxs-lookup"><span data-stu-id="07d15-194">@ (none)</span></span>  <br/> |<span data-ttu-id="07d15-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="07d15-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="07d15-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="07d15-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="07d15-197">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-197">3600</span></span>  <br/> |<span data-ttu-id="07d15-198">@ (none)</span><span class="sxs-lookup"><span data-stu-id="07d15-198">@ (none)</span></span>  <br/> | <span data-ttu-id="07d15-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="07d15-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="07d15-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="07d15-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="07d15-201">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-201">3600</span></span>  <br/> |<span data-ttu-id="07d15-202">@ (none)</span><span class="sxs-lookup"><span data-stu-id="07d15-202">@ (none)</span></span>  <br/> |<span data-ttu-id="07d15-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="07d15-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="07d15-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="07d15-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="07d15-205">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-205">3600</span></span>  <br/> |<span data-ttu-id="07d15-206">@ (none)</span><span class="sxs-lookup"><span data-stu-id="07d15-206">@ (none)</span></span>  <br/> |<span data-ttu-id="07d15-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="07d15-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="07d15-208">msoid</span><span class="sxs-lookup"><span data-stu-id="07d15-208">msoid</span></span>  <br/> |<span data-ttu-id="07d15-209">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-209">3600</span></span>  <br/> |<span data-ttu-id="07d15-210">@ (none)</span><span class="sxs-lookup"><span data-stu-id="07d15-210">@ (none)</span></span>  <br/> |<span data-ttu-id="07d15-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="07d15-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="07d15-212">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="07d15-213">Fügen Sie die fünf anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="07d15-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="07d15-214">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="07d15-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="07d15-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="07d15-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="07d15-216">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="07d15-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="07d15-217">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="07d15-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="07d15-218">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="07d15-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="07d15-219">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="07d15-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="07d15-220">Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="07d15-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="07d15-221">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="07d15-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="07d15-222">Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="07d15-223">Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="07d15-224">Klicken Sie **auf der** Seite Domänennamen unter **Text (TXT-Einträge)** auf **TXT-Einträge** bearbeiten, und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="07d15-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="07d15-225">**Host**</span></span>|<span data-ttu-id="07d15-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07d15-226">**TTL**</span></span>|<span data-ttu-id="07d15-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="07d15-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="07d15-228">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-228">3600</span></span>  <br/> |<span data-ttu-id="07d15-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="07d15-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="07d15-230">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="07d15-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="07d15-231">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-231">Select **Continue**.</span></span>

6. <span data-ttu-id="07d15-232">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="07d15-233">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="07d15-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="07d15-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="07d15-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="07d15-235">Beachten Sie, dass web.com dafür verantwortlich ist, diese Funktionalität verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="07d15-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="07d15-236">Falls Unterschiede zwischen den unten aufgeführten Schritten und der aktuellen gui(Graphical User Interface web.com angezeigt werden), verwenden Sie bitte die web.com [Community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="07d15-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="07d15-237">Um zu beginnen, wechseln Sie zu Ihrer Domänenseite unter web.com über [diesen Link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="07d15-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="07d15-238">Melden Sie sich zuerst an.</span><span class="sxs-lookup"><span data-stu-id="07d15-238">Log in first.</span></span>
      
2. <span data-ttu-id="07d15-239">Wählen Sie **auf der Seite Account Manager** die Option Meine Domänennamen **aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="07d15-240">Wählen Sie unter **Verwalten *meine Domäne*** die Option **Erweiterte #A0 bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="07d15-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="07d15-241">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="07d15-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="07d15-242">Klicken **Sie unter Dienst (SRV-Einträge)** auf **SRV-Einträge bearbeiten,** und wählen Sie dann die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="07d15-243">**Service**</span><span class="sxs-lookup"><span data-stu-id="07d15-243">**Service**</span></span>|<span data-ttu-id="07d15-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="07d15-244">**Protocol**</span></span>|<span data-ttu-id="07d15-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="07d15-245">**TTL**</span></span>|<span data-ttu-id="07d15-246">**Priority**</span><span class="sxs-lookup"><span data-stu-id="07d15-246">**Priority**</span></span>|<span data-ttu-id="07d15-247">**Weight**</span><span class="sxs-lookup"><span data-stu-id="07d15-247">**Weight**</span></span>|<span data-ttu-id="07d15-248">**Port**</span><span class="sxs-lookup"><span data-stu-id="07d15-248">**Port**</span></span>|<span data-ttu-id="07d15-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="07d15-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="07d15-250">_sip</span><span class="sxs-lookup"><span data-stu-id="07d15-250">_sip</span></span> |<span data-ttu-id="07d15-251">_tls</span><span class="sxs-lookup"><span data-stu-id="07d15-251">_tls</span></span> |<span data-ttu-id="07d15-252">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-252">3600</span></span> | <span data-ttu-id="07d15-253">100</span><span class="sxs-lookup"><span data-stu-id="07d15-253">100</span></span>|<span data-ttu-id="07d15-254">1</span><span class="sxs-lookup"><span data-stu-id="07d15-254">1</span></span> |<span data-ttu-id="07d15-255">443</span><span class="sxs-lookup"><span data-stu-id="07d15-255">443</span></span> |<span data-ttu-id="07d15-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="07d15-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="07d15-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="07d15-257">_sipfederationtls</span></span> |<span data-ttu-id="07d15-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="07d15-258">_tcp</span></span> |<span data-ttu-id="07d15-259">3600</span><span class="sxs-lookup"><span data-stu-id="07d15-259">3600</span></span> |<span data-ttu-id="07d15-260">100</span><span class="sxs-lookup"><span data-stu-id="07d15-260">100</span></span> |<span data-ttu-id="07d15-261">1</span><span class="sxs-lookup"><span data-stu-id="07d15-261">1</span></span> |<span data-ttu-id="07d15-262">5061</span><span class="sxs-lookup"><span data-stu-id="07d15-262">5061</span></span> | <span data-ttu-id="07d15-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="07d15-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="07d15-264">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die Werte aus der zweiten Zeile der Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="07d15-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="07d15-265">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-265">Select **Continue**.</span></span>

7. <span data-ttu-id="07d15-266">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="07d15-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="07d15-p116">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="07d15-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
