---
title: Konfigurieren der Integration von Microsoft Cloud App Security
ms.reviewer: ''
description: Erfahren Sie, wie Sie die Einstellungen aktivieren, um die Integration von Microsoft Defender für Endpunkt in Microsoft Cloud App Security zu aktivieren.
keywords: Cloud, App, Sicherheit, Einstellungen, Integration, Ermittlung, Bericht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844754"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Konfigurieren Microsoft Cloud App Security in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Um von Microsoft Defender für Endpunkt Cloud App Discovery-Signalen zu profitieren, aktivieren Sie Microsoft Cloud App Security Integration.

>[!NOTE]
>Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten verfügbar, auf denen Windows 10 ausgeführt wird. Version 1709 (BS Build 16299.1085 mit [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, Version 1803 (Os Build 17134.704 mit [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, Version 1809 (Os Build 17763.379 mit [KB4489899)](https://support.microsoft.com/help/4489899)oder höher Windows 10 Versionen.

> Informationen zur detaillierten Integration von Microsoft Defender für Endpunkt mit Microsoft Cloud App Security finden Sie unter Microsoft Defender für [Endpunktintegration mit](/cloud-app-security/mde-integration) Microsoft Cloud App Security. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Aktivieren Microsoft Cloud App Security in Microsoft Defender für Endpunkt

1. Wählen Sie im Navigationsbereich **"Einstellungen einrichten**  >  **Erweiterte Features"** aus.
2. Wählen Sie **Microsoft Cloud App Security** aus, und schalten Sie die Umschaltfläche auf **"Ein".**
3. Klicken Sie auf **"Einstellungen speichern".**

Nach der Aktivierung beginnt Microsoft Defender für Endpunkt sofort mit der Weiterleitung von Erkennungssignalen an Cloud App Security.

## <a name="view-the-data-collected"></a>Anzeigen der gesammelten Daten

Informationen zum Anzeigen und Zugreifen auf Microsoft Defender für Endpunktdaten in Microsoft Cloud Apps Security finden Sie unter [Untersuchen von Geräten in Cloud App Security.](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)


Weitere Informationen zur Cloudermittlung finden Sie unter [Arbeiten mit ermittelten Apps.](/cloud-app-security/discovered-apps)

Wenn Sie Microsoft Cloud App Security ausprobieren möchten, lesen Sie [Microsoft Cloud App Security Testversion.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)

## <a name="related-topic"></a>Verwandtes Thema
- [Microsoft Cloud App Security Integration](microsoft-cloud-app-security-integration.md)
