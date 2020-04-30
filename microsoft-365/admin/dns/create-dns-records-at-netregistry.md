---
title: Erstellen von DNS-Einträgen bei Netregistry für Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste bei Netregistry für Microsoft einrichten.
ms.openlocfilehash: ed3e3bae232dcbb3c8e4eea3d1a3bc4dd0a88799
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939155"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="ae430-103">Erstellen von DNS-Einträgen bei Netregistry für Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae430-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="ae430-104">[] [Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md) , wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ae430-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ae430-105">Wenn Netregistry Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ae430-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ae430-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="ae430-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="ae430-107">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ae430-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="ae430-108">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae430-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="ae430-109">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="ae430-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ae430-110">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="ae430-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ae430-111">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="ae430-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ae430-112">Nachdem Sie diese Einträge bei Netregistry hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ae430-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="ae430-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae430-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ae430-116">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="ae430-116">Add a TXT record for verification</span></span>
<span data-ttu-id="ae430-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ae430-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="ae430-p102">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="ae430-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae430-p103">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="ae430-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ae430-p104">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ae430-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="ae430-125">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="ae430-127">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="ae430-129">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **TXT-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="ae430-131">Sie müssen vor und nach dem Eintrag im Feld txt Anführungszeichen setzen.</span><span class="sxs-lookup"><span data-stu-id="ae430-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="ae430-132">Geben Sie im Formular **New TXT Record** (Neuer TXT-Eintrag) die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ae430-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ae430-133">**Name**</span><span class="sxs-lookup"><span data-stu-id="ae430-133">**Name**</span></span>|<span data-ttu-id="ae430-134">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="ae430-134">**TTL (SEC)**</span></span>|<span data-ttu-id="ae430-135">**TXT (Verweist auf die Adresse oder den Wert)**</span><span class="sxs-lookup"><span data-stu-id="ae430-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ae430-136">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="ae430-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="ae430-137">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-138">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="ae430-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="ae430-139">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ae430-139">**Note:** This is an example.</span></span> <span data-ttu-id="ae430-140">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ae430-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ae430-141">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ae430-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="ae430-143">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-143">Select **Add record**.</span></span>
    
<span data-ttu-id="ae430-144">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="ae430-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ae430-145">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="ae430-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ae430-146">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="ae430-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ae430-147">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ae430-148">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ae430-149">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ae430-p106">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae430-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ae430-153">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae430-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ae430-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ae430-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="ae430-p107">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ae430-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="ae430-158">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="ae430-160">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="ae430-162">Entfernen Sie unter **aktuelle Zoneneinträge**die standardmäßigen MX-Einträge, indem Sie neben jedem MX-Eintrag in der Liste **Entfernen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ae430-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="ae430-164">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **MX-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="ae430-166">Geben Sie im **neuen MX-Eintrags** Formular die Werte aus der folgenden Tabelle ein, oder kopieren und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="ae430-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ae430-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="ae430-167">**Name**</span></span>|<span data-ttu-id="ae430-168">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="ae430-168">**TTL (SEC)**</span></span>|<span data-ttu-id="ae430-169">**Exchange (verweist auf Adresse oder Wert)**</span><span class="sxs-lookup"><span data-stu-id="ae430-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="ae430-170">**Ist der Host vollständig qualifiziert?**</span><span class="sxs-lookup"><span data-stu-id="ae430-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="ae430-171">**Präferenz (Priorität)**</span><span class="sxs-lookup"><span data-stu-id="ae430-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae430-172">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="ae430-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="ae430-173">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="ae430-174">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ae430-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ae430-175">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* von Ihrem Microsoft-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="ae430-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="ae430-176">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="ae430-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="ae430-177">(aktivieren Sie das Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="ae430-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="ae430-178">10  </span><span class="sxs-lookup"><span data-stu-id="ae430-178">10</span></span>  <br/> <span data-ttu-id="ae430-179">Weitere Informationen zur Priorität finden Sie unter Was ist MX-Priorität?</span><span class="sxs-lookup"><span data-stu-id="ae430-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="ae430-181">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ae430-183">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="ae430-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ae430-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ae430-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="ae430-p109">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ae430-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="ae430-188">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="ae430-190">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="ae430-192">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **CNAME-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="ae430-194">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ae430-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ae430-195">**Name**</span><span class="sxs-lookup"><span data-stu-id="ae430-195">**Name**</span></span>|<span data-ttu-id="ae430-196">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ae430-196">**Type**</span></span>|<span data-ttu-id="ae430-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ae430-197">**TTL**</span></span>|<span data-ttu-id="ae430-198">**Host (Punkt-zu-oder Adresswert)**</span><span class="sxs-lookup"><span data-stu-id="ae430-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae430-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ae430-199">autodiscover</span></span>  <br/> |<span data-ttu-id="ae430-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae430-200">CNAME</span></span>  <br/> |<span data-ttu-id="ae430-201">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ae430-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ae430-203">sip</span><span class="sxs-lookup"><span data-stu-id="ae430-203">sip</span></span>  <br/> |<span data-ttu-id="ae430-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae430-204">CNAME</span></span>  <br/> |<span data-ttu-id="ae430-205">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae430-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ae430-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ae430-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ae430-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae430-208">CNAME</span></span>  <br/> |<span data-ttu-id="ae430-209">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae430-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ae430-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ae430-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ae430-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae430-212">CNAME</span></span>  <br/> |<span data-ttu-id="ae430-213">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ae430-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ae430-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ae430-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ae430-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="ae430-216">CNAME</span></span>  <br/> |<span data-ttu-id="ae430-217">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ae430-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="ae430-220">Wählen Sie **Add Record**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="ae430-222">Wiederholen Sie die vorherigen Schritte, um die anderen fünf CNAME-Einträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae430-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="ae430-223">Geben Sie für jeden Eintrag die Werte aus der nächsten Zeile der Tabelle oben in die Felder für diesen Eintrag ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ae430-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ae430-224">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="ae430-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ae430-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ae430-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae430-226">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="ae430-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ae430-227">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="ae430-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ae430-228">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="ae430-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ae430-229">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="ae430-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="ae430-p111">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ae430-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="ae430-233">Wählen Sie neben der Domäne, die Sie verwalten möchten, **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="ae430-235">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="ae430-237">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **TXT-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="ae430-239">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ae430-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ae430-240">Sie müssen vor und nach dem Eintrag im Feld txt Anführungszeichen setzen.</span><span class="sxs-lookup"><span data-stu-id="ae430-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="ae430-241">**Name**</span><span class="sxs-lookup"><span data-stu-id="ae430-241">**Name**</span></span>|<span data-ttu-id="ae430-242">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ae430-242">**Type**</span></span>|<span data-ttu-id="ae430-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ae430-243">**TTL**</span></span>|<span data-ttu-id="ae430-244">**TXT-Daten (Ziel)**</span><span class="sxs-lookup"><span data-stu-id="ae430-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae430-245">(leer lassen)</span><span class="sxs-lookup"><span data-stu-id="ae430-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="ae430-246">TXT</span><span class="sxs-lookup"><span data-stu-id="ae430-246">TXT</span></span>  <br/> |<span data-ttu-id="ae430-247">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-248">"v = spf1 include:SPF. Protection. Outlook. com-all"</span><span class="sxs-lookup"><span data-stu-id="ae430-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="ae430-249">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ae430-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="ae430-251">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ae430-253">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="ae430-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ae430-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ae430-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="ae430-p112">Um zu beginnen, navigieren Sie über [diesen Link](https://theconsole.netregistry.com.au/) zu Ihrer Domänenseite bei Netregistry. Sie werden aufgefordert, sich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ae430-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="ae430-258">Wählen Sie neben der Domäne, die Sie verwalten möchten, die Option **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="ae430-260">Wählen Sie **Zone Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="ae430-262">Wählen Sie unter **Zonen Eintrag hinzufügen**die Option **SRV-Eintrag** in der Liste aus, und wählen Sie dann **neuen Datensatz erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="ae430-264">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="ae430-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae430-265">Das Feld Name ist eine Kombination aus dem Dienst (beispielsweise _sip) und dem Protokoll (beispielsweise _tls).</span><span class="sxs-lookup"><span data-stu-id="ae430-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="ae430-266">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ae430-266">**Type**</span></span>|<span data-ttu-id="ae430-267">**Name**</span><span class="sxs-lookup"><span data-stu-id="ae430-267">**Name**</span></span>|<span data-ttu-id="ae430-268">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="ae430-268">**TTL (SEC)**</span></span>|<span data-ttu-id="ae430-269">**Priority**</span><span class="sxs-lookup"><span data-stu-id="ae430-269">**Priority**</span></span>|<span data-ttu-id="ae430-270">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ae430-270">**Weight**</span></span>|<span data-ttu-id="ae430-271">**Port**</span><span class="sxs-lookup"><span data-stu-id="ae430-271">**Port**</span></span>|<span data-ttu-id="ae430-272">**Target**</span><span class="sxs-lookup"><span data-stu-id="ae430-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ae430-273">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="ae430-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="ae430-274">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ae430-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="ae430-275">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-276">100</span><span class="sxs-lookup"><span data-stu-id="ae430-276">100</span></span>  <br/> |<span data-ttu-id="ae430-277">1</span><span class="sxs-lookup"><span data-stu-id="ae430-277">1</span></span>  <br/> |<span data-ttu-id="ae430-278">443</span><span class="sxs-lookup"><span data-stu-id="ae430-278">443</span></span>  <br/> |<span data-ttu-id="ae430-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae430-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ae430-280">SRV (Dienst)</span><span class="sxs-lookup"><span data-stu-id="ae430-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="ae430-281">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ae430-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ae430-282">3600 (Sekunden)</span><span class="sxs-lookup"><span data-stu-id="ae430-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ae430-283">100</span><span class="sxs-lookup"><span data-stu-id="ae430-283">100</span></span>  <br/> |<span data-ttu-id="ae430-284">1</span><span class="sxs-lookup"><span data-stu-id="ae430-284">1</span></span>  <br/> |<span data-ttu-id="ae430-285">5061</span><span class="sxs-lookup"><span data-stu-id="ae430-285">5061</span></span>  <br/> |<span data-ttu-id="ae430-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ae430-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="ae430-288">Wählen Sie **Add Record** (Eintrag hinzufügen) aus.</span><span class="sxs-lookup"><span data-stu-id="ae430-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="ae430-290">Wiederholen Sie die vorherigen Schritte, um den anderen SRV-Eintrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae430-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="ae430-291">Geben Sie die Werte aus der zweiten Zeile der Tabelle oben in die Felder für den zweiten Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="ae430-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ae430-p113">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ae430-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

