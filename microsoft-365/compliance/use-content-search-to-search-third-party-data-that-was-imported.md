---
title: Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die in Office 365 importiert wurden
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Verwenden Sie das eDiscovery-Tool für die Inhaltssuche, um nach Elementen zu suchen, die in Office 365 aus einer Drittanbieter-Datenquelle in Postfächer importiert wurden. Sie können eine Abfrage erstellen, um nach allen importierten Elementen zu suchen oder eine Abfrage zum Suchen nach bestimmten Drittanbieter-Datentypen zu erstellen. In diesem Artikel werden die Werte aufgelistet, die Sie in einer Stichwortabfrage verwenden können, um die Datentypen von Drittanbietern zu durchsuchen, die Sie in Office 365 importieren können.
ms.openlocfilehash: 57a39049ae1df3707a96311c9138195b7cc4c83a
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686275"
---
# <a name="use-content-search-to-search-third-party-data-imported-to-office-365"></a><span data-ttu-id="374cb-105">Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die in Office 365 importiert wurden</span><span class="sxs-lookup"><span data-stu-id="374cb-105">Use Content Search to search third-party data imported to Office 365</span></span>

<span data-ttu-id="374cb-106">Sie können das eDiscovery-Tool für die [Inhaltssuche](content-search.md) im Security #a0 Compliance Center verwenden, um nach Elementen zu suchen, die in Office 365 von einer Drittanbieter-Datenquelle in Postfächer importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="374cb-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="374cb-107">Sie können eine Abfrage erstellen, um alle importierten Datenelemente eines Drittanbieters zu durchsuchen, oder Sie können eine Abfrage zum Durchsuchen bestimmter Drittanbieter-Datenelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="374cb-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="374cb-108">Sie können auch eine abfragebasierte Office 365-Aufbewahrungsrichtlinie oder einen abfragebasierten eDiscovery-Speicher erstellen, um drittanbieterdaten in Office 365 zu speichern.</span><span class="sxs-lookup"><span data-stu-id="374cb-108">Also, you can also create a query-based Office 365 retention policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="374cb-109">Weitere Informationen zum Importieren von drittanbieterdaten und eine Liste der Datentypen eines Drittanbieters, die Sie in Office 365 importieren können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="374cb-109">For more information about importing third-party data and a list of the third-party data types that you can import to Office 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="374cb-110">Erstellen einer Abfrage zum Durchsuchen aller drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="374cb-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="374cb-111">Zum Suchen (oder aufbewahren) beliebiger Typen von drittanbieterdaten, die Sie in Office 365 importiert haben, können Sie das `kind:externaldata` Nachrichten Eigenschaftswert-Paar im Feld Schlüsselwort für eine Inhaltssuche oder beim Erstellen eines abfragebasierten haltebereichs verwenden.</span><span class="sxs-lookup"><span data-stu-id="374cb-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="374cb-112">Um beispielsweise nach Elementen zu suchen, die aus einer Datenquelle eines Drittanbieters importiert wurden und das Wort "Contoso" in der Subject-Eigenschaft des importierten Elements enthalten, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="374cb-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="374cb-113">Das vorherige Keyword-Abfragebeispiel enthält die Subject-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="374cb-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="374cb-114">Eine Liste der anderen Eigenschaften von Drittanbieter-Datenelementen, die in eine Stichwortabfrage einbezogen werden können, finden Sie im Abschnitt "Weitere Informationen" unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="374cb-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="374cb-115">Beim Erstellen von Abfragen zum Durchsuchen und Speichern von drittanbieterdaten können Sie auch Bedingungen verwenden, um die Suchergebnisse einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="374cb-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="374cb-116">Weitere Informationen zum Erstellen von Suchabfragen für Inhalte finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="374cb-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="374cb-117">Erstellen einer Abfrage zum Durchsuchen bestimmter Typen von drittanbieterdaten</span><span class="sxs-lookup"><span data-stu-id="374cb-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="374cb-118">Anstatt alle Typen von drittanbieterdaten zu durchsuchen, können Sie Abfragen erstellen, die nur nach einem Typ von drittanbieterdaten suchen, indem Sie die folgende Nachrichten *Eigenschaft: Wert* Paar in das Feld Stichwort für eine Inhaltssuche eingeben:</span><span class="sxs-lookup"><span data-stu-id="374cb-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="374cb-119">Um beispielsweise Facebook-Daten zu durchsuchen, die das Wort "Contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die folgende Abfrage:</span><span class="sxs-lookup"><span data-stu-id="374cb-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="374cb-120">In der folgenden Tabelle sind die Drittanbieter-Datentypen aufgeführt, die Sie durchsuchen können, und der Wert `itemclass:` , der für die Message-Eigenschaft verwendet werden kann, um speziell nach diesem Typ von drittanbieterdaten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="374cb-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="374cb-121">Bei der Abfragesyntax wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="374cb-121">The query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="374cb-122">**Datentyp eines Drittanbieters**</span><span class="sxs-lookup"><span data-stu-id="374cb-122">**Third-party data type**</span></span>|<span data-ttu-id="374cb-123">**Wert für `itemclass:` Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="374cb-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="374cb-124">Versuchen</span><span class="sxs-lookup"><span data-stu-id="374cb-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="374cb-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="374cb-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="374cb-126">AOL mit Pivot-Client
</span><span class="sxs-lookup"><span data-stu-id="374cb-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="374cb-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="374cb-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="374cb-128">Ares</span><span class="sxs-lookup"><span data-stu-id="374cb-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="374cb-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="374cb-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="374cb-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="374cb-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="374cb-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="374cb-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="374cb-132">AXS-Platzhalter</span><span class="sxs-lookup"><span data-stu-id="374cb-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="374cb-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="374cb-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="374cb-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="374cb-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="374cb-135">BearShare</span><span class="sxs-lookup"><span data-stu-id="374cb-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="374cb-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="374cb-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="374cb-137">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="374cb-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="374cb-138">BlackBerry-Anrufprotokolle</span><span class="sxs-lookup"><span data-stu-id="374cb-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="374cb-139">BlackBerry-Messenger</span><span class="sxs-lookup"><span data-stu-id="374cb-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="374cb-140">BlackBerry-PIN</span><span class="sxs-lookup"><span data-stu-id="374cb-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="374cb-141">BlackBerry-SMS</span><span class="sxs-lookup"><span data-stu-id="374cb-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="374cb-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="374cb-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="374cb-143">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="374cb-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="374cb-144">Bloomberg-Messaging</span><span class="sxs-lookup"><span data-stu-id="374cb-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="374cb-145">Box</span><span class="sxs-lookup"><span data-stu-id="374cb-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="374cb-146">Cisco- &amp; Chat-Anwesenheits Server</span><span class="sxs-lookup"><span data-stu-id="374cb-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="374cb-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="374cb-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="374cb-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="374cb-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="374cb-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="374cb-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="374cb-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="374cb-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="374cb-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="374cb-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="374cb-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="374cb-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="374cb-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="374cb-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="374cb-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="374cb-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="374cb-155">Google +</span><span class="sxs-lookup"><span data-stu-id="374cb-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="374cb-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="374cb-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="374cb-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="374cb-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="374cb-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="374cb-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="374cb-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="374cb-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="374cb-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="374cb-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="374cb-161">IBM-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="374cb-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="374cb-162">IBM Sametime</span><span class="sxs-lookup"><span data-stu-id="374cb-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="374cb-163">Ice-Chat</span><span class="sxs-lookup"><span data-stu-id="374cb-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="374cb-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="374cb-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="374cb-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="374cb-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="374cb-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="374cb-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="374cb-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="374cb-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="374cb-168">IRC</span><span class="sxs-lookup"><span data-stu-id="374cb-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="374cb-169">Jive</span><span class="sxs-lookup"><span data-stu-id="374cb-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="374cb-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="374cb-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="374cb-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="374cb-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="374cb-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="374cb-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="374cb-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="374cb-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="374cb-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="374cb-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="374cb-175">Mind align</span><span class="sxs-lookup"><span data-stu-id="374cb-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="374cb-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="374cb-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="374cb-177">MSN</span><span class="sxs-lookup"><span data-stu-id="374cb-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="374cb-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="374cb-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="374cb-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="374cb-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="374cb-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="374cb-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="374cb-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="374cb-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="374cb-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="374cb-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="374cb-183">QQ</span><span class="sxs-lookup"><span data-stu-id="374cb-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="374cb-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="374cb-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="374cb-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="374cb-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="374cb-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="374cb-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="374cb-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="374cb-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="374cb-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="374cb-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="374cb-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="374cb-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="374cb-190">Symphonie</span><span class="sxs-lookup"><span data-stu-id="374cb-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="374cb-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="374cb-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="374cb-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="374cb-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="374cb-193">Tor</span><span class="sxs-lookup"><span data-stu-id="374cb-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="374cb-194">TTT</span><span class="sxs-lookup"><span data-stu-id="374cb-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="374cb-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="374cb-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="374cb-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="374cb-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="374cb-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="374cb-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="374cb-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="374cb-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="374cb-199">Winny</span><span class="sxs-lookup"><span data-stu-id="374cb-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="374cb-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="374cb-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="374cb-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="374cb-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="374cb-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="374cb-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="374cb-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="374cb-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
