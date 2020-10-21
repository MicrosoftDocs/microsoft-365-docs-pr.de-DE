---
title: Erstellen von DNS-Einträgen für Azure-DNS-Zonen
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste in Azure-DNS-Zonen für Microsoft einrichten.
ms.openlocfilehash: 40fadb81ebd0ae5385bbbdad727b1c579142b227
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645671"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="37018-103">Erstellen von DNS-Einträgen für Azure-DNS-Zonen</span><span class="sxs-lookup"><span data-stu-id="37018-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="37018-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="37018-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="37018-105">Wenn Azure Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten.</span><span class="sxs-lookup"><span data-stu-id="37018-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="37018-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="37018-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="37018-107">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="37018-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="37018-108">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="37018-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="37018-109">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37018-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="37018-110">Hinzufügen der vier für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="37018-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="37018-111">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="37018-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="37018-112">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="37018-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="37018-113">Nachdem Sie diese Einträge bei Azure hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="37018-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37018-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="37018-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="37018-117">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="37018-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="37018-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="37018-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="37018-119">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="37018-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="37018-120">Wenn Sie sich für Azure angemeldet haben, haben Sie eine Ressourcengruppe innerhalb einer DNS-Zone erstellt und anschließend Ihren Domänennamen dieser Ressourcengruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="37018-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="37018-121">Dieser Domänenname ist für eine externe Domänenregistrierungsstelle registriert; Azure bietet keine Domänenregistrierungsdienste an.</span><span class="sxs-lookup"><span data-stu-id="37018-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="37018-122">Um DNS-Einträge für Ihre Domäne in Microsoft zu überprüfen und zu erstellen, müssen Sie zuerst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Azure-Namenserver verwenden, die ihrer Ressourcengruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="37018-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="37018-123">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="37018-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="37018-124">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="37018-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="37018-125">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="37018-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="37018-126">Unten sehen Sie ein Beispiel für Azure zugewiesene Namenserver.</span><span class="sxs-lookup"><span data-stu-id="37018-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="37018-127">**Erster Nameserver:** Verwenden Sie den Namenserver Wert, der von Azure zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="37018-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="37018-128">**Zweiter Nameserver:** Verwenden Sie den Namenserver Wert, der von Azure zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="37018-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="37018-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="37018-130">You should use at least two name server records.</span></span> <span data-ttu-id="37018-131">Wenn auf der Website Ihrer Domänenregistrierungsstelle andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="37018-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="37018-132">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="37018-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="37018-133">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="37018-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="37018-134">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37018-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="37018-135">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="37018-135">Add a TXT record for verification</span></span>
<span data-ttu-id="37018-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="37018-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="37018-p106">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="37018-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37018-p107">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="37018-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="37018-141">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="37018-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="37018-142">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="37018-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="37018-144">Geben Sie über die **Suchleiste** auf der **Dashboardseite** die Zeichen in **DNS-Zonen**ein.</span><span class="sxs-lookup"><span data-stu-id="37018-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="37018-145">Wählen Sie in der Ergebnisanzeige **DNS-Zonen** unter dem Abschnitt **Dienste** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="37018-146">Nachdem Sie umgeleitet wurden, wählen Sie die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="37018-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="37018-148">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="37018-150">Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="37018-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="37018-151">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="37018-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="37018-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="37018-152">**Name**</span></span>|<span data-ttu-id="37018-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="37018-153">**Type**</span></span>|<span data-ttu-id="37018-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="37018-154">**TTL**</span></span>|<span data-ttu-id="37018-155">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="37018-155">**TTL unit**</span></span>|<span data-ttu-id="37018-156">**Wert**</span><span class="sxs-lookup"><span data-stu-id="37018-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="37018-157">TXT</span><span class="sxs-lookup"><span data-stu-id="37018-157">TXT</span></span>  <br/> |<span data-ttu-id="37018-158">1</span><span class="sxs-lookup"><span data-stu-id="37018-158">1</span></span>  <br/> |<span data-ttu-id="37018-159">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-159">Hours</span></span>  <br/> |<span data-ttu-id="37018-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="37018-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="37018-161">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="37018-161">**Note:** This is an example.</span></span> <span data-ttu-id="37018-162">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="37018-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="37018-163">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="37018-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="37018-165">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="37018-166">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="37018-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="37018-167">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="37018-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="37018-168">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="37018-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="37018-169">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="37018-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="37018-170">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="37018-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="37018-171">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="37018-172">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="37018-p111">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="37018-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="37018-176">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37018-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="37018-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="37018-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="37018-178">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="37018-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="37018-179">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="37018-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="37018-181">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="37018-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="37018-183">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="37018-185">Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="37018-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="37018-186">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="37018-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="37018-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="37018-187">**Name**</span></span>|<span data-ttu-id="37018-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="37018-188">**Type**</span></span>|<span data-ttu-id="37018-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="37018-189">**TTL**</span></span>|<span data-ttu-id="37018-190">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="37018-190">**TTL unit**</span></span>|<span data-ttu-id="37018-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="37018-191">**Preference**</span></span>|<span data-ttu-id="37018-192">**E-Mail-Austausch**</span><span class="sxs-lookup"><span data-stu-id="37018-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="37018-193">MX</span><span class="sxs-lookup"><span data-stu-id="37018-193">MX</span></span>  <br/> |<span data-ttu-id="37018-194">1</span><span class="sxs-lookup"><span data-stu-id="37018-194">1</span></span>  <br/> |<span data-ttu-id="37018-195">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-195">Hours</span></span>  <br/> |<span data-ttu-id="37018-196">10 </span><span class="sxs-lookup"><span data-stu-id="37018-196">10</span></span>  <br/> <span data-ttu-id="37018-197">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="37018-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="37018-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="37018-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="37018-199">**Hinweis:** Holen Sie sich Ihr  *\<domain-key\>*  Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="37018-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="37018-200">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="37018-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="37018-202">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-202">Select **OK**.</span></span>
    
    ![Azure-BP-configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="37018-204">Wenn im Abschnitt **MX Records** weitere MX-Einträge aufgeführt sind, müssen Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="37018-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="37018-205">Wählen Sie zuerst im Bereich **DNS-Zone** den **MX-Eintragssatz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="37018-207">Wählen Sie als nächstes den MX-Eintrag aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="37018-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="37018-209">Wählen Sie das **Kontextmenü (...)** aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="37018-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="37018-211">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37018-211">Select **Save**.</span></span>
    
    ![Azure-BP-configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="37018-213">Hinzufügen der vier für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="37018-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="37018-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="37018-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="37018-215">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="37018-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="37018-216">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="37018-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="37018-218">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="37018-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="37018-220">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="37018-222">Fügen Sie den ersten der vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="37018-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="37018-223">Geben Sie im Bereich Daten Satz Satz hinzufügen in den Feldern für den neuen Daten Satz Satz die Werte aus der ersten Zeile in der folgenden Tabelle ein, oder kopieren und fügen **Sie Sie** ein.</span><span class="sxs-lookup"><span data-stu-id="37018-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="37018-224">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="37018-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="37018-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="37018-225">**Name**</span></span>|<span data-ttu-id="37018-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="37018-226">**Type**</span></span>|<span data-ttu-id="37018-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="37018-227">**TTL**</span></span>|<span data-ttu-id="37018-228">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="37018-228">**TTL unit**</span></span>|<span data-ttu-id="37018-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="37018-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="37018-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="37018-230">autodiscover</span></span>  <br/> |<span data-ttu-id="37018-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="37018-231">CNAME</span></span>  <br/> |<span data-ttu-id="37018-232">1</span><span class="sxs-lookup"><span data-stu-id="37018-232">1</span></span>  <br/> |<span data-ttu-id="37018-233">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-233">Hours</span></span>  <br/> |<span data-ttu-id="37018-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="37018-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="37018-235">sip</span><span class="sxs-lookup"><span data-stu-id="37018-235">sip</span></span>  <br/> |<span data-ttu-id="37018-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="37018-236">CNAME</span></span>  <br/> |<span data-ttu-id="37018-237">1</span><span class="sxs-lookup"><span data-stu-id="37018-237">1</span></span>  <br/> |<span data-ttu-id="37018-238">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-238">Hours</span></span>  <br/> |<span data-ttu-id="37018-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37018-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="37018-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="37018-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="37018-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="37018-241">CNAME</span></span>  <br/> |<span data-ttu-id="37018-242">1</span><span class="sxs-lookup"><span data-stu-id="37018-242">1</span></span>  <br/> |<span data-ttu-id="37018-243">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-243">Hours</span></span>  <br/> |<span data-ttu-id="37018-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37018-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="37018-246">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-246">Select **OK**.</span></span>
    
    ![Azure-BP-configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="37018-248">Fügen Sie die drei anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="37018-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="37018-249">Wählen Sie im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="37018-250">Erstellen Sie dann im leeren Daten Satz Satz einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **OK** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="37018-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="37018-251">Wiederholen Sie diesen Vorgang, bis Sie alle vier CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="37018-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="37018-252">Optional Fügen Sie zwei CNAME-Einträge für MDM hinzu.</span><span class="sxs-lookup"><span data-stu-id="37018-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37018-253">Wenn Sie über die Mobile Geräteverwaltung (MDM) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="37018-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="37018-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="37018-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="37018-255">(Wenn Sie nicht über MDM verfügen, können Sie diesen Schritt überspringen.)</span><span class="sxs-lookup"><span data-stu-id="37018-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="37018-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="37018-256">**Name**</span></span>|<span data-ttu-id="37018-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="37018-257">**Type**</span></span>|<span data-ttu-id="37018-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="37018-258">**TTL**</span></span>|<span data-ttu-id="37018-259">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="37018-259">**TTL unit**</span></span>|<span data-ttu-id="37018-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="37018-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="37018-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="37018-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="37018-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="37018-262">CNAME</span></span>  <br/> |<span data-ttu-id="37018-263">1</span><span class="sxs-lookup"><span data-stu-id="37018-263">1</span></span>  <br/> |<span data-ttu-id="37018-264">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-264">Hours</span></span>  <br/> |<span data-ttu-id="37018-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="37018-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="37018-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="37018-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="37018-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="37018-267">CNAME</span></span>  <br/> |<span data-ttu-id="37018-268">1</span><span class="sxs-lookup"><span data-stu-id="37018-268">1</span></span>  <br/> |<span data-ttu-id="37018-269">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-269">Hours</span></span>  <br/> |<span data-ttu-id="37018-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="37018-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="37018-271">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="37018-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="37018-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="37018-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="37018-273">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="37018-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="37018-274">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="37018-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="37018-275">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="37018-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="37018-276">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen  *einzelnen*  SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="37018-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="37018-277">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="37018-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="37018-278">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="37018-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="37018-280">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="37018-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="37018-282">Wählen Sie im Bereich **DNS-Zone** den **txt-Eintragssatz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="37018-284">Wählen Sie im Bereich **Eigenschaften von Datensatzgruppe** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="37018-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="37018-285">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="37018-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="37018-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="37018-286">**Name**</span></span>|<span data-ttu-id="37018-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="37018-287">**Type**</span></span>|<span data-ttu-id="37018-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="37018-288">**TTL**</span></span>|<span data-ttu-id="37018-289">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="37018-289">**TTL unit**</span></span>|<span data-ttu-id="37018-290">**Wert**</span><span class="sxs-lookup"><span data-stu-id="37018-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="37018-291">TXT</span><span class="sxs-lookup"><span data-stu-id="37018-291">TXT</span></span>  <br/> |<span data-ttu-id="37018-292">1</span><span class="sxs-lookup"><span data-stu-id="37018-292">1</span></span>  <br/> |<span data-ttu-id="37018-293">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-293">Hours</span></span>  <br/> |<span data-ttu-id="37018-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="37018-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="37018-295">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="37018-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="37018-297">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37018-297">Select **Save**.</span></span>
    
    ![Azure-BP-configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="37018-299">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="37018-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="37018-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="37018-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="37018-301">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="37018-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="37018-302">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="37018-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="37018-304">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="37018-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="37018-306">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="37018-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="37018-308">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="37018-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="37018-309">Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der ersten Zeile in der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="37018-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="37018-310">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="37018-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="37018-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="37018-311">**Name**</span></span>|<span data-ttu-id="37018-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="37018-312">**Type**</span></span>|<span data-ttu-id="37018-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="37018-313">**TTL**</span></span>|<span data-ttu-id="37018-314">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="37018-314">**TTL unit**</span></span>|<span data-ttu-id="37018-315">**Priority**</span><span class="sxs-lookup"><span data-stu-id="37018-315">**Priority**</span></span>|<span data-ttu-id="37018-316">**Weight**</span><span class="sxs-lookup"><span data-stu-id="37018-316">**Weight**</span></span>|<span data-ttu-id="37018-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="37018-317">**Port**</span></span>|<span data-ttu-id="37018-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="37018-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="37018-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="37018-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="37018-320">SRV</span><span class="sxs-lookup"><span data-stu-id="37018-320">SRV</span></span>  <br/> |<span data-ttu-id="37018-321">1</span><span class="sxs-lookup"><span data-stu-id="37018-321">1</span></span>  <br/> |<span data-ttu-id="37018-322">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-322">Hours</span></span>  <br/> |<span data-ttu-id="37018-323">100</span><span class="sxs-lookup"><span data-stu-id="37018-323">100</span></span>  <br/> |<span data-ttu-id="37018-324">1</span><span class="sxs-lookup"><span data-stu-id="37018-324">1</span></span>  <br/> |<span data-ttu-id="37018-325">443</span><span class="sxs-lookup"><span data-stu-id="37018-325">443</span></span>  <br/> |<span data-ttu-id="37018-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37018-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="37018-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="37018-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="37018-328">SRV</span><span class="sxs-lookup"><span data-stu-id="37018-328">SRV</span></span>  <br/> |<span data-ttu-id="37018-329">1</span><span class="sxs-lookup"><span data-stu-id="37018-329">1</span></span>  <br/> |<span data-ttu-id="37018-330">Stunden</span><span class="sxs-lookup"><span data-stu-id="37018-330">Hours</span></span>  <br/> |<span data-ttu-id="37018-331">100</span><span class="sxs-lookup"><span data-stu-id="37018-331">100</span></span>  <br/> |<span data-ttu-id="37018-332">1</span><span class="sxs-lookup"><span data-stu-id="37018-332">1</span></span>  <br/> |<span data-ttu-id="37018-333">5061</span><span class="sxs-lookup"><span data-stu-id="37018-333">5061</span></span>  <br/> |<span data-ttu-id="37018-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37018-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="37018-336">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="37018-336">Select **OK**.</span></span>
    
    ![Azure-BP-configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="37018-338">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="37018-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="37018-339">Geben Sie in den Feldern für den neuen Datensatz die Werte aus der zweiten Zeile der Tabelle ein, oder kopieren Sie Sie, und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="37018-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="37018-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="37018-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
