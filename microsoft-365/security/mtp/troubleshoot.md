---
title: Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst
description: Suchen von Lösungen und Arbeiten mit bekannten Microsoft 365 Defender-Problemen
keywords: Problembehandlung bei Microsoft Threat Protection, Problembehandlung, Azure ATP, Probleme, Add-On, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925718"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

In diesem Abschnitt werden Probleme behandelt, die auftreten können, wenn Sie den Microsoft 365 Defender-Dienst verwenden.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 -Defender-Inhalte werden nicht angezeigt

Wenn im Navigationsbereich keine Funktionen wie Vorfälle, Das Aktionscenter oder die Suche in Ihrem Portal angezeigt werden, müssen Sie überprüfen, ob Ihr Mandant über die entsprechenden Lizenzen verfügt.

Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity-Warnungen werden in den Microsoft 365 Defender-Vorfällen nicht angezeigt

Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber im Rahmen von Microsoft 365 Defender-Vorfällen keine Defender for Identity-Warnungen angezeigt werden, müssen Sie sicherstellen, dass die Integration von Microsoft Cloud App Security und Defender for Identity aktiviert ist.

Weitere Informationen finden Sie unter [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Wo befindet sich die Einstellungsseite zum Aktivieren des Diensts?

Um Microsoft 365 Defender  zu aktivieren, greifen Sie über den Navigationsbereich im Microsoft 365 Security Center auf die Einstellungen zu. Dieses Navigationselement ist nur sichtbar, wenn Sie über die erforderlichen [Berechtigungen und Lizenzen verfügen.](mtp-enable.md#check-license-eligibility-and-required-permissions)
