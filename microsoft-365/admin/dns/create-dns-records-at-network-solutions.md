---
title: Erstellen von DNS-Einträgen bei Netzwerklösungen für Microsoft
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Hier erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Netzwerklösungen für Microsoft einrichten.
ms.openlocfilehash: 25e85bf30527b49ada711af9ba5c418409acd24c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780337"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="57eec-103">Erstellen von DNS-Einträgen bei Netzwerklösungen für Microsoft</span><span class="sxs-lookup"><span data-stu-id="57eec-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="57eec-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="57eec-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="57eec-105">Wenn Network Solutions Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="57eec-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="57eec-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="57eec-106">These are the main records to add.</span></span> <span data-ttu-id="57eec-107">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="57eec-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span> 
  
- [<span data-ttu-id="57eec-108">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="57eec-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="57eec-109">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="57eec-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="57eec-110">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="57eec-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="57eec-111">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="57eec-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="57eec-112">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="57eec-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="57eec-113">Nachdem Sie diese Einträge bei Netzwerklösungen hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="57eec-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="57eec-p102">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57eec-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="57eec-117">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="57eec-117">Add a TXT record for verification</span></span>
<span data-ttu-id="57eec-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="57eec-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="57eec-p103">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="57eec-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57eec-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="57eec-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="57eec-123">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="57eec-123">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="57eec-124">Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="57eec-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="57eec-125">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57eec-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="57eec-126">Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="57eec-128">Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="57eec-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="57eec-130">Wählen Sie **DNS bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-130">Select **Edit DNS**.</span></span>
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="57eec-132">Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="57eec-133">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="57eec-133">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="57eec-135">Scrollen Sie nach unten zum Abschnitt **Text (TXT Records)** , und wählen Sie dann **TXT-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Bearbeiten von TXT-Einträgen auswählen](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="57eec-137">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57eec-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="57eec-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="57eec-138">**Host**</span></span>|<span data-ttu-id="57eec-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57eec-139">**TTL**</span></span>|<span data-ttu-id="57eec-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="57eec-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="57eec-141">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="57eec-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="57eec-142">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-142">3600</span></span>  <br/> |<span data-ttu-id="57eec-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="57eec-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="57eec-144">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="57eec-144">**Note:** This is an example.</span></span> <span data-ttu-id="57eec-145">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="57eec-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="57eec-146">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="57eec-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Eingeben oder Einfügen von Werten in die Felder für den neuen Datensatz](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="57eec-148">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-148">Select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="57eec-150">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-150">Select **Save Changes**.</span></span>
    
    ![Wählen Sie Save Changes aus.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="57eec-152">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="57eec-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="57eec-153">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="57eec-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="57eec-154">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="57eec-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="57eec-155">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="57eec-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="57eec-156">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="57eec-157">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="57eec-158">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="57eec-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57eec-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="57eec-162">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="57eec-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="57eec-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="57eec-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="57eec-164">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="57eec-164">Follow the steps below or [watch the video (start at 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="57eec-165">Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="57eec-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="57eec-166">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57eec-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="57eec-167">Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="57eec-169">Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="57eec-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="57eec-171">Wählen Sie **DNS bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-171">Select **Edit DNS**.</span></span>
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="57eec-173">Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="57eec-174">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="57eec-174">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="57eec-176">Führen Sie einen Bildlauf nach unten zum Abschnitt **Mail Server (MX Records)** durch, und wählen Sie dann **MX-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![Auswählen von "MX-Einträge bearbeiten"](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="57eec-178">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57eec-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="57eec-179">**Priority**</span><span class="sxs-lookup"><span data-stu-id="57eec-179">**Priority**</span></span>|<span data-ttu-id="57eec-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57eec-180">**TTL**</span></span>|<span data-ttu-id="57eec-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="57eec-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57eec-182">10  </span><span class="sxs-lookup"><span data-stu-id="57eec-182">10</span></span>  <br/> <span data-ttu-id="57eec-183">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="57eec-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="57eec-184">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-184">3600</span></span>  <br/> | <span data-ttu-id="57eec-185">*\<domain-key\>*. Mail.Protection.Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="57eec-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="57eec-186">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="57eec-187">**Hinweis:** Holen Sie sich Ihr *\<domain-key\>* Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="57eec-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="57eec-188">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="57eec-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Eingeben oder Einfügen von Werten in die Felder für den neuen Datensatz](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="57eec-190">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-190">Select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="57eec-192">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-192">Select **Save Changes**.</span></span>
    
    ![Wählen Sie Save Changes aus.](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="57eec-194">Wenn weitere MX-Einträge vorhanden sind, löschen Sie diese, indem Sie **Delete** für jeden Eintrag auswählen.</span><span class="sxs-lookup"><span data-stu-id="57eec-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="57eec-196">Wenn alle ausgewählt sind, wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-196">When they are all selected, select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="57eec-198">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-198">Select **Save Changes**.</span></span>
    
    ![Wählen Sie Save Changes aus.](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="57eec-200">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="57eec-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="57eec-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="57eec-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="57eec-202">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="57eec-202">Follow the steps below or [watch the video (start at 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="57eec-203">Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="57eec-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="57eec-204">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57eec-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="57eec-205">Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="57eec-207">Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="57eec-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="57eec-209">Wählen Sie **DNS bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-209">Select **Edit DNS**.</span></span>
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="57eec-211">Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="57eec-212">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="57eec-212">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="57eec-214">Führen Sie einen Bildlauf nach unten zum Abschnitt **Host Aliase (CNAME Records)** durch, und wählen Sie dann **CNAME-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![Wählen Sie unter Host Aliase die Option CNAME-Einträge bearbeiten aus.](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="57eec-216">Geben Sie in die Felder für die vier neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57eec-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="57eec-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="57eec-217">**Alias**</span></span>|<span data-ttu-id="57eec-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57eec-218">**TTL**</span></span>|<span data-ttu-id="57eec-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="57eec-219">**Refers to Host Name**</span></span>|<span data-ttu-id="57eec-220">**Other Host          (Aktivieren Sie das Optionsfeld **Other Host**.)**</span><span class="sxs-lookup"><span data-stu-id="57eec-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57eec-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="57eec-221">autodiscover</span></span>  <br/> |<span data-ttu-id="57eec-222">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-222">3600</span></span>  <br/> |<span data-ttu-id="57eec-223">(keine Einstellung)</span><span class="sxs-lookup"><span data-stu-id="57eec-223">(No setting)</span></span>  <br/> |<span data-ttu-id="57eec-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="57eec-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="57eec-225">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="57eec-226">sip</span><span class="sxs-lookup"><span data-stu-id="57eec-226">sip</span></span>  <br/> |<span data-ttu-id="57eec-227">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-227">3600</span></span>  <br/> |<span data-ttu-id="57eec-228">(keine Einstellung)</span><span class="sxs-lookup"><span data-stu-id="57eec-228">(No setting)</span></span>  <br/> |<span data-ttu-id="57eec-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="57eec-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="57eec-230">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="57eec-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="57eec-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="57eec-232">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-232">3600</span></span>  <br/> |<span data-ttu-id="57eec-233">(keine Einstellung)</span><span class="sxs-lookup"><span data-stu-id="57eec-233">(No setting)</span></span>  <br/> |<span data-ttu-id="57eec-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="57eec-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="57eec-235">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="57eec-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="57eec-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="57eec-237">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-237">3600</span></span>  <br/> |<span data-ttu-id="57eec-238">(keine Einstellung)</span><span class="sxs-lookup"><span data-stu-id="57eec-238">(No setting)</span></span>  <br/> |<span data-ttu-id="57eec-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="57eec-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="57eec-240">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="57eec-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="57eec-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="57eec-242">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-242">3600</span></span>  <br/> |<span data-ttu-id="57eec-243">(keine Einstellung)</span><span class="sxs-lookup"><span data-stu-id="57eec-243">(No setting)</span></span>  <br/> |<span data-ttu-id="57eec-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="57eec-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="57eec-245">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Eingeben oder Einfügen von Werten für die neuen Datensätze](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="57eec-247">Wenn Sie alle benötigten CNAME-Einträge hinzugefügt haben, wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="57eec-249">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-249">Select **Save Changes**.</span></span>
    
    ![Wählen Sie Save Changes aus.](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="57eec-251">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="57eec-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="57eec-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="57eec-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="57eec-253">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="57eec-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="57eec-254">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="57eec-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="57eec-255">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="57eec-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="57eec-256">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="57eec-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="57eec-257">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="57eec-257">Follow the steps below or [watch the video (start at 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="57eec-258">Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="57eec-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="57eec-259">Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57eec-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="57eec-260">Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="57eec-262">Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="57eec-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="57eec-264">Wählen Sie **DNS bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-264">Select **Edit DNS**.</span></span>
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="57eec-266">Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="57eec-267">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="57eec-267">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="57eec-269">Scrollen Sie nach unten zum Abschnitt **Text (TXT Records)** , und wählen Sie dann **TXT-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Auswählen von TXT-Einträgen unter Text bearbeiten](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="57eec-271">Geben Sie in den Feldern für den neuen Eintrag die folgenden Werte ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57eec-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="57eec-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="57eec-272">**Host**</span></span>|<span data-ttu-id="57eec-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57eec-273">**TTL**</span></span>|<span data-ttu-id="57eec-274">**Text**</span><span class="sxs-lookup"><span data-stu-id="57eec-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="57eec-275">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="57eec-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="57eec-276">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-276">3600</span></span>  <br/> |<span data-ttu-id="57eec-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="57eec-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="57eec-278">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="57eec-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Eingeben oder Einfügen von Werten für den neuen Datensatz](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="57eec-280">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-280">Select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="57eec-282">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-282">Select **Save Changes**.</span></span>
    
    ![Wählen Sie Save Changes aus.](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="57eec-284">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="57eec-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="57eec-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="57eec-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="57eec-286">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="57eec-286">Follow the steps below or [watch the video (start at 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="57eec-p113">Im ersten Schritt navigieren Sie über [diesen Link](https://www.networksolutions.com/manage-it) zu Ihrer Domänenseite bei Network Solutions. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57eec-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="57eec-289">Bevor Sie die Schaltfläche **Anmeldung** auswählen, wählen Sie zuerst **Verwalten von Domänennamen** in der Dropdownliste **Anmelden in:** aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Wählen Sie "Manage My Domain Names" aus, und melden Sie sich bei "Network Solutions" an.](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="57eec-291">Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="57eec-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Aktivieren Sie das Kontrollkästchen für Ihre Domäne.](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="57eec-293">Wählen Sie **DNS bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-293">Select **Edit DNS**.</span></span>
    
    ![Wählen Sie Edit DNS aus.](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="57eec-295">Wählen Sie **Erweiterte DNS-Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="57eec-296">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="57eec-296">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie Erweiterte DNS-Einträge verwalten aus.](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="57eec-298">Scrollen Sie zum Abschnitt **Service (SRV Records)** , und wählen Sie dann **SRV-Einträge bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![Wählen Sie "SRV-Einträge unter Dienst bearbeiten" aus.](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="57eec-300">Geben Sie in die Felder für die zwei neuen Einträge die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57eec-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="57eec-301">(Wählen Sie in den Dropdownlisten die Werte **Service** und **Protocol** aus.)</span><span class="sxs-lookup"><span data-stu-id="57eec-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="57eec-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="57eec-302">**Service**</span></span>|<span data-ttu-id="57eec-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="57eec-303">**Protocol**</span></span>|<span data-ttu-id="57eec-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57eec-304">**TTL**</span></span>|<span data-ttu-id="57eec-305">**Priority**</span><span class="sxs-lookup"><span data-stu-id="57eec-305">**Priority**</span></span>|<span data-ttu-id="57eec-306">**Weight**</span><span class="sxs-lookup"><span data-stu-id="57eec-306">**Weight**</span></span>|<span data-ttu-id="57eec-307">**Port**</span><span class="sxs-lookup"><span data-stu-id="57eec-307">**Port**</span></span>|<span data-ttu-id="57eec-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="57eec-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57eec-309">_sip</span><span class="sxs-lookup"><span data-stu-id="57eec-309">_sip</span></span>  <br/> |<span data-ttu-id="57eec-310">_tls</span><span class="sxs-lookup"><span data-stu-id="57eec-310">_tls</span></span>  <br/> |<span data-ttu-id="57eec-311">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-311">3600</span></span>  <br/> |<span data-ttu-id="57eec-312">100</span><span class="sxs-lookup"><span data-stu-id="57eec-312">100</span></span>  <br/> |<span data-ttu-id="57eec-313">1 </span><span class="sxs-lookup"><span data-stu-id="57eec-313">1</span></span>  <br/> |<span data-ttu-id="57eec-314">443</span><span class="sxs-lookup"><span data-stu-id="57eec-314">443</span></span>  <br/> |<span data-ttu-id="57eec-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="57eec-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="57eec-316">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="57eec-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="57eec-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="57eec-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="57eec-318">_tcp</span></span>  <br/> |<span data-ttu-id="57eec-319">3600</span><span class="sxs-lookup"><span data-stu-id="57eec-319">3600</span></span>  <br/> |<span data-ttu-id="57eec-320">100</span><span class="sxs-lookup"><span data-stu-id="57eec-320">100</span></span>  <br/> |<span data-ttu-id="57eec-321">1 </span><span class="sxs-lookup"><span data-stu-id="57eec-321">1</span></span>  <br/> |<span data-ttu-id="57eec-322">5061</span><span class="sxs-lookup"><span data-stu-id="57eec-322">5061</span></span>  <br/> |<span data-ttu-id="57eec-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="57eec-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="57eec-324">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="57eec-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Eingeben oder Einfügen von Werten für die neuen Datensätze](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="57eec-326">Wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-326">Select **Continue**.</span></span>
    
    ![Wählen Sie weiter aus.](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="57eec-328">Wählen Sie **Save Changes**aus.</span><span class="sxs-lookup"><span data-stu-id="57eec-328">Select **Save Changes**.</span></span>
    
    ![Wählen Sie Save Changes aus.](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="57eec-p114">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57eec-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
