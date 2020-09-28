---
title: Ändern von Namenservern zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle
f1.keywords:
- CSH
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
description: In diesem Artikel erfahren Sie, wie Sie Ihre Domäne in Microsoft 365 hinzufügen und einrichten, damit ihre Dienste wie e-Mail und Skype for Business Online ihren eigenen Domänennamen verwenden.
ms.openlocfilehash: 34e4db5748f9d4c1f1864db09071374bcec73e1d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295058"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="f2def-103">Ändern von Namenservern zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="f2def-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="f2def-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="f2def-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f2def-105">Aktivieren Sie zuerst die Informationen zum [Einrichten Ihrer Domäne (hostspezifische Anweisungen)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) , um zu sehen, ob wir Anweisungen für Ihre Registrierungsstelle haben.</span><span class="sxs-lookup"><span data-stu-id="f2def-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="f2def-106">Befolgen Sie diese Anweisungen, um Ihre Domäne in Microsoft 365 hinzuzufügen und einzurichten, damit ihre Dienste wie e-Mail und Teams ihren eigenen Domänennamen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f2def-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="f2def-107">Um dies zu tun, überprüfen Sie Ihre Domäne und ändern dann die Namenserver Ihrer Domäne auf Microsoft 365, damit die richtigen DNS-Einträge für Sie eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="f2def-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="f2def-108">Führen Sie die folgenden Schritte aus, wenn die folgende Anweisung Ihre Situation beschreibt:</span><span class="sxs-lookup"><span data-stu-id="f2def-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="f2def-109">Sie verfügen über eine eigene Domäne und möchten diese für die Zusammenarbeit mit Microsoft 365 einrichten.</span><span class="sxs-lookup"><span data-stu-id="f2def-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="f2def-110">Sie möchten, dass Microsoft 365 Ihre DNS-Einträge für Sie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f2def-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="f2def-111">(Wenn Sie es Ihnen lieber ist, können Sie [Ihre eigenen DNS-Einträge verwalten](../setup/add-domain.md).)</span><span class="sxs-lookup"><span data-stu-id="f2def-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="f2def-112">Hinzufügen eines TXT- oder MX-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="f2def-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="f2def-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f2def-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="f2def-p103">Sie müssen nur einen der beiden Einträge erstellen. TXT ist der bevorzugte Eintragstyp, jedoch wird er von einigen DNS-Hostinganbietern nicht unterstützt. In diesem Fall können Sie stattdessen einen MX-Datensatz erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2def-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="f2def-p104">Bevor Sie Ihre Domäne in Microsoft 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft 365 der Nachweis, dass Sie der Besitzer der Domäne sind.</span><span class="sxs-lookup"><span data-stu-id="f2def-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2def-p105">Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.</span><span class="sxs-lookup"><span data-stu-id="f2def-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="f2def-120">Suchen Sie den Bereich auf der Website Ihres DNS-Host Anbieters, auf dem Sie einen neuen Datensatz erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f2def-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="f2def-121">Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an.</span><span class="sxs-lookup"><span data-stu-id="f2def-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="f2def-122"> Wählen Sie Ihre Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="f2def-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="f2def-123">Suchen Sie die Seite, auf der Sie DNS-Datensätze für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="f2def-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="f2def-124">Erstellen des Datensatzes</span><span class="sxs-lookup"><span data-stu-id="f2def-124">Create the record</span></span>

<span data-ttu-id="f2def-125">Je nachdem, ob Sie einen TXT-Eintrag oder einen MX-Eintrag erstellen möchten, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f2def-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="f2def-126">**Wenn Sie einen TXT-Eintrag erstellen, verwenden Sie die folgenden Werte:**</span><span class="sxs-lookup"><span data-stu-id="f2def-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2def-127">\*\*Record Type \*\*</span><span class="sxs-lookup"><span data-stu-id="f2def-127">**Record Type**</span></span> <br/> |<span data-ttu-id="f2def-128">**Alias** oder **Hostname**</span><span class="sxs-lookup"><span data-stu-id="f2def-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="f2def-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2def-129">**Value**</span></span> <br/> |<span data-ttu-id="f2def-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f2def-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="f2def-131">TXT</span><span class="sxs-lookup"><span data-stu-id="f2def-131">TXT</span></span>  <br/> |<span data-ttu-id="f2def-132">Führen Sie eine der folgenden Aktionen aus: Geben Sie **@** ein, lassen Sie das Feld leer, oder geben Sie Ihren Domänennamen ein.  </span><span class="sxs-lookup"><span data-stu-id="f2def-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="f2def-133">> [!NOTE]> Die Anforderungen für dieses Feld sind je nach DNS-Host unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="f2def-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="f2def-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f2def-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f2def-135">> [!NOTE]> Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f2def-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="f2def-136">Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2def-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="f2def-137">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="f2def-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f2def-138">Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.</span><span class="sxs-lookup"><span data-stu-id="f2def-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="f2def-139">**Wenn Sie einen MX-Eintrag erstellen, verwenden Sie die folgenden Werte:**</span><span class="sxs-lookup"><span data-stu-id="f2def-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f2def-140">\*\*Record Type \*\*</span><span class="sxs-lookup"><span data-stu-id="f2def-140">**Record Type**</span></span>|<span data-ttu-id="f2def-141">**Alias** oder **Hostname**</span><span class="sxs-lookup"><span data-stu-id="f2def-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="f2def-142">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2def-142">**Value**</span></span>|<span data-ttu-id="f2def-143">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="f2def-143">**Priority**</span></span>|<span data-ttu-id="f2def-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f2def-144">**TTL**</span></span>|
|<span data-ttu-id="f2def-145">MX</span><span class="sxs-lookup"><span data-stu-id="f2def-145">MX</span></span>|<span data-ttu-id="f2def-146">Geben Sie **@** oder Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="f2def-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="f2def-147">MS=ms *XXXXXXXX* > [!NOTE]> Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f2def-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="f2def-148">Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2def-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="f2def-149">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="f2def-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f2def-150">Für **Priority** (Priorität) verwenden Sie eine geringere Priorität als für die bereits vorhandenen MX-Einträge, um Konflikte mit dem MX-Eintrag für den E-Mail-Verkehr zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f2def-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="f2def-151">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="f2def-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="f2def-152">Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.</span><span class="sxs-lookup"><span data-stu-id="f2def-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="f2def-153">Speichern des Datensatzes</span><span class="sxs-lookup"><span data-stu-id="f2def-153">Save the record</span></span>

<span data-ttu-id="f2def-154">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f2def-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="f2def-155">Wenn Microsoft 365 den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="f2def-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="f2def-156">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="f2def-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f2def-157">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="f2def-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="f2def-158">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="f2def-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="f2def-159">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="f2def-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f2def-p109">Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f2def-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f2def-163">Ändern der Namenservereinträge (NS) Ihrer Domäne</span><span class="sxs-lookup"><span data-stu-id="f2def-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f2def-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f2def-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="f2def-165">Wenn Sie zum letzten Schritt des Setup-Assistenten für Domänen in Microsoft 365 gelangen, bleibt eine Aufgabe erhalten.</span><span class="sxs-lookup"><span data-stu-id="f2def-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="f2def-166">Um Ihre Domäne mit Microsoft 365-Diensten wie e-Mail einzurichten, ändern Sie die Namenservereinträge (oder NS) Ihrer Domäne bei Ihrer Domänenregistrierungsstelle so, dass Sie auf die primären und sekundären Namenserver von Microsoft 365 verweist.</span><span class="sxs-lookup"><span data-stu-id="f2def-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="f2def-167">Da Microsoft 365 dann Ihr DNS hostet, werden die erforderlichen DNS-Einträge für ihre Dienste automatisch für Sie eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="f2def-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="f2def-168">Sie können die Namenservereinträge selbst aktualisieren, indem Sie die Schritte durchführen, die Ihre Domänenregistrierungsstelle eventuell in den Hilfeinhalten auf ihrer Website bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f2def-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="f2def-169">Wenn Sie mit DNS nicht vertraut sind, wenden Sie sich an den Support bei der Domänenregistrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="f2def-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="f2def-170">Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f2def-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="f2def-171">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, auf dem Sie die Namenserver für Ihre Domäne oder einen Bereich ändern können, in dem Sie benutzerdefinierte Namenserver verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f2def-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="f2def-172">Erstellen Sie Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass Sie mit den folgenden Werten übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="f2def-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f2def-173">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="f2def-173">First nameserver</span></span>  <br/> |<span data-ttu-id="f2def-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f2def-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f2def-175">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="f2def-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="f2def-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f2def-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f2def-177">Dritter Namenserver</span><span class="sxs-lookup"><span data-stu-id="f2def-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="f2def-178">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f2def-178">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f2def-179">Vierter Namenserver</span><span class="sxs-lookup"><span data-stu-id="f2def-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="f2def-180">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f2def-180">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="f2def-181">Es empfiehlt sich, alle vier Datensätze hinzuzufügen, aber wenn Ihre Registrierungsstelle nur zwei unterstützt, fügen Sie **ns1.BDM.microsoftonline.com** und **ns2.BDM.microsoftonline.com**hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2def-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="f2def-182">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="f2def-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f2def-183">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Microsoft 365-Namenserver verweist, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f2def-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f2def-184">Wenn Sie alle Schritte des Assistenten übersprungen haben, beispielsweise das Hinzufügen von e-Mail-Adressen oder wenn Sie Ihre Domäne für Blogs, Einkaufswagen oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f2def-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="f2def-185">Andernfalls kann diese Änderung zu Dienstunterbrechungen führen, beispielsweise bei fehlendem e-Mail-Zugriff oder beim Zugriff auf Ihre aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="f2def-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="f2def-186">Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="f2def-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f2def-187">Erstellen Sie zwei Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:</span><span class="sxs-lookup"><span data-stu-id="f2def-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f2def-188">Erster Namenserver</span><span class="sxs-lookup"><span data-stu-id="f2def-188">First nameserver</span></span>  <br/> |<span data-ttu-id="f2def-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="f2def-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="f2def-190">Zweiter Namenserver</span><span class="sxs-lookup"><span data-stu-id="f2def-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="f2def-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="f2def-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="f2def-192">Sie sollten mindestens zwei Nameserver-Einträge verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2def-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="f2def-193">Wenn andere Namenserver aufgelistet sind, können Sie Sie entweder löschen oder in **NS3.DNS.Partner.microsoftonline.cn** und **NS4.DNS.Partner.microsoftonline.cn**ändern.</span><span class="sxs-lookup"><span data-stu-id="f2def-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="f2def-194">Speichern Sie Ihre Änderungen.</span><span class="sxs-lookup"><span data-stu-id="f2def-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f2def-195">Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass Sie auf die Office 365, die von 21Vianet-Namenservern betrieben werden, hinweisen, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f2def-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f2def-196">Wenn Sie alle Schritte des Assistenten übersprungen haben, beispielsweise das Hinzufügen von e-Mail-Adressen oder wenn Sie Ihre Domäne für Blogs, Einkaufswagen oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f2def-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="f2def-197">Andernfalls kann diese Änderung zu Dienstunterbrechungen führen, beispielsweise bei fehlendem e-Mail-Zugriff oder beim Zugriff auf Ihre aktuelle Website.</span><span class="sxs-lookup"><span data-stu-id="f2def-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="f2def-198">Hier einige weitere Schritte, die beispielsweise für E-Mail- und Websitehosting erforderlich sein können:</span><span class="sxs-lookup"><span data-stu-id="f2def-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="f2def-199">Ziehen Sie alle e-Mail-Adressen, die Ihre Domäne verwenden, auf Microsoft 365, bevor Sie Ihre NS-Einträge ändern.</span><span class="sxs-lookup"><span data-stu-id="f2def-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="f2def-200">Möchten Sie eine Domäne hinzufügen, die zurzeit mit einer Websiteadresse verwendet wird, beispielsweise "www.fourthcoffee.com"?</span><span class="sxs-lookup"><span data-stu-id="f2def-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="f2def-201">Sie können die folgenden Schritte ausführen, während Sie die Domäne hinzufügen, damit die Website gehostet wird, in der die Website gehostet wird, damit Benutzer weiterhin auf die Website gelangen können, nachdem Sie die NS-Einträge der Domäne so geändert haben, dass Sie auf Microsoft 365 zeigen.</span><span class="sxs-lookup"><span data-stu-id="f2def-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="f2def-202">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="f2def-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="f2def-203">Wählen Sie auf der Seite **Domänen** die Domäne aus, und wählen Sie dann **DNS-Einträge**aus.</span><span class="sxs-lookup"><span data-stu-id="f2def-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="f2def-204">Wählen Sie unter **DNS-Einstellungen**die Option **Benutzerdefinierte Datensätze**aus, und wählen Sie dann **neuer benutzerdefinierter Datensatz**aus.</span><span class="sxs-lookup"><span data-stu-id="f2def-204">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="f2def-205">Wählen Sie den Typ des DNS-Eintrags aus, den Sie hinzufügen möchten, und geben Sie die Informationen für den neuen Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="f2def-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="f2def-206">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f2def-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f2def-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f2def-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f2def-208">Dann sind Ihre Microsoft-e-Mails und andere Dienste für die Verwendung Ihrer Domäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f2def-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
