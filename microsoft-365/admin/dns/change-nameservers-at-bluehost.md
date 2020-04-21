---
title: Ändern von Namenservern zum Einrichten von Microsoft mit Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Erfahren Sie, wie Sie Microsoft zum Verwalten Ihrer DNS-Einträge bei Bluehost einrichten können. '
ms.openlocfilehash: 63084b35c3f0d71764bca1995f25d7c6f0842a86
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629911"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="6b1e3-103">Ändern von Namenservern zum Einrichten von Microsoft mit Bluehost</span><span class="sxs-lookup"><span data-stu-id="6b1e3-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="6b1e3-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6b1e3-105">Befolgen Sie diese Anweisungen, wenn Microsoft Ihre DNS-Einträge für Sie verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="6b1e3-106">(Wenn es Ihnen lieber ist, können Sie [alle Ihre DNS-Einträge bei Bluehost verwalten](create-dns-records-at-bluehost.md).)</span><span class="sxs-lookup"><span data-stu-id="6b1e3-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6b1e3-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="6b1e3-107">Add a TXT record for verification</span></span>

<span data-ttu-id="6b1e3-108">Bevor Sie Ihre Domäne mit Microsoft verwenden, müssen wir sicherstellen, dass Sie Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6b1e3-109">Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, beweist Microsoft, dass Sie die Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b1e3-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6b1e3-112">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="6b1e3-113">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6b1e3-114">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="6b1e3-115">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="6b1e3-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="6b1e3-116">Wählen Sie im Bereich **domain_name** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="6b1e3-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="6b1e3-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6b1e3-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b1e3-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-119">**Host Record**</span></span> <br/> |<span data-ttu-id="6b1e3-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-120">**TTL**</span></span> <br/> |<span data-ttu-id="6b1e3-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-121">**Type**</span></span> <br/> |<span data-ttu-id="6b1e3-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="6b1e3-123">14400</span><span class="sxs-lookup"><span data-stu-id="6b1e3-123">14400</span></span>  <br/> |<span data-ttu-id="6b1e3-124">TXT</span><span class="sxs-lookup"><span data-stu-id="6b1e3-124">TXT</span></span>  <br/> |<span data-ttu-id="6b1e3-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6b1e3-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="6b1e3-126">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-126">**Note:** This is an example.</span></span> <span data-ttu-id="6b1e3-127">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="6b1e3-128">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="6b1e3-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="6b1e3-129">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="6b1e3-130">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6b1e3-131">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="6b1e3-132">Wenn Microsoft den richtigen TXT-Eintrag findet, wird Ihre Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6b1e3-133">Wechseln Sie im Microsoft Admin Center zur Seite mit den **Einstellungs** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="6b1e3-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6b1e3-134">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6b1e3-135">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6b1e3-136">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6b1e3-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6b1e3-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6b1e3-139">Wenn Sie Probleme mit dem Nachrichtenfluss oder anderen Problemen haben, nachdem Sie DNS-Einträge hinzugefügt haben, finden Sie unter [Suchen und Beheben von Problemen nach dem Hinzufügen Ihrer Domäne oder DNS-Einträge](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6b1e3-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6b1e3-140">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="6b1e3-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="6b1e3-141">Um die Einrichtung Ihrer Domäne bei Microsoft abzuschließen, ändern Sie die NS-Einträge Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf den primären und sekundären Namenserver verweist.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="6b1e3-142">Dadurch wird Microsoft so eingerichtet, dass die DNS-Einträge der Domäne für Sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="6b1e3-143">Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6b1e3-144">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft Name-Server verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="6b1e3-145">Beispielsweise werden alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain* . com), nach dem Ausführen dieser Änderung an Microsoft weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="6b1e3-146">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="6b1e3-147">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="6b1e3-148">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="6b1e3-149">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="6b1e3-150">Aktivieren Sie auf der Seite **Domänen** im Bereich **domain_name** das Kontrollkästchen für Ihre Domäne, und wählen Sie dann **Name Servers**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="6b1e3-152">Wählen Sie im Bereich **domain_name** die Option **benutzerdefinierte Namenserver verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="6b1e3-154">Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:</span><span class="sxs-lookup"><span data-stu-id="6b1e3-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="6b1e3-155">Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="6b1e3-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="6b1e3-156">Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="6b1e3-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="6b1e3-157">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="6b1e3-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="6b1e3-158">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der folgenden Tabelle direkt oder über Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6b1e3-159">**Erste leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-159">**First empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6b1e3-161">**Zweite leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="6b1e3-164">Wählen Sie **Zeile hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="6b1e3-166">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der ersten Zeile der folgenden Tabelle in die neue leere Zeile ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6b1e3-167">**Dritte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6b1e3-169">**Vierte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="6b1e3-171">Wenn Sie den vierten Namenservereintrag hinzufügen möchten, wählen Sie erneut **Zeile hinzufügen** aus, und erstellen Sie einen Datensatz mit den Werten aus der letzten Zeile der obigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="6b1e3-172">Wählen Sie **Save Nameserver Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="6b1e3-174">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6b1e3-175">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="6b1e3-176">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="6b1e3-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="6b1e3-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="6b1e3-178">(Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="6b1e3-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="6b1e3-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="6b1e3-181">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der folgenden Tabelle direkt oder über Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6b1e3-182">**Erste leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-182">**First empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6b1e3-184">**Zweite leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="6b1e3-187">Wählen Sie **Zeile hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="6b1e3-189">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der ersten Zeile der folgenden Tabelle in die neue leere Zeile ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6b1e3-190">**Dritte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6b1e3-192">**Vierte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="6b1e3-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="6b1e3-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6b1e3-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="6b1e3-195">Wenn Sie den vierten Namenservereintrag hinzufügen möchten, wählen Sie erneut **Zeile hinzufügen** aus, und erstellen Sie einen Datensatz mit den Werten aus der letzten Zeile der obigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="6b1e3-196">Wählen Sie **Save Nameserver Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="6b1e3-198">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="6b1e3-199">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6b1e3-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
