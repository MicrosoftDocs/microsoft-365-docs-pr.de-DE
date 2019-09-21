---
title: Archivieren von Drittanbieterdaten in Office 365
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
description: Administratoren können Daten von Drittanbietern aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen zu Postfächern in Ihrer Office 365 Organisation importieren. Auf diese Weise können Sie Daten aus Facebook, Twitter und anderen Datenquellen von Drittanbietern in Office 365 archivieren. Anschließend können Sie Office 365 Compliance-Features (wie Legal Hold, eDiscovery, in-situ-Archivierung und Aufbewahrungsrichtlinien) für drittanbieterdaten verwenden und anwenden.
ms.openlocfilehash: 4b6236a7eaac4fa061d1cfbb770efd0a721804aa
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081093"
---
# <a name="archive-third-party-data-in-office-365"></a>Archivieren von Drittanbieterdaten in Office 365

Office 365 können Administratoren drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen in Postfächern in Ihrer Office 365 Organisation importieren und archivieren. Beispiele für Drittanbieter-Datenquellen, die Sie in Office 365 importieren können, umfassen die folgenden Dienste: 
  
- **Soziale Netzwerke:** Facebook, LinkedIn, Twitter und jammern 
    
- **Instant Messaging:** Yahoo Messenger, GoogleTalk und Cisco Jabber 
    
- **Dokument Zusammenarbeit:** Box und Dropbox 
    
- **Vertikale Branchen:** Kunden Beziehungs Management (beispielsweise Salesforce Chatter) und Finanzdienstleistungen (wie Bloomberg und Thomson Reuters) 
    
- **SMS/Textnachrichten:** BlackBerry 
    
Nachdem Sie Daten von Drittanbietern importiert haben, können Sie auf diese Daten Office 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, in-situ-Archivierung, Überwachung, Überwachung und Office 365 Aufbewahrungsrichtlinien anwenden. Wenn beispielsweise ein Postfach in das Beweissicherungsverfahren gestellt wird, werden drittanbieterdaten beibehalten. Sie können drittanbieterdaten mithilfe von Microsoft eDiscovery-Tools durchsuchen. Sie können auch Archivierungs-und Aufbewahrungsrichtlinien auf drittanbieterdaten anwenden, genau wie für Microsoft-Daten. Kurz gesagt: das Archivieren von drittanbieterdaten in Office 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

Es gibt zwei Möglichkeiten zum Importieren und Archivieren von drittanbieterdaten in Office 365:

- **Verwenden Sie einen Drittanbieter-Daten Konnektor im Security #a0 Compliance Center:** Verwenden Sie einen benutzerdefinierten Daten Konnektor, der im Security #a1 Compliance Center in Office 365 verfügbar ist. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der Drittanbieter-Datenquelle her, wandelt den Inhalt eines Elements in ein e-Mail-Nachrichtenformat um und importiert dann das Element in ein Postfach in Office 365. Derzeit können Sie Connectors zum Importieren und Archivieren von Daten von Facebook-Geschäfts Seiten, Unternehmens Twitter-Konten, Instant Bloomberg und LinkedIn implementieren. Die Schritt-für-Schritt-Anleitung zum Einrichten eines Connectors finden Sie unter:
   
   - **Facebook:** [Verwenden eines Beispiel-Konnektors zum Archivieren von Facebook-Daten in Office 365](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter:** [Verwenden eines Beispiel-Konnektors zum Archivieren von Twitter-Daten in Office 365](archive-twitter-data-with-sample-connector.md)
    
   - **LinkedIn:** [Einrichten eines Connectors zum Archivieren von LinkedIn Daten in Office 365](archive-linkedin-data.md)

   - **Instant Bloomberg:** [Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten in Office 365](archive-instant-bloomberg-data.md)

- **Arbeiten mit einem Microsoft-Partner:** Ihre Organisation arbeitet mit einem Microsoft-Partner zusammen, der einen benutzerdefinierten Connector bereitstellt, der so konfiguriert ist, dass er regelmäßig Elemente aus der Drittanbieter-Datenquelle extrahiert und anschließend eine Verbindung mit der Microsoft-Cloud über eine Drittanbieter-API herstellen und diese Elemente in importieren kann. Office 365. Der Partner Connector wandelt auch den Inhalt eines Elements aus der Drittanbieter-Datenquelle in eine e-Mail-Nachricht um und importiert diese dann in ein Postfach in Office 365. Eine Liste der Partner, mit denen Sie zusammenarbeiten und den schrittweisen Prozess für diese Methode ausführen können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Office 365](work-with-partner-to-archive-third-party-data.md).
