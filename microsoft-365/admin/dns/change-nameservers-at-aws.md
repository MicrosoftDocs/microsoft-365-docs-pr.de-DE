---
title: Ändern von Namenservern zum Einrichten von Microsoft mit Amazon Webdienste (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Erfahren Sie, wie Sie Microsoft zum Verwalten Ihrer DNS-Einträge bei Amazon Webdienste (AWS) einrichten können. '
ms.openlocfilehash: 9f5bfd54020dfb793bbaad9aa8e081e87abc5ce8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646487"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="8bc3f-103">Ändern von Namenservern zum Einrichten von Microsoft mit Amazon Webdienste (AWS)</span><span class="sxs-lookup"><span data-stu-id="8bc3f-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="8bc3f-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8bc3f-105">Befolgen Sie diese Anweisungen, wenn Microsoft Ihre DNS-Einträge für Sie verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="8bc3f-106">(Wenn es Ihnen lieber ist, können Sie [alle Ihre Microsoft-DNS-Einträge bei AWS verwalten](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="8bc3f-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8bc3f-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="8bc3f-107">Add a TXT record for verification</span></span>

<span data-ttu-id="8bc3f-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bc3f-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8bc3f-p104">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS. Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8bc3f-114">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8bc3f-115">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8bc3f-116">Wählen Sie **Daten Satz Satz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="8bc3f-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="8bc3f-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="8bc3f-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8bc3f-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8bc3f-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-121">**Name**</span></span> <br/> |<span data-ttu-id="8bc3f-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-122">**Type**</span></span> <br/> |<span data-ttu-id="8bc3f-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-123">**Alias**</span></span> <br/> |<span data-ttu-id="8bc3f-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="8bc3f-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-125">**Value**</span></span> <br/> |<span data-ttu-id="8bc3f-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="8bc3f-127">(Lassen Sie dieses Feld leer)</span><span class="sxs-lookup"><span data-stu-id="8bc3f-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="8bc3f-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="8bc3f-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="8bc3f-129">No</span><span class="sxs-lookup"><span data-stu-id="8bc3f-129">No</span></span>  <br/> |<span data-ttu-id="8bc3f-130">300</span><span class="sxs-lookup"><span data-stu-id="8bc3f-130">300</span></span>  <br/> |<span data-ttu-id="8bc3f-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8bc3f-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="8bc3f-p106">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel- oder Verweisadresse** aus der Tabelle in [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="8bc3f-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>  <br/>  |<span data-ttu-id="8bc3f-135">Einfach</span><span class="sxs-lookup"><span data-stu-id="8bc3f-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="8bc3f-136">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="8bc3f-137">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8bc3f-138">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern eine Suche nach dem Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="8bc3f-139">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8bc3f-140">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8bc3f-141">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="8bc3f-142">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="8bc3f-143">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8bc3f-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bc3f-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8bc3f-147">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="8bc3f-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="8bc3f-148">Um die Einrichtung Ihrer Domäne bei Microsoft abzuschließen, ändern Sie die NS-Einträge Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf den primären und sekundären Namenserver von Microsoft verweist.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="8bc3f-149">Dadurch wird Microsoft so eingerichtet, dass die DNS-Einträge der Domäne für Sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="8bc3f-150">Wir fügen alle Einträge hinzu, sodass E-Mails, Skype for Business Online und Ihre öffentliche Website in Verbindung mit Ihrer Domäne funktionieren und alles für Sie eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8bc3f-151">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft Name-Server verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8bc3f-152">Beispielsweise werden alle e-Mails, die an Ihre Domäne gesendet werden (wie Rob@ *your_domain*  . com), nach dem Ausführen dieser Änderung an Microsoft weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="8bc3f-153">Im folgenden Verfahren wird gezeigt, wie Sie alle anderen unerwünschten Namenserver aus der Liste löschen und wie Sie die richtigen Nameserver hinzufügen, wenn Sie noch nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="8bc3f-154">> Wenn Sie die Schritte in diesem Abschnitt abgeschlossen haben, sollten Sie die folgenden vier Namenserver finden: > ns1.BDM.microsoftonline.com > ns2.BDM.microsoftonline.com > NS3.BDM.microsoftonline.com > NS4.BDM.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8bc3f-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="8bc3f-155">Navigieren Sie im ersten Schritt über [diesen Link](https://console.aws.amazon.com/route53/home) zu Ihrer Domänenseite bei AWS.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="8bc3f-156">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8bc3f-157">Wählen Sie auf der Seite **Ressourcen** die Option **gehostete Zonen**aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="8bc3f-158">Wählen Sie auf der Seite **gehostete Zonen** in der Spalte **Domänenname** den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="8bc3f-159">Wählen Sie den **Namenserver**-Eintragssatz aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="8bc3f-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="8bc3f-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="8bc3f-163">(Das heißt, löschen Sie nur aktuelle Namenserver, die  *nicht* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**oder **NS4.BDM.microsoftonline.com**sind.)</span><span class="sxs-lookup"><span data-stu-id="8bc3f-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="8bc3f-165">Wählen Sie in der **Gültigkeitsdauer (Sekunden):** **1H** (1 Stunde) aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Wählen Sie 1H für eine Stunde aus.](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="8bc3f-167">Geben Sie, weiterhin im Eintragssatz **NS - Name server**, in das Feld **Value** den Wert aus der **ersten Zeile** der folgenden Tabelle direkt oder durch Kopieren und Einfügen ein, drücken Sie dann die **EINGABETASTE**, und geben Sie den Wert der nächsten **Zeile** direkt oder durch Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8bc3f-168">Jeder Namenserverwert  *muss*  in seiner eigenen separaten Zeile im Feld **Value** stehen (siehe folgende Abbildung).</span><span class="sxs-lookup"><span data-stu-id="8bc3f-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8bc3f-169">**Erste Zeile**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-169">**First line**</span></span> <br/> |<span data-ttu-id="8bc3f-170">ns1.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="8bc3f-171">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="8bc3f-172">**Zweite Zeile**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-172">**Second line**</span></span> <br/> |<span data-ttu-id="8bc3f-173">ns2.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="8bc3f-174">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="8bc3f-175">**Dritte Zeile**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-175">**Third line**</span></span> <br/> |<span data-ttu-id="8bc3f-176">NS3.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="8bc3f-177">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="8bc3f-178">**Vierte Zeile**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="8bc3f-179">NS4.BDM.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="8bc3f-180">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="8bc3f-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Geben Sie den Wert der ersten Textreihe in das Feld Wert ein oder fügen Sie ihn ein.](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="8bc3f-182">Wählen Sie **Speichersatz speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-182">Select **Save Record Set**.</span></span>
    
    ![Daten Satz Satz speichern auswählen](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="8bc3f-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8bc3f-185">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8bc3f-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
