---
title: Microsoft 365 Defender-APIs-Lizenz und Nutzungsbedingungen
description: Beschreibung der Lizenz und Nutzungsbedingungen für APIs in Microsoft 365 Defender
keywords: API, APIs, Lizenz, Ausdrücke, APIs, Legal, Notices, Code of Conduct
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
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719298"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender-APIs-Lizenz und Nutzungsbedingungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

## <a name="official-terms"></a>Offizielle Ausdrücke

Microsoft 365 Defender-APIs unterliegen der [Microsoft APIs-Lizenz und den Nutzungsbedingungen](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).

## <a name="legal-notices"></a>Rechtliche Hinweise

Microsoft und alle Mitwirkenden gewähren Ihnen eine Lizenz für die Microsoft-Dokumentation und andere Inhalte in [diesem Repository](https://github.com/MicrosoftDocs/microsoft-365-docs)unter der Creative Commons Attribution 4,0 International Public License. Weitere Informationen finden Sie in der [Lizenz](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) Datei.

Microsoft, Windows, Microsoft Azure und/oder andere Microsoft-Produkte und -Dienste, auf die in der Dokumentation verwiesen wird, können Marken oder eingetragene Marken von Microsoft in den USA und/oder anderen Ländern sein.

Die Lizenzen für dieses Projekt gewähren Ihnen keine Rechte zur Verwendung von Microsoft-Namen,-Logos oder-Marken. Die allgemeinen Markenrichtlinien von Microsoft finden Sie unter [Microsoft trademarks](https://go.microsoft.com/fwlink/?LinkID=254653).

Datenschutzinformationen finden Sie unter [Datenschutz bei Microsoft](https://privacy.microsoft.com).

Microsoft und alle Mitwirkenden behalten sich alle anderen Rechte vor, unabhängig davon, ob Sie unter den jeweiligen Urheberrechten, Patenten oder Marken, sei es durch Implikation, Estoppel oder anderweitig.

## <a name="other-restrictions"></a>Sonstige Einschränkungen

Die erweiterte Jagd-API hat einige [Einschränkungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) hinsichtlich der Anzahl der zurückgegebenen Ergebnisse und der Daten, die abgefragt werden können.

1. Sie können nur Daten von den letzten 30 Tagen Abfragen.
1. Die Ergebnisse umfassen maximal 100.000 Zeilen.

### <a name="quotas-and-resource-allocation"></a>Kontingente und Ressourcenzuteilung

Die Microsoft 365 Defender-APIs verfügen über Drosselungs Schwellenwerte.

- **Vorfälle-API**: bis zu 50 Anrufe pro Minute oder 1500 Anrufe pro Stunde.
- **Erweiterte Jagd-API**: bis zu 15 Anrufe pro Minute, 10 Minuten Spielzeit pro Stunde und 4 Stunden Spielzeit pro Tag.

Der HTTP-Antwortstatuscode, der angibt, dass die Einschränkung erfolgt `429` .

Wenn Ihre Anforderung gedrosselt wurde, gibt der Antworttext die Uhrzeit an, zu der Sie die Anforderungen erneut ausführen können.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft 365 Defender-APIs (Übersicht)](api-overview.md)
- [Unterstützte Microsoft 365 Defender-APIs](api-supported.md)
- [Zugreifen auf die Microsoft 365 Defender-APIs](api-access.md)
