---
title: Erstellen von DNS-Einträgen bei Google Domains für Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, lync und andere Dienste in Google Domains für Microsoft einrichten.
ms.openlocfilehash: 6bfe32ba8f77adec97f4ab5ee40e92126be91f10
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049011"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="e1966-103">Erstellen von DNS-Einträgen bei Google Domains für Microsoft</span><span class="sxs-lookup"><span data-stu-id="e1966-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="e1966-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="e1966-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e1966-105">Wenn Google Domains Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e1966-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="e1966-106">Nachdem Sie diese Einträge bei Google-Domänen hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="e1966-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="e1966-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="e1966-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="e1966-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="e1966-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="e1966-109">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie weitere Informationen unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1966-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e1966-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e1966-110">Add a TXT record for verification</span></span>
<span data-ttu-id="e1966-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e1966-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e1966-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="e1966-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1966-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="e1966-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e1966-p104">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e1966-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="e1966-119">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e1966-120">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="e1966-121">Suchen Sie auf der Seite " **Meine Domänen** " nach der Domäne, die Sie mit Microsoft verwenden möchten, und wählen Sie den Link **Verwalten** daneben aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="e1966-122">Wählen Sie in der linken Navigationsleiste **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="e1966-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1966-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1966-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1966-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e1966-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1966-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1966-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="e1966-126">**Name**</span></span> <br/> |<span data-ttu-id="e1966-127">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e1966-127">**Type**</span></span> <br/> |<span data-ttu-id="e1966-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1966-128">**TTL**</span></span> <br/> |<span data-ttu-id="e1966-129">**Daten**</span><span class="sxs-lookup"><span data-stu-id="e1966-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="e1966-130">TXT</span><span class="sxs-lookup"><span data-stu-id="e1966-130">TXT</span></span>  <br/> |<span data-ttu-id="e1966-131">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-131">1H</span></span>  <br/> |<span data-ttu-id="e1966-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e1966-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e1966-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="e1966-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
4. <span data-ttu-id="e1966-136">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1966-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="e1966-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1966-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e1966-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="e1966-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e1966-139">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="e1966-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e1966-140">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="e1966-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e1966-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e1966-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e1966-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e1966-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1966-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e1966-147">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e1966-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e1966-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e1966-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e1966-p108">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e1966-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="e1966-152">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="e1966-153">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="e1966-154">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e1966-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e1966-155">Wenn Sie über ein G Suite-E-Mail-Konto verfügen, müssen Sie zuerst die diesem Konto zugeordneten MX-Einträge löschen.</span><span class="sxs-lookup"><span data-stu-id="e1966-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="e1966-156">Die G Suite MX-Einträge verhindern, dass Sie andere MX-Einträge hinzufügen, einschließlich derer, die für Microsoft erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e1966-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="e1966-157">Beachten Sie, dass Ihr G Suite-Konto durch das Löschen der G Suite-Einträge nicht gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="e1966-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="e1966-158">Gehen Sie folgendermaßen vor, um Ihre G Suite-MX-Einträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e1966-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="e1966-159">Wählen Sie im Abschnitt **synthetische Datensätze** im Bereich **G Suite** die Option **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="e1966-160">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="e1966-160">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie im Abschnitt synthetische Datensätze löschen aus.](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="e1966-162">Wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-162">Select **Delete**.</span></span>
    
    ![Wählen Sie löschen aus.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="e1966-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1966-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1966-165">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1966-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e1966-166">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1966-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1966-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="e1966-167">**Name**</span></span>|<span data-ttu-id="e1966-168">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e1966-168">**Type**</span></span>|<span data-ttu-id="e1966-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1966-169">**TTL**</span></span>|<span data-ttu-id="e1966-170">**Daten**</span><span class="sxs-lookup"><span data-stu-id="e1966-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e1966-171">MX</span><span class="sxs-lookup"><span data-stu-id="e1966-171">MX</span></span>  <br/> |<span data-ttu-id="e1966-172">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-172">1H</span></span>  <br/> |<span data-ttu-id="e1966-173">0  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="e1966-174">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="e1966-p110">Die **0** ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="e1966-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="e1966-177">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="e1966-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="e1966-178">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="e1966-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="e1966-179">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e1966-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="e1966-181">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1966-181">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="e1966-183">Wenn es weitere benutzerdefinierte MX-Einträge gibt, entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="e1966-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="e1966-184">Wählen Sie in der Zeile MX Record die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Wählen Sie bearbeiten in der Zeile MX-Eintrag aus.](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="e1966-186">Wählen Sie für jeden der anderen benutzerdefinierten MX-Einträge den Eintrag im Feld **Daten** aus, und drücken Sie dann die **ENTF** -Taste auf der Tastatur, um den Datensatz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e1966-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="e1966-187">Fahren Sie fort, bis Sie den **Data**-Eintrag für jeden anderen MX-Eintrag gelöscht haben.</span><span class="sxs-lookup"><span data-stu-id="e1966-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="e1966-189">Wenn Sie den **Daten** Eintrag für jeden der anderen MX-Einträge gelöscht haben, wählen Sie **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e1966-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Wählen Sie speichern aus.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1966-191">Hinzufügen der fünf für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="e1966-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="e1966-192">Um zu beginnen, navigieren Sie zu Ihrer [Google Domänen Seite]https://domains.google.com/registrar) (und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="e1966-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="e1966-193">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e1966-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e1966-194">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1966-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="e1966-195">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e1966-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="e1966-196">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1966-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e1966-197">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1966-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1966-198">**Name**</span><span class="sxs-lookup"><span data-stu-id="e1966-198">**Name**</span></span>|<span data-ttu-id="e1966-199">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e1966-199">**Type**</span></span>|<span data-ttu-id="e1966-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1966-200">**TTL**</span></span>|<span data-ttu-id="e1966-201">**Daten**</span><span class="sxs-lookup"><span data-stu-id="e1966-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1966-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e1966-202">autodiscover</span></span>  <br/> |<span data-ttu-id="e1966-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1966-203">CNAME</span></span>  <br/> |<span data-ttu-id="e1966-204">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-204">1H</span></span>  <br/> |<span data-ttu-id="e1966-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="e1966-206">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e1966-207">sip</span><span class="sxs-lookup"><span data-stu-id="e1966-207">sip</span></span>  <br/> |<span data-ttu-id="e1966-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1966-208">CNAME</span></span>  <br/> |<span data-ttu-id="e1966-209">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-209">1H</span></span>  <br/> |<span data-ttu-id="e1966-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e1966-211">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e1966-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e1966-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e1966-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1966-213">CNAME</span></span>  <br/> |<span data-ttu-id="e1966-214">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-214">1H</span></span>  <br/> |<span data-ttu-id="e1966-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="e1966-216">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e1966-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e1966-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e1966-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1966-218">CNAME</span></span>  <br/> |<span data-ttu-id="e1966-219">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-219">1H</span></span>  <br/> |<span data-ttu-id="e1966-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="e1966-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="e1966-221">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="e1966-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e1966-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e1966-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="e1966-223">CNAME</span></span>  <br/> |<span data-ttu-id="e1966-224">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-224">1H</span></span>  <br/> |<span data-ttu-id="e1966-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="e1966-226">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="e1966-228">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1966-228">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="e1966-230">Fügen Sie die anderen vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1966-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="e1966-231">Erstellen Sie im Abschnitt **benutzerdefinierte Ressourceneinträge** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1966-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="e1966-232">Wiederholen Sie diesen Vorgang, bis Sie alle erforderlichen CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e1966-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e1966-233">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="e1966-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1966-234">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="e1966-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e1966-235">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="e1966-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e1966-236">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="e1966-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e1966-237">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e1966-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="e1966-238">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="e1966-238">Need examples?</span></span> <span data-ttu-id="e1966-239">Lesen Sie die Informationen unter [Externe DNS-Einträge für Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="e1966-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="e1966-240">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1966-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="e1966-p113">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e1966-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="e1966-244">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e1966-245">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="e1966-246">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e1966-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="e1966-247">Wählen Sie im Abschnitt **benutzerdefinierte Ressourceneinträge** in der Zeile TXT-Eintrag die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="e1966-p114">Google Domains speichert TXT-Einträge als Satz, der mehrere Datensätze enthalten kann. Wenn Sie über mindestens einen weiteren TXT-Eintrag verfügen, z. B. den zur Überprüfung Ihrer Domäne verwendeten TXT-Eintrag, müssen Sie dieser Datensatzgruppe neue TXT-Einträge hinzufügen. Jeder Versuch, TXT-Einträge als getrennte Einträge einzugeben, führt zu einer Fehlermeldung wegen eines **doppelten Datensatzes**.</span><span class="sxs-lookup"><span data-stu-id="e1966-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Wählen Sie bearbeiten in der Zeile TXT-Eintrag aus.](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="e1966-252">Wählen Sie das Steuerelement **(+)** aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-252">Select the **(+)** control.</span></span> 
    
    ![Wählen Sie das Plus-Steuerelement](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="e1966-254">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e1966-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="e1966-255">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="e1966-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="e1966-256">**Data**</span><span class="sxs-lookup"><span data-stu-id="e1966-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="e1966-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e1966-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="e1966-258">Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="e1966-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="e1966-260">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e1966-260">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e1966-262">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="e1966-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e1966-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e1966-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e1966-p115">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e1966-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="e1966-267">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="e1966-268">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="e1966-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="e1966-269">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e1966-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="e1966-270">Fügen Sie den ersten SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1966-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="e1966-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="e1966-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e1966-272">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="e1966-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e1966-273">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="e1966-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="e1966-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="e1966-274">**Name**</span></span>|<span data-ttu-id="e1966-275">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e1966-275">**Type**</span></span>|<span data-ttu-id="e1966-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e1966-276">**TTL**</span></span>|<span data-ttu-id="e1966-277">**Daten**</span><span class="sxs-lookup"><span data-stu-id="e1966-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e1966-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e1966-278">_sip._tls</span></span>|<span data-ttu-id="e1966-279">SRV</span><span class="sxs-lookup"><span data-stu-id="e1966-279">SRV</span></span>|<span data-ttu-id="e1966-280">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-280">1H</span></span>|<span data-ttu-id="e1966-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="e1966-282">**Dieser Wert muss mit einem Punkt (.) enden.** **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit der gesamte Abstand korrekt bleibt.</span><span class="sxs-lookup"><span data-stu-id="e1966-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="e1966-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e1966-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="e1966-284">SRV</span><span class="sxs-lookup"><span data-stu-id="e1966-284">SRV</span></span>|<span data-ttu-id="e1966-285">1H</span><span class="sxs-lookup"><span data-stu-id="e1966-285">1H</span></span>|<span data-ttu-id="e1966-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="e1966-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="e1966-287">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="e1966-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="e1966-288">Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="e1966-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="e1966-290">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1966-290">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="e1966-292">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1966-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e1966-293">Erstellen Sie im Abschnitt **benutzerdefinierte Ressourceneinträge** einen Datensatz mithilfe der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1966-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e1966-p118">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e1966-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
