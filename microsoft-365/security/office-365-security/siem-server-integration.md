---
title: SIEM-Serverintegration mit Microsoft 365 Diensten und Anwendungen
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Hier erhalten Sie eine Übersicht über die Integration von SIEM-Servern (Security Information and Event Management) in Ihre Microsoft 365 Clouddienste und -anwendungen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8b9c17ba2dcefa65b60a53ab8bff405de4850fc0
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929791"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Siem-Serverintegration (Security Information and Event Management) in Microsoft 365 Dienste und Anwendungen

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Zusammenfassung

Verwendet Oder plant Ihre Organisation, einen SIEM-Server (Security Information and Event Management) zu erhalten? Sie fragen sich vielleicht, wie sie in Microsoft 365 oder Office 365 integriert wird. Dieser Artikel enthält eine Liste der Ressourcen, die Sie verwenden können, um Ihren SIEM-Server in Microsoft 365 Dienste und Anwendungen zu integrieren.

> [!TIP]
> Wenn Sie noch keinen SIEM-Server haben und Ihre Optionen erkunden, sollten Sie **[Microsoft Azure Sentinel](/azure/sentinel/overview)** in Betracht ziehen.

## <a name="do-i-need-a-siem-server"></a>Benötisiere ich einen SIEM-Server?

Ob Sie einen SIEM-Server benötigen, hängt von vielen Faktoren ab, z. B. den Sicherheitsanforderungen Ihrer Organisation und dem Speicherort Ihrer Daten. Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen ohne zusätzliche Server erfüllen, z. B. einen SIEM-Server. Einige Organisationen haben besondere Umstände, die die Verwendung eines SIEM-Servers erfordern. Im Folgenden finden Sie einige Beispiele:

- *Fabrikam* verfügt über lokale Inhalte und Anwendungen und einige in der Cloud (sie verfügen über eine Hybrid-Cloudbereitstellung). Um Sicherheitsberichte über alle Inhalte und Anwendungen hinweg zu erhalten, hat Fabrikam einen SIEM-Server implementiert.

- *Contoso* ist eine Finanzdienstleistungsorganisation mit besonders strengen Sicherheitsanforderungen. Sie haben ihrer Umgebung einen SIEM-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den sie benötigen.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-Serverintegration in Microsoft 365

Ein SIEM-Server kann Daten aus einer Vielzahl von Microsoft 365 Diensten und Anwendungen empfangen. In der folgenden Tabelle sind mehrere Microsoft 365 Dienste und Anwendungen sowie SIEM-Servereingaben und Ressourcen aufgeführt, um mehr zu erfahren.

****

|Microsoft 365 Dienst oder Anwendung|SIEM-Servereingaben/-methoden|Ressourcen mit mehr Informationen|
|---|---|---|
|[Microsoft Defender für Office 365](defender-for-office-365.md)|Überwachungsprotokolle|[SIEM-Integration in Microsoft Defender für Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender für Endpunkt](/windows/security/threat-protection/)|IN Azure gehosteter HTTPS-Endpunkt <p> REST-API|[Abrufen von Warnungen an Ihre SIEM-Tools](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Protokollintegration|[SIEM-Integration in Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Werfen Sie einen Blick auf [Azure Sentinel.](/azure/sentinel/overview) Azure Sentinel enthält Connectors für Microsoft-Lösungen. Diese Connectors sind sofort verfügbar und ermöglichen die Integration in Echtzeit. Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, einschließlich Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und mehr.

### <a name="audit-logging-must-be-turned-on"></a>Überwachungsprotokollierung muss aktiviert sein

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die SIEM-Serverintegration konfigurieren.

- Bei SharePoint Online-, OneDrive for Business- und Azure Active Directory ist [die Überwachungsprotokollierung im Microsoft 365 Defender-Portal aktiviert.](../../compliance/turn-audit-log-search-on-or-off.md)

- Informationen Exchange Online finden Sie unter Verwalten der [Postfachüberwachung.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Weitere Ressourcen

[Integrieren von Sicherheitslösungen in Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](/graph/security-integration)