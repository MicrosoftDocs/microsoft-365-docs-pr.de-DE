---
title: Scheduler für Microsoft 365 FAQs
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Scheduler für Microsoft 365 FAQs
ms.openlocfilehash: d4cedf420dd605d04328b7f1edeabbd4e1bb5ac7
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809165"
---
# <a name="scheduler-for-microsoft-365-faqs"></a><span data-ttu-id="af78c-103">Scheduler für Microsoft 365 FAQs</span><span class="sxs-lookup"><span data-stu-id="af78c-103">Scheduler for Microsoft 365 FAQs</span></span>

<span data-ttu-id="af78c-104">**Frage:** Wie lässt sich Scheduler in andere Cortana-Features integrieren, z. B. *Cortana für Windows,* *tägliche Briefing-E-Mail* und *Meine E-Mails wiedergeben?*</span><span class="sxs-lookup"><span data-stu-id="af78c-104">**Question:** How does Scheduler integrate with other Cortana features, such as *Cortana for Windows*, *Daily Briefing Email*, and *Play My Emails*?</span></span></br>
<span data-ttu-id="af78c-105">Scheduler ist ein unabhängiger Dienst von anderen Cortana-Features.</span><span class="sxs-lookup"><span data-stu-id="af78c-105">Scheduler is an independent service from other Cortana features.</span></span> <span data-ttu-id="af78c-106">Andere Cortana-Features können auf Mandantenebene deaktiviert werden, und scheduler kann weiterhin mithilfe der cortana@yourdomain.com E-Mail-Adresse aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="af78c-106">Other Cortana features can be disabled at the tenant level, and Scheduler can still be enabled by using the cortana@yourdomain.com email address.</span></span> <span data-ttu-id="af78c-107">Derzeit können Benutzer nur per E-Mail mit Scheduler interagieren.</span><span class="sxs-lookup"><span data-stu-id="af78c-107">Currently, users can only interact with Scheduler via email.</span></span>

<span data-ttu-id="af78c-108">**Frage:** Funktioniert dies nur mit Outlook?</span><span class="sxs-lookup"><span data-stu-id="af78c-108">**Question:** Does this work only with Outlook?</span></span> <span data-ttu-id="af78c-109">Werden andere E-Mail-Produkte unterstützt?</span><span class="sxs-lookup"><span data-stu-id="af78c-109">Are other email products supported?</span></span></br>
<span data-ttu-id="af78c-110">Solange Sie über eine Lizenz verfügen, außer den drei oben genannten Anforderungen, können Benutzer cortana@yourdomain.com von jedem E-Mail-Client auf jedem Gerät per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="af78c-110">As long as you have a license, other than the three requirements above, users can email cortana@yourdomain.com from any email client on any device.</span></span>

<span data-ttu-id="af78c-111">**Frage:** Können Sich Kontakte in einer persönlichen Kontaktliste auf Outlook und GAL oder einem anderen Unternehmen befinden?</span><span class="sxs-lookup"><span data-stu-id="af78c-111">**Question:** Can contacts be in a personal contact list on Outlook and GAL or other company equivalent?</span></span></br>
<span data-ttu-id="af78c-112">Besprechungsteilnehmer können alle Personen sein, die eine E-Mail-Adresse innerhalb oder außerhalb des Unternehmens haben.</span><span class="sxs-lookup"><span data-stu-id="af78c-112">Meeting attendees can be anyone with an email address inside or outside the company.</span></span> <span data-ttu-id="af78c-113">Leider kann Scheduler Namen nicht automatisch in E-Mail-Adressen/Aliase übersetzen, indem er sie heute in der GAL nachschlägt.</span><span class="sxs-lookup"><span data-stu-id="af78c-113">Unfortunately, Scheduler cannot automatically translate names to email addresses / alias by looking it up in the GAL today.</span></span>

<span data-ttu-id="af78c-114">**Frage:** Kann ich Scheduler mit meiner installierten (lokalen) Version von Outlook verwenden?</span><span class="sxs-lookup"><span data-stu-id="af78c-114">**Question:** Can I use Scheduler with my installed version (on-premises) version of Outlook?</span></span></br>
<span data-ttu-id="af78c-115">Der Scheduler erfordert Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="af78c-115">Scheduler requires Exchange Online.</span></span> <span data-ttu-id="af78c-116">Funktioniert nicht mit Exchange Server (lokal).</span><span class="sxs-lookup"><span data-stu-id="af78c-116">Does not work with Exchange Server (On-prem).</span></span> <span data-ttu-id="af78c-117">Funktioniert mit jedem E-Mail-Client, Outlook Desktop, OWA, iOS, Android, Gmail usw.</span><span class="sxs-lookup"><span data-stu-id="af78c-117">Works with any email client, Outlook Desktop, OWA, iOS, android, gmail, and so on.</span></span>

<span data-ttu-id="af78c-118">**Frage:** Muss Outlook im Hintergrund geöffnet sein?</span><span class="sxs-lookup"><span data-stu-id="af78c-118">**Question:** Does Outlook have to be open in the background?</span></span></br>
<span data-ttu-id="af78c-119">Outlook muss nicht im Hintergrund geöffnet sein.</span><span class="sxs-lookup"><span data-stu-id="af78c-119">Outlook doesn't need to be open in the background.</span></span> <span data-ttu-id="af78c-120">Sie müssen cortana lediglich eine E-Mail senden und sich darauf verlassen, dass sie den Großteil der Arbeit erledigt.</span><span class="sxs-lookup"><span data-stu-id="af78c-120">All you need to do is send Cortana a mail and rely on it to do the bulk of the work.</span></span>

## <a name="frequently-asked-trust-and-privacy-questions"></a><span data-ttu-id="af78c-121">Häufig gestellte Vertrauens- und Datenschutzfragen</span><span class="sxs-lookup"><span data-stu-id="af78c-121">Frequently Asked Trust and Privacy Questions</span></span>

<span data-ttu-id="af78c-122">**Frage:** Wie funktioniert Scheduler?</span><span class="sxs-lookup"><span data-stu-id="af78c-122">**Question:** How does Scheduler work?</span></span></br>
<span data-ttu-id="af78c-123">Scheduler verwendet Planungsintelligenz (SCHEDULING Intelligence, KI), die mit menschlichen Assistenten erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="af78c-123">Scheduler uses Scheduling Intelligence (AI) augmented with human assistants.</span></span> <span data-ttu-id="af78c-124">Wenn KI-Modelle Unterstützung in der natürlichen Sprache der Kommunikation mit Cortana generieren, eskaliert die Besprechungsanfrage zur Überprüfung und Zum Abschluss an einen Menschen.</span><span class="sxs-lookup"><span data-stu-id="af78c-124">If AI models generate a need for support in the natural language of communication with Cortana, the meeting request escalates to a human for review and completion.</span></span>

<span data-ttu-id="af78c-125">**Frage:** Wer sind die Menschen, die eskalierte Anforderungen überprüfen?</span><span class="sxs-lookup"><span data-stu-id="af78c-125">**Question:** Who are the humans that review escalated requests?</span></span> </br>
<span data-ttu-id="af78c-126">Planerassistenten sind Microsoft Supplier Security and Privacy Assurance (SSPA) für persönliche und streng vertrauliche Informationen zertifiziert.</span><span class="sxs-lookup"><span data-stu-id="af78c-126">Scheduler assistants are Microsoft Supplier Security and Privacy Assurance (SSPA) certified for personal and highly confidential information.</span></span> 

<span data-ttu-id="af78c-127">**Frage:** Was können SSPA-Assistenten anzeigen?</span><span class="sxs-lookup"><span data-stu-id="af78c-127">**Question:** What can SSPA Assistants view?</span></span></br>
<span data-ttu-id="af78c-128">Der Planer und die SSPA-Assistenten können die E-Mails anzeigen, die an Cortana adressiert sind.</span><span class="sxs-lookup"><span data-stu-id="af78c-128">Scheduler and the SSPA Assistants can view  the emails that are addressed to Cortana.</span></span> <span data-ttu-id="af78c-129">In einem Thread-E-Mail-Austausch werden nur die E-Mails verarbeitet, die Cortanas E-Mail-Adresse enthalten, nicht die vorherigen E-Mails im Thread, bevor Cortana hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="af78c-129">In a threaded email exchange, only the emails that include Cortana’s email address will be processed, not the previous emails in the thread before Cortana was added.</span></span>   

<span data-ttu-id="af78c-130">**Frage:** Werden Kundendaten in den Daten Flow des Planers aufbewahrt?</span><span class="sxs-lookup"><span data-stu-id="af78c-130">**Question:** Is customer data retained in the Scheduler’s Data Flow?</span></span> </br>
<span data-ttu-id="af78c-131">Scheduler speichert alle Kundeninhalte innerhalb der Mandantengrenzen und speichert Daten gemäß dsgvo-Richtlinien, Microsoft 365 Trust & Datenschutzrichtlinien und Mandanten-E-Mail-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="af78c-131">Scheduler stores all customer content within the tenant boundaries and retains data in accordance with GDPR guidelines, Microsoft 365 Trust & Privacy policies, and tenant email policies.</span></span>

<span data-ttu-id="af78c-132">**Frage:** Wie verarbeitet Scheduler die Frei/Gebucht-Daten interner Teilnehmer?</span><span class="sxs-lookup"><span data-stu-id="af78c-132">**Question:** How does Scheduler process the free/busy data of internal attendees?</span></span> </br>
<span data-ttu-id="af78c-133">Die Automatisierung des Schedulers verwendet den *findMeetingTimes-Dienst,* um Zeiten zu identifizieren, die für Teilnehmer und den Organisator gegenseitig verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="af78c-133">Scheduler’s automation uses the *findMeetingTimes* service to identify times that are mutually available for attendees and the organizer.</span></span> <span data-ttu-id="af78c-134">Dieser Dienst unterstützt andere Outlook Wie z. *B. vorgeschlagene Uhrzeiten* im Outlook Besprechungsformular.</span><span class="sxs-lookup"><span data-stu-id="af78c-134">This service powers other Outlook experiences such as *Suggested Times* in the Outlook meeting form.</span></span> <span data-ttu-id="af78c-135">Frei/Gebucht-Teilnehmerinformationen werden nicht explizit als Frei/Gebucht-Blöcke genutzt.</span><span class="sxs-lookup"><span data-stu-id="af78c-135">Free/busy attendee information is not consumed explicitly as free/busy blocks.</span></span> 

<span data-ttu-id="af78c-136">**Frage:** Ist Scheduler DSGVO-konform?</span><span class="sxs-lookup"><span data-stu-id="af78c-136">**Question:** Is Scheduler GDPR Compliant?</span></span> </br>
<span data-ttu-id="af78c-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="af78c-137">Yes.</span></span>

<span data-ttu-id="af78c-138">**Frage:** Wer Zugriff auf das Cortana-Postfach hat?</span><span class="sxs-lookup"><span data-stu-id="af78c-138">**Question:** Who has access to the Cortana mailbox?</span></span> </br>
<span data-ttu-id="af78c-139">Der Planer verarbeitet Besprechungsanfragen und zugehörige E-Mails, die an das Cortana-Postfach Ihres Mandanten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="af78c-139">Scheduler processes meeting requests and associated emails that are sent to your tenant’s Cortana mailbox.</span></span> <span data-ttu-id="af78c-140">Microsoft hat keinen anderen Zugriff auf das Cortana-Postfach, außer über die Lockbox-Genehmigung auf Anforderung des Mandantenadministrators.</span><span class="sxs-lookup"><span data-stu-id="af78c-140">Microsoft does not have any other access to the Cortana mailbox except through Lockbox approval at the request of the tenant admin.</span></span>  

<span data-ttu-id="af78c-141">**Frage:** Werden Kundendaten für die Schulung von KI-Modellen verwendet?</span><span class="sxs-lookup"><span data-stu-id="af78c-141">**Question:** Is customer data used for training AI models?</span></span></br>
<span data-ttu-id="af78c-142">Es können keine Kundeninhalte von Scheduler für Microsoft 365 für Datenschulungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af78c-142">No customer content from Scheduler for Microsoft 365 can be used for data training sets.</span></span> <span data-ttu-id="af78c-143">Alle Kundeninhalte befinden sich im Kundenmandanten.</span><span class="sxs-lookup"><span data-stu-id="af78c-143">All customer content resides in the customer tenant.</span></span>  

<span data-ttu-id="af78c-144">**Frage:** Verarbeitet Scheduler verschlüsselte E-Mails?</span><span class="sxs-lookup"><span data-stu-id="af78c-144">**Question:** Will Scheduler process encrypted mail?</span></span></br>
<span data-ttu-id="af78c-145">Nein, verschlüsselte E-Mails werden vom Scheduler-Workflow abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="af78c-145">No, encrypted mail will be rejected by the Scheduler workflow.</span></span> 




