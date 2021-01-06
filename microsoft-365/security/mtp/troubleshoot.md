---
title: Beheben von Problemen mit Microsoft 365 Defender-Diensten
description: Suchen von Lösungen und umgehen mit bekannten Problemen mit Microsoft 365 Defender
keywords: Problembehandlung beim Microsoft-Bedrohungsschutz, Problembehandlung, Azure ATP, Probleme, Add-on, Seite "Einstellungen"
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760458"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Beheben von Problemen mit Microsoft 365 Defender-Diensten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft 365 Defender-Diensts auftreten können.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender-Inhalt wird nicht angezeigt

Wenn im Navigationsbereich keine Funktionen wie die Vorfälle, das Wartungs Center oder die Suche in Ihrem Portal angezeigt werden, müssen Sie sicherstellen, dass Ihr Mandant über die entsprechenden Lizenzen verfügt.

Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender für Identitäts Warnungen wird nicht in den Microsoft 365 Defender-Vorfällen angezeigt

Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber Defender für Identitäts Warnungen als Teil von Microsoft 365 Defender-Vorfällen nicht angezeigt wird, müssen Sie sicherstellen, dass die Microsoft Cloud App Security and Defender for Identity Integration aktiviert ist.

Weitere Informationen finden Sie unter [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Wo befindet sich die Seite "Einstellungen" für die Aktivierung des Diensts?

Um Microsoft 365 Defender zu aktivieren, greifen Sie auf **Einstellungen** im Navigationsbereich im Microsoft 365 Security Center zu. Dieses Navigationselement ist nur sichtbar, wenn Sie über die [erforderlichen Berechtigungen und Lizenzen](mtp-enable.md#check-license-eligibility-and-required-permissions)verfügen.
