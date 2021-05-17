---
title: SIEM-Serverintegration in Microsoft 365 und Anwendungen
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
description: Verschaffen Sie sich einen Überblick über die Integration von SieM-Servern (Security Information and Event Management) in Microsoft 365 cloud services and applications
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bea8aa3914da4b813f3928eddbb6df9c98ef6605
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599947"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integration von Sicherheitsinformationen und Ereignisverwaltungsservern in Microsoft 365 und Anwendungen

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Zusammenfassung

Verwendet oder plant Ihre Organisation, einen Sicherheitsinformations- und Ereignisverwaltungsserver (Security Information and Event Management, SIEM) zu erhalten? Sie fragen sich vielleicht, wie sie in Microsoft 365 oder Office 365. Dieser Artikel enthält eine Liste der Ressourcen, die Sie verwenden können, um Ihren SIEM-Server in Microsoft 365 und Anwendungen zu integrieren.

> [!TIP]
> Wenn Sie noch keinen SIEM-Server haben und Ihre Optionen erkunden, sollten Sie **[Microsoft Azure Sentinel verwenden.](/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Benötigen Sie einen SIEM-Server?

Ob Sie einen SIEM-Server benötigen, hängt von vielen Faktoren ab, z. B. den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem Sich Ihre Daten befinden. Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen ohne zusätzliche Server, z. B. einen SIEM-Server, erfüllen. Einige Organisationen haben spezielle Umstände, die die Verwendung eines SIEM-Servers erfordern. Hier sind einige Beispiele:

- *Fabrikam* verfügt über einige Inhalte und Anwendungen lokal und einige in der Cloud (sie verfügen über eine Hybrid-Cloud-Bereitstellung). Um Sicherheitsberichte für alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen SIEM-Server implementiert.

- *Contoso* ist eine Finanzdienstleisterorganisation, die besonders strenge Sicherheitsanforderungen hat. Sie haben ihrer Umgebung einen SIEM-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den sie benötigen.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-Serverintegration in Microsoft 365

Ein SIEM-Server kann Daten von einer Vielzahl von Microsoft 365 und Anwendungen empfangen. In der folgenden Tabelle sind verschiedene Microsoft 365 und Anwendungen sowie DIEM-Servereingaben und -ressourcen aufgeführt, um mehr zu erfahren.

****

|Microsoft 365 Dienst oder Anwendung|EINGABEN/Methoden des SIEM-Servers|Ressourcen mit mehr Informationen|
|---|---|---|
|[Microsoft Defender für Office 365](defender-for-office-365.md)|Überwachungsprotokolle|[SIEM-Integration in Microsoft Defender for Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender für Endpunkt](/windows/security/threat-protection/)|IN Azure gehosteter HTTPS-Endpunkt <p> REST-API|[Ziehen von Warnungen an Ihre SIEM-Tools](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Protokollintegration|[SIEM-Integration in Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Sehen Sie sich [Azure Sentinel an.](/azure/sentinel/overview) Azure Sentinel bietet Connectors für Microsoft-Lösungen. Diese Connectors sind "sofort verfügbar" und ermöglichen die Echtzeitintegration. Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, einschließlich Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und mehr.

### <a name="audit-logging-must-be-turned-on"></a>Überwachungsprotokollierung muss aktiviert sein

Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die SIEM-Serverintegration konfigurieren.

- Für SharePoint Online, OneDrive for Business und Azure Active Directory wird die Überwachungsprotokollierung im [Security & Compliance Center aktiviert.](../../compliance/turn-audit-log-search-on-or-off.md)

- Weitere Exchange Online finden Sie unter [Verwalten der Postfachüberwachung](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Weitere Ressourcen

[Integrieren von Sicherheitslösungen in Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)](/graph/security-integration)