---
title: Ausführen einer Testversion von Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie ein Testpilotprogramm für SharePoint Syntex in Ihrer Organisation planen und ausführen.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327118"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a><span data-ttu-id="44c56-103">Ausführen einer Testversion von Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="44c56-103">Run a trial of Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="44c56-104">In diesem Artikel wird beschrieben, wie Sie ein Testpilotprogramm einrichten und ausführen, um SharePoint Syntex in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="44c56-104">This article describes how to set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span></span> <span data-ttu-id="44c56-105">Außerdem werden bewährte Methoden für die Testversion empfohlen.</span><span class="sxs-lookup"><span data-stu-id="44c56-105">It also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="44c56-106">Registrieren für eine Testversion</span><span class="sxs-lookup"><span data-stu-id="44c56-106">Sign up for a trial</span></span>

<span data-ttu-id="44c56-107">Die Testversion von SharePoint Syntex bietet 300 Benutzern 30 Tage Lang Zugriff.</span><span class="sxs-lookup"><span data-stu-id="44c56-107">The trial of SharePoint Syntex gives access to 300 users for 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="44c56-108">Bis zu 300 Benutzer sind in der Testversion enthalten, um die automatische Hinzufügung von 1 Million AI Builder-Guthaben sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="44c56-108">Up to 300 users are included in the trial to ensure the automatic addition of 1 million AI Builder credits.</span></span> <span data-ttu-id="44c56-109">Sie müssen nicht 300 Benutzer einschließen, damit eine Testversion erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="44c56-109">You do not have to include 300 users for a trial to succeed.</span></span>

<span data-ttu-id="44c56-110">Sie können die Testversion aus einer der folgenden Quellen abrufen:</span><span class="sxs-lookup"><span data-stu-id="44c56-110">You can get the trial version from one of the following sources:</span></span>

- <span data-ttu-id="44c56-111">Die [SharePoint Syntex Produktseite](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="44c56-111">The [SharePoint Syntex product page](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="44c56-112">Die [Microsoft 365 Admin Center](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="44c56-112">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="44c56-113">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="44c56-113">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="44c56-114">Wechseln Sie zu  >  **Abrechnungskaufdienste**.</span><span class="sxs-lookup"><span data-stu-id="44c56-114">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="44c56-115">Blättern Sie nach unten zum Bereich **Add-Ons**.</span><span class="sxs-lookup"><span data-stu-id="44c56-115">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="44c56-116">Wählen Sie auf der Kachel SharePoint Syntex **Details** aus.</span><span class="sxs-lookup"><span data-stu-id="44c56-116">On the SharePoint Syntex tile, select **Details**.</span></span>
    5.  <span data-ttu-id="44c56-117">Wählen Sie **Kostenlose Testversion abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="44c56-117">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="44c56-118">Um die Testversion zu bestätigen, führen Sie die verbleibenden Schritte des Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="44c56-118">To confirm the trial, follow the remaining wizard steps.</span></span>

<span data-ttu-id="44c56-119">Sie müssen ein Microsoft 365 globaler Administrator oder Abrechnungsadministrator sein, um eine Testversion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44c56-119">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="44c56-120">Wer an einer Testversion beteiligt sein sollten</span><span class="sxs-lookup"><span data-stu-id="44c56-120">Who should be involved in a trial</span></span>

|<span data-ttu-id="44c56-121">Rolle</span><span class="sxs-lookup"><span data-stu-id="44c56-121">Role</span></span>  |<span data-ttu-id="44c56-122">Aktivität</span><span class="sxs-lookup"><span data-stu-id="44c56-122">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="44c56-123">Microsoft 365 globaler Administrator oder Abrechnungsadministrator</span><span class="sxs-lookup"><span data-stu-id="44c56-123">Microsoft 365 global admin or billing admin</span></span>    |     <span data-ttu-id="44c56-124">Aktivieren der Testversion und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="44c56-124">Activate the trial and assign licenses</span></span>    |
|<span data-ttu-id="44c56-125">Microsoft 365 globaler Administrator oder SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="44c56-125">Microsoft 365 global admin or SharePoint admin</span></span>     |   <span data-ttu-id="44c56-126">Konfigurieren SharePoint Syntex und Erstellen von Inhaltscentern</span><span class="sxs-lookup"><span data-stu-id="44c56-126">Configure SharePoint Syntex and create content centers</span></span>      |
|<span data-ttu-id="44c56-127">Geschäftsbenutzer</span><span class="sxs-lookup"><span data-stu-id="44c56-127">Business users</span></span>     |    <span data-ttu-id="44c56-128">Modellerstellung und -tests</span><span class="sxs-lookup"><span data-stu-id="44c56-128">Model building and testing</span></span>     |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="44c56-129">Vor der Aktivierung einer Testversion</span><span class="sxs-lookup"><span data-stu-id="44c56-129">Before you activate a trial</span></span>

<span data-ttu-id="44c56-130">Um eine SharePoint Syntex Testversion erfolgreich zu planen, berücksichtigen Sie die folgenden Faktoren:</span><span class="sxs-lookup"><span data-stu-id="44c56-130">To successfully plan a SharePoint Syntex trial, consider the following factors:</span></span>

- <span data-ttu-id="44c56-131">Die aussagekräftigsten Tests werden in "realen" Szenarien und Daten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="44c56-131">The most meaningful testing is completed on “real world” scenarios and data.</span></span>
- <span data-ttu-id="44c56-132">Sie können eine SharePoint Syntex Testversion nur einmal pro Mandant aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44c56-132">You can only activate a SharePoint Syntex trial once per tenant.</span></span>

<span data-ttu-id="44c56-133">Ein Test- oder Demomandant kann als "Trockenlauf" verwendet werden, um die Aktivierungsschritte und administrativen Kontrollen zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="44c56-133">A test or demo tenant can be used as a “dry run” to walk through the activation steps and administrative controls.</span></span> <span data-ttu-id="44c56-134">Aber es ist wahrscheinlich am besten, das Modell basierend auf einem Produktionsmandanten zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="44c56-134">But it’s probably best to evaluate model building on a production tenant.</span></span>

<span data-ttu-id="44c56-135">Um den Wert einer Testversion für einen Produktionsmandanten zu maximieren, sind Planung und geschäftliches Engagement unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="44c56-135">To maximize the value of a trial on a production tenant, planning and business engagement are essential.</span></span> <span data-ttu-id="44c56-136">Sie sollten einen oder mehrere Geschäftsbereiche einbeziehen, um drei bis sechs Anwendungsfälle zu identifizieren, die möglicherweise von SharePoint Syntex behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="44c56-136">You should engage one or more business areas to identify three-to-six use cases that could potentially be addressed by SharePoint Syntex.</span></span> <span data-ttu-id="44c56-137">Diese Anwendungsfälle sollten:</span><span class="sxs-lookup"><span data-stu-id="44c56-137">These use cases should:</span></span>

- <span data-ttu-id="44c56-138">Schließen Sie Szenarien ein, die entweder durch die Formularverarbeitung oder das Dokumentverständnismodell gelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="44c56-138">Include scenarios that could be solved by either the forms processing or document understanding model.</span></span>
- <span data-ttu-id="44c56-139">Sie haben ein klares Verständnis des Zwecks für alle extrahierten Metadaten; Beispiel: Ansichtsformatierung oder Automatisierung mithilfe von Power Automate.</span><span class="sxs-lookup"><span data-stu-id="44c56-139">Have a clear understanding of the purpose for any extracted metadata; for example, view formatting or automation by using Power Automate.</span></span> <span data-ttu-id="44c56-140">Während sich SharePoint Syntex auf das Klassifizieren von Dokumenten und das Extrahieren von Metadaten konzentriert, ermöglicht diese Metadaten den zu quantifizierenden Wert.</span><span class="sxs-lookup"><span data-stu-id="44c56-140">While SharePoint Syntex is focused on classifying documents and extracting metadata, the value to quantify is what this metadata enables.</span></span>
- <span data-ttu-id="44c56-141">Basieren auf einem definierten Satz von Daten; Beispielsweise bestimmte SharePoint Websites oder Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="44c56-141">Be based on a defined set of data; for example, specific SharePoint sites or libraries.</span></span> <span data-ttu-id="44c56-142">Ein häufiges Missverständnis von SharePoint Syntex besteht darin, dass allgemeine Modelle auf alle Organisationsinhalte angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="44c56-142">A common misconception of SharePoint Syntex is that general purpose models can be applied across all organization content.</span></span> <span data-ttu-id="44c56-143">Eine genauere Ansicht ist, dass Modelle entwickelt wurden, um bestimmte Geschäftsprobleme an zielgerichteten Standorten zu lösen.</span><span class="sxs-lookup"><span data-stu-id="44c56-143">A more accurate view is that models are built to help solve specific business problems in targeted locations.</span></span>

<span data-ttu-id="44c56-144">Alle diese Anwendungsfälle sind möglicherweise nicht gut geeignet für SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="44c56-144">All of these use cases might not be a good fit for SharePoint Syntex.</span></span> <span data-ttu-id="44c56-145">Das Ziel einer Qualitätsprüfung besteht nicht darin, nachzuweisen, dass SharePoint Syntex in alle Szenarien passt.</span><span class="sxs-lookup"><span data-stu-id="44c56-145">The goal of a quality trial isn't to prove that SharePoint Syntex will fit all the scenarios.</span></span> <span data-ttu-id="44c56-146">Stattdessen sollte ihnen die Testversion helfen, den Wert des Produkts besser zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="44c56-146">Instead, the trial should help you better understand the value of product.</span></span>

<span data-ttu-id="44c56-147">Identifizieren Sie für jeden der geplanten Anwendungsfälle Benutzer, die Fachexperten in den verwandten Inhalten oder Prozessen sind.</span><span class="sxs-lookup"><span data-stu-id="44c56-147">For each of the planned use cases, identify users who are subject matter experts in the related content or process.</span></span> <span data-ttu-id="44c56-148">Die Erstellung SharePoint Syntex Modelle konzentriert sich auf Domänenexperten in den Inhalten und nicht auf IT-Experten oder Entwicklerressourcen.</span><span class="sxs-lookup"><span data-stu-id="44c56-148">The creation of SharePoint Syntex models is focused on domain experts in the content, rather than on IT professionals or developer resources.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="44c56-149">Aktivieren einer Testversion</span><span class="sxs-lookup"><span data-stu-id="44c56-149">Activate a trial</span></span>

<span data-ttu-id="44c56-150">Wenn Sie eine Testversion initiieren, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="44c56-150">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="44c56-151">Weisen Sie den relevanten Benutzern Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="44c56-151">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="44c56-152">Führen Sie [eine zusätzliche Einrichtung von SharePoint Syntex](set-up-content-understanding.md)aus.</span><span class="sxs-lookup"><span data-stu-id="44c56-152">Perform [additional setup of SharePoint Syntex](set-up-content-understanding.md).</span></span>
    - <span data-ttu-id="44c56-153">Möglicherweise möchten Sie [zusätzliche Inhaltscenter erstellen.](create-a-content-center.md)</span><span class="sxs-lookup"><span data-stu-id="44c56-153">You might want to [create additional content centers](create-a-content-center.md).</span></span>

<span data-ttu-id="44c56-154">Nachdem die Testversion aktiviert wurde, können Sie Modelle erstellen und Dateien verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="44c56-154">After the trial is activated, you can create models and process files.</span></span> <span data-ttu-id="44c56-155">Siehe [Anleitung für die Modellerstellung.](create-a-content-center.md)</span><span class="sxs-lookup"><span data-stu-id="44c56-155">See [guidance for model creation](create-a-content-center.md).</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="44c56-156">Während einer Testversion</span><span class="sxs-lookup"><span data-stu-id="44c56-156">During a trial</span></span>

<span data-ttu-id="44c56-157">Testzeitraume sind begrenzt. Daher sollten Sie sich zunächst darauf konzentrieren, ob SharePoint Syntex Modelle Dokumente klassifizieren und Metadaten für die definierten Anwendungsfälle extrahieren können.</span><span class="sxs-lookup"><span data-stu-id="44c56-157">Trial periods are limited, so it’s best to focus initially on whether SharePoint Syntex models can classify documents and extract metadata for the defined use cases.</span></span> <span data-ttu-id="44c56-158">Nach Ablauf des Testzeitraums können Sie auswerten, wie die Metadaten ausgenutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="44c56-158">After the trial period is over, you can evaluate how the metadata can be exploited.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="44c56-159">Nach einer Testversion</span><span class="sxs-lookup"><span data-stu-id="44c56-159">After a trial</span></span>

<span data-ttu-id="44c56-160">Basierend auf dem Ergebnis der Testversion können Sie entscheiden, ob Sie mit der Produktionsverwendung von SharePoint Syntex fortfahren möchten.</span><span class="sxs-lookup"><span data-stu-id="44c56-160">Based on the outcome of the trial, you can decide whether to proceed to production use of SharePoint Syntex.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="44c56-161">Fahren Sie mit der Produktionsverwendung fort</span><span class="sxs-lookup"><span data-stu-id="44c56-161">Proceed to production use</span></span>

<span data-ttu-id="44c56-162">Um die Kontinuität des Dienstes sicherzustellen, müssen Sie die erforderliche Anzahl von Lizenzen erwerben und diese Lizenzen Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="44c56-162">To ensure continuity of service, you need to purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="44c56-163">Testbenutzer, die am Ende des Testzeitraums nicht über eine Volllizenz verfügen, können SharePoint Syntex nicht vollständig nutzen.</span><span class="sxs-lookup"><span data-stu-id="44c56-163">Trial users who don’t have a full license at the end of the trial period won’t be able to fully utilize SharePoint Syntex.</span></span>

<span data-ttu-id="44c56-164">Möglicherweise müssen Sie die geplante Verwendung der Formularverarbeitung abschätzen und den erwarteten Umfang des AI Builder-Guthabens planen.</span><span class="sxs-lookup"><span data-stu-id="44c56-164">You might have to estimate your projected use of forms processing and plan for the expected amount of AI Builder credits.</span></span> <span data-ttu-id="44c56-165">Hilfe finden Sie unter ["Schätzen der AI Builder-Kapazität, die für Sie geeignet ist".](https://powerapps.microsoft.com/ai-builder-calculator/)</span><span class="sxs-lookup"><span data-stu-id="44c56-165">For help, see [Estimate the AI Builder capacity that’s right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="44c56-166">Fahren Sie nicht mit der Produktionsverwendung fort</span><span class="sxs-lookup"><span data-stu-id="44c56-166">Don't proceed to production use</span></span>

<span data-ttu-id="44c56-167">Wenn Sie nach der Testversion keine Lizenzen erwerben:</span><span class="sxs-lookup"><span data-stu-id="44c56-167">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="44c56-168">Sie können keine neuen Modelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="44c56-168">You won’t be able to create new models.</span></span>
- <span data-ttu-id="44c56-169">Bibliotheken, in denen Modelle ausgeführt wurden, klassifizieren nicht mehr automatisch Dateien oder extrahieren Modelle.</span><span class="sxs-lookup"><span data-stu-id="44c56-169">Libraries that were running models will no longer automatically classify files or extract models.</span></span>
- <span data-ttu-id="44c56-170">Alle zuvor klassifizierten Dateien oder extrahierten Metadaten sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="44c56-170">Any previously classified files or extracted metadata won’t be affected.</span></span> 
- <span data-ttu-id="44c56-171">Inhaltscenter und alle Dokumentverständnismodelle werden nicht automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44c56-171">Content centers and any document-understanding models won’t be automatically deleted.</span></span> <span data-ttu-id="44c56-172">Diese bleiben für die Verwendung verfügbar, wenn Sie sich entscheiden, in Zukunft Lizenzen zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="44c56-172">These will remain available for use if you decide to purchase licenses in the future.</span></span>
- <span data-ttu-id="44c56-173">Formularverarbeitungsmodelle werden in der Common Data Services (CDS)-Instanz der Standardmäßigen Power Platform-Umgebung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="44c56-173">Forms-processing models will be stored in the Common Data Services (CDS) instance of the default Power Platform environment.</span></span> <span data-ttu-id="44c56-174">Diese können mit zukünftiger Lizenzierung für SharePoint Syntex oder mit AI Builder-Funktionen in der Power Platform verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44c56-174">These could be used with future licensing for SharePoint Syntex or with AI Builder capabilities in the Power Platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="44c56-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44c56-175">See also</span></span>

[<span data-ttu-id="44c56-176">Einführung von Microsoft SharePoint Syntex: Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="44c56-176">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)
