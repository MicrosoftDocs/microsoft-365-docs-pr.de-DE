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
description: In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Connector zum Importieren von drittanbieterdaten aus Datenquellen wie Salesforce Chatter, Yahoo Messenger oder jammern einrichten.
ms.openlocfilehash: 64e903604ea56e5f53e3cc154bd54459a6d8d554
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620211"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="46a34-103">Zusammenarbeit mit einem Partner zum Archivieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="46a34-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="46a34-104">Sie können mit einem Microsoft-Partner zusammenarbeiten, um Daten aus einer Drittanbieter-Datenquelle in Microsoft 365 zu importieren und zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="46a34-105">Ein Partner kann Ihnen einen benutzerdefinierten Connector zur Verfügung stellen, der so konfiguriert ist, dass er Elemente aus der Drittanbieter-Datenquelle extrahiert (regelmäßig) und diese Elemente dann importiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="46a34-106">Der Partner Connector wandelt den Inhalt eines Elements aus der Datenquelle in ein e-Mail-Nachrichtenformat um und speichert dann die Elemente in Postfächern.</span><span class="sxs-lookup"><span data-stu-id="46a34-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="46a34-107">Nachdem Sie Daten von Drittanbietern importiert haben, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, In-Place Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf diese Daten anwenden.</span><span class="sxs-lookup"><span data-stu-id="46a34-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="46a34-108">Die [Kommunikations Kompatibilitäts](communication-compliance.md) Lösung in Microsoft 365 kann nicht auf die drittanbieterdaten angewendet werden, die von den in diesem Artikel erwähnten Partner-Konnektoren importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="46a34-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 

<span data-ttu-id="46a34-109">Im folgenden finden Sie eine Übersicht über den Prozess und die erforderlichen Schritte für die Zusammenarbeit mit einem Microsoft-Partner zum Importieren von drittanbieterdaten.</span><span class="sxs-lookup"><span data-stu-id="46a34-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="46a34-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="46a34-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="46a34-111">Schritt 2: Erstellen und Konfigurieren eines Drittanbieter-Daten Postfachs</span><span class="sxs-lookup"><span data-stu-id="46a34-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="46a34-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="46a34-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="46a34-113">Schritt 4: Bereitstellen von Informationen für Ihren Partner</span><span class="sxs-lookup"><span data-stu-id="46a34-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="46a34-114">Schritt 5: Registrieren des drittanbieterdaten-Konnektors in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="46a34-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="46a34-115">So funktioniert der Prozess zum Importieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="46a34-115">How the third-party data import process works</span></span>

<span data-ttu-id="46a34-116">In der folgenden Abbildung und Beschreibung wird erläutert, wie der Datenimportvorgang eines Drittanbieters bei der Arbeit mit einem Partner funktioniert.</span><span class="sxs-lookup"><span data-stu-id="46a34-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![So funktioniert der Prozess zum Importieren von Drittanbieterdaten](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="46a34-118">Der Kunde arbeitet mit seinem Partner an der Wahl, um einen Connector zu konfigurieren, der Elemente aus der Drittanbieter-Datenquelle extrahiert und diese Elemente dann nach Microsoft 365 importiert wird.</span><span class="sxs-lookup"><span data-stu-id="46a34-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="46a34-119">Der Partner Connector stellt über eine API eines Drittanbieters (auf geplanter oder konfigurierter Basis) eine Verbindung mit Drittanbieter-Datenquellen her und extrahiert Elemente aus der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="46a34-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="46a34-120">Der Partnerconnector konvertiert den Inhalt eines Elements in ein E-Mail-Format.</span><span class="sxs-lookup"><span data-stu-id="46a34-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="46a34-121">Eine Beschreibung des Nachrichtenformat Schemas finden Sie im Abschnitt [Weitere Informationen](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="46a34-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="46a34-122">Partner Connector stellt über einen bekannten Endpunkt eine Verbindung mit dem Azure-Dienst in Microsoft 365 mithilfe des Exchange-Webdiensts (EWS) her.</span><span class="sxs-lookup"><span data-stu-id="46a34-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="46a34-p103">Elemente werden in das Postfach eines bestimmten Benutzers oder in ein spezielles Postfach zur Aufnahme aller Drittanbieterdaten importiert. Ob ein Element in das Postfach eines bestimmten Benutzers oder in das Postfach für Drittanbieterdaten importiert wird, basiert auf den folgenden Kriterien:</span><span class="sxs-lookup"><span data-stu-id="46a34-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="46a34-125">**Elemente mit einer Benutzer-ID, die einem Benutzerkonto entspricht:** Wenn der Partner Connector die Benutzer-ID des Elements in der Drittanbieter-Datenquelle einer bestimmten Benutzer-ID in Microsoft 365 zuordnen kann, wird das Element in den Ordner " **Bereinigungen** " des Ordners "refundable Items" des Benutzers kopiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="46a34-126">Benutzer können nicht auf Elemente im Ordner „Endgültige Löschvorgänge“ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="46a34-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="46a34-127">Sie können jedoch eDiscovery-Tools verwenden, um nach Elementen im Ordner "Säuberungen" zu suchen.</span><span class="sxs-lookup"><span data-stu-id="46a34-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="46a34-128">**Elemente, die nicht über eine Benutzer-ID verfügen, die einem Benutzerkonto entspricht:** Wenn der Partner Connector die Benutzer-ID eines Elements nicht einer bestimmten Benutzer-ID zuordnen kann, wird das Element in den Ordner **Posteingangs** Verzeichnis des Drittanbieter-Daten Postfachs kopiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="46a34-129">Das Importieren von Elementen in den Posteingang ermöglicht Ihnen oder einem anderen Benutzer in Ihrer Organisation, sich beim Drittanbieter-Postfach anzumelden und diese Elemente zu verwalten und zu sehen, ob Anpassungen an der Partnerconnectorkonfiguration vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="46a34-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="46a34-130">Schritt 1: Partner für Drittanbieterdaten suchen</span><span class="sxs-lookup"><span data-stu-id="46a34-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="46a34-131">Eine wichtige Komponente für das Archivieren von drittanbieterdaten in Microsoft 365 besteht darin, einen Microsoft-Partner zu finden und zu verwenden, der sich auf das Erfassen von Daten aus einer Drittanbieter-Datenquelle und das Importieren dieser Daten in Microsoft 365 spezialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="46a34-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="46a34-132">Nachdem die Daten importiert wurden, können Sie zusammen mit anderen Microsoft-Daten Ihrer Organisation wie e-Mails von Exchange und Dokumenten aus SharePoint und OneDrive für Unternehmen archiviert und aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="46a34-133">Ein Partner erstellt einen Konnektor, der Daten aus den drittanbieterdaten Quellen Ihrer Organisation extrahiert (wie BlackBerry, Facebook, Google +, Thomson Reuters, Twitter und YouTube) und übergibt diese Daten an eine Microsoft 365-API, die Elemente als e-Mail-Nachrichten in Exchange-Postfächer importiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>
  
<span data-ttu-id="46a34-134">In den folgenden Abschnitten werden die Microsoft-Partner (und die von Ihnen unterstützten drittanbieterdaten Quellen) aufgeführt, die am Programm zum Archivieren von drittanbieterdaten in Microsoft 365 teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="46a34-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="46a34-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="46a34-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="46a34-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="46a34-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="46a34-137">Globanet</span><span class="sxs-lookup"><span data-stu-id="46a34-137">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="46a34-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="46a34-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="46a34-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="46a34-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="46a34-140">Verba</span><span class="sxs-lookup"><span data-stu-id="46a34-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="46a34-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="46a34-141">17a-4 LLC</span></span>

<span data-ttu-id="46a34-142">die [17a-4 LLC](https://www.17a-4.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="46a34-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="46a34-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="46a34-143">BlackBerry</span></span>
    
- <span data-ttu-id="46a34-144">Bloomberg Data Streams</span><span class="sxs-lookup"><span data-stu-id="46a34-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="46a34-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="46a34-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="46a34-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="46a34-146">FactSet</span></span>
    
- <span data-ttu-id="46a34-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="46a34-147">HipChat</span></span>
    
- <span data-ttu-id="46a34-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="46a34-148">InvestEdge</span></span>
    
- <span data-ttu-id="46a34-149">Schwätzchen</span><span class="sxs-lookup"><span data-stu-id="46a34-149">LivePerson</span></span>
    
- <span data-ttu-id="46a34-150">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="46a34-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="46a34-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="46a34-151">OpenText</span></span>
    
- <span data-ttu-id="46a34-152">Live-Hilfe für Oracle/ATG 'click-to-call'</span><span class="sxs-lookup"><span data-stu-id="46a34-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="46a34-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="46a34-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="46a34-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="46a34-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="46a34-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="46a34-155">MindAlign</span></span>
    
- <span data-ttu-id="46a34-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="46a34-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="46a34-157">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="46a34-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="46a34-158">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="46a34-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="46a34-159">SQL-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="46a34-159">SQL Databases</span></span>
    
- <span data-ttu-id="46a34-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="46a34-160">Squawker</span></span>
    
- <span data-ttu-id="46a34-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="46a34-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="46a34-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="46a34-162">ArchiveSocial</span></span>

<span data-ttu-id="46a34-163">[ArchiveSocial ](https://www.archivesocial.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="46a34-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="46a34-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="46a34-164">Facebook</span></span>
    
- <span data-ttu-id="46a34-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="46a34-165">Flickr</span></span>
    
- <span data-ttu-id="46a34-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="46a34-166">Instagram</span></span>
    
- <span data-ttu-id="46a34-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="46a34-167">LinkedIn</span></span>
    
- <span data-ttu-id="46a34-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="46a34-168">Pinterest</span></span>
    
- <span data-ttu-id="46a34-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="46a34-169">Twitter</span></span>
    
- <span data-ttu-id="46a34-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="46a34-170">YouTube</span></span>
    
- <span data-ttu-id="46a34-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="46a34-171">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="46a34-172">Globanet</span><span class="sxs-lookup"><span data-stu-id="46a34-172">Globanet</span></span>

<span data-ttu-id="46a34-173">[Globanet](https://www.globanet.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="46a34-173">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="46a34-174">AOL mit Pivot-Client
</span><span class="sxs-lookup"><span data-stu-id="46a34-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="46a34-175">BlackBerry-Anrufprotokolle (v5, v10, v12)
</span><span class="sxs-lookup"><span data-stu-id="46a34-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-176">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-177">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-178">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-179">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="46a34-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="46a34-180">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="46a34-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="46a34-181">Box</span><span class="sxs-lookup"><span data-stu-id="46a34-181">Box</span></span>
    
- <span data-ttu-id="46a34-182">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="46a34-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="46a34-183">Cisco Chat &amp; Presence Server (v10, v 10.5.1 SU1, v 11.0, v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="46a34-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="46a34-184">Cisco WebEx-Teams</span><span class="sxs-lookup"><span data-stu-id="46a34-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="46a34-185">Citrix-Arbeitsbereichs &amp; Freigabe</span><span class="sxs-lookup"><span data-stu-id="46a34-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="46a34-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="46a34-186">CrowdCompass</span></span>

- <span data-ttu-id="46a34-187">Benutzerdefinierte Textdateien mit Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="46a34-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="46a34-188">Benutzerdefinierte XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="46a34-188">Custom XML files</span></span>
    
- <span data-ttu-id="46a34-189">Facebook (Seiten)</span><span class="sxs-lookup"><span data-stu-id="46a34-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="46a34-190">FactSet</span><span class="sxs-lookup"><span data-stu-id="46a34-190">Factset</span></span>
    
- <span data-ttu-id="46a34-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="46a34-191">FXConnect</span></span>
    
- <span data-ttu-id="46a34-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="46a34-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="46a34-193">Jive</span><span class="sxs-lookup"><span data-stu-id="46a34-193">Jive</span></span>
    
- <span data-ttu-id="46a34-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="46a34-194">Macgregor XIP</span></span>

- <span data-ttu-id="46a34-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="46a34-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="46a34-196">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="46a34-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="46a34-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46a34-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="46a34-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="46a34-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="46a34-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="46a34-199">Mobile Guard</span></span>
    
- <span data-ttu-id="46a34-200">Pivot</span><span class="sxs-lookup"><span data-stu-id="46a34-200">Pivot</span></span>
    
- <span data-ttu-id="46a34-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="46a34-201">Salesforce Chatter</span></span>

- <span data-ttu-id="46a34-202">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="46a34-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="46a34-203">Skype for Business, Versionen 2007 R2 - 2016 (lokal)</span><span class="sxs-lookup"><span data-stu-id="46a34-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="46a34-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="46a34-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="46a34-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="46a34-205">Symphony</span></span>
    
- <span data-ttu-id="46a34-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="46a34-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="46a34-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="46a34-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="46a34-208">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="46a34-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="46a34-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="46a34-209">Twitter</span></span>
    
- <span data-ttu-id="46a34-210">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="46a34-210">UBS Chat</span></span>
    
- <span data-ttu-id="46a34-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="46a34-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="46a34-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="46a34-212">OpenText</span></span>

<span data-ttu-id="46a34-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="46a34-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="46a34-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="46a34-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="46a34-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="46a34-215">Axs Exchange</span></span>
    
- <span data-ttu-id="46a34-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="46a34-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="46a34-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="46a34-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="46a34-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="46a34-218">Axs Signed</span></span>
    
- <span data-ttu-id="46a34-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="46a34-219">Bloomberg</span></span>
    
- <span data-ttu-id="46a34-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="46a34-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="46a34-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="46a34-221">Smarsh</span></span>

<span data-ttu-id="46a34-222">[Smarsh](https://www.smarsh.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="46a34-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="46a34-223">Versuchen</span><span class="sxs-lookup"><span data-stu-id="46a34-223">AIM</span></span>
    
- <span data-ttu-id="46a34-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="46a34-224">American Idol</span></span>
    
- <span data-ttu-id="46a34-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="46a34-225">Apple Juice</span></span>
    
- <span data-ttu-id="46a34-226">AOL mit Pivot-Client</span><span class="sxs-lookup"><span data-stu-id="46a34-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="46a34-227">Ares</span><span class="sxs-lookup"><span data-stu-id="46a34-227">Ares</span></span>
    
- <span data-ttu-id="46a34-228">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="46a34-229">Bear Share</span><span class="sxs-lookup"><span data-stu-id="46a34-229">Bear Share</span></span>
    
- <span data-ttu-id="46a34-230">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="46a34-230">Bit Torrent</span></span>
    
- <span data-ttu-id="46a34-231">BlackBerry-Anrufprotokolle (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-232">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-233">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-234">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="46a34-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="46a34-235">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="46a34-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="46a34-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="46a34-236">CellTrust</span></span>
    
- <span data-ttu-id="46a34-237">Chat Import</span><span class="sxs-lookup"><span data-stu-id="46a34-237">Chat Import</span></span>
    
- <span data-ttu-id="46a34-238">Echtzeitprotokollierung und -richtinie für Chat</span><span class="sxs-lookup"><span data-stu-id="46a34-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="46a34-239">Störgeräusche</span><span class="sxs-lookup"><span data-stu-id="46a34-239">Chatter</span></span>
    
- <span data-ttu-id="46a34-240">Cisco Chat &amp; Presence Server (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="46a34-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="46a34-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="46a34-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="46a34-242">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="46a34-242">Collaboration Import</span></span>
    
- <span data-ttu-id="46a34-243">Echtzeitprotokollierung für Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="46a34-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="46a34-244">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="46a34-244">Direct Connect</span></span>
    
- <span data-ttu-id="46a34-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="46a34-245">Facebook</span></span>
    
- <span data-ttu-id="46a34-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="46a34-246">FactSet</span></span>
    
- <span data-ttu-id="46a34-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="46a34-247">FastTrack</span></span>
    
- <span data-ttu-id="46a34-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="46a34-248">Gnutella</span></span>
    
- <span data-ttu-id="46a34-249">Google +</span><span class="sxs-lookup"><span data-stu-id="46a34-249">Google+</span></span>
    
- <span data-ttu-id="46a34-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="46a34-250">GoToMyPC</span></span>
    
- <span data-ttu-id="46a34-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="46a34-251">Hopster</span></span>
    
- <span data-ttu-id="46a34-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="46a34-252">HubConnex</span></span>
    
- <span data-ttu-id="46a34-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="46a34-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="46a34-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="46a34-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="46a34-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="46a34-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="46a34-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="46a34-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="46a34-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="46a34-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="46a34-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="46a34-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="46a34-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="46a34-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="46a34-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="46a34-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="46a34-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="46a34-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="46a34-262">Ice/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="46a34-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="46a34-263">Chat-Import</span><span class="sxs-lookup"><span data-stu-id="46a34-263">IM Import</span></span>
    
- <span data-ttu-id="46a34-264">Echtzeitprotokollierung und -richtinie für Chat</span><span class="sxs-lookup"><span data-stu-id="46a34-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="46a34-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="46a34-265">Indii Messenger</span></span>
    
- <span data-ttu-id="46a34-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="46a34-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="46a34-267">IRC</span><span class="sxs-lookup"><span data-stu-id="46a34-267">IRC</span></span>
    
- <span data-ttu-id="46a34-268">Jive</span><span class="sxs-lookup"><span data-stu-id="46a34-268">Jive</span></span>
    
- <span data-ttu-id="46a34-269">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="46a34-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="46a34-270">Jive Import</span><span class="sxs-lookup"><span data-stu-id="46a34-270">Jive Import</span></span>
    
- <span data-ttu-id="46a34-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="46a34-271">JXTA</span></span>
    
- <span data-ttu-id="46a34-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="46a34-272">LinkedIn</span></span>
    
- <span data-ttu-id="46a34-273">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="46a34-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="46a34-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="46a34-274">MFTP</span></span>
    
- <span data-ttu-id="46a34-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="46a34-276">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="46a34-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="46a34-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="46a34-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="46a34-278">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="46a34-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="46a34-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="46a34-279">MindAlign</span></span>
    
- <span data-ttu-id="46a34-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="46a34-280">Mobile Guard</span></span>
    
- <span data-ttu-id="46a34-281">MSN</span><span class="sxs-lookup"><span data-stu-id="46a34-281">MSN</span></span>
    
- <span data-ttu-id="46a34-282">My Space</span><span class="sxs-lookup"><span data-stu-id="46a34-282">My Space</span></span>
    
- <span data-ttu-id="46a34-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="46a34-283">NEONetwork</span></span>
    
- <span data-ttu-id="46a34-284">Dediziertes Microsoft 365 lync</span><span class="sxs-lookup"><span data-stu-id="46a34-284">Microsoft 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="46a34-285">Microsoft 365 Shared Chat</span><span class="sxs-lookup"><span data-stu-id="46a34-285">Microsoft 365 Shared IM</span></span>
    
- <span data-ttu-id="46a34-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="46a34-286">Pinterest</span></span>
    
- <span data-ttu-id="46a34-287">Pivot</span><span class="sxs-lookup"><span data-stu-id="46a34-287">Pivot</span></span>
    
- <span data-ttu-id="46a34-288">QQ</span><span class="sxs-lookup"><span data-stu-id="46a34-288">QQ</span></span>
    
- <span data-ttu-id="46a34-289">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="46a34-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="46a34-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="46a34-290">SoftEther</span></span>
    
- <span data-ttu-id="46a34-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="46a34-291">Symphony</span></span>
    
- <span data-ttu-id="46a34-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="46a34-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="46a34-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="46a34-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="46a34-294">Tor</span><span class="sxs-lookup"><span data-stu-id="46a34-294">Tor</span></span>
    
- <span data-ttu-id="46a34-295">TTT</span><span class="sxs-lookup"><span data-stu-id="46a34-295">TTT</span></span>
    
- <span data-ttu-id="46a34-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="46a34-296">Twitter</span></span>
    
- <span data-ttu-id="46a34-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="46a34-297">WinMX</span></span>
    
- <span data-ttu-id="46a34-298">Winny</span><span class="sxs-lookup"><span data-stu-id="46a34-298">Winny</span></span>
    
- <span data-ttu-id="46a34-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="46a34-299">Yahoo</span></span>
    
- <span data-ttu-id="46a34-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="46a34-300">Yammer</span></span>
    
- <span data-ttu-id="46a34-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="46a34-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="46a34-302">Verba</span><span class="sxs-lookup"><span data-stu-id="46a34-302">Verba</span></span>

<span data-ttu-id="46a34-303">[Verba](https://www.verba.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="46a34-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="46a34-304">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="46a34-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="46a34-305">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="46a34-306">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="46a34-306">Avtec Radio</span></span>
    
- <span data-ttu-id="46a34-307">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="46a34-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="46a34-308">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="46a34-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="46a34-309">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="46a34-310">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-310">Centile Voice</span></span>
    
- <span data-ttu-id="46a34-311">Chatnachricht in Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="46a34-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="46a34-312">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="46a34-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="46a34-313">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="46a34-314">Cisco UCCX/UCCE-Video</span><span class="sxs-lookup"><span data-stu-id="46a34-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="46a34-315">Cisco UCCX/UCCE-VoIP</span><span class="sxs-lookup"><span data-stu-id="46a34-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="46a34-316">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="46a34-316">ESChat Radio</span></span>
    
- <span data-ttu-id="46a34-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="46a34-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="46a34-318">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="46a34-319">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="46a34-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="46a34-320">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="46a34-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="46a34-321">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="46a34-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="46a34-322">Oracle/Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="46a34-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="46a34-323">Oracle/Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="46a34-324">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="46a34-325">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="46a34-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="46a34-326">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="46a34-327">Chatnachricht in Skype for Business/Lync</span><span class="sxs-lookup"><span data-stu-id="46a34-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="46a34-328">Skype for Business/Lync Video</span><span class="sxs-lookup"><span data-stu-id="46a34-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="46a34-329">Skype for Business/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="46a34-330">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="46a34-331">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="46a34-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="46a34-332">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="46a34-333">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="46a34-333">Truphone Voice</span></span>
    
- <span data-ttu-id="46a34-334">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="46a34-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="46a34-335">Windows Desktop-Computerbildschirm</span><span class="sxs-lookup"><span data-stu-id="46a34-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="46a34-336">Schritt 2: Erstellen und Konfigurieren eines Drittanbieter-Daten Postfachs in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46a34-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="46a34-337">Hier finden Sie die Schritte zum Erstellen und Konfigurieren eines Drittanbieter-Daten Postfachs zum Importieren von Daten nach Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46a34-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="46a34-338">Wie bereits erläutert, werden Elemente in dieses Postfach importiert, wenn der Partner Connector die Benutzer-ID des Elements keinem Benutzerkonto zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="46a34-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="46a34-339">**Führen Sie diese Aufgaben im Microsoft 365 Admin Center aus.**</span><span class="sxs-lookup"><span data-stu-id="46a34-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="46a34-340">Erstellen Sie ein Benutzerkonto, und weisen Sie ihm eine Lizenz für Exchange Online Plan 2 zu. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern zu Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="46a34-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="46a34-341">Eine Plan 2-Lizenz ist erforderlich, um das Postfach in einem Beweissicherungsverfahren aufzubewahren oder ein Archivpostfach mit einem unbegrenzten Speicherkontingent zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="46a34-342">Fügen Sie das Benutzerkonto für das Drittanbieter-Daten Postfach der **Administratorrolle Exchange-Administrator** in Microsoft 365 hinzu. Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="46a34-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="46a34-343">Notieren Sie die Anmeldeinformationen für dieses Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="46a34-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="46a34-344">Sie müssen diese für Ihren Partner bereitstellen, wie in Schritt 4 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46a34-344">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="46a34-345">**Führen Sie diese Aufgaben im Exchange Admin Center aus.**</span><span class="sxs-lookup"><span data-stu-id="46a34-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="46a34-346">Ausblenden des Drittanbieter-Daten Postfachs aus dem Adressbuch und anderen Adresslisten in Ihrer Organisation; Weitere Informationen finden Sie unter [Verwalten von Benutzerpostfächern](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="46a34-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="46a34-347">Alternativ können Sie den folgenden PowerShell-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="46a34-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="46a34-348">Weisen Sie dem Drittanbieter-Daten Postfach die Berechtigung **FullAccess** zu, damit Administratoren oder Compliance Officer das Drittanbieter-Daten Postfach im Outlook-Desktop Client öffnen können. Weitere Informationen finden Sie unter [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="46a34-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="46a34-349">Aktivieren Sie die folgenden kompatibilitätsbezogenen Funktionen für das Drittanbieter-Daten Postfach:</span><span class="sxs-lookup"><span data-stu-id="46a34-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="46a34-350">Aktivieren des Archivpostfachs siehe [Aktivieren von archivpostfächern](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="46a34-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="46a34-351">Auf diese Weise können Sie Speicherplatz im primären Postfach freigeben, indem Sie eine Archivrichtlinie einrichten, mit der Datenelemente von Drittanbietern in das Archivpostfach verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="46a34-352">Dadurch erhalten Sie unbegrenzten Speicher für drittanbieterdaten.</span><span class="sxs-lookup"><span data-stu-id="46a34-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="46a34-353">Aktivieren Sie für das Drittanbieterdaten-Postfach das Beweissicherungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="46a34-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="46a34-354">Sie können auch eine Microsoft 365-Aufbewahrungsrichtlinie im Security and Compliance Center anwenden.</span><span class="sxs-lookup"><span data-stu-id="46a34-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="46a34-355">Beim Platzieren dieses Postfachs bleiben Datenelemente von Drittanbietern (auf unbestimmte Zeit oder für eine bestimmte Dauer) erhalten und verhindern, dass Sie aus dem Postfach gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="46a34-356">Lesen Sie eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="46a34-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="46a34-357">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="46a34-357">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="46a34-358">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="46a34-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="46a34-359">Aktivieren der postfachüberwachungsprotokollierung für den Besitzer-, Stellvertreter-und Administratorzugriff auf das Daten Postfach eines Drittanbieters; siehe [Aktivieren der postfachüberwachung](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="46a34-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="46a34-360">Auf diese Weise können Sie alle von Benutzern ausgeführten Aktivitäten überwachen, die Zugriff auf das Daten Postfach eines Drittanbieters haben.</span><span class="sxs-lookup"><span data-stu-id="46a34-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="46a34-361">Schritt 3: Benutzerpostfächer für Drittanbieterdaten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="46a34-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="46a34-362">Als Nächstes müssen Sie die Benutzerpostfächer für die Unterstützung von Drittanbieterdaten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="46a34-363">Führen Sie diese Aufgaben mithilfe der Exchange-Verwaltungskonsole oder mithilfe der entsprechenden Windows PowerShell-Cmdlets aus.</span><span class="sxs-lookup"><span data-stu-id="46a34-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="46a34-364">Aktivieren Sie das Archivpostfach für jeden Benutzer. siehe [Aktivieren von archivpostfächern](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="46a34-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="46a34-365">Platzieren von Benutzerpostfächern für das Beweissicherungsverfahren oder Anwenden einer Microsoft 365-Aufbewahrungsrichtlinie Lesen Sie eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="46a34-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="46a34-366">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="46a34-366">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="46a34-367">Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="46a34-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="46a34-368">Wie bereits weiter oben erwähnt, können Sie beim Aktivieren des Beweissicherungsverfahrens für Postfächer festlegen, wie lange Elemente aus einer Drittanbieter-Datenquelle aufbewahrt werden sollen. Sie können auch festlegen, dass sie dauerhaft aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="46a34-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="46a34-369">Schritt 4: Bereitstellen von Informationen für Ihren Partner</span><span class="sxs-lookup"><span data-stu-id="46a34-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="46a34-370">Der letzte Schritt besteht darin, dem Partner die folgenden Informationen bereitzustellen, damit er den Connector für die Verbindung mit Ihrer Organisation konfigurieren kann, um Daten in Benutzerpostfächer und das Drittanbieter-Daten Postfach zu importieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="46a34-371">Der Endpunkt, der zum Herstellen einer Verbindung mit dem Azure-Dienst in Microsoft 365 verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="46a34-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="46a34-372">Die Anmeldeinformationen (Benutzer-ID und Kennwort von Microsoft 365) des Drittanbieter-Daten Postfachs, das Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="46a34-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="46a34-373">Diese Anmeldeinformationen sind erforderlich, damit der Partnerconnector auf Elemente zugreifen und sie in das Drittanbieterdaten-Postfach importieren kann.</span><span class="sxs-lookup"><span data-stu-id="46a34-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="46a34-374">Schritt 5: Registrieren des drittanbieterdaten-Konnektors in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="46a34-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="46a34-375">Ab dem 30. September 2018 wird der Azure-Dienst in Microsoft 365 die moderne Authentifizierung in Exchange Online verwenden, um Daten Konnektoren von Drittanbietern zu authentifizieren, die versuchen, eine Verbindung mit Ihrer Organisation herzustellen, um Daten zu importieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="46a34-376">Der Grund für diese Änderung besteht darin, dass die moderne Authentifizierung mehr Sicherheit bietet als die aktuelle Methode, die auf einer Zulassungsliste für Connectors von Drittanbietern basiert, die den zuvor beschriebenen Endpunkt zum Herstellen einer Verbindung mit dem Azure-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="46a34-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="46a34-377">Damit ein Drittanbieter-Daten Konnektor mithilfe der neuen modernen Authentifizierungsmethode eine Verbindung mit Microsoft 365 herstellen kann, muss ein Administrator in Ihrer Organisation einwilligen, den Connector als vertrauenswürdige Dienstanwendung in Azure Active Directory zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="46a34-378">Dies erfolgt durch Annahme einer Berechtigungsanforderung, damit der Connector auf die Daten Ihrer Organisation in Azure Active Directory zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="46a34-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="46a34-379">Nachdem Sie diese Anforderung angenommen haben, wird der Drittanbieter-Daten Konnektor als Unternehmensanwendung zu Azure Active Directory hinzugefügt und als Dienstprinzipal dargestellt.</span><span class="sxs-lookup"><span data-stu-id="46a34-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="46a34-380">Weitere Informationen zum Zustimmungsprozess finden Sie unter  [Mandanten-admin-Zustimmung](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="46a34-380">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="46a34-381">Hier sind die Schritte zum Zugreifen auf und akzeptieren der Anforderung zum Registrieren des Connectors:</span><span class="sxs-lookup"><span data-stu-id="46a34-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="46a34-382">Wechseln Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) , und melden Sie sich mit den Anmeldeinformationen eines globalen Administrators an.</span><span class="sxs-lookup"><span data-stu-id="46a34-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="46a34-383">Das folgende Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46a34-383">The following dialog box is displayed.</span></span> <span data-ttu-id="46a34-384">Sie können die Carets erweitern, um die Berechtigungen zu überprüfen, die dem Connector zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Das Dialogfeld Berechtigungsanforderung wird angezeigt.](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="46a34-386">Klicken Sie auf **Annehmen**.</span><span class="sxs-lookup"><span data-stu-id="46a34-386">Click **Accept**.</span></span>

<span data-ttu-id="46a34-387">Nachdem Sie die Anforderung angenommen haben, wird das [Azure-Portal](https://portal.azure.com) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46a34-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="46a34-388">Um die Liste der Anwendungen für Ihre Organisation anzuzeigen, klicken Sie auf **Azure Active Directory**  >  **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="46a34-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="46a34-389">Der Microsoft 365-Drittanbieter-Daten Konnektor wird auf dem Blade **Enterprise-Anwendungen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="46a34-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46a34-390">Nach dem 30. September 2018 werden drittanbieterdaten nicht mehr in Postfächer in Ihrer Organisation importiert, wenn Sie keinen Daten Konnektor eines Drittanbieters in Azure Active Directory registrieren.</span><span class="sxs-lookup"><span data-stu-id="46a34-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="46a34-391">Hinweis vorhandene Drittanbieter-Daten-Konnektoren (die vor dem 30. September 2018 erstellt wurden) müssen ebenfalls in Azure Active Directory registriert werden, indem Sie das Verfahren in Schritt 5 ausführen.</span><span class="sxs-lookup"><span data-stu-id="46a34-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="46a34-392">Widerrufen der Zustimmung für einen Daten Konnektor eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="46a34-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="46a34-393">Nachdem Ihre Organisation der Berechtigungsanforderung zugestimmt hat, um einen Drittanbieter-Daten Konnektor in Azure Active Directory zu registrieren, kann Ihre Organisation diese Zustimmung jederzeit widerrufen.</span><span class="sxs-lookup"><span data-stu-id="46a34-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="46a34-394">Das Widerrufen der Zustimmung für einen Connector bedeutet jedoch, dass Daten aus der Drittanbieter-Datenquelle nicht mehr in Microsoft 365 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="46a34-395">Um die Zustimmung für einen Drittanbieter-Datenconnector zu widerrufen, können Sie die Anwendung (durch Löschen des entsprechenden Dienst Prinzipals) aus Azure Active Directory mithilfe des Blades **Enterprise-Anwendungen** im Azure-Portal oder mithilfe der [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell löschen.</span><span class="sxs-lookup"><span data-stu-id="46a34-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="46a34-396">Sie können auch das Cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="46a34-396">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="46a34-397">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46a34-397">More information</span></span>

- <span data-ttu-id="46a34-398">Wie bereits weiter oben erläutert, werden Elemente aus Drittanbieter-Datenquellen als E-Mail-Nachrichten in Exchange-Postfächer importiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="46a34-399">Der Partner Connector importiert das Element mithilfe eines Schemas, das für die Microsoft 365-API erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="46a34-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="46a34-400">Die folgende Tabelle beschreibt die Nachrichteneigenschaften eines Elements aus einer Drittanbieter-Datenquelle, nachdem es als E-Mail-Nachricht in ein Exchange-Postfach importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="46a34-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="46a34-401">Zudem ist angegeben, wenn die Nachrichteneigenschaft zwingend erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="46a34-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="46a34-402">Erforderliche Eigenschaften müssen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="46a34-403">Wenn ein Element eine obligatorische Eigenschaft fehlt, wird es nicht in Microsoft 365 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="46a34-404">Beim Importvorgang wird eine Fehlermeldung mit der Erläuterung zurückgegeben, warum ein Element nicht importiert wurde und welche Eigenschaft fehlt.</span><span class="sxs-lookup"><span data-stu-id="46a34-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="46a34-405">**Nachrichteneigenschaft**</span><span class="sxs-lookup"><span data-stu-id="46a34-405">**Message property**</span></span>|<span data-ttu-id="46a34-406">**Erforderlich?**</span><span class="sxs-lookup"><span data-stu-id="46a34-406">**Mandatory?**</span></span>|<span data-ttu-id="46a34-407">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="46a34-407">**Description**</span></span>|<span data-ttu-id="46a34-408">**Beispielwert**</span><span class="sxs-lookup"><span data-stu-id="46a34-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="46a34-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="46a34-409">**FROM**</span></span> <br/> |<span data-ttu-id="46a34-410">Ja</span><span class="sxs-lookup"><span data-stu-id="46a34-410">Yes</span></span>  <br/> |<span data-ttu-id="46a34-411">Der Benutzer, der das Element in der Drittanbieter-Datenquelle ursprünglich erstellt oder gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="46a34-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="46a34-412">Der Partner Connector versucht, die Benutzer-ID des Quellelements (beispielsweiseeines Twitter-Handles) einem Benutzerkonto für alle Teilnehmer (Benutzer in den Feldern von und bis) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="46a34-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="46a34-413">Eine Kopie der Nachricht wird in das Postfach jedes Teilnehmers importiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="46a34-414">Wenn keines der Teilnehmer aus dem Element einem Benutzerkonto zugeordnet werden kann, wird das Element in das Archivierungs Postfach eines Drittanbieters in Microsoft 365 importiert.</span><span class="sxs-lookup"><span data-stu-id="46a34-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="46a34-415">Der Teilnehmer, der als Absender des Elements identifiziert wird, muss über ein aktives Postfach in der Organisation verfügen, in das das Element importiert wird.</span><span class="sxs-lookup"><span data-stu-id="46a34-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="46a34-416">Wenn der Absender nicht über ein aktives Postfach verfügt, wird der folgende Fehler zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="46a34-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="46a34-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="46a34-417">**TO**</span></span> <br/> |<span data-ttu-id="46a34-418">Ja</span><span class="sxs-lookup"><span data-stu-id="46a34-418">Yes</span></span>  <br/> |<span data-ttu-id="46a34-419">Der Benutzer, der ein Element erhalten hat (wenn für ein Element in der Datenquelle zutreffend).</span><span class="sxs-lookup"><span data-stu-id="46a34-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="46a34-420">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="46a34-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="46a34-421">Nein</span><span class="sxs-lookup"><span data-stu-id="46a34-421">No</span></span>  <br/> |<span data-ttu-id="46a34-422">Der Betreff des Quellelements.</span><span class="sxs-lookup"><span data-stu-id="46a34-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="46a34-423">**Datum**</span><span class="sxs-lookup"><span data-stu-id="46a34-423">**DATE**</span></span> <br/> |<span data-ttu-id="46a34-424">Ja</span><span class="sxs-lookup"><span data-stu-id="46a34-424">Yes</span></span>  <br/> |<span data-ttu-id="46a34-425">Das Datum, an dem das Element ursprünglich erstellt oder in der Kundendatenquelle veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="46a34-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="46a34-426">Beispielsweise dieses Datum, an dem eine Twitter-Nachricht getweetet wurde.</span><span class="sxs-lookup"><span data-stu-id="46a34-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="46a34-427">**Text**</span><span class="sxs-lookup"><span data-stu-id="46a34-427">**BODY**</span></span> <br/> |<span data-ttu-id="46a34-428">Nein</span><span class="sxs-lookup"><span data-stu-id="46a34-428">No</span></span>  <br/> |<span data-ttu-id="46a34-429">Der Inhalt der Nachricht oder des Beitrags.</span><span class="sxs-lookup"><span data-stu-id="46a34-429">The contents of the message or post.</span></span> <span data-ttu-id="46a34-430">Bei einigen Datenquellen kann der Inhalt dieser Eigenschaft mit dem Inhalt der Eigenschaft **SUBJECT** identisch sein.</span><span class="sxs-lookup"><span data-stu-id="46a34-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="46a34-431">Während des Importvorgangs versucht der Partner Connector, die vollständige Genauigkeit von der Inhaltsquelle wie möglich beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="46a34-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="46a34-432">Soweit möglich, werden Dateien, Grafiken oder andere Inhalte aus dem Textkörper des Quellelements in diese Eigenschaft einbezogen.</span><span class="sxs-lookup"><span data-stu-id="46a34-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="46a34-433">Andernfalls wird der Inhalt aus dem Quellelement in die Eigenschaft **ATTACHMENT** einbezogen.</span><span class="sxs-lookup"><span data-stu-id="46a34-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="46a34-434">Der Inhalt dieser Eigenschaft hängt vom Partner-Konnektor und der Funktion der QuellPlattform ab.</span><span class="sxs-lookup"><span data-stu-id="46a34-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="46a34-435">**Anlage**</span><span class="sxs-lookup"><span data-stu-id="46a34-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="46a34-436">Nein</span><span class="sxs-lookup"><span data-stu-id="46a34-436">No</span></span>  <br/> |<span data-ttu-id="46a34-437">Wenn ein Element in der Datenquelle (beispielsweise ein tweet in Twitter oder eine Chatnachrichten Unterhaltung) über eine angefügte Datei verfügt oder Bilder enthält, versucht der Partner Connect zunächst, Anlagen in die **Body** -Eigenschaft einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="46a34-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="46a34-438">Wenn dies nicht möglich ist, wird es zur \* \* Attachment \* \*-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="46a34-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="46a34-439">Weitere Beispiele für Anlagen sind „Gefällt mir“-Angaben in Facebook, Metadaten aus der Inhaltsquelle und Antworten auf eine Nachricht oder einen Beitrag.</span><span class="sxs-lookup"><span data-stu-id="46a34-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="46a34-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="46a34-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="46a34-441">Ja</span><span class="sxs-lookup"><span data-stu-id="46a34-441">Yes</span></span>  <br/> | <span data-ttu-id="46a34-442">Dies ist eine Eigenschaft mit mehreren Werten, die vom Partnerconnector erstellt und mit Werten gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="46a34-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="46a34-443">Das Format dieser Eigenschaft ist  `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="46a34-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="46a34-444">(Diese Eigenschaft muss mit beginnen  `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="46a34-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="46a34-445">Dieses Format ähnelt dem für die  `IPM.NOTE.X` Nachrichtenklasse.) Diese Eigenschaft enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="46a34-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="46a34-446">`Source`: Gibt die Datenquelle eines Drittanbieters an; zum Beispiel Twitter, Facebook oder BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="46a34-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="46a34-447">`Event`: Gibt die Art der Aktivität an, die in der Drittanbieter-Datenquelle ausgeführt wurde, die die Elemente erstellt hat; zum Beispiel ein tweet in Twitter oder ein Beitrag in Facebook.</span><span class="sxs-lookup"><span data-stu-id="46a34-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="46a34-448">Ereignisse sind für die jeweilige Datenquelle spezifisch.</span><span class="sxs-lookup"><span data-stu-id="46a34-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="46a34-449">Ein Zweck dieser Eigenschaft ist es zum Beispiel, bestimmte Elemente basierend auf der Datenquelle zu filtern, aus der ein Element stammt, oder basierend auf dem Typ des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="46a34-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="46a34-450">So könnten Sie in einer eDiscovery-Suche zum Beispiel eine Suchabfrage erstellen, um alle Tweets zu finden, die von einem bestimmten Benutzer gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="46a34-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="46a34-451">Wenn Elemente erfolgreich in Postfächer in Microsoft 365 importiert werden, wird ein eindeutiger Bezeichner als Teil der HTTP-Antwort zurück an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="46a34-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="46a34-452">Dieser Bezeichner,  `x-IngestionCorrelationID` der aufgerufen wird, kann für nachfolgende Problembehandlungszwecke von Partnern zur End-to-End-Überwachung von Elementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46a34-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="46a34-453">Es wird empfohlen, dass Partner diese Informationen entsprechend erfassen und sammeln.</span><span class="sxs-lookup"><span data-stu-id="46a34-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="46a34-454">Im Folgenden ist ein Beispiel einer HTTP-Antwort mit diesem Bezeichner aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="46a34-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="46a34-455">Sie können das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um nach Elementen zu suchen, die von einer Drittanbieter-Datenquelle in Postfächer importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="46a34-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="46a34-456">Um gezielt nach diesen importierten Elementen zu suchen, können Sie die folgenden Nachrichten Eigenschaftswert-Paare im Feld Stichwort für eine Inhaltssuche verwenden.</span><span class="sxs-lookup"><span data-stu-id="46a34-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="46a34-457">**`kind:externaldata`**: Verwenden Sie dieses Eigenschaftswert-Paar, um alle Drittanbieter-Datentypen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="46a34-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="46a34-458">Um beispielsweise nach Elementen zu suchen, die aus einer Drittanbieter-Datenquelle importiert wurden und das Wort "Contoso" in der Subject-Eigenschaft des importierten Elements enthielten, würden Sie die Stichwortabfrage verwenden  `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="46a34-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="46a34-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Verwenden Sie dieses Eigenschaftswert-Paar, um nur einen Typ von drittanbieterdaten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="46a34-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="46a34-460">Wenn Sie beispielsweise nur Facebook-Daten durchsuchen möchten, die das Wort "Contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die Stichwort-Abfrage  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="46a34-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="46a34-461">Eine vollständige Liste der Werte, die für Drittanbieter-Datentypen für die Eigenschaft verwendet werden sollen  `itemclass` , finden Sie unter [Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die in Microsoft 365 importiert wurden](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="46a34-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="46a34-462">Weitere Informationen zur Verwendung der Inhaltssuche und zum Erstellen von Stichwortsuchabfragen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="46a34-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="46a34-463">Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="46a34-463">Content Search</span></span>](content-search.md)
    
  - [<span data-ttu-id="46a34-464">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="46a34-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
