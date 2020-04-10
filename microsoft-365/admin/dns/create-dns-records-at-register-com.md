---
title: Erstellen von DNS-Einträgen für Office 365 bei Register.com
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Register.com für Office 365 einrichten.
ms.openlocfilehash: d89e1843a7c914843c7e9d5c41582878e138473a
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211098"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="bd1ff-103">Erstellen von DNS-Einträgen für Office 365 bei Register.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="bd1ff-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="bd1ff-105">Wenn Register.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="bd1ff-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-106">These are the main records to add.</span></span> <span data-ttu-id="bd1ff-107">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="bd1ff-108">Hinzufügen eines TXT-Eintrags bei Register.com, um zu überprüfen, ob Sie der Besitzer der Domäne sind</span><span class="sxs-lookup"><span data-stu-id="bd1ff-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="bd1ff-109">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="bd1ff-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="bd1ff-110">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="bd1ff-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="bd1ff-111">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="bd1ff-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="bd1ff-112">Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="bd1ff-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="bd1ff-113">Nachdem Sie diese Einträge bei Register.com hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="bd1ff-114">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd1ff-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="bd1ff-118">Hinzufügen eines TXT-Eintrags bei Register.com, um zu überprüfen, ob Sie der Besitzer der Domäne sind</span><span class="sxs-lookup"><span data-stu-id="bd1ff-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="bd1ff-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="bd1ff-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="bd1ff-p103">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd1ff-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="bd1ff-124">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bd1ff-125">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="bd1ff-126">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="bd1ff-127">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="bd1ff-128">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="bd1ff-129">Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="bd1ff-130">Führen Sie einen Bildlauf nach unten zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **Edit TXT Records (SPF)** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="bd1ff-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="bd1ff-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="bd1ff-132">**Host Name**</span></span> <br/> |<span data-ttu-id="bd1ff-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="bd1ff-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="bd1ff-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="bd1ff-p106">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="bd1ff-138">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="bd1ff-139">Wählen Sie auf der nächsten Seite erneut **Continue** aus, um Ihre Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="bd1ff-140">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="bd1ff-141">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="bd1ff-142">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="bd1ff-143">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="bd1ff-144">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="bd1ff-145">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="bd1ff-146">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bd1ff-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="bd1ff-150">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="bd1ff-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="bd1ff-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="bd1ff-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="bd1ff-152">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bd1ff-153">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="bd1ff-154">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="bd1ff-155">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="bd1ff-156">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="bd1ff-157">Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="bd1ff-158">Führen Sie einen Bildlauf zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **e-Mail-Exchanger-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Wählen Sie Bearbeiten von e-Mail-Exchanger-Einträgen](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="bd1ff-160">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="bd1ff-161">(Wählen Sie in der Dropdownliste den Wert **Priority** aus.)</span><span class="sxs-lookup"><span data-stu-id="bd1ff-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bd1ff-162">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-163">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-164">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="bd1ff-165">Hoch</span><span class="sxs-lookup"><span data-stu-id="bd1ff-165">High</span></span>  <br/> <span data-ttu-id="bd1ff-166">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="bd1ff-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="bd1ff-167">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="bd1ff-168">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="bd1ff-169">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="bd1ff-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen des Werts aus der Tabelle](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="bd1ff-171">Wenn bereits andere MX-Einträge aufgeführt sind, wählen Sie jeden dieser Einträge zum Löschen aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="bd1ff-173">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-173">Select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="bd1ff-175">Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie weiter aus.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="bd1ff-177">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="bd1ff-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="bd1ff-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="bd1ff-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="bd1ff-179">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bd1ff-180">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="bd1ff-181">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="bd1ff-182">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="bd1ff-183">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="bd1ff-184">Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="bd1ff-185">Scrollen Sie zum Abschnitt **Erweiterte technische Einstellungen** , und wählen Sie dann **Bearbeiten von Domänen Alias Einträgen**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Auswählen von Datensätzen zum Bearbeiten von Domänen Aliasen](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="bd1ff-187">Wählen Sie **Weitere Domänenaliase hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-187">Select **Add more domain aliases**.</span></span>
    
    ![Wählen Sie weitere Domänenaliase hinzufügen aus.](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="bd1ff-189">Fügen Sie die erforderlichen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="bd1ff-190">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="bd1ff-191">\*\*\*\*Erstes Feld (ohne Beschriftung)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-192">\*\*\*\*Points to\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="bd1ff-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="bd1ff-193">autodiscover</span></span>  <br/> |<span data-ttu-id="bd1ff-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="bd1ff-195">sip</span><span class="sxs-lookup"><span data-stu-id="bd1ff-195">sip</span></span>  <br/> |<span data-ttu-id="bd1ff-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="bd1ff-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="bd1ff-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="bd1ff-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="bd1ff-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="bd1ff-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="bd1ff-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="bd1ff-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="bd1ff-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="bd1ff-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="bd1ff-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Kopieren und Einfügen der DNS-Werte aus der Tabelle](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="bd1ff-204">Wenn Sie alle benötigten CNAME-Einträge hinzugefügt haben, wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="bd1ff-206">Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie weiter aus.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="bd1ff-208">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="bd1ff-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="bd1ff-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="bd1ff-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd1ff-210">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="bd1ff-211">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="bd1ff-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="bd1ff-213">Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="bd1ff-214">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bd1ff-215">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="bd1ff-216">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="bd1ff-217">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="bd1ff-218">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="bd1ff-219">Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="bd1ff-220">Führen Sie einen Bildlauf zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **TXT-Datensätze bearbeiten (SPF)** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Bearbeiten von TXT-Einträgen auswählen (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="bd1ff-222">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="bd1ff-223">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-224">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="bd1ff-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="bd1ff-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="bd1ff-226">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="bd1ff-228">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-228">Select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="bd1ff-230">Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie weiter aus.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="bd1ff-232">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="bd1ff-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="bd1ff-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="bd1ff-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="bd1ff-234">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="bd1ff-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="bd1ff-237">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="bd1ff-238">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="bd1ff-239">Suchen Sie nach der Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. Wählen Sie dann in dieser Zeile **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="bd1ff-240">Führen Sie einen Bildlauf zum Abschnitt **Erweiterte technische Einstellungen** durch, und wählen Sie dann **SRV-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Auswählen der Option zum Bearbeiten von SRV-Einträgen](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="bd1ff-242">Fügen Sie den ersten der zwei SRV-Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="bd1ff-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="bd1ff-243">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="bd1ff-244">(Wählen Sie in der Dropdownliste den Wert **Priority** aus.)</span><span class="sxs-lookup"><span data-stu-id="bd1ff-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="bd1ff-245">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-247">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-248">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-249">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-250">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="bd1ff-251">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd1ff-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="bd1ff-252">_sip</span><span class="sxs-lookup"><span data-stu-id="bd1ff-252">_sip</span></span>  <br/> |<span data-ttu-id="bd1ff-253">_tls</span><span class="sxs-lookup"><span data-stu-id="bd1ff-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="bd1ff-254">High</span><span class="sxs-lookup"><span data-stu-id="bd1ff-254">High</span></span>  <br/> |<span data-ttu-id="bd1ff-255">1</span><span class="sxs-lookup"><span data-stu-id="bd1ff-255">1</span></span>  <br/> |<span data-ttu-id="bd1ff-256">443</span><span class="sxs-lookup"><span data-stu-id="bd1ff-256">443</span></span>  <br/> |<span data-ttu-id="bd1ff-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="bd1ff-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bd1ff-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="bd1ff-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="bd1ff-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="bd1ff-260">High</span><span class="sxs-lookup"><span data-stu-id="bd1ff-260">High</span></span>  <br/> |<span data-ttu-id="bd1ff-261">1</span><span class="sxs-lookup"><span data-stu-id="bd1ff-261">1</span></span>  <br/> |<span data-ttu-id="bd1ff-262">5061</span><span class="sxs-lookup"><span data-stu-id="bd1ff-262">5061</span></span>  <br/> |<span data-ttu-id="bd1ff-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bd1ff-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Kopieren Sie die Werte aus der Tabelle, und fügen Sie Sie ein.](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="bd1ff-265">Wählen Sie **Weitere SRV-Einträge hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-265">Select **Add more SRV records**.</span></span>
    
    ![Wählen Sie weitere SRV-Einträge hinzufügen aus.](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="bd1ff-267">Fügen Sie den zweiten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="bd1ff-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="bd1ff-268">Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="bd1ff-269">Wenn Sie beide SRV-Einträge hinzugefügt haben, wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="bd1ff-271">Wählen Sie auf der nächsten Seite erneut **Continue** aus, um die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bd1ff-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie weiter aus.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="bd1ff-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="bd1ff-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
