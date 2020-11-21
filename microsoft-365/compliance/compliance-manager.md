---
title: Microsoft Compliance-Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager unterstützt Organisationen bei der Vereinfachung und Automatisierung von Risikobewertungen und schlägt Empfohlene Maßnahmen zur Behandlung von Risiken vor.
ms.openlocfilehash: 7bff6a2a7a150a08b98fe7a92cd71d266df9fda7
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376546"
---
# <a name="microsoft-compliance-manager"></a><span data-ttu-id="262e5-103">Microsoft Compliance-Manager</span><span class="sxs-lookup"><span data-stu-id="262e5-103">Microsoft Compliance Manager</span></span>

<span data-ttu-id="262e5-104">**In diesem Artikel:** Erfahren Sie, was Compliance-Manager ist, wie Sie die Compliance vereinfachen und Risiken reduzieren können, sowie die wichtigsten Komponenten.</span><span class="sxs-lookup"><span data-stu-id="262e5-104">**In this article:** Learn what Compliance Manager is, how it helps simplify compliance and reduce risk, and its key components.</span></span>

## <a name="whats-new-the-ga-release-of-compliance-manager"></a><span data-ttu-id="262e5-105">Neuerungen: die GA-Version von Compliance-Manager</span><span class="sxs-lookup"><span data-stu-id="262e5-105">What's new: the GA release of Compliance Manager</span></span>

<span data-ttu-id="262e5-106">Compliance-Manager ist jetzt allgemein (GA) als End-to-End-Compliance-Verwaltungslösung im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="262e5-106">Compliance Manager is now generally available (GA) as an end-to-end compliance management solution inside the [Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span> <span data-ttu-id="262e5-107">Mit dieser Version schließt Compliance-Manager den Übergang von seinem vorherigen Speicherort im Microsoft Service Trust-Portal ab.</span><span class="sxs-lookup"><span data-stu-id="262e5-107">With this release, Compliance Manager completes the transition from its previous location in the Microsoft Service Trust Portal.</span></span> <span data-ttu-id="262e5-108">Compliance-Manager steht nun auch für US Government Community (gcc) moderate und gcc High Customers zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="262e5-108">Compliance Manager is also now available to US Government Community (GCC) Moderate and GCC High customers.</span></span>

<span data-ttu-id="262e5-109">Was als Public Preview of Compliance Score begann, hat sich zu einem zentralisierten Tool mit verbesserten Compliance-Verwaltungsfunktionen und größerer Benutzerfreundlichkeit entwickelt.</span><span class="sxs-lookup"><span data-stu-id="262e5-109">What began as the public preview of Compliance Score has evolved into a centralized tool with enhanced compliance management capabilities and greater ease of use.</span></span>  <span data-ttu-id="262e5-110">Die GA-Version enthält eine größere Sammlung vordefinierter Bewertungen, die Sie bei der Skalierung Ihrer Compliance-Aktivitäten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="262e5-110">The GA release brings a larger collection of pre-built assessments to help you scale your compliance activities.</span></span>

<span data-ttu-id="262e5-111">**Erfahren Sie mehr über die GA-Version:**</span><span class="sxs-lookup"><span data-stu-id="262e5-111">**Learn more about the GA release:**</span></span>
- <span data-ttu-id="262e5-112">Unsere [häufig gestellten Fragen](compliance-manager-faq.md) begleiten Sie ausführlich durch die Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="262e5-112">Our [frequently asked questions](compliance-manager-faq.md) walk you through the evolution in greater detail.</span></span>
- <span data-ttu-id="262e5-113">Lesen Sie mehr über GA-Funktionsverbesserungen in [diesem Blogbeitrag](https://aka.ms/compliancemanager/GAblog).</span><span class="sxs-lookup"><span data-stu-id="262e5-113">Read about GA feature enhancements in [this blog post](https://aka.ms/compliancemanager/GAblog).</span></span>

<span data-ttu-id="262e5-114">Sehen Sie sich das Video unten an, um zu erfahren, wie Compliance-Manager die Compliance-Verwaltung in Ihrer Organisation vereinfachen kann:</span><span class="sxs-lookup"><span data-stu-id="262e5-114">Watch the video below to learn how Compliance Manager can help simplify how your organization manages compliance:</span></span>
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a><span data-ttu-id="262e5-115">Was ist Compliance-Manager?</span><span class="sxs-lookup"><span data-stu-id="262e5-115">What is Compliance Manager</span></span>

<span data-ttu-id="262e5-116">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) ist ein Feature im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md) , mit dem Sie die Compliance-Anforderungen Ihrer Organisation mit größerer Leichtigkeit und Bequemlichkeit verwalten können.</span><span class="sxs-lookup"><span data-stu-id="262e5-116">[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that helps you manage your organization’s compliance requirements with greater ease and convenience.</span></span> <span data-ttu-id="262e5-117">Compliance-Manager kann Sie während der gesamten Compliance-Reise unterstützen, von der Bestandsaufnahme ihrer Datenschutzrisiken bis hin zur Verwaltung der Komplexität der Implementierung von Steuerelementen, dem aktuellen Stand mit Vorschriften und Zertifizierungen sowie der Berichterstellung an Auditoren.</span><span class="sxs-lookup"><span data-stu-id="262e5-117">Compliance Manager can help you throughout your compliance journey, from taking inventory of your data protection risks to managing the complexities of implementing controls, staying current with regulations and certifications, and reporting to auditors.</span></span>

<span data-ttu-id="262e5-118">Compliance-Manager hilft, die Compliance zu vereinfachen und Risiken zu verringern, indem Sie:</span><span class="sxs-lookup"><span data-stu-id="262e5-118">Compliance Manager helps simplify compliance and reduce risk by providing:</span></span>

- <span data-ttu-id="262e5-119">Vordefinierte Bewertungen für gängige Branchen-und regionale Standards und Vorschriften oder benutzerdefinierte Bewertungen zur Erfüllung ihrer eindeutigen Compliance-Anforderungen (verfügbare Bewertungen hängen von Ihrem Lizenzvertrag ab; [Weitere Informationen](https://go.microsoft.com/fwlink/?linkid=2132371)).</span><span class="sxs-lookup"><span data-stu-id="262e5-119">Pre-built assessments for common industry and regional standards and regulations, or custom assessments to meet your unique compliance needs (available assessments depend on your licensing agreement; [learn more](https://go.microsoft.com/fwlink/?linkid=2132371)).</span></span>

- <span data-ttu-id="262e5-120">Workflow Funktionen, die Sie bei der effizienten Durchführung ihrer Risikobewertungen mithilfe eines einzigen Tools unterstützen.</span><span class="sxs-lookup"><span data-stu-id="262e5-120">Workflow capabilities to help you efficiently complete your risk assessments through a single tool.</span></span>

- <span data-ttu-id="262e5-121">Ausführliche Schritt-für-Schritt-Anleitungen zu vorgeschlagenen Verbesserungs Aktionen, die Ihnen dabei helfen, die für Ihre Organisation relevanten Standards und Vorschriften einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="262e5-121">Detailed step-by-step guidance on suggested improvement actions to help you comply with the standards and regulations that are most relevant for your organization.</span></span> <span data-ttu-id="262e5-122">Für Aktionen, die von Microsoft verwaltet werden, werden Implementierungsdetails und Überwachungsergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="262e5-122">For actions that are managed by Microsoft, you’ll see implementation details and audit results.</span></span>

- <span data-ttu-id="262e5-123">Eine risikobasierte Konformitätsbewertung, die Ihnen hilft, Ihre Compliance-Haltung zu verstehen, indem Sie Ihren Fortschritt beim Abschließen von Verbesserungs Aktionen messen.</span><span class="sxs-lookup"><span data-stu-id="262e5-123">A risk-based compliance score to help you understand your compliance posture by measuring your progress in completing improvement actions.</span></span>

<span data-ttu-id="262e5-124">Ihr Compliance-Manager-Dashboard zeigt das aktuelle Kompatibilitäts Ergebnis an, hilft Ihnen, die Aufmerksamkeit zu erfahren, und führt Sie zu wichtigen Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="262e5-124">Your Compliance Manager dashboard shows your current compliance score, helps you see what needs attention, and guides you to key improvement actions.</span></span> <span data-ttu-id="262e5-125">Unten sehen Sie ein Beispiel, wie Ihr Compliance-Manager-Dashboard aussehen wird:</span><span class="sxs-lookup"><span data-stu-id="262e5-125">Below is an example of what your Compliance Manager dashboard will look like:</span></span>

<span data-ttu-id="262e5-126">![Compliance-Manager – Dashboard](../media/compliance-manager-dashboard.png "Compliance-Manager-Dashboard")</span><span class="sxs-lookup"><span data-stu-id="262e5-126">![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Compliance Manager dashboard")</span></span>

## <a name="understanding-your-compliance-score"></a><span data-ttu-id="262e5-127">Grundlegendes zur Konformitätsbewertung</span><span class="sxs-lookup"><span data-stu-id="262e5-127">Understanding your compliance score</span></span>

<span data-ttu-id="262e5-128">Compliance-Manager vergibt Ihnen Punkte für die Durchführung von Verbesserungsmaßnahmen, die zur Einhaltung einer Richtlinie, eines Standards oder einer Richtlinie ergriffen wurden, und kombiniert diese Punkte in einer allgemeinen Konformitätsbewertung.</span><span class="sxs-lookup"><span data-stu-id="262e5-128">Compliance Manager awards you points for completing improvement actions taken to comply with a regulation, standard, or policy, and combines those points into an overall compliance score.</span></span> <span data-ttu-id="262e5-129">Jede Aktion unterscheidet sich je nach den potenziellen Risiken durch eine andere Auswirkung auf Ihre Bewertung.</span><span class="sxs-lookup"><span data-stu-id="262e5-129">Each action has a different impact on your score depending on the potential risks involved.</span></span> <span data-ttu-id="262e5-130">Ihre Konformitätsbewertung kann Ihnen dabei helfen, Prioritäten zu setzen, auf die Sie sich konzentrieren müssen, um Ihre allgemeine Compliance-Haltung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="262e5-130">Your compliance score can help prioritize which action to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="262e5-131">Compliance-Manager gibt Ihnen eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis.</span><span class="sxs-lookup"><span data-stu-id="262e5-131">Compliance Manager gives you an initial score based on the Microsoft 365 data protection baseline.</span></span> <span data-ttu-id="262e5-132">Dieser Basisplan umfasst eine Reihe von Steuerelementen, die wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung beinhalten.</span><span class="sxs-lookup"><span data-stu-id="262e5-132">This baseline is a set of controls that includes key regulations and standards for data protection and general data governance.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="262e5-133">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="262e5-133">Learn more</span></span>

<span data-ttu-id="262e5-134">Grund [Legendes zur Berechnung der Konformitätsbewertung](compliance-score-calculation.md)</span><span class="sxs-lookup"><span data-stu-id="262e5-134">[Understand how your compliance score is calculated](compliance-score-calculation.md).</span></span>

<span data-ttu-id="262e5-135">[Erfahren Sie, wie Sie mit Verbesserungs Aktionen arbeiten](compliance-manager-improvement-actions.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-135">[Learn how to work with improvement actions](compliance-manager-improvement-actions.md).</span></span>

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a><span data-ttu-id="262e5-136">Wichtige Elemente: Steuerelemente, Bewertungen, Vorlagen, Verbesserungs Aktionen</span><span class="sxs-lookup"><span data-stu-id="262e5-136">Key elements: controls, assessments, templates, improvement actions</span></span>

<span data-ttu-id="262e5-137">Compliance-Manager verwendet mehrere Datenelemente, die Sie bei der Verwaltung Ihrer Compliance-Aktivitäten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="262e5-137">Compliance Manager uses several data elements to help you manage your compliance activities.</span></span> <span data-ttu-id="262e5-138">Wenn Sie den Compliance-Manager verwenden, um Compliance-Aktivitäten zuzuweisen, zu testen und zu überwachen, ist es hilfreich, ein grundlegendes Verständnis der wichtigsten Elemente zu haben: Steuerelemente, Bewertungen, Vorlagen und Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="262e5-138">As you use Compliance Manager to assign, test, and monitor compliance activities, it’s helpful to have a basic understanding of the key elements: controls, assessments, templates, and improvement actions.</span></span>

### <a name="controls"></a><span data-ttu-id="262e5-139">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="262e5-139">Controls</span></span>

<span data-ttu-id="262e5-140">Ein Steuerelement ist eine Anforderung einer Verordnung, eines Standards oder einer Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="262e5-140">A control is a requirement of a regulation, standard, or policy.</span></span> <span data-ttu-id="262e5-141">Es definiert, wie Sie die Systemkonfiguration, den Organisationsprozess und die Personen, die für die Erfüllung einer bestimmten Anforderung einer Richtlinie, eines Standards oder einer Richtlinie zuständig sind, bewerten und verwalten.</span><span class="sxs-lookup"><span data-stu-id="262e5-141">It defines how you assess and manage system configuration, organizational process, and people responsible for meeting a specific requirement of a regulation, standard, or policy.</span></span>

<span data-ttu-id="262e5-142">Compliance-Manager verfolgt die folgenden Arten von Steuerelementen:</span><span class="sxs-lookup"><span data-stu-id="262e5-142">Compliance Manager tracks the following types of controls:</span></span>

1. <span data-ttu-id="262e5-143">Von **Microsoft verwaltete Steuer** Elemente: Steuerelemente für Microsoft Cloud-Dienste, die von Microsoft für die Implementierung zuständig sind</span><span class="sxs-lookup"><span data-stu-id="262e5-143">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft is responsible for implementing</span></span>
2. <span data-ttu-id="262e5-144">**Ihre Steuerelemente**: manchmal auch als von Kunden verwaltete Steuerelemente bezeichnet, sind dies Steuerelemente, die von Ihrer Organisation implementiert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="262e5-144">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
3. <span data-ttu-id="262e5-145">**Gemeinsame Steuerelemente**: Dies sind Steuerelemente, die sowohl in Ihrer Organisation als auch in Microsoft für die Implementierung verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="262e5-145">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>

##### <a name="learn-more"></a><span data-ttu-id="262e5-146">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="262e5-146">Learn more</span></span>

<span data-ttu-id="262e5-147">[Überwachen Sie den Status Ihrer Steuerelemente](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span><span class="sxs-lookup"><span data-stu-id="262e5-147">[Monitor progress of your controls](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).</span></span>

<span data-ttu-id="262e5-148">[Erfahren Sie, wie Compliance-Manager Steuerelemente kontinuierlich bewertet](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span><span class="sxs-lookup"><span data-stu-id="262e5-148">[Learn how Compliance Manager continuously assesses controls](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).</span></span>

### <a name="assessments"></a><span data-ttu-id="262e5-149">Bewertungen</span><span class="sxs-lookup"><span data-stu-id="262e5-149">Assessments</span></span>

<span data-ttu-id="262e5-150">Bei einem Assessment handelt es sich um eine Gruppierung von Steuerelementen aus einer bestimmten Verordnung, einem Standard oder einer Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="262e5-150">An assessment is grouping of controls from a specific regulation, standard, or policy.</span></span> <span data-ttu-id="262e5-151">Durch das Abschließen der Aktionen innerhalb eines Assessments können Sie die Anforderungen eines Standards, einer Verordnung oder eines Gesetzes erfüllen.</span><span class="sxs-lookup"><span data-stu-id="262e5-151">Completing the actions within an assessment help you meet the requirements of a standard, regulation, or law.</span></span> <span data-ttu-id="262e5-152">Beispielsweise haben Sie möglicherweise eine Einschätzung, dass, wenn Sie alle darin enthaltenen Aktionen durchführen, Ihnen hilft, Ihre Microsoft 365-Einstellungen in Einklang mit den ISO 27001-Anforderungen zu bringen.</span><span class="sxs-lookup"><span data-stu-id="262e5-152">For example, you may have an assessment that, when you complete all actions within it, helps to bring your Microsoft 365 settings in line with ISO 27001 requirements.</span></span>

<span data-ttu-id="262e5-153">Assessments weisen mehrere Komponenten auf:</span><span class="sxs-lookup"><span data-stu-id="262e5-153">Assessments have several components:</span></span>

- <span data-ttu-id="262e5-154">**Im Bereich Dienste**: die spezifische Gruppe von Microsoft-Diensten, die für die Bewertung gelten.</span><span class="sxs-lookup"><span data-stu-id="262e5-154">**In-scope services**: the specific set of Microsoft services applicable to the assessment</span></span>
- <span data-ttu-id="262e5-155">Von Microsoft **verwaltete Steuer** Elemente: Steuerelemente für Microsoft Cloud-Dienste, die Microsoft in Ihrem Auftrag implementiert</span><span class="sxs-lookup"><span data-stu-id="262e5-155">**Microsoft managed controls**: controls for Microsoft cloud services, which Microsoft implements on your behalf</span></span>
- <span data-ttu-id="262e5-156">**Ihre Steuerelemente**: manchmal auch als von Kunden verwaltete Steuerelemente bezeichnet, sind dies Steuerelemente, die von Ihrer Organisation implementiert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="262e5-156">**Your controls**: sometimes referred to as customer managed controls, these are controls implemented and managed by your organization</span></span>
- <span data-ttu-id="262e5-157">**Gemeinsame Steuerelemente**: Dies sind Steuerelemente, die sowohl in Ihrer Organisation als auch in Microsoft für die Implementierung verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="262e5-157">**Shared controls**: these are controls that both your organization and Microsoft share responsibility for implementing</span></span>
- <span data-ttu-id="262e5-158">**Bewertungsergebnis**: zeigt den Fortschritt beim erreichen von Gesamt möglichen Punkten von Aktionen innerhalb der Bewertung an, die von Ihrer Organisation und von Microsoft verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="262e5-158">**Assessment score**: shows your progress in achieving total possible points from actions within the assessment that are managed by your organization and by Microsoft</span></span>

<span data-ttu-id="262e5-159">Beim Erstellen von Bewertungen weisen Sie diese einer Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="262e5-159">When creating assessments, you’ll assign them to a group.</span></span> <span data-ttu-id="262e5-160">Sie können Gruppen auf beliebige Weise konfigurieren, die für Ihre Organisation am logischsten ist.</span><span class="sxs-lookup"><span data-stu-id="262e5-160">You can configure groups in whatever way is most logical for your organization.</span></span> <span data-ttu-id="262e5-161">Sie können beispielsweise Bewertungen nach Überwachungsjahr, Region, Lösung, Teams in Ihrer Organisation oder auf andere Weise gruppieren.</span><span class="sxs-lookup"><span data-stu-id="262e5-161">For example, you may group assessments by audit year, region, solution, teams within your organization, or some other way.</span></span> <span data-ttu-id="262e5-162">Nachdem Sie Gruppen erstellt haben, können Sie [Ihr Compliance-Manager-Dashboard Filtern](compliance-manager-setup.md#filtering-your-dashboard-view) , um Ihre Bewertung von einer oder mehreren Gruppen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="262e5-162">Once you create groups, you can [filter your Compliance Manager dashboard](compliance-manager-setup.md#filtering-your-dashboard-view) to view your score by one or more groups.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="262e5-163">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="262e5-163">Learn more</span></span>

<span data-ttu-id="262e5-164">[Erstellen und Verwalten von Bewertungen im Compliance-Manager](compliance-manager-assessments.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-164">[Build and manage assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

### <a name="templates"></a><span data-ttu-id="262e5-165">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="262e5-165">Templates</span></span>

<span data-ttu-id="262e5-166">Compliance-Manager stellt Vorlagen zur Verfügung, mit denen Sie schnell Bewertungen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="262e5-166">Compliance Manager provides templates to help you quickly create assessments.</span></span> <span data-ttu-id="262e5-167">Sie können diese Vorlagen ändern, um eine für Ihre Anforderungen optimierte Bewertung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="262e5-167">You can modify these templates to create an assessment optimized for your needs.</span></span> <span data-ttu-id="262e5-168">Sie können auch eine benutzerdefinierte Bewertung erstellen, indem Sie eine Vorlage mit ihren eigenen Steuerelementen und Aktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="262e5-168">You can also build a custom assessment by creating a template with your own controls and actions.</span></span> <span data-ttu-id="262e5-169">Beispielsweise kann es sein, dass eine Vorlage eine interne Geschäftsprozess Steuerung oder einen regionalen Datenschutzstandard abdeckt, der nicht von einer unserer 150 vorab erstellten Bewertungs Vorlagen abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="262e5-169">For example, you may want a template to cover an internal business process control, or a regional data protection standard that isn’t covered by one of our 150+ pre-built assessment templates.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="262e5-170">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="262e5-170">Learn more</span></span>

<span data-ttu-id="262e5-171">[Hier finden Sie eine Liste der vom Compliance-Manager bereitgestellten Bewertungs Vorlagen](compliance-manager-templates-list.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-171">[View the list of assessment templates provided by Compliance Manager](compliance-manager-templates-list.md).</span></span>

<span data-ttu-id="262e5-172">[Hier erhalten Sie detaillierte Anweisungen zum Erstellen und Ändern von Vorlagen für Bewertungen](compliance-manager-templates.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-172">[Get detailed instructions for creating and modifying templates for assessments](compliance-manager-templates.md).</span></span>

### <a name="improvement-actions"></a><span data-ttu-id="262e5-173">Verbesserungs Aktionen</span><span class="sxs-lookup"><span data-stu-id="262e5-173">Improvement actions</span></span>

<span data-ttu-id="262e5-174">Verbesserungs Aktionen helfen beim zentralisieren Ihrer Compliance-Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="262e5-174">Improvement actions help centralize your compliance activities.</span></span> <span data-ttu-id="262e5-175">Jede Verbesserungs Aktion enthält empfohlene Anleitungen, die Sie bei der Anpassung an Datenschutzbestimmungen und-Standards unterstützen sollen.</span><span class="sxs-lookup"><span data-stu-id="262e5-175">Each improvement action provides recommended guidance that’s intended to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="262e5-176">Verbesserungs Aktionen können Benutzern in Ihrer Organisation zugewiesen werden, um Implementierungs-und Testaufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="262e5-176">Improvement actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="262e5-177">Sie können auch Dokumentation, Notizen und Datensatzstatus Aktualisierungen in der Verbesserungs Aktion speichern.</span><span class="sxs-lookup"><span data-stu-id="262e5-177">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

##### <a name="learn-more"></a><span data-ttu-id="262e5-178">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="262e5-178">Learn more</span></span>

<span data-ttu-id="262e5-179">[Verwenden Sie Verbesserungs Aktionen, um den Compliance-Workflow zu verwalten](compliance-manager-improvement-actions.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-179">[Use improvement actions to manage your compliance workflow](compliance-manager-improvement-actions.md).</span></span>

<span data-ttu-id="262e5-180">[Erfahren Sie, wie sich Aktionen auf das Konformitäts Ergebnis auswirken](compliance-score-calculation.md#action-types-and-points).</span><span class="sxs-lookup"><span data-stu-id="262e5-180">[Learn how actions impact your compliance score](compliance-score-calculation.md#action-types-and-points).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="262e5-181">Unterstützte Sprachen</span><span class="sxs-lookup"><span data-stu-id="262e5-181">Supported languages</span></span>

<span data-ttu-id="262e5-182">Compliance-Manager ist in den folgenden Sprachen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="262e5-182">Compliance Manager is available in the following languages:</span></span>

- <span data-ttu-id="262e5-183">Englisch</span><span class="sxs-lookup"><span data-stu-id="262e5-183">English</span></span>
- <span data-ttu-id="262e5-184">Bahasa Indonesisch</span><span class="sxs-lookup"><span data-stu-id="262e5-184">Bahasa Indonesian</span></span>
- <span data-ttu-id="262e5-185">Bahasa Malay</span><span class="sxs-lookup"><span data-stu-id="262e5-185">Bahasa Malay</span></span>
- <span data-ttu-id="262e5-186">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="262e5-186">Chinese (Simplified)</span></span>
- <span data-ttu-id="262e5-187">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="262e5-187">Chinese (Traditional)</span></span>
- <span data-ttu-id="262e5-188">Tschechisch</span><span class="sxs-lookup"><span data-stu-id="262e5-188">Czech</span></span>
- <span data-ttu-id="262e5-189">Dänisch</span><span class="sxs-lookup"><span data-stu-id="262e5-189">Danish</span></span>
- <span data-ttu-id="262e5-190">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="262e5-190">Dutch</span></span>
- <span data-ttu-id="262e5-191">Finnisch</span><span class="sxs-lookup"><span data-stu-id="262e5-191">Finnish</span></span>
- <span data-ttu-id="262e5-192">Französisch</span><span class="sxs-lookup"><span data-stu-id="262e5-192">French</span></span>
- <span data-ttu-id="262e5-193">Deutsch</span><span class="sxs-lookup"><span data-stu-id="262e5-193">German</span></span>
- <span data-ttu-id="262e5-194">Hebräisch</span><span class="sxs-lookup"><span data-stu-id="262e5-194">Hebrew</span></span>
- <span data-ttu-id="262e5-195">Ungarisch</span><span class="sxs-lookup"><span data-stu-id="262e5-195">Hungarian</span></span>
- <span data-ttu-id="262e5-196">Italienisch</span><span class="sxs-lookup"><span data-stu-id="262e5-196">Italian</span></span>
- <span data-ttu-id="262e5-197">Japanisch</span><span class="sxs-lookup"><span data-stu-id="262e5-197">Japanese</span></span>
- <span data-ttu-id="262e5-198">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="262e5-198">Korean</span></span>
- <span data-ttu-id="262e5-199">Norwegisch</span><span class="sxs-lookup"><span data-stu-id="262e5-199">Norwegian</span></span>
- <span data-ttu-id="262e5-200">Polnisch</span><span class="sxs-lookup"><span data-stu-id="262e5-200">Polish</span></span>
- <span data-ttu-id="262e5-201">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="262e5-201">Portuguese (Brazilian)</span></span>
- <span data-ttu-id="262e5-202">Russisch</span><span class="sxs-lookup"><span data-stu-id="262e5-202">Russian</span></span>
- <span data-ttu-id="262e5-203">Spanisch</span><span class="sxs-lookup"><span data-stu-id="262e5-203">Spanish</span></span>
- <span data-ttu-id="262e5-204">Schwedisch</span><span class="sxs-lookup"><span data-stu-id="262e5-204">Swedish</span></span>
- <span data-ttu-id="262e5-205">Thailändisch</span><span class="sxs-lookup"><span data-stu-id="262e5-205">Thai</span></span>
- <span data-ttu-id="262e5-206">Türkisch</span><span class="sxs-lookup"><span data-stu-id="262e5-206">Turkish</span></span>

## <a name="next-steps-set-up-and-customize"></a><span data-ttu-id="262e5-207">Nächste Schritte: Einrichten und anpassen</span><span class="sxs-lookup"><span data-stu-id="262e5-207">Next steps: set up and customize</span></span>

<span data-ttu-id="262e5-208">Informationen zum Anmelden, Zuweisen von Berechtigungen und Rollen, Konfigurieren von Einstellungen und Personalisieren der Dashboardansicht finden Sie unter [Erste Schritte mit Compliance-Manager](compliance-manager-setup.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-208">Learn how to sign in, assign permissions and roles, configure settings, and personalize your dashboard view at [Get started with Compliance Manager](compliance-manager-setup.md).</span></span>

<span data-ttu-id="262e5-209">Beginnen Sie dann mit dem Anpassen von Compliance-Manager, um Sie bei der Einhaltung von Branchenstandards zu unterstützen, die für Ihr Unternehmen am wichtigsten sind, indem Sie [Assessments einrichten](compliance-manager-assessments.md).</span><span class="sxs-lookup"><span data-stu-id="262e5-209">Then start customizing Compliance Manager to help you comply with industry standards that matter most to your organization by [setting up assessments](compliance-manager-assessments.md).</span></span>