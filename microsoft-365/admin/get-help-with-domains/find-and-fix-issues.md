---
title: Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537547"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="6264d-103">Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="6264d-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="6264d-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="6264d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6264d-105">Die Einrichtung Ihrer Domäne für die Arbeit mit Microsoft 365 kann eine Herausforderung darstellen.</span><span class="sxs-lookup"><span data-stu-id="6264d-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="6264d-106">Das DNS-System ist zu verwenden, und das DNS-Setup für Ihre Domäne wirkt sich auf wichtige Geschäftsaktivitäten wie E-Mail aus.</span><span class="sxs-lookup"><span data-stu-id="6264d-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="6264d-107">Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6264d-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="6264d-108">Wechseln Sie **zu**  >  **Setupdomänen,** und zeigen Sie die Benachrichtigungen in der **Spalte Status** an.</span><span class="sxs-lookup"><span data-stu-id="6264d-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="6264d-109">Wenn ein Problem angezeigt wird, wählen Sie die drei Punkte (weitere Aktionen) aus, und wählen Sie dann **Integrität überprüfen aus.**</span><span class="sxs-lookup"><span data-stu-id="6264d-109">If you see an issue, select the three dots (more actions), and then choose **Check health**.</span></span> <span data-ttu-id="6264d-110">In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6264d-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="6264d-111">Was ist los?</span><span class="sxs-lookup"><span data-stu-id="6264d-111">What's going on?</span></span>

- [<span data-ttu-id="6264d-112">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="6264d-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="6264d-113">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="6264d-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="6264d-114">Alle E-Mails wurden zu Microsoft 365 und Sie wollten nur, dass IHRE E-Mail gewechselt wird?</span><span class="sxs-lookup"><span data-stu-id="6264d-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="6264d-115">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="6264d-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="6264d-116">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="6264d-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="6264d-117">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="6264d-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="6264d-118">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="6264d-118">Can't verify your domain?</span></span>
<span data-ttu-id="6264d-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6264d-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6264d-120">Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:</span><span class="sxs-lookup"><span data-stu-id="6264d-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="6264d-p103">**Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich!</span><span class="sxs-lookup"><span data-stu-id="6264d-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="6264d-125">**Der Eintrag wurde nicht gespeichert.**</span><span class="sxs-lookup"><span data-stu-id="6264d-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="6264d-126">Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei zu speichern (in der der DNS-Eintrag gespeichert ist), damit der Eintrag im Internet aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6264d-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="6264d-127">Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz sehen und überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="6264d-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="6264d-128">**Der Eintrag wurde noch nicht im Internet aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="6264d-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="6264d-129">In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="6264d-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="6264d-130">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="6264d-130">Outlook isn't working?</span></span>
<span data-ttu-id="6264d-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="6264d-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="6264d-132">Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="6264d-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="6264d-133">Alle E-Mails wurden zu Microsoft 365 und Sie wollten nur, dass IHRE E-Mail gewechselt wird?</span><span class="sxs-lookup"><span data-stu-id="6264d-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="6264d-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="6264d-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="6264d-135">Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird in der Regel der MX-Eintrag Ihrer Domäne (von Ihnen oder Microsoft 365) aktualisiert, um auf Microsoft 365 zu verweisen, und alle an diese Domäne gesendeten E-Mails werden an Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6264d-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6264d-136">Stellen Sie sicher, dass Sie Postfächer in Microsoft 365 für alle Personen erstellt haben, die E-Mails in Ihrer Domäne haben, BEVOR Sie den MX-Eintrag ändern.</span><span class="sxs-lookup"><span data-stu-id="6264d-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="6264d-137">Was passiert, wenn Sie E-Mails nicht für alle in Ihrer Domäne verschieben möchten, um Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="6264d-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="6264d-138">Sie können stattdessen [ein Pilotprojekt mit Microsoft 365 und nur wenigen E-Mail-Adressen in die Wege leiten](../setup/domains-faq.yml). </span><span class="sxs-lookup"><span data-stu-id="6264d-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="6264d-139">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="6264d-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="6264d-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="6264d-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="6264d-141">Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="6264d-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="6264d-142">Um z. B. zu Microsoft 365, dass Ihre Organisation für ein Schulabonnement qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="6264d-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="6264d-143">Lesen Sie die Anleitungen unter [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status,](../setup/domains-faq.yml) or to activate Yammer to make sure you've completed all the required steps.</span><span class="sxs-lookup"><span data-stu-id="6264d-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="6264d-144">Der Vorgang ist für jede Situation ein wenig anders.</span><span class="sxs-lookup"><span data-stu-id="6264d-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="6264d-145">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="6264d-145">Services not working with your domain?</span></span>
<span data-ttu-id="6264d-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="6264d-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="6264d-147">Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6264d-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="6264d-148">Die Problembehandlung für Domänen in Microsoft 365 zeigt alle Datensätze an, die behoben werden müssen, und genau das, worauf die Datensätze festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6264d-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="6264d-149">Sie haben Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail-Nachrichten funktionieren in Outlook auf dem Desktop nicht?</span><span class="sxs-lookup"><span data-stu-id="6264d-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="6264d-150">Sehen Sie sich [die verschiedenen Nachrichtenflussszenarien](/exchange/mail-flow-best-practices/mail-flow-best-practices) an, die Sie mit Microsoft 365 können, um sicherzustellen, dass sie für Ihr Unternehmen richtig eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="6264d-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="6264d-151">Darüber hinaus finden Sie hier weitere Hilfe zur Problembehandlung im Zusammenhang mit E-Mails: [Beheben von Problemen mit Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="6264d-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="6264d-152">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="6264d-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="6264d-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="6264d-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="6264d-154">Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="6264d-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="6264d-155">Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="6264d-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="6264d-156">Sie können Ihren A- oder #A0 nicht aktualisieren, um auf Ihre Website zu verweisen: Aktualisieren von benutzerdefinierten [#A1 in Microsoft 365](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="6264d-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="6264d-157">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6264d-157">Related content</span></span>

[<span data-ttu-id="6264d-158">Problembehandlung: Überwachen von Daten bei überprüften Domänenänderung</span><span class="sxs-lookup"><span data-stu-id="6264d-158">Troubleshoot: Audit data on verified domain change</span></span>](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

