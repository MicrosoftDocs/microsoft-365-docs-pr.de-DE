---
title: Steuern der Informationen unterliegen der Datenschutzverordnung
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
description: Verwenden Sie Microsoft 365-Aufbewahrungs Bezeichnungen und-Richtlinien zum Verwalten personenbezogener Daten in Ihrer Microsoft 365-Umgebung.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377045"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="e385b-103">Steuern der Informationen unterliegen der Datenschutzverordnung</span><span class="sxs-lookup"><span data-stu-id="e385b-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="e385b-104">Die Steuerelemente zur Steuerung der Informationssteuerung können in Ihrer Umgebung eingesetzt werden, um die Anforderungen an die Einhaltung von Datenschutzrichtlinien zu erfüllen, einschließlich einer spezifischen Datenschutzverordnung (dsgvo), des HIPAA-HITECH (Datenschutzgesetz der USA), des California Consumer Protection Act (CCPA) und des Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="e385b-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="e385b-105">Diese Steuerelemente fallen in erster Linie in die folgenden Lösungsbereiche:</span><span class="sxs-lookup"><span data-stu-id="e385b-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="e385b-106">Aufbewahrungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e385b-106">Retention policies</span></span>
- <span data-ttu-id="e385b-107">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e385b-107">Retention labels</span></span>
- <span data-ttu-id="e385b-108">Datensatzverwaltung</span><span class="sxs-lookup"><span data-stu-id="e385b-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="e385b-109">Datenschutzbestimmungen, die sich auf die Steuerung der Informationssteuerung auswirken</span><span class="sxs-lookup"><span data-stu-id="e385b-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="e385b-110">Im folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich möglicherweise auf die Steuerelemente für die Informationssteuerung beziehen:</span><span class="sxs-lookup"><span data-stu-id="e385b-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="e385b-111">Dsgvo-Artikel (13) (2) (a)</span><span class="sxs-lookup"><span data-stu-id="e385b-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="e385b-112">Dsgvo-Artikel (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="e385b-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="e385b-113">HIPAA-HITECH (45 CFR 164.312 (c) (2))</span><span class="sxs-lookup"><span data-stu-id="e385b-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="e385b-114">HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="e385b-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="e385b-115">HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))</span><span class="sxs-lookup"><span data-stu-id="e385b-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="e385b-116">LGPD-Artikel 46</span><span class="sxs-lookup"><span data-stu-id="e385b-116">LGPD Article 46</span></span>

<span data-ttu-id="e385b-117">Weitere Informationen zu diesen Richtlinien finden Sie unter [bewerten von Datenschutzrisiken und Identifizieren von vertraulichen Informations Artikeln](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="e385b-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="e385b-118">Für die Informationssteuerung werden in der Regel die Datenschutzbestimmungen für Folgendes gefordert:</span><span class="sxs-lookup"><span data-stu-id="e385b-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="e385b-119">Sie sollten ein technisches Schema für Aufbewahrung und Löschung für personenbezogene Daten verwenden, die in Microsoft 365 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e385b-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="e385b-120">Wenn Sie personenbezogene Daten speichern möchten, informieren Sie den Betreff darüber, wie lange die Daten gespeichert werden, was heute auf Front-End-Websystemen üblich ist.</span><span class="sxs-lookup"><span data-stu-id="e385b-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="e385b-121">Personenbezogene Daten sollten mit überprüfbaren Methoden vor versehentlicher Verarbeitung, Verlust oder Änderung geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="e385b-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="e385b-122">Alle Aktionen, die mit personenbezogenen Daten ausgeführt werden, sollten dokumentiert werden, und die Dokumentation sollte für einen bestimmten Zeitraum aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="e385b-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="e385b-123">Da die Datenschutzbestimmungen hinsichtlich der Datenaufbewahrung und-Löschung nicht sehr spezifisch sind, müssen andere Faktoren berücksichtigt werden, die die Richtlinien für die Informationssteuerung für persönliche Informationen diktieren, die in Ihrem Microsoft 365-Abonnement gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="e385b-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="e385b-124">Hier ein paar Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e385b-124">Here are a few examples:</span></span>

- <span data-ttu-id="e385b-125">Alterung von Consumer-Konten nach 5 Jahren Inaktivität und erfordert Löschung oder Anonymisierung von Kontodaten nach diesem Moment, erfordern Orchestrierung zwischen dem System speichern der Daten und Workflows im Zusammenhang mit Benachrichtigungen und andere Automatisierung.</span><span class="sxs-lookup"><span data-stu-id="e385b-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="e385b-126">Konfigurieren von Regeln für die Beibehaltung von Richtlinien und Verfahren im Zusammenhang mit dsgvo für drei Jahre nach der abgelösten Einstellung, die mit dem aufbewahrungszeitplan der Organisation für Richtlinien und Verfahren übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e385b-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="e385b-127">Verwalten eines separaten Abonnements für die Kommunikation mit Verbrauchern über die Support Organisation.</span><span class="sxs-lookup"><span data-stu-id="e385b-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="e385b-128">Alle e-Mail-Nachrichten wurden nach zwei Wochen aufbewahrt und gelöscht, um die Datenschutz Schulden im System zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e385b-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="e385b-129">Eine wichtige Frage zu beantworten ist:</span><span class="sxs-lookup"><span data-stu-id="e385b-129">A key question to answer is:</span></span> 

- <span data-ttu-id="e385b-130">Wie lange müssen Daten, die personenbezogene Daten enthalten, aus gültigen geschäftlichen Gründen aufbewahrt werden, um zu verhindern, dass "Keep it Forever" praktiziert wird?</span><span class="sxs-lookup"><span data-stu-id="e385b-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="e385b-131">Dies muss mit dem aufbewahrungsbedarf für Business Continuity ausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="e385b-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="e385b-132">Unabhängig von den rechtlichen und geschäftlichen Gründen, um personenbezogene Informationen zu speichern oder zu löschen, bietet Microsoft eine Reihe von Funktionen zur Implementierung Ihres Daten steuerungsschemas in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e385b-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="e385b-133">Managing Information Governance in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e385b-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="e385b-134">Informationen zu Beginn finden Sie unter [Manage Information Governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="e385b-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="e385b-135">Entwickeln von Zeitplänen für die Datenaufbewahrung für Container, e-Mail und Inhalte</span><span class="sxs-lookup"><span data-stu-id="e385b-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="e385b-136">Denken Sie dabei an Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e385b-136">Keep the following in mind:</span></span>

- <span data-ttu-id="e385b-137">Das Festlegen eines Daten Aufbewahrungs Zeitplans für definierte Informationstypen sollte als Voraussetzung für die Implementierung eines Aufbewahrungs-oder Lösch Schemas betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="e385b-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="e385b-138">Angesichts der Anzahl von Informationstypen, die von den meisten Organisationen als wichtig erachtet werden, und der entsprechenden umfangreichen Aufbewahrungszeiträume für Datensätze, die mit diesen übereinstimmen, ist die Implementierung einer Daten Aufbewahrungs-und Datensatzverwaltungsstrategie geplant.</span><span class="sxs-lookup"><span data-stu-id="e385b-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="e385b-139">Der Schlüssel zum Einrichten einer effektiven Strategie für die Datensteuerung dieses Typs besteht darin, sich auf die Geschäftsfunktionen und Informationstypen mit der höchsten Priorität zu konzentrieren, die eine formellere Verwaltung erfordern.</span><span class="sxs-lookup"><span data-stu-id="e385b-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="e385b-140">Beispiele sind gesetzliche Verträge, Abschlüsse und Dokumentationen zur behördlichen Konformität.</span><span class="sxs-lookup"><span data-stu-id="e385b-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="e385b-141">Versuchen Sie, einen separaten aufbewahrungszeitplan für jeden einzelnen Informationstyp zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e385b-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="e385b-142">Versuchen Sie, allgemeine Kategorien so weit wie möglich zu nutzen, beispielsweise mit Aufbewahrungszeit Plänen von 7 Jahren für allgemeine Geschäftsinhalte.</span><span class="sxs-lookup"><span data-stu-id="e385b-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="e385b-143">Wenn die personenbezogenen Informationstypen in Ihrer Umgebung besser bekannt sind, legen Sie Aufbewahrungs-und Lösch Zeitpläne für diese Art von Inhalten fest, und passen Sie Ihre Informationsarchitektur an, um die Steuerung dieser Art von Informationen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="e385b-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="e385b-144">Isolieren Sie beispielsweise persönliche Informationen in separaten Websites, Bibliotheken oder Ordnern mit gesteuertem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e385b-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="e385b-145">Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e385b-145">Retention policies and retention labels</span></span>

<span data-ttu-id="e385b-146">Verwenden Sie [Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen](../compliance/retention.md) zum aufbewahren oder Löschen von Inhalten in Microsoft 365, die personenbezogene Daten enthalten oder erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="e385b-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="e385b-147">Datensatzverwaltung</span><span class="sxs-lookup"><span data-stu-id="e385b-147">Records management</span></span>

<span data-ttu-id="e385b-148">Verwenden Sie Aufbewahrungs Bezeichnungen, die Inhalte als Datensatz deklarieren, um eine Daten [Satz Verwaltungslösung](../compliance/records-management.md) für Daten in Microsoft 365 zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="e385b-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="e385b-149">Für den Datenschutz werden Datensubjekt Anfragen (DSRs), die von der Rechtsabteilung empfangen werden, als Datensatz deklariert und können auf unbestimmte Zeit gespeichert oder mit einem Nachweis entsorgt werden, um die Aufbewahrungspflichten für gesetzliche Aktivitäten einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="e385b-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

