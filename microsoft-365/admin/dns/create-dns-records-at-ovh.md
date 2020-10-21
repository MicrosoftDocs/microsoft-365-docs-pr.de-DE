---
title: Erstellen von DNS-Einträgen bei OVH für Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter OVH für Microsoft einrichten.
ms.openlocfilehash: 87a2a731a253fdc0593a1aae8020e615dca63c4a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645815"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="a7ee5-103">Erstellen von DNS-Einträgen bei OVH für Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7ee5-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="a7ee5-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7ee5-105">Wenn OVH Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a7ee5-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="a7ee5-107">Erstellen von DNS-Einträgen bei OVH für Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7ee5-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="a7ee5-108">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="a7ee5-109">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="a7ee5-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="a7ee5-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="a7ee5-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="a7ee5-111">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="a7ee5-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="a7ee5-112">Nachdem Sie diese Einträge bei OVH hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="a7ee5-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7ee5-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a7ee5-116">Add a TXT record for verification</span></span>
<span data-ttu-id="a7ee5-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="a7ee5-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="a7ee5-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7ee5-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a7ee5-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="a7ee5-125">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="a7ee5-127">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="a7ee5-129">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="a7ee5-131">**Txt** auswählen</span><span class="sxs-lookup"><span data-stu-id="a7ee5-131">Select **TXT**</span></span>
    
    ![OVH Select TXT-Eintrag](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="a7ee5-133">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="a7ee5-134">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="a7ee5-135">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-135">**Record type**</span></span>|<span data-ttu-id="a7ee5-136">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-136">**Sub-domain**</span></span>|<span data-ttu-id="a7ee5-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-137">**TTL**</span></span>|<span data-ttu-id="a7ee5-138">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7ee5-139">TXT</span><span class="sxs-lookup"><span data-stu-id="a7ee5-139">TXT</span></span>  <br/> |<span data-ttu-id="a7ee5-140">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="a7ee5-141">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="a7ee5-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="a7ee5-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="a7ee5-143">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-143">**Note:** This is an example.</span></span> <span data-ttu-id="a7ee5-144">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a7ee5-145">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="a7ee5-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="a7ee5-146">Wählen Sie **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="a7ee5-148">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7ee5-149">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a7ee5-150">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7ee5-151">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a7ee5-152">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a7ee5-153">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a7ee5-154">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a7ee5-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a7ee5-158">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a7ee5-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="a7ee5-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="a7ee5-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="a7ee5-163">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="a7ee5-165">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="a7ee5-167">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="a7ee5-169">Wählen Sie **MX**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="a7ee5-171">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="a7ee5-172">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a7ee5-173">Standardmäßig verwendet OVH relative Notation für das Ziel, wodurch der Domänenname am Ende des Ziel Datensatzes hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="a7ee5-174">Um stattdessen absolute Notation zu verwenden, fügen Sie dem Zieldatensatz einen Punkt hinzu, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="a7ee5-175">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-175">**Record type**</span></span>|<span data-ttu-id="a7ee5-176">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-176">**Sub-domain**</span></span>|<span data-ttu-id="a7ee5-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-177">**TTL**</span></span>|<span data-ttu-id="a7ee5-178">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-178">**Priority**</span></span>|<span data-ttu-id="a7ee5-179">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7ee5-180">MX</span><span class="sxs-lookup"><span data-stu-id="a7ee5-180">MX</span></span>  <br/> |<span data-ttu-id="a7ee5-181">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="a7ee5-182">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="a7ee5-183">10 </span><span class="sxs-lookup"><span data-stu-id="a7ee5-183">10</span></span>  <br/> <span data-ttu-id="a7ee5-184">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="a7ee5-185">\<domain-key\>. Mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="a7ee5-186">**Hinweis:** Holen Sie sich Ihr  *\<domain-key\>*  Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="a7ee5-187">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="a7ee5-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX-Eintrag für e-Mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="a7ee5-189">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="a7ee5-191">Wählen Sie **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="a7ee5-193">Wenn weitere MX-Einträge vorhanden sind, löschen Sie diese in der Liste auf der Seite **DNS zone**.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="a7ee5-194">Wählen Sie jeden Datensatz aus, und wählen Sie dann in der Spalte **Aktionen** das Symbol Papierkorb-kann **gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="a7ee5-196">Wählen Sie **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7ee5-197">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="a7ee5-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a7ee5-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="a7ee5-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="a7ee5-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="a7ee5-202">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="a7ee5-204">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="a7ee5-206">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="a7ee5-208">Wählen Sie **CNAME**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="a7ee5-210">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="a7ee5-211">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="a7ee5-212">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="a7ee5-213">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-213">**Record type**</span></span>|<span data-ttu-id="a7ee5-214">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-214">**Sub-domain**</span></span>|<span data-ttu-id="a7ee5-215">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-215">**Target**</span></span>|<span data-ttu-id="a7ee5-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7ee5-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7ee5-217">CNAME</span></span>  <br/> |<span data-ttu-id="a7ee5-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a7ee5-218">autodiscover</span></span>  <br/> |<span data-ttu-id="a7ee5-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="a7ee5-220">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="a7ee5-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7ee5-221">CNAME</span></span>  <br/> |<span data-ttu-id="a7ee5-222">sip</span><span class="sxs-lookup"><span data-stu-id="a7ee5-222">sip</span></span>  <br/> |<span data-ttu-id="a7ee5-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="a7ee5-224">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="a7ee5-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7ee5-225">CNAME</span></span>  <br/> |<span data-ttu-id="a7ee5-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a7ee5-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a7ee5-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="a7ee5-228">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="a7ee5-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7ee5-229">CNAME</span></span>  <br/> |<span data-ttu-id="a7ee5-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a7ee5-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a7ee5-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="a7ee5-232">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="a7ee5-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7ee5-233">CNAME</span></span>  <br/> |<span data-ttu-id="a7ee5-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a7ee5-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a7ee5-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="a7ee5-236">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-236">3600 seconds</span></span>  <br/> |
   
    ![OVH-CNAME-Eintrag](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="a7ee5-238">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="a7ee5-240">Wählen Sie **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="a7ee5-241">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="a7ee5-242">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7ee5-243">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="a7ee5-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7ee5-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="a7ee5-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7ee5-245">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a7ee5-246">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a7ee5-247">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="a7ee5-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a7ee5-248">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a7ee5-p116">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="a7ee5-252">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="a7ee5-254">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="a7ee5-256">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="a7ee5-258">Wählen Sie **txt**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="a7ee5-259">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="a7ee5-260">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-260">**Record type**</span></span>|<span data-ttu-id="a7ee5-261">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-261">**Sub-domain**</span></span>|<span data-ttu-id="a7ee5-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-262">**TTL**</span></span>|<span data-ttu-id="a7ee5-263">**TXT-Wert**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7ee5-264">TXT</span><span class="sxs-lookup"><span data-stu-id="a7ee5-264">TXT</span></span>  <br/> |<span data-ttu-id="a7ee5-265">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="a7ee5-266">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="a7ee5-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7ee5-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a7ee5-268">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH-Add TXT-Eintrag für SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="a7ee5-270">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-270">Select **Next**.</span></span>
    
    ![OVH Hinzufügen des txt-Eintrags für SPF und Auswählen von Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="a7ee5-272">Wählen Sie **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7ee5-274">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="a7ee5-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a7ee5-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="a7ee5-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="a7ee5-p117">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="a7ee5-279">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="a7ee5-281">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="a7ee5-283">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="a7ee5-285">Wählen Sie **SRV**aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="a7ee5-287">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="a7ee5-288">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="a7ee5-289">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="a7ee5-290">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-290">**Record type**</span></span>|<span data-ttu-id="a7ee5-291">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-291">**Sub-domain**</span></span>|<span data-ttu-id="a7ee5-292">**Priority**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-292">**Priority**</span></span>|<span data-ttu-id="a7ee5-293">**Weight**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-293">**Weight**</span></span>|<span data-ttu-id="a7ee5-294">**Port**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-294">**Port**</span></span>|<span data-ttu-id="a7ee5-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-295">**TTL**</span></span>|<span data-ttu-id="a7ee5-296">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="a7ee5-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7ee5-297">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="a7ee5-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="a7ee5-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="a7ee5-299">100</span><span class="sxs-lookup"><span data-stu-id="a7ee5-299">100</span></span>  <br/> |<span data-ttu-id="a7ee5-300">1</span><span class="sxs-lookup"><span data-stu-id="a7ee5-300">1</span></span>  <br/> |<span data-ttu-id="a7ee5-301">443</span><span class="sxs-lookup"><span data-stu-id="a7ee5-301">443</span></span>  <br/> |<span data-ttu-id="a7ee5-302">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="a7ee5-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="a7ee5-304">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="a7ee5-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="a7ee5-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a7ee5-306">100</span><span class="sxs-lookup"><span data-stu-id="a7ee5-306">100</span></span>  <br/> |<span data-ttu-id="a7ee5-307">1</span><span class="sxs-lookup"><span data-stu-id="a7ee5-307">1</span></span>  <br/> |<span data-ttu-id="a7ee5-308">5061</span><span class="sxs-lookup"><span data-stu-id="a7ee5-308">5061</span></span>  <br/> |<span data-ttu-id="a7ee5-309">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="a7ee5-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH-SRV-Eintrag](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="a7ee5-312">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="a7ee5-314">Wählen Sie **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="a7ee5-p119">Wiederholen Sie die vorherigen Schritte, um den anderen SRV-Eintrag zu erstellen. Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="a7ee5-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a7ee5-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
