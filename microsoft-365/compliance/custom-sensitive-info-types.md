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
search.appverid:
- MOE150
- MET150
description: Bekommen Sie einen Überblick über benutzerdefinierte Typen vertraulicher Informationen für DLP.
ms.openlocfilehash: b95501c08c2ac53eed6101abfa9f4b814c49f940
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076980"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="c4e04-103">Benutzerdefinierte Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="c4e04-103">Custom sensitive information types</span></span>

## <a name="overview"></a><span data-ttu-id="c4e04-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c4e04-104">Overview</span></span>

<span data-ttu-id="c4e04-105">Office 365 enthält viele einsatzbereite integrierte Typen vertraulicher Informationen, die Sie in Ihrer Organisation nutzen können, wie zum Beispiel zur [Verhinderung vor Datenverlust](data-loss-prevention-policies.md) (DLP) oder mit [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="c4e04-105">Office 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="c4e04-106">Integrierte Typen vertraulicher Informationen helfen beim Erkennen und Schützen von Kreditkartennummern, Bankverbindungsnummern, Reisepassnummern und mehr, basierend auf Mustern, die durch einen regulären Ausdruck (RegEx) oder eine Funktion definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c4e04-106">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="c4e04-107">Weitere Informationen finden Sie unter [Wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c4e04-107">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="c4e04-108">Was aber ist, wenn Sie eine andere Art Typ vertraulicher Informationen identifizieren und schützen müssen, zum Beispiel für Mitarbeiter-IDs oder Projektnummern, die ein für Ihre Organisation spezifisches Format verwendet?</span><span class="sxs-lookup"><span data-stu-id="c4e04-108">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="c4e04-109">Hierfür können Sie einen benutzerdefinierten Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4e04-109">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="c4e04-110">Die grundlegenden Bestandteile eines benutzerdefinierten Typs für vertrauliche Informationen sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c4e04-110">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="c4e04-111">**Primäres Muster**: Mitarbeiter-ID-Nummer, Projektnummern usw. Dieses wird in der Regel durch einen regulären Ausdruck (RegEx) gekennzeichnet, kann aber auch eine Liste von Schlüsselwörtern sein.</span><span class="sxs-lookup"><span data-stu-id="c4e04-111">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="c4e04-p103">**Zusätzliche Nachweise**: Angenommen, Sie suchen nach einer neunstelligen Mitarbeiter-ID-Nummer. Nicht alle neunstelligen ID-Nummern sind Mitarbeiter-ID-Nummern, Sie können daher nach zusätzlichem Text suchen: Schlüsselwörter wie „Mitarbeiter“, „Ausweis“, „ID“ oder andere Textmuster basierend auf zusätzlichen regulären Ausdrücken. Diese Nachweise (auch bezeichnet als _unterstützende_ oder _bestätigende_ Nachweise) erhöhen die Wahrscheinlichkeit, dass die neunstellige Nummer, die in Inhalten gefunden wird, auch wirklich eine Mitarbeiter-ID-Nummer ist.</span><span class="sxs-lookup"><span data-stu-id="c4e04-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="c4e04-p104">**Zeichenabstand**: Je näher sich das primäre Muster an den unterstützenden Nachweisen befindet, desto größer ist die Wahrscheinlichkeit, dass die gefundenen Inhalte den von Ihnen gesuchten Inhalten entsprechen. Sie können den Zeichenabstand zwischen dem primären Muster und den unterstützenden Nachweisen angeben (auch als _Näherungsfenster_ bezeichnet), wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c4e04-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="c4e04-p105">**Zuverlässigkeitsgrad**: Je mehr unterstützende Nachweise Sie haben, desto höher die Wahrscheinlichkeit, dass eine Übereinstimmung die vertraulichen Informationen enthält, die Sie suchen. Sie können höhere Zuverlässigkeitsstufen für Übereinstimmungen zuweisen, die gefunden werden, indem Sie mehr Nachweise verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4e04-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="c4e04-p106">Wenn eine Übereinstimmung gefunden wurde, gibt ein Muster eine Anzahl und einen Zuverlässigkeitsgrad zurück, die bzw. den Sie in den Bedingungen Ihrer DLP-Richtlinien verwenden können. Wenn Sie eine Bedingung zum Erkennen eines Typs vertraulicher Informationen zu einer DLP-Richtlinie hinzufügen, können Sie die Anzahl und den Zuverlässigkeitsgrad wie in der folgenden Abbildung dargestellt bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="c4e04-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Instanzenanzahl und Optionen für die Übereinstimmungsgenauigkeit](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="c4e04-123">Benutzerdefinierte Typen vertraulicher Informationen erstellen</span><span class="sxs-lookup"><span data-stu-id="c4e04-123">Creating custom sensitive information types</span></span>

<span data-ttu-id="c4e04-124">Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c4e04-124">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="c4e04-125">**Verwenden von EDM** (NEU!) Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen, basierend auf der Klassifizierung der genauen Datenübereinstimmung (EDM).</span><span class="sxs-lookup"><span data-stu-id="c4e04-125">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="c4e04-126">Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4e04-126">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="c4e04-127">Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="c4e04-127">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="c4e04-128">**Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4e04-128">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="c4e04-129">Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="c4e04-129">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="c4e04-130">Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c4e04-130">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="c4e04-131">**Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers.</span><span class="sxs-lookup"><span data-stu-id="c4e04-131">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="c4e04-132">Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4e04-132">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="c4e04-133">Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="c4e04-133">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>



