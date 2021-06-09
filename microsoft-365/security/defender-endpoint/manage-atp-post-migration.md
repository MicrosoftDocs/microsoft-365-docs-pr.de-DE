---
title: Verwalten von Microsoft Defender für Endpunkt nach der Migration
description: Nachdem Sie nun zu Microsoft Defender für Endpunkt gewechselt haben, besteht Der nächste Schritt darin, Ihre Bedrohungsschutzfeatures zu verwalten.
keywords: nach der Migration, verwalten, Vorgänge, Wartung, Auslastung, Microsoft Defender für Endpunkt, edr
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
ms.openlocfilehash: ea5e4cb1c4a93f5f8bd5da1c0c94b095d03ac680
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845618"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Verwalten von Microsoft Defender für Endpunkt nach der Migration

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Nachdem Sie von Ihrer vorherigen Endpunktschutz- und Antivirenlösung zu Microsoft Defender für Endpunkt gewechselt sind, besteht der nächste Schritt darin, Ihre Features und Funktionen zu verwalten. Es wird [empfohlen, Microsoft Endpoint Manager](/mem/endpoint-manager-overview)zu verwenden, das [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) und [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)umfasst, um die Geräte und Sicherheitseinstellungen Ihrer Organisation zu verwalten. Sie können jedoch andere Tools/Methoden verwenden, z. B. [Gruppenrichtlinienobjekte in Azure Active Directory Domänendienste.](/azure/active-directory-domain-services/manage-group-policy) 

Die folgende Tabelle enthält verschiedene Tools/Methoden, die Sie verwenden können, mit Links, um mehr zu erfahren. 
<br/><br/>

|Tool/Methode  |Beschreibung  |
|---------|---------|
|Einblicke in **[das Bedrohungs- und Sicherheitsrisikomanagement-Dashboard](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |Das Dashboard für bedrohungsbezogene & Sicherheitsrisikomanagement bietet umsetzbare Informationen, die Ihr Sicherheitsteam verwenden kann, um die Gefährdung zu verringern und den Sicherheitsstatus Ihrer Organisation zu verbessern. <br/><br/>Siehe ["Bedrohungs-& Sicherheitsrisikomanagement"](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) und ["Übersicht über die Microsoft Defender Security Center".](/microsoft-365/security/defender-endpoint/use)  |
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (empfohlen)    |Microsoft Intune (Intune), eine Komponente von [Microsoft Endpoint Manager,](/mem/endpoint-manager-overview)konzentriert sich auf die Verwaltung mobiler Geräte (Mobile Device Management, MDM) und die Verwaltung mobiler Anwendungen (Mobile Application Management, MAM). Mit Intune steuern Sie, wie die Geräte Ihrer Organisation verwendet werden, einschließlich Mobiltelefonen, Tablets und Laptops. Sie können auch bestimmte Richtlinien konfigurieren, um Anwendungen zu steuern. <br/><br/>Weitere Informationen finden Sie unter [Verwalten von Microsoft Defender für Endpunkt mit Intune.](manage-atp-post-migration-intune.md)         |
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), früher bekannt als System Center Configuration Manager, ist eine Komponente von [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). Configuration Manager ist ein leistungsstarkes Tool zum Verwalten Ihrer Benutzer, Geräte und Software.<br/><br/>Siehe [Verwalten von Microsoft Defender für Endpunkt mit Configuration Manager.](manage-atp-post-migration-configuration-manager.md)        |
|**[Gruppenrichtlinienobjekte in Azure Active Directory Domänendiensten](/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory Domänendienste](/azure/active-directory-domain-services/overview) enthält integrierte Gruppenrichtlinienobjekte für Benutzer und Geräte. Sie können die integrierten Gruppenrichtlinienobjekte nach Bedarf für Ihre Umgebung anpassen sowie benutzerdefinierte Gruppenrichtlinienobjekte und Organisationseinheiten (OUs) erstellen. <br/><br/>Siehe [Verwalten von Microsoft Defender für Endpunkt mit Gruppenrichtlinienobjekten.](manage-atp-post-migration-group-policy-objects.md) |
|**[PowerShell, WMI, and MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Es wird empfohlen, Microsoft Endpoint Manager (einschließlich Intune und Configuration Manager) zum Verwalten von Bedrohungsschutzfeatures auf den Geräten Ihrer Organisation zu verwenden. Sie können jedoch einige Einstellungen konfigurieren, z. B. Microsoft Defender Antivirus Einstellungen auf einzelnen Geräten (Endpunkten) mit PowerShell, WMI oder dem MPCmdRun.exe-Tool.*<br/><br/>Sie können PowerShell verwenden, um Microsoft Defender Antivirus, Exploit-Schutz und Die Verringerung der Angriffsfläche zu verwalten. Siehe [Konfigurieren von Microsoft Defender für Endpunkt mit PowerShell.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)<br/><br/>Sie können Windows Verwaltungsinstrumentation (Management Instrumentation, WMI) verwenden, um Microsoft Defender Antivirus und Ausschlüsse zu verwalten. Siehe [Konfigurieren von Microsoft Defender für Endpunkt mit WMI.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)<br/><br/>Sie können das Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) verwenden, um Microsoft Defender Antivirus und Ausschlüsse zu verwalten und Verbindungen zwischen Ihrem Netzwerk und der Cloud zu überprüfen. Siehe [Konfigurieren von Microsoft Defender für Endpunkt mit MPCmdRun.exe. ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) |

## <a name="see-also"></a>Siehe auch

- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
