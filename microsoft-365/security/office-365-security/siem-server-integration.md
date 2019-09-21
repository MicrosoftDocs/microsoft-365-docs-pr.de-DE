---
title: Siem-Server Integration mit Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 'Zusammenfassung: Lesen Sie diesen Artikel, um einen Überblick über die Integration von Siem Server mit Microsoft 365 zu erhalten.'
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082644"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen

## <a name="overview"></a>Übersicht

Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet oder wenn Sie einen Siem-Server bald erhalten möchten, Fragen Sie sich möglicherweise, wie sich das in Ihren Microsoft 365, einschließlich Office 365 E5, integrieren lässt. Ob Sie einen Siem-Server benötigen, hängt von vielen Faktoren ab, beispielsweise von den Sicherheitsanforderungen Ihrer Organisation. Microsoft 365 bietet eine Vielzahl von Sicherheitsfeatures; Wenn Ihre Organisation jedoch Inhalte und Anwendungen lokal und in der Cloud hat (wie bei einer hybriden Cloud-Bereitstellung), können Sie einen Siem-Server für zusätzlichen Schutz verwenden. Wenn Ihre Organisation besonders strenge Sicherheitsanforderungen erfüllt, müssen Sie möglicherweise einen Siem-Server zu Ihrer Umgebung hinzufügen.

## <a name="siem-server-integration-microsoft-365"></a>Siem-Server Integration Microsoft 365

Ein Siem-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und-Anwendungen empfangen. In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und-Anwendungen zusammen mit Siem Server-Eingaben aufgeführt, und weitere Informationen zur Integration von Siem Server finden Sie unter. 

| Microsoft 365-Dienst oder-Anwendung | Siem-Server Eingaben | Ressourcen für weitere Informationen |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md) <br/>oder<br/>[Informationen zu Bedrohungen in Office 365](office-365-ti.md) | Überwachungsprotokolle | [Siem-Integration mit Office 365 Advanced Threat Protection](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Protokoll Integration | [Siem-Integration in Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/siem) |
| [Microsoft Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | Protokoll Integration | [Abrufen von Benachrichtigungen an Ihre Siem-Tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Azure-Sicherheits Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Bedrohungsschutz und Bedrohungserkennung) | Warnungen | [Azure Security Data Export to Siem-Pipeline Configuration – Vorschau](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Azure Advanced Threat Analytics](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure-Monitor | [Blog Verwenden von Azure Monitor zur Integration in Siem-Tools](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |Protokoll Integration |[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>Die Überwachungsprotokollierung muss aktiviert sein.

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren. 

- Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security #a0 Compliance Center aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Für Exchange Online [ist die Überwachungsprotokollierung mit Windows PowerShell aktiviert](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>Siehe auch

[Cloudakzeptanz und Hybridlösungen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


