---
title: Ändern von Namenservern zum Einrichten von Microsoft mit Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Erfahren Sie, wie Sie Microsoft zum Verwalten der DNS-Einträge Ihrer benutzerdefinierten Domäne bei Hostgator einrichten können.
ms.openlocfilehash: 09f0409ed2a5f81b450c9aae7bb3699373ce6f22
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629887"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="b8ed4-103">Ändern von Namenservern zum Einrichten von Microsoft 365 mit Hostgator</span><span class="sxs-lookup"><span data-stu-id="b8ed4-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="b8ed4-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="b8ed4-105">Befolgen Sie diese Anweisungen, wenn Microsoft Ihre DNS-Einträge für Sie verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="b8ed4-106">(Wenn es Ihnen lieber ist, können Sie [alle Ihre Microsoft-DNS-Einträge bei Hostgator verwalten](create-dns-records-at-hostgator.md).)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="b8ed4-107">Verweisen Sie Ihre Domäne auf Ihr Hostingkonto.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8ed4-108">Sie müssen dieses Verfahren ausführen, bevor Sie das Verfahren im folgenden Abschnitt, **Hinzufügen eines TXT-Eintrags zur Überprüfung** durchführen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="b8ed4-109">Führen Sie die folgenden Schritte aus, um Ihre Domäne und Hostingkonten zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="b8ed4-p102">Im ersten Schritt navigieren Sie über [diesen Link](https://portal.hostgator.com/domain/manage) zur Kundenportalseite bei Hostgator. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="b8ed4-113">Wählen Sie die Registerkarte **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-113">Select the **Domains** tab.</span></span>
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="b8ed4-115">Wählen Sie auf der Seite " **Domänen verwalten** " im Bereich " **Meine Domänen** " die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="b8ed4-117">Wählen Sie auf der Seite **Domänenübersicht** im Bereich **Name Servers** die Option **Change**aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="b8ed4-119">Wählen Sie auf der Seite **Namensserver** für Ihre Domäne in der Dropdownliste **Host Konto auswählen** das **Hostingkonto** aus, das Ihrer Domäne zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="b8ed4-121">Wählen Sie **Namenserver speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b8ed4-123">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="b8ed4-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8ed4-124">Bevor Sie dieses Verfahren ausführen, müssen Sie zuerst das Verfahren im ersten Abschnitt dieses Artikels ausführen, indem Sie [Ihre Domäne auf Ihr Hostingkonto hinweisen.](#point-your-domain-to-your-hosting-account).</span><span class="sxs-lookup"><span data-stu-id="b8ed4-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="b8ed4-125">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-125">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b8ed4-126">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-126">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8ed4-p104">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="b8ed4-p105">Um zu beginnen, wechseln Sie zu Ihrer cPanel-Seite bei Hostgator. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="b8ed4-p106">(Jedem gehosteten Konto bei Hostgator ist eine eindeutige cPanel-Adresse zugewiesen. Ihre cPanel-Adresse sollte wie folgt aussehen: https://YourSiteAddress:secure-port-number. Diese Adresse ist in der Anmelde-E-Mail, die Sie von Hostgator erhalten, angegeben.)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b8ed4-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="b8ed4-135">Um zu beginnen, können Sie entweder ein Hostingkonto von Hostgator erwerben oder [die Namenservereinträge (NS) Ihrer Domäne so ändern](#change-your-domains-nameserver-ns-records) , dass Sie auf Microsoft verweist.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="b8ed4-136">Wählen Sie auf der Seite **Systemsteuerung** im Bereich **Domänen** die Option **Erweiterter DNS-Zonen-Editor**aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="b8ed4-137">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="b8ed4-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="b8ed4-139">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8ed4-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-140">**Name**</span></span> <br/> |<span data-ttu-id="b8ed4-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-141">**TTL**</span></span> <br/> |<span data-ttu-id="b8ed4-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-142">**Type**</span></span> <br/> |<span data-ttu-id="b8ed4-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="b8ed4-p108">Verwenden Sie Ihren  *Domänennamen*  (z. B. "fourthcoffee.com").  </span><span class="sxs-lookup"><span data-stu-id="b8ed4-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="b8ed4-146">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="b8ed4-147">1</span><span class="sxs-lookup"><span data-stu-id="b8ed4-147">1</span></span>  <br/> |<span data-ttu-id="b8ed4-148">TXT</span><span class="sxs-lookup"><span data-stu-id="b8ed4-148">TXT</span></span>  <br/> |<span data-ttu-id="b8ed4-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b8ed4-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b8ed4-150">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-150">**Note:** This is an example.</span></span> <span data-ttu-id="b8ed4-151">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b8ed4-152">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="b8ed4-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="b8ed4-153">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="b8ed4-154">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b8ed4-155">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="b8ed4-156">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b8ed4-157">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b8ed4-158">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b8ed4-159">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b8ed4-160">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b8ed4-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b8ed4-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b8ed4-163">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b8ed4-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b8ed4-164">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="b8ed4-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b8ed4-165">Um die Einrichtung Ihrer Domäne bei Microsoft abzuschließen, ändern Sie die NS-Einträge Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf den primären und sekundären Namenserver von Microsoft verweist.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="b8ed4-166">Dadurch wird Microsoft so eingerichtet, dass die DNS-Einträge der Domäne für Sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="b8ed4-167">Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b8ed4-168">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft Name-Server verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="b8ed4-169">Beispielsweise werden alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain* . com), nach dem Ausführen dieser Änderung an Microsoft weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b8ed4-170">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="b8ed4-171">Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**und **NS4.BDM.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="b8ed4-p114">Im ersten Schritt navigieren Sie über [diesen Link](https://portal.hostgator.com/domain/manage) zur Kundenportalseite bei Hostgator. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="b8ed4-175">Wählen Sie die Registerkarte **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-175">Select the **Domains** tab.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="b8ed4-177">Wählen Sie auf der Seite " **Domänen verwalten** " im Bereich " **Meine Domänen** " die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="b8ed4-179">Wählen Sie auf der Seite **Domain Overview** im Bereich **Name Servers** die Option **Change**aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="b8ed4-181">Wählen Sie auf der Seite **Namensserver** für Ihre Domäne in der Dropdownliste **Host Konto auswählen** das **Hostingkonto** aus, das Ihrer Domäne zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="b8ed4-183">Wählen Sie " **meine Namenserver manuell festlegen**" aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="b8ed4-185">**Vorsicht**: Befolgen Sie diese Schritte nur, wenn Sie andere Namenserver als die vier richtigen Namenserver haben.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="b8ed4-186">(Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="b8ed4-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="b8ed4-187">Während Sie sich noch auf der Seite **Name Servers** für Ihre Domäne befinden, löschen Sie in der Liste der Nameserver jeden Nameserver in dieser Liste, indem Sie ihn auswählen und dann die **ENTF**-TASTE auf der Tastatur drücken.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="b8ed4-189">Während Sie sich noch in der Liste der Nameserver befinden, geben Sie die beiden ersten Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="b8ed4-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="b8ed4-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b8ed4-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b8ed4-192">**Name Server 2:**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="b8ed4-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b8ed4-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b8ed4-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="b8ed4-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b8ed4-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b8ed4-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="b8ed4-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="b8ed4-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b8ed4-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="b8ed4-199">Fügen Sie die anderen Namenserverwerte hinzu.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="b8ed4-200">Wählen Sie **(+)** hinzufügen aus, und geben Sie den Wert aus der nächsten Zeile der Tabelle in das Feld für den Datensatz ein, oder kopieren und fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="b8ed4-201">Wiederholen Sie diesen Vorgang, bis Sie alle vier Namenservereinträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="b8ed4-203">Wählen Sie **Namenserver speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="b8ed4-205">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b8ed4-206">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8ed4-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
