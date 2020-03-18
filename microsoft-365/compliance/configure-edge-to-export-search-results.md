---
title: Verwenden des Office 365 eDiscovery-Export Tools in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Sie müssen die ClickOnce-Unterstützung aktivieren, um die neueste Version von Microsoft Edge zum Herunterladen von Suchergebnissen aus der Inhaltssuche und von eDiscovery im Security and Compliance Center zu verwenden.
ms.openlocfilehash: 80924b124521b24ffabf1e0273802265cd715500
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710344"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Verwenden des Office 365 eDiscovery-Export Tools in Microsoft Edge

Aufgrund der letzten Änderungen an der neuesten Version von Microsoft Edge ist die ClickOnce-Unterstützung standardmäßig nicht mehr aktiviert. Um das eDiscovery-Export Tool Microsoft Office 365 zum Herunterladen von Inhaltssuche oder eDiscovery-Suchergebnissen weiterhin zu verwenden, müssen Sie entweder [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) verwenden oder die ClickOnce-Unterstützung in der neuesten Version von Microsoft Edge aktivieren.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Aktivieren der ClickOnce-Unterstützung in Microsoft Edge

1. Wechseln Sie in Microsoft Edge zu **Edge://Flags/#Edge-Click-Once**.

2. Wenn der vorhandene Wert in der Dropdownliste auf **Standard** oder **deaktiviert** festgelegt ist, ändern Sie ihn in **aktiviert**.

   ![](../media/ClickOnceimage1.png)

3. Scrollen Sie nach unten zum Browserfenster, und klicken Sie auf **neu** starten, um Edge neu zu starten.

   ![](../media/ClickOnceimage2.png)

**Hinweis:** Organisationen können mithilfe von Gruppenrichtlinien die ClickOnce-Unterstützung deaktivieren. Um zu überprüfen, ob eine Organisationsrichtlinie für die ClickOnce-Unterstützung vorhanden ist, wechseln Sie zu **Edge://Policy**. Der folgende Screenshot zeigt, dass ClickOnce in der gesamten Organisation aktiviert ist. Wenn dieser Richtlinienwert auf **false**festgelegt ist, müssen Sie einen Administrator in Ihrer Organisation kontaktieren.

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Installieren und Ausführen des eDiscovery-Export Tools

1. Klicken Sie auf der Flyout-Seite eines Exports in Inhaltssuche oder eines eDiscovery-Falls auf " **Ergebnisse herunterladen** ".

   ![Klicken Sie auf der Flyout-Seite auf Download Ergebnisse, um Suchergebnisse herunterzuladen.](../media/ClickOnceExport1.png)

2. Sie werden mit einer Bestätigung aufgefordert, das Tool zu starten, indem Sie auf **Öffnen**klicken.

   ![Klicken Sie auf öffnen, um das eDiscovery-Export Tool zu starten](../media/ClickOnceimage4.png)

   Wenn das Microsoft Office-eDiscovery-Export Tool 365 nicht installiert ist, werden Sie mit einer Sicherheitswarnung aufgefordert, 

   ![Klicken Sie auf installieren, um das eDiscovery-Export Tool zu installieren](../media/ClickOnceimage5.png)

3. Klicken Sie auf **Installieren**. Nachdem die Installation erfolgt ist, wird das Export Tool automatisch gestartet.

Weitere Informationen hierzu finden Sie in den folgenden Themen:

- [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)

- [Aktivieren von testmarkierungen in Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
