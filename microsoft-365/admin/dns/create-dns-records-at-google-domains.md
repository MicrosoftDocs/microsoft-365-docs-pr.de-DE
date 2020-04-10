---
title: Erstellen von DNS-Einträgen für Office 365 bei Google Domains
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, lync und andere Dienste in Google Domains für Office 365 einrichten.
ms.openlocfilehash: f0a9a42127fc5b722679013b899255f77840d670
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211727"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a><span data-ttu-id="d5d9e-103">Erstellen von DNS-Einträgen für Office 365 bei Google Domains</span><span class="sxs-lookup"><span data-stu-id="d5d9e-103">Create DNS records at Google Domains for Office 365</span></span>

 <span data-ttu-id="d5d9e-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d5d9e-105">Wenn Google Domains Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Lync und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="d5d9e-106">Nachdem Sie diese Einträge bei Google Domains hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-106">After you add these records at Google Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="d5d9e-107">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="d5d9e-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5d9e-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d5d9e-111">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="d5d9e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="d5d9e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d5d9e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d5d9e-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5d9e-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d5d9e-p104">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="d5d9e-120">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-120">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="d5d9e-121">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-121">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="d5d9e-122">Suchen Sie auf der Seite " **Meine Domänen** " nach der Domäne, die Sie mit Office 365 verwenden möchten, und wählen Sie den Link **Verwalten** daneben aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-122">On the **My domains** page, find the domain you want to use with Office 365, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="d5d9e-123">Wählen Sie in der linken Navigationsleiste **DNS**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-123">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="d5d9e-124">Geben Sie im Abschnitt \* \* benutzerdefinierte Ressourceneinträge \* \* in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-124">In the \*\* Custom resource records \*\* section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d5d9e-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-125">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="d5d9e-126">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-126">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d5d9e-127">**Name**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-127">**Name**</span></span> <br/> |<span data-ttu-id="d5d9e-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-128">**Type**</span></span> <br/> |<span data-ttu-id="d5d9e-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-129">**TTL**</span></span> <br/> |<span data-ttu-id="d5d9e-130">**Daten**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-130">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="d5d9e-131">TXT</span><span class="sxs-lookup"><span data-stu-id="d5d9e-131">TXT</span></span>  <br/> |<span data-ttu-id="d5d9e-132">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-132">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d5d9e-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d5d9e-p106">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p106">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
4. <span data-ttu-id="d5d9e-137">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-137">Select **Add**.</span></span>
    
5. <span data-ttu-id="d5d9e-138">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d5d9e-139">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-139">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="d5d9e-140">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-140">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d5d9e-141">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="d5d9e-142">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="d5d9e-143">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-143">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="d5d9e-144">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5d9e-p107">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="d5d9e-148">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="d5d9e-148">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="d5d9e-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d5d9e-149"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d5d9e-p108">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="d5d9e-153">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-153">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="d5d9e-154">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-154">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="d5d9e-155">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-155">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d5d9e-p109">Wenn Sie über ein G Suite-E-Mail-Konto verfügen, müssen Sie zuerst die diesem Konto zugeordneten MX-Einträge löschen. Die G Suite-MX-Einträge verhindern, dass Sie andere MX-Einträge hinzufügen, einschließlich der für Office 365 erforderlichen Einträge. Beachten Sie, dass Ihr G Suite-Konto durch das Löschen der G Suite-Einträge nicht gelöscht wird. Gehen Sie folgendermaßen vor, um Ihre G Suite-MX-Einträge zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p109">If you have a G Suite email account, you must first delete the MX records associated with that account. The G Suite MX records prevent you from adding any other MX records, including those required for Office 365. Note that deleting the G Suite records does not delete your G Suite account. To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="d5d9e-160">Wählen Sie im Abschnitt **synthetische Datensätze** im Bereich **G Suite** die Option **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-160">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="d5d9e-161">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-161">(You may have to scroll down.)</span></span>
    
    ![Wählen Sie im Abschnitt synthetische Datensätze löschen aus.](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="d5d9e-163">Wählen Sie **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-163">Select **Delete**.</span></span>
    
    ![Wählen Sie löschen aus.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="d5d9e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-165">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d5d9e-166">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-166">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="d5d9e-167">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-167">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d5d9e-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-168">**Name**</span></span>|<span data-ttu-id="d5d9e-169">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-169">**Type**</span></span>|<span data-ttu-id="d5d9e-170">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-170">**TTL**</span></span>|<span data-ttu-id="d5d9e-171">**Daten**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-171">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d5d9e-172">MX</span><span class="sxs-lookup"><span data-stu-id="d5d9e-172">MX</span></span>  <br/> |<span data-ttu-id="d5d9e-173">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-173">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-174">0  *\<Domänenschlüssel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-174">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d5d9e-175">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-175">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d5d9e-p110">Die **0** ist der MX-Prioritätswert. Fügen Sie ihn am Anfang des MX-Werts hinzu, vom Rest des Werts durch ein Leerzeichen getrennt.  </span><span class="sxs-lookup"><span data-stu-id="d5d9e-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="d5d9e-178">**Hinweis:** Rufen Sie Ihren Domänenschlüssel (\<*domain-key*\>) aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-178">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span>  [<span data-ttu-id="d5d9e-179">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="d5d9e-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="d5d9e-180">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-180">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="d5d9e-182">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-182">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="d5d9e-184">Wenn es weitere benutzerdefinierte MX-Einträge gibt, entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-184">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="d5d9e-185">Wählen Sie in der Zeile MX Record die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-185">Select **Edit** in the MX record row.</span></span> 
    
    ![Wählen Sie bearbeiten in der Zeile MX-Eintrag aus.](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="d5d9e-187">Wählen Sie für jeden der anderen benutzerdefinierten MX-Einträge den Eintrag im Feld **Daten** aus, und drücken Sie dann die **ENTF** -Taste auf der Tastatur, um den Datensatz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-187">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="d5d9e-188">Fahren Sie fort, bis Sie den **Data**-Eintrag für jeden anderen MX-Eintrag gelöscht haben.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-188">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="d5d9e-190">Wenn Sie den **Daten** Eintrag für jeden der anderen MX-Einträge gelöscht haben, wählen Sie **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-190">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Wählen Sie speichern aus.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="d5d9e-192">Fügen Sie die für Office 365 erforderlichen fünf CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-192">Add the five CNAME records that are required for Office 365</span></span>

1. <span data-ttu-id="d5d9e-193">Um zu beginnen, navigieren Sie zu Ihrer [Google Domänen Seite]https://domains.google.com/registrar) (und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-193">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="d5d9e-194">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-194">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="d5d9e-195">Fügen Sie den ersten CNAME-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-195">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="d5d9e-196">Geben Sie im Bereich **Custom resource records** in den Feldern für den neuen Eintrag die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-196">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="d5d9e-197">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-197">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="d5d9e-198">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-198">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d5d9e-199">**Name**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-199">**Name**</span></span>|<span data-ttu-id="d5d9e-200">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-200">**Type**</span></span>|<span data-ttu-id="d5d9e-201">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-201">**TTL**</span></span>|<span data-ttu-id="d5d9e-202">**Daten**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-202">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d5d9e-203">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d5d9e-203">autodiscover</span></span>  <br/> |<span data-ttu-id="d5d9e-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="d5d9e-204">CNAME</span></span>  <br/> |<span data-ttu-id="d5d9e-205">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-205">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-206">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-206">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d5d9e-207">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-207">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d5d9e-208">sip</span><span class="sxs-lookup"><span data-stu-id="d5d9e-208">sip</span></span>  <br/> |<span data-ttu-id="d5d9e-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="d5d9e-209">CNAME</span></span>  <br/> |<span data-ttu-id="d5d9e-210">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-210">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-211">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-211">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d5d9e-212">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-212">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d5d9e-213">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d5d9e-213">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d5d9e-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="d5d9e-214">CNAME</span></span>  <br/> |<span data-ttu-id="d5d9e-215">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-215">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-216">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-216">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d5d9e-217">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-217">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d5d9e-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d5d9e-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d5d9e-219">CNAME</span><span class="sxs-lookup"><span data-stu-id="d5d9e-219">CNAME</span></span>  <br/> |<span data-ttu-id="d5d9e-220">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-220">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-221">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-221">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="d5d9e-222">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-222">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d5d9e-223">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d5d9e-223">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d5d9e-224">CNAME</span><span class="sxs-lookup"><span data-stu-id="d5d9e-224">CNAME</span></span>  <br/> |<span data-ttu-id="d5d9e-225">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-225">1H</span></span>  <br/> |<span data-ttu-id="d5d9e-226">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-226">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="d5d9e-227">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-227">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="d5d9e-229">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-229">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="d5d9e-231">Fügen Sie die anderen vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-231">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="d5d9e-232">Erstellen Sie im Abschnitt **benutzerdefinierte Ressourceneinträge** einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-232">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="d5d9e-233">Wiederholen Sie diesen Vorgang, bis Sie alle erforderlichen CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-233">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d5d9e-234">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="d5d9e-234">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5d9e-235">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-235">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d5d9e-236">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-236">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d5d9e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-237">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="d5d9e-238">Damit verfügen Sie über einen einzigen SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-238">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="d5d9e-239">Benötigen Sie Beispiele?</span><span class="sxs-lookup"><span data-stu-id="d5d9e-239">Need examples?</span></span> <span data-ttu-id="d5d9e-240">Schauen Sie sich diese [Details und SPF-Beispieleinträge](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords) an.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-240">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="d5d9e-241">Zum Überprüfen Ihres SPF-Eintrags können Sie eines dieser [SPF-Überprüfungstools](../setup/domains-faq.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-241">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="d5d9e-p113">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="d5d9e-245">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-245">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="d5d9e-246">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-246">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="d5d9e-247">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-247">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="d5d9e-248">Wählen Sie im Abschnitt **benutzerdefinierte Ressourceneinträge** in der Zeile TXT-Eintrag die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-248">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d5d9e-p114">Google Domains speichert TXT-Einträge als Satz, der mehrere Datensätze enthalten kann. Wenn Sie über mindestens einen weiteren TXT-Eintrag verfügen, z. B. den zur Überprüfung Ihrer Domäne verwendeten TXT-Eintrag, müssen Sie dieser Datensatzgruppe neue TXT-Einträge hinzufügen. Jeder Versuch, TXT-Einträge als getrennte Einträge einzugeben, führt zu einer Fehlermeldung wegen eines **doppelten Datensatzes**.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Wählen Sie bearbeiten in der Zeile TXT-Eintrag aus.](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="d5d9e-253">Wählen Sie das Steuerelement **(+)** aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-253">Select the **(+)** control.</span></span> 
    
    ![Wählen Sie das Plus-Steuerelement](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="d5d9e-255">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-255">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d5d9e-256">(Möglicherweise müssen Sie nach unten scrollen.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-256">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d5d9e-257">**Data**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-257">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="d5d9e-258">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d5d9e-258">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="d5d9e-259">Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-259">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="d5d9e-261">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-261">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="d5d9e-263">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="d5d9e-263">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="d5d9e-264"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d5d9e-264"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d5d9e-p115">Im ersten Schritt navigieren Sie über [diesen Link](https://domains.google.com/registrar) zu Ihrer Domänenseite bei Google Domains. Sie werden aufgefordert, sich anzumelden. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="d5d9e-268">Wählen Sie **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-268">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="d5d9e-269">Geben Sie Ihre Anmeldeinformationen ein, und wählen Sie dann erneut **Anmelden**aus.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-269">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="d5d9e-270">Wählen Sie auf der Seite **Domänen** im Abschnitt **Domäne** die Option **DNS** für die Domäne konfigurieren aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-270">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="d5d9e-271">Fügen Sie den ersten SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-271">Add the first SRV record.</span></span>
    
    <span data-ttu-id="d5d9e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-272">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d5d9e-273">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-273">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="d5d9e-274">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d5d9e-274">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="d5d9e-275">**Name**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-275">**Name**</span></span>|<span data-ttu-id="d5d9e-276">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-276">**Type**</span></span>|<span data-ttu-id="d5d9e-277">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-277">**TTL**</span></span>|<span data-ttu-id="d5d9e-278">**Daten**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-278">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d5d9e-279">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d5d9e-279">_sip._tls</span></span>|<span data-ttu-id="d5d9e-280">SRV</span><span class="sxs-lookup"><span data-stu-id="d5d9e-280">SRV</span></span>|<span data-ttu-id="d5d9e-281">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-281">1H</span></span>|<span data-ttu-id="d5d9e-282">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-282">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="d5d9e-283">**Dieser Wert muss mit einem Punkt (.) enden.** **Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit der gesamte Abstand korrekt bleibt.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-283">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="d5d9e-284">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d5d9e-284">_sipfederationtls._tcp</span></span>|<span data-ttu-id="d5d9e-285">SRV</span><span class="sxs-lookup"><span data-stu-id="d5d9e-285">SRV</span></span>|<span data-ttu-id="d5d9e-286">1H</span><span class="sxs-lookup"><span data-stu-id="d5d9e-286">1H</span></span>|<span data-ttu-id="d5d9e-287">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-287">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="d5d9e-288">**Dieser Wert MUSS mit einem Punkt (.) enden.**</span><span class="sxs-lookup"><span data-stu-id="d5d9e-288">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="d5d9e-289">Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-289">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Eingeben oder Einfügen von Werten im Abschnitt benutzerdefinierte Ressourceneinträge](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="d5d9e-291">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-291">Select **Add**.</span></span>
    
    ![Wählen Sie hinzufügen aus.](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="d5d9e-293">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-293">Add the other SRV record.</span></span>
    
    <span data-ttu-id="d5d9e-294">Erstellen Sie im Abschnitt **benutzerdefinierte Ressourceneinträge** einen Datensatz mithilfe der Werte aus der zweiten Zeile in der Tabelle, und wählen Sie dann erneut **Hinzufügen** aus, um diesen Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d5d9e-294">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d5d9e-p118">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d5d9e-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
