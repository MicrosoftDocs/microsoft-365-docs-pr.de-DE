---
title: Erstellen von DNS-Einträgen bei OVH für Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter OVH für Microsoft einrichten.
ms.openlocfilehash: b462979a3ab1bcf769c78d15d9fd3ad03f307ef0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400340"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a><span data-ttu-id="b7231-103">Erstellen von DNS-Einträgen bei OVH für Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7231-103">Create DNS records at OVH for Microsoft</span></span>

<span data-ttu-id="b7231-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b7231-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b7231-105">Wenn OVH Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b7231-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="b7231-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="b7231-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="b7231-107">Erstellen von DNS-Einträgen bei OVH für Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7231-107">Create DNS records at OVH for Microsoft</span></span>](#create-dns-records-at-ovh-for-microsoft)
    
- [<span data-ttu-id="b7231-108">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b7231-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="b7231-109">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b7231-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="b7231-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b7231-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="b7231-111">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="b7231-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="b7231-112">Nachdem Sie diese Einträge bei OVH hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="b7231-112">After you add these records at OVH, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="b7231-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b7231-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b7231-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b7231-116">Add a TXT record for verification</span></span>
<span data-ttu-id="b7231-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="b7231-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="b7231-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="b7231-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7231-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="b7231-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b7231-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b7231-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b7231-125">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b7231-125">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b7231-127">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-127">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b7231-129">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-129">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b7231-131">**Txt** auswählen</span><span class="sxs-lookup"><span data-stu-id="b7231-131">Select **TXT**</span></span>
    
    ![OVH Select TXT-Eintrag](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="b7231-133">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b7231-133">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="b7231-134">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="b7231-134">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="b7231-135">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="b7231-135">**Record type**</span></span>|<span data-ttu-id="b7231-136">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="b7231-136">**Sub-domain**</span></span>|<span data-ttu-id="b7231-137">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b7231-137">**TTL**</span></span>|<span data-ttu-id="b7231-138">**Wert**</span><span class="sxs-lookup"><span data-stu-id="b7231-138">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b7231-139">TXT</span><span class="sxs-lookup"><span data-stu-id="b7231-139">TXT</span></span>  <br/> |<span data-ttu-id="b7231-140">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="b7231-140">(leave blank)</span></span>  <br/> |<span data-ttu-id="b7231-141">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-141">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b7231-142">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="b7231-142">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="b7231-143">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b7231-143">**Note:** This is an example.</span></span> <span data-ttu-id="b7231-144">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b7231-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="b7231-145">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b7231-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b7231-146">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-146">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="b7231-148">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b7231-148">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b7231-149">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="b7231-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b7231-150">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b7231-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b7231-151">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="b7231-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b7231-152">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="b7231-153">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="b7231-154">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="b7231-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b7231-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b7231-158">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b7231-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b7231-159"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="b7231-159"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="b7231-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b7231-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b7231-163">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b7231-163">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b7231-165">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-165">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b7231-167">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-167">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b7231-169">Wählen Sie **MX**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-169">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="b7231-171">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b7231-171">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="b7231-172">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="b7231-172">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b7231-173">Standardmäßig verwendet OVH relative Notation für das Ziel, wodurch der Domänenname am Ende des Ziel Datensatzes hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b7231-173">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="b7231-174">Um stattdessen absolute Notation zu verwenden, fügen Sie dem Zieldatensatz einen Punkt hinzu, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b7231-174">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="b7231-175">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="b7231-175">**Record type**</span></span>|<span data-ttu-id="b7231-176">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="b7231-176">**Sub-domain**</span></span>|<span data-ttu-id="b7231-177">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b7231-177">**TTL**</span></span>|<span data-ttu-id="b7231-178">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="b7231-178">**Priority**</span></span>|<span data-ttu-id="b7231-179">**Target**</span><span class="sxs-lookup"><span data-stu-id="b7231-179">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b7231-180">MX</span><span class="sxs-lookup"><span data-stu-id="b7231-180">MX</span></span>  <br/> |<span data-ttu-id="b7231-181">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="b7231-181">(leave blank)</span></span>  <br/> |<span data-ttu-id="b7231-182">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-182">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b7231-183">10  </span><span class="sxs-lookup"><span data-stu-id="b7231-183">10</span></span>  <br/> <span data-ttu-id="b7231-184">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="b7231-184">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="b7231-185">\<domain-key\>. Mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-185">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="b7231-186">**Hinweis:** Holen Sie sich Ihr *\<domain-key\>* Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="b7231-186">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="b7231-187">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b7231-187">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX-Eintrag für e-Mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="b7231-189">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-189">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="b7231-191">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-191">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="b7231-193">Wenn weitere MX-Einträge vorhanden sind, löschen Sie diese in der Liste auf der Seite **DNS zone**.</span><span class="sxs-lookup"><span data-stu-id="b7231-193">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="b7231-194">Wählen Sie jeden Datensatz aus, und wählen Sie dann in der Spalte **Aktionen** das Symbol Papierkorb-kann **gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-194">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="b7231-196">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-196">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b7231-197">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="b7231-197">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b7231-198"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="b7231-198"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="b7231-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b7231-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b7231-202">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b7231-202">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b7231-204">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-204">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b7231-206">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-206">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b7231-208">Wählen Sie **CNAME**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-208">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="b7231-210">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b7231-210">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="b7231-211">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b7231-211">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="b7231-212">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="b7231-212">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="b7231-213">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="b7231-213">**Record type**</span></span>|<span data-ttu-id="b7231-214">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="b7231-214">**Sub-domain**</span></span>|<span data-ttu-id="b7231-215">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="b7231-215">**Target**</span></span>|<span data-ttu-id="b7231-216">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b7231-216">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b7231-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="b7231-217">CNAME</span></span>  <br/> |<span data-ttu-id="b7231-218">autodiscover</span><span class="sxs-lookup"><span data-stu-id="b7231-218">autodiscover</span></span>  <br/> |<span data-ttu-id="b7231-219">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-219">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="b7231-220">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-220">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b7231-221">CNAME</span><span class="sxs-lookup"><span data-stu-id="b7231-221">CNAME</span></span>  <br/> |<span data-ttu-id="b7231-222">sip</span><span class="sxs-lookup"><span data-stu-id="b7231-222">sip</span></span>  <br/> |<span data-ttu-id="b7231-223">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-223">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="b7231-224">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-224">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b7231-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="b7231-225">CNAME</span></span>  <br/> |<span data-ttu-id="b7231-226">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b7231-226">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b7231-227">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-227">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="b7231-228">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-228">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b7231-229">CNAME</span><span class="sxs-lookup"><span data-stu-id="b7231-229">CNAME</span></span>  <br/> |<span data-ttu-id="b7231-230">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b7231-230">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b7231-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="b7231-231">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="b7231-232">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-232">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="b7231-233">CNAME</span><span class="sxs-lookup"><span data-stu-id="b7231-233">CNAME</span></span>  <br/> |<span data-ttu-id="b7231-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b7231-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b7231-235">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-235">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="b7231-236">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-236">3600 seconds</span></span>  <br/> |
   
    ![OVH-CNAME-Eintrag](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="b7231-238">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-238">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="b7231-240">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-240">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="b7231-241">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7231-241">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="b7231-242">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b7231-242">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b7231-243">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="b7231-243">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b7231-244"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="b7231-244"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7231-245">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="b7231-245">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b7231-246">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="b7231-246">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b7231-247">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="b7231-247">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b7231-248">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="b7231-248">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="b7231-p116">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b7231-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b7231-252">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b7231-252">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b7231-254">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-254">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b7231-256">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-256">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b7231-258">Wählen Sie **txt**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-258">Select **TXT**.</span></span>
    
6. <span data-ttu-id="b7231-259">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b7231-259">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="b7231-260">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="b7231-260">**Record type**</span></span>|<span data-ttu-id="b7231-261">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="b7231-261">**Sub-domain**</span></span>|<span data-ttu-id="b7231-262">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b7231-262">**TTL**</span></span>|<span data-ttu-id="b7231-263">**TXT-Wert**</span><span class="sxs-lookup"><span data-stu-id="b7231-263">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b7231-264">TXT</span><span class="sxs-lookup"><span data-stu-id="b7231-264">TXT</span></span>  <br/> |<span data-ttu-id="b7231-265">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="b7231-265">(leave blank)</span></span>  <br/> |<span data-ttu-id="b7231-266">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-266">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b7231-267">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b7231-267">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b7231-268">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="b7231-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH-Add TXT-Eintrag für SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="b7231-270">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-270">Select **Next**.</span></span>
    
    ![OVH Hinzufügen des txt-Eintrags für SPF und Auswählen von Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="b7231-272">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-272">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b7231-274">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="b7231-274">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b7231-275"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="b7231-275"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="b7231-p117">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b7231-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="b7231-279">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="b7231-279">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="b7231-281">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-281">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="b7231-283">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-283">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="b7231-285">Wählen Sie **SRV**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-285">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="b7231-287">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b7231-287">Create the first SRV record.</span></span>
    
    <span data-ttu-id="b7231-288">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b7231-288">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="b7231-289">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="b7231-289">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="b7231-290">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="b7231-290">**Record type**</span></span>|<span data-ttu-id="b7231-291">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="b7231-291">**Sub-domain**</span></span>|<span data-ttu-id="b7231-292">**Priority**</span><span class="sxs-lookup"><span data-stu-id="b7231-292">**Priority**</span></span>|<span data-ttu-id="b7231-293">**Weight**</span><span class="sxs-lookup"><span data-stu-id="b7231-293">**Weight**</span></span>|<span data-ttu-id="b7231-294">**Port**</span><span class="sxs-lookup"><span data-stu-id="b7231-294">**Port**</span></span>|<span data-ttu-id="b7231-295">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b7231-295">**TTL**</span></span>|<span data-ttu-id="b7231-296">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="b7231-296">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b7231-297">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="b7231-297">SRV (Service)</span></span>  <br/> |<span data-ttu-id="b7231-298">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="b7231-298">_sip._tls</span></span>  <br/> |<span data-ttu-id="b7231-299">100</span><span class="sxs-lookup"><span data-stu-id="b7231-299">100</span></span>  <br/> |<span data-ttu-id="b7231-300">1 </span><span class="sxs-lookup"><span data-stu-id="b7231-300">1</span></span>  <br/> |<span data-ttu-id="b7231-301">443</span><span class="sxs-lookup"><span data-stu-id="b7231-301">443</span></span>  <br/> |<span data-ttu-id="b7231-302">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-302">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b7231-303">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-303">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="b7231-304">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="b7231-304">SRV (Service)</span></span>  <br/> |<span data-ttu-id="b7231-305">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b7231-305">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="b7231-306">100</span><span class="sxs-lookup"><span data-stu-id="b7231-306">100</span></span>  <br/> |<span data-ttu-id="b7231-307">1 </span><span class="sxs-lookup"><span data-stu-id="b7231-307">1</span></span>  <br/> |<span data-ttu-id="b7231-308">5061</span><span class="sxs-lookup"><span data-stu-id="b7231-308">5061</span></span>  <br/> |<span data-ttu-id="b7231-309">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="b7231-309">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="b7231-310">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b7231-310">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH-SRV-Eintrag](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="b7231-312">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-312">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="b7231-314">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="b7231-314">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="b7231-p119">Wiederholen Sie die vorherigen Schritte, um den anderen SRV-Eintrag zu erstellen. Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="b7231-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b7231-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b7231-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
