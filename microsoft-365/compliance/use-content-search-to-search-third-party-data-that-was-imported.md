---
title: Verwenden der Inhaltssuche zum Durchsuchen von importierten Daten von Drittanbietern
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
description: Verwenden Sie das eDiscovery-Tool für die Inhaltssuche, um nach Elementen zu suchen, die von einer Drittanbieter-Datenquelle in Postfächer in Microsoft 365 importiert wurden, indem Sie Abfragen erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 916a780bccc3f24d509991e8ac72f31b374757d4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819095"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Verwenden der Inhaltssuche zum Durchsuchen von drittanbieterdaten, die von einem benutzerdefinierten Partner Connector importiert wurden

Sie können das eDiscovery-Tool für die [Inhaltssuche](content-search.md) im Security & Compliance Center verwenden, um nach Elementen zu suchen, die in Microsoft 365 von einer Drittanbieter-Datenquelle in Postfächer importiert wurden. Sie können eine Abfrage erstellen, um alle importierten Datenelemente eines Drittanbieters zu durchsuchen, oder Sie können eine Abfrage zum Durchsuchen bestimmter Drittanbieter-Datenelemente erstellen. Darüber hinaus können Sie auch eine abfragebasierte Aufbewahrungsrichtlinie oder einen abfragebasierten eDiscovery-Speicher erstellen, um drittanbieterdaten zu speichern.
  
Weitere Informationen zur Zusammenarbeit mit einem Partner zum Importieren von drittanbieterdaten und einer Liste der Drittanbieter Datentypen, die Sie in Microsoft 365 importieren können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365](work-with-partner-to-archive-third-party-data.md).

> [!IMPORTANT]
> Die Anleitungen in diesem Artikel gelten nur für drittanbieterdaten, die von einem benutzerdefinierten Partner Connector importiert wurden. Dieser Artikel gilt nicht für drittanbieterdaten, die mithilfe der [Drittanbieter-Daten Konnektoren](archiving-third-party-data.md#third-party-data-connectors) im Microsoft Compliance Center importiert werden.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Erstellen einer Abfrage zum Durchsuchen aller drittanbieterdaten

Zum Suchen (oder aufbewahren) beliebiger Typen von drittanbieterdaten, die Sie in Office 365 importiert haben, können Sie das `kind:externaldata` Nachrichten Eigenschaftswert-Paar im Feld Schlüsselwort für eine Inhaltssuche oder beim Erstellen eines abfragebasierten haltebereichs verwenden. Um beispielsweise nach Elementen zu suchen, die aus einer Datenquelle eines Drittanbieters importiert wurden und das Wort "Contoso" in der Subject-Eigenschaft des importierten Elements enthalten, verwenden Sie die folgende Abfrage: 
  
```powershell
kind:externaldata AND subject:contoso
```

Das vorherige Keyword-Abfragebeispiel enthält die Subject-Eigenschaft. Eine Liste der anderen Eigenschaften von Drittanbieter-Datenelementen, die in eine Stichwortabfrage einbezogen werden können, finden Sie im Abschnitt "Weitere Informationen" unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).
  
Beim Erstellen von Abfragen zum Durchsuchen und Speichern von drittanbieterdaten können Sie auch Bedingungen verwenden, um die Suchergebnisse einzuschränken. Weitere Informationen zum Erstellen von Suchabfragen für Inhalte finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Erstellen einer Abfrage zum Durchsuchen bestimmter Typen von drittanbieterdaten

Anstatt alle Typen von drittanbieterdaten zu durchsuchen, können Sie Abfragen erstellen, die nur nach einem Typ von drittanbieterdaten suchen, indem Sie die folgende Nachrichten *Eigenschaft: Wert* Paar in das Feld Stichwort für eine Inhaltssuche eingeben:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Um beispielsweise Facebook-Daten zu durchsuchen, die das Wort "Contoso" in der Subject-Eigenschaft enthalten, verwenden Sie die folgende Abfrage:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

In der folgenden Tabelle sind die Drittanbieter-Datentypen aufgeführt, die Sie durchsuchen können, und der Wert, der für die Message-Eigenschaft verwendet werden kann, `itemclass:` um speziell nach diesem Typ von drittanbieterdaten zu suchen. Bei der Abfragesyntax wird die Groß-/Kleinschreibung nicht beachtet. 
  
|**Datentyp eines Drittanbieters**|**Wert für `itemclass:` Eigenschaft**|
|:-----|:-----|
|Versuchen  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL mit Pivot-Client
  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|AXS-Platzhalter  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|BearShare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|BlackBerry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry-Anrufprotokolle  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry-Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry-PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry-SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg Mail  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg-Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco-Chat- &amp; Anwesenheits Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google +  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM-Verbindungen  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM Sametime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|Ice-Chat  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
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
|Mind align  <br/> | `ipm.externaldata.MindAlign*` <br/> |
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
|Symphonie  <br/> | `ipm.externaldata.Symphony*` <br/> |
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
