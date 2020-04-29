---
title: Erstellen von DNS-Einträgen bei Amazon Webdienste (AWS) für Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei Amazon Webdienste (AWS) für Microsoft einrichten.
ms.openlocfilehash: 1ce4d47dce2fce177efafade49b78ea706cf14e2
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919539"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="03f84-103">Erstellen von DNS-Einträgen bei Amazon Webdienste (AWS) für Microsoft</span><span class="sxs-lookup"><span data-stu-id="03f84-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="03f84-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="03f84-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="03f84-105">Wenn AWS Ihr DNS-Hosting-Anbieter ist, befolgen Sie die Schritte in diesem Artikel, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype online for Business usw. einzurichten.</span><span class="sxs-lookup"><span data-stu-id="03f84-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="03f84-106">Nachdem Sie diese Einträge bei AWS hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="03f84-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="03f84-107">Informationen über Webhosting und DNS für Websites mit Microsfot finden Sie unter [Verwenden einer öffentlichen Website mit Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="03f84-107">To learn about webhosting and DNS for websites with Microsfot, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="03f84-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="03f84-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="03f84-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="03f84-111">Add a TXT record for verification</span></span>
<span data-ttu-id="03f84-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="03f84-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="03f84-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="03f84-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03f84-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="03f84-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="03f84-117">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS.</span><span class="sxs-lookup"><span data-stu-id="03f84-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="03f84-118">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="03f84-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="03f84-119">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="03f84-120">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="03f84-120">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="03f84-121">Wählen Sie **Daten Satz Satz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="03f84-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="03f84-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="03f84-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="03f84-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="03f84-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="03f84-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="03f84-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="03f84-126">**Name**</span></span> <br/> |<span data-ttu-id="03f84-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="03f84-127">**Type**</span></span> <br/> |<span data-ttu-id="03f84-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="03f84-128">**Alias**</span></span> <br/> |<span data-ttu-id="03f84-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="03f84-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="03f84-130">**Value**</span><span class="sxs-lookup"><span data-stu-id="03f84-130">**Value**</span></span> <br/> |<span data-ttu-id="03f84-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="03f84-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="03f84-132">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="03f84-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="03f84-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="03f84-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="03f84-134">No</span><span class="sxs-lookup"><span data-stu-id="03f84-134">No</span></span>  <br/> |<span data-ttu-id="03f84-135">300</span><span class="sxs-lookup"><span data-stu-id="03f84-135">300</span></span>  <br/> |<span data-ttu-id="03f84-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="03f84-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="03f84-137">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="03f84-137">**Note:** This is an example.</span></span> <span data-ttu-id="03f84-138">Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03f84-138">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="03f84-139">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="03f84-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="03f84-140">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="03f84-141">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="03f84-142">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="03f84-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="03f84-143">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="03f84-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="03f84-144">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="03f84-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="03f84-145">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="03f84-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="03f84-146">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="03f84-147">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="03f84-148">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="03f84-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="03f84-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="03f84-152">Hinzufügen eines MX-Eintrags, damit e-Mails für Ihre Domäne an Microsoft 365 gelangen</span><span class="sxs-lookup"><span data-stu-id="03f84-152">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="03f84-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="03f84-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="03f84-p108">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="03f84-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="03f84-156">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="03f84-157">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="03f84-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="03f84-158">Wählen Sie **Daten Satz Satz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="03f84-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="03f84-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="03f84-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="03f84-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="03f84-161">**Name**</span><span class="sxs-lookup"><span data-stu-id="03f84-161">**Name**</span></span>|<span data-ttu-id="03f84-162">**Typ**</span><span class="sxs-lookup"><span data-stu-id="03f84-162">**Type**</span></span>|<span data-ttu-id="03f84-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="03f84-163">**Alias**</span></span>|<span data-ttu-id="03f84-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="03f84-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="03f84-165">**Value**</span><span class="sxs-lookup"><span data-stu-id="03f84-165">**Value**</span></span>|<span data-ttu-id="03f84-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="03f84-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="03f84-167">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="03f84-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="03f84-168">MX - Mail exchange</span><span class="sxs-lookup"><span data-stu-id="03f84-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="03f84-169">No</span><span class="sxs-lookup"><span data-stu-id="03f84-169">No</span></span>  <br/> |<span data-ttu-id="03f84-170">300</span><span class="sxs-lookup"><span data-stu-id="03f84-170">300</span></span>  <br/> |<span data-ttu-id="03f84-171">0  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="03f84-p109">Die 0 ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="03f84-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="03f84-174">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="03f84-175">**Hinweis:** Rufen Sie \<Ihren *Domänenschlüssel* \> aus Ihrem Microsoft 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="03f84-175">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="03f84-176">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="03f84-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="03f84-177">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-177">Simple</span></span>  <br/> |
       
    ![AWS-BP-configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="03f84-179">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="03f84-181">Wenn es weitere MX-Einträge gibt, entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="03f84-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="03f84-182">AWS speichert MX-Einträge als Satz, der mehrere Datensätze enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="03f84-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="03f84-183">**DO NOT** Wählen Sie nicht **Daten Satz Satz löschen**aus, da dadurch alle MX-Einträge gelöscht werden, einschließlich des soeben hinzugefügten MX-Eintrags.</span><span class="sxs-lookup"><span data-stu-id="03f84-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="03f84-184">Verwenden Sie stattdessen die folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="03f84-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="03f84-185">Wählen Sie zuerst den MX-Eintragssatz aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="03f84-187">Löschen Sie als nächstes im Bereich **Edit Record Set** die einzelnen überflüssigen MX-Einträge, indem Sie den Eintrag im Feld **Value** auswählen und dann **ENTF** auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="03f84-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="03f84-189">Wählen Sie **Speichersatz speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="03f84-191">Fügen Sie die fünf CNAME-Einträge hinzu, die für Microsoft 365 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="03f84-191">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="03f84-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="03f84-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="03f84-p112">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="03f84-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="03f84-195">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="03f84-196">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="03f84-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="03f84-197">Wählen Sie **Daten Satz Satz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="03f84-198">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="03f84-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="03f84-199">Geben Sie im Bereich **Create Record Set** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="03f84-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="03f84-200">(Wählen Sie die Werte für **Type** und **Routing Policy** aus den Dropdownlisten aus.)</span><span class="sxs-lookup"><span data-stu-id="03f84-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="03f84-201">**Name**</span><span class="sxs-lookup"><span data-stu-id="03f84-201">**Name**</span></span>|<span data-ttu-id="03f84-202">**Typ**</span><span class="sxs-lookup"><span data-stu-id="03f84-202">**Type**</span></span>|<span data-ttu-id="03f84-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="03f84-203">**Alias**</span></span>|<span data-ttu-id="03f84-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="03f84-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="03f84-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="03f84-205">**Value**</span></span>|<span data-ttu-id="03f84-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="03f84-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="03f84-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="03f84-207">autodiscover</span></span>  <br/> |<span data-ttu-id="03f84-208">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="03f84-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="03f84-209">No</span><span class="sxs-lookup"><span data-stu-id="03f84-209">No</span></span>  <br/> |<span data-ttu-id="03f84-210">300</span><span class="sxs-lookup"><span data-stu-id="03f84-210">300</span></span>  <br/> |<span data-ttu-id="03f84-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="03f84-212">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="03f84-213">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="03f84-214">sip</span><span class="sxs-lookup"><span data-stu-id="03f84-214">sip</span></span>  <br/> |<span data-ttu-id="03f84-215">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="03f84-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="03f84-216">No</span><span class="sxs-lookup"><span data-stu-id="03f84-216">No</span></span>  <br/> |<span data-ttu-id="03f84-217">300</span><span class="sxs-lookup"><span data-stu-id="03f84-217">300</span></span>  <br/> |<span data-ttu-id="03f84-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="03f84-219">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="03f84-220">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="03f84-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="03f84-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="03f84-222">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="03f84-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="03f84-223">No</span><span class="sxs-lookup"><span data-stu-id="03f84-223">No</span></span>  <br/> |<span data-ttu-id="03f84-224">300</span><span class="sxs-lookup"><span data-stu-id="03f84-224">300</span></span>  <br/> |<span data-ttu-id="03f84-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="03f84-226">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="03f84-227">Einfach</span><span class="sxs-lookup"><span data-stu-id="03f84-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="03f84-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="03f84-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="03f84-229">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="03f84-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="03f84-230">No</span><span class="sxs-lookup"><span data-stu-id="03f84-230">No</span></span>  <br/> |<span data-ttu-id="03f84-231">300</span><span class="sxs-lookup"><span data-stu-id="03f84-231">300</span></span>  <br/> |<span data-ttu-id="03f84-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="03f84-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="03f84-233">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="03f84-234">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="03f84-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="03f84-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="03f84-236">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="03f84-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="03f84-237">No</span><span class="sxs-lookup"><span data-stu-id="03f84-237">No</span></span>  <br/> |<span data-ttu-id="03f84-238">300</span><span class="sxs-lookup"><span data-stu-id="03f84-238">300</span></span>  <br/> |<span data-ttu-id="03f84-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="03f84-240">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="03f84-241">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-241">Simple</span></span>  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="03f84-243">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="03f84-245">Fügen Sie die anderen vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="03f84-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="03f84-246">Wählen Sie auf der Seite **gehostete Zonen** die Option **Daten Satz Satz erstellen**aus, erstellen Sie einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Erstellen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="03f84-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="03f84-247">Wiederholen Sie diesen Vorgang, bis Sie alle fünf CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="03f84-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="03f84-248">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="03f84-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="03f84-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="03f84-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="03f84-250">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="03f84-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="03f84-251">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="03f84-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="03f84-252">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="03f84-252">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="03f84-253">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="03f84-253">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="03f84-254">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="03f84-254">Need examples?</span></span> <span data-ttu-id="03f84-255">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="03f84-255">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="03f84-256">Zum Überprüfen des SPF-Eintrags können Sie eines dieser[SPF-Überprüfungstools](../setup/domains-faq.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="03f84-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="03f84-257">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS.</span><span class="sxs-lookup"><span data-stu-id="03f84-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="03f84-258">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="03f84-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="03f84-259">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="03f84-260">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="03f84-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="03f84-261">Wählen Sie den **txt** -Daten Satz Satz aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="03f84-p115">Drücken Sie im Bereich **Edit Record Set** am Ende des aktuellen Eintrags im Feld **Value:** für den vorhandenen Eintrag die EINGABETASTE auf der Tastatur, um eine neue Zeile zu erstellen. Geben Sie dann in diese neue Zeile (unter dem vorhandenen Wert) direkt oder durch Kopieren und Einfügen den Wert aus der folgenden Tabelle ein. (Ein Beispiel können Sie in der Abbildung unter der Tabelle sehen.)</span><span class="sxs-lookup"><span data-stu-id="03f84-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="03f84-265">**Wert:**</span><span class="sxs-lookup"><span data-stu-id="03f84-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="03f84-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="03f84-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="03f84-p116">(Die in der Bildschirmanleitung angezeigten Anführungszeichen werden automatisch eingefügt. Sie müssen Sie nicht manuell eingeben.)  </span><span class="sxs-lookup"><span data-stu-id="03f84-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="03f84-269">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="03f84-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![AWS-BP-configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="03f84-271">Wählen Sie **Speichersatz speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="03f84-273">Fügen Sie die beiden SRV-Einträge hinzu, die für Microsoft 365 erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="03f84-273">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="03f84-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="03f84-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="03f84-p117">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="03f84-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="03f84-277">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="03f84-278">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="03f84-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="03f84-279">Wählen Sie **Daten Satz Satz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="03f84-280">Fügen Sie den ersten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="03f84-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="03f84-281">Geben Sie im Bereich **Create Record Set** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="03f84-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="03f84-282">(Wählen Sie die Werte für **Type** und **Routing Policy** aus den Dropdownlisten aus.)</span><span class="sxs-lookup"><span data-stu-id="03f84-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="03f84-283">**Name**</span><span class="sxs-lookup"><span data-stu-id="03f84-283">**Name**</span></span>|<span data-ttu-id="03f84-284">**Typ**</span><span class="sxs-lookup"><span data-stu-id="03f84-284">**Type**</span></span>|<span data-ttu-id="03f84-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="03f84-285">**Alias**</span></span>|<span data-ttu-id="03f84-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="03f84-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="03f84-287">**Value**</span><span class="sxs-lookup"><span data-stu-id="03f84-287">**Value**</span></span>|<span data-ttu-id="03f84-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="03f84-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="03f84-289">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="03f84-289">_sip._tls</span></span>|<span data-ttu-id="03f84-290">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="03f84-290">SRV - Service locator</span></span>|<span data-ttu-id="03f84-291">No</span><span class="sxs-lookup"><span data-stu-id="03f84-291">No</span></span>|<span data-ttu-id="03f84-292">300</span><span class="sxs-lookup"><span data-stu-id="03f84-292">300</span></span>|<span data-ttu-id="03f84-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="03f84-294">**Dieser Wert muss mit einem Punkt (.) enden.**></span><span class="sxs-lookup"><span data-stu-id="03f84-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="03f84-295">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="03f84-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="03f84-296">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-296">Simple</span></span>|
    |<span data-ttu-id="03f84-297">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="03f84-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="03f84-298">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="03f84-298">SRV - Service locator</span></span>|<span data-ttu-id="03f84-299">No</span><span class="sxs-lookup"><span data-stu-id="03f84-299">No</span></span>|<span data-ttu-id="03f84-300">300</span><span class="sxs-lookup"><span data-stu-id="03f84-300">300</span></span>|<span data-ttu-id="03f84-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="03f84-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="03f84-302">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="03f84-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="03f84-303">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="03f84-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="03f84-304">Simple</span><span class="sxs-lookup"><span data-stu-id="03f84-304">Simple</span></span>|
   
    ![AWS-BP-configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="03f84-306">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="03f84-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="03f84-308">Fügen Sie den anderen SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="03f84-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="03f84-309">Wählen Sie auf der Seite **gehostete Zonen** die Option **Daten Satz Satz erstellen**aus, erstellen Sie einen Datensatz mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Erstellen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="03f84-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="03f84-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="03f84-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
