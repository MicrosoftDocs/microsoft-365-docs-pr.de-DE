---
title: SIEM-Serverintegration in Microsoft 365-Dienste und -Anwendungen
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
description: Verschaffen Sie sich einen Überblick über die Integration von SieM-Servern (Security Information and Event Management) in Ihre Microsoft 365-Clouddienste und -Anwendungen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee164000d9a8dc9469097917658a88efe5cdc08c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064463"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integration von Sicherheitsinformationen und Ereignisverwaltungsservern in Microsoft 365-Dienste und -Anwendungen

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Zusammenfassung

Verwendet oder plant Ihre Organisation, einen Sicherheitsinformations- und Ereignisverwaltungsserver (Security Information and Event Management, SIEM) zu erhalten? Sie fragen sich vielleicht, wie es in Microsoft 365 oder Office 365 integriert wird. Dieser Artikel enthält eine Liste der Ressourcen, die Sie verwenden können, um Ihren SIEM-Server in Microsoft 365-Dienste und -Anwendungen zu integrieren.

> [!TIP]
> Wenn Sie noch keinen SIEM-Server haben und Ihre Optionen erkunden, ziehen Sie **[Microsoft Azure Sentinel in Betracht.](/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Benötigen Sie einen SIEM-Server?

Ob Sie einen SIEM-Server benötigen, hängt von vielen Faktoren ab, z. B. den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem Sich Ihre Daten befinden. Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen ohne zusätzliche Server erfüllen, z. B. einen SIEM-Server. Einige Organisationen haben spezielle Umstände, die die Verwendung eines SIEM-Servers erfordern. Im Folgenden finden Sie einige Beispiele:

- *Fabrikam* verfügt über einige Inhalte und Anwendungen lokal und einige in der Cloud (sie verfügen über eine Hybrid-Cloud-Bereitstellung). Um Sicherheitsberichte für alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen SIEM-Server implementiert.

- *Contoso* ist eine Finanzdienstleisterorganisation, die besonders strenge Sicherheitsanforderungen hat. Sie haben ihrer Umgebung einen SIEM-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den sie benötigen.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-Serverintegration in Microsoft 365

Ein SIEM-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und -Anwendungen empfangen. In der folgenden Tabelle sind verschiedene Microsoft 365-Dienste und -Anwendungen sowie SIEM-Servereingaben und -ressourcen aufgeführt, um mehr zu erfahren.

****

|Microsoft 365-Dienst oder -Anwendung|EINGABEN/Methoden des SIEM-Servers|Ressourcen mit mehr Informationen|
|---|---|---|
|[Microsoft Defender für Office 365](defender-for-office-365.md)|Überwachungsprotokolle|[SIEM-Integration in Microsoft Defender für Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/)|IN Azure gehosteter HTTPS-Endpunkt <p> REST-API|[Ziehen von Warnungen an Ihre SIEM-Tools](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Protokollintegration|[SIEM-Integration in Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Sehen Sie sich [Azure Sentinel an.](/azure/sentinel/overview) Azure Sentinel bietet Connectors für Microsoft-Lösungen. Diese Connectors sind "sofort verfügbar" und ermöglichen die Echtzeitintegration. Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, einschließlich Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und mehr.

### <a name="audit-logging-must-be-turned-on"></a>Überwachungsprotokollierung muss aktiviert sein

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die SIEM-Serverintegration konfigurieren.

- Für SharePoint Online, OneDrive for Business und Azure Active Directory ist die Überwachungsprotokollierung im [Security & Compliance Center aktiviert.](../../compliance/turn-audit-log-search-on-or-off.md)

- Informationen zu Exchange Online finden Sie unter [Verwalten der Postfachüberwachung](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Weitere Ressourcen

[Integrieren von Sicherheitslösungen in Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](/graph/security-integration)