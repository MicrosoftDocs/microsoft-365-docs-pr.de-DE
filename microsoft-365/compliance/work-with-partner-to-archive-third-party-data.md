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
ms.openlocfilehash: c3b824909ae1243e2dd1f12b799e53d00d9615ca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126654"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="ee563-103">Zusammenarbeit mit einem Partner zum Archivieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="ee563-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="ee563-104">Sie können mit einem Microsoft-Partner zusammenarbeiten, um Daten aus einer Drittanbieter-Datenquelle in Microsoft 365 zu importieren und zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="ee563-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="ee563-105">Ein Partner kann Ihnen einen benutzerdefinierten Connector zur Verfügung stellen, der so konfiguriert ist, dass er Elemente aus der Drittanbieter-Datenquelle extrahiert (regelmäßig) und diese Elemente dann importiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="ee563-106">Der Partner Connector wandelt den Inhalt eines Elements aus der Datenquelle in ein e-Mail-Nachrichtenformat um und speichert dann die Elemente in Postfächern.</span><span class="sxs-lookup"><span data-stu-id="ee563-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="ee563-107">Nach dem Importieren von drittanbieterdaten können Sie Microsoft 365-Kompatibilitätsfeatures wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf diese Daten anwenden.</span><span class="sxs-lookup"><span data-stu-id="ee563-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
  
<span data-ttu-id="ee563-108">Im folgenden finden Sie eine Übersicht über den Prozess und die erforderlichen Schritte für die Zusammenarbeit mit einem Microsoft-Partner zum Importieren von drittanbieterdaten.</span><span class="sxs-lookup"><span data-stu-id="ee563-108">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="ee563-109">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="ee563-109">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="ee563-110">Schritt 2: Erstellen und Konfigurieren eines Drittanbieter-Daten Postfachs</span><span class="sxs-lookup"><span data-stu-id="ee563-110">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="ee563-111">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="ee563-111">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="ee563-112">Schritt 4: Bereitstellen von Informationen für Ihren Partner</span><span class="sxs-lookup"><span data-stu-id="ee563-112">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="ee563-113">Schritt 5: Registrieren des drittanbieterdaten-Konnektors in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ee563-113">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="ee563-114">So funktioniert der Prozess zum Importieren von Drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="ee563-114">How the third-party data import process works</span></span>

<span data-ttu-id="ee563-115">In der folgenden Abbildung und Beschreibung wird erläutert, wie der Datenimportvorgang eines Drittanbieters bei der Arbeit mit einem Partner funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ee563-115">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![So funktioniert der Prozess zum Importieren von Drittanbieterdaten](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="ee563-117">Der Kunde arbeitet mit seinem Partner an der Wahl, um einen Connector zu konfigurieren, der Elemente aus der Drittanbieter-Datenquelle extrahiert und diese Elemente dann nach Microsoft 365 importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee563-117">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="ee563-118">Der Partner Connector stellt über eine API eines Drittanbieters (auf geplanter oder konfigurierter Basis) eine Verbindung mit Drittanbieter-Datenquellen her und extrahiert Elemente aus der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ee563-118">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="ee563-119">Der Partnerconnector konvertiert den Inhalt eines Elements in ein E-Mail-Format.</span><span class="sxs-lookup"><span data-stu-id="ee563-119">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="ee563-120">Eine Beschreibung des Nachrichtenformat Schemas finden Sie im Abschnitt [Weitere Informationen](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="ee563-120">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="ee563-121">Partner Connector stellt über einen bekannten Endpunkt eine Verbindung mit dem Azure-Dienst in Microsoft 365 mithilfe des Exchange-Webdiensts (EWS) her.</span><span class="sxs-lookup"><span data-stu-id="ee563-121">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="ee563-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span><span class="sxs-lookup"><span data-stu-id="ee563-122">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox.</span></span> <span data-ttu-id="ee563-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span><span class="sxs-lookup"><span data-stu-id="ee563-123">Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="ee563-124">**Elemente mit einer Benutzer-ID, die einem Benutzerkonto entspricht:** Wenn der Partner Connector die Benutzer-ID des Elements in der Drittanbieter-Datenquelle einer bestimmten Benutzer-ID in Office 365 zuordnen kann, wird das Element im Ordner "refundable Items" des Benutzers in den Ordner " **Säuberungen** " kopiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-124">**Items that have a user ID that corresponds to an user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="ee563-125">Benutzer können nicht auf Elemente im Ordner „Endgültige Löschvorgänge“ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ee563-125">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="ee563-126">Sie können jedoch eDiscovery-Tools verwenden, um nach Elementen im Ordner "Säuberungen" zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ee563-126">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="ee563-127">**Elemente, die nicht über eine Benutzer-ID verfügen, die einem Benutzerkonto entspricht:** Wenn der Partner Connector die Benutzer-ID eines Elements nicht einer bestimmten Benutzer-ID zuordnen kann, wird das Element in den Ordner **Posteingangs** Verzeichnis des Drittanbieter-Daten Postfachs kopiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-127">**Items that don't have a user ID that corresponds to an user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="ee563-128">Das Importieren von Elementen in den Posteingang ermöglicht Ihnen oder einem anderen Benutzer in Ihrer Organisation, sich beim Drittanbieter-Postfach anzumelden und diese Elemente zu verwalten und zu sehen, ob Anpassungen an der Partnerconnectorkonfiguration vorgenommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ee563-128">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="ee563-129">Schritt 1: Partner für Drittanbieterdaten suchen</span><span class="sxs-lookup"><span data-stu-id="ee563-129">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="ee563-130">Eine wichtige Komponente zum Archivieren von drittanbieterdaten in Microsoft 365 besteht darin, einen Microsoft-Partner zu finden und zu verwenden, der sich auf das Erfassen von Daten aus einer Drittanbieter-Datenquelle und das Importieren in Office 365 spezialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="ee563-130">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="ee563-131">Nachdem die Daten importiert wurden, können Sie zusammen mit anderen Microsoft-Daten Ihrer Organisation wie e-Mails von Exchange und Dokumenten aus SharePoint und OneDrive für Unternehmen archiviert und aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-131">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="ee563-132">Ein Partner erstellt einen Konnektor, der Daten aus den drittanbieterdaten Quellen Ihrer Organisation extrahiert (wie BlackBerry, Facebook, Google +, Thomson Reuters, Twitter und YouTube) und übergibt diese Daten an eine Office 365-API, die Elemente als e-Mail-Nachrichten in Exchange-Postfächer importiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-132">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="ee563-133">In den folgenden Abschnitten werden die Microsoft-Partner (und die von Ihnen unterstützten Drittanbieter-Datenquellen) aufgeführt, die am Programm zum Archivieren von drittanbieterdaten in Office 365 teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="ee563-133">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="ee563-134">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="ee563-134">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="ee563-135">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="ee563-135">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="ee563-136">Globanet</span><span class="sxs-lookup"><span data-stu-id="ee563-136">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="ee563-137">OpenText</span><span class="sxs-lookup"><span data-stu-id="ee563-137">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="ee563-138">Smarsh</span><span class="sxs-lookup"><span data-stu-id="ee563-138">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="ee563-139">Verba</span><span class="sxs-lookup"><span data-stu-id="ee563-139">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="ee563-140">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="ee563-140">17a-4 LLC</span></span>

<span data-ttu-id="ee563-141">die [17a-4 LLC](https://www.17a-4.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="ee563-141">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="ee563-142">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="ee563-142">BlackBerry</span></span>
    
- <span data-ttu-id="ee563-143">Bloomberg Data Streams</span><span class="sxs-lookup"><span data-stu-id="ee563-143">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="ee563-144">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="ee563-144">Cisco Jabber</span></span>
    
- <span data-ttu-id="ee563-145">FactSet</span><span class="sxs-lookup"><span data-stu-id="ee563-145">FactSet</span></span>
    
- <span data-ttu-id="ee563-146">HipChat</span><span class="sxs-lookup"><span data-stu-id="ee563-146">HipChat</span></span>
    
- <span data-ttu-id="ee563-147">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="ee563-147">InvestEdge</span></span>
    
- <span data-ttu-id="ee563-148">Schwätzchen</span><span class="sxs-lookup"><span data-stu-id="ee563-148">LivePerson</span></span>
    
- <span data-ttu-id="ee563-149">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="ee563-149">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="ee563-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="ee563-150">OpenText</span></span>
    
- <span data-ttu-id="ee563-151">Live-Hilfe für Oracle/ATG 'click-to-call'</span><span class="sxs-lookup"><span data-stu-id="ee563-151">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="ee563-152">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="ee563-152">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="ee563-153">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="ee563-153">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="ee563-154">MindAlign</span><span class="sxs-lookup"><span data-stu-id="ee563-154">MindAlign</span></span>
    
- <span data-ttu-id="ee563-155">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="ee563-155">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="ee563-156">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="ee563-156">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="ee563-157">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="ee563-157">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="ee563-158">SQL-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="ee563-158">SQL Databases</span></span>
    
- <span data-ttu-id="ee563-159">Squawker</span><span class="sxs-lookup"><span data-stu-id="ee563-159">Squawker</span></span>
    
- <span data-ttu-id="ee563-160">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="ee563-160">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="ee563-161">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="ee563-161">ArchiveSocial</span></span>

<span data-ttu-id="ee563-162">[ArchiveSocial](https://www.archivesocial.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="ee563-162">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ee563-163">Facebook</span><span class="sxs-lookup"><span data-stu-id="ee563-163">Facebook</span></span>
    
- <span data-ttu-id="ee563-164">Flickr</span><span class="sxs-lookup"><span data-stu-id="ee563-164">Flickr</span></span>
    
- <span data-ttu-id="ee563-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="ee563-165">Instagram</span></span>
    
- <span data-ttu-id="ee563-166">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ee563-166">LinkedIn</span></span>
    
- <span data-ttu-id="ee563-167">Pinterest</span><span class="sxs-lookup"><span data-stu-id="ee563-167">Pinterest</span></span>
    
- <span data-ttu-id="ee563-168">Twitter</span><span class="sxs-lookup"><span data-stu-id="ee563-168">Twitter</span></span>
    
- <span data-ttu-id="ee563-169">YouTube</span><span class="sxs-lookup"><span data-stu-id="ee563-169">YouTube</span></span>
    
- <span data-ttu-id="ee563-170">Vimeo</span><span class="sxs-lookup"><span data-stu-id="ee563-170">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="ee563-171">Globanet</span><span class="sxs-lookup"><span data-stu-id="ee563-171">Globanet</span></span>

<span data-ttu-id="ee563-172">[Globanet](https://www.globanet.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="ee563-172">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ee563-173">AOL mit Pivot-Client
</span><span class="sxs-lookup"><span data-stu-id="ee563-173">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="ee563-174">BlackBerry-Anrufprotokolle (v5, v10, v12)
</span><span class="sxs-lookup"><span data-stu-id="ee563-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-175">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-176">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-177">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-178">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="ee563-178">Bloomberg Chat</span></span>
    
- <span data-ttu-id="ee563-179">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="ee563-179">Bloomberg Mail</span></span>
    
- <span data-ttu-id="ee563-180">Box</span><span class="sxs-lookup"><span data-stu-id="ee563-180">Box</span></span>
    
- <span data-ttu-id="ee563-181">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="ee563-181">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="ee563-182">Cisco Chat &amp; Presence Server (v10, v 10.5.1 SU1, v 11.0, v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="ee563-182">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="ee563-183">Cisco WebEx-Teams</span><span class="sxs-lookup"><span data-stu-id="ee563-183">Cisco Webex Teams</span></span>

- <span data-ttu-id="ee563-184">Citrix-Arbeitsbereichs &amp; Freigabe</span><span class="sxs-lookup"><span data-stu-id="ee563-184">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="ee563-185">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="ee563-185">CrowdCompass</span></span>

- <span data-ttu-id="ee563-186">Benutzerdefinierte Textdateien mit Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="ee563-186">Custom-delimited text files</span></span>
    
- <span data-ttu-id="ee563-187">Benutzerdefinierte XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="ee563-187">Custom XML files</span></span>
    
- <span data-ttu-id="ee563-188">Facebook (Seiten)</span><span class="sxs-lookup"><span data-stu-id="ee563-188">Facebook (Pages)</span></span>
    
- <span data-ttu-id="ee563-189">FactSet</span><span class="sxs-lookup"><span data-stu-id="ee563-189">Factset</span></span>
    
- <span data-ttu-id="ee563-190">FXConnect</span><span class="sxs-lookup"><span data-stu-id="ee563-190">FXConnect</span></span>
    
- <span data-ttu-id="ee563-191">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="ee563-191">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="ee563-192">Jive</span><span class="sxs-lookup"><span data-stu-id="ee563-192">Jive</span></span>
    
- <span data-ttu-id="ee563-193">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="ee563-193">Macgregor XIP</span></span>

- <span data-ttu-id="ee563-194">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ee563-194">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="ee563-195">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ee563-195">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="ee563-196">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee563-196">Microsoft Teams</span></span>
       
- <span data-ttu-id="ee563-197">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="ee563-197">Microsoft Yammer</span></span>
    
- <span data-ttu-id="ee563-198">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="ee563-198">Mobile Guard</span></span>
    
- <span data-ttu-id="ee563-199">Pivot</span><span class="sxs-lookup"><span data-stu-id="ee563-199">Pivot</span></span>
    
- <span data-ttu-id="ee563-200">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="ee563-200">Salesforce Chatter</span></span>

- <span data-ttu-id="ee563-201">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee563-201">Skype for Business Online</span></span>
    
- <span data-ttu-id="ee563-202">Skype for Business, Versionen 2007 R2 - 2016 (lokal)</span><span class="sxs-lookup"><span data-stu-id="ee563-202">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="ee563-203">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="ee563-203">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="ee563-204">Symphonie</span><span class="sxs-lookup"><span data-stu-id="ee563-204">Symphony</span></span>
    
- <span data-ttu-id="ee563-205">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="ee563-205">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="ee563-206">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="ee563-206">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="ee563-207">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="ee563-207">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="ee563-208">Twitter</span><span class="sxs-lookup"><span data-stu-id="ee563-208">Twitter</span></span>
    
- <span data-ttu-id="ee563-209">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="ee563-209">UBS Chat</span></span>
    
- <span data-ttu-id="ee563-210">YouTube</span><span class="sxs-lookup"><span data-stu-id="ee563-210">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="ee563-211">OpenText</span><span class="sxs-lookup"><span data-stu-id="ee563-211">OpenText</span></span>

<span data-ttu-id="ee563-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="ee563-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ee563-213">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="ee563-213">Axs Encrypted</span></span>
    
- <span data-ttu-id="ee563-214">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="ee563-214">Axs Exchange</span></span>
    
- <span data-ttu-id="ee563-215">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="ee563-215">Axs Local Archive</span></span>
    
- <span data-ttu-id="ee563-216">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="ee563-216">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="ee563-217">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="ee563-217">Axs Signed</span></span>
    
- <span data-ttu-id="ee563-218">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ee563-218">Bloomberg</span></span>
    
- <span data-ttu-id="ee563-219">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="ee563-219">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="ee563-220">Smarsh</span><span class="sxs-lookup"><span data-stu-id="ee563-220">Smarsh</span></span>

<span data-ttu-id="ee563-221">[Smarsh](https://www.smarsh.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="ee563-221">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ee563-222">Versuchen</span><span class="sxs-lookup"><span data-stu-id="ee563-222">AIM</span></span>
    
- <span data-ttu-id="ee563-223">American Idol</span><span class="sxs-lookup"><span data-stu-id="ee563-223">American Idol</span></span>
    
- <span data-ttu-id="ee563-224">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="ee563-224">Apple Juice</span></span>
    
- <span data-ttu-id="ee563-225">AOL mit Pivot-Client</span><span class="sxs-lookup"><span data-stu-id="ee563-225">AOL with Pivot client</span></span>
    
- <span data-ttu-id="ee563-226">Ares</span><span class="sxs-lookup"><span data-stu-id="ee563-226">Ares</span></span>
    
- <span data-ttu-id="ee563-227">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-227">Bazaar Voice</span></span>
    
- <span data-ttu-id="ee563-228">Bear Share</span><span class="sxs-lookup"><span data-stu-id="ee563-228">Bear Share</span></span>
    
- <span data-ttu-id="ee563-229">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="ee563-229">Bit Torrent</span></span>
    
- <span data-ttu-id="ee563-230">BlackBerry-Anrufprotokolle (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-230">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-231">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-231">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-232">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-232">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-233">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="ee563-233">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="ee563-234">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="ee563-234">Bloomberg Mail</span></span>
    
- <span data-ttu-id="ee563-235">CellTrust</span><span class="sxs-lookup"><span data-stu-id="ee563-235">CellTrust</span></span>
    
- <span data-ttu-id="ee563-236">Chat Import</span><span class="sxs-lookup"><span data-stu-id="ee563-236">Chat Import</span></span>
    
- <span data-ttu-id="ee563-237">Echtzeitprotokollierung und -richtinie für Chat</span><span class="sxs-lookup"><span data-stu-id="ee563-237">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="ee563-238">Störgeräusche</span><span class="sxs-lookup"><span data-stu-id="ee563-238">Chatter</span></span>
    
- <span data-ttu-id="ee563-239">Cisco Chat &amp; Presence Server (v 9.0.1, v 9.1, v 9.1.1 SU1, V10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="ee563-239">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="ee563-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="ee563-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="ee563-241">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="ee563-241">Collaboration Import</span></span>
    
- <span data-ttu-id="ee563-242">Echtzeitprotokollierung für Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="ee563-242">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="ee563-243">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="ee563-243">Direct Connect</span></span>
    
- <span data-ttu-id="ee563-244">Facebook</span><span class="sxs-lookup"><span data-stu-id="ee563-244">Facebook</span></span>
    
- <span data-ttu-id="ee563-245">FactSet</span><span class="sxs-lookup"><span data-stu-id="ee563-245">FactSet</span></span>
    
- <span data-ttu-id="ee563-246">FastTrack</span><span class="sxs-lookup"><span data-stu-id="ee563-246">FastTrack</span></span>
    
- <span data-ttu-id="ee563-247">Gnutella</span><span class="sxs-lookup"><span data-stu-id="ee563-247">Gnutella</span></span>
    
- <span data-ttu-id="ee563-248">Google +</span><span class="sxs-lookup"><span data-stu-id="ee563-248">Google+</span></span>
    
- <span data-ttu-id="ee563-249">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="ee563-249">GoToMyPC</span></span>
    
- <span data-ttu-id="ee563-250">Hopster</span><span class="sxs-lookup"><span data-stu-id="ee563-250">Hopster</span></span>
    
- <span data-ttu-id="ee563-251">HubConnex</span><span class="sxs-lookup"><span data-stu-id="ee563-251">HubConnex</span></span>
    
- <span data-ttu-id="ee563-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="ee563-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="ee563-253">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="ee563-253">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="ee563-254">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="ee563-254">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="ee563-255">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="ee563-255">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="ee563-256">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="ee563-256">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="ee563-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="ee563-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="ee563-258">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="ee563-258">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="ee563-259">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="ee563-259">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="ee563-260">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="ee563-260">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="ee563-261">Ice/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="ee563-261">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="ee563-262">Chat-Import</span><span class="sxs-lookup"><span data-stu-id="ee563-262">IM Import</span></span>
    
- <span data-ttu-id="ee563-263">Echtzeitprotokollierung und -richtinie für Chat</span><span class="sxs-lookup"><span data-stu-id="ee563-263">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="ee563-264">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="ee563-264">Indii Messenger</span></span>
    
- <span data-ttu-id="ee563-265">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="ee563-265">Instant Bloomberg</span></span>
    
- <span data-ttu-id="ee563-266">IRC</span><span class="sxs-lookup"><span data-stu-id="ee563-266">IRC</span></span>
    
- <span data-ttu-id="ee563-267">Jive</span><span class="sxs-lookup"><span data-stu-id="ee563-267">Jive</span></span>
    
- <span data-ttu-id="ee563-268">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="ee563-268">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="ee563-269">Jive Import</span><span class="sxs-lookup"><span data-stu-id="ee563-269">Jive Import</span></span>
    
- <span data-ttu-id="ee563-270">JXTA</span><span class="sxs-lookup"><span data-stu-id="ee563-270">JXTA</span></span>
    
- <span data-ttu-id="ee563-271">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="ee563-271">LinkedIn</span></span>
    
- <span data-ttu-id="ee563-272">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="ee563-272">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="ee563-273">MFTP</span><span class="sxs-lookup"><span data-stu-id="ee563-273">MFTP</span></span>
    
- <span data-ttu-id="ee563-274">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-274">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="ee563-275">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="ee563-275">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="ee563-276">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ee563-276">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="ee563-277">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="ee563-277">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="ee563-278">MindAlign</span><span class="sxs-lookup"><span data-stu-id="ee563-278">MindAlign</span></span>
    
- <span data-ttu-id="ee563-279">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="ee563-279">Mobile Guard</span></span>
    
- <span data-ttu-id="ee563-280">MSN</span><span class="sxs-lookup"><span data-stu-id="ee563-280">MSN</span></span>
    
- <span data-ttu-id="ee563-281">My Space</span><span class="sxs-lookup"><span data-stu-id="ee563-281">My Space</span></span>
    
- <span data-ttu-id="ee563-282">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="ee563-282">NEONetwork</span></span>
    
- <span data-ttu-id="ee563-283">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="ee563-283">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="ee563-284">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="ee563-284">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="ee563-285">Pinterest</span><span class="sxs-lookup"><span data-stu-id="ee563-285">Pinterest</span></span>
    
- <span data-ttu-id="ee563-286">Pivot</span><span class="sxs-lookup"><span data-stu-id="ee563-286">Pivot</span></span>
    
- <span data-ttu-id="ee563-287">QQ</span><span class="sxs-lookup"><span data-stu-id="ee563-287">QQ</span></span>
    
- <span data-ttu-id="ee563-288">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="ee563-288">Skype for Business 2015</span></span>
    
- <span data-ttu-id="ee563-289">SoftEther</span><span class="sxs-lookup"><span data-stu-id="ee563-289">SoftEther</span></span>
    
- <span data-ttu-id="ee563-290">Symphonie</span><span class="sxs-lookup"><span data-stu-id="ee563-290">Symphony</span></span>
    
- <span data-ttu-id="ee563-291">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="ee563-291">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="ee563-292">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="ee563-292">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="ee563-293">Tor</span><span class="sxs-lookup"><span data-stu-id="ee563-293">Tor</span></span>
    
- <span data-ttu-id="ee563-294">TTT</span><span class="sxs-lookup"><span data-stu-id="ee563-294">TTT</span></span>
    
- <span data-ttu-id="ee563-295">Twitter</span><span class="sxs-lookup"><span data-stu-id="ee563-295">Twitter</span></span>
    
- <span data-ttu-id="ee563-296">WinMX</span><span class="sxs-lookup"><span data-stu-id="ee563-296">WinMX</span></span>
    
- <span data-ttu-id="ee563-297">Winny</span><span class="sxs-lookup"><span data-stu-id="ee563-297">Winny</span></span>
    
- <span data-ttu-id="ee563-298">Yahoo</span><span class="sxs-lookup"><span data-stu-id="ee563-298">Yahoo</span></span>
    
- <span data-ttu-id="ee563-299">Yammer</span><span class="sxs-lookup"><span data-stu-id="ee563-299">Yammer</span></span>
    
- <span data-ttu-id="ee563-300">YouTube</span><span class="sxs-lookup"><span data-stu-id="ee563-300">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="ee563-301">Verba</span><span class="sxs-lookup"><span data-stu-id="ee563-301">Verba</span></span>

<span data-ttu-id="ee563-302">[Verba](https://www.verba.com) unterstützt die folgenden Drittanbieter-Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="ee563-302">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="ee563-303">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="ee563-303">Avaya Aura Video</span></span>
    
- <span data-ttu-id="ee563-304">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-304">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="ee563-305">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="ee563-305">Avtec Radio</span></span>
    
- <span data-ttu-id="ee563-306">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="ee563-306">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="ee563-307">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="ee563-307">BroadSoft Video</span></span>
    
- <span data-ttu-id="ee563-308">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-308">BroadSoft Voice</span></span>
    
- <span data-ttu-id="ee563-309">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-309">Centile Voice</span></span>
    
- <span data-ttu-id="ee563-310">Chatnachricht in Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="ee563-310">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="ee563-311">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="ee563-311">Cisco UC Video</span></span>
    
- <span data-ttu-id="ee563-312">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-312">Cisco UC Voice</span></span>
    
- <span data-ttu-id="ee563-313">Cisco UCCX/UCCE-Video</span><span class="sxs-lookup"><span data-stu-id="ee563-313">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="ee563-314">Cisco UCCX/UCCE-VoIP</span><span class="sxs-lookup"><span data-stu-id="ee563-314">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="ee563-315">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="ee563-315">ESChat Radio</span></span>
    
- <span data-ttu-id="ee563-316">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="ee563-316">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="ee563-317">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-317">IP Trade Voice</span></span>
    
- <span data-ttu-id="ee563-318">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="ee563-318">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="ee563-319">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="ee563-319">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="ee563-320">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="ee563-320">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="ee563-321">Oracle/Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="ee563-321">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="ee563-322">Oracle/Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-322">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="ee563-323">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-323">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="ee563-324">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="ee563-324">SIPREC Video</span></span>
    
-  <span data-ttu-id="ee563-325">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-325">SIPREC Voice</span></span> 
    
- <span data-ttu-id="ee563-326">Chatnachricht in Skype for Business/Lync</span><span class="sxs-lookup"><span data-stu-id="ee563-326">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="ee563-327">Skype for Business/Lync Video</span><span class="sxs-lookup"><span data-stu-id="ee563-327">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="ee563-328">Skype for Business/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-328">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="ee563-329">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-329">Speakerbus Voice</span></span>
    
- <span data-ttu-id="ee563-330">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="ee563-330">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="ee563-331">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-331">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="ee563-332">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="ee563-332">Truphone Voice</span></span>
    
- <span data-ttu-id="ee563-333">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="ee563-333">TwistedPair Radio</span></span>
    
- <span data-ttu-id="ee563-334">Windows Desktop-Computerbildschirm</span><span class="sxs-lookup"><span data-stu-id="ee563-334">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="ee563-335">Schritt 2: Drittanbieter-Postfach in Office 365 erstellen und konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ee563-335">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="ee563-336">Hier finden Sie die Schritte zum Erstellen und Konfigurieren eines Drittanbieter-Daten Postfachs zum Importieren von Daten in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee563-336">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="ee563-337">Wie bereits erläutert, werden Elemente in dieses Postfach importiert, wenn der Partner Connector die Benutzer-ID des Elements keinem Benutzerkonto zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="ee563-337">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an user account.</span></span>
  
 <span data-ttu-id="ee563-338">**Führen Sie diese Aufgaben im Microsoft 365 Admin Center aus.**</span><span class="sxs-lookup"><span data-stu-id="ee563-338">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="ee563-339">Erstellen Sie ein Benutzerkonto, und weisen Sie ihm eine Lizenz für Exchange Online Plan 2 zu. Weitere Informationen finden Sie unter [Hinzufügen von Benutzern zu Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="ee563-339">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="ee563-340">Eine Plan 2-Lizenz ist erforderlich, um das Postfach in einem Beweissicherungsverfahren aufzubewahren oder ein Archivpostfach mit einem unbegrenzten Speicherkontingent zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ee563-340">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="ee563-341">Fügen Sie das Benutzerkonto für das Drittanbieter-Daten Postfach der **Administratorrolle Exchange-Administrator** in Office 365 hinzu. Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="ee563-341">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ee563-342">Notieren Sie die Anmeldeinformationen für dieses Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="ee563-342">Write down the credentials for this user account.</span></span> <span data-ttu-id="ee563-343">Sie müssen diese für Ihren Partner bereitstellen, wie in Schritt 4 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ee563-343">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="ee563-344">**Führen Sie diese Aufgaben im Exchange Admin Center aus.**</span><span class="sxs-lookup"><span data-stu-id="ee563-344">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="ee563-345">Ausblenden des Drittanbieter-Daten Postfachs aus dem Adressbuch und anderen Adresslisten in Ihrer Organisation; Weitere Informationen finden Sie unter [Verwalten von Benutzerpostfächern](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="ee563-345">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="ee563-346">Alternativ können Sie den folgenden PowerShell-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ee563-346">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="ee563-347">Weisen Sie dem Drittanbieter-Daten Postfach die Berechtigung **FullAccess** zu, damit Administratoren oder Compliance Officer das Drittanbieter-Daten Postfach im Outlook-Desktop Client öffnen können. Weitere Informationen finden Sie unter [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="ee563-347">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="ee563-348">Aktivieren Sie die folgenden kompatibilitätsbezogenen Funktionen für das Drittanbieter-Daten Postfach:</span><span class="sxs-lookup"><span data-stu-id="ee563-348">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="ee563-349">Aktivieren des Archivpostfachs siehe [Aktivieren von archivpostfächern](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ee563-349">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="ee563-350">Auf diese Weise können Sie Speicherplatz im primären Postfach freigeben, indem Sie eine Archivrichtlinie einrichten, mit der Datenelemente von Drittanbietern in das Archivpostfach verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-350">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="ee563-351">Dadurch erhalten Sie unbegrenzten Speicher für drittanbieterdaten.</span><span class="sxs-lookup"><span data-stu-id="ee563-351">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="ee563-352">Aktivieren Sie für das Drittanbieterdaten-Postfach das Beweissicherungsverfahren.</span><span class="sxs-lookup"><span data-stu-id="ee563-352">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="ee563-353">Sie können auch eine Microsoft 365-Aufbewahrungsrichtlinie im Security and Compliance Center anwenden.</span><span class="sxs-lookup"><span data-stu-id="ee563-353">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="ee563-354">Beim Platzieren dieses Postfachs bleiben Datenelemente von Drittanbietern (auf unbestimmte Zeit oder für eine bestimmte Dauer) erhalten und verhindern, dass Sie aus dem Postfach gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-354">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="ee563-355">Lesen Sie eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ee563-355">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="ee563-356">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="ee563-356">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="ee563-357">Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ee563-357">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="ee563-358">Aktivieren der postfachüberwachungsprotokollierung für den Besitzer-, Stellvertreter-und Administratorzugriff auf das Daten Postfach eines Drittanbieters; siehe [Aktivieren der postfachüberwachung](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="ee563-358">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="ee563-359">Auf diese Weise können Sie alle von Benutzern ausgeführten Aktivitäten überwachen, die Zugriff auf das Daten Postfach eines Drittanbieters haben.</span><span class="sxs-lookup"><span data-stu-id="ee563-359">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="ee563-360">Schritt 3: Benutzerpostfächer für Drittanbieterdaten konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ee563-360">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="ee563-361">Als Nächstes müssen Sie die Benutzerpostfächer für die Unterstützung von Drittanbieterdaten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ee563-361">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="ee563-362">Führen Sie diese Aufgaben mithilfe der Exchange-Verwaltungskonsole oder mithilfe der entsprechenden Windows PowerShell-Cmdlets aus.</span><span class="sxs-lookup"><span data-stu-id="ee563-362">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="ee563-363">Aktivieren Sie das Archivpostfach für jeden Benutzer. siehe [Aktivieren von archivpostfächern](enable-archive-mailboxes.md) und [Aktivieren der unbegrenzten Archivierung](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="ee563-363">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="ee563-364">Platzieren von Benutzerpostfächern für das Beweissicherungsverfahren oder Anwenden einer Microsoft 365-Aufbewahrungsrichtlinie Lesen Sie eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ee563-364">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="ee563-365">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="ee563-365">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="ee563-366">Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ee563-366">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="ee563-367">Wie bereits weiter oben erwähnt, können Sie beim Aktivieren des Beweissicherungsverfahrens für Postfächer festlegen, wie lange Elemente aus einer Drittanbieter-Datenquelle aufbewahrt werden sollen. Sie können auch festlegen, dass sie dauerhaft aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ee563-367">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="ee563-368">Schritt 4: Bereitstellen von Informationen für Ihren Partner</span><span class="sxs-lookup"><span data-stu-id="ee563-368">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="ee563-369">Der letzte Schritt besteht darin, dem Partner die folgenden Informationen bereitzustellen, damit er den Connector für die Verbindung mit Ihrer Organisation konfigurieren kann, um Daten in Benutzerpostfächer und das Drittanbieter-Daten Postfach zu importieren.</span><span class="sxs-lookup"><span data-stu-id="ee563-369">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="ee563-370">Der Endpunkt, der zum Herstellen einer Verbindung mit dem Azure-Dienst in Office 365 verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="ee563-370">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="ee563-371">Die Anmeldeinformationen (Benutzer-ID und Kennwort von Microsoft 365) des Drittanbieter-Daten Postfachs, das Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ee563-371">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="ee563-372">Diese Anmeldeinformationen sind erforderlich, damit der Partnerconnector auf Elemente zugreifen und sie in das Drittanbieterdaten-Postfach importieren kann.</span><span class="sxs-lookup"><span data-stu-id="ee563-372">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="ee563-373">Schritt 5: Registrieren des drittanbieterdaten-Konnektors in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ee563-373">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="ee563-374">Ab dem 30. September 2018 wird der Azure-Dienst in Office 365 zunächst die moderne Authentifizierung in Exchange Online verwenden, um Daten Konnektoren von Drittanbietern zu authentifizieren, die versuchen, eine Verbindung mit Ihrer Organisation herzustellen, um Daten zu importieren.</span><span class="sxs-lookup"><span data-stu-id="ee563-374">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="ee563-375">Der Grund für diese Änderung besteht darin, dass die moderne Authentifizierung mehr Sicherheit bietet als die aktuelle Methode, die auf einer Zulassungsliste für Connectors von Drittanbietern basiert, die den zuvor beschriebenen Endpunkt zum Herstellen einer Verbindung mit dem Azure-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee563-375">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="ee563-376">Damit ein Drittanbieter-Daten Konnektor mithilfe der neuen modernen Authentifizierungsmethode eine Verbindung mit Office 365 herstellen kann, muss ein Administrator in Ihrer Organisation zustimmen, dass der Connector als vertrauenswürdige Dienstanwendung in Azure Active Directory registriert wird.</span><span class="sxs-lookup"><span data-stu-id="ee563-376">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="ee563-377">Dies erfolgt durch Annahme einer Berechtigungsanforderung, damit der Connector auf die Daten Ihrer Organisation in Azure Active Directory zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ee563-377">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="ee563-378">Nachdem Sie diese Anforderung angenommen haben, wird der Drittanbieter-Daten Konnektor als Unternehmensanwendung zu Azure Active Directory hinzugefügt und als Dienstprinzipal dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ee563-378">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="ee563-379">Weitere Informationen zum Zustimmungsprozess finden Sie unter [Mandanten-admin-Zustimmung](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="ee563-379">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="ee563-380">Hier sind die Schritte zum Zugreifen auf und akzeptieren der Anforderung zum Registrieren des Connectors:</span><span class="sxs-lookup"><span data-stu-id="ee563-380">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="ee563-381">Wechseln Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) , und melden Sie sich mit den Anmeldeinformationen eines globalen Administrators an.</span><span class="sxs-lookup"><span data-stu-id="ee563-381">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="ee563-382">Das folgende Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee563-382">The following dialog box is displayed.</span></span> <span data-ttu-id="ee563-383">Sie können die Carets erweitern, um die Berechtigungen zu überprüfen, die dem Connector zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-383">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![Das Dialogfeld Berechtigungsanforderung wird angezeigt.](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="ee563-385">Klicken Sie auf **Annehmen**.</span><span class="sxs-lookup"><span data-stu-id="ee563-385">Click **Accept**.</span></span>

<span data-ttu-id="ee563-386">Nachdem Sie die Anforderung angenommen haben, wird das [Azure-Portal](https://portal.azure.com) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee563-386">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="ee563-387">Um die Liste der Anwendungen für Ihre Organisation anzuzeigen, klicken Sie auf **Azure Active Directory**  >  **Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="ee563-387">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="ee563-388">Der Office 365 Drittanbieter-Daten Connector wird auf dem Blade **Enterprise-Anwendungen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee563-388">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee563-389">Nach dem 30. September 2018 werden drittanbieterdaten nicht mehr in Postfächer in Ihrer Organisation importiert, wenn Sie keinen Daten Konnektor eines Drittanbieters in Azure Active Directory registrieren.</span><span class="sxs-lookup"><span data-stu-id="ee563-389">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="ee563-390">Hinweis vorhandene Drittanbieter-Daten-Konnektoren (die vor dem 30. September 2018 erstellt wurden) müssen ebenfalls in Azure Active Directory registriert werden, indem Sie das Verfahren in Schritt 5 ausführen.</span><span class="sxs-lookup"><span data-stu-id="ee563-390">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="ee563-391">Widerrufen der Zustimmung für einen Daten Konnektor eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="ee563-391">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="ee563-392">Nachdem Ihre Organisation der Berechtigungsanforderung zugestimmt hat, um einen Drittanbieter-Daten Konnektor in Azure Active Directory zu registrieren, kann Ihre Organisation diese Zustimmung jederzeit widerrufen.</span><span class="sxs-lookup"><span data-stu-id="ee563-392">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="ee563-393">Das Widerrufen der Zustimmung für einen Connector bedeutet jedoch, dass Daten aus der Drittanbieter-Datenquelle nicht mehr in Office 365 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-393">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="ee563-394">Um die Zustimmung für einen Drittanbieter-Datenconnector zu widerrufen, können Sie die Anwendung (durch Löschen des entsprechenden Dienst Prinzipals) aus Azure Active Directory mithilfe des Blades **Enterprise-Anwendungen** im Azure-Portal oder mithilfe des [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell löschen.</span><span class="sxs-lookup"><span data-stu-id="ee563-394">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="ee563-395">Sie können auch das Cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee563-395">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="ee563-396">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee563-396">More information</span></span>

- <span data-ttu-id="ee563-397">Wie bereits weiter oben erläutert, werden Elemente aus Drittanbieter-Datenquellen als E-Mail-Nachrichten in Exchange-Postfächer importiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-397">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="ee563-398">Der Partner Connector importiert das Element mithilfe eines Schemas, das für die Office 365-API erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ee563-398">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="ee563-399">Die folgende Tabelle beschreibt die Nachrichteneigenschaften eines Elements aus einer Drittanbieter-Datenquelle, nachdem es als E-Mail-Nachricht in ein Exchange-Postfach importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ee563-399">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="ee563-400">Zudem ist angegeben, wenn die Nachrichteneigenschaft zwingend erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ee563-400">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="ee563-401">Erforderliche Eigenschaften müssen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-401">Mandatory properties must be populated.</span></span> <span data-ttu-id="ee563-402">Wenn ein Element eine obligatorische Eigenschaft fehlt, wird es nicht in Office 365 importiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-402">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="ee563-403">Beim Importvorgang wird eine Fehlermeldung mit der Erläuterung zurückgegeben, warum ein Element nicht importiert wurde und welche Eigenschaft fehlt.</span><span class="sxs-lookup"><span data-stu-id="ee563-403">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="ee563-404">**Nachrichteneigenschaft**</span><span class="sxs-lookup"><span data-stu-id="ee563-404">**Message property**</span></span>|<span data-ttu-id="ee563-405">**Erforderlich?**</span><span class="sxs-lookup"><span data-stu-id="ee563-405">**Mandatory?**</span></span>|<span data-ttu-id="ee563-406">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ee563-406">**Description**</span></span>|<span data-ttu-id="ee563-407">**Beispielwert**</span><span class="sxs-lookup"><span data-stu-id="ee563-407">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ee563-408">**FROM**</span><span class="sxs-lookup"><span data-stu-id="ee563-408">**FROM**</span></span> <br/> |<span data-ttu-id="ee563-409">Ja</span><span class="sxs-lookup"><span data-stu-id="ee563-409">Yes</span></span>  <br/> |<span data-ttu-id="ee563-410">Der Benutzer, der das Element in der Drittanbieter-Datenquelle ursprünglich erstellt oder gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="ee563-410">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="ee563-411">Der Partner Connector versucht, die Benutzer-ID des Quellelements (beispielsweiseeines Twitter-Handles) einem Benutzerkonto für alle Teilnehmer (Benutzer in den Feldern von und bis) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ee563-411">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="ee563-412">Eine Kopie der Nachricht wird in das Postfach jedes Teilnehmers importiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-412">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="ee563-413">Wenn keines der Teilnehmer aus dem Element einem Benutzerkonto zugeordnet werden kann, wird das Element in Office 365 in das Archivierungs Postfach eines Drittanbieters importiert.</span><span class="sxs-lookup"><span data-stu-id="ee563-413">If none of the participants from the item can be mapped to an user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="ee563-414">Der Teilnehmer, der als Absender des Elements identifiziert wird, muss über ein aktives Postfach in der Organisation verfügen, in das das Element importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee563-414">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="ee563-415">Wenn der Absender nicht über ein aktives Postfach verfügt, wird der folgende Fehler zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ee563-415">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="ee563-416">**TO**</span><span class="sxs-lookup"><span data-stu-id="ee563-416">**TO**</span></span> <br/> |<span data-ttu-id="ee563-417">Ja</span><span class="sxs-lookup"><span data-stu-id="ee563-417">Yes</span></span>  <br/> |<span data-ttu-id="ee563-418">Der Benutzer, der ein Element erhalten hat (wenn für ein Element in der Datenquelle zutreffend).</span><span class="sxs-lookup"><span data-stu-id="ee563-418">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="ee563-419">**Betreff**</span><span class="sxs-lookup"><span data-stu-id="ee563-419">**SUBJECT**</span></span> <br/> |<span data-ttu-id="ee563-420">Nein</span><span class="sxs-lookup"><span data-stu-id="ee563-420">No</span></span>  <br/> |<span data-ttu-id="ee563-421">Der Betreff des Quellelements.</span><span class="sxs-lookup"><span data-stu-id="ee563-421">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="ee563-422">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ee563-422">**DATE**</span></span> <br/> |<span data-ttu-id="ee563-423">Ja</span><span class="sxs-lookup"><span data-stu-id="ee563-423">Yes</span></span>  <br/> |<span data-ttu-id="ee563-424">Das Datum, an dem das Element ursprünglich erstellt oder in der Kundendatenquelle veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="ee563-424">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="ee563-425">Beispielsweise dieses Datum, an dem eine Twitter-Nachricht getweetet wurde.</span><span class="sxs-lookup"><span data-stu-id="ee563-425">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="ee563-426">**Text**</span><span class="sxs-lookup"><span data-stu-id="ee563-426">**BODY**</span></span> <br/> |<span data-ttu-id="ee563-427">Nein</span><span class="sxs-lookup"><span data-stu-id="ee563-427">No</span></span>  <br/> |<span data-ttu-id="ee563-428">Der Inhalt der Nachricht oder des Beitrags.</span><span class="sxs-lookup"><span data-stu-id="ee563-428">The contents of the message or post.</span></span> <span data-ttu-id="ee563-429">Bei einigen Datenquellen kann der Inhalt dieser Eigenschaft mit dem Inhalt der Eigenschaft **SUBJECT** identisch sein.</span><span class="sxs-lookup"><span data-stu-id="ee563-429">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="ee563-430">Während des Importvorgangs versucht der Partner Connector, die vollständige Genauigkeit von der Inhaltsquelle wie möglich beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="ee563-430">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="ee563-431">Soweit möglich, werden Dateien, Grafiken oder andere Inhalte aus dem Textkörper des Quellelements in diese Eigenschaft einbezogen.</span><span class="sxs-lookup"><span data-stu-id="ee563-431">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="ee563-432">Andernfalls wird der Inhalt aus dem Quellelement in die Eigenschaft **ATTACHMENT** einbezogen.</span><span class="sxs-lookup"><span data-stu-id="ee563-432">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="ee563-433">Der Inhalt dieser Eigenschaft hängt vom Partner-Konnektor und der Funktion der QuellPlattform ab.</span><span class="sxs-lookup"><span data-stu-id="ee563-433">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="ee563-434">**Anlage**</span><span class="sxs-lookup"><span data-stu-id="ee563-434">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="ee563-435">Nein</span><span class="sxs-lookup"><span data-stu-id="ee563-435">No</span></span>  <br/> |<span data-ttu-id="ee563-436">Wenn ein Element in der Datenquelle (beispielsweise ein tweet in Twitter oder eine Chatnachrichten Unterhaltung) über eine angefügte Datei verfügt oder Bilder enthält, versucht der Partner Connect zunächst, Anlagen in die **Body** -Eigenschaft einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ee563-436">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="ee563-437">Wenn dies nicht möglich ist, wird es zur \* \* Attachment \* \*-Eigenschaft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ee563-437">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="ee563-438">Weitere Beispiele für Anlagen sind „Gefällt mir“-Angaben in Facebook, Metadaten aus der Inhaltsquelle und Antworten auf eine Nachricht oder einen Beitrag.</span><span class="sxs-lookup"><span data-stu-id="ee563-438">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="ee563-439">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="ee563-439">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="ee563-440">Ja</span><span class="sxs-lookup"><span data-stu-id="ee563-440">Yes</span></span>  <br/> | <span data-ttu-id="ee563-441">Dies ist eine Eigenschaft mit mehreren Werten, die vom Partnerconnector erstellt und mit Werten gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="ee563-441">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="ee563-442">Das Format dieser Eigenschaft ist `IPM.NOTE.Source.Event` .</span><span class="sxs-lookup"><span data-stu-id="ee563-442">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="ee563-443">(Diese Eigenschaft muss mit beginnen `IPM.NOTE` .</span><span class="sxs-lookup"><span data-stu-id="ee563-443">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="ee563-444">Dieses Format ähnelt dem für die `IPM.NOTE.X` Nachrichtenklasse.) Diese Eigenschaft enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="ee563-444">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="ee563-445">`Source`: Gibt die Datenquelle eines Drittanbieters an; zum Beispiel Twitter, Facebook oder BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="ee563-445">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="ee563-446">`Event`: Gibt die Art der Aktivität an, die in der Drittanbieter-Datenquelle ausgeführt wurde, die die Elemente erstellt hat; zum Beispiel ein tweet in Twitter oder ein Beitrag in Facebook.</span><span class="sxs-lookup"><span data-stu-id="ee563-446">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="ee563-447">Ereignisse sind für die jeweilige Datenquelle spezifisch.</span><span class="sxs-lookup"><span data-stu-id="ee563-447">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="ee563-448">Ein Zweck dieser Eigenschaft ist es zum Beispiel, bestimmte Elemente basierend auf der Datenquelle zu filtern, aus der ein Element stammt, oder basierend auf dem Typ des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="ee563-448">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="ee563-449">So könnten Sie in einer eDiscovery-Suche zum Beispiel eine Suchabfrage erstellen, um alle Tweets zu finden, die von einem bestimmten Benutzer gepostet wurden.</span><span class="sxs-lookup"><span data-stu-id="ee563-449">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="ee563-450">Wenn Elemente in Office 365 erfolgreich in Postfächer importiert werden, wird ein eindeutiger Bezeichner als Teil der HTTP-Antwort zurück an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee563-450">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="ee563-451">Dieser Bezeichner, `x-IngestionCorrelationID` der aufgerufen wird, kann für nachfolgende Problembehandlungszwecke von Partnern zur End-to-End-Überwachung von Elementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee563-451">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="ee563-452">Es wird empfohlen, dass Partner diese Informationen entsprechend erfassen und sammeln.</span><span class="sxs-lookup"><span data-stu-id="ee563-452">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="ee563-453">Im Folgenden ist ein Beispiel einer HTTP-Antwort mit diesem Bezeichner aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ee563-453">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="ee563-454">Sie können das Tool für die Inhaltssuche im Security and Compliance Center verwenden, um nach Elementen zu suchen, die von einer Drittanbieter-Datenquelle in Postfächer importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ee563-454">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="ee563-455">Um gezielt nach diesen importierten Elementen zu suchen, können Sie die folgenden Nachrichten Eigenschaftswert-Paare im Feld Stichwort für eine Inhaltssuche verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee563-455">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="ee563-456">**`kind:externaldata`**: Verwenden Sie dieses Eigenschaftswert-Paar, um alle Drittanbieter-Datentypen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="ee563-456">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="ee563-457">Um beispielsweise nach Elementen zu suchen, die aus einer Drittanbieter-Datenquelle importiert wurden und das Wort "Contoso" in der Subject-Eigenschaft des importierten Elements enthielten, würden Sie die Stichwortabfrage verwenden `kind:externaldata AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="ee563-457">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="ee563-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Verwenden Sie dieses Eigenschaftswert-Paar, um nur einen Typ von drittanbieterdaten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ee563-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="ee563-459">Wenn Sie beispielsweise nur Facebook-Daten durchsuchen möchten, die das Wort "Contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die Stichwort-Abfrage `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .</span><span class="sxs-lookup"><span data-stu-id="ee563-459">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="ee563-460">Eine vollständige Liste der Werte, die für Drittanbieter-Datentypen für die Eigenschaft verwendet werden sollen `itemclass` , finden Sie unter [Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die in Office 365 importiert wurden](use-content-search-to-search-third-party-data-that-was-imported.md).</span><span class="sxs-lookup"><span data-stu-id="ee563-460">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="ee563-461">Weitere Informationen zur Verwendung der Inhaltssuche und zum Erstellen von Stichwortsuchabfragen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ee563-461">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="ee563-462">Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="ee563-462">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="ee563-463">Stichwortabfragen und Suchbedingungen für die Inhaltssuche</span><span class="sxs-lookup"><span data-stu-id="ee563-463">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
