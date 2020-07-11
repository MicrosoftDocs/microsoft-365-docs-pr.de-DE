---
title: Erstellen von DNS-Einträgen für Microsoft bei Google Domains
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste bei Google Domains für Microsoft einrichten.
ms.openlocfilehash: e6b1dd1eb90957a4e7fe22bd4b66ac87b2a51d09
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400449"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="7dd4e-103">Erstellen von DNS-Einträgen für Microsoft bei Google Domains</span><span class="sxs-lookup"><span data-stu-id="7dd4e-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="7dd4e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7dd4e-105">Wenn Google Domains Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="7dd4e-106">Nachdem Sie diese Einträge bei Google Domains hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="7dd4e-107">In der Regel dauert es etwa 15 Minuten, bis DNS-Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7dd4e-108">Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7dd4e-109">Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Microsoft hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7dd4e-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="7dd4e-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7dd4e-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7dd4e-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7dd4e-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="7dd4e-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7dd4e-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="7dd4e-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-115">You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7dd4e-116">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-116">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="7dd4e-117">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-117">You'll be prompted to sign in.</span></span> <span data-ttu-id="7dd4e-118">To do so:</span><span class="sxs-lookup"><span data-stu-id="7dd4e-118">To do so:</span></span>
    
1. <span data-ttu-id="7dd4e-119">Wählen Sie **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="7dd4e-120">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="7dd4e-121">Suchen Sie auf der Seite **My domains** die Domäne, die Sie mit Microsoft verwenden möchten, und wählen Sie den Link **MANAGE** daneben aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="7dd4e-122">Wählen Sie im linken Navigationsbereich **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="7dd4e-123">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7dd4e-124">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7dd4e-125">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7dd4e-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-126">**Name**</span></span> <br/> |<span data-ttu-id="7dd4e-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-127">**Type**</span></span> <br/> |<span data-ttu-id="7dd4e-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-128">**TTL**</span></span> <br/> |<span data-ttu-id="7dd4e-129">**Data**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="7dd4e-130">TXT</span><span class="sxs-lookup"><span data-stu-id="7dd4e-130">TXT</span></span>  <br/> |<span data-ttu-id="7dd4e-131">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-131">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7dd4e-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7dd4e-133">**Note:** This is an example.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-133">**Note:** This is an example.</span></span> <span data-ttu-id="7dd4e-134">Use your specific **Destination or Points to Address** value here, from the table.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7dd4e-135">How do I find this?</span><span class="sxs-lookup"><span data-stu-id="7dd4e-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="7dd4e-136">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="7dd4e-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7dd4e-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="7dd4e-139">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7dd4e-140">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7dd4e-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7dd4e-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7dd4e-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7dd4e-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7dd4e-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7dd4e-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="7dd4e-147">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="7dd4e-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7dd4e-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7dd4e-149">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-149">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="7dd4e-150">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-150">You'll be prompted to sign in.</span></span> <span data-ttu-id="7dd4e-151">To do so:</span><span class="sxs-lookup"><span data-stu-id="7dd4e-151">To do so:</span></span>
    
2. <span data-ttu-id="7dd4e-152">Wählen Sie **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="7dd4e-153">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="7dd4e-154">Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7dd4e-155">Wenn Sie über ein G Suite-E-Mail-Konto verfügen, müssen Sie zuerst die diesem Konto zugeordneten MX-Einträge löschen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="7dd4e-156">Die G Suite-MX-Einträge verhindern, dass Sie andere MX-Einträge hinzufügen, einschließlich der für Microsoft erforderlichen Einträge.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="7dd4e-157">Beachten Sie, dass Ihr G Suite-Konto durch das Löschen der G Suite-Einträge nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="7dd4e-158">Gehen Sie folgendermaßen vor, um Ihre G Suite-MX-Einträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="7dd4e-159">Wählen Sie im Abschnitt **Synthetic records** im Bereich **G Suite** die Option **Delete** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="7dd4e-160">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-160">(You may have to scroll down.)</span></span>
    
    ![Im Abschnitt "Synthetic records" auf "Delete" klicken](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="7dd4e-162">Wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-162">Select **Delete**.</span></span>
    
    !["Löschen" auswählen](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="7dd4e-164">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7dd4e-165">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7dd4e-166">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7dd4e-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-167">**Name**</span></span>|<span data-ttu-id="7dd4e-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-168">**Type**</span></span>|<span data-ttu-id="7dd4e-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-169">**TTL**</span></span>|<span data-ttu-id="7dd4e-170">**Data**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="7dd4e-171">MX</span><span class="sxs-lookup"><span data-stu-id="7dd4e-171">MX</span></span>  <br/> |<span data-ttu-id="7dd4e-172">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-172">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7dd4e-174">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7dd4e-175">The **0** is the MX priority value.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-175">The **0** is the MX priority value.</span></span> <span data-ttu-id="7dd4e-176">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-176">Add it to the beginning of the MX value, separated from the remainder of the value by a space.</span></span>  <br/> <span data-ttu-id="7dd4e-177">**Hinweis:** Erhalten Sie Ihren \<*domain-key*\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="7dd4e-178">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="7dd4e-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="7dd4e-179">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="7dd4e-181">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-181">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="7dd4e-183">Wenn es weitere benutzerdefinierte MX-Einträge gibt, entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="7dd4e-184">Wählen Sie **Edit** in der Zeile mit dem MX-Eintrag aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-184">Select **Edit** in the MX record row.</span></span> 
    
    !["Edit" in der Zeile mit dem MX-Eintrag auswählen](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="7dd4e-186">Wählen Sie für jeden weiteren benutzerdefinierten MX-Eintrag den Eintrag im Feld **Data** aus, und drücken Sie dann die** **ENTF-TASTE auf der Tastatur, um diesen Eintrag zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="7dd4e-187">Fahren Sie fort, bis Sie den **Data**-Eintrag für jeden anderen MX-Eintrag gelöscht haben.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="7dd4e-189">Wenn Sie den **Data**-Eintrag für jeden anderen MX-Eintrag gelöscht haben, wählen Sie **Save** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    !["Save" auswählen](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="7dd4e-191">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="7dd4e-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="7dd4e-192">Wechseln Sie im ersten Schritt zu Ihrer [Google Domains-Seite] (https://domains.google.com/registrar), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="7dd4e-193">Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="7dd4e-194">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="7dd4e-195">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="7dd4e-196">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7dd4e-197">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7dd4e-198">**Name**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-198">**Name**</span></span>|<span data-ttu-id="7dd4e-199">**Type**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-199">**Type**</span></span>|<span data-ttu-id="7dd4e-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-200">**TTL**</span></span>|<span data-ttu-id="7dd4e-201">**Data**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7dd4e-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7dd4e-202">autodiscover</span></span>  <br/> |<span data-ttu-id="7dd4e-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="7dd4e-203">CNAME</span></span>  <br/> |<span data-ttu-id="7dd4e-204">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-204">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7dd4e-206">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dd4e-207">sip</span><span class="sxs-lookup"><span data-stu-id="7dd4e-207">sip</span></span>  <br/> |<span data-ttu-id="7dd4e-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="7dd4e-208">CNAME</span></span>  <br/> |<span data-ttu-id="7dd4e-209">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-209">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7dd4e-211">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dd4e-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7dd4e-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7dd4e-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="7dd4e-213">CNAME</span></span>  <br/> |<span data-ttu-id="7dd4e-214">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-214">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7dd4e-216">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dd4e-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7dd4e-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7dd4e-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="7dd4e-218">CNAME</span></span>  <br/> |<span data-ttu-id="7dd4e-219">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-219">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7dd4e-221">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="7dd4e-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7dd4e-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7dd4e-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="7dd4e-223">CNAME</span></span>  <br/> |<span data-ttu-id="7dd4e-224">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-224">1H</span></span>  <br/> |<span data-ttu-id="7dd4e-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7dd4e-226">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="7dd4e-228">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-228">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="7dd4e-230">Fügen Sie die anderen vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="7dd4e-231">Erstellen Sie im Abschnitt **Custom resource records** einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut die Option **Add** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="7dd4e-232">Wiederholen Sie diesen Vorgang, bis Sie alle erforderlichen CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7dd4e-233">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="7dd4e-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dd4e-234">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7dd4e-235">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7dd4e-236">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="7dd4e-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7dd4e-237">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="7dd4e-238">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="7dd4e-238">Need examples?</span></span> <span data-ttu-id="7dd4e-239">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="7dd4e-240">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="7dd4e-241">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-241">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="7dd4e-242">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-242">You'll be prompted to sign in.</span></span> <span data-ttu-id="7dd4e-243">To do so:</span><span class="sxs-lookup"><span data-stu-id="7dd4e-243">To do so:</span></span>
    
1. <span data-ttu-id="7dd4e-244">Wählen Sie **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="7dd4e-245">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="7dd4e-246">Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="7dd4e-247">Wählen Sie im Abschnitt **Custom resource records** in der Zeile mit dem TXT-Eintrag die Option **Edit** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7dd4e-248">Google Domains stores TXT records as a set that may contain multiple records.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-248">Google Domains stores TXT records as a set that may contain multiple records.</span></span> <span data-ttu-id="7dd4e-249">When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-249">When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set.</span></span> <span data-ttu-id="7dd4e-250">Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-250">Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    !["Edit" in der Zeile mit dem TXT-Eintrag auswählen](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="7dd4e-252">Wählen Sie das Steuerelement **(+)** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-252">Select the **(+)** control.</span></span> 
    
    ![Pluszeichen auswählen](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="7dd4e-254">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="7dd4e-255">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="7dd4e-256">**Daten**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="7dd4e-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7dd4e-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="7dd4e-258">Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="7dd4e-260">Wählen Sie **Save** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-260">Select **Save**.</span></span>
    
    !["Save" auswählen](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="7dd4e-262">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="7dd4e-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="7dd4e-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7dd4e-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7dd4e-264">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-264">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="7dd4e-265">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-265">You'll be prompted to sign in.</span></span> <span data-ttu-id="7dd4e-266">To do so:</span><span class="sxs-lookup"><span data-stu-id="7dd4e-266">To do so:</span></span>
    
2. <span data-ttu-id="7dd4e-267">Wählen Sie **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="7dd4e-268">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="7dd4e-269">Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="7dd4e-270">Fügen Sie den ersten SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="7dd4e-271">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7dd4e-272">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="7dd4e-273">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="7dd4e-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="7dd4e-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-274">**Name**</span></span>|<span data-ttu-id="7dd4e-275">**Type**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-275">**Type**</span></span>|<span data-ttu-id="7dd4e-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-276">**TTL**</span></span>|<span data-ttu-id="7dd4e-277">**Data**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7dd4e-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7dd4e-278">_sip._tls</span></span>|<span data-ttu-id="7dd4e-279">SRV</span><span class="sxs-lookup"><span data-stu-id="7dd4e-279">SRV</span></span>|<span data-ttu-id="7dd4e-280">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-280">1H</span></span>|<span data-ttu-id="7dd4e-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="7dd4e-282">**Dieser Wert MUSS mit einem Punkt (.) enden.** **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="7dd4e-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7dd4e-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7dd4e-284">SRV</span><span class="sxs-lookup"><span data-stu-id="7dd4e-284">SRV</span></span>|<span data-ttu-id="7dd4e-285">1H</span><span class="sxs-lookup"><span data-stu-id="7dd4e-285">1H</span></span>|<span data-ttu-id="7dd4e-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="7dd4e-287">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="7dd4e-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="7dd4e-288">Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Geben Sie im Abschnitt "Custom resource records" Werte ein. Sie können die Werte auch kopieren und einfügen.](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="7dd4e-290">Wählen Sie **Add** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-290">Select **Add**.</span></span>
    
    !["Add" auswählen](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="7dd4e-292">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="7dd4e-293">Erstellen Sie im Abschnitt **Custom resource records** einen Eintrag mit den Werten aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut die Option **Add** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7dd4e-294">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-294">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7dd4e-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="7dd4e-295">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7dd4e-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7dd4e-296">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
