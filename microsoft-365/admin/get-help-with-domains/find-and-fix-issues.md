---
title: Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden
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
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: 0a315be243395940146479e05de2c7044a5a36ab
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560251"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="78a4d-103">Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="78a4d-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="78a4d-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="78a4d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="78a4d-p101">Das Einrichten Ihrer Domäne für die Zusammenarbeit mit Microsoft 365 kann eine Herausforderung darstellen. Das DNS-System ist Nitpicky, mit dem Sie arbeiten können, und das DNS-Setup für Ihre Domäne betrifft wichtige geschäftliche Aktivitäten wie e-Mail!</span><span class="sxs-lookup"><span data-stu-id="78a4d-p101">Getting your domain set up to work with Microsoft 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="78a4d-107">Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen.</span><span class="sxs-lookup"><span data-stu-id="78a4d-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="78a4d-108">Wechseln Sie zu **Setup**  >  **Domänen** , und zeigen Sie die Benachrichtigungen in der Spalte **Status** an.</span><span class="sxs-lookup"><span data-stu-id="78a4d-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="78a4d-109">Wenn ein Problem angezeigt wird, wählen Sie „Weitere Aktionen“ aus (die drei Punkte), und wählen Sie dann **Integrität überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="78a4d-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="78a4d-110">In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78a4d-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="78a4d-111">Was ist los?</span><span class="sxs-lookup"><span data-stu-id="78a4d-111">What's going on?</span></span>

- [<span data-ttu-id="78a4d-112">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="78a4d-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="78a4d-113">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="78a4d-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="78a4d-114">Alle e-Mails wurden zu Microsoft 365 gewechselt, und Sie wollten nur, dass Ihre e-Mail gewechselt wird?</span><span class="sxs-lookup"><span data-stu-id="78a4d-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="78a4d-115">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="78a4d-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="78a4d-116">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="78a4d-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="78a4d-117">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="78a4d-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="78a4d-118">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="78a4d-118">Can't verify your domain?</span></span>
<span data-ttu-id="78a4d-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="78a4d-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="78a4d-120">Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:</span><span class="sxs-lookup"><span data-stu-id="78a4d-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="78a4d-p103">**Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich!</span><span class="sxs-lookup"><span data-stu-id="78a4d-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="78a4d-p104">**Der Datensatz wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei (in der der DNS-Eintrag gespeichert ist) zu speichern, damit Sie über das Internet aktualisiert wird. Stellen Sie sicher, dass Sie Ihre Änderungen gespeichert haben, damit Microsoft 365 den Datensatz sehen und überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="78a4d-p104">**The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="78a4d-128">**Der Eintrag wurde noch nicht im Internet aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="78a4d-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="78a4d-129">In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="78a4d-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="78a4d-130">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="78a4d-130">Outlook isn't working?</span></span>
<span data-ttu-id="78a4d-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="78a4d-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="78a4d-132">Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="78a4d-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="78a4d-133">Alle e-Mails wurden zu Microsoft 365 gewechselt, und Sie wollten nur, dass Ihre e-Mail gewechselt wird?</span><span class="sxs-lookup"><span data-stu-id="78a4d-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="78a4d-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="78a4d-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="78a4d-135">Wenn Sie Ihre Domäne zu Microsoft 365 hinzufügen, wird der MX-Eintrag Ihrer Domäne in der Regel aktualisiert (von Ihnen oder von Microsoft 365), um auf Microsoft 365 zu deuten, und alle e-Mails, die an diese Domäne gesendet werden, beginnen mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78a4d-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="78a4d-136">Stellen Sie sicher, dass Sie in Microsoft 365 Postfächer für alle Benutzer erstellt haben, die e-Mails in Ihrer Domäne haben, bevor Sie den MX-Eintrag ändern.</span><span class="sxs-lookup"><span data-stu-id="78a4d-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="78a4d-137">Was geschieht, wenn Sie e-Mails nicht für alle Benutzer Ihrer Domäne nach Microsoft 365 bewegen möchten?</span><span class="sxs-lookup"><span data-stu-id="78a4d-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="78a4d-138">Sie können [stattdessen ein Pilotprojekt von Microsoft 365 mit nur wenigen e-Mail-Adressen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)ausführen.</span><span class="sxs-lookup"><span data-stu-id="78a4d-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="78a4d-139">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="78a4d-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="78a4d-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="78a4d-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="78a4d-141">Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="78a4d-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="78a4d-142">Um beispielsweise Microsoft 365 zu beweisen, dass Ihre Organisation für ein Schul Abonnement qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="78a4d-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="78a4d-143">Lesen Sie den Leitfaden unter [verify your Microsoft 365 Domain to prove Ownership, Non-Profit oder Education Status, oder aktivieren Sie jammern](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) , um sicherzustellen, dass Sie alle erforderlichen Schritte abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="78a4d-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="78a4d-144">Der Vorgang ist für jede Situation ein wenig anders.</span><span class="sxs-lookup"><span data-stu-id="78a4d-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="78a4d-145">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="78a4d-145">Services not working with your domain?</span></span>
<span data-ttu-id="78a4d-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="78a4d-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="78a4d-147">Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen.</span><span class="sxs-lookup"><span data-stu-id="78a4d-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="78a4d-148">In der Domänen-Problembehandlung in Microsoft 365 werden alle Datensätze angezeigt, die repariert werden müssen, und genau das, worauf die Datensätze festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="78a4d-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="78a4d-p111">Haben Sie Ihren DNS richtig eingerichtet, aber e-Mails funktionieren nicht in Outlook auf Ihrem Desktop? Sehen Sie sich die [unterschiedlichen Nachrichtenfluss Szenarien an, die Sie mit Microsoft 365 haben können](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) , um sicherzustellen, dass Sie die Dinge ordnungsgemäß für Ihr Unternehmen eingerichtet haben. Weitere Informationen zur Problembehandlung mit e-Mails finden Sie hier: [Beheben von Outlook-Problemen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="78a4d-p111">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="78a4d-152">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="78a4d-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="78a4d-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="78a4d-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="78a4d-154">Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="78a4d-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="78a4d-155">Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="78a4d-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="78a4d-156">Sie können einen Eintrag oder CNAME-Eintrag nicht so aktualisieren, dass er auf Ihre Website verweist: [Aktualisieren von benutzerdefinierten DNS-Einträgen in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="78a4d-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
