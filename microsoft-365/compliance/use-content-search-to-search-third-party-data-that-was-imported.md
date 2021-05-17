---
title: Durchsuchen importierter Daten durch Drittanbieter mithilfe der Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Verwenden Sie das eDiscovery-Tool für die Inhaltssuche, um nach Elementen zu suchen, die in Postfächer in Microsoft 365 aus einer Datenquelle eines Drittanbieters importiert wurden, indem Sie Abfragen erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324571"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Durchsuchen von Von einem benutzerdefinierten Partnerconnector importierten Drittanbieterdaten mithilfe der Inhaltssuche

Sie können das [eDiscovery-Tool](content-search.md) für die Inhaltssuche im Security & Compliance Center verwenden, um nach Elementen zu suchen, die in Postfächer in Microsoft 365 aus einer Datenquelle eines Drittanbieters importiert wurden. Sie können eine Abfrage erstellen, um alle importierten Datenelemente von Drittanbietern zu durchsuchen, oder Sie können eine Abfrage erstellen, um bestimmte Datenelemente von Drittanbietern zu durchsuchen. Sie können auch eine abfragebasierte Aufbewahrungsrichtlinie oder einen abfragebasierten eDiscovery-Speicher erstellen, um Daten von Drittanbietern zu erhalten.
  
Weitere Informationen zum Arbeiten mit einem Partner zum Importieren von Drittanbieterdaten sowie eine Liste der Drittanbieterdatentypen, die Sie in Microsoft 365 importieren können, finden Sie unter Arbeiten mit einem Partner zum Archivieren von Drittanbieterdaten [in Office 365](work-with-partner-to-archive-third-party-data.md).

> [!IMPORTANT]
> Die Anleitung in diesem Artikel gilt nur für Drittanbieterdaten, die von einem benutzerdefinierten Partnerconnector importiert wurden. Dieser Artikel gilt nicht für Drittanbieterdaten, die mithilfe [](archiving-third-party-data.md#third-party-data-connectors) der Datenconnectors von Drittanbietern im Microsoft Compliance Center importiert werden.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Erstellen einer Abfrage zum Durchsuchen aller Drittanbieterdaten

Zum Durchsuchen (oder In-Warteschleifen) beliebiger Drittanbieterdaten, die Sie in Office 365 importiert haben, können Sie das Nachrichteneigenschafts-Wert-Paar im Schlüsselwortfeld für eine Inhaltssuche oder beim Erstellen eines abfragebasierten Haltespeichers `kind:externaldata` verwenden. Um beispielsweise nach Elementen zu suchen, die aus einer beliebigen Datenquelle eines Drittanbieters importiert wurden und das Wort "contoso" in der Subject-Eigenschaft des importierten Elements enthalten, verwenden Sie die folgende Abfrage: 
  
```powershell
kind:externaldata AND subject:contoso
```

Das vorherige Schlüsselwortabfragebeispiel enthält die subject-Eigenschaft. Eine Liste anderer Eigenschaften für Datenelemente von Drittanbietern, die in eine Stichwortabfrage aufgenommen werden können, finden Sie im Abschnitt "Weitere Informationen" unter Arbeiten mit einem Partner zum Archivieren von Drittanbieterdaten [in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).
  
Beim Erstellen von Abfragen zum Suchen und Speichern von Drittanbieterdaten können Sie auch Bedingungen verwenden, um die Suchergebnisse zu einenten. Weitere Informationen zum Erstellen von Inhaltssuchabfragen finden Sie unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Erstellen einer Abfrage zum Durchsuchen bestimmter Arten von Drittanbieterdaten

Anstatt alle Arten von Drittanbieterdaten zu durchsuchen, können Sie Abfragen erstellen, die nur nach einem bestimmten Typ von Drittanbieterdaten suchen, indem Sie die folgende Message-Eigenschaft *verwenden:* Wertpaar im Schlüsselwortfeld für eine Inhaltssuche:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Wenn Sie beispielsweise Facebook-Daten durchsuchen möchten, die das Wort "contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die folgende Abfrage:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

In der folgenden Tabelle sind die Datentypen von Drittanbietern aufgeführt, die Sie durchsuchen können, und den Wert, der für die Message-Eigenschaft verwendet werden soll, um speziell nach diesem Typ von  `itemclass:` Drittanbieterdaten zu suchen. Bei der Abfragesyntax wird die Zwischenschreibung nicht beachtet. 
  
|**Datentyp eines Drittanbieters**|**Wert für  `itemclass:` Eigenschaft**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL mit Pivot-Client
  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs Placeholder  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry-Anrufprotokolle  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg Message  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE Chat  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Mind Align  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
