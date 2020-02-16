---
title: " Integration von Security Information and Event Management (SIEM) Server in Microsoft 365-Dienste und-Anwendungen"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Erhalten Sie einen Überblick über die Integration von Security Information and Event Management (SIEM) Server mit Ihren Microsoft 365 Cloud-Diensten und-Anwendungen.
ms.openlocfilehash: d5adf0a72ac78475cb47f06732375ce01c0d72be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082194"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integration von Security Information and Event Management (SIEM) Server in Microsoft 365-Dienste und-Anwendungen

## <a name="summary"></a>Zusammenfassung

Verwendet oder plant Ihre Organisation einen Siem-Server (Security Information and Event Management)? Möglicherweise Fragen Sie sich, wie es in Microsoft 365 oder Office 365 integriert werden kann. Dieser Artikel enthält eine Liste der Ressourcen, die Sie zur Integration Ihres Siem-Servers in Microsoft 365-Dienste und-Anwendungen verwenden können.

> [!TIP]
> Wenn Sie noch keinen Siem-Server haben und Ihre Optionen untersuchen, sollten Sie sich **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** ansehen.

## <a name="do-i-need-a-siem-server"></a>Benötige ich einen Siem-Server?

Ob Sie einen Siem-Server benötigen, hängt von vielen Faktoren ab, beispielsweise von den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem sich Ihre Daten befinden. Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen erfüllen, ohne zusätzliche Server wie einen Siem-Server. Einige Organisationen haben spezielle Umstände, die die Verwendung eines Siem-Servers erfordern. Im Folgenden finden Sie einige Beispiele:

- *Fabrikam* verfügt über einige Inhalte und Anwendungen vor Ort und einige in der Cloud (Sie verfügen über eine hybride Cloud-Bereitstellung). Um Sicherheitsberichte über alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen Siem-Server implementiert. 

- *Contoso* ist eine Finanzdienstleistungsorganisation mit besonders strengen Sicherheitsanforderungen. Sie haben ihren Umgebungen einen Siem-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den Sie benötigen.

## <a name="siem-server-integration-with-microsoft-365"></a>Siem-Server Integration mit Microsoft 365

Ein Siem-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und-Anwendungen empfangen. In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und-Anwendungen zusammen mit Siem Server-Eingaben und Ressourcen aufgeführt, um weitere Informationen zu erhalten. 

| Microsoft 365-Dienst oder-Anwendung | Siem-Server-Eingänge/-Methoden | Ressourcen mit mehr Informationen |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md)  | Überwachungsprotokolle | [Siem-Integration mit Office 365 Advanced Threat Protection](siem-integration-with-office-365-ti.md) |
| [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | In Azure gehosteter HTTPS-Endpunkt <br/>REST-API| [Abrufen von Benachrichtigungen an Ihre Siem-Tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Protokoll Integration | [Siem-Integration in Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Schauen Sie sich [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)an. Azure Sentinel verfügt über Connectors für Microsoft-Lösungen. Diese Konnektoren sind "Out-of-the-Box" verfügbar und bieten eine Echtzeitintegration. Sie können Azure Sentinel mit Ihren Microsoft Threat Protection-Lösungen und Microsoft 365-Diensten verwenden, darunter Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security und vieles mehr.

### <a name="audit-logging-must-be-turned-on"></a>Die Überwachungsprotokollierung muss aktiviert sein.

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren. 

- Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security & Compliance Center aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Für Exchange Online [ist die Überwachungsprotokollierung mit Windows PowerShell aktiviert](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="more-resources"></a>Weitere Ressourcen

[Integrieren von Sicherheitslösungen im Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](https://docs.microsoft.com/graph/security-integration)
