---
title: Ändern von Namenservern zum Einrichten von Microsoft mit Google-Domänen
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Erfahren Sie, wie Sie Microsoft zum Verwalten der DNS-Einträge Ihrer benutzerdefinierten Domäne in Google-Domänen einrichten können.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658440"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="e379c-103">Ändern von Namenservern zum Einrichten von Microsoft mit Google-Domänen</span><span class="sxs-lookup"><span data-stu-id="e379c-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="e379c-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="e379c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e379c-105">Befolgen Sie diese Anweisungen, wenn Microsoft Ihre DNS-Einträge für Sie verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="e379c-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="e379c-106">(Wenn es Ihnen lieber ist, können Sie [alle Ihre DNS-Einträge bei Google Domains verwalten](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="e379c-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e379c-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e379c-107">Add a TXT record for verification</span></span>

<span data-ttu-id="e379c-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="e379c-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e379c-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="e379c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e379c-112">Um zu beginnen, navigieren Sie über [diesen Link](https://domains.google.com/registrar)zu ihrer Domänen Seite bei Google Domains.</span><span class="sxs-lookup"><span data-stu-id="e379c-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="e379c-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="e379c-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="e379c-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="e379c-114">To do so:</span></span>
    
1. <span data-ttu-id="e379c-115">Wählen Sie **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e379c-116">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie erneut **Anmelden** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="e379c-117">Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e379c-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e379c-118">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e379c-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e379c-119">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="e379c-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e379c-120">(Wählen Sie in der Dropdownliste den Wert für **Type** aus.)</span><span class="sxs-lookup"><span data-stu-id="e379c-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e379c-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="e379c-121">**Name**</span></span> <br/> |<span data-ttu-id="e379c-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="e379c-122">**Type**</span></span> <br/> |<span data-ttu-id="e379c-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e379c-123">**TTL**</span></span> <br/> |<span data-ttu-id="e379c-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="e379c-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="e379c-125">TXT</span><span class="sxs-lookup"><span data-stu-id="e379c-125">TXT</span></span>  <br/> |<span data-ttu-id="e379c-126">1H</span><span class="sxs-lookup"><span data-stu-id="e379c-126">1H</span></span>  <br/> |<span data-ttu-id="e379c-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e379c-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="e379c-p105">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="e379c-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>       <br/>  |
   
4. <span data-ttu-id="e379c-131">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e379c-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="e379c-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e379c-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e379c-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="e379c-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e379c-134">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="e379c-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e379c-135">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="e379c-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e379c-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e379c-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e379c-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e379c-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e379c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e379c-142">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="e379c-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="e379c-143">Um die Einrichtung Ihrer Domäne bei Microsoft abzuschließen, ändern Sie die NS-Einträge Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf den primären und sekundären Namenserver von Microsoft verweist.</span><span class="sxs-lookup"><span data-stu-id="e379c-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="e379c-144">Dadurch wird Microsoft so eingerichtet, dass die DNS-Einträge der Domäne für Sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e379c-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="e379c-145">Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="e379c-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e379c-146">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft Name-Server verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e379c-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="e379c-147">Beispielsweise alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="e379c-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="e379c-148">com) wird gestartet, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="e379c-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e379c-149">Im folgenden Verfahren wird gezeigt, wie Sie andere, unerwünschte Namenserver aus der Liste löschen können, und Sie erfahren, wie Sie die richtigen Namenserver hinzufügen, wenn sie sich nicht bereits in der Liste befinden.</span><span class="sxs-lookup"><span data-stu-id="e379c-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="e379c-150">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden:</span><span class="sxs-lookup"><span data-stu-id="e379c-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="e379c-p110">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e379c-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="e379c-154">Wählen Sie **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e379c-155">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Sign In** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="e379c-156">Wählen Sie auf der Seite **Domains** im Abschnitt **Domain** die Option **Configure DNS** für die Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="e379c-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e379c-157">Wählen Sie auf der Seite **Domains** im Abschnitt **Name servers** die Option **Use custom name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="e379c-159">Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:</span><span class="sxs-lookup"><span data-stu-id="e379c-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="e379c-160">Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="e379c-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="e379c-161">Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="e379c-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="e379c-162">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="e379c-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="e379c-163">Fügen Sie den ersten Namenserver hinzu.</span><span class="sxs-lookup"><span data-stu-id="e379c-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="e379c-164">Geben Sie im Bereich **Name servers** im Feld **NAME SERVER** den ersten Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e379c-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="e379c-165">**Erster Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-165">**First name server**</span></span> <br/> |<span data-ttu-id="e379c-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e379c-167">**Zweiter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-167">**Second name server**</span></span> <br/> |<span data-ttu-id="e379c-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e379c-169">**Dritter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-169">**Third name server**</span></span> <br/> |<span data-ttu-id="e379c-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e379c-171">**Vierter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="e379c-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="e379c-174">Wählen Sie das Steuerelement **+ (hinzufügen)** aus, um eine leere Zeile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e379c-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="e379c-176">Fügen Sie die anderen drei Namenservereinträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e379c-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="e379c-177">Erstellen Sie im Abschnitt **benutzerdefinierte Namenserver verwenden** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann das Steuerelement **+ (hinzufügen)** aus, um eine weitere Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e379c-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="e379c-178">Wiederholen Sie diesen Vorgang, bis Sie alle vier Namenservereinträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e379c-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="e379c-179">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="e379c-181">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e379c-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e379c-182">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e379c-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="e379c-183">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="e379c-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="e379c-184">Wenn andere Namenserver aufgeführt sind, wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e379c-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="e379c-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="e379c-186">(Das heißt, löschen Sie nur aktuelle Namenserver, die  *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com** oder **NS4.BDM.microsoftonline.com** sind.)</span><span class="sxs-lookup"><span data-stu-id="e379c-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="e379c-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="e379c-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="e379c-190">Geben Sie anschließend im Bereich **Name servers** in den **NAME SERVER**-Zeilen die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e379c-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="e379c-191">**Erster Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-191">**First name server**</span></span> <br/> |<span data-ttu-id="e379c-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e379c-193">**Zweiter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-193">**Second name server**</span></span> <br/> |<span data-ttu-id="e379c-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e379c-195">**Dritter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-195">**Third name server**</span></span> <br/> |<span data-ttu-id="e379c-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e379c-197">**Vierter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="e379c-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="e379c-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e379c-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="e379c-200">Wählen Sie das Steuerelement **+ (hinzufügen)** aus, um eine leere Zeile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e379c-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="e379c-202">Fügen Sie die anderen beiden Namenservereinträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e379c-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="e379c-203">Erstellen Sie im Abschnitt **benutzerdefinierte Namenserver verwenden** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann das Steuerelement **+ (hinzufügen)** aus, um eine weitere Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e379c-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="e379c-204">Wiederholen Sie diesen Vorgang, bis Sie alle vier Namenservereinträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e379c-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="e379c-205">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e379c-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="e379c-207">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e379c-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e379c-208">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e379c-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
