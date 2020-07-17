---
title: Ändern von Namenservern zum Einrichten von Microsoft mit 1&1 Ionos
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Erfahren Sie, wie Sie Office 365, die von 21Vianet betrieben werden, zum Verwalten Ihrer DNS-Einträge einrichten können, wenn 1&1 Internet der DNS-Hostanbieter ist.
ms.openlocfilehash: 79870d534e7d825fd59dbbbec54c796227f5faf1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780373"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="a2d43-103">Ändern von Namenservern zum Einrichten von Microsoft 365 mit 1&1 Ionos</span><span class="sxs-lookup"><span data-stu-id="a2d43-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="a2d43-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="a2d43-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a2d43-105">Befolgen Sie diese Anweisungen, wenn Microsoft 365 Ihre Microsoft 365-DNS-Einträge für Sie verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="a2d43-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="a2d43-106">(Wenn es Ihnen lieber ist, können Sie [alle Ihre Microsoft 365-DNS-Einträge mit 1&1 Ionos verwalten](create-dns-records-at-1-1-internet.md).)</span><span class="sxs-lookup"><span data-stu-id="a2d43-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a2d43-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="a2d43-107">Add a TXT record for verification</span></span>


<span data-ttu-id="a2d43-p102">Bevor Sie Ihre Domäne in Microsoft 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="a2d43-p102">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2d43-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="a2d43-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a2d43-112">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="a2d43-112">Follow the steps below or [watch the video (start at 0:42)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
1. <span data-ttu-id="a2d43-113">Um zu beginnen, wechseln Sie über [diesen Link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)zu ihrer Domänen Seite bei 1&1 Ionos.</span><span class="sxs-lookup"><span data-stu-id="a2d43-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="a2d43-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a2d43-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="a2d43-115">Wählen Sie unter **Meine Domänen**die Option **Domänen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="a2d43-116">Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten. Wählen Sie dann das **Panel** -Steuerelement ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="a2d43-117">Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="a2d43-118">Wählen Sie im Abschnitt **txt-und SRV-Einträge** die Option **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="a2d43-119">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a2d43-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="a2d43-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="a2d43-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a2d43-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="a2d43-121">**Type**</span></span> <br/> |<span data-ttu-id="a2d43-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="a2d43-122">**Prefix**</span></span> <br/> |<span data-ttu-id="a2d43-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="a2d43-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="a2d43-124">TXT</span><span class="sxs-lookup"><span data-stu-id="a2d43-124">TXT</span></span>  <br/> |<span data-ttu-id="a2d43-125">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="a2d43-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a2d43-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a2d43-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="a2d43-127">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a2d43-127">**Note**: This is an example.</span></span> <span data-ttu-id="a2d43-128">Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2d43-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="a2d43-129">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="a2d43-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="a2d43-130">Wählen Sie **Speichern**und dann erneut **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="a2d43-131">Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="a2d43-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a2d43-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a2d43-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a2d43-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="a2d43-134">Wenn Microsoft 365 den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="a2d43-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a2d43-135">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="a2d43-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="a2d43-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="a2d43-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="a2d43-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a2d43-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="a2d43-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="a2d43-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a2d43-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="a2d43-141">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie weitere Informationen unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domänen-oder DNS-Einträge in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a2d43-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a2d43-142">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="a2d43-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="a2d43-143">Um die Einrichtung Ihrer Domäne mit Microsoft 365 abzuschließen, ändern Sie die NS-Einträge Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf den primären und sekundären Namenserver von Microsoft 365 verweist.</span><span class="sxs-lookup"><span data-stu-id="a2d43-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="a2d43-144">Dadurch wird Microsoft 365 zum Aktualisieren der DNS-Einträge der Domäne für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a2d43-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="a2d43-145">Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="a2d43-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a2d43-146">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft 365-Namenserver verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a2d43-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="a2d43-147">Beispielsweise werden alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain* . com), nach dem vornehmen dieser Änderung zu Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2d43-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="a2d43-148">Möchten Sie Ihre NS-Einträge so ändern, dass Microsoft 365 Ihre Domäne einrichten kann?</span><span class="sxs-lookup"><span data-stu-id="a2d43-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="a2d43-149">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span><span class="sxs-lookup"><span data-stu-id="a2d43-149">Follow the steps below or [watch the video (start at 2:47)](https://support.microsoft.com/office/0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a2d43-150">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="a2d43-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="a2d43-151">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="a2d43-152">Um zu beginnen, navigieren Sie über [diesen Link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)zu ihrer Domänen Seite bei 1&1 Ionos.</span><span class="sxs-lookup"><span data-stu-id="a2d43-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="a2d43-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="a2d43-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="a2d43-154">Wählen Sie unter **Meine Domänen**die Option **Domänen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="a2d43-155">Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="a2d43-156">Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="a2d43-157">Wählen Sie im Abschnitt **Name Server Settings** die Option **Other name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="a2d43-158">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="a2d43-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="a2d43-159">Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:</span><span class="sxs-lookup"><span data-stu-id="a2d43-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="a2d43-160">Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="a2d43-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="a2d43-161">Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="a2d43-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="a2d43-162">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="a2d43-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="a2d43-163">Geben Sie im Feld **Name server 1** den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a2d43-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a2d43-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="a2d43-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="a2d43-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Eingeben eines Werts in das Feld Name Server 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="a2d43-167">Wählen Sie in der Dropdownliste **Additional name servers** den Eintrag **My secondary name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="a2d43-169">Geben Sie in den Feldern **Name server 2, 3 und 4** den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a2d43-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a2d43-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="a2d43-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="a2d43-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a2d43-172">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="a2d43-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="a2d43-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a2d43-174">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="a2d43-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="a2d43-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
![Eingeben von Namenserver Werten](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="a2d43-177">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a2d43-177">Select **Save**.</span></span>
    
    ![Auswählen von "Speichern" auf der Seite "Name Server-Einstellungen"](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="a2d43-179">Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-179">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Auswählen von "Speichern" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="a2d43-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a2d43-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a2d43-182">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a2d43-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="a2d43-183">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="a2d43-183">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="a2d43-p113">Folgen Sie diesen Schritten  *nur*  , wenn es andere Namenserver als die vier  *korrekten*  Namenserver gibt. (Das heißt, löschen Sie  *nur*  andere als die vier korrekten Namenserver, also  *nicht* **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** oder **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="a2d43-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="a2d43-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="a2d43-186">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="a2d43-188">Geben Sie in den Feldern **Nameserver 1, 2, 3 und 4** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="a2d43-188">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a2d43-189">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="a2d43-189">**Name server 1**</span></span> <br/> |<span data-ttu-id="a2d43-190">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-190">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a2d43-191">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="a2d43-191">**Name server 2**</span></span> <br/> |<span data-ttu-id="a2d43-192">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-192">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a2d43-193">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="a2d43-193">**Name server 3**</span></span> <br/> |<span data-ttu-id="a2d43-194">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-194">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a2d43-195">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="a2d43-195">**Name server 4**</span></span> <br/> |<span data-ttu-id="a2d43-196">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a2d43-196">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Eingeben von Namenserver Werten](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="a2d43-198">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a2d43-198">Select **Save**.</span></span>
    
    ![Auswählen von "Speichern" auf der Seite "Name Server-Einstellungen"](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="a2d43-200">Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="a2d43-200">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Auswählen von "Speichern" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="a2d43-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a2d43-202">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a2d43-203">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a2d43-203">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


