---
title: Erstellen von DNS-Einträgen Register.com Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mails, Skype for Business Online und andere Dienste unter Register.com Microsoft einrichten.
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910054"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="83041-103">Erstellen von DNS-Einträgen Register.com Microsoft</span><span class="sxs-lookup"><span data-stu-id="83041-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="83041-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="83041-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="83041-105">Wenn Register.com Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="83041-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="83041-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="83041-106">These are the main records to add.</span></span> <span data-ttu-id="83041-107">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="83041-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="83041-108">Hinzufügen eines TXT-Eintrags bei Register.com, um zu überprüfen, ob Sie der Besitzer der Domäne sind</span><span class="sxs-lookup"><span data-stu-id="83041-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="83041-109">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Microsoft geleitet werden</span><span class="sxs-lookup"><span data-stu-id="83041-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="83041-110">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="83041-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="83041-111">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="83041-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="83041-112">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="83041-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="83041-113">Nachdem Sie diese Datensätze unter Register.com hinzugefügt haben, wird Ihre Domäne für die Arbeit mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="83041-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="83041-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="83041-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="83041-117">Hinzufügen eines TXT-Eintrags bei Register.com, um zu überprüfen, ob Sie der Besitzer der Domäne sind</span><span class="sxs-lookup"><span data-stu-id="83041-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="83041-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="83041-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="83041-p103">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="83041-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83041-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="83041-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="83041-123">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="83041-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="83041-p105">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83041-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="83041-126">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="83041-127">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="83041-128">Suchen Sie die Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. und wählen Sie dann in dieser Zeile **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="83041-129">Scrollen Sie nach unten zum **Abschnitt Erweiterte technische** Einstellungen, und wählen Sie dann Edit TXT Records **(SPF) aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="83041-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="83041-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="83041-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="83041-131">**Host Name**</span></span> <br/> |<span data-ttu-id="83041-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="83041-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="83041-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="83041-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="83041-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="83041-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
7. <span data-ttu-id="83041-137">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="83041-138">Wählen Sie auf der nächsten Seite **Erneut** fortfahren aus, um die Änderungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="83041-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="83041-139">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="83041-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="83041-140">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="83041-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="83041-141">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="83041-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="83041-142">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="83041-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="83041-143">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="83041-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="83041-144">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="83041-145">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83041-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="83041-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="83041-149">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="83041-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="83041-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="83041-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="83041-151">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="83041-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="83041-p108">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83041-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="83041-154">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="83041-155">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="83041-156">Suchen Sie die Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. und wählen Sie dann in dieser Zeile **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="83041-157">Scrollen Sie zum **Abschnitt Erweiterte technische Einstellungen,** und wählen Sie **dann E-Mail-Exchanger-Datensätze bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Auswählen von E-Mail-Exchanger-Datensätzen bearbeiten](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="83041-159">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83041-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="83041-160">(Wählen Sie den **Prioritätswert** aus der Dropdownliste aus.)</span><span class="sxs-lookup"><span data-stu-id="83041-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="83041-161">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="83041-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="83041-163">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="83041-164">High</span><span class="sxs-lookup"><span data-stu-id="83041-164">High</span></span>  <br/> <span data-ttu-id="83041-165">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="83041-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="83041-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="83041-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="83041-167">**Hinweis:** Erhalten Sie Ihren \<*domain-key*\> über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="83041-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="83041-168">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="83041-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopieren und Einfügen des Werts aus der Tabelle](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="83041-170">Wenn bereits andere MX-Einträge aufgeführt sind, wählen Sie jeden dieser Einträge zum Löschen aus.</span><span class="sxs-lookup"><span data-stu-id="83041-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="83041-172">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-172">Select **Continue**.</span></span>
    
    ![Wählen Sie Weiter aus.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="83041-174">Wählen Sie auf der nächsten Seite **Erneut** fortfahren aus, um Die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="83041-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie Weiter aus.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="83041-176">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="83041-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="83041-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="83041-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="83041-178">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="83041-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="83041-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83041-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="83041-181">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="83041-182">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="83041-183">Suchen Sie die Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. und wählen Sie dann in dieser Zeile **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="83041-184">Scrollen Sie zum **Abschnitt Erweiterte technische Einstellungen,** und wählen Sie **dann Domänenaliasendatensätze bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Wählen Sie Domänenaliasendatensätze bearbeiten aus.](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="83041-186">Wählen **Sie Weitere Domänenaliasen hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-186">Select **Add more domain aliases**.</span></span>
    
    ![Wählen Sie Weitere Domänenaliasen hinzufügen aus.](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="83041-188">Fügen Sie die erforderlichen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="83041-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="83041-189">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83041-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="83041-190">\*\*\*\*Erstes Feld (ohne Beschriftung)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="83041-191">\*\*\*\*Points to\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="83041-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="83041-192">autodiscover</span></span>  <br/> |<span data-ttu-id="83041-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="83041-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="83041-194">sip</span><span class="sxs-lookup"><span data-stu-id="83041-194">sip</span></span>  <br/> |<span data-ttu-id="83041-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="83041-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="83041-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="83041-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="83041-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="83041-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="83041-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="83041-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="83041-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="83041-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="83041-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="83041-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="83041-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="83041-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Kopieren und Einfügen der DNS-Werte aus der Tabelle](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="83041-203">Wenn Sie alle benötigten #A0 hinzugefügt haben, wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Wählen Sie Weiter aus.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="83041-205">Wählen Sie auf der nächsten Seite **Erneut** fortfahren aus, um Die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="83041-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie Weiter aus.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="83041-207">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="83041-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="83041-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="83041-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="83041-209">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="83041-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="83041-210">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="83041-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="83041-211">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="83041-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="83041-212">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="83041-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="83041-213">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="83041-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="83041-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83041-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="83041-216">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="83041-217">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="83041-218">Suchen Sie die Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. und wählen Sie dann in dieser Zeile **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="83041-219">Scrollen Sie zum **Abschnitt Erweiterte technische Einstellungen,** und wählen Sie **dann Edit TXT Records (SPF) aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Select Edit TXT Records (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="83041-221">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83041-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="83041-222">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="83041-223">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="83041-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="83041-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="83041-225">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="83041-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Kopieren und Einfügen der Werte aus der Tabelle](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="83041-227">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-227">Select **Continue**.</span></span>
    
    ![Wählen Sie Weiter aus.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="83041-229">Wählen Sie auf der nächsten Seite **Erneut** fortfahren aus, um Die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="83041-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie Weiter aus.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="83041-231">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="83041-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="83041-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="83041-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="83041-233">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="83041-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="83041-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://www.register.com/myaccount/) zu Ihrer Domänenseite bei Register.com. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="83041-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="83041-236">Wählen Sie **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="83041-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="83041-237">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="83041-238">Suchen Sie die Zeile, die den Namen der Domäne enthält, die Sie ändern möchten. und wählen Sie dann in dieser Zeile **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="83041-239">Scrollen Sie zum **Abschnitt Erweiterte technische Einstellungen,** und wählen Sie **dann SRV-Einträge bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Auswählen von Bearbeiten von SRV-Datensätzen](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="83041-241">Fügen Sie den ersten der zwei SRV-Einträge hinzu:</span><span class="sxs-lookup"><span data-stu-id="83041-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="83041-242">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83041-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="83041-243">(Wählen Sie den **Prioritätswert** aus der Dropdownliste aus.)</span><span class="sxs-lookup"><span data-stu-id="83041-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="83041-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="83041-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="83041-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="83041-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="83041-248">\*\*\*\*Weight\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="83041-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="83041-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83041-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="83041-251">_sip</span><span class="sxs-lookup"><span data-stu-id="83041-251">_sip</span></span>  <br/> |<span data-ttu-id="83041-252">_tls</span><span class="sxs-lookup"><span data-stu-id="83041-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="83041-253">High</span><span class="sxs-lookup"><span data-stu-id="83041-253">High</span></span>  <br/> |<span data-ttu-id="83041-254">1</span><span class="sxs-lookup"><span data-stu-id="83041-254">1</span></span>  <br/> |<span data-ttu-id="83041-255">443</span><span class="sxs-lookup"><span data-stu-id="83041-255">443</span></span>  <br/> |<span data-ttu-id="83041-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="83041-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="83041-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="83041-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="83041-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="83041-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="83041-259">High</span><span class="sxs-lookup"><span data-stu-id="83041-259">High</span></span>  <br/> |<span data-ttu-id="83041-260">1</span><span class="sxs-lookup"><span data-stu-id="83041-260">1</span></span>  <br/> |<span data-ttu-id="83041-261">5061</span><span class="sxs-lookup"><span data-stu-id="83041-261">5061</span></span>  <br/> |<span data-ttu-id="83041-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="83041-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Kopieren und Einfügen der Werte aus der Tabelle](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="83041-264">Wählen **Sie Weitere SRV-Einträge hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-264">Select **Add more SRV records**.</span></span>
    
    ![Wählen Sie Weitere SRV-Einträge hinzufügen aus.](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="83041-266">Fügen Sie den zweiten SRV-Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="83041-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="83041-267">Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="83041-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="83041-268">Wenn Sie beide SRV-Einträge hinzugefügt haben, wählen Sie **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="83041-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Wählen Sie Weiter aus.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="83041-270">Wählen Sie auf der nächsten Seite **Erneut** fortfahren aus, um Die Änderungen zu bestätigen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="83041-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Wählen Sie Weiter aus.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="83041-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="83041-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
