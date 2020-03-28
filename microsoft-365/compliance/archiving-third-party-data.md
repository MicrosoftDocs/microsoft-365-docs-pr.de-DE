---
title: Archivieren von drittanbieterdaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Administratoren können Daten von Drittanbietern aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen zu Postfächern in Ihrer Microsoft 365-Organisation importieren. Auf diese Weise können Sie Daten aus Facebook, Twitter und anderen Datenquellen von Drittanbietern in Microsoft 365 archivieren. Anschließend können Sie Microsoft 365-Kompatibilitätsfeatures (wie Legal Hold, eDiscovery, in-situ-Archivierung und Aufbewahrungsrichtlinien) für drittanbieterdaten verwenden und anwenden.
ms.openlocfilehash: 72afb48f74a30bac2904e857a33487a83eba48cd
ms.sourcegitcommit: f9b5eca20e025acc36635cbd1786ff3407295857
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "43027655"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="62cc2-105">Archivieren von drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="62cc2-105">Archive third-party data</span></span>

<span data-ttu-id="62cc2-106">Microsoft 365 ermöglicht Administratoren das Importieren und Archivieren von drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen in Postfächern in Ihrer Microsoft 365-Organisation.</span><span class="sxs-lookup"><span data-stu-id="62cc2-106">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="62cc2-107">Beispiele für Drittanbieter-Datenquellen, die Sie in Microsoft 365 importieren können, umfassen die folgenden Dienste:</span><span class="sxs-lookup"><span data-stu-id="62cc2-107">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="62cc2-108">**Soziale Netzwerke:** Facebook, LinkedIn, Twitter und jammern</span><span class="sxs-lookup"><span data-stu-id="62cc2-108">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="62cc2-109">**Instant Messaging:** Yahoo Messenger und googletalk</span><span class="sxs-lookup"><span data-stu-id="62cc2-109">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="62cc2-110">**Dokument Zusammenarbeit:** Box und Dropbox</span><span class="sxs-lookup"><span data-stu-id="62cc2-110">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="62cc2-111">**Vertikale Branchen:** Kunden Beziehungs Management (beispielsweise Salesforce Chatter) und Finanzdienstleistungen (wie Bloomberg und Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="62cc2-111">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="62cc2-112">**SMS/Textnachrichten:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="62cc2-112">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="62cc2-113">Nach dem Importieren von drittanbieterdaten können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, in-situ-Archivierung, Überwachung, Kommunikations Konformität und Aufbewahrungsrichtlinien auf diese Daten anwenden.</span><span class="sxs-lookup"><span data-stu-id="62cc2-113">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="62cc2-114">Wenn beispielsweise ein Postfach in das Beweissicherungsverfahren gestellt wird, werden drittanbieterdaten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="62cc2-114">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="62cc2-115">Sie können drittanbieterdaten mithilfe von Microsoft eDiscovery-Tools durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="62cc2-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="62cc2-116">Sie können auch Archivierungs-und Aufbewahrungsrichtlinien auf drittanbieterdaten anwenden, genau wie für Microsoft-Daten.</span><span class="sxs-lookup"><span data-stu-id="62cc2-116">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="62cc2-117">Kurz gesagt: das Archivieren von drittanbieterdaten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.</span><span class="sxs-lookup"><span data-stu-id="62cc2-117">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="62cc2-118">Es gibt zwei Möglichkeiten zum Importieren und Archivieren von drittanbieterdaten in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="62cc2-118">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="62cc2-119">**Verwenden Sie einen Drittanbieter-Daten Konnektor im Security & Compliance Center:** Verwenden Sie einen benutzerdefinierten Daten Konnektor, der im Microsoft 365 Compliance Center verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="62cc2-119">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="62cc2-120">Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der Drittanbieter-Datenquelle her, wandelt den Inhalt eines Elements in ein e-Mail-Nachrichtenformat um und importiert dann das Element in ein Postfach in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62cc2-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="62cc2-121">Derzeit können Sie Connectors zum Importieren und Archivieren von Daten von Facebook-Geschäfts Seiten, Unternehmens Twitter-Konten, LinkedIn, Instant Bloomberg und den Personaldaten Ihrer Organisation implementieren.</span><span class="sxs-lookup"><span data-stu-id="62cc2-121">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="62cc2-122">Eine Schritt-für-Schritt-Anleitung zum Einrichten eines dieser Connectors finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="62cc2-122">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="62cc2-123">**Facebook:** [Verwenden eines Connectors zum Archivieren von Facebook-Daten](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="62cc2-123">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="62cc2-124">**Twitter:** [Verwenden eines Connectors zum Archivieren von Twitter-Daten](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="62cc2-124">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="62cc2-125">**LinkedIn:** [Einrichten eines Connectors zum Archivieren von LinkedIn Daten](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="62cc2-125">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="62cc2-126">**Instant Bloomberg:** [Einrichten eines Connectors zum Archivieren von sofort Bloomberg-Daten](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="62cc2-126">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="62cc2-127">**HR-Daten:** [Einrichten eines Connectors zum Importieren von HR-Daten](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="62cc2-127">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="62cc2-128">**Arbeiten mit einem Microsoft-Partner:** Ihre Organisation arbeitet mit einem Microsoft-Partner zusammen, der einen benutzerdefinierten Connector bereitstellt, der so konfiguriert ist, dass er regelmäßig Elemente aus der Drittanbieter-Datenquelle extrahiert und anschließend eine Verbindung mit der Microsoft-Cloud über eine Drittanbieter-API herstellen und diese Elemente nach Microsoft 365 importieren kann.</span><span class="sxs-lookup"><span data-stu-id="62cc2-128">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="62cc2-129">Der Partner Connector konvertiert auch den Inhalt eines Elements aus der Drittanbieter-Datenquelle in eine e-Mail-Nachricht und importiert diese dann in ein Postfach in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62cc2-129">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="62cc2-130">Eine Liste der Partner, mit denen Sie zusammenarbeiten und den schrittweisen Prozess für diese Methode ausführen können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="62cc2-130">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
