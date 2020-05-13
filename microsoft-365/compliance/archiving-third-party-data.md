---
title: Archivieren von Drittanbieterdaten
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
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen zu Microsoft 365-Postfächern importieren.
ms.openlocfilehash: 2d011fcb63e0ec9804ade62f9fdcd1dd95fbf798
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210531"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="3d582-103">Archivieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="3d582-103">Archive third-party data</span></span>

<span data-ttu-id="3d582-104">Microsoft 365 ermöglicht Administratoren das Importieren und Archivieren von drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen in Postfächern in Ihrer Microsoft 365-Organisation.</span><span class="sxs-lookup"><span data-stu-id="3d582-104">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3d582-105">Beispiele für Drittanbieter-Datenquellen, die Sie in Microsoft 365 importieren können, umfassen die folgenden Dienste:</span><span class="sxs-lookup"><span data-stu-id="3d582-105">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="3d582-106">**Soziale Netzwerke:** Facebook, LinkedIn, Twitter und jammern</span><span class="sxs-lookup"><span data-stu-id="3d582-106">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="3d582-107">**Instant Messaging:** Yahoo Messenger und googletalk</span><span class="sxs-lookup"><span data-stu-id="3d582-107">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="3d582-108">**Dokument Zusammenarbeit:** Box und Dropbox</span><span class="sxs-lookup"><span data-stu-id="3d582-108">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="3d582-109">**Vertikale Branchen:** Kunden Beziehungs Management (beispielsweise Salesforce Chatter) und Finanzdienstleistungen (wie Bloomberg und Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="3d582-109">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="3d582-110">**SMS/Textnachrichten:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="3d582-110">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="3d582-111">Nach dem Importieren von drittanbieterdaten können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, in-situ-Archivierung, Überwachung, Kommunikations Konformität und Aufbewahrungsrichtlinien auf diese Daten anwenden.</span><span class="sxs-lookup"><span data-stu-id="3d582-111">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="3d582-112">Wenn beispielsweise ein Postfach in das Beweissicherungsverfahren gestellt wird, werden drittanbieterdaten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3d582-112">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="3d582-113">Sie können drittanbieterdaten mithilfe von Microsoft eDiscovery-Tools durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="3d582-113">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="3d582-114">Sie können auch Archivierungs-und Aufbewahrungsrichtlinien auf drittanbieterdaten anwenden, genau wie für Microsoft-Daten.</span><span class="sxs-lookup"><span data-stu-id="3d582-114">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="3d582-115">Kurz gesagt: das Archivieren von drittanbieterdaten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.</span><span class="sxs-lookup"><span data-stu-id="3d582-115">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="3d582-116">Es gibt zwei Möglichkeiten zum Importieren und Archivieren von drittanbieterdaten in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="3d582-116">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="3d582-117">**Verwenden Sie einen Drittanbieter-Daten Konnektor im Security & Compliance Center:** Verwenden Sie einen benutzerdefinierten Daten Konnektor, der im Microsoft 365 Compliance Center verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3d582-117">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3d582-118">Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der Drittanbieter-Datenquelle her, wandelt den Inhalt eines Elements in ein e-Mail-Nachrichtenformat um und importiert dann das Element in ein Postfach in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d582-118">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="3d582-119">Derzeit können Sie Connectors zum Importieren und Archivieren von Daten von Facebook-Geschäfts Seiten, Unternehmens Twitter-Konten, LinkedIn, Instant Bloomberg und den Personaldaten Ihrer Organisation implementieren.</span><span class="sxs-lookup"><span data-stu-id="3d582-119">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="3d582-120">Eine Schritt-für-Schritt-Anleitung zum Einrichten eines dieser Connectors finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="3d582-120">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="3d582-121">**Facebook:** [Verwenden eines Connectors zum Archivieren von Facebook-Daten (Vorschau)](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3d582-121">**Facebook:** [Use a connector to archive Facebook data (preview)](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="3d582-122">**Twitter:** [Verwenden eines Connectors zum Archivieren von Twitter-Daten (Vorschau)](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3d582-122">**Twitter:** [Use a connector to archive Twitter data (preview)](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="3d582-123">**LinkedIn:** [Einrichten eines Connectors zum Archivieren von LinkedIn Daten](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="3d582-123">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="3d582-124">**Instant Bloomberg:** [Einrichten eines Connectors zum Archivieren von sofort Bloomberg-Daten](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="3d582-124">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="3d582-125">**HR-Daten:** [Einrichten eines Connectors zum Importieren von HR-Daten (Vorschau)](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="3d582-125">**HR data:** [Set up a connector to import HR data (preview)](import-hr-data.md)</span></span>

- <span data-ttu-id="3d582-126">**Arbeiten mit einem Microsoft-Partner:** Ihre Organisation arbeitet mit einem Microsoft-Partner zusammen, der einen benutzerdefinierten Connector bereitstellt, der so konfiguriert ist, dass er regelmäßig Elemente aus der Drittanbieter-Datenquelle extrahiert und anschließend eine Verbindung mit der Microsoft-Cloud über eine Drittanbieter-API herstellen und diese Elemente nach Microsoft 365 importieren kann.</span><span class="sxs-lookup"><span data-stu-id="3d582-126">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="3d582-127">Der Partner Connector konvertiert auch den Inhalt eines Elements aus der Drittanbieter-Datenquelle in eine e-Mail-Nachricht und importiert diese dann in ein Postfach in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d582-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="3d582-128">Eine Liste der Partner, mit denen Sie zusammenarbeiten und den schrittweisen Prozess für diese Methode ausführen können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="3d582-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
