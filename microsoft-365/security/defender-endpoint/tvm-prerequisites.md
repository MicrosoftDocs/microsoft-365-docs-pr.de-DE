---
title: Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikomanagement
description: Bevor Sie mit der Verwendung von Bedrohungs- und Sicherheitsrisikomanagement beginnen, stellen Sie sicher, dass Sie über die entsprechenden Konfigurationen und Berechtigungen verfügen.
keywords: Voraussetzungen für bedrohungs- & Sicherheitsrisikomanagement Berechtigungen, Bedrohungs- und Sicherheitsrisikomanagement Berechtigungsvoraussetzungen, Microsoft Defender für Endpunkt-TVM-Berechtigungsvoraussetzungen, Sicherheitsrisikomanagement
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843950"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Stellen Sie sicher, dass Ihre Geräte:

- Sind in Microsoft Defender für Endpunkt integriert
- Ausführen [unterstützter Betriebssysteme und Plattformen](tvm-supported-os.md)
- Installieren und bereitstellen Sie die folgenden obligatorischen Updates in Ihrem Netzwerk, um die Erkennungsraten ihrer Sicherheitslücken zu erhöhen:

> Freigabe | KB-Nummer und Verknüpfung für Sicherheitsupdate
> :---|:---
> Windows 10 Version 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) und [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Version 1803 | [KB4493464](https://support.microsoft.com/help/4493464) und [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Version 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Version 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Sind in [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) integriert, um von Bedrohungs- und Sicherheitsrisikomanagement gefundene Bedrohungen zu beheben. Wenn Sie Configuration Manager verwenden, aktualisieren Sie Die Konsole auf die neueste Version.
    - **Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Wartungsanforderung. Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.
- Sie haben mindestens eine Sicherheitsempfehlung, die auf der Geräteseite angezeigt werden kann.
- Als coverwaltet gekennzeichnet oder gekennzeichnet werden

## <a name="relevant-permission-options"></a>Relevante Berechtigungsoptionen

1. Melden Sie sich bei Microsoft Defender Security Center mit einem Konto an, dem ein Sicherheitsadministrator oder eine globale Administratorrolle zugewiesen ist.
2. Wählen Sie im Navigationsbereich **Einstellungen > Rollen** aus.

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](user-roles.md)

### <a name="view-data"></a>Anzeigen von Daten

- **Sicherheitsvorgänge** – Anzeigen aller Sicherheitsvorgänge im Portal
- **Bedrohung und Sicherheitsrisikomanagement** – Anzeigen Bedrohungs- und Sicherheitsrisikomanagement Daten im Portal

### <a name="active-remediation-actions"></a>Aktive Abhilfemaßnahmen

- **Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zugelassener/blockierter Listen für Automatisierung und Indikatoren
- **Bedrohung und Sicherheitsrisikomanagement – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen
- **Bedrohung und Sicherheitsrisikomanagement – Behandlung** von Korrekturen – Übermitteln neuer Wartungsanforderungen, Erstellen von Tickets und Verwalten vorhandener Wartungsaktivitäten

Weitere Informationen finden Sie unter [RBAC-Berechtigungsoptionen](user-roles.md#permission-options)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Bedrohungen und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Unterstützte Betriebssysteme und Plattformen](tvm-supported-os.md)
- [Zuweisen des Gerätewerts](tvm-assign-device-value.md)
- [Dashboard für Bedrohungen und Sicherheitsrisikomanagement](tvm-dashboard-insights.md)

