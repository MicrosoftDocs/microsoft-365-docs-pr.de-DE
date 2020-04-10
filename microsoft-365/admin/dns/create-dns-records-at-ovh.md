---
title: Erstellen von DNS-Einträgen für Office 365 bei OVH
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter OVH für Office 365 einrichten.
ms.openlocfilehash: 3ba4e61c875f74a0a6cf76c8b7cd82ea88e0221b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211110"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a><span data-ttu-id="35128-103">Erstellen von DNS-Einträgen für Office 365 bei OVH</span><span class="sxs-lookup"><span data-stu-id="35128-103">Create DNS records at OVH for Office 365</span></span>

<span data-ttu-id="35128-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="35128-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="35128-105">Wenn OVH Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="35128-105">If OVH is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="35128-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="35128-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="35128-107">Erstellen von DNS-Einträgen bei OVH für Office 365</span><span class="sxs-lookup"><span data-stu-id="35128-107">Create DNS records at OVH for Office 365</span></span>](#create-dns-records-at-ovh-for-office-365)
    
- [<span data-ttu-id="35128-108">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="35128-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="35128-109">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="35128-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="35128-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="35128-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="35128-111">Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="35128-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="35128-112">Nachdem Sie diese Einträge bei OVH hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="35128-112">After you add these records at OVH, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="35128-113">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="35128-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="35128-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35128-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="35128-117">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="35128-117">Add a TXT record for verification</span></span>
<span data-ttu-id="35128-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="35128-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="35128-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="35128-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35128-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="35128-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="35128-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="35128-p104">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="35128-126">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="35128-126">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="35128-128">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-128">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="35128-130">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-130">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="35128-132">**Txt** auswählen</span><span class="sxs-lookup"><span data-stu-id="35128-132">Select **TXT**</span></span>
    
    ![OVH Select TXT-Eintrag](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. <span data-ttu-id="35128-134">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="35128-134">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="35128-135">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="35128-135">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="35128-136">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="35128-136">**Record type**</span></span>|<span data-ttu-id="35128-137">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="35128-137">**Sub-domain**</span></span>|<span data-ttu-id="35128-138">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35128-138">**TTL**</span></span>|<span data-ttu-id="35128-139">**Wert**</span><span class="sxs-lookup"><span data-stu-id="35128-139">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35128-140">TXT</span><span class="sxs-lookup"><span data-stu-id="35128-140">TXT</span></span>  <br/> |<span data-ttu-id="35128-141">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="35128-141">(leave blank)</span></span>  <br/> |<span data-ttu-id="35128-142">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-142">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="35128-143">MS=msxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="35128-143">MS=msxxxxxxxx</span></span>  <br/> <span data-ttu-id="35128-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="35128-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="35128-147">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-147">Select **Confirm**.</span></span> 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. <span data-ttu-id="35128-149">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="35128-149">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="35128-150">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="35128-150">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="35128-151">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="35128-151">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="35128-152">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="35128-152">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="35128-153">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="35128-153">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="35128-154">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-154">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="35128-155">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-155">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="35128-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35128-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="35128-159">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="35128-159">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="35128-160"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="35128-160"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="35128-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="35128-p108">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="35128-164">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="35128-164">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="35128-166">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-166">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="35128-168">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-168">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="35128-170">Wählen Sie **MX**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-170">Select **MX**.</span></span>
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. <span data-ttu-id="35128-172">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="35128-172">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> <span data-ttu-id="35128-173">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="35128-173">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="35128-174">Standardmäßig verwendet OVH relative Notation für das Ziel, wodurch der Domänenname am Ende des Ziel Datensatzes hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="35128-174">By default OVH uses relative notation for the target, which adds the domain name to the end of the target record.</span></span> <span data-ttu-id="35128-175">Um stattdessen absolute Notation zu verwenden, fügen Sie dem Zieldatensatz einen Punkt hinzu, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="35128-175">To use absolute notation instead, add a dot to the target record as shown in the table below.</span></span> 
  
    |<span data-ttu-id="35128-176">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="35128-176">**Record type**</span></span>|<span data-ttu-id="35128-177">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="35128-177">**Sub-domain**</span></span>|<span data-ttu-id="35128-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35128-178">**TTL**</span></span>|<span data-ttu-id="35128-179">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="35128-179">**Priority**</span></span>|<span data-ttu-id="35128-180">**Target**</span><span class="sxs-lookup"><span data-stu-id="35128-180">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35128-181">MX</span><span class="sxs-lookup"><span data-stu-id="35128-181">MX</span></span>  <br/> |<span data-ttu-id="35128-182">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="35128-182">(leave blank)</span></span>  <br/> |<span data-ttu-id="35128-183">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-183">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="35128-184">10  </span><span class="sxs-lookup"><span data-stu-id="35128-184">10</span></span>  <br/> <span data-ttu-id="35128-185">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="35128-185">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="35128-186">\<Domänenschlüssel\>.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="35128-186">\<domain-key\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="35128-187">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="35128-187">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="35128-188">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="35128-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX-Eintrag für e-Mail](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. <span data-ttu-id="35128-190">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-190">Select **Next**.</span></span>
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. <span data-ttu-id="35128-192">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-192">Select **Confirm**.</span></span>
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. <span data-ttu-id="35128-194">Wenn weitere MX-Einträge vorhanden sind, löschen Sie diese in der Liste auf der Seite **DNS zone**.</span><span class="sxs-lookup"><span data-stu-id="35128-194">If there are any other MX records, delete them all in the list on the **DNS zone** page.</span></span> <span data-ttu-id="35128-195">Wählen Sie jeden Datensatz aus, und wählen Sie dann in der Spalte **Aktionen** das Symbol Papierkorb-kann **gelöscht** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-195">Select each record and then, in the **Actions** column, select the trash-can **Delete** icon.</span></span> 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. <span data-ttu-id="35128-197">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-197">Select **Confirm**.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="35128-198">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="35128-198">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="35128-199"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="35128-199"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="35128-p113">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="35128-p113">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="35128-203">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="35128-203">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="35128-205">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-205">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="35128-207">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-207">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="35128-209">Wählen Sie **CNAME**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-209">Select **CNAME**.</span></span>
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. <span data-ttu-id="35128-211">Erstellen Sie den ersten CNAME-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="35128-211">Create the first CNAME record.</span></span>
    
    <span data-ttu-id="35128-212">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="35128-212">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="35128-213">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="35128-213">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="35128-214">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="35128-214">**Record type**</span></span>|<span data-ttu-id="35128-215">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="35128-215">**Sub-domain**</span></span>|<span data-ttu-id="35128-216">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="35128-216">**Target**</span></span>|<span data-ttu-id="35128-217">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35128-217">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35128-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="35128-218">CNAME</span></span>  <br/> |<span data-ttu-id="35128-219">autodiscover</span><span class="sxs-lookup"><span data-stu-id="35128-219">autodiscover</span></span>  <br/> |<span data-ttu-id="35128-220">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="35128-220">autodiscover.outlook.com.</span></span>  <br/> |<span data-ttu-id="35128-221">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-221">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="35128-222">CNAME</span><span class="sxs-lookup"><span data-stu-id="35128-222">CNAME</span></span>  <br/> |<span data-ttu-id="35128-223">sip</span><span class="sxs-lookup"><span data-stu-id="35128-223">sip</span></span>  <br/> |<span data-ttu-id="35128-224">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="35128-224">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="35128-225">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-225">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="35128-226">CNAME</span><span class="sxs-lookup"><span data-stu-id="35128-226">CNAME</span></span>  <br/> |<span data-ttu-id="35128-227">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="35128-227">lyncdiscover</span></span>  <br/> |<span data-ttu-id="35128-228">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="35128-228">webdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="35128-229">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-229">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="35128-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="35128-230">CNAME</span></span>  <br/> |<span data-ttu-id="35128-231">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="35128-231">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="35128-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="35128-232">enterpriseregistration.windows.net.</span></span>  <br/> |<span data-ttu-id="35128-233">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-233">3600 seconds</span></span>  <br/> |
    |<span data-ttu-id="35128-234">CNAME</span><span class="sxs-lookup"><span data-stu-id="35128-234">CNAME</span></span>  <br/> |<span data-ttu-id="35128-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="35128-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="35128-236">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="35128-236">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |<span data-ttu-id="35128-237">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-237">3600 seconds</span></span>  <br/> |
   
    ![OVH-CNAME-Eintrag](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. <span data-ttu-id="35128-239">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-239">Select **Next**.</span></span>
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. <span data-ttu-id="35128-241">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-241">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="35128-242">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35128-242">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="35128-243">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="35128-243">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="35128-244">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="35128-244">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="35128-245"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="35128-245"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="35128-246">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="35128-246">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="35128-247">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="35128-247">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="35128-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="35128-248">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="35128-249">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="35128-249">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="35128-p116">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="35128-p116">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="35128-253">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="35128-253">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="35128-255">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-255">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="35128-257">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-257">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="35128-259">Wählen Sie **txt**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-259">Select **TXT**.</span></span>
    
6. <span data-ttu-id="35128-260">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="35128-260">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="35128-261">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="35128-261">**Record type**</span></span>|<span data-ttu-id="35128-262">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="35128-262">**Sub-domain**</span></span>|<span data-ttu-id="35128-263">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35128-263">**TTL**</span></span>|<span data-ttu-id="35128-264">**TXT-Wert**</span><span class="sxs-lookup"><span data-stu-id="35128-264">**TXT Value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35128-265">TXT</span><span class="sxs-lookup"><span data-stu-id="35128-265">TXT</span></span>  <br/> |<span data-ttu-id="35128-266">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="35128-266">(leave blank)</span></span>  <br/> |<span data-ttu-id="35128-267">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-267">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="35128-268">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="35128-268">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="35128-269">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="35128-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![OVH-Add TXT-Eintrag für SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. <span data-ttu-id="35128-271">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-271">Select **Next**.</span></span>
    
    ![OVH Hinzufügen des txt-Eintrags für SPF und Auswählen von Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. <span data-ttu-id="35128-273">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-273">Select **Confirm**.</span></span>
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="35128-275">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="35128-275">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="35128-276"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="35128-276"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="35128-p117">Um zu beginnen, navigieren Sie über [diesen Link](https://www.ovh.com/manager/) zu Ihrer Domänenseite bei OVH. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="35128-p117">To get started, go to your domains page in OVH by using [this link](https://www.ovh.com/manager/). You'll be prompted to log in.</span></span>
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. <span data-ttu-id="35128-280">Wählen Sie unter **Domänen**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="35128-280">Under **Domains**, select the name of the domain that you want edit.</span></span>
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. <span data-ttu-id="35128-282">Wählen Sie **DNS-Zone**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-282">Select **DNS zone**.</span></span>
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. <span data-ttu-id="35128-284">Wählen Sie **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-284">Select **Add an entry**.</span></span>
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. <span data-ttu-id="35128-286">Wählen Sie **SRV**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-286">Select **SRV**.</span></span>
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. <span data-ttu-id="35128-288">Erstellen Sie den ersten SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="35128-288">Create the first SRV record.</span></span>
    
    <span data-ttu-id="35128-289">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="35128-289">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> <span data-ttu-id="35128-290">Um einen TTL-Wert zuzuweisen, wählen Sie in der Dropdownliste **personalisiert** aus, und geben Sie den Wert in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="35128-290">To assign a TTL value, choose **Personalized** from the drop-down list, and then type the value in the text box.</span></span> 
    
    |<span data-ttu-id="35128-291">**Eintragstyp**</span><span class="sxs-lookup"><span data-stu-id="35128-291">**Record type**</span></span>|<span data-ttu-id="35128-292">**Unterdomäne**</span><span class="sxs-lookup"><span data-stu-id="35128-292">**Sub-domain**</span></span>|<span data-ttu-id="35128-293">**Priority**</span><span class="sxs-lookup"><span data-stu-id="35128-293">**Priority**</span></span>|<span data-ttu-id="35128-294">**Weight**</span><span class="sxs-lookup"><span data-stu-id="35128-294">**Weight**</span></span>|<span data-ttu-id="35128-295">**Port**</span><span class="sxs-lookup"><span data-stu-id="35128-295">**Port**</span></span>|<span data-ttu-id="35128-296">**TTL**</span><span class="sxs-lookup"><span data-stu-id="35128-296">**TTL**</span></span>|<span data-ttu-id="35128-297">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="35128-297">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="35128-298">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="35128-298">SRV (Service)</span></span>  <br/> |<span data-ttu-id="35128-299">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="35128-299">_sip._tls</span></span>  <br/> |<span data-ttu-id="35128-300">100</span><span class="sxs-lookup"><span data-stu-id="35128-300">100</span></span>  <br/> |<span data-ttu-id="35128-301">1</span><span class="sxs-lookup"><span data-stu-id="35128-301">1</span></span>  <br/> |<span data-ttu-id="35128-302">443</span><span class="sxs-lookup"><span data-stu-id="35128-302">443</span></span>  <br/> |<span data-ttu-id="35128-303">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-303">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="35128-304">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="35128-304">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="35128-305">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="35128-305">SRV (Service)</span></span>  <br/> |<span data-ttu-id="35128-306">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="35128-306">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="35128-307">100</span><span class="sxs-lookup"><span data-stu-id="35128-307">100</span></span>  <br/> |<span data-ttu-id="35128-308">1</span><span class="sxs-lookup"><span data-stu-id="35128-308">1</span></span>  <br/> |<span data-ttu-id="35128-309">5061</span><span class="sxs-lookup"><span data-stu-id="35128-309">5061</span></span>  <br/> |<span data-ttu-id="35128-310">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="35128-310">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="35128-311">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="35128-311">sipfed.online.lync.com.</span></span>  <br/> |
       
    ![OVH-SRV-Eintrag](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. <span data-ttu-id="35128-313">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="35128-313">Select **Next**.</span></span>
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. <span data-ttu-id="35128-315">Wählen Sie **bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="35128-315">Select **Confirm**.</span></span>
    
9. <span data-ttu-id="35128-p119">Wiederholen Sie die vorherigen Schritte, um den anderen SRV-Eintrag zu erstellen. Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="35128-p119">Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="35128-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="35128-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
