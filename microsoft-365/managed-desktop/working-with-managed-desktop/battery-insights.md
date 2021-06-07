---
title: Akku-Einblicke
description: Ein Bericht, der Daten über die prognostizierte Akkulaufzeit und die wichtigsten Energieverbraucher zeigt
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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739792"
---
# <a name="battery-insights"></a>Akku-Einblicke
Diese Ansicht bietet Energie-, Akku- und App-Nutzungsmetriken für Ihre Microsoft Managed Desktop Geräte. Für diese Zwecke wird eine App als "verwendet" betrachtet, wenn sie ausgeführt wird und im Fokus steht.

Um Nutzungsdaten anzuzeigen, wählen Sie die Registerkarte **"Akku"** aus.

![Akkubereich: Pro Gerätemodell in oberer linker Ecke, oberer Energieverbraucher (nach App) oben rechts, Insights-Tabelle unten. Link "Dokumentation" oben rechts](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Prognostizierte Akkulaufzeit

Im Bereich **"Prognostizierte Akkulaufzeit"** stellen wir Nach Gerätemodell geordnete Vorhersagen für die erwartete Akkulaufzeit für Ihre Geräte bereit.

> [!NOTE]
> Diese Daten werden aus dem Sampling von Energieverbrauch, Nutzungszeit und Akkukapazität aus einer zufälligen <em>Auswahl</em> der Geräte in Ihrer Microsoft Managed Desktop-Bereitstellung abgeleitet, die auch Berichtsdaten bereitstellen.

Die Tabelle enthält die prognostizierte Akkulaufzeit (in Stunden), die durchschnittliche Akkulaufzeit für dieselben Modelle in anderen Microsoft Managed Desktop Bereitstellungen und die Anzahl der Geräte, die diese Daten in Ihrer Umgebung melden. Sortieren Sie die Daten, indem Sie die Spaltenüberschriften auswählen.



## <a name="top-energy-consumers"></a>Die wichtigsten Energieverbraucher

Im Bereich der **wichtigsten Energieverbraucher** finden Sie die Apps in Ihrer Umgebung, die den größten Energieverbrauch in Millattstunden (mWh) verbrauchen. Die angezeigten Apps beziehen sich auf ein bestimmtes Gerät, das Sie im Abschnitt **"Prognostizierte Akkulaufzeit"** auf der linken Seite auswählen. Um beispielsweise den Pro-App-Verbrauch für Ihre Microsoft Surface Book 2-Geräte anzuzeigen, wählen Sie diese Zeile im Akkulaufzeitbereich aus. Wenn Sie kein Modell auswählen, gelten die angezeigten App-Nutzungsdaten für alle Apps, für die wir Daten gemeinsam haben.

 Für jede App zeigen farbige Segmente die Verteilung des Energieverbrauchs der App in diesen Kategorien an:

- CPU
- Anzeigen
- Netzwerk
- Andere

"Andere" könnten den Energieverbrauch einer Vielzahl von Quellen umfassen, z. B. Datenträgeraktivität, mobile Breitbandnutzung und Energie, die durch internen Widerstand verloren gegangen ist. 

Sie können diese Ansicht so filtern, dass nur Vordergrund-Apps, Hintergrund-Apps oder beides angezeigt werden, indem Sie das Menü oben rechts verwenden. Vordergrund-Apps sind Apps, die in den letzten 28 Tagen eine Benutzerinteraktion durchgeführt haben, z. B. die Auswahl einer Aktion mit der Maus.

## <a name="insights"></a>Einblicke

Der Bereich **"Insights"** zeigt die drei wichtigsten Energieverbraucher in den Kategorien CPU und Netzwerk an. Diese Elemente verbrauchen im Vergleich zu allen Microsoft Managed Desktop Bereitstellungen eine überdurchschnittliche Energie. Die Anzeigeressource wird nicht angezeigt, da sie stark von der Gerätenutzungszeit und den Einstellungen für die Bildschirmhelligkeit abhängt. 

Wählen Sie die Einträge in der Spalte **"Details"** aus, um weitere Informationen zu erhalten.

## <a name="battery-optimization"></a>Optimierung des Akkus

Windows 10 bietet zahlreiche [Geräteeinstellungen,](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) um den Stromverbrauch zu verbessern und die Akkulaufzeit Ihrer Microsoft Managed Desktop Geräte zu erhöhen. Einige dieser Einstellungen können andere Windows Funktionen verringern. Daher müssen Sie auch andere Faktoren wie die Rolle des Geräts in Ihrer Organisation berücksichtigen. Windows Unterstützung verwaltet eine Liste dieser [Tipps zum Stromsparen.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

Benutzer können einige Einstellungen selbst anpassen, ohne dass administratoreigene Rechte oder Unterstützung erforderlich sind. Andere Einstellungen erfordern Unterstützung durch den IT-Administrator Ihrer Organisation.
