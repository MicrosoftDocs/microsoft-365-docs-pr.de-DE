---
title: Behandeln von Problemen mit Microsoft Threat Protection-Diensten
description: Suchen nach Lösungen und Umgehen bekannter Probleme mit Microsoft Threat Protection
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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661981"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Behandeln von Problemen mit Microsoft Threat Protection-Diensten

**Gilt für:**
- Microsoft Threat Protection

Dieser Abschnitt bezieht sich auf Probleme, die bei Verwendung des Microsoft Threat Protection-Diensts auftreten können.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Microsoft Threat Protection-Inhalt wird nicht angezeigt
Wenn im Navigationsbereich keine Funktionen wie die Vorfälle, das Wartungs Center oder die Suche in Ihrem Portal angezeigt werden, müssen Sie sicherstellen, dass Ihr Mandant über die entsprechenden Lizenzen verfügt. 

Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Azure ATP-Warnungen werden in den Microsoft Threat Protection-Vorfällen nicht angezeigt
Wenn Sie Azure ATP in Ihrer Umgebung bereitgestellt haben, in Microsoft Threat Protection-Vorfällen aber keine Azure ATP-Warnungen angezeigt werden, müssen Sie sicherstellen, dass Microsoft Cloud App Security und Azure ATP-Integration aktiviert sind. 

Weitere Informationen finden Sie unter [Azure ATP-Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Ist Microsoft Threat Protection für US Government Community Cloud (GCC) oder GCC High verfügbar?
Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Wo befindet sich die Seite "Einstellungen" für die Aktivierung des Diensts?
Um Microsoft Threat Protection zu aktivieren, greifen Sie auf **Einstellungen** im Navigationsbereich im Microsoft 365 Security Center zu. Dieses Navigationselement ist nur sichtbar, wenn Sie über die [erforderlichen Berechtigungen und Lizenzen](mtp-enable.md#check-license-eligibility-and-required-permissions)verfügen.

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>Kann ich anstelle der erforderlichen E5-Lizenzen ein Add-on verwenden?
Derzeit gibt es keine Add-ons für Microsoft Threat Protection. [Siehe Lizenzierungsanforderungen](prerequisites.md) 

