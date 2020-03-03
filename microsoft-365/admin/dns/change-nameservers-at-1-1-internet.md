---
title: Ändern von Namenservern zum Einrichten von Office 365 mit 1&1 Ionos
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Erfahren Sie, wie Sie Office 365, die von 21Vianet betrieben werden, zum Verwalten Ihrer DNS-Einträge einrichten können, wenn 1&1 Internet der DNS-Hostanbieter ist.
ms.openlocfilehash: 3678d5372b9edd8e9333ad78862694b450abe53a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352566"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a><span data-ttu-id="daa6e-103">Ändern von Namenservern zum Einrichten von Office 365 mit 1&1 Ionos</span><span class="sxs-lookup"><span data-stu-id="daa6e-103">Change nameservers to set up Office 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="daa6e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="daa6e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="daa6e-105">Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge automatisch verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="daa6e-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="daa6e-106">(Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei 1&1 Ionos verwalten](create-dns-records-at-1-1-internet.md).)</span><span class="sxs-lookup"><span data-stu-id="daa6e-106">(If you prefer, you can [manage all your Office 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="daa6e-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="daa6e-107">Add a TXT record for verification</span></span>


<span data-ttu-id="daa6e-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="daa6e-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="daa6e-112">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="daa6e-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="daa6e-113">Um zu beginnen, wechseln Sie über [diesen Link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)zu ihrer Domänen Seite bei 1&1 Ionos.</span><span class="sxs-lookup"><span data-stu-id="daa6e-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="daa6e-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="daa6e-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="daa6e-115">Wählen Sie unter **Meine Domänen**die Option **Domänen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="daa6e-116">Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten. Wählen Sie dann das **Panel** -Steuerelement ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="daa6e-117">Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="daa6e-118">Wählen Sie im Abschnitt **txt-und SRV-Einträge** die Option **Eintrag hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="daa6e-119">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="daa6e-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="daa6e-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="daa6e-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="daa6e-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="daa6e-121">**Type**</span></span> <br/> |<span data-ttu-id="daa6e-122">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="daa6e-122">**Prefix**</span></span> <br/> |<span data-ttu-id="daa6e-123">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="daa6e-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="daa6e-124">TXT</span><span class="sxs-lookup"><span data-stu-id="daa6e-124">TXT</span></span>  <br/> |<span data-ttu-id="daa6e-125">(Dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="daa6e-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="daa6e-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="daa6e-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="daa6e-127">**Hinweis:** Dies ist ein nur Beispiel.</span><span class="sxs-lookup"><span data-stu-id="daa6e-127">**Note**: This is an example.</span></span> <span data-ttu-id="daa6e-128">Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.</span><span class="sxs-lookup"><span data-stu-id="daa6e-128">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="daa6e-129">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="daa6e-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="daa6e-130">Wählen Sie **Speichern**und dann erneut **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="daa6e-131">Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="daa6e-132">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="daa6e-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="daa6e-133">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="daa6e-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="daa6e-134">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="daa6e-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="daa6e-135">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="daa6e-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="daa6e-136">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="daa6e-137">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="daa6e-138">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="daa6e-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="daa6e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="daa6e-142">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="daa6e-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="daa6e-p107">Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="daa6e-p108">Wenn Sie die Namenservereinträge Ihrer Domäne so ändern, dass sie auf die Office 365-Namenserver verweisen, hat dies Auswirkungen auf alle Dienste, die aktuell mit Ihrer Domäne verbunden sind. So gehen beispielsweise alle an Ihre Domäne (z. B. an Bernd@ *Ihre_Domäne*  .com) gesendeten E-Mail-Nachrichten bei Office 365 ein, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
<span data-ttu-id="daa6e-p109">Sind Sie bereit, Ihre NS-Einträge so zu ändern, dass Office 365 Ihre Domäne einrichten kann? Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an (beginnen Sie bei 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="daa6e-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="daa6e-150">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="daa6e-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="daa6e-151">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="daa6e-152">Um zu beginnen, navigieren Sie über [diesen Link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)zu ihrer Domänen Seite bei 1&1 Ionos.</span><span class="sxs-lookup"><span data-stu-id="daa6e-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="daa6e-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="daa6e-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="daa6e-154">Wählen Sie unter **Meine Domänen**die Option **Domänen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="daa6e-155">Suchen Sie auf der Seite **Domänen Center** die Domäne, die Sie aktualisieren möchten, und wählen Sie dann das Steuerelement **Panel** ( **v**) für diese Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="daa6e-156">Wählen Sie im Bereich **Domäneneinstellungen** die Option **DNS-Einstellungen bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="daa6e-157">Wählen Sie im Abschnitt **Name Server Settings** die Option **Other name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="daa6e-158">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="daa6e-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="daa6e-159">Abhängig davon, ob auf der jetzt angezeigten Seite bereits Namenserver aufgelistet sind oder nicht, setzen Sie den Vorgang mit einem der beiden folgenden Verfahren fort:</span><span class="sxs-lookup"><span data-stu-id="daa6e-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="daa6e-160">Wenn noch **KEINE** Namenserver aufgelistet sind, [Wenn noch KEINE Namenserver aufgelistet sind](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="daa6e-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="daa6e-161">Wenn **BEREITS** Namenserver aufgelistet sind, [Wenn Namenserver BEREITS aufgelistet sind](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="daa6e-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="daa6e-162">Wenn noch KEINE Namenserver aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="daa6e-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="daa6e-163">Geben Sie im Feld **Name server 1** den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="daa6e-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="daa6e-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="daa6e-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="daa6e-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Eingeben eines Werts in das Feld Name Server 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="daa6e-167">Wählen Sie in der Dropdownliste **Additional name servers** den Eintrag **My secondary name servers** aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="daa6e-169">Geben Sie in den Feldern **Name server 2, 3 und 4** den Wert aus der folgenden Tabelle ein. Sie können den Wert auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="daa6e-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="daa6e-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="daa6e-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="daa6e-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="daa6e-172">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="daa6e-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="daa6e-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="daa6e-174">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="daa6e-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="daa6e-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="daa6e-176">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="daa6e-176">Select **Save**.</span></span>
    
    ![Auswählen von "Speichern" auf der Seite "Name Server-Einstellungen"](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="daa6e-178">Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-178">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Auswählen von "Speichern" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="daa6e-p112">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="daa6e-182">Wenn Namenserver BEREITS aufgelistet sind</span><span class="sxs-lookup"><span data-stu-id="daa6e-182">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="daa6e-p113">Folgen Sie diesen Schritten  *nur*  , wenn es andere Namenserver als die vier  *korrekten*  Namenserver gibt. (Das heißt, löschen Sie  *nur*  andere als die vier korrekten Namenserver, also  *nicht* **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** oder **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="daa6e-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="daa6e-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="daa6e-187">Geben Sie in den Feldern **Nameserver 1, 2, 3 und 4** die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="daa6e-187">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="daa6e-188">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="daa6e-188">**Name server 1**</span></span> <br/> |<span data-ttu-id="daa6e-189">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-189">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="daa6e-190">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="daa6e-190">**Name server 2**</span></span> <br/> |<span data-ttu-id="daa6e-191">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-191">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="daa6e-192">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="daa6e-192">**Name server 3**</span></span> <br/> |<span data-ttu-id="daa6e-193">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-193">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="daa6e-194">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="daa6e-194">**Name server 4**</span></span> <br/> |<span data-ttu-id="daa6e-195">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="daa6e-195">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Eingeben von Namenserver Werten](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="daa6e-197">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="daa6e-197">Select **Save**.</span></span>
    
    ![Auswählen von "Speichern" auf der Seite "Name Server-Einstellungen"](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="daa6e-199">Wählen Sie im Dialogfeld **DNS-Einstellungen bearbeiten** die Option **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="daa6e-199">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Auswählen von "Speichern" im Dialogfeld "DNS-Einstellungen bearbeiten"](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="daa6e-p114">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="daa6e-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  


