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
# <a name="archive-third-party-data"></a>Archivieren von Drittanbieterdaten

Microsoft 365 ermöglicht Administratoren das Importieren und Archivieren von drittanbieterdaten aus Social Media-Plattformen, Instant Messaging-Plattformen und Dokument Zusammenarbeits Plattformen in Postfächern in Ihrer Microsoft 365-Organisation. Beispiele für Drittanbieter-Datenquellen, die Sie in Microsoft 365 importieren können, umfassen die folgenden Dienste: 
  
- **Soziale Netzwerke:** Facebook, LinkedIn, Twitter und jammern

- **Instant Messaging:** Yahoo Messenger und googletalk

- **Dokument Zusammenarbeit:** Box und Dropbox

- **Vertikale Branchen:** Kunden Beziehungs Management (beispielsweise Salesforce Chatter) und Finanzdienstleistungen (wie Bloomberg und Thomson Reuters)

- **SMS/Textnachrichten:** BlackBerry

Nach dem Importieren von drittanbieterdaten können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, in-situ-Archivierung, Überwachung, Kommunikations Konformität und Aufbewahrungsrichtlinien auf diese Daten anwenden. Wenn beispielsweise ein Postfach in das Beweissicherungsverfahren gestellt wird, werden drittanbieterdaten beibehalten. Sie können drittanbieterdaten mithilfe von Microsoft eDiscovery-Tools durchsuchen. Sie können auch Archivierungs-und Aufbewahrungsrichtlinien auf drittanbieterdaten anwenden, genau wie für Microsoft-Daten. Kurz gesagt: das Archivieren von drittanbieterdaten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

Es gibt zwei Möglichkeiten zum Importieren und Archivieren von drittanbieterdaten in Microsoft 365:

- **Verwenden Sie einen Drittanbieter-Daten Konnektor im Security & Compliance Center:** Verwenden Sie einen benutzerdefinierten Daten Konnektor, der im Microsoft 365 Compliance Center verfügbar ist. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der Drittanbieter-Datenquelle her, wandelt den Inhalt eines Elements in ein e-Mail-Nachrichtenformat um und importiert dann das Element in ein Postfach in Microsoft 365. Derzeit können Sie Connectors zum Importieren und Archivieren von Daten von Facebook-Geschäfts Seiten, Unternehmens Twitter-Konten, LinkedIn, Instant Bloomberg und den Personaldaten Ihrer Organisation implementieren. Eine Schritt-für-Schritt-Anleitung zum Einrichten eines dieser Connectors finden Sie unter:

   - **Facebook:** [Verwenden eines Connectors zum Archivieren von Facebook-Daten (Vorschau)](archive-facebook-data-with-sample-connector.md)

   - **Twitter:** [Verwenden eines Connectors zum Archivieren von Twitter-Daten (Vorschau)](archive-twitter-data-with-sample-connector.md)

   - **LinkedIn:** [Einrichten eines Connectors zum Archivieren von LinkedIn Daten](archive-linkedin-data.md)

   - **Instant Bloomberg:** [Einrichten eines Connectors zum Archivieren von sofort Bloomberg-Daten](archive-instant-bloomberg-data.md)

   - **HR-Daten:** [Einrichten eines Connectors zum Importieren von HR-Daten (Vorschau)](import-hr-data.md)

- **Arbeiten mit einem Microsoft-Partner:** Ihre Organisation arbeitet mit einem Microsoft-Partner zusammen, der einen benutzerdefinierten Connector bereitstellt, der so konfiguriert ist, dass er regelmäßig Elemente aus der Drittanbieter-Datenquelle extrahiert und anschließend eine Verbindung mit der Microsoft-Cloud über eine Drittanbieter-API herstellen und diese Elemente nach Microsoft 365 importieren kann. Der Partner Connector konvertiert auch den Inhalt eines Elements aus der Drittanbieter-Datenquelle in eine e-Mail-Nachricht und importiert diese dann in ein Postfach in Microsoft 365. Eine Liste der Partner, mit denen Sie zusammenarbeiten und den schrittweisen Prozess für diese Methode ausführen können, finden Sie unter [Arbeiten mit einem Partner zum Archivieren von drittanbieterdaten in Microsoft 365](work-with-partner-to-archive-third-party-data.md).
