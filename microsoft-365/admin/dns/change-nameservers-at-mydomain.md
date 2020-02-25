---
title: Ändern von Namenservern zum Einrichten von Office 365 bei MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Erfahren Sie, wie Sie Office 365 einrichten können, um die DNS-Einträge Ihrer benutzerdefinierten Domäne bei mydomain zu verwalten.
ms.openlocfilehash: 05681fb48cc4c06aa44421029739a71ef6e59871
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242685"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="c676f-103">Ändern von Namenservern zum Einrichten von Office 365 bei MyDomain</span><span class="sxs-lookup"><span data-stu-id="c676f-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="c676f-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="c676f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="c676f-p101">Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge automatisch verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei MyDomain selbst verwalten](create-dns-records-at-mydomain.md).)</span><span class="sxs-lookup"><span data-stu-id="c676f-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c676f-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="c676f-107">Add a TXT record for verification</span></span>

<span data-ttu-id="c676f-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="c676f-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c676f-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="c676f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c676f-p104">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c676f-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c676f-114">Wählen Sie im Abschnitt **Meine Favoriten** die Option **Domäne zentral**aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="c676f-115">Wählen Sie unter **Domäne**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="c676f-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="c676f-116">Wählen Sie in der Zeile **Übersicht** die Option **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="c676f-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="c676f-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="c676f-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span><span class="sxs-lookup"><span data-stu-id="c676f-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="c676f-119">**Content**</span><span class="sxs-lookup"><span data-stu-id="c676f-119">**Content**</span></span> <br/> |
|<span data-ttu-id="c676f-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c676f-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c676f-121">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c676f-121">**Note**: This is an example.</span></span> <span data-ttu-id="c676f-122">Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c676f-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="c676f-123">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="c676f-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="c676f-124">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c676f-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="c676f-125">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c676f-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c676f-126">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c676f-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c676f-127">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="c676f-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c676f-128">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="c676f-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c676f-129">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c676f-130">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c676f-131">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c676f-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c676f-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c676f-135">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="c676f-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="c676f-p107">Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="c676f-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c676f-139">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Office 365 Namenserver verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c676f-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="c676f-140">Beispielsweise alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="c676f-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="c676f-141">com) wird in Office 365 gestartet, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="c676f-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c676f-p109">Im folgenden Verfahren wird gezeigt, wie Sie andere, unerwünschte Namenserver aus der Liste löschen können, und Sie erfahren, wie Sie die richtigen Namenserver hinzufügen, wenn sie sich nicht bereits in der Liste befinden.</span><span class="sxs-lookup"><span data-stu-id="c676f-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="c676f-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="c676f-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="c676f-144">Im ersten Schritt navigieren Sie über [diesen Link](https://www.mydomain.com/controlpanel) zu Ihrer Domänenseite bei MyDomain.</span><span class="sxs-lookup"><span data-stu-id="c676f-144">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="c676f-145">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c676f-145">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c676f-146">Wählen Sie im Abschnitt **Meine Favoriten** die Option **Domäne zentral**aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="c676f-147">Wählen Sie unter **Domäne**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="c676f-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="c676f-148">Wählen Sie in der Zeile **Übersicht** die Option Namen **Server**aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Mydomain-BP-redelegate-1-1](../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="c676f-150">Wählen Sie im Abschnitt **Update Name Servers** die Option **Use different name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="c676f-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Mydomain-BP-redelegate-1-2-1](../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="c676f-152">Je nachdem, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, fahren Sie mit einem der beiden folgenden Verfahren fort.</span><span class="sxs-lookup"><span data-stu-id="c676f-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="c676f-153">Wenn die richtigen Namenserver bereits aufgelistet SIND</span><span class="sxs-lookup"><span data-stu-id="c676f-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="c676f-154">Wenn die richtigen Namenserver bereits aufgelistet sind, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="c676f-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Mydomain-BP-redelegate-1-2-2](../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="c676f-156">Wenn die richtigen Namenserver noch NICHT aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="c676f-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="c676f-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="c676f-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="c676f-158">(Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="c676f-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="c676f-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="c676f-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Mydomain-BP-redelegate-1-3-1](../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="c676f-161">Wählen Sie zweimal **Hinzufügen** aus, um zwei neue Nameserver-Zeilen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c676f-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Mydomain-BP-redelegate-1-3-2](../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="c676f-163">Geben Sie in die Felder für die Einträge die Namenserverwerte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="c676f-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="c676f-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="c676f-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="c676f-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c676f-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c676f-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="c676f-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="c676f-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c676f-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c676f-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="c676f-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="c676f-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c676f-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c676f-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="c676f-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="c676f-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c676f-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Mydomain-BP-redelegate-1-4](../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="c676f-173">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c676f-173">Select **Save**.</span></span>
    
    ![Mydomain-BP-redelegate-1-5](../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="c676f-p112">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="c676f-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
