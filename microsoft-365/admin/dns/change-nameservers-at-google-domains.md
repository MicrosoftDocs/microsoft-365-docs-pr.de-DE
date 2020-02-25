---
title: Ändern von Namenservern zum Einrichten von Office 365 bei Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Erfahren Sie, wie Sie Office 365 einrichten können, um die DNS-Einträge Ihrer benutzerdefinierten Domäne bei Google Domains zu verwalten.
ms.openlocfilehash: 771d38b9a3d08bef75c3ad1958f981539edb6c04
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242765"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="ede47-103">Ändern von Namenservern zum Einrichten von Office 365 bei Google Domains</span><span class="sxs-lookup"><span data-stu-id="ede47-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="ede47-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ede47-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ede47-p101">Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge automatisch verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei Google Domains verwalten](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="ede47-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ede47-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ede47-107">Add a TXT record for verification</span></span>

<span data-ttu-id="ede47-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="ede47-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="ede47-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="ede47-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ede47-112">Um zu beginnen, navigieren Sie über [diesen Link](https://domains.google.com/registrar)zu ihrer Domänen Seite bei Google Domains.</span><span class="sxs-lookup"><span data-stu-id="ede47-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="ede47-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="ede47-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="ede47-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="ede47-114">To do so:</span></span>
    
1. <span data-ttu-id="ede47-115">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="ede47-116">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="ede47-117">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ede47-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="ede47-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ede47-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="ede47-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="ede47-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="ede47-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="ede47-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ede47-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="ede47-121">**Name**</span></span> <br/> |<span data-ttu-id="ede47-122">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ede47-122">**Type**</span></span> <br/> |<span data-ttu-id="ede47-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ede47-123">**TTL**</span></span> <br/> |<span data-ttu-id="ede47-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="ede47-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="ede47-125">TXT</span><span class="sxs-lookup"><span data-stu-id="ede47-125">TXT</span></span>  <br/> |<span data-ttu-id="ede47-126">1H</span><span class="sxs-lookup"><span data-stu-id="ede47-126">1H</span></span>  <br/> |<span data-ttu-id="ede47-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ede47-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="ede47-p105">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="ede47-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>       <br/>  |
   
4. <span data-ttu-id="ede47-131">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ede47-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="ede47-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ede47-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ede47-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ede47-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="ede47-134">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="ede47-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ede47-135">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="ede47-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="ede47-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ede47-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ede47-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ede47-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ede47-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="ede47-142">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="ede47-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="ede47-p107">Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ede47-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ede47-146">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Office 365 Namenserver verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ede47-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="ede47-147">Beispielsweise alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="ede47-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="ede47-148">com) wird in Office 365 gestartet, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="ede47-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ede47-149">Im folgenden Verfahren wird gezeigt, wie Sie andere, unerwünschte Namenserver aus der Liste löschen können, und Sie erfahren, wie Sie die richtigen Namenserver hinzufügen, wenn sie sich nicht bereits in der Liste befinden.</span><span class="sxs-lookup"><span data-stu-id="ede47-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="ede47-150">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden:</span><span class="sxs-lookup"><span data-stu-id="ede47-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="ede47-p110">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ede47-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="ede47-154">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="ede47-155">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="ede47-156">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="ede47-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="ede47-157">Wählen Sie auf der Seite **Domains** im Abschnitt **Name servers** die Option **Use custom name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="ede47-159">Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:</span><span class="sxs-lookup"><span data-stu-id="ede47-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="ede47-160">Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="ede47-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="ede47-161">Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="ede47-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="ede47-162">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="ede47-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="ede47-163">Fügen Sie den ersten Namenserver hinzu.</span><span class="sxs-lookup"><span data-stu-id="ede47-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="ede47-164">Geben Sie im Bereich **Name servers** im Feld **NAME SERVER** den ersten Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ede47-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="ede47-165">**Erster Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-165">**First name server**</span></span> <br/> |<span data-ttu-id="ede47-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ede47-167">**Zweiter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-167">**Second name server**</span></span> <br/> |<span data-ttu-id="ede47-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ede47-169">**Dritter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-169">**Third name server**</span></span> <br/> |<span data-ttu-id="ede47-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ede47-171">**Vierter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="ede47-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegate-1-2](../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="ede47-174">Wählen Sie das Steuerelement **+ (hinzufügen)** aus, um eine leere Zeile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ede47-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="ede47-176">Fügen Sie die anderen drei Namenservereinträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="ede47-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="ede47-177">Erstellen Sie im Abschnitt **benutzerdefinierte Namenserver verwenden** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann das Steuerelement **+ (hinzufügen)** aus, um eine weitere Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ede47-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="ede47-178">Wiederholen Sie diesen Vorgang, bis Sie alle vier Namenservereinträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ede47-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="ede47-179">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ede47-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="ede47-p111">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ede47-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="ede47-183">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="ede47-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="ede47-184">Wenn andere Namenserver aufgeführt sind, wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="ede47-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ede47-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="ede47-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="ede47-186">(Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="ede47-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="ede47-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="ede47-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="ede47-190">Geben Sie anschließend im Bereich **Name servers** in den **NAME SERVER**-Zeilen die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ede47-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="ede47-191">**Erster Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-191">**First name server**</span></span> <br/> |<span data-ttu-id="ede47-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ede47-193">**Zweiter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-193">**Second name server**</span></span> <br/> |<span data-ttu-id="ede47-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ede47-195">**Dritter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-195">**Third name server**</span></span> <br/> |<span data-ttu-id="ede47-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="ede47-197">**Vierter Namenserver**</span><span class="sxs-lookup"><span data-stu-id="ede47-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="ede47-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="ede47-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegate-1-7](../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="ede47-200">Wählen Sie das Steuerelement **+ (hinzufügen)** aus, um eine leere Zeile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ede47-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="ede47-202">Fügen Sie die anderen beiden Namenservereinträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="ede47-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="ede47-203">Erstellen Sie im Abschnitt **benutzerdefinierte Namenserver verwenden** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann das Steuerelement **+ (hinzufügen)** aus, um eine weitere Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ede47-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="ede47-204">Wiederholen Sie diesen Vorgang, bis Sie alle vier Namenservereinträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ede47-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="ede47-205">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ede47-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="ede47-p113">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ede47-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
