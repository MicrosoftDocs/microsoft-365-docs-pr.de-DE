---
title: Erstellen von DNS-Einträgen für Azure-DNS-Zonen
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste in Azure-DNS-Zonen für Office 365 einrichten.
ms.openlocfilehash: 30e54da8ffd51165b1cc0d2eb82d9d02eefdaf4d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362740"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="352f2-103">Erstellen von DNS-Einträgen für Azure-DNS-Zonen</span><span class="sxs-lookup"><span data-stu-id="352f2-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="352f2-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="352f2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="352f2-105">Wenn Azure Ihr DNS-Hostinganbieter ist, führen Sie die Schritte in diesem Artikel aus, um Ihre Domäne zu überprüfen und DNS-Einträge für e-Mail, Skype for Business Online usw. einzurichten.</span><span class="sxs-lookup"><span data-stu-id="352f2-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="352f2-106">Das sind die wichtigsten hinzuzufügenden Einträge.</span><span class="sxs-lookup"><span data-stu-id="352f2-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="352f2-107">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="352f2-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="352f2-108">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="352f2-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="352f2-109">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne an Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="352f2-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="352f2-110">Hinzufügen der vier für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="352f2-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="352f2-111">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="352f2-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="352f2-112">Hinzufügen der zwei für Office 365 erforderlichen SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="352f2-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="352f2-113">Nachdem Sie diese Einträge bei Azure hinzugefügt haben, ist Ihre Domäne für die Verwendung von Office 365 Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="352f2-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="352f2-p101">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="352f2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="352f2-117">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="352f2-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="352f2-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="352f2-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="352f2-119">Sie müssen dieses Verfahren bei der Domänenregistrierungsstelle ausführen, bei der Sie Ihre Domäne erworben und registriert haben.</span><span class="sxs-lookup"><span data-stu-id="352f2-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="352f2-120">Wenn Sie sich für Azure angemeldet haben, haben Sie eine Ressourcengruppe innerhalb einer DNS-Zone erstellt und anschließend Ihren Domänennamen dieser Ressourcengruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="352f2-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="352f2-121">Dieser Domänenname ist für eine externe Domänenregistrierungsstelle registriert; Azure bietet keine Domänenregistrierungsdienste an.</span><span class="sxs-lookup"><span data-stu-id="352f2-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="352f2-122">Zum Überprüfen und Erstellen von DNS-Einträgen für Ihre Domäne in Office 365 müssen Sie zunächst die Namenserver bei Ihrer Domänenregistrierungsstelle ändern, damit Sie die Azure-Namenserver verwenden, die ihrer Ressourcengruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="352f2-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="352f2-123">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="352f2-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="352f2-124">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="352f2-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="352f2-125">Erstellen Sie entweder zwei Namenservereinträge unter Verwendung der Werte in der nachstehenden Tabelle, oder bearbeiten Sie die vorhandenen Einträge, damit sie diesen Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="352f2-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="352f2-126">Unten sehen Sie ein Beispiel für Azure zugewiesene Namenserver.</span><span class="sxs-lookup"><span data-stu-id="352f2-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="352f2-127">**Erster Nameserver:** Verwenden Sie den Namenserver Wert, der von Azure zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="352f2-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="352f2-128">**Zweiter Nameserver:** Verwenden Sie den Namenserver Wert, der von Azure zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="352f2-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="352f2-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="352f2-130">You should use at least two name server records.</span></span> <span data-ttu-id="352f2-131">Wenn auf der Website Ihrer Domänenregistrierungsstelle andere Namenserver aufgeführt sind, sollten Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="352f2-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="352f2-132">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="352f2-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="352f2-p105">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im DNS-System aktualisiert wurden. Dann sind Ihre Office 365-E-Mails und andere Dienste für das Arbeiten mit Ihrer Domäne eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="352f2-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="352f2-135">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="352f2-135">Add a TXT record for verification</span></span>
<span data-ttu-id="352f2-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="352f2-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="352f2-p106">Bevor Sie Ihre Domäne in Office 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Office 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="352f2-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="352f2-p107">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="352f2-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="352f2-141">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="352f2-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="352f2-142">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="352f2-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="352f2-144">Geben Sie über die **Suchleiste** auf der **Dashboardseite** die Zeichen in **DNS-Zonen**ein.</span><span class="sxs-lookup"><span data-stu-id="352f2-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="352f2-145">Wählen Sie in der Ergebnisanzeige **DNS-Zonen** unter dem Abschnitt **Dienste** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="352f2-146">Nachdem Sie umgeleitet wurden, wählen Sie die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="352f2-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="352f2-148">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="352f2-150">Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="352f2-151">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="352f2-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="352f2-152">**Name**</span><span class="sxs-lookup"><span data-stu-id="352f2-152">**Name**</span></span>|<span data-ttu-id="352f2-153">**Typ**</span><span class="sxs-lookup"><span data-stu-id="352f2-153">**Type**</span></span>|<span data-ttu-id="352f2-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="352f2-154">**TTL**</span></span>|<span data-ttu-id="352f2-155">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="352f2-155">**TTL unit**</span></span>|<span data-ttu-id="352f2-156">**Wert**</span><span class="sxs-lookup"><span data-stu-id="352f2-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="352f2-157">TXT</span><span class="sxs-lookup"><span data-stu-id="352f2-157">TXT</span></span>  <br/> |<span data-ttu-id="352f2-158">1</span><span class="sxs-lookup"><span data-stu-id="352f2-158">1</span></span>  <br/> |<span data-ttu-id="352f2-159">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-159">Hours</span></span>  <br/> |<span data-ttu-id="352f2-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="352f2-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="352f2-p110">**Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert von **Ziel oder verweisende Adresse** aus der Tabelle in Office 365.           [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="352f2-p110">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="352f2-165">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="352f2-166">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="352f2-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="352f2-167">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Office 365 zurück und fordern Office 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="352f2-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="352f2-168">Wenn Office 365 den richtigen TXT-Eintrag findet, wird die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="352f2-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="352f2-169">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="352f2-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="352f2-170">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="352f2-171">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="352f2-172">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="352f2-p111">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="352f2-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="352f2-176">Hinzufügen eines MX-Eintrags, damit E-Mails für Ihre Domäne zu Office 365 geleitet werden</span><span class="sxs-lookup"><span data-stu-id="352f2-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="352f2-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="352f2-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="352f2-178">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="352f2-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="352f2-179">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="352f2-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="352f2-181">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="352f2-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="352f2-183">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="352f2-185">Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="352f2-186">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="352f2-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="352f2-187">**Name**</span><span class="sxs-lookup"><span data-stu-id="352f2-187">**Name**</span></span>|<span data-ttu-id="352f2-188">**Typ**</span><span class="sxs-lookup"><span data-stu-id="352f2-188">**Type**</span></span>|<span data-ttu-id="352f2-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="352f2-189">**TTL**</span></span>|<span data-ttu-id="352f2-190">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="352f2-190">**TTL unit**</span></span>|<span data-ttu-id="352f2-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="352f2-191">**Preference**</span></span>|<span data-ttu-id="352f2-192">**E-Mail-Austausch**</span><span class="sxs-lookup"><span data-stu-id="352f2-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="352f2-193">MX</span><span class="sxs-lookup"><span data-stu-id="352f2-193">MX</span></span>  <br/> |<span data-ttu-id="352f2-194">1</span><span class="sxs-lookup"><span data-stu-id="352f2-194">1</span></span>  <br/> |<span data-ttu-id="352f2-195">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-195">Hours</span></span>  <br/> |<span data-ttu-id="352f2-196">10 </span><span class="sxs-lookup"><span data-stu-id="352f2-196">10</span></span>  <br/> <span data-ttu-id="352f2-197">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="352f2-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="352f2-198">*\<Domänenschlüssel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="352f2-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="352f2-199">**Hinweis:** Rufen Sie Ihren \* \<Domänenschlüssel\> \* aus Ihrem Office 365-Konto ab.</span><span class="sxs-lookup"><span data-stu-id="352f2-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="352f2-200">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="352f2-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="352f2-202">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-202">Select **OK**.</span></span>
    
    ![Azure-BP-configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="352f2-204">Wenn im Abschnitt **MX Records** weitere MX-Einträge aufgeführt sind, müssen Sie Sie löschen.</span><span class="sxs-lookup"><span data-stu-id="352f2-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="352f2-205">Wählen Sie zuerst im Bereich **DNS-Zone** den **MX-Eintragssatz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="352f2-207">Wählen Sie als nächstes den MX-Eintrag aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="352f2-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="352f2-209">Wählen Sie das **Kontextmenü (...)** aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="352f2-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="352f2-211">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="352f2-211">Select **Save**.</span></span>
    
    ![Azure-BP-configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="352f2-213">Hinzufügen der vier für Office 365 erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="352f2-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="352f2-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="352f2-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="352f2-215">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="352f2-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="352f2-216">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="352f2-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="352f2-218">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="352f2-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="352f2-220">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="352f2-222">Fügen Sie den ersten der vier CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="352f2-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="352f2-223">Geben Sie im Bereich Daten Satz Satz hinzufügen in den Feldern für den neuen Daten Satz Satz die Werte aus der ersten Zeile in der folgenden Tabelle ein, oder kopieren und fügen **Sie Sie** ein.</span><span class="sxs-lookup"><span data-stu-id="352f2-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="352f2-224">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="352f2-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="352f2-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="352f2-225">**Name**</span></span>|<span data-ttu-id="352f2-226">**Typ**</span><span class="sxs-lookup"><span data-stu-id="352f2-226">**Type**</span></span>|<span data-ttu-id="352f2-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="352f2-227">**TTL**</span></span>|<span data-ttu-id="352f2-228">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="352f2-228">**TTL unit**</span></span>|<span data-ttu-id="352f2-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="352f2-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="352f2-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="352f2-230">autodiscover</span></span>  <br/> |<span data-ttu-id="352f2-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="352f2-231">CNAME</span></span>  <br/> |<span data-ttu-id="352f2-232">1</span><span class="sxs-lookup"><span data-stu-id="352f2-232">1</span></span>  <br/> |<span data-ttu-id="352f2-233">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-233">Hours</span></span>  <br/> |<span data-ttu-id="352f2-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="352f2-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="352f2-235">sip</span><span class="sxs-lookup"><span data-stu-id="352f2-235">sip</span></span>  <br/> |<span data-ttu-id="352f2-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="352f2-236">CNAME</span></span>  <br/> |<span data-ttu-id="352f2-237">1</span><span class="sxs-lookup"><span data-stu-id="352f2-237">1</span></span>  <br/> |<span data-ttu-id="352f2-238">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-238">Hours</span></span>  <br/> |<span data-ttu-id="352f2-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="352f2-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="352f2-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="352f2-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="352f2-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="352f2-241">CNAME</span></span>  <br/> |<span data-ttu-id="352f2-242">1</span><span class="sxs-lookup"><span data-stu-id="352f2-242">1</span></span>  <br/> |<span data-ttu-id="352f2-243">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-243">Hours</span></span>  <br/> |<span data-ttu-id="352f2-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="352f2-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="352f2-246">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-246">Select **OK**.</span></span>
    
    ![Azure-BP-configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="352f2-248">Fügen Sie die drei anderen CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="352f2-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="352f2-249">Wählen Sie im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="352f2-250">Erstellen Sie dann im leeren Daten Satz Satz einen Datensatz mithilfe der Werte aus der nächsten Zeile in der Tabelle, und wählen Sie dann erneut **OK** aus, um den Datensatz abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="352f2-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="352f2-251">Wiederholen Sie diesen Vorgang, bis Sie alle vier CNAME-Einträge erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="352f2-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="352f2-252">Optional Fügen Sie zwei CNAME-Einträge für MDM hinzu.</span><span class="sxs-lookup"><span data-stu-id="352f2-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="352f2-253">Wenn Sie über MDM (Mobile Device Management) für Office 365 verfügen, müssen Sie zwei zusätzliche CNAME-Einträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="352f2-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="352f2-254">Folgen Sie den Schritten für die anderen vier CNAME-Einträge, geben Sie jedoch die Werte aus der nachstehenden Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="352f2-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="352f2-255">(Wenn Sie nicht über MDM verfügen, können Sie diesen Schritt überspringen.)</span><span class="sxs-lookup"><span data-stu-id="352f2-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="352f2-256">**Name**</span><span class="sxs-lookup"><span data-stu-id="352f2-256">**Name**</span></span>|<span data-ttu-id="352f2-257">**Typ**</span><span class="sxs-lookup"><span data-stu-id="352f2-257">**Type**</span></span>|<span data-ttu-id="352f2-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="352f2-258">**TTL**</span></span>|<span data-ttu-id="352f2-259">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="352f2-259">**TTL unit**</span></span>|<span data-ttu-id="352f2-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="352f2-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="352f2-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="352f2-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="352f2-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="352f2-262">CNAME</span></span>  <br/> |<span data-ttu-id="352f2-263">1</span><span class="sxs-lookup"><span data-stu-id="352f2-263">1</span></span>  <br/> |<span data-ttu-id="352f2-264">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-264">Hours</span></span>  <br/> |<span data-ttu-id="352f2-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="352f2-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="352f2-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="352f2-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="352f2-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="352f2-267">CNAME</span></span>  <br/> |<span data-ttu-id="352f2-268">1</span><span class="sxs-lookup"><span data-stu-id="352f2-268">1</span></span>  <br/> |<span data-ttu-id="352f2-269">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-269">Hours</span></span>  <br/> |<span data-ttu-id="352f2-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="352f2-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="352f2-271">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="352f2-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="352f2-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="352f2-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="352f2-273">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="352f2-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="352f2-274">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="352f2-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="352f2-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="352f2-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="352f2-276">Damit verfügen Sie über einen  *einzigen*  SPF-Eintrag, in dem beide Wertemengen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="352f2-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="352f2-277">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="352f2-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="352f2-278">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="352f2-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="352f2-280">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="352f2-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="352f2-282">Wählen Sie im Bereich **DNS-Zone** den **txt-Eintragssatz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="352f2-284">Wählen Sie im Bereich **Eigenschaften von Datensatzgruppe** in den Feldern für den neuen Daten Satz Satz die Werte aus der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="352f2-285">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="352f2-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="352f2-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="352f2-286">**Name**</span></span>|<span data-ttu-id="352f2-287">**Typ**</span><span class="sxs-lookup"><span data-stu-id="352f2-287">**Type**</span></span>|<span data-ttu-id="352f2-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="352f2-288">**TTL**</span></span>|<span data-ttu-id="352f2-289">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="352f2-289">**TTL unit**</span></span>|<span data-ttu-id="352f2-290">**Wert**</span><span class="sxs-lookup"><span data-stu-id="352f2-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="352f2-291">TXT</span><span class="sxs-lookup"><span data-stu-id="352f2-291">TXT</span></span>  <br/> |<span data-ttu-id="352f2-292">1</span><span class="sxs-lookup"><span data-stu-id="352f2-292">1</span></span>  <br/> |<span data-ttu-id="352f2-293">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-293">Hours</span></span>  <br/> |<span data-ttu-id="352f2-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="352f2-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="352f2-295">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="352f2-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="352f2-297">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="352f2-297">Select **Save**.</span></span>
    
    ![Azure-BP-configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="352f2-299">Hinzufügen der für Office 365 erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="352f2-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="352f2-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="352f2-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="352f2-301">Um zu beginnen, navigieren Sie über [diesen Link](https://portal.azure.com )zu ihrer Domänen Seite bei Azure.</span><span class="sxs-lookup"><span data-stu-id="352f2-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="352f2-302">Sie werden aufgefordert, sich zuerst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="352f2-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="352f2-304">Wählen Sie auf der Seite **Dashboard** im Bereich **alle Ressourcen** die Domäne aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="352f2-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="352f2-306">Wählen Sie auf der Seite **Einstellungen** für Ihre Domäne im Bereich **DNS-Zone** die Option **+ Record-Satz**aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="352f2-308">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="352f2-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="352f2-309">Wählen Sie im Bereich Daten Satz Satz **Hinzufügen** in den Feldern für den neuen Daten Satz Satz die Werte aus der ersten Zeile in der folgenden Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="352f2-310">(Wählen Sie in den Dropdownlisten die Werte für **Typ** und **TTL-Einheit** aus.)</span><span class="sxs-lookup"><span data-stu-id="352f2-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="352f2-311">**Name**</span><span class="sxs-lookup"><span data-stu-id="352f2-311">**Name**</span></span>|<span data-ttu-id="352f2-312">**Typ**</span><span class="sxs-lookup"><span data-stu-id="352f2-312">**Type**</span></span>|<span data-ttu-id="352f2-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="352f2-313">**TTL**</span></span>|<span data-ttu-id="352f2-314">**TTL-Einheit**</span><span class="sxs-lookup"><span data-stu-id="352f2-314">**TTL unit**</span></span>|<span data-ttu-id="352f2-315">**Priority**</span><span class="sxs-lookup"><span data-stu-id="352f2-315">**Priority**</span></span>|<span data-ttu-id="352f2-316">**Weight**</span><span class="sxs-lookup"><span data-stu-id="352f2-316">**Weight**</span></span>|<span data-ttu-id="352f2-317">**Port**</span><span class="sxs-lookup"><span data-stu-id="352f2-317">**Port**</span></span>|<span data-ttu-id="352f2-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="352f2-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="352f2-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="352f2-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="352f2-320">SRV</span><span class="sxs-lookup"><span data-stu-id="352f2-320">SRV</span></span>  <br/> |<span data-ttu-id="352f2-321">1</span><span class="sxs-lookup"><span data-stu-id="352f2-321">1</span></span>  <br/> |<span data-ttu-id="352f2-322">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-322">Hours</span></span>  <br/> |<span data-ttu-id="352f2-323">100</span><span class="sxs-lookup"><span data-stu-id="352f2-323">100</span></span>  <br/> |<span data-ttu-id="352f2-324">1</span><span class="sxs-lookup"><span data-stu-id="352f2-324">1</span></span>  <br/> |<span data-ttu-id="352f2-325">443</span><span class="sxs-lookup"><span data-stu-id="352f2-325">443</span></span>  <br/> |<span data-ttu-id="352f2-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="352f2-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="352f2-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="352f2-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="352f2-328">SRV</span><span class="sxs-lookup"><span data-stu-id="352f2-328">SRV</span></span>  <br/> |<span data-ttu-id="352f2-329">1</span><span class="sxs-lookup"><span data-stu-id="352f2-329">1</span></span>  <br/> |<span data-ttu-id="352f2-330">Stunden</span><span class="sxs-lookup"><span data-stu-id="352f2-330">Hours</span></span>  <br/> |<span data-ttu-id="352f2-331">100</span><span class="sxs-lookup"><span data-stu-id="352f2-331">100</span></span>  <br/> |<span data-ttu-id="352f2-332">1</span><span class="sxs-lookup"><span data-stu-id="352f2-332">1</span></span>  <br/> |<span data-ttu-id="352f2-333">5061</span><span class="sxs-lookup"><span data-stu-id="352f2-333">5061</span></span>  <br/> |<span data-ttu-id="352f2-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="352f2-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="352f2-336">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="352f2-336">Select **OK**.</span></span>
    
    ![Azure-BP-configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="352f2-338">Fügen Sie den anderen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="352f2-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="352f2-339">Geben Sie in den Feldern für den neuen Datensatz die Werte aus der zweiten Zeile der Tabelle ein, oder kopieren Sie Sie, und fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="352f2-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="352f2-p120">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="352f2-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
