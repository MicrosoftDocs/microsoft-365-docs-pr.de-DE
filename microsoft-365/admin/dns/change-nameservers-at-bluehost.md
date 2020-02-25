---
title: Ändern von Namenservern zum Einrichten von Office 365 bei Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Erfahren Sie, wie Sie Office 365 einrichten können, um Ihre DNS-Einträge bei Bluehost zu verwalten. '
ms.openlocfilehash: 27d73071a08477b0adc372d8a88db2c805fecacf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241131"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="30066-103">Ändern von Namenservern zum Einrichten von Office 365 bei Bluehost</span><span class="sxs-lookup"><span data-stu-id="30066-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="30066-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="30066-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="30066-p101">Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge verwalten soll. (Wenn Sie es vorziehen, können Sie auch [alle Ihre Office 365-DNS-Einträge bei Bluehost verwalten](create-dns-records-at-bluehost.md).)</span><span class="sxs-lookup"><span data-stu-id="30066-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="30066-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="30066-107">Add a TXT record for verification</span></span>

<span data-ttu-id="30066-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="30066-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30066-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="30066-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="30066-112">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="30066-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="30066-113">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="30066-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="30066-114">Suchen Sie auf der Seite **Domains** im Bereich **Domain** die Zeile mit der Domäne, die Sie ändern möchten, und aktivieren Sie dann das Kontrollkästchen für diese Domäne.</span><span class="sxs-lookup"><span data-stu-id="30066-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="30066-115">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="30066-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="30066-116">Wählen Sie im Bereich **domain_name** in der Zeile **DNS-Zonen-Editor** die Option DNS- **Einträge verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="30066-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="30066-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="30066-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="30066-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30066-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="30066-119">**Host Record**</span></span> <br/> |<span data-ttu-id="30066-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="30066-120">**TTL**</span></span> <br/> |<span data-ttu-id="30066-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="30066-121">**Type**</span></span> <br/> |<span data-ttu-id="30066-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="30066-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="30066-123">14400</span><span class="sxs-lookup"><span data-stu-id="30066-123">14400</span></span>  <br/> |<span data-ttu-id="30066-124">TXT</span><span class="sxs-lookup"><span data-stu-id="30066-124">TXT</span></span>  <br/> |<span data-ttu-id="30066-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="30066-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="30066-p105">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="30066-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span> <br/> |

   
5. <span data-ttu-id="30066-129">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="30066-130">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="30066-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="30066-131">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="30066-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="30066-132">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="30066-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="30066-133">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="30066-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="30066-134">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="30066-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="30066-135">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="30066-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="30066-136">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="30066-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="30066-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="30066-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="30066-140">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="30066-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="30066-p107">Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="30066-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="30066-p108">Wenn Sie die Namenservereinträge Ihrer Domäne so ändern, dass sie auf die Office 365-Namenserver verweisen, hat dies Auswirkungen auf alle Dienste, die aktuell mit Ihrer Domäne verbunden sind. So gehen beispielsweise alle an Ihre Domäne (z. B. an Bernd@ *Ihre_Domäne*  .com) gesendeten E-Mail-Nachrichten bei Office 365 ein, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="30066-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="30066-146">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="30066-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="30066-147">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="30066-148">Im ersten Schritt navigieren Sie über [diesen Link](https://my.bluehost.com/cgi/dm) zu Ihrer Domänenseite bei Bluehost.</span><span class="sxs-lookup"><span data-stu-id="30066-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="30066-149">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="30066-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="30066-150">Aktivieren Sie auf der Seite **Domänen** im Bereich **domain_name** das Kontrollkästchen für Ihre Domäne, und wählen Sie dann **Name Servers**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="30066-152">Wählen Sie im Bereich **domain_name** die Option **benutzerdefinierte Namenserver verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="30066-154">Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:</span><span class="sxs-lookup"><span data-stu-id="30066-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="30066-155">Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="30066-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="30066-156">Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="30066-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="30066-157">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="30066-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="30066-158">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der folgenden Tabelle direkt oder über Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="30066-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="30066-159">**Erste leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-159">**First empty row**</span></span> <br/> |<span data-ttu-id="30066-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="30066-161">**Zweite leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="30066-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-1](../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="30066-164">Wählen Sie **Zeile hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="30066-166">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der ersten Zeile der folgenden Tabelle in die neue leere Zeile ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="30066-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="30066-167">**Dritte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="30066-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="30066-169">**Vierte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="30066-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="30066-171">Wenn Sie den vierten Namenservereintrag hinzufügen möchten, wählen Sie erneut **Zeile hinzufügen** aus, und erstellen Sie einen Datensatz mit den Werten aus der letzten Zeile der obigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="30066-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="30066-172">Wählen Sie **Save Nameserver Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="30066-p111">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="30066-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="30066-176">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="30066-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="30066-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="30066-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="30066-178">(Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="30066-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="30066-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="30066-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="30066-181">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der folgenden Tabelle direkt oder über Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="30066-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="30066-182">**Erste leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-182">**First empty row**</span></span> <br/> |<span data-ttu-id="30066-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="30066-184">**Zweite leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="30066-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3](../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="30066-187">Wählen Sie **Zeile hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="30066-189">Geben Sie im Abschnitt **Use Custom Nameservers** die Werte aus der ersten Zeile der folgenden Tabelle in die neue leere Zeile ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="30066-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="30066-190">**Dritte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="30066-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="30066-192">**Vierte leere Zeile**</span><span class="sxs-lookup"><span data-stu-id="30066-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="30066-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="30066-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="30066-195">Wenn Sie den vierten Namenservereintrag hinzufügen möchten, wählen Sie erneut **Zeile hinzufügen** aus, und erstellen Sie einen Datensatz mit den Werten aus der letzten Zeile der obigen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="30066-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="30066-196">Wählen Sie **Save Nameserver Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="30066-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="30066-p113">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="30066-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
