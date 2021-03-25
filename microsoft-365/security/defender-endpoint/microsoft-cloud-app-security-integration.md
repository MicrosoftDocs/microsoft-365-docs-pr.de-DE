---
title: Übersicht über die Integration von Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender for Endpoint integriert sich in Cloud App Security, indem alle Cloud-App-Netzwerkaktivitäten weitergeleitet werden.
keywords: Cloud, App, Netzwerk, Sichtbarkeit, Nutzung
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185599"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Übersicht über Microsoft Cloud App Security in Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) ist eine umfassende Lösung, die Einblicke in Cloud-Apps und -Dienste bietet, indem Sie den Zugriff auf Cloud-Apps steuern und einschränken und gleichzeitig Complianceanforderungen für in der Cloud gespeicherte Daten durchsetzen können. Weitere Informationen finden Sie unter [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security auf](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) Geräten mit Windows 10, Version 1809 oder höher, verfügbar.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Integration von Microsoft Defender for Endpoint und Cloud App Security 

Die Cloud App Security-Ermittlung basiert auf Clouddatenverkehrsprotokollen, die von der Unternehmensfirewall und Proxyservern an sie weitergeleitet werden. Microsoft Defender for Endpoint integriert sich in Cloud App Security, indem alle Cloud-App-Netzwerkaktivitäten gesammelt und weitergeleitet werden, was eine unvergleichliche Sichtbarkeit für die Cloud-App-Nutzung bietet. Die Überwachungsfunktionalität ist in das Gerät integrierte und bietet eine vollständige Abdeckung der Netzwerkaktivität.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


Die Integration bietet die folgenden wichtigen Verbesserungen an der vorhandenen Cloud App Security-Erkennung: 

- Überall verfügbar– Da die Netzwerkaktivität direkt vom Endpunkt erfasst wird, ist sie überall verfügbar, wo sich das Gerät befindet, im oder aus dem Unternehmensnetzwerk, da es nicht mehr vom Datenverkehr abhängig ist, der über die Unternehmensfirewall oder proxyserver geleitet wird. 

- Keine Konfiguration erforderlich– Für die Weiterleitung von Clouddatenverkehrsprotokollen an Cloud App Security ist eine Firewall- und Proxyserverkonfiguration erforderlich. Bei der Integration von Defender for Endpoint und Cloud App Security ist keine Konfiguration erforderlich. Schalten Sie es einfach in den Microsoft Defender Security Center-Einstellungen ein, und Sie können losgehen. 

- Gerätekontext – Clouddatenverkehrsprotokolle haben keinen Gerätekontext. Die Netzwerkaktivität von Defender for Endpoint wird mit dem Gerätekontext (auf welches Gerät auf die Cloud-App zugegriffen hat) gemeldet, damit Sie genau verstehen können, wo (Gerät) die Netzwerkaktivität stattgefunden hat, und nicht nur, wer (Benutzer) sie ausgeführt hat. 

Weitere Informationen zur Clouderkennung finden Sie unter [Arbeiten mit ermittelten Apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).

## <a name="related-topic"></a>Verwandtes Thema

- [Konfigurieren der Integration von Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
