---
title: Ändern von Namenservern zum Einrichten von Office 365 bei Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Erfahren Sie, wie Sie Office 365 einrichten können, um Ihre DNS-Einträge bei Amazon Webdienste (AWS) zu verwalten. '
ms.openlocfilehash: a7125cf0add8200fe152c426f47e7f27a8f6226c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212353"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="38704-103">Ändern von Namenservern zum Einrichten von Office 365 bei Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="38704-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="38704-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="38704-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="38704-p101">Führen Sie die folgenden Anweisungen aus, wenn Office 365 Ihre Office 365-DNS-Einträge automatisch verwalten soll. (Wenn es Ihnen lieber ist, können Sie [alle Ihre Office 365-DNS-Einträge bei AWS selbst verwalten](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="38704-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="38704-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="38704-107">Add a TXT record for verification</span></span>

<span data-ttu-id="38704-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="38704-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38704-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="38704-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="38704-p104">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="38704-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="38704-114">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="38704-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="38704-115">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="38704-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="38704-116">Wählen Sie **Daten Satz Satz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="38704-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="38704-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="38704-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="38704-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="38704-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="38704-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="38704-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38704-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="38704-121">**Name**</span></span> <br/> |<span data-ttu-id="38704-122">**Typ**</span><span class="sxs-lookup"><span data-stu-id="38704-122">**Type**</span></span> <br/> |<span data-ttu-id="38704-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="38704-123">**Alias**</span></span> <br/> |<span data-ttu-id="38704-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="38704-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="38704-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="38704-125">**Value**</span></span> <br/> |<span data-ttu-id="38704-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="38704-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="38704-127">(Lassen Sie dieses Feld leer)</span><span class="sxs-lookup"><span data-stu-id="38704-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="38704-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="38704-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="38704-129">No</span><span class="sxs-lookup"><span data-stu-id="38704-129">No</span></span>  <br/> |<span data-ttu-id="38704-130">300</span><span class="sxs-lookup"><span data-stu-id="38704-130">300</span></span>  <br/> |<span data-ttu-id="38704-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="38704-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="38704-p106">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="38704-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>  <br/>  |<span data-ttu-id="38704-135">Simple</span><span class="sxs-lookup"><span data-stu-id="38704-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="38704-136">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="38704-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="38704-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="38704-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="38704-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="38704-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="38704-139">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="38704-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="38704-140">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="38704-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="38704-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="38704-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="38704-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="38704-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="38704-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="38704-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="38704-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="38704-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="38704-147">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="38704-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="38704-p108">Zum Abschluss der Einrichtung Ihrer Domäne in Office 365 ändern Sie die NS-Einträge bei Ihrer Domänenregistrierungsstelle so, dass sie auf die primären und sekundären Office 365-Namenserver verweisen. Dadurch wird Office 365 zum Aktualisieren der DNS-Einträge der Domäne eingerichtet. Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="38704-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="38704-p109">Wenn Sie die Namenservereinträge Ihrer Domäne so ändern, dass sie auf die Office 365-Namenserver verweisen, hat dies Auswirkungen auf alle Dienste, die aktuell mit Ihrer Domäne verbunden sind. So gehen beispielsweise alle an Ihre Domäne (z. B. an Bernd@ *Ihre_Domäne*  .com) gesendeten E-Mail-Nachrichten bei Office 365 ein, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="38704-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="38704-153">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="38704-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="38704-154">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="38704-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="38704-155">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS.</span><span class="sxs-lookup"><span data-stu-id="38704-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="38704-156">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="38704-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="38704-157">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="38704-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="38704-158">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="38704-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="38704-159">Wählen Sie den **Namenserver**-Eintragssatz aus.</span><span class="sxs-lookup"><span data-stu-id="38704-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="38704-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="38704-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="38704-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="38704-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="38704-163">(Das heißt, löschen Sie nur aktuelle Namenserver, die *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="38704-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="38704-165">Wählen Sie in der **Gültigkeitsdauer (Sekunden):** **1H** (1 Stunde) aus.</span><span class="sxs-lookup"><span data-stu-id="38704-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Wählen Sie 1H für eine Stunde aus.](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="38704-167">Geben Sie, weiterhin im Eintragssatz **NS - Name server**, in das Feld **Value** den Wert aus der **ersten Zeile** der folgenden Tabelle direkt oder durch Kopieren und Einfügen ein, drücken Sie dann die **EINGABETASTE**, und geben Sie den Wert der nächsten **Zeile** direkt oder durch Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="38704-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="38704-168">Jeder Namenserverwert  *muss*  in seiner eigenen separaten Zeile im Feld **Value** stehen (siehe folgende Abbildung).</span><span class="sxs-lookup"><span data-stu-id="38704-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38704-169">**Erste Zeile**</span><span class="sxs-lookup"><span data-stu-id="38704-169">**First line**</span></span> <br/> |<span data-ttu-id="38704-170">ns1.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="38704-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="38704-171">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="38704-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="38704-172">**Zweite Zeile**</span><span class="sxs-lookup"><span data-stu-id="38704-172">**Second line**</span></span> <br/> |<span data-ttu-id="38704-173">ns2.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="38704-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="38704-174">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="38704-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="38704-175">**Dritte Zeile**</span><span class="sxs-lookup"><span data-stu-id="38704-175">**Third line**</span></span> <br/> |<span data-ttu-id="38704-176">NS3.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="38704-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="38704-177">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="38704-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="38704-178">**Vierte Zeile**</span><span class="sxs-lookup"><span data-stu-id="38704-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="38704-179">NS4.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="38704-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="38704-180">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="38704-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Geben Sie den Wert der ersten Textreihe in das Feld Wert ein oder fügen Sie ihn ein.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="38704-182">Wählen Sie **Speichersatz speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="38704-182">Select **Save Record Set**.</span></span>
    
    ![Daten Satz Satz speichern auswählen](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="38704-p113">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="38704-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
