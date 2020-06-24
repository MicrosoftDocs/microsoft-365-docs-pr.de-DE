---
title: Voraussetzungen für Microsoft Threat Protection
description: Hier lernen Sie die Lizenz-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für Microsoft Threat Protection kennen.
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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844906"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Voraussetzungen für Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

Erfahren Sie mehr über Lizenzierung und andere Anforderungen für die Einrichtung und Verwendung von [Microsoft Threat Protection](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Durch diese Lizenzen erhalten Sie ohne zusätzliche Kosten Zugriff auf Microsoft Threat Protection-Funktionen im Microsoft 365 Security Center:

- Microsoft 365 E5 oder A5
- Microsoft 365 E5 Sicherheit oder a5-Sicherheit
- Windows 10 Enterprise E5 oder A5
- Enterprise Mobility + Security (EMS) E5 oder A5 
- Office 365 E5 oder A5
- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection 
- Microsoft Cloud App-Sicherheit
- Office 365 Advanced Threat Protection (Plan 2)

> [!NOTE]
> Testlizenzen für Office 365 bieten derzeit keinen Zugriff auf Microsoft Threat Protection.

Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Sie haben noch keine Lizenz? [Testen oder Kaufen eines Microsoft 365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Überprüfen vorhandener Lizenzen
Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen. Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.

>[!NOTE]
> Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können. Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.

## <a name="required-permissions"></a>Erforderliche Berechtigungen
Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft Threat Protection zu aktivieren. Eine Liste der Rollen, die für die Verwendung von Microsoft Threat Protection erforderlich sind, sowie Informationen darüber, wie der Zugriff auf Daten reguliert wird, finden Sie unter [Managing Access to Microsoft Threat Protection](mtp-permissions.md).

## <a name="browser-requirements"></a>Browseranforderungen
Greifen Sie auf Microsoft Threat Protection im Microsoft 365 Security Center mit Microsoft Edge, Internet Explorer 11 oder einem beliebigen HTML 5-konformen Webbrowser zu.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Verfügbarkeit für US gcc, gcc High und andere US-Regierungsinstitutionen
Derzeit steht Microsoft Threat Protection *nicht* zur Verfügung:
- US Government Community Cloud (gcc)
- US Government Community Cloud High (gcc hoch)
- US-Verteidigungsministerium
- Alle US-Regierungsinstitutionen mit kommerziellen Lizenzen

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
- [Aktivieren von Microsoft Threat Protection](mtp-enable.md)
- [Verwalten von Zugriff und Berechtigungen](mtp-permissions.md)
