---
title: Erstellen von DNS-Einträgen bei Netregistry für Office 365
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei Netregistry für Office 365 einrichten.
ms.openlocfilehash: de4e16fa20f950edef8d30b4c6d02214e3753b9c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252609"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="57723-103">Erstellen von DNS-Einträgen bei Netregistry für Office 365</span><span class="sxs-lookup"><span data-stu-id="57723-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="57723-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="57723-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="57723-105">Wenn Netregistry Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="57723-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="57723-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="57723-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="57723-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="57723-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="57723-108">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="57723-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="57723-109">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="57723-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="57723-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="57723-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="57723-111">Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="57723-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="57723-112">Nachdem Sie diese Einträge bei Netregistry hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365 Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="57723-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="57723-113">Informationen zu Webhosting und DNS für Websites mit Office 365 finden Sie unter [Verwenden einer öffentlichen Website mit Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="57723-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="57723-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57723-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="57723-117">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="57723-117">Add a TXT record for verification</span></span>
<span data-ttu-id="57723-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="57723-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="57723-p102">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="57723-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57723-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="57723-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="57723-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57723-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="57723-126">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="57723-128">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="57723-130">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **TXT-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="57723-132">Sie müssen vor und nach dem Eintrag im Feld txt Anführungszeichen setzen.</span><span class="sxs-lookup"><span data-stu-id="57723-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="57723-133">Geben Sie im Formular **New TXT Record** (Neuer TXT-Eintrag) die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57723-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="57723-134">**Name**</span><span class="sxs-lookup"><span data-stu-id="57723-134">**Name**</span></span>|<span data-ttu-id="57723-135">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="57723-135">**TTL (SEC)**</span></span>|<span data-ttu-id="57723-136">**TXT (Verweist auf die Adresse oder den Wert)**</span><span class="sxs-lookup"><span data-stu-id="57723-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="57723-137">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="57723-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="57723-138">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-139">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="57723-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="57723-p105">**Hinweis:** Dies ist ein nur Beispiel. Verwenden Sie jeweils Ihren Wert für **die Zieladresse bzw. die Adresse, auf die verwiesen wird** aus der Tabelle in Office 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="57723-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>  |
       
    ![Netregistry_verificationTXTvalues](../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="57723-144">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-144">Select **Add record**.</span></span>
    
<span data-ttu-id="57723-145">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="57723-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="57723-146">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="57723-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="57723-147">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="57723-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="57723-148">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="57723-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="57723-149">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="57723-150">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="57723-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57723-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="57723-154">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="57723-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="57723-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="57723-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="57723-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57723-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="57723-159">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="57723-161">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="57723-163">Entfernen Sie unter **aktuelle Zoneneinträge**die standardmäßigen MX-Einträge, indem Sie neben jedem MX-Eintrag in der Liste **Entfernen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="57723-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="57723-165">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **MX-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="57723-167">Geben Sie im **neuen MX-Eintrags** Formular die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="57723-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="57723-168">**Name**</span><span class="sxs-lookup"><span data-stu-id="57723-168">**Name**</span></span>|<span data-ttu-id="57723-169">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="57723-169">**TTL (SEC)**</span></span>|<span data-ttu-id="57723-170">**Exchange (verweist auf Adresse oder Wert)**</span><span class="sxs-lookup"><span data-stu-id="57723-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="57723-171">**Ist der Host vollständig qualifiziert?**</span><span class="sxs-lookup"><span data-stu-id="57723-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="57723-172">**Präferenz (Priorität)**</span><span class="sxs-lookup"><span data-stu-id="57723-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57723-173">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="57723-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="57723-174">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="57723-175">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="57723-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="57723-176">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="57723-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="57723-177">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="57723-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="57723-178">(aktivieren Sie das Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="57723-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="57723-179">10 </span><span class="sxs-lookup"><span data-stu-id="57723-179">10</span></span>  <br/> <span data-ttu-id="57723-180">Weitere Informationen zur Priorität finden Sie unter Was ist MX-Priorität?</span><span class="sxs-lookup"><span data-stu-id="57723-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="57723-182">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="57723-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="57723-184">Hinzufügen der für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="57723-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="57723-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="57723-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="57723-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57723-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="57723-189">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="57723-191">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="57723-193">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **CNAME-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="57723-195">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57723-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="57723-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="57723-196">**Name**</span></span>|<span data-ttu-id="57723-197">**Typ**</span><span class="sxs-lookup"><span data-stu-id="57723-197">**Type**</span></span>|<span data-ttu-id="57723-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57723-198">**TTL**</span></span>|<span data-ttu-id="57723-199">**Host (Punkt-zu-oder Adresswert)**</span><span class="sxs-lookup"><span data-stu-id="57723-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57723-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="57723-200">autodiscover</span></span>  <br/> |<span data-ttu-id="57723-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="57723-201">CNAME</span></span>  <br/> |<span data-ttu-id="57723-202">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="57723-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="57723-204">sip</span><span class="sxs-lookup"><span data-stu-id="57723-204">sip</span></span>  <br/> |<span data-ttu-id="57723-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="57723-205">CNAME</span></span>  <br/> |<span data-ttu-id="57723-206">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57723-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57723-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="57723-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="57723-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="57723-209">CNAME</span></span>  <br/> |<span data-ttu-id="57723-210">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57723-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57723-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="57723-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="57723-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="57723-213">CNAME</span></span>  <br/> |<span data-ttu-id="57723-214">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="57723-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="57723-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="57723-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="57723-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="57723-217">CNAME</span></span>  <br/> |<span data-ttu-id="57723-218">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="57723-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="57723-221">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="57723-223">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57723-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="57723-224">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="57723-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="57723-225">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="57723-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="57723-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="57723-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="57723-227">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="57723-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="57723-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="57723-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="57723-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="57723-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="57723-230">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="57723-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="57723-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57723-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="57723-234">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="57723-236">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="57723-238">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **TXT-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="57723-240">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="57723-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="57723-241">Sie müssen vor und nach dem Eintrag im Feld txt Anführungszeichen setzen.</span><span class="sxs-lookup"><span data-stu-id="57723-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="57723-242">**Name**</span><span class="sxs-lookup"><span data-stu-id="57723-242">**Name**</span></span>|<span data-ttu-id="57723-243">**Typ**</span><span class="sxs-lookup"><span data-stu-id="57723-243">**Type**</span></span>|<span data-ttu-id="57723-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="57723-244">**TTL**</span></span>|<span data-ttu-id="57723-245">**TXT-Daten (Ziel)**</span><span class="sxs-lookup"><span data-stu-id="57723-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57723-246">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="57723-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="57723-247">TXT</span><span class="sxs-lookup"><span data-stu-id="57723-247">TXT</span></span>  <br/> |<span data-ttu-id="57723-248">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-249">"v = spf1 include:SPF. Protection. Outlook. com-all"</span><span class="sxs-lookup"><span data-stu-id="57723-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="57723-250">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="57723-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="57723-252">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="57723-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="57723-254">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="57723-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="57723-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="57723-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="57723-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="57723-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="57723-259">Wählen Sie neben der Domäne, die Sie verwalten möchten, die Option **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="57723-261">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="57723-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="57723-263">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **SRV-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="57723-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="57723-265">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="57723-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57723-266">Das Feld Name ist eine Kombination aus dem Dienst (beispielsweise _sip) und dem Protokoll (beispielsweise _tls).</span><span class="sxs-lookup"><span data-stu-id="57723-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="57723-267">**Typ**</span><span class="sxs-lookup"><span data-stu-id="57723-267">**Type**</span></span>|<span data-ttu-id="57723-268">**Name**</span><span class="sxs-lookup"><span data-stu-id="57723-268">**Name**</span></span>|<span data-ttu-id="57723-269">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="57723-269">**TTL (SEC)**</span></span>|<span data-ttu-id="57723-270">**Priority**</span><span class="sxs-lookup"><span data-stu-id="57723-270">**Priority**</span></span>|<span data-ttu-id="57723-271">**Weight**</span><span class="sxs-lookup"><span data-stu-id="57723-271">**Weight**</span></span>|<span data-ttu-id="57723-272">**Port**</span><span class="sxs-lookup"><span data-stu-id="57723-272">**Port**</span></span>|<span data-ttu-id="57723-273">**Target**</span><span class="sxs-lookup"><span data-stu-id="57723-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="57723-274">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="57723-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="57723-275">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="57723-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="57723-276">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-277">100</span><span class="sxs-lookup"><span data-stu-id="57723-277">100</span></span>  <br/> |<span data-ttu-id="57723-278">1</span><span class="sxs-lookup"><span data-stu-id="57723-278">1</span></span>  <br/> |<span data-ttu-id="57723-279">443</span><span class="sxs-lookup"><span data-stu-id="57723-279">443</span></span>  <br/> |<span data-ttu-id="57723-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57723-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="57723-281">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="57723-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="57723-282">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="57723-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="57723-283">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="57723-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="57723-284">100</span><span class="sxs-lookup"><span data-stu-id="57723-284">100</span></span>  <br/> |<span data-ttu-id="57723-285">1</span><span class="sxs-lookup"><span data-stu-id="57723-285">1</span></span>  <br/> |<span data-ttu-id="57723-286">5061</span><span class="sxs-lookup"><span data-stu-id="57723-286">5061</span></span>  <br/> |<span data-ttu-id="57723-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="57723-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="57723-289">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="57723-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="57723-291">Wiederholen Sie die vorherigen Schritte, um den anderen SRV-Eintrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57723-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="57723-292">Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="57723-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="57723-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="57723-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

