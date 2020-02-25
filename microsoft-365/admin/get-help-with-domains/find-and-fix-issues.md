---
title: Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Erfahren Sie, wie Sie Probleme einkreisen können, die beim Einrichten einer benutzerdefinierten Domäne auftreten. Stellen Sie zunächst sicher, dass die DNS-Einträge ordnungsgemäß eingerichtet sind.
ms.openlocfilehash: 277e87ad6b06db0b1ef3b3cb5eaaa45a2e77ed6f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252957"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a><span data-ttu-id="582de-103">Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge in Office 365 hinzugefügt wurden</span><span class="sxs-lookup"><span data-stu-id="582de-103">Find and fix issues after adding your domain or DNS records in Office 365</span></span>

 <span data-ttu-id="582de-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="582de-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="582de-p101">Das Einrichten Ihrer Domäne für die Zusammenarbeit mit Office 365 kann eine Herausforderung darstellen. Das DNS-System kann sich bei der Arbeit als recht anspruchsvoll erweisen, und außerdem wirkt sich die DNS-Einrichtung für Ihre Domäne auf wichtige geschäftliche Aktivitäten wie z. B. E-Mail aus!</span><span class="sxs-lookup"><span data-stu-id="582de-p101">Getting your domain set up to work with Office 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="582de-107">Sie können nach Problemen mit Ihrer Domäne suchen, indem Sie deren Status überprüfen.</span><span class="sxs-lookup"><span data-stu-id="582de-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="582de-108">Wechseln Sie zu **Einstellungen** > **Domänen**, und zeigen Sie die Benachrichtigungen in der Spalte **Status** an.</span><span class="sxs-lookup"><span data-stu-id="582de-108">Go to **Settings** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="582de-109">Wenn ein Problem angezeigt wird, wählen Sie „Weitere Aktionen“ aus (die drei Punkte), und wählen Sie dann **Integrität überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="582de-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="582de-110">In dem Bereich, der nun geöffnet wird, werden alle mit Ihrer Domäne auftretenden Probleme beschrieben.</span><span class="sxs-lookup"><span data-stu-id="582de-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="582de-111">Was ist los?</span><span class="sxs-lookup"><span data-stu-id="582de-111">What's going on?</span></span>

- [<span data-ttu-id="582de-112">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="582de-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="582de-113">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="582de-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="582de-114">Die E-Mail-Adressen aller Benutzer wurden auf Office 365 umgestellt, Sie wollten jedoch, dass nur IHRE E-Mail-Adresse umgestellt wird?</span><span class="sxs-lookup"><span data-stu-id="582de-114">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="582de-115">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="582de-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="582de-116">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="582de-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="582de-117">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="582de-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="582de-118">Sie können Ihre Domäne nicht überprüfen?</span><span class="sxs-lookup"><span data-stu-id="582de-118">Can't verify your domain?</span></span>
<span data-ttu-id="582de-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="582de-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="582de-120">Es gibt einige häufige Gründe dafür, dass die Domänenüberprüfung nicht wie gewünscht funktioniert:</span><span class="sxs-lookup"><span data-stu-id="582de-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="582de-p103">**Der Wert des Prüfeintrags ist nicht ganz korrekt.** Vergewissern Sie sich, dass Sie den exakten Wert kopiert und in den TXT-Prüfeintrag bei Ihrem DNS-Host eingefügt haben. Ein häufiges Problem ist, dass der Teil "MS=" des Eintrags fehlt. Diese Angabe ist ebenfalls erforderlich!</span><span class="sxs-lookup"><span data-stu-id="582de-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="582de-p104">**Der Eintrag wurde nicht gespeichert.** Bei einigen DNS-Hosts müssen Sie einen zusätzlichen Schritt ausführen, um die Zonendatei zu speichern (in der der DNS-Eintrag gespeichert ist), damit der Eintrag im Internet aktualisiert wird. Stellen Sie sicher, dass Sie die Änderungen gespeichert haben, damit der Eintrag von Office 365 angezeigt und überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="582de-p104">**The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Office 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="582de-128">**Der Eintrag wurde noch nicht im Internet aktualisiert.**</span><span class="sxs-lookup"><span data-stu-id="582de-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="582de-129">In der Regel dauert es nur ein paar Minuten, bis wir den neuen Eintrag sehen können, aber gelegentlich kann es auch ein paar Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="582de-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="582de-130">Outlook funktioniert nicht?</span><span class="sxs-lookup"><span data-stu-id="582de-130">Outlook isn't working?</span></span>
<span data-ttu-id="582de-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="582de-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="582de-132">Wenn Sie Ihren MX-Eintrag und andere DNS-Einträge für Ihre Domäne ordnungsgemäß eingerichtet haben, aber Ihr E-Mail-Programm nicht funktioniert, können wir Ihnen dabei helfen, [Ihre Probleme mit Outlook zu beheben](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="582de-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span>
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="582de-133">Die E-Mail-Adressen aller Benutzer wurden auf Office 365 umgestellt, Sie wollten jedoch, dass nur IHRE E-Mail-Adresse umgestellt wird?</span><span class="sxs-lookup"><span data-stu-id="582de-133">Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="582de-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="582de-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="582de-135">Wenn Sie Ihre Domäne zu Office 365 hinzufügen, wird in der Regel der MX-Eintrag der Domäne (durch Sie oder Office 365) so aktualisiert, dass er auf Office 365 verweist und dass ALLE an diese Domäne gesendeten E-Mails von Office 365 empfangen werden. </span><span class="sxs-lookup"><span data-stu-id="582de-135">When you add your domain to Office 365, typically your domain's MX record is updated (by you or Office 365) to point to Office 365, and ALL email sent to that domain will start coming to Office 365.</span></span> <span data-ttu-id="582de-136">Sorgen Sie dafür, dass Sie in Office 365 Postfächer für alle Personen erstellt haben, die in Ihrer Domäne über E-Mail verfügen, BEVOR Sie den MX-Eintrag ändern. </span><span class="sxs-lookup"><span data-stu-id="582de-136">Make sure you've created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="582de-137">Sie möchten nicht für jeden in Ihrer Domäne E-Mails nach Office 365 verschieben?</span><span class="sxs-lookup"><span data-stu-id="582de-137">What if you don't want to move email for everyone on your domain to Office 365?</span></span> <span data-ttu-id="582de-138">Sie können stattdessen [ein Pilotprojekt mit Office 365 und nur wenigen E-Mail-Adressen in die Wege leiten](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx). </span><span class="sxs-lookup"><span data-stu-id="582de-138">You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="582de-139">Sie können den Status eines Schulkontos oder des Kontos einer gemeinnützigen Organisation nicht bestätigen?</span><span class="sxs-lookup"><span data-stu-id="582de-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="582de-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="582de-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="582de-141">Es gibt eine Reihe von Szenarios, in denen Sie lediglich die Domäne Ihrer Organisation bestätigen und keine Dienste einrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="582de-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="582de-142">Beispielsweise um Office 365 nachzuweisen, dass Ihre Organisation zu einem Schul-Abonnement berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="582de-142">For example, to prove to Office 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="582de-143">Lesen Sie den Leitfaden in [Überprüfen der Office 365-Domäne zum Bestätigen des Besitzrechts, des gemeinnützigen oder Ausbildungsstatus oder zum Aktivieren von Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590), um sicherzustellen, dass Sie alle erforderlichen Schritte ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="582de-143">Check out the guidance in [Verify your Office 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="582de-144">Der Vorgang ist für jede Situation ein wenig anders.</span><span class="sxs-lookup"><span data-stu-id="582de-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="582de-145">Dienste funktionieren nicht mit Ihrer Domäne?</span><span class="sxs-lookup"><span data-stu-id="582de-145">Services not working with your domain?</span></span>
<span data-ttu-id="582de-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="582de-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="582de-147">Wir können Sie beim Diagnostizieren von Problemen mit der DNS-Einrichtung Ihrer Domäne unterstützen.</span><span class="sxs-lookup"><span data-stu-id="582de-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="582de-148">Die Problembehandlung bei Domänen in Office 365 zeigt alle Einträge an, die korrigiert werden müssen, und gibt genau an, wie die Einträge festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="582de-148">The domains troubleshooter in Office 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="582de-p111">Sie haben Ihr DNS ordnungsgemäß eingerichtet, aber E-Mail-Nachrichten funktionieren in Outlook auf dem Desktop nicht? Lesen Sie [Unterschiedliche Szenarien für den E-Mail-Fluss in Office 365](https://go.microsoft.com/fwlink/?LinkId=787530), um sicherzustellen, dass alles für Ihr Unternehmen ordnungsgemäß eingerichtet ist. Darüber hinaus finden Sie hier weitere Hilfe zur Problembehandlung im Zusammenhang mit E-Mails: [Beheben von Problemen mit Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span><span class="sxs-lookup"><span data-stu-id="582de-p111">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="582de-152">Sie können nicht auf Ihre Website zugreifen?</span><span class="sxs-lookup"><span data-stu-id="582de-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="582de-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="582de-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="582de-154">Wenn Sie alle DNS-Probleme behoben haben, aber weiterhin Probleme auftreten, führen Sie eine der folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="582de-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="582de-155">Benutzer können auf Ihre Website unter "www.mydomain.com" nicht zugreifen: [Diagnostizieren von Websiteproblemen](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span><span class="sxs-lookup"><span data-stu-id="582de-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)</span></span>
    
- <span data-ttu-id="582de-156">Sie können Ihren A-Eintrag oder CNAME-Eintrag nicht so aktualisieren, dass er auf Ihre Website verweist: [Aktualisieren von benutzerdefinierten DNS-Einträgen in Office 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="582de-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Office 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
