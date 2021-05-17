---
title: Zusammenarbeit mit einem Partner zum Archivieren von Drittanbieterdaten
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einen benutzerdefinierten Connector zum Importieren von Drittanbieterdaten aus Datenquellen wie Salesforce Chatter, Yahoo Messenger oder Yammer.
ms.openlocfilehash: 6e93ff765129296f62b43c93937701169bbf4b03
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164940"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="7d5e1-103">Zusammenarbeit mit einem Partner zum Archivieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="7d5e1-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="7d5e1-104">Sie können mit einem Microsoft-Partner zusammenarbeiten, um Daten aus einer Datenquelle eines Drittanbieters zu importieren und zu Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="7d5e1-105">Ein Partner kann Ihnen einen benutzerdefinierten Connector bereitstellen, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) extrahiert und anschließend importiert werden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="7d5e1-106">Der Partnerconnector konvertiert den Inhalt eines Elements aus der Datenquelle in ein E-Mail-Nachrichtenformat und speichert die Elemente dann in Postfächern.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="7d5e1-107">Nachdem Daten von Drittanbietern importiert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, In-Place Archiving, Auditing und Microsoft 365 retention policies auf diese Daten anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7d5e1-108">Die [](communication-compliance.md) Kommunikationskonformitätslösung in Microsoft 365 kann nicht auf die von Partnerconnectors importierten Drittanbieterdaten angewendet werden, die in diesem Artikel erwähnt werden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 

<span data-ttu-id="7d5e1-109">Im Folgenden finden Sie eine Übersicht über den Prozess und die Schritte, die für die Zusammenarbeit mit einem Microsoft-Partner zum Importieren von Drittanbieterdaten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="7d5e1-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="7d5e1-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="7d5e1-111">Schritt 2: Erstellen und Konfigurieren eines Drittanbieterdatenpostfachs</span><span class="sxs-lookup"><span data-stu-id="7d5e1-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="7d5e1-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="7d5e1-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="7d5e1-113">Schritt 4: Bereitstellen von Informationen für Ihren Partner</span><span class="sxs-lookup"><span data-stu-id="7d5e1-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="7d5e1-114">Schritt 5: Registrieren des Drittanbieterdatenconnector in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7d5e1-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="7d5e1-115">So funktioniert der Prozess zum Importieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="7d5e1-115">How the third-party data import process works</span></span>

<span data-ttu-id="7d5e1-116">In der folgenden Abbildung und Beschreibung wird erläutert, wie der Datenimportprozess eines Drittanbieters bei der Zusammenarbeit mit einem Partner funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![So funktioniert der Prozess zum Importieren von Drittanbieterdaten](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="7d5e1-118">Der Kunde arbeitet mit seinem Partner ihrer Wahl zusammen, um einen Connector zu konfigurieren, der Elemente aus der Datenquelle eines Drittanbieters extrahiert und diese Elemente dann in die Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="7d5e1-119">Der Partnerconnector stellt eine Verbindung mit Datenquellen von Drittanbietern über eine Drittanbieter-API (geplant oder wie konfiguriert) bereit und extrahiert Elemente aus der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="7d5e1-120">Der Partnerconnector konvertiert den Inhalt eines Elements in ein E-Mail-Format.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="7d5e1-121">Eine Beschreibung [des](#more-information) Nachrichtenformatschemas finden Sie im Abschnitt Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="7d5e1-122">Partnerconnector stellt eine Verbindung mit dem Azure-Dienst in Microsoft 365 mithilfe von Exchange Web Service (EWS) über einen bekannten Endpunkt bereit.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="7d5e1-p103">Elemente werden in das Postfach eines bestimmten Benutzers oder in ein spezielles Postfach zur Aufnahme aller Drittanbieterdaten importiert. Ob ein Element in das Postfach eines bestimmten Benutzers oder in das Postfach für Drittanbieterdaten importiert wird, basiert auf den folgenden Kriterien:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="7d5e1-125">**Elemente mit einer Benutzer-ID, die einem Benutzerkonto entspricht:** Wenn der Partnerconnector die Benutzer-ID des Elements in der Datenquelle eines Drittanbieters einer bestimmten Benutzer-ID in Microsoft 365 zuordnung, wird das Element in den Ordner "Löschen" im Ordner "Wiederherstellbare Elemente" des Benutzers kopiert. </span><span class="sxs-lookup"><span data-stu-id="7d5e1-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="7d5e1-126">Benutzer können nicht auf Elemente im Ordner „Endgültige Löschvorgänge“ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="7d5e1-127">Sie können jedoch eDiscovery-Tools verwenden, um nach Elementen im Ordner "Löschen" zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="7d5e1-128">**Elemente, die keine Benutzer-ID haben, die einem Benutzerkonto entspricht:** Wenn der Partnerconnector die Benutzer-ID eines Elements nicht einer bestimmten Benutzer-ID zuordnung, wird das Element **in** den Posteingangsordner des Datenpostfachs eines Drittanbieters kopiert.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="7d5e1-129">Das Importieren von Elementen in den Posteingang ermöglicht Ihnen oder einem anderen Benutzer in Ihrer Organisation, sich beim Drittanbieter-Postfach anzumelden und diese Elemente zu verwalten und zu sehen, ob Anpassungen an der Partnerconnectorkonfiguration vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="7d5e1-130">Schritt 1: Partner für Drittanbieterdaten suchen</span><span class="sxs-lookup"><span data-stu-id="7d5e1-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="7d5e1-131">Eine wichtige Komponente für die Archivierung von Drittanbieterdaten in Microsoft 365 ist die Suche und Zusammenarbeit mit einem Microsoft-Partner, der sich auf die Erfassung von Daten aus einer Datenquelle eines Drittanbieters und deren Import in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="7d5e1-132">Nachdem die Daten importiert wurden, können sie zusammen mit den anderen Microsoft-Daten Ihrer Organisation archiviert und aufbewahrt werden, z. B. E-Mails von Exchange und Dokumente aus SharePoint und OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="7d5e1-133">Ein Partner erstellt einen Connector, der Daten aus den Datenquellen von Drittanbietern Ihrer Organisation extrahiert (z. B. BlackBerry, Facebook, Google+, Thomson Reuters, Twitter und YouTube) und diese Daten an eine Microsoft 365-API weitergibt, die Elemente als E-Mail-Nachrichten in Exchange-Postfächer importiert.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>
  
<span data-ttu-id="7d5e1-134">In den folgenden Abschnitten sind die Microsoft-Partner (und die von ihnen unterstützten Drittanbieterdatenquellen) aufgeführt, die am Programm zur Archivierung von Drittanbieterdaten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="7d5e1-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="7d5e1-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="7d5e1-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="7d5e1-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="7d5e1-137">Veritas</span><span class="sxs-lookup"><span data-stu-id="7d5e1-137">Veritas</span></span>](#veritas)
  
[<span data-ttu-id="7d5e1-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="7d5e1-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="7d5e1-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="7d5e1-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="7d5e1-140">Verba</span><span class="sxs-lookup"><span data-stu-id="7d5e1-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="7d5e1-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="7d5e1-141">17a-4 LLC</span></span>

<span data-ttu-id="7d5e1-142">[17a-4 LLC](https://www.17a-4.com) unterstützt die folgenden Drittanbieterdatenquellen:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="7d5e1-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="7d5e1-143">BlackBerry</span></span>
    
- <span data-ttu-id="7d5e1-144">Bloomberg Data Streams</span><span class="sxs-lookup"><span data-stu-id="7d5e1-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="7d5e1-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="7d5e1-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="7d5e1-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="7d5e1-146">FactSet</span></span>
    
- <span data-ttu-id="7d5e1-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="7d5e1-147">HipChat</span></span>
    
- <span data-ttu-id="7d5e1-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="7d5e1-148">InvestEdge</span></span>
    
- <span data-ttu-id="7d5e1-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="7d5e1-149">LivePerson</span></span>
    
- <span data-ttu-id="7d5e1-150">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="7d5e1-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="7d5e1-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="7d5e1-151">OpenText</span></span>
    
- <span data-ttu-id="7d5e1-152">Live-Hilfe für Oracle/ATG 'click-to-call'</span><span class="sxs-lookup"><span data-stu-id="7d5e1-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="7d5e1-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="7d5e1-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="7d5e1-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="7d5e1-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="7d5e1-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="7d5e1-155">MindAlign</span></span>
    
- <span data-ttu-id="7d5e1-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="7d5e1-157">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="7d5e1-158">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="7d5e1-159">SQL-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="7d5e1-159">SQL Databases</span></span>
    
- <span data-ttu-id="7d5e1-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="7d5e1-160">Squawker</span></span>
    
- <span data-ttu-id="7d5e1-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="7d5e1-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="7d5e1-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="7d5e1-162">ArchiveSocial</span></span>

<span data-ttu-id="7d5e1-163">[ArchiveSocial ](https://www.archivesocial.com) unterstützt die folgenden Datenquellen von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7d5e1-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="7d5e1-164">Facebook</span></span>
    
- <span data-ttu-id="7d5e1-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="7d5e1-165">Flickr</span></span>
    
- <span data-ttu-id="7d5e1-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="7d5e1-166">Instagram</span></span>
    
- <span data-ttu-id="7d5e1-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7d5e1-167">LinkedIn</span></span>
    
- <span data-ttu-id="7d5e1-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="7d5e1-168">Pinterest</span></span>
    
- <span data-ttu-id="7d5e1-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="7d5e1-169">Twitter</span></span>
    
- <span data-ttu-id="7d5e1-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d5e1-170">YouTube</span></span>
    
- <span data-ttu-id="7d5e1-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="7d5e1-171">Vimeo</span></span>
  
### <a name="veritas"></a><span data-ttu-id="7d5e1-172">Veritas</span><span class="sxs-lookup"><span data-stu-id="7d5e1-172">Veritas</span></span>

<span data-ttu-id="7d5e1-173">Die folgenden Datenquellen von Drittanbietern werden von ["Veritas"](https://www.globanet.com) unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-173">[Veritas](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7d5e1-174">AOL mit Pivot-Client
</span><span class="sxs-lookup"><span data-stu-id="7d5e1-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="7d5e1-175">BlackBerry-Anrufprotokolle (v5, v10, v12)
</span><span class="sxs-lookup"><span data-stu-id="7d5e1-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-176">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-177">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-178">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-179">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="7d5e1-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="7d5e1-180">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="7d5e1-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="7d5e1-181">Box</span><span class="sxs-lookup"><span data-stu-id="7d5e1-181">Box</span></span>
    
- <span data-ttu-id="7d5e1-182">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="7d5e1-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="7d5e1-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="7d5e1-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="7d5e1-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="7d5e1-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="7d5e1-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="7d5e1-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="7d5e1-186">CrowdCompass</span></span>

- <span data-ttu-id="7d5e1-187">Benutzerdefinierte getrennte Textdateien</span><span class="sxs-lookup"><span data-stu-id="7d5e1-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="7d5e1-188">Benutzerdefinierte XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="7d5e1-188">Custom XML files</span></span>
    
- <span data-ttu-id="7d5e1-189">Facebook (Seiten)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="7d5e1-190">Factset</span><span class="sxs-lookup"><span data-stu-id="7d5e1-190">Factset</span></span>
    
- <span data-ttu-id="7d5e1-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="7d5e1-191">FXConnect</span></span>
    
- <span data-ttu-id="7d5e1-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="7d5e1-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="7d5e1-193">Jive</span><span class="sxs-lookup"><span data-stu-id="7d5e1-193">Jive</span></span>
    
- <span data-ttu-id="7d5e1-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="7d5e1-194">Macgregor XIP</span></span>

- <span data-ttu-id="7d5e1-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7d5e1-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="7d5e1-196">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7d5e1-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="7d5e1-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d5e1-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="7d5e1-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="7d5e1-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="7d5e1-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="7d5e1-199">Mobile Guard</span></span>
    
- <span data-ttu-id="7d5e1-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="7d5e1-200">Pivot</span></span>
    
- <span data-ttu-id="7d5e1-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="7d5e1-201">Salesforce Chatter</span></span>

- <span data-ttu-id="7d5e1-202">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7d5e1-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="7d5e1-203">Skype for Business, Versionen 2007 R2 - 2016 (lokal)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="7d5e1-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="7d5e1-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="7d5e1-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="7d5e1-205">Symphony</span></span>
    
- <span data-ttu-id="7d5e1-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="7d5e1-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="7d5e1-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="7d5e1-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="7d5e1-208">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="7d5e1-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="7d5e1-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="7d5e1-209">Twitter</span></span>
    
- <span data-ttu-id="7d5e1-210">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="7d5e1-210">UBS Chat</span></span>
    
- <span data-ttu-id="7d5e1-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d5e1-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="7d5e1-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="7d5e1-212">OpenText</span></span>

<span data-ttu-id="7d5e1-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) unterstützt die folgenden Drittanbieterdatenquellen:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7d5e1-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="7d5e1-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="7d5e1-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="7d5e1-215">Axs Exchange</span></span>
    
- <span data-ttu-id="7d5e1-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="7d5e1-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="7d5e1-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="7d5e1-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="7d5e1-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="7d5e1-218">Axs Signed</span></span>
    
- <span data-ttu-id="7d5e1-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="7d5e1-219">Bloomberg</span></span>
    
- <span data-ttu-id="7d5e1-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="7d5e1-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="7d5e1-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="7d5e1-221">Smarsh</span></span>

<span data-ttu-id="7d5e1-222">[Smarsh](https://www.smarsh.com) unterstützt die folgenden Datenquellen von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7d5e1-223">AIM</span><span class="sxs-lookup"><span data-stu-id="7d5e1-223">AIM</span></span>
    
- <span data-ttu-id="7d5e1-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="7d5e1-224">American Idol</span></span>
    
- <span data-ttu-id="7d5e1-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-225">Apple Juice</span></span>
    
- <span data-ttu-id="7d5e1-226">AOL mit Pivot-Client</span><span class="sxs-lookup"><span data-stu-id="7d5e1-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="7d5e1-227">Ares</span><span class="sxs-lookup"><span data-stu-id="7d5e1-227">Ares</span></span>
    
- <span data-ttu-id="7d5e1-228">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="7d5e1-229">Bear Share</span><span class="sxs-lookup"><span data-stu-id="7d5e1-229">Bear Share</span></span>
    
- <span data-ttu-id="7d5e1-230">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="7d5e1-230">Bit Torrent</span></span>
    
- <span data-ttu-id="7d5e1-231">BlackBerry-Anrufprotokolle (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-232">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-233">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-234">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="7d5e1-235">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="7d5e1-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="7d5e1-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="7d5e1-236">CellTrust</span></span>
    
- <span data-ttu-id="7d5e1-237">Chat Import</span><span class="sxs-lookup"><span data-stu-id="7d5e1-237">Chat Import</span></span>
    
- <span data-ttu-id="7d5e1-238">Echtzeitprotokollierung und -richtinie für Chat</span><span class="sxs-lookup"><span data-stu-id="7d5e1-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="7d5e1-239">Chatter</span><span class="sxs-lookup"><span data-stu-id="7d5e1-239">Chatter</span></span>
    
- <span data-ttu-id="7d5e1-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="7d5e1-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="7d5e1-242">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="7d5e1-242">Collaboration Import</span></span>
    
- <span data-ttu-id="7d5e1-243">Echtzeitprotokollierung für Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="7d5e1-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="7d5e1-244">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="7d5e1-244">Direct Connect</span></span>
    
- <span data-ttu-id="7d5e1-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="7d5e1-245">Facebook</span></span>
    
- <span data-ttu-id="7d5e1-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="7d5e1-246">FactSet</span></span>
    
- <span data-ttu-id="7d5e1-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="7d5e1-247">FastTrack</span></span>
    
- <span data-ttu-id="7d5e1-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="7d5e1-248">Gnutella</span></span>
    
- <span data-ttu-id="7d5e1-249">Google+</span><span class="sxs-lookup"><span data-stu-id="7d5e1-249">Google+</span></span>
    
- <span data-ttu-id="7d5e1-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="7d5e1-250">GoToMyPC</span></span>
    
- <span data-ttu-id="7d5e1-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="7d5e1-251">Hopster</span></span>
    
- <span data-ttu-id="7d5e1-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="7d5e1-252">HubConnex</span></span>
    
- <span data-ttu-id="7d5e1-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="7d5e1-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="7d5e1-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="7d5e1-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="7d5e1-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="7d5e1-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="7d5e1-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="7d5e1-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="7d5e1-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="7d5e1-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="7d5e1-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="7d5e1-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="7d5e1-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="7d5e1-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="7d5e1-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="7d5e1-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="7d5e1-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="7d5e1-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="7d5e1-263">Chat-Import</span><span class="sxs-lookup"><span data-stu-id="7d5e1-263">IM Import</span></span>
    
- <span data-ttu-id="7d5e1-264">Echtzeitprotokollierung und -richtinie für Chat</span><span class="sxs-lookup"><span data-stu-id="7d5e1-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="7d5e1-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="7d5e1-265">Indii Messenger</span></span>
    
- <span data-ttu-id="7d5e1-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="7d5e1-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="7d5e1-267">IRC</span><span class="sxs-lookup"><span data-stu-id="7d5e1-267">IRC</span></span>
    
- <span data-ttu-id="7d5e1-268">Jive</span><span class="sxs-lookup"><span data-stu-id="7d5e1-268">Jive</span></span>
    
- <span data-ttu-id="7d5e1-269">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="7d5e1-270">Jive Import</span><span class="sxs-lookup"><span data-stu-id="7d5e1-270">Jive Import</span></span>
    
- <span data-ttu-id="7d5e1-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="7d5e1-271">JXTA</span></span>
    
- <span data-ttu-id="7d5e1-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7d5e1-272">LinkedIn</span></span>
    
- <span data-ttu-id="7d5e1-273">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="7d5e1-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="7d5e1-274">MFTP</span></span>
    
- <span data-ttu-id="7d5e1-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="7d5e1-276">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="7d5e1-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7d5e1-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="7d5e1-278">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="7d5e1-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="7d5e1-279">MindAlign</span></span>
    
- <span data-ttu-id="7d5e1-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="7d5e1-280">Mobile Guard</span></span>
    
- <span data-ttu-id="7d5e1-281">MSN</span><span class="sxs-lookup"><span data-stu-id="7d5e1-281">MSN</span></span>
    
- <span data-ttu-id="7d5e1-282">My Space</span><span class="sxs-lookup"><span data-stu-id="7d5e1-282">My Space</span></span>
    
- <span data-ttu-id="7d5e1-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="7d5e1-283">NEONetwork</span></span>
    
- <span data-ttu-id="7d5e1-284">Microsoft 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="7d5e1-284">Microsoft 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="7d5e1-285">Microsoft 365 Freigegebene IM</span><span class="sxs-lookup"><span data-stu-id="7d5e1-285">Microsoft 365 Shared IM</span></span>
    
- <span data-ttu-id="7d5e1-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="7d5e1-286">Pinterest</span></span>
    
- <span data-ttu-id="7d5e1-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="7d5e1-287">Pivot</span></span>
    
- <span data-ttu-id="7d5e1-288">QQ</span><span class="sxs-lookup"><span data-stu-id="7d5e1-288">QQ</span></span>
    
- <span data-ttu-id="7d5e1-289">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="7d5e1-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="7d5e1-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="7d5e1-290">SoftEther</span></span>
    
- <span data-ttu-id="7d5e1-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="7d5e1-291">Symphony</span></span>
    
- <span data-ttu-id="7d5e1-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="7d5e1-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="7d5e1-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="7d5e1-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="7d5e1-294">Tor</span><span class="sxs-lookup"><span data-stu-id="7d5e1-294">Tor</span></span>
    
- <span data-ttu-id="7d5e1-295">TTT</span><span class="sxs-lookup"><span data-stu-id="7d5e1-295">TTT</span></span>
    
- <span data-ttu-id="7d5e1-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="7d5e1-296">Twitter</span></span>
    
- <span data-ttu-id="7d5e1-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="7d5e1-297">WinMX</span></span>
    
- <span data-ttu-id="7d5e1-298">Winny</span><span class="sxs-lookup"><span data-stu-id="7d5e1-298">Winny</span></span>
    
- <span data-ttu-id="7d5e1-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="7d5e1-299">Yahoo</span></span>
    
- <span data-ttu-id="7d5e1-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="7d5e1-300">Yammer</span></span>
    
- <span data-ttu-id="7d5e1-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="7d5e1-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="7d5e1-302">Verba</span><span class="sxs-lookup"><span data-stu-id="7d5e1-302">Verba</span></span>

<span data-ttu-id="7d5e1-303">[Verba](https://www.verba.com) unterstützt die folgenden Datenquellen von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="7d5e1-304">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="7d5e1-305">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="7d5e1-306">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="7d5e1-306">Avtec Radio</span></span>
    
- <span data-ttu-id="7d5e1-307">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="7d5e1-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="7d5e1-308">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="7d5e1-309">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="7d5e1-310">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-310">Centile Voice</span></span>
    
- <span data-ttu-id="7d5e1-311">Chatnachricht in Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="7d5e1-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="7d5e1-312">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="7d5e1-313">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="7d5e1-314">Cisco UCCX/UCCE Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="7d5e1-315">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="7d5e1-316">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="7d5e1-316">ESChat Radio</span></span>
    
- <span data-ttu-id="7d5e1-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="7d5e1-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="7d5e1-318">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="7d5e1-319">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="7d5e1-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="7d5e1-320">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="7d5e1-321">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="7d5e1-322">Oracle/Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="7d5e1-323">Oracle/Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="7d5e1-324">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="7d5e1-325">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="7d5e1-326">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="7d5e1-327">Chatnachricht in Skype for Business/Lync</span><span class="sxs-lookup"><span data-stu-id="7d5e1-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="7d5e1-328">Skype for Business/Lync Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="7d5e1-329">Skype for Business/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="7d5e1-330">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="7d5e1-331">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="7d5e1-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="7d5e1-332">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="7d5e1-333">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="7d5e1-333">Truphone Voice</span></span>
    
- <span data-ttu-id="7d5e1-334">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="7d5e1-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="7d5e1-335">Windows Desktop-Computerbildschirm</span><span class="sxs-lookup"><span data-stu-id="7d5e1-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="7d5e1-336">Schritt 2: Erstellen und Konfigurieren eines Drittanbieterdatenpostfachs in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d5e1-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="7d5e1-337">Im Folgenden finden Sie die Schritte zum Erstellen und Konfigurieren eines Datenpostfachs eines Drittanbieters zum Importieren von Daten Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="7d5e1-338">Wie bereits erläutert, werden Elemente in dieses Postfach importiert, wenn der Partnerconnector die Benutzer-ID des Elements nicht einem Benutzerkonto zuordnung.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="7d5e1-339">**Führen Sie diese Aufgaben im Microsoft 365 Admin Center aus.**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="7d5e1-340">Erstellen Sie ein Benutzerkonto, und weisen Sie ihm eine Exchange Online Plan 2 zu. Weitere [Informationen finden Sie unter](../admin/add-users/add-users.md)Hinzufügen von Benutzern Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="7d5e1-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](../admin/add-users/add-users.md).</span></span> <span data-ttu-id="7d5e1-341">Eine Plan 2-Lizenz ist erforderlich, um das Postfach in einem Rechtsstreit zu platzieren oder ein Archivpostfach mit einem unbegrenzten Speicherkontingent zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="7d5e1-342">Fügen Sie das Benutzerkonto für das Datenpostfach eines Drittanbieters der Administratorrolle **Exchange** administrator in Microsoft 365; Weitere [Informationen finden Sie unter Zuweisen von Administratorrollen in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7d5e1-p109">Notieren Sie die Anmeldeinformationen für dieses Benutzerkonto. Sie müssen diese für Ihren Partner bereitstellen, wie in Schritt 4 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-p109">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="7d5e1-345">**Führen Sie diese Aufgaben im Exchange Admin Center aus.**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="7d5e1-346">Ausblenden des Drittanbieterdatenpostfachs aus dem Adressbuch und anderen Adresslisten in Ihrer Organisation; weitere [Informationen finden Sie unter Verwalten von Benutzerpostfächern](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span> <span data-ttu-id="7d5e1-347">Alternativ können Sie den folgenden PowerShell-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="7d5e1-348">Weisen Sie dem Datenpostfach eines Drittanbieters die Berechtigung **FullAccess** zu, damit Administratoren oder Compliance officers das Datenpostfach eines Drittanbieters im Outlook öffnen können. Weitere [Informationen finden Sie unter Verwalten von Berechtigungen für Empfänger](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="7d5e1-349">Aktivieren Sie die folgenden compliancebezogenen Features für das Datenpostfach eines Drittanbieters:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="7d5e1-350">Aktivieren des Archivpostfachs; weitere [Informationen finden Sie unter Aktivieren von Archivpostfächern](enable-archive-mailboxes.md) und Aktivieren der [unbegrenzten Archivierung.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="7d5e1-351">Auf diese Weise können Sie Speicherplatz im primären Postfach frei machen, indem Sie eine Archivrichtlinie einrichten, die Datenelemente von Drittanbietern in das Archivpostfach verschiebt.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="7d5e1-352">Dadurch erhalten Sie unbegrenzten Speicherplatz für Drittanbieterdaten.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="7d5e1-353">Aktivieren Sie für das Drittanbieterdaten-Postfach das Beweissicherungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="7d5e1-354">Sie können auch eine Microsoft 365 im Security and Compliance Center anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="7d5e1-355">Durch das Speichern dieses Postfachs werden Datenelemente von Drittanbietern (auf unbestimmte Zeit oder für eine bestimmte Dauer) aufbewahrt und verhindert, dass sie aus dem Postfach gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="7d5e1-356">Sehen Sie sich eines der folgenden Themen an:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="7d5e1-357">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="7d5e1-357">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)
    
      - [<span data-ttu-id="7d5e1-358">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="7d5e1-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="7d5e1-359">Aktivieren der Postfach-Überwachungsprotokollierung für Besitzer-, Stellvertreter- und Administratorzugriff auf das Datenpostfach eines Drittanbieters; weitere [Informationen finden Sie unter Aktivieren der Postfachüberwachung](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="7d5e1-360">Auf diese Weise können Sie alle Aktivitäten überwachen, die von jedem Benutzer ausgeführt werden, der Zugriff auf das Datenpostfach eines Drittanbieters hat.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="7d5e1-361">Schritt 3: Benutzerpostfächer für Drittanbieterdaten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7d5e1-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="7d5e1-362">Als Nächstes müssen Sie die Benutzerpostfächer für die Unterstützung von Drittanbieterdaten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="7d5e1-363">Führen Sie diese Aufgaben mithilfe des Exchange Admin Center oder mithilfe der entsprechenden cmdlets Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="7d5e1-364">Aktivieren des Archivpostfachs für jeden Benutzer; weitere [Informationen finden Sie unter Aktivieren von Archivpostfächern](enable-archive-mailboxes.md) und Aktivieren der [unbegrenzten Archivierung.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="7d5e1-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="7d5e1-365">Platzieren sie das Aufbewahrungsverfahren für Benutzerpostfächer, oder wenden Sie Microsoft 365 Aufbewahrungsrichtlinie an; siehe eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="7d5e1-366">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="7d5e1-366">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)
    
    - [<span data-ttu-id="7d5e1-367">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="7d5e1-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="7d5e1-368">Wie bereits weiter oben erwähnt, können Sie beim Aktivieren des Beweissicherungsverfahrens für Postfächer festlegen, wie lange Elemente aus einer Drittanbieter-Datenquelle aufbewahrt werden sollen. Sie können auch festlegen, dass sie dauerhaft aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="7d5e1-369">Schritt 4: Bereitstellen von Informationen für Ihren Partner</span><span class="sxs-lookup"><span data-stu-id="7d5e1-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="7d5e1-370">Der letzte Schritt besteht in der Bereitstellung der folgenden Informationen für Ihren Partner, damit er den Connector so konfigurieren kann, dass eine Verbindung mit Ihrer Organisation hergestellt wird, um Daten in Benutzerpostfächer und das Datenpostfach eines Drittanbieters zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="7d5e1-371">Der Endpunkt, der zum Herstellen einer Verbindung mit dem Azure-Dienst in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="7d5e1-372">Die Anmeldeinformationen (Microsoft 365 Benutzer-ID und kennwort) des Datenpostfachs eines Drittanbieters, das Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="7d5e1-373">Diese Anmeldeinformationen sind erforderlich, damit der Partnerconnector auf Elemente zugreifen und sie in das Drittanbieterdaten-Postfach importieren kann.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="7d5e1-374">Schritt 5: Registrieren des Drittanbieterdatenconnector in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7d5e1-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="7d5e1-375">Ab dem 30. September 2018 verwendet der Azure-Dienst in Microsoft 365 die moderne Authentifizierung in Exchange Online, um Datenconnectors von Drittanbietern zu authentifizieren, die versuchen, eine Verbindung mit Ihrer Organisation herzustellen, um Daten zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="7d5e1-376">Der Grund für diese Änderung ist, dass die moderne Authentifizierung mehr Sicherheit bietet als die aktuelle Methode, die auf einer Liste zulässiger Connectors von Drittanbietern basiert, die den zuvor beschriebenen Endpunkt zum Herstellen einer Verbindung mit dem Azure-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="7d5e1-377">Damit ein Datenconnector eines Drittanbieters eine Verbindung mit Microsoft 365 mithilfe der neuen modernen Authentifizierungsmethode herstellen kann, muss ein Administrator in Ihrer Organisation zustimmen, den Connector als vertrauenswürdige Dienstanwendung in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="7d5e1-378">Dies geschieht, indem eine Berechtigungsanforderung akzeptiert wird, um dem Connector den Zugriff auf die Daten Ihrer Organisation in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="7d5e1-379">Nachdem Sie diese Anforderung akzeptiert haben, wird der Drittanbieterdatenconnector als Unternehmensanwendung zu Azure Active Directory und als Dienstprinzipal dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="7d5e1-380">Weitere Informationen zum Zustimmungsprozess finden Sie unter  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-380">For more information the consent process, see  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="7d5e1-381">Hier sind die Schritte, um auf die Anforderung zum Registrieren des Connectors zu zugreifen und diese zu akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="7d5e1-382">Wechseln Sie [zu dieser Seite,](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) und melden Sie sich mit den Anmeldeinformationen eines globalen Administrators an.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="7d5e1-383">Das folgende Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-383">The following dialog box is displayed.</span></span> <span data-ttu-id="7d5e1-384">Sie können die Carets erweitern, um die Berechtigungen zu überprüfen, die dem Connector zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Das Dialogfeld Berechtigungsanforderung wird angezeigt](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="7d5e1-386">Klicken Sie auf **Annehmen**.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-386">Click **Accept**.</span></span>

<span data-ttu-id="7d5e1-387">Nachdem Sie die Anforderung akzeptiert haben, wird das [Azure-Portal](https://portal.azure.com) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="7d5e1-388">Klicken Sie zum Anzeigen der Liste der Anwendungen für Ihre Organisation **auf Azure Active Directory**  >  **Enterprise Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="7d5e1-389">Der Microsoft 365-Datenconnector eines Drittanbieters wird auf dem **Blatt Enterprise aufgeführt.**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d5e1-390">Nach dem 30. September 2018 werden Drittanbieterdaten nicht mehr in Postfächer in Ihrer Organisation importiert, wenn Sie keinen Datenconnector eines Drittanbieters in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="7d5e1-391">Beachten Sie, dass vorhandene Datenconnectors von Drittanbietern (die vor dem 30. September 2018 erstellt wurden) auch in Azure Active Directory registriert werden müssen, indem Sie das Verfahren in Schritt 5 folgen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="7d5e1-392">Widerrufen der Zustimmung für einen Datenconnector eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="7d5e1-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="7d5e1-393">Nachdem Ihre Organisation der Berechtigungsanforderung zur Registrierung eines Drittanbieterdatenconnector in Azure Active Directory zugestimmt hat, kann Ihre Organisation diese Zustimmung jederzeit widerrufen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="7d5e1-394">Das Widerrufen der Zustimmung für einen Connector bedeutet jedoch, dass Daten aus der Datenquelle eines Drittanbieters nicht mehr in die Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="7d5e1-395">Zum Widerrufen der Zustimmung für einen Drittanbieterdatenconnector können Sie die Anwendung (durch Löschen des entsprechenden Dienstprinzipals) aus Azure Active Directory mithilfe des **Blatts Enterprise-Anwendungen** im Azure-Portal oder mithilfe des [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell löschen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="7d5e1-396">Sie können auch das [Cmdlet Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-396">You can also use the [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="7d5e1-397">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d5e1-397">More information</span></span>

- <span data-ttu-id="7d5e1-398">Wie bereits weiter oben erläutert, werden Elemente aus Drittanbieter-Datenquellen als E-Mail-Nachrichten in Exchange-Postfächer importiert.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="7d5e1-399">Der Partnerconnector importiert das Element mithilfe eines Schemas, das von der Microsoft 365 ist.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="7d5e1-400">Die folgende Tabelle beschreibt die Nachrichteneigenschaften eines Elements aus einer Drittanbieter-Datenquelle, nachdem es als E-Mail-Nachricht in ein Exchange-Postfach importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="7d5e1-401">Zudem ist angegeben, wenn die Nachrichteneigenschaft zwingend erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="7d5e1-402">Erforderliche Eigenschaften müssen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="7d5e1-403">Wenn einem Element eine obligatorische Eigenschaft fehlt, wird es nicht in die Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="7d5e1-404">Der Importvorgang gibt eine Fehlermeldung zurück, in der erläutert wird, warum ein Element nicht importiert wurde und welche Eigenschaft fehlt.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="7d5e1-405">**Nachrichteneigenschaft**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-405">**Message property**</span></span>|<span data-ttu-id="7d5e1-406">**Erforderlich?**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-406">**Mandatory?**</span></span>|<span data-ttu-id="7d5e1-407">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-407">**Description**</span></span>|<span data-ttu-id="7d5e1-408">**Beispielwert**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7d5e1-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-409">**FROM**</span></span> <br/> |<span data-ttu-id="7d5e1-410">Ja</span><span class="sxs-lookup"><span data-stu-id="7d5e1-410">Yes</span></span>  <br/> |<span data-ttu-id="7d5e1-411">Der Benutzer, der das Element in der Drittanbieter-Datenquelle ursprünglich erstellt oder gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="7d5e1-412">Der Partnerconnector versucht, die Benutzer-ID aus dem Quellelement (z. B. ein Twitter-Handle) einem Benutzerkonto für alle Teilnehmer (Benutzer in den Feldern FROM und TO) zu zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="7d5e1-413">Eine Kopie der Nachricht wird in das Postfach jedes Teilnehmers importiert.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="7d5e1-414">Wenn keiner der Teilnehmer aus dem Element einem Benutzerkonto zugeordnet werden kann, wird das Element in das Archivierungspostfach eines Drittanbieters in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="7d5e1-415">Der Teilnehmer, der als Absender des Elements identifiziert wird, muss über ein aktives Postfach in der Organisation verfügen, in die das Element importiert wird.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="7d5e1-416">Wenn der Absender nicht über ein aktives Postfach verfügt, wird der folgende Fehler zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="7d5e1-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-417">**TO**</span></span> <br/> |<span data-ttu-id="7d5e1-418">Ja</span><span class="sxs-lookup"><span data-stu-id="7d5e1-418">Yes</span></span>  <br/> |<span data-ttu-id="7d5e1-419">Der Benutzer, der ein Element erhalten hat (wenn für ein Element in der Datenquelle zutreffend).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="7d5e1-420">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="7d5e1-421">Nein</span><span class="sxs-lookup"><span data-stu-id="7d5e1-421">No</span></span>  <br/> |<span data-ttu-id="7d5e1-422">Der Betreff des Quellelements.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="7d5e1-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-423">**DATE**</span></span> <br/> |<span data-ttu-id="7d5e1-424">Ja</span><span class="sxs-lookup"><span data-stu-id="7d5e1-424">Yes</span></span>  <br/> |<span data-ttu-id="7d5e1-425">Das Datum, an dem das Element ursprünglich in der Kundendatenquelle erstellt oder veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="7d5e1-426">Beispielsweise das Datum, an dem eine Twitter-Nachricht getwittert wurde.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="7d5e1-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-427">**BODY**</span></span> <br/> |<span data-ttu-id="7d5e1-428">Nein</span><span class="sxs-lookup"><span data-stu-id="7d5e1-428">No</span></span>  <br/> |<span data-ttu-id="7d5e1-429">Der Inhalt der Nachricht oder des Beitrags.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-429">The contents of the message or post.</span></span> <span data-ttu-id="7d5e1-430">Bei einigen Datenquellen kann der Inhalt dieser Eigenschaft mit dem Inhalt der Eigenschaft **SUBJECT** identisch sein.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="7d5e1-431">Während des Importvorgangs versucht der Partnerconnector, die vollständige Genauigkeit von der Inhaltsquelle so wie möglich zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="7d5e1-432">Soweit möglich, werden Dateien, Grafiken oder andere Inhalte aus dem Textkörper des Quellelements in diese Eigenschaft einbezogen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="7d5e1-433">Andernfalls wird der Inhalt aus dem Quellelement in die Eigenschaft **ATTACHMENT** einbezogen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="7d5e1-434">Der Inhalt dieser Eigenschaft hängt vom Partnerconnector und von der Funktion der Quellplattform ab.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="7d5e1-435">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="7d5e1-436">Nein</span><span class="sxs-lookup"><span data-stu-id="7d5e1-436">No</span></span>  <br/> |<span data-ttu-id="7d5e1-437">Wenn ein Element in der Datenquelle (z. B. ein Tweet in Twitter oder eine Instant Messaging-Unterhaltung) über eine angefügte Datei verfügt oder Bilder enthält, versucht die Partner-Verbindung zunächst, Anlagen in die **BODY-Eigenschaft** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="7d5e1-438">Wenn dies nicht möglich ist, wird es der \*\* ATTACHMENT \*\* -Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="7d5e1-439">Weitere Beispiele für Anlagen sind „Gefällt mir“-Angaben in Facebook, Metadaten aus der Inhaltsquelle und Antworten auf eine Nachricht oder einen Beitrag.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="7d5e1-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="7d5e1-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="7d5e1-441">Ja</span><span class="sxs-lookup"><span data-stu-id="7d5e1-441">Yes</span></span>  <br/> | <span data-ttu-id="7d5e1-442">Dies ist eine Eigenschaft mit mehreren Werten, die vom Partnerconnector erstellt und mit Werten gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="7d5e1-443">Das Format dieser Eigenschaft ist  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="7d5e1-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="7d5e1-444">(Diese Eigenschaft muss mit  `IPM.NOTE` beginnen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="7d5e1-445">Dieses Format ähnelt dem format für die  `IPM.NOTE.X` Nachrichtenklasse.) Diese Eigenschaft enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="7d5e1-446">`Source`: Gibt die Datenquelle eines Drittanbieters an; z. B. Twitter, Facebook oder BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="7d5e1-447">`Event`: Gibt den Typ der Aktivität an, die in der Datenquelle eines Drittanbieters ausgeführt wurde, von der die Elemente erstellt wurden; z. B. ein Tweet in Twitter oder ein Beitrag in Facebook.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="7d5e1-448">Ereignisse sind für die jeweilige Datenquelle spezifisch.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="7d5e1-449">Ein Zweck dieser Eigenschaft ist es zum Beispiel, bestimmte Elemente basierend auf der Datenquelle zu filtern, aus der ein Element stammt, oder basierend auf dem Typ des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="7d5e1-450">So könnten Sie in einer eDiscovery-Suche zum Beispiel eine Suchabfrage erstellen, um alle Tweets zu finden, die von einem bestimmten Benutzer gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="7d5e1-451">Wenn Elemente erfolgreich in Postfächer in Microsoft 365 importiert werden, wird ein eindeutiger Bezeichner als Teil der HTTP-Antwort an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="7d5e1-452">Dieser Bezeichner namens , kann für nachfolgende Problembehandlungszwecke von Partnern für die  `x-IngestionCorrelationID` End-to-End-Nachverfolgung von Elementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="7d5e1-453">Es wird empfohlen, dass Partner diese Informationen entsprechend erfassen und sammeln.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="7d5e1-454">Im Folgenden ist ein Beispiel einer HTTP-Antwort mit diesem Bezeichner aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="7d5e1-455">Sie können das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um nach Elementen zu suchen, die aus einer Datenquelle eines Drittanbieters in Postfächer importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="7d5e1-456">Um speziell nach diesen importierten Elementen zu suchen, können Sie die folgenden Nachrichteneigenschaft-Wert-Paare im Schlüsselwortfeld für eine Inhaltssuche verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="7d5e1-457">**`kind:externaldata`**: Verwenden Sie dieses Eigenschaften-Wert-Paar, um alle Datentypen von Drittanbietern zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="7d5e1-458">Wenn Sie beispielsweise nach Elementen suchen möchten, die aus einer Datenquelle eines Drittanbieters importiert wurden und das Wort "contoso" in der Subject-Eigenschaft des importierten Elements enthalten, verwenden Sie die Schlüsselwortabfrage  `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="7d5e1-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="7d5e1-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Verwenden Sie dieses Eigenschaften-Wert-Paar, um nur einen angegebenen Typ von Drittanbieterdaten zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="7d5e1-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="7d5e1-460">Wenn Sie beispielsweise nur Facebook-Daten durchsuchen möchten, die das Wort "contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die Schlüsselwortabfrage  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="7d5e1-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="7d5e1-461">Eine vollständige Liste der Werte, die für Drittanbieterdatentypen für die Eigenschaft verwendet werden sollen, finden Sie unter `itemclass` Use Content Search to search [third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="7d5e1-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="7d5e1-462">Weitere Informationen zur Verwendung der Inhaltssuche und zum Erstellen von Stichwortsuchabfragen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="7d5e1-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="7d5e1-463">Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="7d5e1-463">Content Search</span></span>](content-search.md)
    
  - [<span data-ttu-id="7d5e1-464">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="7d5e1-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)