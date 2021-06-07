---
title: Benutzerressourcentyp
description: Abrufen der letzten Microsoft Defender für Endpunkt-Warnungen im Zusammenhang mit Benutzern.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 39b73772bcc626590aa784bb5b21357f66229816
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772137"
---
# <a name="user-resource-type"></a>Benutzerressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Benutzerbezogene Warnungen auflisten](get-user-related-alerts.md) | [Warnung](alerts.md) Sammlung |  Listet alle Warnungen auf, die einem [Benutzer](user.md)zugeordnet sind.
[Benutzerbezogene Geräte auflisten](get-user-related-machines.md) | [Computersammlung](machine.md) | Listet alle Geräte auf, die von einem [Benutzer](user.md)angemeldet wurden.
