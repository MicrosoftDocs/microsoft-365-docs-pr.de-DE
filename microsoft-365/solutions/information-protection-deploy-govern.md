---
title: Regeln von Informationen, die den Datenschutzbestimmungen unterliegen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Verwenden Microsoft 365 Aufbewahrungsbezeichnungen und -richtlinien zum Verwalten personenbezogener Daten in Microsoft 365 Umgebung.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928436"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="55243-103">Regeln von Informationen, die den Datenschutzbestimmungen unterliegen</span><span class="sxs-lookup"><span data-stu-id="55243-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="55243-104">Steuerungssteuerelemente für die Information Governance können in Ihrer Umgebung eingesetzt werden, um anforderungen an die Einhaltung von Datenschutzbestimmungen zu erfüllen, einschließlich einer Zahl, die speziell für die DSGVO (General Data Protection Regulation, DSGVO), HIPAA-HITECH (Us States Health Care Privacy Act), California Consumer Protection Act (CCPA) und den Brazil Data Protection Act (LGPD) gilt.</span><span class="sxs-lookup"><span data-stu-id="55243-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="55243-105">Diese Steuerelemente fallen in erster Linie in die folgenden Lösungsbereiche:</span><span class="sxs-lookup"><span data-stu-id="55243-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="55243-106">Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="55243-106">Retention policies</span></span>
- <span data-ttu-id="55243-107">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="55243-107">Retention labels</span></span>
- <span data-ttu-id="55243-108">Datensatzverwaltung</span><span class="sxs-lookup"><span data-stu-id="55243-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="55243-109">Datenschutzbestimmungen, die sich auf Die Steuerung von Informationen auswirken</span><span class="sxs-lookup"><span data-stu-id="55243-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="55243-110">Im Folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich auf Die Steuerung von Informationen beziehen können:</span><span class="sxs-lookup"><span data-stu-id="55243-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="55243-111">Artikel zur DSGVO (13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="55243-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="55243-112">Artikel zur DSGVO (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="55243-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="55243-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="55243-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="55243-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="55243-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="55243-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="55243-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="55243-116">LGPD Artikel 46</span><span class="sxs-lookup"><span data-stu-id="55243-116">LGPD Article 46</span></span>

<span data-ttu-id="55243-117">Weitere Informationen zu diesen Bestimmungen finden Sie im Artikel "Bewerten von Datenschutzrisiken und Identifizieren [vertraulicher Informationen".](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="55243-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="55243-118">Für die Steuerung von Informationen müssen Datenschutzbestimmungen in der Regel Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="55243-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="55243-119">Sie sollten ein technisches Schema für die Aufbewahrung und Löschung von personenbezogenen Daten verwenden, die in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55243-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="55243-120">Wenn Sie personenbezogene Daten speichern möchten, informieren Sie den Betreff darüber, wie lange die Daten gespeichert werden, was in Front-End-Websystemen zur Standardpraxis gehört.</span><span class="sxs-lookup"><span data-stu-id="55243-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="55243-121">Personenbezogene Daten sollten mit überprüfbaren Methoden vor versehentlicher Verarbeitung, Verlust oder Änderung geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="55243-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="55243-122">Alle Aktionen, die gegen personenbezogene Daten ausgeführt werden, sollten dokumentiert werden, und diese Dokumentation sollte für einen bestimmten Zeitraum aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="55243-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="55243-123">Da die Datenschutzbestimmungen nicht sehr spezifisch sind, wenn es um die Aufbewahrung und Löschung von Daten geht, müssen andere Faktoren berücksichtigt werden, die Richtlinien für die Informationsverwaltung für personenbezogene Informationen bestimmen können, die in Ihrem abonnement gespeicherten Microsoft 365 sind.</span><span class="sxs-lookup"><span data-stu-id="55243-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="55243-124">Hier ein paar Beispiele:</span><span class="sxs-lookup"><span data-stu-id="55243-124">Here are a few examples:</span></span>

- <span data-ttu-id="55243-125">Das Altern von Verbraucherkonten nach 5 Jahren Inaktivität erfordert das Löschen oder Anonymisieren von Kontodaten nach diesem Zeitpunkt, was eine Orchestrierung zwischen dem System erfordert, in dem die Daten und Workflows im Zusammenhang mit Benachrichtigungen und anderer Automatisierung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="55243-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="55243-126">Konfigurieren von Regeln für die Beibehaltung von Richtlinien und Verfahren im Zusammenhang mit der DSGVO für drei Jahre, nachdem sie ersetzt wurden, was dem Aufbewahrungszeitplan der Organisation für Richtlinien und Verfahren entspricht.</span><span class="sxs-lookup"><span data-stu-id="55243-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="55243-127">Verwalten eines separaten Abonnements für die Kommunikation mit Verbrauchern über die Supportorganisation.</span><span class="sxs-lookup"><span data-stu-id="55243-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="55243-128">Alle E-Mail-Kommunikationen wurden nach zwei Wochen aufbewahrt und gelöscht, um den Aufbau von Datenschutzschulden im System zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="55243-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="55243-129">Eine wichtige Frage, die Sie beantworten müssen, ist:</span><span class="sxs-lookup"><span data-stu-id="55243-129">A key question to answer is:</span></span> 

- <span data-ttu-id="55243-130">Wie lange müssen Informationen, die personenbezogene Daten enthalten, aus gültigen geschäftlichen Gründen aufbewahrt werden, um zu verhindern, dass sie für immer beibehalten werden?</span><span class="sxs-lookup"><span data-stu-id="55243-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="55243-131">Dies muss mit den Aufbewahrungsanforderungen für die Geschäftskontinuität abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="55243-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="55243-132">Unabhängig von den rechtlichen und geschäftlichen Gründen für die Aufbewahrung personenbezogener Informationen oder deren Löschung bietet Microsoft eine Reihe von Funktionen, um Ihr Data Governance-Schema in einem Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55243-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="55243-133">Verwalten der Informationsverwaltung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55243-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="55243-134">Informationen dazu finden Sie unter [Manage information governance](../compliance/manage-information-governance.md) and Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="55243-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="55243-135">Entwickeln von Datenaufbewahrungszeitplänen für Container, E-Mails und Inhalte</span><span class="sxs-lookup"><span data-stu-id="55243-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="55243-136">Denken Sie dabei an Folgendes:</span><span class="sxs-lookup"><span data-stu-id="55243-136">Keep the following in mind:</span></span>

- <span data-ttu-id="55243-137">Die Festlegung eines Zeitplans für die Datenspeicherung für definierte Informationstypen sollte als Voraussetzung für die Implementierung eines Aufbewahrungs- oder Löschungsschemas betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="55243-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="55243-138">Angesichts der Anzahl der Informationstypen, die die meisten Organisationen für wichtig halten, und der zugehörigen großen Aufbewahrungszeitpläne für Datensätze, die mit ihnen zusammenhingen, erfordert die Implementierung einer Strategie für die Datenspeicherung und Datensatzverwaltung eine Planung.</span><span class="sxs-lookup"><span data-stu-id="55243-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="55243-139">Der Schlüssel zum Einrichten einer effektiven Daten-Governance-Strategie dieses Typs besteht in der Fokussierung auf die wichtigsten Geschäftsfunktionen und Informationstypen, die eine formellere Verwaltung erfordern.</span><span class="sxs-lookup"><span data-stu-id="55243-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="55243-140">Beispiele hierfür sind Gesetzliche Verträge, Abschlüsse und Dokumentation zur Einhaltung gesetzlicher Vorschriften.</span><span class="sxs-lookup"><span data-stu-id="55243-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="55243-141">Versuchen Sie, einen separaten Aufbewahrungszeitplan für jeden einzelnen Informationstyp zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="55243-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="55243-142">Versuchen Sie, allgemeine Kategorien so weit wie möglich zu verwenden, z. B. mit Aufbewahrungszeitplänen von 7 Jahren für allgemeine Geschäftsinhalte.</span><span class="sxs-lookup"><span data-stu-id="55243-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="55243-143">Sobald die typen personenbezogenen Informationen in Ihrer Umgebung besser bekannt sind, richten Sie Aufbewahrungs- und Löschungszeitpläne für diese Art von Inhalten ein, und passen Sie Ihre Informationsarchitektur an, um die Steuerung dieser Art von Informationen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="55243-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="55243-144">Isolieren Sie beispielsweise personenbezogene Informationen in separaten Websites, Bibliotheken oder Ordnern mit kontrolliertem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="55243-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="55243-145">Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="55243-145">Retention policies and retention labels</span></span>

<span data-ttu-id="55243-146">Verwenden [Sie Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen,](../compliance/retention.md) um Inhalte in Microsoft 365, die personenbezogene Daten enthalten oder enthalten sollen, zu speichern oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="55243-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="55243-147">Datensatzverwaltung</span><span class="sxs-lookup"><span data-stu-id="55243-147">Records management</span></span>

<span data-ttu-id="55243-148">Verwenden Sie Aufbewahrungsbezeichnungen, die Inhalte als Datensatz deklarieren, um eine [Datensatzverwaltungslösung](../compliance/records-management.md) für Daten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55243-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="55243-149">Für den Datenschutz werden Anträge von Personen, die von der Rechtsabteilung empfangen werden, als Datensatz deklariert und können für unbegrenzte Zeit gespeichert oder mit Nachweisen beseitigt werden, um die Aufbewahrungsspezifikationen für gesetzliche Aktivitäten einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="55243-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>