---
title: Benutzerdefinierte Typen vertraulicher Informationen für DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Hier finden Sie eine Übersicht über die benutzerdefinierten vertraulichen Informationstypen für DLP (Verhinderung von Datenverlust), z.B. primäres Muster, Zeichenabstand und Konfidenzniveau.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21d0be23847a8fbd27b6082ca28cdca2d4eed05
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379175"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="48a09-103">Benutzerdefinierten Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="48a09-103">Custom sensitive information types</span></span>

<span data-ttu-id="48a09-104">Microsoft 365 enthält viele einsatzbereite integrierte Typen vertraulicher Informationen, die Sie in Ihrer Organisation nutzen können, wie zum Beispiel zur [Verhinderung vor Datenverlust](data-loss-prevention-policies.md) (DLP) oder mit [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="48a09-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="48a09-105">Integrierte Typen vertraulicher Informationen helfen beim Erkennen und Schützen von Kreditkartennummern, Bankverbindungsnummern, Reisepassnummern und mehr, basierend auf Mustern, die durch einen regulären Ausdruck (RegEx) oder eine Funktion definiert sind.</span><span class="sxs-lookup"><span data-stu-id="48a09-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="48a09-106">Weitere Informationen finden Sie unter [Wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="48a09-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="48a09-107">Was aber ist, wenn Sie eine andere Art Typ vertraulicher Informationen identifizieren und schützen müssen, zum Beispiel für Mitarbeiter-IDs oder Projektnummern, die ein für Ihre Organisation spezifisches Format verwendet?</span><span class="sxs-lookup"><span data-stu-id="48a09-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="48a09-108">Hierfür können Sie einen benutzerdefinierten Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="48a09-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="48a09-109">Die grundlegenden Bestandteile eines benutzerdefinierten Typs für vertrauliche Informationen sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="48a09-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="48a09-110">**Primäres Muster**: Mitarbeiter-ID-Nummer, Projektnummern usw. Dieses wird in der Regel durch einen regulären Ausdruck (RegEx) gekennzeichnet, kann aber auch eine Liste von Schlüsselwörtern sein.</span><span class="sxs-lookup"><span data-stu-id="48a09-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="48a09-p103">**Zusätzliche Nachweise**: Angenommen, Sie suchen nach einer neunstelligen Mitarbeiter-ID-Nummer. Nicht alle neunstelligen ID-Nummern sind Mitarbeiter-ID-Nummern, Sie können daher nach zusätzlichem Text suchen: Schlüsselwörter wie „Mitarbeiter“, „Ausweis“, „ID“ oder andere Textmuster basierend auf zusätzlichen regulären Ausdrücken. Diese Nachweise (auch bezeichnet als _unterstützende_ oder _bestätigende_ Nachweise) erhöhen die Wahrscheinlichkeit, dass die neunstellige Nummer, die in Inhalten gefunden wird, auch wirklich eine Mitarbeiter-ID-Nummer ist.</span><span class="sxs-lookup"><span data-stu-id="48a09-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="48a09-p104">**Zeichenabstand**: Je näher sich das primäre Muster an den unterstützenden Nachweisen befindet, desto größer ist die Wahrscheinlichkeit, dass die gefundenen Inhalte den von Ihnen gesuchten Inhalten entsprechen. Sie können den Zeichenabstand zwischen dem primären Muster und den unterstützenden Nachweisen angeben (auch als _Näherungsfenster_ bezeichnet), wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="48a09-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="48a09-p105">**Zuverlässigkeitsgrad**: Je mehr unterstützende Nachweise Sie haben, desto höher die Wahrscheinlichkeit, dass eine Übereinstimmung die vertraulichen Informationen enthält, die Sie suchen. Sie können höhere Zuverlässigkeitsstufen für Übereinstimmungen zuweisen, die gefunden werden, indem Sie mehr Nachweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="48a09-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="48a09-p106">Wenn eine Übereinstimmung gefunden wurde, gibt ein Muster eine Anzahl und einen Zuverlässigkeitsgrad zurück, die bzw. den Sie in den Bedingungen Ihrer DLP-Richtlinien verwenden können. Wenn Sie eine Bedingung zum Erkennen eines Typs vertraulicher Informationen zu einer DLP-Richtlinie hinzufügen, können Sie die Anzahl und den Zuverlässigkeitsgrad wie in der folgenden Abbildung dargestellt bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="48a09-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="48a09-122">Benutzerdefinierte Typen vertraulicher Informationen erstellen</span><span class="sxs-lookup"><span data-stu-id="48a09-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="48a09-123">Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="48a09-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="48a09-124">**EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten.</span><span class="sxs-lookup"><span data-stu-id="48a09-124">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="48a09-125">Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="48a09-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="48a09-126">Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="48a09-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="48a09-127">**Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48a09-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="48a09-128">Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="48a09-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="48a09-129">Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="48a09-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="48a09-130">**Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="48a09-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="48a09-131">Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden.</span><span class="sxs-lookup"><span data-stu-id="48a09-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="48a09-132">Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="48a09-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

> [!NOTE]
> <span data-ttu-id="48a09-133">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Doppelbyte-Zeichensatz-Sprachen für:</span><span class="sxs-lookup"><span data-stu-id="48a09-133">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="48a09-134">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="48a09-134">Chinese (simplified)</span></span>
> - <span data-ttu-id="48a09-135">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="48a09-135">Chinese (traditional)</span></span>
> - <span data-ttu-id="48a09-136">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="48a09-136">Korean</span></span>
> - <span data-ttu-id="48a09-137">Japanisch</span><span class="sxs-lookup"><span data-stu-id="48a09-137">Japanese</span></span>
> 
><span data-ttu-id="48a09-138">Diese Vorschau ist nur in der kommerziellen Cloud verfügbar, und die Einführung ist beschränkt auf:</span><span class="sxs-lookup"><span data-stu-id="48a09-138">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="48a09-139">Japan</span><span class="sxs-lookup"><span data-stu-id="48a09-139">Japan</span></span>
> - <span data-ttu-id="48a09-140">Korea</span><span class="sxs-lookup"><span data-stu-id="48a09-140">Korea</span></span>
> - <span data-ttu-id="48a09-141">China</span><span class="sxs-lookup"><span data-stu-id="48a09-141">China</span></span>
> - <span data-ttu-id="48a09-142">Hongkong (SAR)</span><span class="sxs-lookup"><span data-stu-id="48a09-142">Hong Kong</span></span>
> - <span data-ttu-id="48a09-143">Macau (SAR)</span><span class="sxs-lookup"><span data-stu-id="48a09-143">Macau</span></span>
> - <span data-ttu-id="48a09-144">Taiwan</span><span class="sxs-lookup"><span data-stu-id="48a09-144">Taiwan</span></span>
>
><span data-ttu-id="48a09-145">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48a09-145">This support is available for sensitive information types.</span></span> <span data-ttu-id="48a09-146">Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="48a09-146">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

