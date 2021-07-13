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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: 1dcc52be68fca11245e1a2437d9fe5a3f23ed694
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393895"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="d15bb-103">Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="d15bb-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="d15bb-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="d15bb-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d15bb-105">Es kann schwierig sein, Ihre Domäne für die Arbeit mit Microsoft 365 einzurichten.</span><span class="sxs-lookup"><span data-stu-id="d15bb-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="d15bb-106">Das DNS-System eignet sich gut für die Arbeit, und das DNS-Setup für Ihre Domäne wirkt sich auf wichtige Geschäftsaktivitäten wie E-Mails aus.</span><span class="sxs-lookup"><span data-stu-id="d15bb-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="d15bb-107">Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d15bb-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="d15bb-108">Wechseln **Sie** zu  >  **"Setupdomänen",** und zeigen Sie die Benachrichtigungen in der Spalte **"Status"** an.</span><span class="sxs-lookup"><span data-stu-id="d15bb-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="d15bb-109">Wenn ein Problem auftritt, wählen Sie die drei Punkte (weitere Aktionen) und dann **"Integrität überprüfen"** aus.</span><span class="sxs-lookup"><span data-stu-id="d15bb-109">If you see an issue, select the three dots (more actions), and then choose **Check health**.</span></span> <span data-ttu-id="d15bb-110">In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d15bb-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="d15bb-111">Was ist los?</span><span class="sxs-lookup"><span data-stu-id="d15bb-111">What's going on?</span></span>

- [<span data-ttu-id="d15bb-112">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="d15bb-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="d15bb-113">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="d15bb-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="d15bb-114">Die E-Mails aller Benutzer wurden auf Microsoft 365 umgestellt, und Sie wollten nur, dass IHRE E-Mail wechselt?</span><span class="sxs-lookup"><span data-stu-id="d15bb-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="d15bb-115">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="d15bb-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="d15bb-116">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="d15bb-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="d15bb-117">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="d15bb-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="d15bb-118">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="d15bb-118">Can't verify your domain?</span></span>
<span data-ttu-id="d15bb-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d15bb-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d15bb-120">Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:</span><span class="sxs-lookup"><span data-stu-id="d15bb-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="d15bb-p103">**Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich!</span><span class="sxs-lookup"><span data-stu-id="d15bb-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="d15bb-125">**Der Eintrag wurde nicht gespeichert.**</span><span class="sxs-lookup"><span data-stu-id="d15bb-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="d15bb-126">Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei zu speichern (in der der DNS-Eintrag gespeichert ist), damit der Eintrag im Internet aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d15bb-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="d15bb-127">Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz anzeigen und überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="d15bb-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="d15bb-128">**Der Eintrag wurde noch nicht im Internet aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="d15bb-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="d15bb-129">In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="d15bb-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="d15bb-130">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="d15bb-130">Outlook isn't working?</span></span>
<span data-ttu-id="d15bb-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="d15bb-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="d15bb-132">Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="d15bb-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="d15bb-133">Die E-Mails aller Benutzer wurden auf Microsoft 365 umgestellt, und Sie wollten nur, dass IHRE E-Mail wechselt?</span><span class="sxs-lookup"><span data-stu-id="d15bb-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="d15bb-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="d15bb-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="d15bb-135">Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird in der Regel der MX-Eintrag Ihrer Domäne (von Ihnen oder Microsoft 365) aktualisiert, um auf Microsoft 365 zu verweisen, und ALLE an diese Domäne gesendeten E-Mails werden an Microsoft 365 gesendet.</span><span class="sxs-lookup"><span data-stu-id="d15bb-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="d15bb-136">Stellen Sie sicher, dass Sie Postfächer in Microsoft 365 für alle Benutzer erstellt haben, die über E-Mails in Ihrer Domäne verfügen, BEVOR Sie den MX-Eintrag ändern.</span><span class="sxs-lookup"><span data-stu-id="d15bb-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="d15bb-137">Was geschieht, wenn Sie keine E-Mails für alle Benutzer in Ihrer Domäne in Microsoft 365 verschieben möchten?</span><span class="sxs-lookup"><span data-stu-id="d15bb-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="d15bb-138">Sie können stattdessen [ein Pilotprojekt mit Microsoft 365 und nur wenigen E-Mail-Adressen in die Wege leiten](../setup/domains-faq.yml). </span><span class="sxs-lookup"><span data-stu-id="d15bb-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](../setup/domains-faq.yml).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="d15bb-139">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="d15bb-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="d15bb-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="d15bb-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="d15bb-141">Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="d15bb-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="d15bb-142">Zum Beispiel, um Microsoft 365 nachzuweisen, dass Ihre Organisation für ein Schulabonnement qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="d15bb-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="d15bb-143">Lesen Sie die Anleitung unter ["Überprüfen Ihrer Microsoft 365 Domäne, um den Besitz, den Status einer gemeinnützigen Organisation oder eines Bildungsbereichs nachzuweisen, oder um Yammer zu aktivieren,](../setup/domains-faq.yml) um sicherzustellen, dass Sie alle erforderlichen Schritte ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d15bb-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](../setup/domains-faq.yml) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="d15bb-144">Der Vorgang ist für jede Situation ein wenig anders.</span><span class="sxs-lookup"><span data-stu-id="d15bb-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="d15bb-145">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="d15bb-145">Services not working with your domain?</span></span>
<span data-ttu-id="d15bb-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="d15bb-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="d15bb-147">Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d15bb-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="d15bb-148">Die Problembehandlung für Domänen in Microsoft 365 zeigt Alle Datensätze an, die korrigiert werden müssen, und genau, auf welche Datensätze festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="d15bb-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="d15bb-149">Sie haben Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail-Nachrichten funktionieren in Outlook auf dem Desktop nicht?</span><span class="sxs-lookup"><span data-stu-id="d15bb-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="d15bb-150">Sehen Sie sich die [verschiedenen E-Mail-Flussszenarien an,](/exchange/mail-flow-best-practices/mail-flow-best-practices) die Sie mit Microsoft 365 haben können, um sicherzustellen, dass Sie alles richtig für Ihr Unternehmen eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="d15bb-150">Check out the [different mail flow scenarios you can have with Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="d15bb-151">Darüber hinaus finden Sie hier weitere Hilfe zur Problembehandlung im Zusammenhang mit E-Mails: [Beheben von Problemen mit Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="d15bb-151">Or get more troubleshooting help with email here: [Fix Outlook problems](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="d15bb-152">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="d15bb-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="d15bb-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="d15bb-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="d15bb-154">Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="d15bb-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="d15bb-155">Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="d15bb-155">People can't get to your website at www.mydomain.com: [Track down website issues](../setup/add-domain.md)</span></span>
    
- <span data-ttu-id="d15bb-156">Sie können Ihren A- oder CNAME-Eintrag nicht so aktualisieren, dass er auf Ihre Website verweist: [Aktualisieren von benutzerdefinierten DNS-Einträgen in Microsoft 365](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="d15bb-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../setup/add-domain.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="d15bb-157">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="d15bb-157">Related content</span></span>

<span data-ttu-id="d15bb-158">[Problembehandlung: Überwachen von Daten zu überprüften Domänenänderungen](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d15bb-158">[Troubleshoot: Audit data on verified domain change](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (article)</span></span>\
<span data-ttu-id="d15bb-159">[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="d15bb-159">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

