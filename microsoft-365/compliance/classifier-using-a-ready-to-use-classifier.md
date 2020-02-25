---
title: Verwenden einer integrierten Klassifizierung (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 enthält eine Reihe integrierter Klassifizierungen, die Sie zum Identifizieren und Beschriften von Inhalten in Ihrer Organisation verwenden können. In diesem Thema wird gezeigt, wie Sie die Verwendung dieser Klassifizierungen vorbereiten.
ms.openlocfilehash: 2157e06da251b1f02b6a4623c573d350d838aff0
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266731"
---
# <a name="using-a-built-in-classifier-preview"></a><span data-ttu-id="58238-104">Verwenden einer integrierten Klassifizierung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="58238-104">Using a built-in classifier (preview)</span></span>

<span data-ttu-id="58238-105">Microsoft hat eine Reihe von Klassifizierungen mit sehr umfangreichen Beispieldatensätzen geschult und getestet, mit denen bestimmte Inhaltskategorien identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="58238-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="58238-106">Weitere Informationen finden Sie unter [Erste Schritte mit Schulungs Klassifizierern (Vorschau)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="58238-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="58238-107">Diese Klassifizierungen werden standardmäßig in `Ready to use` der Gruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58238-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="58238-108">**Anstößige Sprache**: erkennt Textelemente, die Profanität, Beleidigungen, verspottungen und verschleierte Ausdrücke enthalten (bei denen es sich um Ausdrücke handelt, die die gleiche Bedeutung wie ein beleidigender Ausdruck haben).</span><span class="sxs-lookup"><span data-stu-id="58238-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="58238-109">**Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.</span><span class="sxs-lookup"><span data-stu-id="58238-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="58238-110">**Sourcecode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in weit verbreiteten Programmiersprachen für Computer geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="58238-110">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="58238-111">**Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung.</span><span class="sxs-lookup"><span data-stu-id="58238-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="58238-112">**Profanity**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen.</span><span class="sxs-lookup"><span data-stu-id="58238-112">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="58238-113">**Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden;</span><span class="sxs-lookup"><span data-stu-id="58238-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="58238-114">Bevor Sie integrierte Klassifizierungen in Ihrem Klassifikations-und Bezeichnungs Workflow verwenden, sollten Sie Sie anhand eines Beispiels für die Inhalte Ihrer Organisation testen, das Ihrer Meinung nach der Kategorie entspricht, um sicherzustellen, dass Ihre Klassifizierungs Vorhersagen Ihren Erwartungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="58238-114">Before using built-in classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58238-115">Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind.</span><span class="sxs-lookup"><span data-stu-id="58238-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="58238-116">Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="58238-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="58238-117">Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Folgen dieser Sprache und dienen nicht dazu, die alleinigen Möglichkeiten Ihrer Organisation zur Überwachung oder Reaktion auf die Verwendung von zu bieten. solche Sprache.</span><span class="sxs-lookup"><span data-stu-id="58238-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="58238-118">Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="58238-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a><span data-ttu-id="58238-119">Vorgehensweise vorbereiten und Verwenden einer integrierten Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="58238-119">How to prepare for and use a built-in classifier</span></span>

1. <span data-ttu-id="58238-120">Sammeln Sie Inhaltselemente für den verfügbaren Test, die Sie in die Kategorie der integrierten Klassifizierung (positive Übereinstimmungen) und diejenigen, die nicht berücksichtigt werden sollten (negative Übereinstimmungen) in der Kategorie, die Sie testen, gehören.</span><span class="sxs-lookup"><span data-stu-id="58238-120">Collect disposable test content items that you feel belong in the category of the built-in classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58238-121">Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.</span><span class="sxs-lookup"><span data-stu-id="58238-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="58238-122">Erstellen eines dedizierten SharePoint Online Ordners; warten Sie mindestens eine Stunde, bis der Ordner dem Suchindex hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="58238-122">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="58238-123">Notieren Sie sich die Ordner-URL.</span><span class="sxs-lookup"><span data-stu-id="58238-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="58238-124">Melden Sie sich bei Microsoft 365 Compliance Center mit Compliance Admin oder Security Admin Role Access an, und öffnen Sie **Microsoft 365 Compliance Center** > **Records Management (Preview)** > **Label Policies** Tab.</span><span class="sxs-lookup"><span data-stu-id="58238-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="58238-125">Wählen `Auto-apply a label`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="58238-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="58238-126">Wählen `Choose a label to auto-apply`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="58238-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="58238-127">Wählen `Create new labels` Sie und erstellen Sie eine Bezeichnung für die Verwendung nur mit diesem Test.</span><span class="sxs-lookup"><span data-stu-id="58238-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="58238-128">Wenn Sie dies tun, lassen `Retention` Sie die Einstellung aus.</span><span class="sxs-lookup"><span data-stu-id="58238-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="58238-129">Sie möchten keine Aufbewahrung oder andere Aktionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="58238-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="58238-130">In diesem Fall verwenden Sie die Aufbewahrungs Bezeichnung einfach als Textbeschriftung, ohne dass Aktionen erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="58238-130">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="58238-131">Sie können beispielsweise eine Aufbewahrungs Bezeichnung mit dem Namen "Sourcecode-Klassifizierungs Test" ohne Aktionen erstellen und diese Aufbewahrungs Bezeichnung automatisch auf Inhalte anwenden, für die die Quell Code Klassifizierung als Bedingung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58238-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="58238-132">Weitere Informationen zum Erstellen von Aufbewahrungs Bezeichnungen finden Sie unter [Overview of Retention Labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="58238-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="58238-133">Wählen `Auto-apply a label` Sie und `Choose a label to auto-apply`dann aus.</span><span class="sxs-lookup"><span data-stu-id="58238-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="58238-134">Weitere Informationen zur Verwendung von Condition Based Auto-Apply a Label finden Sie unter [Automatisches Anwenden von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="58238-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="58238-135">Wählen Sie Ihre Test Bezeichnung in der Liste aus `Next`, und wählen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="58238-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="58238-136">Wählen `Apply label to content that matches a trainable classifier`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="58238-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![Auswählen der Klassifizierung als Bedingung](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="58238-138">.</span><span class="sxs-lookup"><span data-stu-id="58238-138">.</span></span>

10. <span data-ttu-id="58238-139">Wählen Sie Ihre Klassifizierung aus der Liste aus, in diesem Fall`Source Code`</span><span class="sxs-lookup"><span data-stu-id="58238-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="58238-140">Nennen Sie die Richtlinie, beispielsweise "Quellcode-integrierter Klassifizierungs Test".</span><span class="sxs-lookup"><span data-stu-id="58238-140">Name the policy, for example "Source code built-in classifier test".</span></span>

12. <span data-ttu-id="58238-141">Wählen `Let me choose specific locations`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="58238-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="58238-142">Deaktivieren Sie alle Speicherorte `SharePoint sites` , außer `Choose sites`und wählen Sie.</span><span class="sxs-lookup"><span data-stu-id="58238-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="58238-143">Geben Sie in Schritt 2 die URL für die Website ein.</span><span class="sxs-lookup"><span data-stu-id="58238-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="58238-144">Beenden Sie den Assistenten, und wählen Sie`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="58238-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="58238-145">Platzieren Sie die Testelemente in den Ordner dedizierter SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58238-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="58238-146">Lassen Sie eine Stunde für die Anwendung der Bezeichnung zu.</span><span class="sxs-lookup"><span data-stu-id="58238-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="58238-147">Überprüfen Sie die Eigenschaften der Dokumente für die Bezeichnung, um festzustellen, ob die Klassifizierung den Testinhalt wie erwartet enthielt und ausschloß.</span><span class="sxs-lookup"><span data-stu-id="58238-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="58238-148">Überprüfen Sie die Elemente, die beschriftet wurden.</span><span class="sxs-lookup"><span data-stu-id="58238-148">Review the items that were labeled.</span></span>

20. <span data-ttu-id="58238-149">Löschen Sie den Inhalt und die Bezeichnungsrichtlinie, wenn Sie mit Ihren Tests fertig sind.</span><span class="sxs-lookup"><span data-stu-id="58238-149">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="58238-150">Siehe auch:</span><span class="sxs-lookup"><span data-stu-id="58238-150">See also:</span></span>

- [<span data-ttu-id="58238-151">Erste Schritte mit lernbaren Klassifizierungen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="58238-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="58238-152">Übersicht über Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="58238-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="58238-153">Automatisches Anwenden von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung</span><span class="sxs-lookup"><span data-stu-id="58238-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
