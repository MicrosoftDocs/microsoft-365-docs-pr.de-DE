---
title: Gerätenamen
description: Verwalten Microsoft Managed Desktop Gerätenamen
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893890"
---
# <a name="device-names"></a>Gerätenamen

Microsoft Managed Desktop verwendet Windows Autopilot, Azure Active Directory und Microsoft Intune. Damit diese Dienste nahtlos zusammenarbeiten können, benötigen Geräte konsistente, standardisierte Namen. Microsoft Managed Desktop wendet ein standardisiertes Namensformat (vom Format *MMD-%RAND11)* an, wenn Geräte registriert sind. Windows Autopilot weist diese Namen zu. Weitere Informationen zu Autopilot finden Sie unter [First-run experience with Autopilot und the Enrollment Status Page](../get-started/esp-first-run.md).

## <a name="automated-name-changes"></a>Automatische Namensänderungen

Wenn ein Gerät später umbenannt wird, Microsoft Managed Desktop wird es automatisch in einen neuen Namen im standardisierten Format umbenannt. Dieser Vorgang erfolgt alle vier Stunden. Die Namensänderung erfolgt beim nächsten Neustart des Geräts durch den Benutzer.

> [!IMPORTANT]
> Wenn Ihre Umgebung von bestimmten Gerätenamen abhängt (z. B. zur Unterstützung einer bestimmten Netzwerkkonfiguration), sollten Sie optionen untersuchen, um diese Abhängigkeit zu entfernen, bevor Sie sich für Microsoft Managed Desktop. Wenn Sie die Namensabhängigkeit behalten müssen, können Sie eine Anforderung über das [Administratorportal](../working-with-managed-desktop/admin-support.md) senden, um die Umbenennungsfunktion zu deaktivieren und das gewünschte Namensformat zu verwenden.