---
title: Voraussetzungen für Microsoft 365 Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen und andere Konfigurationseinstellungen für Microsoft 365 Defender
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz, E5, A5, EMS, Kauf
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
ms.openlocfilehash: afa5cd42545eddafb1d0ec1a6d88eb0903e07820
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454551"
---
# <a name="microsoft-365-defender-prerequisites"></a>Voraussetzungen für Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Erfahren Sie mehr über die Lizenzierung und andere Anforderungen für die Bereitstellung und Verwendung von [Microsoft 365 Defender](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Jede dieser Lizenzen ermöglicht Ihnen den Zugriff auf Microsoft 365 Defender-Features im Microsoft 365 Security Center ohne zusätzliche Kosten:

- Microsoft 365 E5 oder A5
- Microsoft 365 E5 Security oder A5 Security
- Windows 10 Enterprise E5 oder A5
- Enterprise Mobility + Security (EMS) E5 oder A5 
- Office 365 E5 oder A5
- Microsoft Defender für Endpunkt
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Microsoft Defender für Office 365 (Plan 2)

Weitere Informationen finden Sie [in den Microsoft 365 Enterprise-Dienstplänen.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Sie haben noch keine Lizenz? [Testen oder Kaufen eines Microsoft 365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Überprüfen vorhandener Lizenzen
Wechseln Sie zu Microsoft 365 Admin Center ([admin.microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen zu sehen. Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.

>[!NOTE]
> Sie müssen entweder der  Rolle "Abrechnungsadministrator" oder **"Globaler** [Leser" in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen werden, um Lizenzinformationen anzeigen zu können. Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Sie müssen ein globaler Administrator **oder** **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender aktivieren zu können. Eine Liste der für die Verwendung von Microsoft 365 Defender erforderlichen Rollen und Informationen zur Regulierung des Zugriffs auf Daten finden Sie unter Verwalten des Zugriffs auf [Microsoft 365 Defender](mtp-permissions.md).

## <a name="browser-requirements"></a>Browseranforderungen
Zugreifen auf Microsoft 365 Defender im Microsoft 365 Security Center mithilfe von Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-kompatiblen Webbrowser.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Verfügbarkeit für us GCC, GCC High und andere US Government Institutions
Derzeit steht Microsoft 365 Defender *nicht* zur Verfügung für:
- US Government Community Cloud (GCC)
- US Government Community Cloud High (GCC High)
- US Department of Defense
- Alle US-Behörden mit kommerziellen Lizenzen

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivieren von Microsoft 365 Defender](mtp-enable.md)
- [Verwalten von Zugriff und Berechtigungen](mtp-permissions.md)
