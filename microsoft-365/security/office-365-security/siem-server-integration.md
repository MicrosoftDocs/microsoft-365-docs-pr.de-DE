---
title: Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen
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
- seo-marvel-apr2020
description: Erhalten Sie einen Überblick über die Integration von Security Information and Event Management (SIEM) Server mit Ihren Microsoft 365 Cloud-Diensten und-Anwendungen.
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919764"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integration von Security Information and Event Management (SIEM) Server in Microsoft 365-Dienste und-Anwendungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


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

****

|Microsoft 365-Dienst oder-Anwendung|Siem-Server-Eingänge/-Methoden|Ressourcen mit mehr Informationen|
|---|---|---|
|[Microsoft Defender für Office 365](office-365-atp.md)|Überwachungsprotokolle|[Siem-Integration mit Microsoft Defender für Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/)|In Azure gehosteter HTTPS-Endpunkt <br/>REST-API|[Abrufen von Benachrichtigungen an Ihre Siem-Tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Protokoll Integration|[Siem-Integration in Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Schauen Sie sich [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)an. Azure Sentinel verfügt über Connectors für Microsoft-Lösungen. Diese Konnektoren sind "Out-of-the-Box" verfügbar und bieten eine Echtzeitintegration. Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, darunter Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und vieles mehr.

### <a name="audit-logging-must-be-turned-on"></a>Die Überwachungsprotokollierung muss aktiviert sein.

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren.

- Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security & Compliance Center aktiviert](../../compliance/turn-audit-log-search-on-or-off.md).

- Informationen zu Exchange Online finden Sie unter [Verwalten der postfachüberwachung](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Weitere Ressourcen

[Integrieren von Sicherheitslösungen in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](https://docs.microsoft.com/graph/security-integration)
