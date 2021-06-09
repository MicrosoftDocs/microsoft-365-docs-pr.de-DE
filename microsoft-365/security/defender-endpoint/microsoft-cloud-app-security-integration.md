---
title: Übersicht über Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender für Endpunkt lässt sich in Cloud App Security integrieren, indem alle Cloud-App-Netzwerkaktivitäten weitergeleitet werden.
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
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844742"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>übersicht über Microsoft Cloud App Security in Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) ist eine umfassende Lösung, die Einblicke in Cloud-Apps und -Dienste bietet, indem Sie den Zugriff auf Cloud-Apps steuern und einschränken und gleichzeitig Complianceanforderungen für in der Cloud gespeicherte Daten erzwingen können. Weitere Informationen finden Sie unter [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten mit Windows 10 Version 1809 oder höher verfügbar.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Integration von Microsoft Defender für Endpunkt und Cloud App Security 

Cloud App Security Ermittlung basiert auf Clouddatenverkehrsprotokollen, die von Unternehmensfirewall- und Proxyservern an sie weitergeleitet werden. Microsoft Defender für Endpunkt lässt sich in Cloud App Security integrieren, indem alle Cloud-App-Netzwerkaktivitäten gesammelt und weitergeleitet werden, sodass die Cloud-App-Nutzung sichtbar wird. Die Überwachungsfunktionalität ist in das Gerät integriert und bietet eine vollständige Abdeckung der Netzwerkaktivität.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


Die Integration bietet die folgenden wesentlichen Verbesserungen an der vorhandenen Cloud App Security Ermittlung: 

- Überall verfügbar– Da die Netzwerkaktivität direkt vom Endpunkt erfasst wird, ist sie überall verfügbar, wo sich das Gerät im oder außerhalb des Unternehmensnetzwerks befindet, da es nicht mehr vom Datenverkehr abhängt, der über die Unternehmensfirewall oder Proxyserver geleitet wird. 

- Funktioniert sofort einsatzbereit, keine Konfiguration erforderlich – Das Weiterleiten von Clouddatenverkehrsprotokollen an Cloud App Security erfordert eine Firewall- und Proxyserverkonfiguration. Bei der Integration von Defender für Endpunkt und Cloud App Security ist keine Konfiguration erforderlich. Schalten Sie es einfach in Microsoft Defender Security Center Einstellungen ein, und Sie können loslegen. 

- Gerätekontext: Clouddatenverkehrsprotokollen fehlt der Gerätekontext. Defender für Endpunkt-Netzwerkaktivität wird mit dem Gerätekontext gemeldet (welches Gerät auf die Cloud-App zugegriffen hat), sodass Sie genau verstehen können, wo (Gerät) die Netzwerkaktivität stattgefunden hat, zusätzlich zu dem, wer (Benutzer) sie ausgeführt hat. 

Weitere Informationen zur Cloudermittlung finden Sie unter [Arbeiten mit ermittelten Apps.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Verwandtes Thema

- [Konfigurieren der Integration von Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
