---
title: Microsoft 365 Defender-APIs- Lizenz und Nutzungsbedingungen
description: Beschreibung der Lizenz und der Nutzungsbedingungen für APIs in Microsoft 365 Defender
keywords: api, apis, license, terms, apis, legal, notices, code of conduct
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
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930954"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender-APIs- Lizenz und Nutzungsbedingungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="official-terms"></a>Offizielle Begriffe

Microsoft 365 Defender-APIs unterliegen der [Microsoft-APIs-Lizenz und den Nutzungsbedingungen.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Rechtliche Hinweise

Microsoft und alle Mitwirkenden gewähren Ihnen eine Lizenz für die Microsoft-Dokumentation und andere Inhalte [in](https://github.com/MicrosoftDocs/microsoft-365-docs)diesem Repository unter der öffentlichen Creative Commons Attribution 4.0-Lizenz. Weitere Informationen finden Sie in der [LIZENZdatei.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure und/oder andere Microsoft-Produkte und -Dienste, auf die in der Dokumentation verwiesen wird, können Marken oder eingetragene Marken von Microsoft in den USA und/oder anderen Ländern sein.

Die Lizenzen für dieses Projekt gewähren Ihnen keine Rechte zur Verwendung von Microsoft-Namen, Logos oder Marken. Die allgemeinen Markenrichtlinien von Microsoft finden Sie unter [Microsoft Trademarks](https://go.microsoft.com/fwlink/?LinkID=254653).

Datenschutzinformationen finden Sie unter ["Datenschutz" bei Microsoft.](https://privacy.microsoft.com)

Microsoft und alle Mitwirkenden behalten sich alle anderen Rechte vor, sei es unter ihren jeweiligen Urheberrechten, Patenten oder Marken, sei es durch Implikationen, Estoppel oder anderweitig.

## <a name="other-restrictions"></a>Weitere Einschränkungen

Die API für die erweiterte Suche hat einige Einschränkungen [hinsichtlich](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) der Anzahl der zurückgegebenen Ergebnisse und der Daten, die abgefragt werden können.

1. Sie können nur Daten aus den letzten 30 Tagen abfragen.
1. Die Ergebnisse enthalten maximal 100.000 Zeilen.

### <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuordnung

Die Microsoft 365 Defender-APIs haben Drosselungsschwellenwerte.

- **Vorfall-API:** Bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde.
- **Api für die** erweiterte Suche: Bis zu 15 Aufrufe pro Minute, 10 Minuten Laufzeit pro Stunde und 4 Stunden Laufzeit pro Tag.

Der HTTP-Antwortstatuscode, der angibt, dass die Drosselung . `429`

Wenn Ihre Anforderung gedrosselt wurde, gibt der Antworttext den Zeitpunkt an, zu dem Sie mit dem Erneuten Senden von Anforderungen beginnen können.

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Microsoft 365 Defender-APIs](api-overview.md)
- [Unterstützte Microsoft 365 Defender-APIs](api-supported.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
