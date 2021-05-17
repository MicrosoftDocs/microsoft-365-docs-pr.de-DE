---
title: Gerätewert zuweisen – Bedrohungs- und Sicherheitsrisikomanagement
description: Erfahren Sie, wie Sie einem Gerät einen niedrigen, normalen oder hohen Wert zuweisen, um zwischen den Ressourcenprioritäten zu unterscheiden.
keywords: Microsoft Defender for Endpoint-Gerätewert, Bedrohungs- und Sicherheitsrisikomanagement Gerätewert, hochwertige Geräte, Gerätewert-Belichtungsergebnis
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935197"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>Gerätewert zuweisen – Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Wenn Sie den Wert eines Geräts definieren, können Sie zwischen den Ressourcenprioritäten unterscheiden. Der Gerätewert wird verwendet, um die Risikobereitschaft eines einzelnen Vermögenswerts in die Berechnung Bedrohungs- und Sicherheitsrisikomanagement Risikos zu integrieren. Geräte, die als "hoher Wert" zugewiesen sind, erhalten mehr Gewichtung.

Sie können auch die [Set Device Value API verwenden.](set-device-value.md)

Gerätewertoptionen:

- Niedrig
- Normal (Standard)
- Hoch

Beispiele für Geräte, denen ein hoher Wert zugewiesen werden sollte:

- Domänencontroller, Active Directory
- Mit dem Internet zu verbindende Geräte
- VIP-Geräte
- Geräte, die interne/externe Produktionsdienste hosten

## <a name="choose-device-value"></a>Gerätewert auswählen

1. Navigieren Sie zu einer beliebigen Geräteseite, der einfachste Ort ist aus dem Gerätebestand.

2. Wählen **Sie Gerätewert** aus drei Punkten neben der Aktionsleiste am oberen Rand der Seite aus.

    ![Beispiel für das Dropdownmenü des Gerätewerts.](images/tvm-device-value-dropdown.png)

3. Ein Flyout wird mit dem aktuellen Gerätewert und dem, was es bedeutet, angezeigt. Überprüfen Sie den Wert des Geräts, und wählen Sie das Gerät aus, das am besten zu Ihrem Gerät passt.
![Beispiel für das Flyout des Gerätewerts.](images/tvm-device-value-flyout.png)

## <a name="how-device-value-impacts-your-exposure-score"></a>Auswirkungen des Gerätewerts auf ihre Belichtungsergebnis

Die Belichtungsnote ist ein gewichteter Durchschnitt auf allen Geräten. Wenn Sie Gerätegruppen haben, können Sie die Bewertung auch nach Gerätegruppe filtern.

- Normale Geräte haben eine Gewichtung von 1
- Geräte mit geringem Wert haben eine Gewichtung von 0,75
- Hochwertige Geräte haben eine Gewichtung von NumberOfAssets /10.
    - Wenn Sie über 100 Geräte verfügen, hat jedes hochwertige Gerät eine Gewichtung von 10 (100/10)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen](next-gen-threat-and-vuln-mgt.md)
- [Belichtungsergebnis](tvm-exposure-score.md)
- [APIs](next-gen-threat-and-vuln-mgt.md#apis)