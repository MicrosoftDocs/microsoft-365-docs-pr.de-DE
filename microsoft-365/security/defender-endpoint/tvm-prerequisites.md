---
title: Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Bevor Sie mit der Verwaltung von Bedrohungen und Sicherheitslücken beginnen, stellen Sie sicher, dass Sie über die entsprechenden Konfigurationen und Berechtigungen verfügen.
keywords: Voraussetzungen & sicherheitsrisikoverwaltungsberechtigungen, Voraussetzungen für die Bedrohungs- und Sicherheitsrisikoverwaltung, MDATP-TVM-Berechtigungen, Sicherheitsrisikoverwaltung
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
ms.openlocfilehash: 1d9c3233f72541ccd0463eefef93bde5e7d9900f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499963"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Voraussetzungen & Berechtigungen – Bedrohungs- und Sicherheitsrisikoverwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedrohungs- und Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)
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

- Werden in [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) und  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) onboarded, um bedrohungs- und sicherheitsrisikobedrohungen zu helfen. Wenn Sie Configuration Manager verwenden, aktualisieren Sie Ihre Konsole auf die neueste Version.
    - **Hinweis:** Wenn Sie die Intune-Verbindung aktiviert haben, erhalten Sie eine Option zum Erstellen einer Intune-Sicherheitsaufgabe beim Erstellen einer Korrekturanforderung. Diese Option wird nicht angezeigt, wenn die Verbindung nicht festgelegt ist.
- Mindestens eine Sicherheitsempfehlung, die auf der Geräteseite angezeigt werden kann
- Markiert oder als gemeinsam verwaltet gekennzeichnet

## <a name="relevant-permission-options"></a>Relevante Berechtigungsoptionen

1. Melden Sie sich beim Microsoft Defender Security Center mit einem Konto an, dem ein Sicherheitsadministrator oder eine globale Administratorrolle zugewiesen ist.
2. Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](user-roles.md)

### <a name="view-data"></a>Anzeigen von Daten

- **Sicherheitsvorgänge** – Anzeigen aller Daten zu Sicherheitsvorgängen im Portal
- **Bedrohungs- und Sicherheitsrisikoverwaltung** – Anzeigen von Daten zur Verwaltung von Bedrohungen und Sicherheitslücken im Portal

### <a name="active-remediation-actions"></a>Aktive Korrekturaktionen

- **Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zulässiger/blockierter Listen für Automatisierung und Indikatoren
- **Bedrohungs- und Sicherheitsrisikoverwaltung – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen
- **Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung** von Abhilfemaßnahmen – Übermitteln neuer Behebungsanforderungen, Erstellen von Tickets und Verwalten vorhandener Abhilfemaßnahmen

Weitere Informationen finden Sie unter [RBAC-Berechtigungsoptionen.](user-roles.md#permission-options)

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken](next-gen-threat-and-vuln-mgt.md)
- [Unterstützte Betriebssysteme und Plattformen](tvm-supported-os.md)
- [Zuweisen des Gerätewerts](tvm-assign-device-value.md)
- [Dashboard zur Verwaltung von Bedrohungen und Sicherheitslücken](tvm-dashboard-insights.md)

