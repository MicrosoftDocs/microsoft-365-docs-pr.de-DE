---
title: Akku-Einblicke
description: Ein Bericht, der Daten über die vorhergesagte Akkulaufzeit und die besten Stromverbraucher enthält
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579710"
---
# <a name="battery-insights"></a>Akku-Einblicke
Diese Ansicht bietet Leistungs-, Akku- und App-Nutzungsmetriken für Ihre Microsoft Managed Desktop-Geräte. Zu diesen Zwecken wird eine App als "in Gebrauch" betrachtet, wenn sie ausgeführt wird und im Fokus steht.

Wählen Sie zum Anzeigen von Verwendungsdaten die Registerkarte **Akku** aus.

![Akkubereich: Vorhergesagte Akkulaufzeit pro Gerätemodell oben links, Energieverbraucher (per App) oben rechts, Einblicke tabelle unten. Dokumentationslink oben rechts](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Vorhergesagte Akkulaufzeit

Im Bereich **Vorhergesagte** Akkulaufzeit bieten wir Vorhersagen für die erwartete Akkulaufzeit für Ihre Geräte, organisiert nach Gerätemodell.

> [!NOTE]
> Diese Daten werden aus einer zufälligen Auswahl der Geräte <em></em> in Ihrer Microsoft Managed Desktop-Bereitstellung abgeleitet, die auch Daten melden.

Die Tabelle enthält die vorhergesagte Akkulaufzeit (in Stunden), die durchschnittliche Akkulaufzeit für dieselben Modelle in anderen Microsoft Managed Desktop-Bereitstellungen und die Anzahl der Geräte, die diese Daten in Ihrer Umgebung melden. Sortieren Sie die Daten, indem Sie die Spaltenüberschriften auswählen.



## <a name="top-energy-consumers"></a>Energieverbraucher am meisten

Im Bereich **Top energy consumers** finden Sie die Apps in Ihrer Umgebung, die die meiste Energie in mgWatt-Stunden (mWh) verbrauchen. Die angezeigten Apps werden pro bestimmtem Gerät angezeigt, das Sie im Abschnitt **"Vorhergesagte Akkulaufzeit"** links auswählen. Wenn Sie z. B. den Verbrauch pro App für Microsoft Surface Book 2-Geräte sehen möchten, wählen Sie diese Zeile im Bereich Akkulaufzeit aus. Wenn Sie kein Modell auswählen, werden die angezeigten App-Nutzungsdaten für alle Apps verwendet, für die wir Daten gemeinsam verwenden.

 Für jede App zeigen farbige Segmente die Verteilung des Energieverbrauchs der App unter den folgenden Kategorien an:

- CPU
- Anzeigen
- Netzwerk
- Andere

"Other" könnte den Energieverbrauch aus einer Vielzahl von Quellen umfassen, z. B. Datenträgeraktivität, mobile Breitbandnutzung und Energie, die durch internen Widerstand verloren geht. 

Sie können diese Ansicht filtern, um nur Vordergrund-Apps, Hintergrund-Apps oder beides anzuzeigen, indem Sie das Menü oben rechts verwenden. Vordergrund-Apps sind Apps, die in den letzten 28 Tagen eine Benutzerinteraktion hatten, z. B. das Auswählen einer Maus.

## <a name="insights"></a>Einblicke

Der **Bereich Insights** zeigt die drei Energieverbraucher in den Kategorien CPU und Netzwerk an. Diese Elemente verbrauchen im Vergleich zu allen Microsoft Managed Desktop-Bereitstellungen überdurchschnittlich viel Energie. Die Anzeigeressource wird nicht angezeigt, da sie stark von der Gerätenutzungszeit und den Einstellungen für die Bildschirmhelligkeit abhängt. 

Wählen Sie die Einträge in der **Spalte Details** aus, um weitere Informationen zu erhalten.

## <a name="battery-optimization"></a>Akkuoptimierung

Windows 10 bietet zahlreiche [Geräteeinstellungen,](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) um den Energieverbrauch zu verbessern und die Akkulaufzeit Ihrer Microsoft Managed Desktop-Geräte zu erhöhen. Einige dieser Einstellungen können andere Windows-Funktionen verringern, sodass Sie auch andere Faktoren berücksichtigen müssen, z. B. die Rolle des Geräts in Ihrer Organisation. Die Windows-Unterstützung verwaltet eine Liste dieser [Tipps zum Speichern von Akkus.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Benutzer können einige Einstellungen selbst anpassen, ohne dass administratorerweiterungen oder -support benötigt werden. Andere Einstellungen erfordern Unterstützung durch den IT-Administrator Ihrer Organisation.
