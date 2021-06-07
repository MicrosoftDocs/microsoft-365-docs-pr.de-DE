---
title: Schützen der Daten Ihrer Organisation mit gerätesteuerung
description: Überwachen Sie die Datensicherheit Ihrer Organisation über Gerätesteuerungsberichte.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772365"
---
# <a name="protect-your-organizations-data-with-device-control"></a>Schützen der Daten Ihrer Organisation mit gerätesteuerung

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2069559)

Die Gerätesteuerung von Microsoft Defender für Endpunkt schützt vor Datenverlust, indem die Mediennutzung durch Geräte in Ihrer Organisation überwacht und gesteuert wird, z. B. die Verwendung von Wechselmedien und USB-Laufwerken.

Mit dem Gerätesteuerungsbericht können Sie Ereignisse anzeigen, die sich auf die Mediennutzung beziehen, z. B.:

- **Überwachungsereignisse:** Zeigt die Anzahl der Überwachungsereignisse an, die auftreten, wenn externe Medien verbunden sind.
- **Richtlinienereignisse:** Zeigt die Anzahl der Richtlinienereignisse an, die auftreten, wenn eine Gerätesteuerungsrichtlinie ausgelöst wird.

> [!NOTE]
> Das Überwachungsereignis zum Nachverfolgen der Mediennutzung ist standardmäßig für Geräte aktiviert, die in Microsoft Defender für Endpunkt integriert sind.

## <a name="understanding-the-audit-events"></a>Grundlegendes zu den Überwachungsereignissen

Zu den Überwachungsereignissen gehören:

- **USB-Laufwerkshalterung und Aufheben der Bereitstellung:** Überwachungsereignisse, die generiert werden, wenn ein USB-Laufwerk bereitgestellt oder die Bereitstellung aufgehoben wird.
- **PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.

## <a name="monitor-device-control-security"></a>Überwachen der Gerätesteuerungssicherheit

Die Gerätesteuerung in Microsoft Defender für Endpunkt ermöglicht Sicherheitsadministratoren Tools, mit denen sie die Gerätesteuerungssicherheit ihrer Organisation über Berichte nachverfolgen können. Sie finden den Gerätesteuerungsbericht im Microsoft 365 Security Center, indem Sie zu **"Berichte > Geräteschutz"** wechseln.

Die Karte "Geräteschutz" im **Dashboard "Berichte"** zeigt die Anzahl von Überwachungsereignissen an, die vom Medientyp in den letzten 180 Tagen generiert wurden.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](images/devicecontrolcard.png)

Die Schaltfläche **"Details anzeigen"** zeigt weitere Mediennutzungsdaten auf der Berichtsseite des **Gerätesteuerelements** an.

Die Seite bietet ein Dashboard mit der aggregierten Anzahl von Ereignissen pro Typ und einer Liste von Ereignissen. Administratoren können nach Zeitbereich, Medienklassenname und Geräte-ID filtern.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)

Wenn Sie ein Ereignis auswählen, wird ein Flyout mit weiteren Informationen angezeigt:

- **Allgemeine Details:** Datum, Aktionsmodus und die Richtlinie dieses Ereignisses.
- **Medieninformationen:** Medieninformationen umfassen Medienname, Klassenname, Klassen-GUID, Geräte-ID, Anbieter-ID, Volume, Seriennummer und Bustyp.
- **Standortdetails:** Gerätename und MDATP Geräte-ID.

> [!div class="mx-imgBorder"]
> ![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)

Um Echtzeitaktivitäten für diese Medien in der gesamten Organisation anzuzeigen, wählen Sie die Schaltfläche **"Erweiterte Suche öffnen"** aus. Dazu gehört eine eingebettete, vordefinierte Abfrage.

> [!div class="mx-imgBorder"]
> ![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)

Um die Sicherheit des Geräts anzuzeigen, wählen Sie die Schaltfläche **"Geräteseite öffnen"** im Flyout aus. Mit dieser Schaltfläche wird die Geräteentitätsseite geöffnet.

> [!div class="mx-imgBorder"]
> ![DeviceEntityPage](images/Devicesecuritypage.png)

## <a name="reporting-delays"></a>Melden von Verzögerungen

Der Gerätesteuerungsbericht kann eine 12-Stunden-Verzögerung von dem Zeitpunkt, zu dem eine Medienverbindung auftritt, bis zu dem Zeitpunkt haben, an dem das Ereignis auf der Karte oder in der Domänenliste wiedergegeben wird.
