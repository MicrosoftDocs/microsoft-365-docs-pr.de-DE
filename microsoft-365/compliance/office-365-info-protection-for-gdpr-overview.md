---
title: Übersicht über Office 365 Information Protection für die DSGVO
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Hier erhalten Sie eine Übersicht über Office 365 Information Protection für die DSGVO. Erfahren Sie, wie Sie personenbezogene Daten ermitteln, klassifizieren, schützen und überwachen können.
ms.openlocfilehash: 079ff7b7dab099f289bbd0366bba00d5ecf55b80
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597862"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a><span data-ttu-id="79629-104">Übersicht über Office 365 Information Protection für die DSGVO</span><span class="sxs-lookup"><span data-stu-id="79629-104">Overview of Office 365 Information Protection for GDPR</span></span>

<span data-ttu-id="79629-p102">Diese Lösung veranschaulicht, wie vertrauliche Daten, die in Office 365-Diensten gespeichert sind, geschützt werden können. Sie bietet Empfehlungen zum Ermitteln, Klassifizieren, Schützen und Überwachen von persönlichen Daten. Dabei wird die Datenschutz-Grundverordnung (DSGVO) als Beispiel verwendet, Sie können das Verfahren jedoch auch für die Einhaltung vieler anderer Bestimmungen nutzen.</span><span class="sxs-lookup"><span data-stu-id="79629-p102">This solution demonstrates how to protect sensitive data that is stored in Office 365 services. It includes prescriptive recommendations for discovering, classifying, protecting, and monitoring personal data. This solution uses General Data Protection Regulation (GDPR) as an example, but you can apply the same process to achieve compliance with many other regulations.</span></span>

<span data-ttu-id="79629-p103">Die DSGVO regelt die Erfassung, Speicherung, Verarbeitung und Freigabe von personenbezogenen Daten. Personenbezogene Daten sind unter der DSGVO allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen, die Einwohner der Europäischen Union (EU) ist.</span><span class="sxs-lookup"><span data-stu-id="79629-p103">GDPR regulates the collection, storage, processing, and sharing of personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="79629-110">Artikel 4: Definitionen</span><span class="sxs-lookup"><span data-stu-id="79629-110">Article 4 – Definitions</span></span>

> <span data-ttu-id="79629-111">Als „personenbezogene Daten“ gelten alle Informationen über eine identifizierte oder identifizierbare natürliche Person („betroffene Person“). Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt, insbesondere durch Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.</span><span class="sxs-lookup"><span data-stu-id="79629-111">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="79629-p104">Diese Lösung soll Organisationen beim Erkennen und Schützen der personenbezogenen Daten in Office 365 helfen, die möglicherweise der DSGVO unterliegen. Sie wird nicht als Nachweis für DSGVO-Compliance angeboten. Organisationen sind für die Einhaltung ihrer DSGVO selbst verantwortlich und werden angewiesen, ihre Rechts- und Compliance-Teams heranzuziehen oder Rat und Hilfe bei auf Compliance spezialisierten Drittanbietern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="79629-p104">This solution is intended to help organizations discover and protect personal data in Office 365 that might be subject to the GDPR. It is not offered as a GDPR compliance attestation. Organizations are responsible for ensuring their own GDPR compliance and are advised to consult their legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>

<span data-ttu-id="79629-115">[DSGVO-Bewertung](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) ist ein kostenloses, schnelles Online-Selbstauswertungstool, mit dem Ihre Organisation ihre allgemeine Stufe der Bereitschaft zur Einhaltung der DSGVO überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="79629-115">[GDPR Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) is a quick, online self-evaluation tool available at no cost to help your organization review its overall level of readiness to comply with the GDPR.</span></span>

## <a name="assess-and-manage-your-compliance-risk"></a><span data-ttu-id="79629-116">Bewerten und Verwalten Ihres Compliance-Risikos</span><span class="sxs-lookup"><span data-stu-id="79629-116">Assess and manage your compliance risk</span></span>

<span data-ttu-id="79629-p105">Der erste Schritt in Richtung DSGVO-Compliance ist, zu beurteilen, ob die DSGVO für Ihre Organisation zutrifft, und wenn ja, in welchem Umfang. Bei dieser Analyse wird untersucht, welche Daten in Ihrer Organisation verarbeitet und wo sie gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="79629-p105">The first step towards GDPR compliance is to assess whether the GDPR applies to your organization, and, if so, to what extent. This analysis includes understanding the data your organization processes and where it resides.</span></span>

### <a name="step-1--use-compliance-score-to-view-the-regulation-requirements-and-track-your-progress"></a><span data-ttu-id="79629-119">Schritt 1 – Verwenden der Compliancebewertung zum Anzeigen der gesetzlichen Anforderungen und zum Nachverfolgen Ihres Fortschritts</span><span class="sxs-lookup"><span data-stu-id="79629-119">Step 1 — Use Compliance Score to view the regulation requirements and track your progress</span></span>

<span data-ttu-id="79629-120">Die Compliancebewertung bietet Tools zum Nachverfolgen, Implementieren und Verwalten der Überwachungssteuerelemente, mit denen Ihre Organisation die Einhaltung verschiedener Standards, auch der DSGVO, leichter erreichen kann.</span><span class="sxs-lookup"><span data-stu-id="79629-120">Compliance Score provides tools to track, implement, and manage the auditing controls to help your organization reach compliance against various standards, including GDPR.</span></span>

![Verwenden von Compliancebewertung und Compliance-Manager zum Anzeigen von Anforderungen und zum Nachverfolgen des Fortschritts](Media/Overview-image1.png)

<span data-ttu-id="79629-122">Weitere Informationen finden Sie unter [Compliancebewertung](compliance-score.md).</span><span class="sxs-lookup"><span data-stu-id="79629-122">For more information, see [Compliance Score](compliance-score.md).</span></span>

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a><span data-ttu-id="79629-123">Schritt 2 – Verwenden der Inhaltssuche und vertraulicher Informationstypen für die Suche nach personenbezogenen Daten</span><span class="sxs-lookup"><span data-stu-id="79629-123">Step 2 — Use Content Search and sensitive information types to find personal data</span></span> 

<span data-ttu-id="79629-p106">Entdecken Sie personenbezogene Daten in Ihrer Umgebung, die der DSGVO unterliegen. Verwenden Sie die Inhaltssuche zusammen mit vertraulichen Informationstypen zu folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="79629-p106">Discover personal data in your environment that is subject to the GDPR. Use Content Search together with sensitive information types to:</span></span>

- <span data-ttu-id="79629-126">Suchen und Melden des Speicherorts von personenbezogenen Daten</span><span class="sxs-lookup"><span data-stu-id="79629-126">Find and report on where personal data resides.</span></span>

- <span data-ttu-id="79629-127">Optimieren vertraulicher Datentypen und anderer Abfragen, um alle personenbezogenen Daten in Ihrer Umgebung zu finden.</span><span class="sxs-lookup"><span data-stu-id="79629-127">Optimize sensitive data types and other queries to find all personal data in your environment.</span></span>

![Verwenden der Inhaltssuche und vertraulicher Informationstypen zum Suchen nach personenbezogenen Daten](Media/Overview-image2.png)

<span data-ttu-id="79629-p107">Vertrauliche Informationstypen definieren, wie bestimmte Informationstypen, z. B. Kreditkartennummern, vom automatisierten Prozess erkannt werden. Dieser Artikel enthält einen Basissatz, den Sie als Ausgangspunkt verwenden können. Weitere vertrauliche Informationstypen werden in Kürze für personenbezogene Daten in EU-Ländern verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="79629-p107">Sensitive information types define how the automated process recognizes specific information types such as health service numbers and credit card numbers. This article includes a set you can use as a starting point. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

<span data-ttu-id="79629-132">Weitere Informationen finden Sie unter [Suchen und Finden personenbezogener Daten](search-for-and-find-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="79629-132">For more information, see [Search for and find personal data](search-for-and-find-personal-data.md).</span></span> 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a><span data-ttu-id="79629-133">Klassifizieren, Schützen und Überwachen von personenbezogenen Daten in Office 365 und anderen SaaS-Apps</span><span class="sxs-lookup"><span data-stu-id="79629-133">Classify, protect, and monitor personal data in Office 365 and other SaaS apps</span></span>

<span data-ttu-id="79629-134">Einige der Funktionen zum Schutz von Informationen in Office 365 können auch zum Schutz vertraulicher Daten in anderen SaaS-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79629-134">Some of the capabilities used for information protection in Office 365 can also be used to protect sensitive data in other SaaS applications.</span></span>

![Klassifizieren, Schützen und Überwachen von personenbezogenen Daten](Media/Overview-image3.png)

<span data-ttu-id="79629-136">Diese Abbildung wird im restlichen Abschnitt beschrieben (Schritte 3 bis 5).</span><span class="sxs-lookup"><span data-stu-id="79629-136">This illustration is described by the rest this section (steps 3-5).</span></span>

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a><span data-ttu-id="79629-137">Schritt 3 – Entscheiden, ob Sie zusätzlich zu vertraulichen Informationstypen Beschriftungen verwenden möchten</span><span class="sxs-lookup"><span data-stu-id="79629-137">Step 3 — Decide if you want to use labels in addition to sensitive information types</span></span>

<span data-ttu-id="79629-p108">Vertrauliche Informationstypen sind eine Form der Klassifizierung. Unter [Erstellen eines Klassifizierungsschemas für personenbezogene Daten](architect-a-classification-schema-for-personal-data.md) finden Sie Hinweise zu der Entscheidung, ob Sie auch Beschriftungen implementieren möchten. Weitere Informationen zum Anwenden von Beschriftungen finden Sie unter [Anwenden von Beschriftungen auf personenbezogene Daten in Office 365](apply-labels-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="79629-p108">Sensitive information types are a form of classification. See [Architect a classification schema for personal data](architect-a-classification-schema-for-personal-data.md), to decide if you also want to implement labels. To apply labels, see [Apply labels to personal data in Office 365](apply-labels-to-personal-data-in-office-365.md).</span></span>

<span data-ttu-id="79629-p109">In der Abbildung gelten vertrauliche Informationstypen und Beschriftungen allgemein in Office 365. In Kürze können Sie diese mit Cloud App Security verwenden, um vertrauliche Daten in anderen SaaS-Apps wie Box und Salesforce zu finden.</span><span class="sxs-lookup"><span data-stu-id="79629-p109">In the illustration, sensitive information types and labels work across Office 365. Coming soon, you can use these with Cloud App Security to find sensitive data in other SaaS apps, such as Box and Salesforce.</span></span>

### <a name="step-4--protect-personal-data-in-office-365"></a><span data-ttu-id="79629-143">Schritt 4 – Schützen personenbezogener Daten in Office 365</span><span class="sxs-lookup"><span data-stu-id="79629-143">Step 4 — Protect personal data in Office 365</span></span> 

<span data-ttu-id="79629-p110">Der Schutz personenbezogener Daten beginnt mit der Verhinderung von Datenverlust in Office 365. Es gibt mehrere andere empfohlene Funktionen für den Schutz des Zugriffs auf persönliche Daten, z. B. die Office 365-Nachrichtenverschlüsselung für E-Mail.</span><span class="sxs-lookup"><span data-stu-id="79629-p110">Protection for personal data starts with Office 365 data loss prevention. There are several other capabilities recommended for protecting access to personal data, including Office 365 Message Encryption for email.</span></span>

<span data-ttu-id="79629-146">Diese Schutzfunktionen können auf bestimmte Datasets ausgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="79629-146">These protections can be targeted to specific data sets:</span></span>

- <span data-ttu-id="79629-147">Berechtigungen auf Website- und Bibliotheksebene</span><span class="sxs-lookup"><span data-stu-id="79629-147">Site and library-level permissions</span></span>

- <span data-ttu-id="79629-148">Richtlinien für externe Freigabe auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="79629-148">Site-level external sharing policies</span></span>

- <span data-ttu-id="79629-149">Gerätezugriffsrichtlinien auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="79629-149">Site-level device access policies</span></span>

<span data-ttu-id="79629-150">Der Schutz für den Zugriff auf Office 365 und andere Clouddienste umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="79629-150">Protection for access to Office 365 and other cloud services include:</span></span>

- <span data-ttu-id="79629-151">Identitäts- und Gerätezugriffsschutz in Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="79629-151">Identity and device access protection in Enterprise Mobility + Security (EMS)</span></span>

- <span data-ttu-id="79629-152">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="79629-152">Privileged access management</span></span>

- <span data-ttu-id="79629-153">Windows 10-Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="79629-153">Windows 10 security capabilities</span></span>

<span data-ttu-id="79629-154">Weitere Informationen über das Anwenden von Schutzfunktionen finden Sie unter [Anwenden von Schutz auf personenbezogene Daten in Office 365](apply-protection-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="79629-154">For more information about applying proteciton, see [Apply protection to personal data in Office 365](apply-protection-to-personal-data-in-office-365.md).</span></span>

### <a name="step-5--monitor-for-leaks-of-personal-data"></a><span data-ttu-id="79629-155">Schritt 5 – Überwachen auf Lecks für personenbezogene Daten</span><span class="sxs-lookup"><span data-stu-id="79629-155">Step 5 — Monitor for leaks of personal data</span></span>

<span data-ttu-id="79629-p111">Berichte zur Verhinderung von Datenverlust in Office 365 bieten die größtmögliche Detailebene für die Überwachung vertraulicher Daten. Sie können automatisierte Warnungen einrichten und Verletzungen mithilfe des Office 365-Überwachungsprotokolls untersuchen. Durch Cloud App Security wird die Möglichkeit zum Suchen und Überwachen vertraulicher Daten auf andere SaaS-Anbieter erweitert. Weitere Informationen zu diesen Tools finden Sie unter [Überwachen auf Verletzungen personenbezogener Daten](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="79629-p111">Office 365 data loss prevention reports provide the greatest level of detail for monitoring sensitive data. You can setup automated alerts and investigate breaches by using the Office 365 audit log. Cloud App Security extends the ability to find and monitor sensitive data to other SaaS providers. For more information on these tools, see [Monitor for breaches of personal data](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span></span>
