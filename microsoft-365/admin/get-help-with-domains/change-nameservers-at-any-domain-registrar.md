---
title: Ändern des Namenservers zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle.
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 'Erfahren Sie, wie Sie Ihre Domäne in Microsoft 365 hinzufügen und einrichten, damit Ihre Dienste wie E-Mail und Skype for Business Online Ihren eigenen Domänennamen verwenden. '
ms.openlocfilehash: 7f1ade6cb3013126fb011fe9232b3b4c2e9a82d4
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683127"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="14625-103">Ändern des Namenservers zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="14625-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="14625-104">**[Lesen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="14625-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="14625-105">Befolgen Sie diese Anweisungen, um Ihre Domäne in Microsoft 365 hinzuzufügen und einzurichten, damit Ihre Dienste wie E-Mail und Teams Ihren eigenen Domänennamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="14625-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="14625-106">Hierzu überprüfen Sie Ihre Domäne und ändern dann deren Namenserver zu Microsoft 365, damit die richtigen DNS-Einträge für Sie eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="14625-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="14625-107">Befolgen Sie diese Schritte, wenn die folgenden Aussagen auf Ihre Situation zutreffen:</span><span class="sxs-lookup"><span data-stu-id="14625-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="14625-108">Sie verfügen über eine eigene Domäne und möchten diese in Verbindung mit Microsoft 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="14625-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="14625-109">Sie wollen, dass Microsoft 365 Ihre DNS-Einträge für Sie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="14625-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="14625-110">(Wenn Sie es Ihnen lieber ist, können Sie [Ihre eigenen DNS-Einträge verwalten](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="14625-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="14625-111">Hinzufügen eines TXT- oder MX-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="14625-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="14625-p103">Sie müssen nur einen der beiden Einträge erstellen. TXT ist der bevorzugte Eintragstyp, jedoch wird er von einigen DNS-Hostinganbietern nicht unterstützt. In diesem Fall können Sie stattdessen einen MX-Datensatz erstellen.</span><span class="sxs-lookup"><span data-stu-id="14625-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="14625-p104">Bevor Sie Ihre Domäne in Microsoft 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="14625-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14625-p105">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="14625-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="14625-118">Suchen Sie den Bereich auf der Website Ihres DNS-Hostinganbieters, in dem ein neuer Eintrag erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="14625-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="14625-119">Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an.</span><span class="sxs-lookup"><span data-stu-id="14625-119">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="14625-120"> Wählen Sie Ihre Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="14625-120">Choose your domain.</span></span>
    
3. <span data-ttu-id="14625-121">Suchen Sie die Seite, auf der Sie DNS-Datensätze für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="14625-121">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="14625-122">Erstellen des Eintrags</span><span class="sxs-lookup"><span data-stu-id="14625-122">Create the record</span></span>

<span data-ttu-id="14625-123">Je nachdem, ob Sie einen TXT-Eintrag oder einen MX-Eintrag erstellen möchten, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="14625-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="14625-124">**Wenn Sie einen TXT-Eintrag erstellen, verwenden Sie die folgenden Werte:**</span><span class="sxs-lookup"><span data-stu-id="14625-124">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14625-125">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="14625-125">**Record Type**</span></span> <br/> |<span data-ttu-id="14625-126">**Alias** oder **Hostname**</span><span class="sxs-lookup"><span data-stu-id="14625-126">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="14625-127">**Value**</span><span class="sxs-lookup"><span data-stu-id="14625-127">**Value**</span></span> <br/> |<span data-ttu-id="14625-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14625-128">**TTL**</span></span> <br/> |
|<span data-ttu-id="14625-129">TXT</span><span class="sxs-lookup"><span data-stu-id="14625-129">TXT</span></span>  <br/> |<span data-ttu-id="14625-130">Führen Sie eine der folgenden Aktionen aus: Geben Sie **@** ein, lassen Sie das Feld leer, oder geben Sie Ihren Domänennamen ein.  </span><span class="sxs-lookup"><span data-stu-id="14625-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="14625-131">> [!NOTE]> Die Anforderungen für dieses Feld sind je nach DNS-Host unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="14625-131">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="14625-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="14625-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="14625-133">> [!NOTE]> Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="14625-133">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="14625-134">Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14625-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="14625-135">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="14625-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="14625-136">Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.</span><span class="sxs-lookup"><span data-stu-id="14625-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="14625-137">**Wenn Sie einen MX-Eintrag erstellen, verwenden Sie die folgenden Werte:**</span><span class="sxs-lookup"><span data-stu-id="14625-137">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14625-138">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="14625-138">**Record Type**</span></span>|<span data-ttu-id="14625-139">**Alias** oder **Hostname**</span><span class="sxs-lookup"><span data-stu-id="14625-139">**Alias** or **Host Name**</span></span>|<span data-ttu-id="14625-140">**Value**</span><span class="sxs-lookup"><span data-stu-id="14625-140">**Value**</span></span>|<span data-ttu-id="14625-141">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="14625-141">**Priority**</span></span>|<span data-ttu-id="14625-142">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14625-142">**TTL**</span></span>|
|<span data-ttu-id="14625-143">MX</span><span class="sxs-lookup"><span data-stu-id="14625-143">MX</span></span>|<span data-ttu-id="14625-144">Geben Sie **@** oder Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="14625-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="14625-145">MS=ms *XXXXXXXX* > [!NOTE]> Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="14625-145">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="14625-146">Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14625-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="14625-147">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="14625-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="14625-148">Für **Priority** (Priorität) verwenden Sie eine geringere Priorität als für die bereits vorhandenen MX-Einträge, um Konflikte mit dem MX-Eintrag für den E-Mail-Verkehr zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="14625-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="14625-149">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="14625-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="14625-150">Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.</span><span class="sxs-lookup"><span data-stu-id="14625-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="14625-151">Speichern des Eintrags</span><span class="sxs-lookup"><span data-stu-id="14625-151">Save the record</span></span>

<span data-ttu-id="14625-152">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="14625-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="14625-153">Wenn Microsoft 365 den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="14625-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="14625-154">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="14625-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="14625-155">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="14625-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="14625-156">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="14625-156">On the **Setup** page, select **Start setup**.</span></span>
 
  
4. <span data-ttu-id="14625-157">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="14625-157">On the **Verify domain** page, select **Verify**.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="14625-p109">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="14625-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="14625-161">Ändern der Namenservereinträge (NS-Einträge) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="14625-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="14625-162">Als letzten Schritt im Setupassistenten für Domänen in Microsoft 365 müssen Sie nur noch eine einzige Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="14625-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="14625-163">Um Ihre Domäne mit Microsoft 365-Diensten wie E-Mail einzurichten, ändern Sie die Namenservereinträge (oder NS-Einträge) bei Ihrer Domänenregistrierungsstelle so, dass diese auf die primären und sekundären Microsoft 365-Namenserver verweisen.</span><span class="sxs-lookup"><span data-stu-id="14625-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="14625-164">Weil Ihr DNS von Microsoft 365 gehostet wird, werden anschließend die erforderlichen DNS-Einträge für Ihre Dienste für Sie automatisch eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="14625-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="14625-165">Sie können die Namenservereinträge selbst aktualisieren, indem Sie die Schritte durchführen, die Ihre Domänenregistrierungsstelle eventuell in den Hilfeinhalten auf ihrer Website bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="14625-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="14625-166">Wenn Sie mit DNS nicht vertraut sind, wenden Sie sich an den Support bei der Domänenregistrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="14625-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="14625-167">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="14625-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="14625-168">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können, oder einen Bereich, in dem Sie benutzerdefinierte Namensserver verwenden können.</span><span class="sxs-lookup"><span data-stu-id="14625-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="14625-169">Erstellen Sie Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:</span><span class="sxs-lookup"><span data-stu-id="14625-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="14625-170">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="14625-170">First nameserver</span></span>  <br/> |<span data-ttu-id="14625-171">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="14625-171">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="14625-172">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="14625-172">Second nameserver</span></span>  <br/> |<span data-ttu-id="14625-173">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="14625-173">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="14625-174">Dritter Namenserver</span><span class="sxs-lookup"><span data-stu-id="14625-174">Third nameserver</span></span>  <br/> |<span data-ttu-id="14625-175">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="14625-175">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="14625-176">Vierter Namenserver</span><span class="sxs-lookup"><span data-stu-id="14625-176">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="14625-177">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="14625-177">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="14625-178">Idealerweise fügen Sie alle vier Einträge hinzu, aber wenn Ihre Registrierungsstelle nur zwei unterstützt, fügen Sie **ns1.bdm.microsoftonline.com** und **ns2.bdm.microsoftonline.com** hinzu.</span><span class="sxs-lookup"><span data-stu-id="14625-178">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="14625-179">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="14625-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="14625-180">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass sie auf die Microsoft 365-Namenserver verweisen, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="14625-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="14625-181">Wenn Sie einzelne Schritte des Assistenten übersprungen haben, z. B. das Hinzufügen von E-Mail-Adressen, oder wenn Sie Ihre Domäne für Blogs, Warenkörbe oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14625-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="14625-182">Andernfalls könnte diese Änderung zu Ausfallzeiten des Dienstes führen, z. B. mangelnder E-Mail-Zugriff oder fehlender Zugriff auf Ihre aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="14625-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="14625-183">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="14625-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="14625-184">Erstellen Sie zwei Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:</span><span class="sxs-lookup"><span data-stu-id="14625-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="14625-185">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="14625-185">First nameserver</span></span>  <br/> |<span data-ttu-id="14625-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="14625-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="14625-187">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="14625-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="14625-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="14625-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="14625-189">Sie sollten mindestens zwei Namenservereinträge verwenden.</span><span class="sxs-lookup"><span data-stu-id="14625-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="14625-190">Wenn weitere Namenserver aufgelistet sind, können Sie diese entweder löschen oder ändern in **ns3.dns.partner.microsoftonline.com** und **ns4.dns.partner.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="14625-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="14625-191">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="14625-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="14625-192">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass sie auf Office 365 verweisen, das von 21Vianet-Namenservern betrieben wird, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="14625-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="14625-193">Wenn Sie einzelne Schritte des Assistenten übersprungen haben, z. B. das Hinzufügen von E-Mail-Adressen, oder wenn Sie Ihre Domäne für Blogs, Warenkörbe oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14625-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="14625-194">Andernfalls könnte diese Änderung zu Ausfallzeiten des Dienstes führen, z. B. mangelnder E-Mail-Zugriff oder fehlender Zugriff auf Ihre aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="14625-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="14625-195">Hier einige weitere Schritte, die beispielsweise für E-Mail- und Websitehosting erforderlich sein können:</span><span class="sxs-lookup"><span data-stu-id="14625-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="14625-196">Verschieben Sie alle E-Mail-Adressen, die Ihre Domäne verwenden, auf Microsoft 365, bevor Sie Ihre NS-Einträge ändern.</span><span class="sxs-lookup"><span data-stu-id="14625-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="14625-197">Möchten Sie eine Domäne hinzufügen, die zurzeit mit einer Websiteadresse verwendet wird, beispielsweise „www.fourthcoffee.com“?</span><span class="sxs-lookup"><span data-stu-id="14625-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="14625-198">Sie können die nachfolgenden Schritte beim Hinzufügen der Domäne durchführen, um den aktuellen Host als Host für die Website beizubehalten, sodass die Website weiterhin erreichbar ist, nachdem Sie die NS-Einträge der Domäne so geändert haben, dass sie auf Microsoft 365 verweisen.</span><span class="sxs-lookup"><span data-stu-id="14625-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="14625-199">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="14625-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="14625-200">Wählen Sie auf der Seite **Domänen** eine Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="14625-200">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="14625-201">Wählen Sie auf der Seite Domänendetails die Registerkarte **DNS-Einträge** aus.</span><span class="sxs-lookup"><span data-stu-id="14625-201">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="14625-202">Wählen **Sie Datensatz hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="14625-202">Select **Add record**.</span></span>

5. <span data-ttu-id="14625-203">Wählen Sie **im Bereich Benutzerdefinierten DNS-Eintrag** hinzufügen in der **Dropdownliste** Typ die Option **A (Adresse) aus.**</span><span class="sxs-lookup"><span data-stu-id="14625-203">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="14625-204">Geben Sie **im Feld Hostname oder Alias** **@** ein.</span><span class="sxs-lookup"><span data-stu-id="14625-204">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="14625-205">Geben Sie **im Feld IP-Adresse** die statische IP-Adresse für die Website ein, auf der sie derzeit gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="14625-205">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="14625-206">Beispiel: 172.16.140.1.</span><span class="sxs-lookup"><span data-stu-id="14625-206">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="14625-207">Dies muss eine _statische_ IP-Adresse für die Website und keine _dynamische IP-Adresse_ sein.</span><span class="sxs-lookup"><span data-stu-id="14625-207">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="14625-208">Um sicherzustellen, dass Sie eine statische IP-Adresse für Ihre öffentliche Website erhalten können, überprüfen Sie die Website, auf der Ihre Website hostet.</span><span class="sxs-lookup"><span data-stu-id="14625-208">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="14625-209">Wenn Sie die TTL-Einstellung für den Datensatz ändern möchten, wählen Sie in der Dropdownliste **TTL** eine neue Dauer aus.</span><span class="sxs-lookup"><span data-stu-id="14625-209">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="14625-210">Fahren Sie andernfalls mit Schritt 9 fort.</span><span class="sxs-lookup"><span data-stu-id="14625-210">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="14625-211">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14625-211">Select **Save**.</span></span> 
    
<span data-ttu-id="14625-212">Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.</span><span class="sxs-lookup"><span data-stu-id="14625-212">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="14625-213">Wählen **Sie Datensatz hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="14625-213">Select **Add record**.</span></span>

3.  <span data-ttu-id="14625-214">Wählen Sie im Bereich Benutzerdefinierte **#A0** hinzufügen in der **Dropdownliste** Typ die Option **CNAME (Alias)** aus.</span><span class="sxs-lookup"><span data-stu-id="14625-214">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="14625-215">Geben Sie **im Feld Hostname oder Alias** www **ein.**</span><span class="sxs-lookup"><span data-stu-id="14625-215">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="14625-216">Geben Sie im Feld Punkte **zu Adresse** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Website ein.</span><span class="sxs-lookup"><span data-stu-id="14625-216">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="14625-217">Beispielsweise **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="14625-217">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="14625-218">Wenn Sie die TTL-Einstellung für den Datensatz ändern möchten, wählen Sie in der Dropdownliste **TTL** eine neue Dauer aus.</span><span class="sxs-lookup"><span data-stu-id="14625-218">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="14625-219">Fahren Sie andernfalls mit Schritt 6 fort.</span><span class="sxs-lookup"><span data-stu-id="14625-219">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="14625-220">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="14625-220">Select **Save**.</span></span>

<span data-ttu-id="14625-221">Nachdem die Nameservereinträge so aktualisiert wurden, dass sie auf Microsoft verweisen, ist die Domäneneinrichtung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="14625-221">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="14625-222">E-Mails werden an Microsoft geroutet, und der Datenverkehr zu Ihrer Websiteadresse wird weiterhin an Ihren aktuellen Websitehost gesendet."</span><span class="sxs-lookup"><span data-stu-id="14625-222">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="14625-223">Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im gesamten DNS-System aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="14625-223">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="14625-224">Danach sind Ihre Microsoft-E-Mails und andere Dienste alle dafür eingerichtet, mit Ihrer Domäne zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="14625-224">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="14625-225">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="14625-225">Related content</span></span>

<span data-ttu-id="14625-226">[Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](create-dns-records-at-any-dns-hosting-provider.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="14625-226">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="14625-227">[Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](find-and-fix-issues.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="14625-227">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="14625-228">[Domänen verwalten](index.yml) (Linkseite)</span><span class="sxs-lookup"><span data-stu-id="14625-228">[Manage domains](index.yml) (link page)</span></span>
