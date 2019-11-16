---
title: Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Lesen Sie diesen Artikel, um einen Überblick über die Integration von Siem Server mit Microsoft 365 zu erhalten.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677508"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen

## <a name="summary"></a>Zusammenfassung

Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet oder wenn Sie einen Siem-Server bald erhalten möchten, Fragen Sie sich möglicherweise, wie sich das in Microsoft 365 oder Office 365 integrieren lässt. Dieser Artikel enthält eine Liste der Ressourcen, die Sie zum Einrichten der Integration von Siem Server mit Ihren Microsoft 365-Diensten und-Anwendungen verwenden können.

> [!TIP]
> Wenn Sie noch keinen Siem-Server haben und Ihre Optionen untersuchen, sollten Sie sich **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** ansehen.

## <a name="do-i-need-a-siem-server"></a>Benötige ich einen Siem-Server?

Ob Sie einen Siem-Server benötigen, hängt von vielen Faktoren ab, beispielsweise von den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem sich Ihre Daten befinden. Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen erfüllen, ohne zusätzliche Server wie einen Siem-Server. Einige Organisationen haben spezielle Umstände, die die Verwendung eines Siem-Servers erfordern. Im Folgenden finden Sie einige Beispiele:

- *Fabrikam* verfügt über einige Inhalte und Anwendungen vor Ort und einige in der Cloud (Sie verfügen über eine hybride Cloud-Bereitstellung). Um Sicherheitsberichte über alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen Siem-Server implementiert. 

- *Contoso* ist eine Finanzdienstleistungsorganisation mit besonders strengen Sicherheitsanforderungen. Sie haben ihren Umgebungen einen Siem-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den Sie benötigen.

## <a name="siem-server-integration-with-microsoft-365"></a>Siem-Server Integration mit Microsoft 365

Ein Siem-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und-Anwendungen empfangen. In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und-Anwendungen zusammen mit Siem Server-Eingaben und Ressourcen aufgeführt, um weitere Informationen zur Integration von Siem Server zu erhalten. 

| Microsoft 365-Dienst oder-Anwendung | Siem-Server Eingaben | Ressourcen mit mehr Informationen |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md)  | Überwachungsprotokolle | [Siem-Integration mit Office 365 Advanced Threat Protection](siem-integration-with-office-365-ti.md) |
| [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | In Azure gehosteter HTTPS-Endpunkt <br/>REST-API| [Abrufen von Benachrichtigungen an Ihre Siem-Tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Protokoll Integration | [Siem-Integration in Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Sehen Sie sich [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)an, der mit einer Reihe von Connectors für Microsoft-Lösungen ausgestattet ist, die sofort verfügbar sind und eine Echtzeitintegration bieten, einschließlich Microsoft Threat Protection-Lösungen und Microsoft 365-Quellen, einschließlich Office 365, Azure AD, Azure ATP und Microsoft Cloud-App-Sicherheit und vieles mehr.

### <a name="audit-logging-must-be-turned-on"></a>Die Überwachungsprotokollierung muss aktiviert sein.

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren. 

- Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security #a0 Compliance Center aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Für Exchange Online [ist die Überwachungsprotokollierung mit Windows PowerShell aktiviert](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="additional-resources"></a>Zusätzliche Ressourcen

[Integrieren von Sicherheitslösungen im Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](https://docs.microsoft.com/graph/security-integration)