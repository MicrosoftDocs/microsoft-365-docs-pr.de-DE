---
title: Voraussetzungen für Microsoft 365 Defender
description: Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für Microsoft 365 Defender.
keywords: Anforderungen, Voraussetzungen, Hardware, Software, Browser, MTP, M365, Lizenz, E5, A5, EMS, kaufen
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844776"
---
# <a name="microsoft-365-defender-prerequisites"></a>Voraussetzungen für Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Erfahren Sie mehr über Lizenzierung und andere Anforderungen für die Einrichtung und Verwendung von [Microsoft 365 Defender](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Durch diese Lizenzen erhalten Sie ohne zusätzliche Kosten Zugriff auf Microsoft 365 Defender-Funktionen im Microsoft 365 Security Center:

- Microsoft 365 E5 oder A5
- Microsoft 365 E5 Sicherheit oder a5-Sicherheit
- Windows 10 Enterprise E5 oder A5
- Enterprise Mobility + Security (EMS) E5 oder A5 
- Office 365 E5 oder A5
- Microsoft Defender für Endpunkt
- Microsoft Defender für Identity 
- Microsoft Cloud App-Sicherheit
- Verteidiger für Office 365 (Plan 2)

> [!NOTE]
> Testlizenzen für Office 365 bieten derzeit keinen Zugriff auf Microsoft 365 Defender.

Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Sie haben noch keine Lizenz? [Testen oder Kaufen eines Microsoft 365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Überprüfen vorhandener Lizenzen
Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen. Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.

>[!NOTE]
> Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können. Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren. Eine Liste der Rollen, die für die Verwendung von Microsoft 365 Defender erforderlich sind, sowie Informationen darüber, wie der Zugriff auf Daten reguliert wird, finden Sie unter [Managing Access to Microsoft 365 Defender](mtp-permissions.md).

## <a name="browser-requirements"></a>Browseranforderungen
Greifen Sie auf Microsoft 365 Defender im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Verfügbarkeit für US gcc, gcc High und andere US-Regierungsinstitutionen
Derzeit steht Microsoft 365 Defender *nicht* für Folgendes zur Verfügung:
- US Government Community Cloud (gcc)
- US Government Community Cloud High (gcc hoch)
- US-Verteidigungsministerium
- Alle US-Regierungsinstitutionen mit kommerziellen Lizenzen

## <a name="related-topics"></a>Verwandte Themen
- [Microsoft 365 Defender (Übersicht)](microsoft-threat-protection.md)
- [Aktivieren von Microsoft 365 Defender](mtp-enable.md)
- [Verwalten von Zugriff und Berechtigungen](mtp-permissions.md)
