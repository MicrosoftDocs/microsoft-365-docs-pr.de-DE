---
title: Erweiterte Indizierung von Daten für eine Untersuchung
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 77a4b3e1826889e996b875c9427013c7b08dfaaf
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600642"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a>Erweiterte Indizierung von Daten für eine Untersuchung

Inhalte im Live-System können teilweise aus einer Reihe von Gründen indiziert werden, einschließlich des Vorhandenseins von Bildern, nicht unterstützten Dateitypen oder wenn die Größenbeschränkungen für die Indizierungs Datei auftreten. Wenn Sie mit Datenüberlauf mit hohem Risiko zu tun haben, möchten Sie sicherstellen, dass die Suche alle Daten erfasst, die Sie untersuchen möchten. Wenn eine Person von Interesse zu einer Datenermittlung hinzugefügt wird, werden alle Inhalte in Office 365, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind. Dieser Vorgang wird als *Erweiterte Indizierung*bezeichnet. 

Weitere Informationen zur Verarbeitungsunterstützung in Office 365 und teilweise indizierten Elementen finden Sie unter:

- [Unterstützte Dateitypen in Daten Ermittlungen](supported-filetypes-datainvestigations.md)

- [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)

- [Von der Exchange-Suche indizierte Dateiformate](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Anzeigen erweiterter Indizierungs Ergebnisse

Nachdem der erweiterte Indizierungsprozess abgeschlossen ist, können Sie ein Verständnis der Effektivität der erneuten Verarbeitung erhalten.  In der Ansicht Personen von Interesse indiziert das Diagramm alle Elemente, die dem *Hybrid Index*hinzugefügt werden.  Im Hybrid Index werden durch Daten Untersuchungen (Preview) die wieder verarbeiteten Inhalte gespeichert.

Das Diagramm enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp. Weitere Informationen finden Sie unter [Fehlerkorrektur bei der Verarbeitung von Daten](error-remediation.md).

## <a name="updating-advanced-indexes-for-people-of-interest"></a>Aktualisieren erweiterter Indizes für interessante Personen

Wenn eine Person von Interesse zu einer Daten Untersuchung hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet. Im Laufe der Zeit werden dem Postfach eines Benutzers oder dem OneDrive-Konto jedoch möglicherweise mehr teilweise indizierte Elemente hinzugefügt.  Bei Bedarf können Sie die Indizes aktualisieren.

> [!NOTE]
> Das Aktualisieren von Indizes für Personen mit Interesse ist ein langwieriger Prozess. Es wird empfohlen, dass Sie Indizes nicht mehr als einmal pro Tag in einer Untersuchung aktualisieren.
