---
title: Erstellen von DNS-Einträgen für Azure DNS-Zonen
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
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste bei Azure DNS-Zonen für Microsoft einrichten.
ms.openlocfilehash: c276570ec1d5ff079348bd8202ea597ef61e88f6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656867"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="e61ae-103">Erstellen von DNS-Einträgen für Azure DNS-Zonen</span><span class="sxs-lookup"><span data-stu-id="e61ae-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="e61ae-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e61ae-105">Wenn Azure Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="e61ae-106">Dies sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="e61ae-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="e61ae-107">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="e61ae-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="e61ae-108">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e61ae-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="e61ae-109">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Microsoft geleitet werden</span><span class="sxs-lookup"><span data-stu-id="e61ae-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="e61ae-110">Hinzufügen der vier für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="e61ae-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="e61ae-111">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="e61ae-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="e61ae-112">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="e61ae-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="e61ae-113">Nachdem Sie diese Einträge bei Azure hinzugefügt haben, ist Ihre Domäne für die Verwendung von Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="e61ae-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e61ae-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e61ae-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e61ae-117">Ändern der Nameservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="e61ae-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="e61ae-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="e61ae-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e61ae-119">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="e61ae-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="e61ae-120">Bei Ihrer Anmeldung für Azure haben Sie eine Ressourcengruppe innerhalb einer DNS-Zone erstellt und dann dieser Ressourcengruppe Ihren Domänennamen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="e61ae-121">Dieser Domänenname ist bei einer externen Domänenregistrierungsstelle registriert. Azure bietet keine Domänenregistrierungsdienste an.</span><span class="sxs-lookup"><span data-stu-id="e61ae-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="e61ae-122">Um DNS-Einträge für Ihre Domäne bei Microsoft zu überprüfen und zu erstellen, müssen Sie zuerst die Nameserver bei Ihrer Domänenregistrierungsstelle so ändern, dass sie die Ihrer Ressourcengruppe zugeordneten Azure-Nameserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="e61ae-123">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e61ae-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="e61ae-124">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="e61ae-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="e61ae-125">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="e61ae-126">Ein Beispiel für von Azure zugewiesene Nameserver ist unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e61ae-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="e61ae-127">**Erster Nameserver:** Verwenden Sie den von Azure zugewiesenen Nameserverwert.</span><span class="sxs-lookup"><span data-stu-id="e61ae-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="e61ae-128">**Zweiter Nameserver:** Verwenden Sie den von Azure zugewiesenen Nameserverwert.</span><span class="sxs-lookup"><span data-stu-id="e61ae-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="e61ae-130">Verwenden Sie mindestens zwei Nameservereinträge.</span><span class="sxs-lookup"><span data-stu-id="e61ae-130">You should use at least two name server records.</span></span> <span data-ttu-id="e61ae-131">Wenn auf der Website Ihrer Domänenregistrierungsstelle weitere Nameserver aufgeführt sind, sollten Sie diese löschen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="e61ae-132">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e61ae-133">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e61ae-134">Dann sind Ihre Microsoft-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="e61ae-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e61ae-135">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="e61ae-135">Add a TXT record for verification</span></span>
<span data-ttu-id="e61ae-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="e61ae-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="e61ae-p106">Bevor Sie Ihre Domäne mit Microsoft verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="e61ae-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e61ae-p107">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e61ae-141">Navigieren Sie im ersten Schritt über [diesen Link](https://portal.azure.com ) zu Ihrer Domänenseite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="e61ae-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e61ae-142">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e61ae-144">Geben Sie in der **Suchleiste** auf der Seite **Dashboard** den Begriff **DNS-Zonen** ein.</span><span class="sxs-lookup"><span data-stu-id="e61ae-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="e61ae-145">Wählen Sie in der Ergebnisanzeige im Abschnitt **Dienste** die Option **DNS-Zonen** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="e61ae-146">Sobald Sie umgeleitet wurden, wählen Sie die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e61ae-148">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e61ae-150">Wählen Sie im Bereich **Recordset hinzufügen** in den Feldern für das neue Recordset die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e61ae-151">(Wählen Sie in der Dropdownliste die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="e61ae-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e61ae-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="e61ae-152">**Name**</span></span>|<span data-ttu-id="e61ae-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="e61ae-153">**Type**</span></span>|<span data-ttu-id="e61ae-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e61ae-154">**TTL**</span></span>|<span data-ttu-id="e61ae-155">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="e61ae-155">**TTL unit**</span></span>|<span data-ttu-id="e61ae-156">**Wert**</span><span class="sxs-lookup"><span data-stu-id="e61ae-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e61ae-157">TXT</span><span class="sxs-lookup"><span data-stu-id="e61ae-157">TXT</span></span>  <br/> |<span data-ttu-id="e61ae-158">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-158">1</span></span>  <br/> |<span data-ttu-id="e61ae-159">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-159">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e61ae-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="e61ae-161">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e61ae-161">**Note:** This is an example.</span></span> <span data-ttu-id="e61ae-162">Verwenden Sie hier Ihren spezifischen „Ziel“- oder **Verweist auf die Adresse**-Wert aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e61ae-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="e61ae-163">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="e61ae-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="e61ae-165">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="e61ae-166">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e61ae-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e61ae-167">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft zurück und fordern Sie den Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="e61ae-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="e61ae-168">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="e61ae-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e61ae-169">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="e61ae-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="e61ae-170">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="e61ae-171">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="e61ae-172">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="e61ae-p111">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e61ae-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="e61ae-176">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="e61ae-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="e61ae-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="e61ae-178">Navigieren Sie im ersten Schritt über [diesen Link](https://portal.azure.com ) zu Ihrer Domänenseite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="e61ae-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e61ae-179">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e61ae-181">Wählen Sie auf der Seite **Dashboard** im Bereich **Alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e61ae-183">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e61ae-185">Wählen Sie im Bereich **Recordset hinzufügen** in den Feldern für das neue Recordset die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e61ae-186">(Wählen Sie in der Dropdownliste die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="e61ae-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e61ae-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="e61ae-187">**Name**</span></span>|<span data-ttu-id="e61ae-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="e61ae-188">**Type**</span></span>|<span data-ttu-id="e61ae-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e61ae-189">**TTL**</span></span>|<span data-ttu-id="e61ae-190">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="e61ae-190">**TTL unit**</span></span>|<span data-ttu-id="e61ae-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="e61ae-191">**Preference**</span></span>|<span data-ttu-id="e61ae-192">**Mail Exchange**</span><span class="sxs-lookup"><span data-stu-id="e61ae-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e61ae-193">MX</span><span class="sxs-lookup"><span data-stu-id="e61ae-193">MX</span></span>  <br/> |<span data-ttu-id="e61ae-194">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-194">1</span></span>  <br/> |<span data-ttu-id="e61ae-195">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-195">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-196">10</span><span class="sxs-lookup"><span data-stu-id="e61ae-196">10</span></span>  <br/> <span data-ttu-id="e61ae-197">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="e61ae-197">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="e61ae-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="e61ae-199">**Hinweis:** Erhalten Sie Ihren *\<domain-key\>* über Ihr Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="e61ae-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="e61ae-200">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="e61ae-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="e61ae-202">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="e61ae-204">Wenn im Abschnitt **MX Records** andere MX-Einträge aufgeführt sind, müssen Sie diese löschen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="e61ae-205">Wählen Sie zunächst im Bereich **DNS-Zone** das **MX-Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="e61ae-207">Wählen Sie als nächstes das MX-Recordset aus, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="e61ae-209">Wählen Sie das **Kontextmenü (...)** und dann **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="e61ae-211">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="e61ae-213">Hinzufügen der vier für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="e61ae-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="e61ae-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e61ae-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="e61ae-215">Navigieren Sie im ersten Schritt über [diesen Link](https://portal.azure.com ) zu Ihrer Domänenseite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="e61ae-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e61ae-216">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e61ae-218">Wählen Sie auf der Seite **Dashboard** im Bereich **Alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e61ae-220">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e61ae-222">Fügen Sie den ersten der vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e61ae-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="e61ae-223">Geben Sie im Bereich **Recordset hinzufügen** in den Feldern für das neue Recordset die Werte aus der ersten Zeile der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e61ae-224">(Wählen Sie in der Dropdownliste die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="e61ae-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e61ae-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="e61ae-225">**Name**</span></span>|<span data-ttu-id="e61ae-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="e61ae-226">**Type**</span></span>|<span data-ttu-id="e61ae-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e61ae-227">**TTL**</span></span>|<span data-ttu-id="e61ae-228">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="e61ae-228">**TTL unit**</span></span>|<span data-ttu-id="e61ae-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e61ae-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e61ae-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e61ae-230">autodiscover</span></span>  <br/> |<span data-ttu-id="e61ae-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="e61ae-231">CNAME</span></span>  <br/> |<span data-ttu-id="e61ae-232">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-232">1</span></span>  <br/> |<span data-ttu-id="e61ae-233">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-233">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="e61ae-235">sip</span><span class="sxs-lookup"><span data-stu-id="e61ae-235">sip</span></span>  <br/> |<span data-ttu-id="e61ae-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="e61ae-236">CNAME</span></span>  <br/> |<span data-ttu-id="e61ae-237">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-237">1</span></span>  <br/> |<span data-ttu-id="e61ae-238">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-238">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e61ae-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e61ae-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="e61ae-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="e61ae-241">CNAME</span></span>  <br/> |<span data-ttu-id="e61ae-242">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-242">1</span></span>  <br/> |<span data-ttu-id="e61ae-243">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-243">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="e61ae-246">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="e61ae-248">Fügen Sie die drei anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e61ae-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="e61ae-249">Wählen Sie im Bereich **DNS-Zone** die Option **+ Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="e61ae-250">Erstellen Sie dann im leeren Recordset einen Eintrag mit den Werten aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **OK** aus, um diesen Eintrag abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="e61ae-251">Wiederholen Sie diesen Vorgang, bis Sie alle vier CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e61ae-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="e61ae-252">(Optional) Fügen Sie 2 CNAME-Einträge für MDM hinzu.</span><span class="sxs-lookup"><span data-stu-id="e61ae-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e61ae-253">Wenn Sie über MDM (Mobile Device Management) für Microsoft verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="e61ae-254">Folgen Sie den Schritten für die anderen vier CNAME-Einträge, geben Sie jedoch die Werte aus der nachstehenden Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="e61ae-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="e61ae-255">(Wenn Sie nicht mit MDM arbeiten, können Sie diesen Schritt überspringen.)</span><span class="sxs-lookup"><span data-stu-id="e61ae-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="e61ae-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="e61ae-256">**Name**</span></span>|<span data-ttu-id="e61ae-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="e61ae-257">**Type**</span></span>|<span data-ttu-id="e61ae-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e61ae-258">**TTL**</span></span>|<span data-ttu-id="e61ae-259">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="e61ae-259">**TTL unit**</span></span>|<span data-ttu-id="e61ae-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e61ae-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e61ae-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="e61ae-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="e61ae-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="e61ae-262">CNAME</span></span>  <br/> |<span data-ttu-id="e61ae-263">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-263">1</span></span>  <br/> |<span data-ttu-id="e61ae-264">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-264">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="e61ae-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="e61ae-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="e61ae-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="e61ae-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="e61ae-267">CNAME</span></span>  <br/> |<span data-ttu-id="e61ae-268">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-268">1</span></span>  <br/> |<span data-ttu-id="e61ae-269">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-269">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="e61ae-271">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="e61ae-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="e61ae-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="e61ae-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="e61ae-273">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="e61ae-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="e61ae-274">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="e61ae-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="e61ae-275">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="e61ae-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="e61ae-276">sondern fügen Sie die erforderlichen Microsoft-Werte dem aktuellen Eintrag hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e61ae-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="e61ae-277">Navigieren Sie im ersten Schritt über [diesen Link](https://portal.azure.com ) zu Ihrer Domänenseite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="e61ae-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e61ae-278">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e61ae-280">Wählen Sie auf der Seite **Dashboard** im Bereich **Alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e61ae-282">Wählen Sie im Bereich **DNS-Zone** das **TXT-Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="e61ae-284">Wählen Sie im Bereich **Recordseteigenschaften** in den Feldern für das neue Recordset die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="e61ae-285">(Wählen Sie in der Dropdownliste die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="e61ae-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e61ae-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="e61ae-286">**Name**</span></span>|<span data-ttu-id="e61ae-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="e61ae-287">**Type**</span></span>|<span data-ttu-id="e61ae-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e61ae-288">**TTL**</span></span>|<span data-ttu-id="e61ae-289">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="e61ae-289">**TTL unit**</span></span>|<span data-ttu-id="e61ae-290">**Wert**</span><span class="sxs-lookup"><span data-stu-id="e61ae-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="e61ae-291">TXT</span><span class="sxs-lookup"><span data-stu-id="e61ae-291">TXT</span></span>  <br/> |<span data-ttu-id="e61ae-292">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-292">1</span></span>  <br/> |<span data-ttu-id="e61ae-293">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-293">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="e61ae-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="e61ae-295">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="e61ae-297">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="e61ae-299">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="e61ae-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="e61ae-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="e61ae-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="e61ae-301">Navigieren Sie im ersten Schritt über [diesen Link](https://portal.azure.com ) zu Ihrer Domänenseite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="e61ae-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="e61ae-302">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="e61ae-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="e61ae-304">Wählen Sie auf der Seite **Dashboard** im Bereich **Alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e61ae-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="e61ae-306">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Recordset** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="e61ae-308">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="e61ae-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="e61ae-309">Wählen Sie im Bereich **Recordset hinzufügen** in den Feldern für das neue Recordset die Werte aus der ersten Zeile der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="e61ae-310">(Wählen Sie in der Dropdownliste die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="e61ae-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="e61ae-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="e61ae-311">**Name**</span></span>|<span data-ttu-id="e61ae-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="e61ae-312">**Type**</span></span>|<span data-ttu-id="e61ae-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e61ae-313">**TTL**</span></span>|<span data-ttu-id="e61ae-314">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="e61ae-314">**TTL unit**</span></span>|<span data-ttu-id="e61ae-315">**Priority**</span><span class="sxs-lookup"><span data-stu-id="e61ae-315">**Priority**</span></span>|<span data-ttu-id="e61ae-316">**Weight**</span><span class="sxs-lookup"><span data-stu-id="e61ae-316">**Weight**</span></span>|<span data-ttu-id="e61ae-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="e61ae-317">**Port**</span></span>|<span data-ttu-id="e61ae-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="e61ae-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="e61ae-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="e61ae-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="e61ae-320">SRV</span><span class="sxs-lookup"><span data-stu-id="e61ae-320">SRV</span></span>  <br/> |<span data-ttu-id="e61ae-321">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-321">1</span></span>  <br/> |<span data-ttu-id="e61ae-322">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-322">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-323">100</span><span class="sxs-lookup"><span data-stu-id="e61ae-323">100</span></span>  <br/> |<span data-ttu-id="e61ae-324">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-324">1</span></span>  <br/> |<span data-ttu-id="e61ae-325">443</span><span class="sxs-lookup"><span data-stu-id="e61ae-325">443</span></span>  <br/> |<span data-ttu-id="e61ae-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="e61ae-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="e61ae-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="e61ae-328">SRV</span><span class="sxs-lookup"><span data-stu-id="e61ae-328">SRV</span></span>  <br/> |<span data-ttu-id="e61ae-329">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-329">1</span></span>  <br/> |<span data-ttu-id="e61ae-330">Stunden</span><span class="sxs-lookup"><span data-stu-id="e61ae-330">Hours</span></span>  <br/> |<span data-ttu-id="e61ae-331">100</span><span class="sxs-lookup"><span data-stu-id="e61ae-331">100</span></span>  <br/> |<span data-ttu-id="e61ae-332">1</span><span class="sxs-lookup"><span data-stu-id="e61ae-332">1</span></span>  <br/> |<span data-ttu-id="e61ae-333">5061</span><span class="sxs-lookup"><span data-stu-id="e61ae-333">5061</span></span>  <br/> |<span data-ttu-id="e61ae-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="e61ae-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="e61ae-336">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e61ae-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="e61ae-338">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="e61ae-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="e61ae-339">Geben Sie in den Feldern für den neuen Eintrag die Werte aus der zweiten Zeile der Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="e61ae-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e61ae-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e61ae-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
