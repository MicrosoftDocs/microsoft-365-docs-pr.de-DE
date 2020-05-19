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
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280534"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Voraussetzungen für Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Einrichtung und Verwendung von Microsoft Threat Protection.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

>[!IMPORTANT]
>Ab dem 12. Mai 2020 wird Microsoft schrittweise neue, optimierte Erfahrungen rund um die Lizenzanforderungen einführen und [Microsoft Threat Protection aktivieren](mtp-enable.md). Einige Wochen während dieses Zeitraums werden einige Kunden beginnen, Änderungen an Ihren Portal-Erlebnissen zu sehen. Informationen zu den neuen Erfahrungen sind in diesem Artikel als **neue Erfahrung** markiert.

Um Microsoft Threat Protection verwenden zu können, benötigen Sie entweder eine einzelne Lizenz oder eine Kombination aus Lizenzen. Diese Lizenzen oder Lizenz Kombinationen ermöglichen den Zugriff auf Microsoft Threat Protection-Features ohne zusätzliche Kosten.

### <a name="single-license"></a>Einzelne Lizenz
Sie können *eine* der folgenden Lizenzen verwenden:

- Microsoft 365 E5 oder A5
- Microsoft 365 E5 Sicherheit oder a5-Sicherheit

### <a name="combination-of-licenses"></a>Kombination von Lizenzen
Sie können auch eine Kombination aus Lizenzen für E5-oder A5-Abonnements für Office 365, *Enterprise Mobility + Security (EMS)* und Windows verwenden. Die Lizenzkombination muss *alle* diese Lizenzen enthalten:

- Office 365 E5 oder A5
- *Enterprise Mobility + Security (EMS)* E5 oder A5
- Windows 10 Enterprise E5 oder A5

Weitere Informationen finden Sie unter [Microsoft 365 Enterprise-Dienstpläne](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Sie haben noch keine Lizenz? [Testen oder Kaufen eines Microsoft 365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


**Neue Erfahrung:** Ab dem 12. Mai 2020 werden Kunden allmählich Änderungen an dieser Erfahrung erhalten. Für Personen mit der neuen Benutzeroberfläche steht Ihnen die Option zum Aktivieren von Microsoft Threat Protection für *alle* Kunden mit einer der folgenden Lizenzen zur Verfügung:

- Microsoft 365 E5 oder A5
- Microsoft 365 E5 Sicherheit oder a5-Sicherheit
- Windows 10 Enterprise E5 oder A5
- Enterprise Mobility + Security (EMS) E5 oder A5 
- Office 365 E5 oder A5
- Microsoft Defender Advanced Threat Protection 
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security 
- Office 365 Advanced Threat Protection (Plan 2) 

### <a name="check-your-existing--licenses"></a>Überprüfen vorhandener Lizenzen
Wechseln Sie zu Microsoft 365 Admin Center ([Admin.Microsoft.com](https://admin.microsoft.com/)), um Ihre vorhandenen Lizenzen anzuzeigen. Navigieren Sie im Admin Center zu **Abrechnung** > **Lizenzen**.

>[!NOTE]
> Sie müssen entweder die Rolle **"abrechnungsadministrator"** oder " **globaler Leser** " [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) zugewiesen sein, um Lizenzinformationen anzeigen zu können. Wenn Sie Probleme beim Zugriff haben, wenden Sie sich an einen globalen Administrator.

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
