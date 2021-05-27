---
title: Konfigurieren Microsoft Defender Antivirus mithilfe Microsoft Endpoint Manager
description: Verwenden Microsoft Endpoint Manager und Microsoft Intune zum Konfigurieren von Microsoft Defender AV und Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683751"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Verwenden Microsoft Endpoint Manager zum Konfigurieren und Verwalten von Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Sie können die [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) zum Konfigurieren von Microsoft Defender Antivirus verwenden. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Configuration Manager](/mem/configmgr/core/understand/introduction) sind jetzt Teil Endpoint Manager.  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Konfigurieren Microsoft Defender Antivirus Scans in Endpoint Manager

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Navigieren Sie zu **Endpunktsicherheit**.

3. Wählen **Sie unter Verwalten** die Option Antivirus **aus.**

4. Wählen Sie ihre Microsoft Defender Antivirus aus. 

5. Wählen Sie unter **Verwalten** die Option **Eigenschaften** aus.

6. Wählen Sie direkt neben **Konfigurationseinstellungen** die Option **Bearbeiten** aus.

7. Erweitern Sie den **Abschnitt Scan,** und überprüfen oder bearbeiten Sie Die Scaneinstellungen.

8. Wählen Sie **Überprüfen + Speichern aus.**


> [!TIP]
> Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).


## <a name="related-articles"></a>Verwandte Artikel

- [Referenzartikel für Verwaltungs- und Konfigurationstools](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)