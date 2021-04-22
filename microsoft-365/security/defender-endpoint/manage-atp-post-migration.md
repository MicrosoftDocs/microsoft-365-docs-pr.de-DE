---
title: Verwalten von Microsoft Defender for Endpoint nach der Migration
description: Nachdem Sie den Wechsel zu Microsoft Defender for Endpoint vorgenommen haben, besteht der nächste Schritt in der Verwaltung Ihrer Funktionen zum Schutz vor Bedrohungen.
keywords: nach der Migration, Verwalten, Betrieb, Wartung, Auslastung, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: eedd13030fd6a649985dc7280dc256e4ab35089a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933193"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Verwalten von Microsoft Defender for Endpoint nach der Migration

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Nachdem Sie von Ihrer vorherigen Endpunktschutz- und Antivirenlösung zu Microsoft Defender for Endpoint umgezogen sind, besteht der nächste Schritt in der Verwaltung Ihrer Features und Funktionen. Es wird [empfohlen, Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)zu verwenden, der Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) und Microsoft Endpoint [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)umfasst, um die Geräte und Sicherheitseinstellungen Ihrer Organisation zu verwalten. Sie können jedoch andere Tools/Methoden verwenden, z. B. [Gruppenrichtlinienobjekte in Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy). 

In der folgenden Tabelle sind verschiedene Tools/Methoden aufgeführt, die Sie verwenden können, mit Links, um mehr zu erfahren. 
<br/><br/>

|Tool/Methode  |Beschreibung  |
|---------|---------|
|**[Einblicke in das](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** Dashboard zur Bedrohungs- und Sicherheitsrisikoverwaltung im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |Das Dashboard & Sicherheitsrisikoverwaltung bietet aktionenfähige Informationen, die Ihr Sicherheitsbetriebsteam verwenden kann, um die Gefährdung zu reduzieren und die Sicherheitsposition Ihrer Organisation zu verbessern. <br/><br/>Weitere [Informationen & Verwaltung von Sicherheitsrisiken und](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Übersicht über das Microsoft Defender Security Center finden Sie unter Threat & vulnerability management und Overview of the Microsoft Defender Security [Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (empfohlen)    |Microsoft Intune (Intune), eine Komponente von [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)konzentriert sich auf die Verwaltung mobiler Geräte (MOBILE Device Management, MDM) und mobile Anwendungsverwaltung (Mobile Application Management, MAM). Mit Intune steuern Sie, wie die Geräte Ihrer Organisation verwendet werden, einschließlich Mobiltelefone, Tablets und Laptops. Sie können auch bestimmte Richtlinien zum Steuern von Anwendungen konfigurieren. <br/><br/>Weitere [Informationen finden Sie unter Manage Microsoft Defender for Endpoint using Intune](manage-atp-post-migration-intune.md).         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), früher als System Center Configuration Manager bezeichnet, ist eine Komponente von [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview). Configuration Manager ist ein leistungsstarkes Tool zum Verwalten ihrer Benutzer, Geräte und Software.<br/><br/>Weitere [Informationen finden Sie unter Manage Microsoft Defender for Endpoint with Configuration Manager](manage-atp-post-migration-configuration-manager.md).        |
|**[Gruppenrichtlinienobjekte in Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/overview) enthält integrierte Gruppenrichtlinienobjekte für Benutzer und Geräte. Sie können die integrierten Gruppenrichtlinienobjekte nach Bedarf für Ihre Umgebung anpassen und benutzerdefinierte Gruppenrichtlinienobjekte und Organisationseinheiten erstellen. <br/><br/>Weitere [Informationen finden Sie unter Manage Microsoft Defender for Endpoint with Group Policy Objects](manage-atp-post-migration-group-policy-objects.md). |
|**[PowerShell, WMI, and MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Es wird empfohlen, Microsoft Endpoint Manager (einschließlich Intune und Configuration Manager) zum Verwalten von Bedrohungsschutzfeatures auf den Geräten Ihrer Organisation zu verwenden. Sie können jedoch einige Einstellungen konfigurieren, z. B. Microsoft Defender Antivirus-Einstellungen auf einzelnen Geräten (Endpunkten) mit PowerShell, WMI oder dem MPCmdRun.exe Tool.*<br/><br/>Sie können PowerShell verwenden, um Microsoft Defender Antivirus, exploit protection und Ihre Regeln zur Reduzierung der Angriffsfläche zu verwalten. Weitere [Informationen finden Sie unter Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).<br/><br/>Sie können Windows Management Instrumentation (WMI) verwenden, um Microsoft Defender Antivirus und Ausschlüsse zu verwalten. Weitere [Informationen finden Sie unter Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).<br/><br/>Sie können das Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) verwenden, um Microsoft Defender Antivirus und Ausschlüsse zu verwalten sowie Verbindungen zwischen Ihrem Netzwerk und der Cloud zu überprüfen. Weitere [Informationen finden Sie unter Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe). |

## <a name="see-also"></a>Siehe auch

- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
