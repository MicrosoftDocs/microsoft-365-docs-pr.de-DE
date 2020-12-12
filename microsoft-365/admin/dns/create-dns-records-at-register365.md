---
title: Erstellen von DNS-Einträgen bei Register365 für Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Register365 für Microsoft einrichten.
ms.openlocfilehash: 6cefdeff3da1256911d80066b55b00f5bef24055
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656915"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="418fd-103">Erstellen von DNS-Einträgen bei Register365 für Microsoft</span><span class="sxs-lookup"><span data-stu-id="418fd-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="418fd-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="418fd-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="418fd-105">Wenn Register365 Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="418fd-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="418fd-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="418fd-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="418fd-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="418fd-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="418fd-108">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="418fd-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="418fd-109">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="418fd-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="418fd-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="418fd-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="418fd-111">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="418fd-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="418fd-112">Nachdem Sie diese Einträge bei Microsoft hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="418fd-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="418fd-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="418fd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="418fd-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="418fd-116">Add a TXT record for verification</span></span>
<span data-ttu-id="418fd-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="418fd-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="418fd-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="418fd-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="418fd-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="418fd-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="418fd-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="418fd-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="418fd-125">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="418fd-126">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-126">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="418fd-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="418fd-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="418fd-129">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="418fd-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="418fd-130">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="418fd-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="418fd-131">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="418fd-132">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="418fd-132">**Host name**</span></span>|<span data-ttu-id="418fd-133">**Type**</span><span class="sxs-lookup"><span data-stu-id="418fd-133">**Type**</span></span>|<span data-ttu-id="418fd-134">**Result**</span><span class="sxs-lookup"><span data-stu-id="418fd-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="418fd-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="418fd-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="418fd-136">TXT</span><span class="sxs-lookup"><span data-stu-id="418fd-136">TXT</span></span>  <br/> |<span data-ttu-id="418fd-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="418fd-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="418fd-138">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="418fd-138">**Note:** This is an example.</span></span> <span data-ttu-id="418fd-139">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="418fd-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="418fd-140">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="418fd-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="418fd-142">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-142">Select **Save**.</span></span>
    
    <span data-ttu-id="418fd-143">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-143">(You may have to scroll down.)</span></span>
    
    !["Save" auswählen](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="418fd-145">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="418fd-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="418fd-146">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="418fd-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="418fd-147">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="418fd-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="418fd-148">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="418fd-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="418fd-149">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="418fd-150">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="418fd-151">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="418fd-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="418fd-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="418fd-155">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="418fd-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="418fd-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="418fd-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="418fd-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="418fd-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="418fd-160">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="418fd-161">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-161">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="418fd-163">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Mail exchange records** in den Feldern für den neuen Eintrag die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="418fd-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="418fd-164">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="418fd-165">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="418fd-165">**Host name**</span></span>|<span data-ttu-id="418fd-166">**Priority**</span><span class="sxs-lookup"><span data-stu-id="418fd-166">**Priority**</span></span>|<span data-ttu-id="418fd-167">**Result**</span><span class="sxs-lookup"><span data-stu-id="418fd-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="418fd-168">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="418fd-169">1 </span><span class="sxs-lookup"><span data-stu-id="418fd-169">1</span></span>  <br/> <span data-ttu-id="418fd-170">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="418fd-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="418fd-171">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="418fd-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="418fd-172">**Hinweis:** Holen Sie sich Ihr  *\<domain-key\>*  Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="418fd-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="418fd-173">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="418fd-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="418fd-175">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-175">Select **Save**.</span></span>
    
    <span data-ttu-id="418fd-176">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-176">(You may have to scroll down.)</span></span>
    
    !["Save" auswählen](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="418fd-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="418fd-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="418fd-180">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-180">Select **Save**.</span></span>
    
    <span data-ttu-id="418fd-181">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-181">(You may have to scroll down.)</span></span>
    
    !["Save" auswählen](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="418fd-183">Hinzufügen der sechs CNAME-Einträge, die für Microsoft erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="418fd-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="418fd-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="418fd-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="418fd-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="418fd-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="418fd-188">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="418fd-189">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-189">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="418fd-191">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **A, CNAME, AAAA, TXT and NS records** in den Feldern für die neuen Einträge die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="418fd-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="418fd-192">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="418fd-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="418fd-193">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="418fd-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="418fd-194">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="418fd-195">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="418fd-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="418fd-196">\*\*\*\*Type\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="418fd-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="418fd-197">\*\*\*\*Result\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="418fd-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="418fd-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="418fd-198">autodiscover</span></span>  <br/> |<span data-ttu-id="418fd-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="418fd-199">CNAME</span></span>  <br/> |<span data-ttu-id="418fd-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="418fd-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="418fd-201">sip</span><span class="sxs-lookup"><span data-stu-id="418fd-201">sip</span></span>  <br/> |<span data-ttu-id="418fd-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="418fd-202">CNAME</span></span>  <br/> |<span data-ttu-id="418fd-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="418fd-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="418fd-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="418fd-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="418fd-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="418fd-205">CNAME</span></span>  <br/> |<span data-ttu-id="418fd-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="418fd-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="418fd-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="418fd-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="418fd-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="418fd-208">CNAME</span></span>  <br/> |<span data-ttu-id="418fd-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="418fd-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="418fd-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="418fd-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="418fd-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="418fd-211">CNAME</span></span>  <br/> |<span data-ttu-id="418fd-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="418fd-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="418fd-214">Wählen Sie **Save** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-214">Select **Save**.</span></span>
    
    !["Save" auswählen](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="418fd-216">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="418fd-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="418fd-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="418fd-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="418fd-218">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="418fd-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="418fd-219">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="418fd-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="418fd-220">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="418fd-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="418fd-221">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="418fd-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="418fd-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="418fd-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="418fd-225">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="418fd-226">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-226">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="418fd-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="418fd-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="418fd-229">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="418fd-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="418fd-230">(Wenn Sie eine Zeile hinzufügen möchten, wählen Sie **Add a/CNAME Records (+)** aus.)</span><span class="sxs-lookup"><span data-stu-id="418fd-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="418fd-231">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="418fd-232">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="418fd-232">**Host name**</span></span>|<span data-ttu-id="418fd-233">**Type**</span><span class="sxs-lookup"><span data-stu-id="418fd-233">**Type**</span></span>|<span data-ttu-id="418fd-234">**Result**</span><span class="sxs-lookup"><span data-stu-id="418fd-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="418fd-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="418fd-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="418fd-236">TXT</span><span class="sxs-lookup"><span data-stu-id="418fd-236">TXT</span></span>  <br/> |<span data-ttu-id="418fd-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="418fd-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="418fd-238">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="418fd-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Eingeben von Werten auf der Seite "DNS-Zone hinzufügen/ändern"](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="418fd-240">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-240">Select **Save**.</span></span>
    
    <span data-ttu-id="418fd-241">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-241">(You may have to scroll down.)</span></span>
    
    !["Save" auswählen](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="418fd-243">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="418fd-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="418fd-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="418fd-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="418fd-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://admin.register365.com/dns/) zu Ihrer Domänenseite bei Register365. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="418fd-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    ![Die Anmeldeseite der Systemsteuerung](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="418fd-248">Suchen Sie auf der Seite **Dashboard** nach dem Namen der Domäne, die Sie gerade aktualisieren, und wählen Sie dann in der Dropdownliste den Eintrag **DNS Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="418fd-249">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-249">(You may have to scroll down.)</span></span>
    
    ![Auswählen von DNS-Einstellungen in der Liste](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="418fd-251">Geben Sie auf der Seite **Add/Modify DNS Zone** im Abschnitt **Service records** in den Feldern für die neuen Einträge die Werte aus der nachstehenden Tabelle manuell ein, oder kopieren Sie die Werte, und fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="418fd-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="418fd-252">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="418fd-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="418fd-253">**Name**</span></span>|<span data-ttu-id="418fd-254">**Priority**</span><span class="sxs-lookup"><span data-stu-id="418fd-254">**Priority**</span></span>|<span data-ttu-id="418fd-255">**Weight**</span><span class="sxs-lookup"><span data-stu-id="418fd-255">**Weight**</span></span>|<span data-ttu-id="418fd-256">**Port**</span><span class="sxs-lookup"><span data-stu-id="418fd-256">**Port**</span></span>|<span data-ttu-id="418fd-257">**Result**</span><span class="sxs-lookup"><span data-stu-id="418fd-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="418fd-258">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="418fd-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="418fd-259">100</span><span class="sxs-lookup"><span data-stu-id="418fd-259">100</span></span>  <br/> |<span data-ttu-id="418fd-260">1 </span><span class="sxs-lookup"><span data-stu-id="418fd-260">1</span></span>  <br/> |<span data-ttu-id="418fd-261">443</span><span class="sxs-lookup"><span data-stu-id="418fd-261">443</span></span>  <br/> |<span data-ttu-id="418fd-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="418fd-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="418fd-263">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="418fd-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="418fd-264">100</span><span class="sxs-lookup"><span data-stu-id="418fd-264">100</span></span>  <br/> |<span data-ttu-id="418fd-265">1 </span><span class="sxs-lookup"><span data-stu-id="418fd-265">1</span></span>  <br/> |<span data-ttu-id="418fd-266">5061</span><span class="sxs-lookup"><span data-stu-id="418fd-266">5061</span></span>  <br/> |<span data-ttu-id="418fd-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="418fd-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Eingeben von Werten im Abschnitt "Diensteinträge"](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="418fd-269">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="418fd-269">Select **Save**.</span></span>
    
    <span data-ttu-id="418fd-270">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="418fd-270">(You may have to scroll down.)</span></span>
    
    !["Save" auswählen](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="418fd-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="418fd-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
