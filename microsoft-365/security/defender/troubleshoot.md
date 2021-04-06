---
title: Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst
description: Suchen von Lösungen und Problemumgehungen für bekannte Microsoft 365 Defender-Probleme
keywords: Problembehandlung für Microsoft Threat Protection, Problembehandlung, Azure ATP, Probleme, Add-On, Einstellungsseite
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
ms.openlocfilehash: a2cd27bf7bf8b1c4931b9d768f3a6b5e5f2a0d93
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592036"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft 365 Defender-Diensts auftreten können.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender-Inhalte werden nicht angezeigt

Wenn im Navigationsbereich keine Funktionen wie Vorfälle, Aktionscenter oder Suche in Ihrem Portal angezeigt werden, müssen Sie überprüfen, ob Ihr Mandant über die entsprechenden Lizenzen verfügt.

Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity-Warnungen werden in den Microsoft 365 Defender-Vorfällen nicht angezeigt

Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber im Rahmen von Microsoft 365 Defender-Vorfällen keine Defender for Identity-Warnungen angezeigt werden, müssen Sie sicherstellen, dass die Integration von Microsoft Cloud App Security und Defender for Identity aktiviert ist.

Weitere Informationen finden Sie unter [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Wo befindet sich die Einstellungsseite zum Aktivieren des Diensts?

Um Microsoft 365 Defender  zu aktivieren, greifen Sie über den Navigationsbereich im Microsoft 365 Security Center auf Einstellungen zu. Dieses Navigationselement ist nur sichtbar, wenn Sie über die erforderlichen [Berechtigungen und Lizenzen verfügen.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Wie erstelle ich eine Ausnahme für meine Datei/URL?

Ein falsch positives Ergebnis ist eine Datei oder URL, die als schädlich erkannt wird, aber keine Bedrohung darstellt. Sie können Indikatoren erstellen und Ausschlüsse definieren, um die Blockierung zu aufheben und bestimmte Dateien/URLs zu erlauben. Weitere [Informationen finden Sie unter Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


