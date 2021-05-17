---
title: Behandeln von Microsoft 365 von Problemen mit dem Defender-Dienst
description: Suchen von Lösungen und Problemumgehungen zu bekannten problemen Microsoft 365 Defender
keywords: Problembehandlung Microsoft 365 Defender, Problembehandlung, Microsoft Defender for Identity, Probleme, Add-On, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933397"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Behandeln von Microsoft 365 von Problemen mit dem Defender-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft 365 auftreten können.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Inhalt von Defender Microsoft 365 nicht angezeigt

Wenn im Navigationsbereich keine Funktionen wie Vorfälle, Aktionscenter oder Suche in Ihrem Portal angezeigt werden, müssen Sie überprüfen, ob Ihr Mandant über die entsprechenden Lizenzen verfügt.

Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity-Warnungen werden nicht in den Microsoft 365 Defender-Vorfällen angezeigt

Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber im Rahmen von Microsoft 365 Defender-Vorfällen keine Defender for Identity-Warnungen angezeigt werden, müssen Sie sicherstellen, dass die Integration von Microsoft Cloud App Security und Defender for Identity aktiviert ist.

Weitere Informationen finden Sie unter [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Wo befindet sich die Einstellungsseite zum Aktivieren des Diensts?

Um Defender Microsoft 365 zu aktivieren, greifen **Sie Einstellungen** navigationsbereich im Microsoft 365 auf die Microsoft 365 zu. Dieses Navigationselement ist nur sichtbar, wenn Sie über die erforderlichen [Berechtigungen und Lizenzen verfügen.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Wie erstelle ich eine Ausnahme für meine Datei/URL?

Ein falsch positives Ergebnis ist eine Datei oder URL, die als schädlich erkannt wird, aber keine Bedrohung darstellt. Sie können Indikatoren erstellen und Ausschlüsse definieren, um die Blockierung zu aufheben und bestimmte Dateien/URLs zu erlauben. Weitere [Informationen finden Sie unter Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


