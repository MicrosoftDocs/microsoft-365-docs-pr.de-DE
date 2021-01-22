---
title: Voraussetzungen für Microsoft 365 Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für Microsoft 365 Defender
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz, E5, A5, EMS, kaufen
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
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930090"
---
# <a name="microsoft-365-defender-prerequisites"></a>Voraussetzungen für Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Erfahren Sie mehr über Lizenzierung und andere Anforderungen für die Bereitstellung und Verwendung [von Microsoft 365 Defender.](microsoft-threat-protection.md)

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Jede dieser Lizenzen ermöglicht Ihnen den Zugriff auf Microsoft 365 Defender-Features im Microsoft 365 Security Center ohne zusätzliche Kosten:

- Microsoft 365 E5 oder A5
- Microsoft 365 E5 Security oder A5 Security
- Windows 10 Enterprise E5 oder A5
- Enterprise Mobility + Security (EMS) E5 oder A5 
- Office 365 E5 oder A5
- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity 
- Microsoft Cloud App-Sicherheit
- Defender für Office 365 (Plan 2)

> [!NOTE]
> Testlizenzen für Office 365 bieten derzeit keinen Zugriff auf Microsoft 365 Defender.

Weitere Informationen finden Sie [in den Microsoft 365 Enterprise-Serviceplänen.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Sie haben noch keine Lizenz? [Testen oder Kaufen eines Microsoft 365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Überprüfen vorhandener Lizenzen
Wechseln Sie zum Microsoft 365 Admin Center ([admin.microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen zu sehen. Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.

>[!NOTE]
> Sie müssen entweder dem  Abrechnungsadministrator oder der Rolle des globalen **Lesers** [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können. Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Sie müssen ein globaler **Administrator oder** ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren. Eine Liste der Rollen, die für die Verwendung von Microsoft 365 Defender erforderlich sind, sowie Informationen dazu, wie der Zugriff auf Daten reguliert ist, finden Sie unter Verwaltung des Zugriffs auf [Microsoft 365 Defender.](mtp-permissions.md)

## <a name="browser-requirements"></a>Browseranforderungen
Greifen Sie auf Microsoft 365 Defender im Microsoft 365 Security Center mithilfe von Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-kompatiblen Webbrowser zu.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Verfügbarkeit für GCC, GCC High und andere US-Regierungseinrichtungen
Derzeit ist Microsoft 365 Defender *nicht* verfügbar für:
- US Government Community Cloud (GCC)
- US Government Community Cloud High (GCC High)
- US-Verteidigungsministeriums
- Alle US-Regierungseinrichtungen mit kommerziellen Lizenzen

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivieren von Microsoft 365 Defender](mtp-enable.md)
- [Verwalten von Zugriff und Berechtigungen](mtp-permissions.md)
