---
title: Dashboard-Einblicke – Bedrohungs- und Sicherheitsrisikomanagement
description: Das Bedrohungs- und Sicherheitsrisikomanagement-Dashboard kann SecOps und Sicherheitsadministratoren dabei helfen, Cybersicherheitsbedrohungen zu adressieren und die Ausfallsicherheit ihrer Organisation zu erhöhen.
keywords: Microsoft Defender for Endpoint-tvm, Microsoft Defender for Endpoint-tvm Dashboard, Threat & Sicherheitsrisikomanagement, Bedrohungs- und Sicherheitsrisikomanagement, risk-based threat & Sicherheitsrisikomanagement, security configuration, Microsoft Secure Score for Devices, exposure score
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934141"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Dashboard-Einblicke – Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Threat and Sicherheitsrisikomanagement ist eine Komponente von Defender for Endpoint und bietet sowohl Sicherheitsadministratoren als auch Sicherheitsbetriebsteams einen eindeutigen Wert, einschließlich:


- Erkenntnisse aus Erkennung und Reaktion am Endpunkt in Echtzeit in Korrelation mit Endpunktsicherheitsrisiken
- Unbezahlbarer Sicherheitsrisikokontext für Geräte bei Vorfalluntersuchungen
- Integrierte Korrekturprozesse durch Microsoft Intune und Microsoft Endpoint Configuration Manager  
  
Sie können die Bedrohungs- und Sicherheitsrisikomanagement in den [Microsoft Defender Security Center](https://securitycenter.windows.com/) verwenden:

- Anzeigen von Belichtungsergebnis und Microsoft Secure Score für Geräte, zusammen mit den besten Sicherheitsempfehlungen, Softwarerisiken, Korrekturaktivitäten und verfügbar gemachten Geräten
- Korrelieren EDR Erkenntnisse mit Endpunktrisiken und Verarbeiten dieser Sicherheitsrisiken
- Auswählen von Korrekturoptionen zum Triagen und Nachverfolgen der Problembehebungsaufgaben
- Auswählen von Ausnahmeoptionen und Nachverfolgen aktiver Ausnahmen

> [!NOTE]
> Geräte, die in den letzten 30 Tagen nicht aktiv sind, werden nicht in die Daten ein faktoriert, die die Bedrohungs- und Sicherheitsrisikomanagement ihrer Organisation und die Microsoft Secure Score für Geräte spiegeln.

Sehen Sie sich dieses Video an, um eine kurze Übersicht darüber zu erhalten, was sich im Bedrohungs- und Sicherheitsrisikomanagement befindet.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Bedrohung und Sicherheitsrisikomanagement Dashboard

 ![Microsoft Defender for Endpoint-Portal](images/tvm-dashboard-devices.png)

Bereich | Beschreibung
:---|:---
**Ausgewählte Gerätegruppen (#/#)**   | Filtern Sie Bedrohungs- und Sicherheitsrisikomanagement daten, die im Dashboard angezeigt werden möchten, und Karten nach Gerätegruppen. Was Sie im Filter auswählen, gilt auf den Bedrohungs- und Sicherheitsrisikomanagement Seiten.
[**Gefährdungsscore**](tvm-exposure-score.md)   | Sehen Sie sich den aktuellen Status der Geräteexposition Ihrer Organisation gegenüber Bedrohungen und Sicherheitsrisiken an. Mehrere Faktoren wirken sich auf die Belichtungssentwertung Ihrer Organisation aus: Auf Ihren Geräten festgestellte Schwächen, wahrscheinlichkeit, dass Ihre Geräte verletzt werden, der Wert der Geräte für Ihre Organisation und relevante Warnungen, die mit Ihren Geräten erkannt wurden. Das Ziel ist es, die Belichtungszahl Ihrer Organisation zu senken, um sicherer zu sein. Um die Bewertung zu reduzieren, müssen Sie die zugehörigen Sicherheitskonfigurationsprobleme beheben, die in den Sicherheitsempfehlungen aufgeführt sind.
[**Microsoft-Sicherheitsbewertung für Geräte**](tvm-microsoft-secure-score-devices.md) | Sehen Sie sich die Sicherheitslage des Betriebssystems, der Anwendungen, des Netzwerks, der Konten und der Sicherheitskontrollen Ihrer Organisation an. Ziel ist es, die damit verbundenen Sicherheitskonfigurationsprobleme zu beheben, um die Bewertung für Geräte zu erhöhen. Wenn Sie die Balken auswählen, gelangen Sie zur **Seite Sicherheitsempfehlung.**
**Verteilung der Gerätebelichtung** | Sehen Sie, wie viele Geräte basierend auf ihrer Belichtungsstufe verfügbar gemacht werden. Wählen Sie einen Abschnitt im Ringdiagramm aus, um zur Listenseite Geräte zu wechseln und die betroffenen Gerätenamen, die Risikostufe, die Risikostufe und andere Details wie Domäne, Betriebssystemplattform, Integritätsstatus, wann sie zuletzt angezeigt wurde, und die Tags anzuzeigen. 
**Die besten Sicherheitsempfehlungen** | Sehen Sie sich die sortierten Sicherheitsempfehlungen an, die basierend auf der Risikoexposition Ihrer Organisation und der benötigten Dringlichkeit sortiert und priorisiert werden. Wählen **Sie Weitere Anzeigen** aus, um die restlichen Sicherheitsempfehlungen in der Liste zu sehen. Wählen **Sie Ausnahmen anzeigen** für die Liste der Empfehlungen mit einer Ausnahme aus.
**Besonders anfällige Software** | Erhalten Sie In Echtzeit Einblick in das Softwareinventar Ihrer Organisation mit einer liste mit Stapelrang auf den Geräten Ihres Netzwerks installierter anfälliger Software und deren Auswirkungen auf Ihre organisatorische Gefährdungsbewertung. Wählen Sie ein Element für Details oder **Weitere** Anzeigen aus, um den Rest der Liste anfälliger Software auf der **Seite Softwareinventar anzuzeigen.**
**Die besten Korrekturaktivitäten** | Verfolgen Sie die Korrekturaktivitäten, die aus den Sicherheitsempfehlungen generiert wurden. Sie können jedes Element in der Liste  auswählen, um die  Details auf der Seite Korrektur anzuzeigen, oder weitere Anzeigen auswählen, um die restlichen Korrekturaktivitäten und aktive Ausnahmen anzuzeigen.
**Am besten verfügbar gemachte Geräte** | Anzeigen der verfügbar gemachten Gerätenamen und deren Belichtungsstufe. Wählen Sie einen Gerätenamen aus der Liste aus, um zur Geräteseite zu wechseln, auf der Sie die Warnungen, Risiken, Vorfälle, Sicherheitsempfehlungen, installierte Software und ermittelte Sicherheitsrisiken im Zusammenhang mit den verfügbar gemachten Geräten anzeigen können. Wählen **Sie Weitere Anzeigen** aus, um den Rest der Liste der verfügbar gemachten Geräte zu sehen. In der Geräteliste können Sie Tags verwalten, automatisierte Untersuchungen initiieren, eine Liveantwortsitzung initiieren, ein Untersuchungspaket sammeln, Einen Antivirenscan ausführen, die Ausführung von Apps einschränken und das Gerät isolieren.

Weitere Informationen zu den im Portal verwendeten Symbolen finden Sie unter [Microsoft Defender for Endpoint-Symbole](portal-overview.md#microsoft-defender-for-endpoint-icons).


## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen](next-gen-threat-and-vuln-mgt.md)
- [Gefährdungsscore](tvm-exposure-score.md)
- [Microsoft-Sicherheitsbewertung für Geräte](tvm-microsoft-secure-score-devices.md)
- [Sicherheitsempfehlungen](tvm-security-recommendation.md)
- [Softwarebestand](tvm-software-inventory.md)
- [Ablauf der Veranstaltung](threat-and-vuln-mgt-event-timeline.md)

