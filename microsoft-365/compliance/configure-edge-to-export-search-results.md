---
title: Verwenden des eDiscovery-Exporttools in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Sie müssen die ClickOnce aktivieren, um die neueste Version von Microsoft Edge zum Herunterladen von Suchergebnissen aus der Inhaltssuche und eDiscovery im Security and Compliance Center zu verwenden.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546819"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Verwenden des eDiscovery-Exporttools in Microsoft Edge

Als Ergebnis der letzten Änderungen an der neuesten Version von Microsoft Edge ist ClickOnce unterstützung standardmäßig nicht mehr aktiviert. Um weiterhin das eDiscovery-Exporttool zum Herunterladen von Inhaltssuche- oder eDiscovery-Suchergebnissen zu verwenden, müssen Sie [entweder Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) verwenden oder ClickOnce-Unterstützung in der neuesten Version von Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Aktivieren ClickOnce Unterstützung in Microsoft Edge

1. Wechseln Microsoft Edge zu **edge://flags/#edge-click-once**.

2. Wenn der vorhandene Wert in der Dropdownliste auf **Standard** oder **Deaktiviert** festgelegt ist, ändern Sie ihn in **Aktiviert**.

   ![Auswählen von Aktiviert in der Dropdownliste](../media/ClickOnceimage1.png)

3. Scrollen Sie nach unten im Browserfenster, und klicken Sie **auf Neu starten,** um Edge neu zu starten.

   ![Klicken Sie auf Neustart](../media/ClickOnceimage2.png)

**Hinweis:** Organisationen können Gruppenrichtlinien verwenden, um ClickOnce zu deaktivieren. Um zu überprüfen, ob eine Organisationsrichtlinie für ClickOnce ist, wechseln Sie **zu edge://policy**. Der folgende Screenshot zeigt, ClickOnce in der gesamten Organisation aktiviert ist. Wenn dieser Richtlinienwert auf **false festgelegt** ist, müssen Sie sich an einen Administrator in Ihrer Organisation wenden.

![Liste der Edgeorganisationsrichtlinien](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Installieren und Ausführen des eDiscovery-Exporttools

1. Klicken **Sie auf der** Flyoutseite eines Exports in der Inhaltssuche oder in einem eDiscovery-Fall auf Ergebnisse herunterladen.

   ![Klicken Sie auf der Flyoutseite auf Ergebnisse herunterladen, um Suchergebnisse herunterzuladen.](../media/ClickOnceExport1.png)

2. Sie werden aufgefordert, eine Bestätigung zum Starten des Tools zu erhalten, klicken Sie auf **Öffnen**.

   ![Klicken Sie auf Öffnen, um das eDiscovery-Exporttool zu starten.](../media/ClickOnceimage4.png)

   Wenn das eDiscovery-Exporttool nicht installiert ist, werden Sie mit einer Sicherheitswarnung aufgefordert. 

   ![Klicken Sie auf Installieren, um das eDiscovery-Exporttool zu installieren.](../media/ClickOnceimage5.png)

3. Klicken Sie auf **Installieren**. Nach der Installation wird das Exporttool automatisch gestartet.

Weitere Informationen finden Sie in den folgenden Themen:

- [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)

- [Aktivieren von Experimentflags in Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
