---
title: Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikomanagement
description: Bevor Sie mit der Bedrohungs- und Sicherheitsrisikomanagement beginnen, stellen Sie sicher, dass Sie über die entsprechenden Konfigurationen und Berechtigungen verfügen.
keywords: Voraussetzungen & Sicherheitsrisikomanagement Berechtigungen, Bedrohungs- und Sicherheitsrisikomanagement Berechtigungen, Voraussetzungen für Microsoft Defender für Endpoint TVM-Berechtigungen, Sicherheitsrisikomanagement
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
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935185"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikomanagement

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohung und Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Stellen Sie sicher, dass Ihre Geräte:

- Werden in Microsoft Defender for Endpoint onboarded
- Ausführen [unterstützter Betriebssysteme und Plattformen](tvm-supported-os.md)
- Die folgenden obligatorischen Updates müssen in Ihrem Netzwerk installiert und bereitgestellt werden, um die Erkennungsraten für Sicherheitslücken zu erhöhen:

> Freigabe | Sicherheitsupdate KB-Nummer und Link
> :---|:---
> Windows 10 Version 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) und [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Version 1803 | [KB4493464](https://support.microsoft.com/help/4493464) und [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Version 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Version 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Werden in [die](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) Microsoft Intune [und](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) Microsoft Endpoint Configuration Manager, um bedrohungen zu Bedrohungs- und Sicherheitsrisikomanagement. Wenn Sie Configuration Manager verwenden, aktualisieren Sie Ihre Konsole auf die neueste Version.
    - **Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Korrekturanforderung. Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.
- Mindestens eine Sicherheitsempfehlung, die auf der Geräteseite angezeigt werden kann
- Markiert oder als gemeinsam verwaltet gekennzeichnet

## <a name="relevant-permission-options"></a>Relevante Berechtigungsoptionen

1. Melden Sie sich bei Microsoft Defender Security Center konto mit einem zugewiesenen Sicherheitsadministrator oder einer globalen Administratorrolle an.
2. Wählen Sie im Navigationsbereich die **Option Einstellungen > Rollen aus.**

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](user-roles.md)

### <a name="view-data"></a>Anzeigen von Daten

- **Sicherheitsvorgänge** – Anzeigen aller Daten zu Sicherheitsvorgängen im Portal
- **Bedrohung und Sicherheitsrisikomanagement** – Anzeigen Bedrohungs- und Sicherheitsrisikomanagement Daten im Portal

### <a name="active-remediation-actions"></a>Aktive Korrekturaktionen

- **Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zulässiger/blockierter Listen für Automatisierung und Indikatoren
- **Bedrohung und Sicherheitsrisikomanagement – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen
- **Bedrohung und Sicherheitsrisikomanagement – Behandlung** von Abhilfemaßnahmen – Übermitteln neuer Abhilfemaßnahmen, Erstellen von Tickets und Verwalten vorhandener Abhilfemaßnahmen

Weitere Informationen finden Sie unter [RBAC-Berechtigungsoptionen.](user-roles.md#permission-options)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen](next-gen-threat-and-vuln-mgt.md)
- [Unterstützte Betriebssysteme und Plattformen](tvm-supported-os.md)
- [Zuweisen des Gerätewerts](tvm-assign-device-value.md)
- [Bedrohung und Sicherheitsrisikomanagement Dashboard](tvm-dashboard-insights.md)

