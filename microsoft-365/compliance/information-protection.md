---
title: Microsoft Information Protection in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: Implementieren Sie Microsoft Information Protection (MIP), um vertrauliche Informationen unabhängig davon, wo sie sich befinden oder unterwegs sind, zu schützen.
ms.openlocfilehash: 2a1ec47ce888dc6d31868d65f9c4c113fa9b968c
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709507"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365

>*[Lizenzierung von Microsoft 365 Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementieren Sie Microsoft Information Protection (MIP), um vertrauliche Informationen unabhängig davon, wo sie sich befinden oder unterwegs sind, zu finden, zu klassifizieren und zu schützen.

Die MIP-Funktionen sind in Microsoft 365 Compliance enthalten und bieten Ihnen die erforderlichen Instrumente, um [Ihre Daten zu kennen](#know-your-data), [sie zu schützen ](#protect-your-data)und [Datenverlust zu verhindern](#prevent-data-loss).

![Darstellung dazu, wie MIP beim Auffinden, Klassifizieren und Schützen vertraulicher Daten hilft.](../media/powered-by-intelligent-platform.png)

Informationen zum Kontrolle Ihrer Daten finden Sie unter [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Kennen Sie Ihre Daten

> [!NOTE]
> Informationen zum Klassifizieren und Beschriften von Daten in Azure Purview (aktuell als Vorschau) finden Sie unter [Automatische Beschriftung Ihrer Inhalte in Azure Purview](https://docs.microsoft.com/azure/purview/create-sensitivity-label).
> 
> Informationen zu diesem neuen Release finden Sie im Blogbeitrag [Microsoft Information Protection and Microsoft Azure Purview: Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481).



Verwenden Sie die folgenden Funktionen, um Ihre Datenlandschaft zu verstehen und wichtige Daten in Ihrer Hybridumgebung zu ermitteln:
 
|Funktion|Welches Probleme löst es für Sie?|Erste Schritte|
|:------|:------------|:--------------------|:-----------------------------|
|[Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)| Identifiziert vertrauliche Daten mithilfe von integrierten oder benutzerdefinierten regulären Ausdrücken oder einer Funktion, zusammen mit bestätigenden Belegen, die Stichwörter, Konfidenzniveau und Nähe umfassen.| [Anpassen eines benutzerdefinierten vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md)|
|[Trainierbare Klassifizierer (Vorschau)](classifier-learn-about.md)| Klassifiziert Daten für Sie mit einer der integrierten Klassifizierungen oder trainiert eine Klassifizierung anhand Ihrer Inhalte. | [Erste Schritte mit trainierbaren Klassifizierern (Vorschau)](classifier-get-started-with.md) |
|[Datenklassifizierung](data-classification-overview.md) | Identifiziert Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden sowie die daran durch Ihre Benutzer vorgenommenen Aktionen.  | [Erste Schritte mit dem Inhalts-Explorer](data-classification-content-explorer.md)<br /><br /> [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Schützen Sie Ihre Daten

Verwenden Sie die folgenden Funktionen, um flexible Schutzmaßnahmen wie Verschlüsselung, Zugriffsbeschränkungen und visuelle Markierungen anzuwenden:

|Funktion|Welches Probleme löst es für Sie?|Erste Schritte|
|:------|:------------|---------------------|:----------------------------|
|[Vertraulichkeitsbezeichnungen](sensitivity-labels.md)| Eine einzige Lösung über Apps, Dienste und Geräte hinweg, um Ihre Daten zu kennzeichnen und zu schützen, während sie innerhalb und außerhalb Ihres Unternehmens unterwegs sind. <br /><br />Beispielszenario: [Anwenden und Anzeigen von Bezeichnungen in Power BI und Schutz der Daten beim Speichern außerhalb des Diensts](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Erste Schritte mit Vertraulichkeitsbezeichnungen](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Erweitert auf Windows-Computern die Vertraulichkeitsbezeichnungen für zusätzliche Features und Funktionen, die das Bezeichnen und Schützen aller Dateitypen aus dem Datei-Explorer und PowerShell umfassen.<br /><br /> Beispiel für zusätzliche Features: [Benutzerdefinierte Konfigurationen für den Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection-Client für einheitliche Bezeichnungen – Leitfaden für Administratoren](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Verschlüsselung mit Doppelschlüssel](double-key-encryption.md)| Nur Sie können geschützte Inhalte entschlüsseln, und im Falle behördlicher Vorschriften müssen die Verschlüsselungsschlüssel innerhalb einer geographischen Region aufbewahrt werden. | [Bereitstellen der Verschlüsselung mit Doppelschlüssel](double-key-encryption.md#deploy-dke)|
|[Office 365-Nachrichtenverschlüsselung (OME)](ome.md)| Verschlüsselt E-Mail-Nachrichten und angefügte Dokumente, die an einen beliebigen Benutzer an einem beliebigen Gerät gesendet werden, sodass nur autorisierte Empfänger die gesendeten Informationen lesen können.  <br /><br />Beispielszenario: [Widerrufen von E-Mails, die von der erweiterten Nachrichtenverschlüsselung verschlüsselt wurden](revoke-ome-encrypted-mail.md) | [Einrichten neuer Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)|
|[Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md) | Schützt vor der Anzeige von Daten durch nicht autorisierte Systeme oder Personen und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren. | [Einrichten des Kundenschlüssels für Office 365](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Schützt SharePoint-Listen und -Bibliotheken so, dass wenn ein Benutzer ein Dokument auscheckt, die heruntergeladene Datei nur von autorisierten Personen und entsprechend den von Ihnen festgelegten Richtlinien angezeigt und verwendet werden kann. | [Einrichten von Information Rights Management (IRM) im SharePoint Admin Center](set-up-irm-in-sp-admin-center.md)|
[Rights Management-Connector](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Nur Schutz für vorhandene lokale Bereitstellungen, die Exchange oder SharePoint Server verwenden, oder Dateiserver, auf denen die Windows Server- und Dateiklassifizierungsinfrastruktur (File Classification Infrastructure FCI) ausgeführt wird. | [Schritte zum Bereitstellen des RMS-Connectors](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection-Scanner für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Erkennt, kennzeichnet und schützt vertrauliche Informationen, die sich in lokalen Datenspeichern befinden. | [Konfigurieren und Installieren des Azure Information Protection-Scanners für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Erkennt, kennzeichnet und schützt vertrauliche Informationen, die sich in Datenspeichern in der Cloud befinden. | [Ermitteln, Klassifizieren, Bezeichnen und Schützen regulierter und vertraulicher Daten, die in der Cloud gespeichert sind](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection-SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Erweitert Vertraulichkeitsbezeichnungen auf Drittanbieter-Apps und -Dienste.  <br /><br /> Beispielszenario: [Festlegen und Abrufen einer Vertraulichkeitsbezeichnung ( C++ )](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Setup und Konfiguration des Microsoft Information Protection (MIP)-SDKs](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Verhindern von Datenverlust

Verwenden Sie die folgenden Funktionen, um die versehentliche Freigabe vertraulicher Informationen zu verhindern:


|Funktion|Welches Probleme löst es für Sie?|Erste Schritte|
|:------|:------------|:---------------------|:-----------------------------|
|[Verhinderung von Datenverlust (Data Loss Prevention, DLP)](data-loss-prevention-policies.md)| Hilft, die unbeabsichtigte Freigabe von vertraulichen Elementen zu verhindern. <br /><br />Beispielszenario: [Schutz vertraulicher Informationen in Microsoft Teams-Chat- und Kanalnachrichten](dlp-microsoft-teams.md) | [Erste Schritte mit der standardmäßigen DLP-Richtlinie](get-started-with-the-default-dlp-policy.md)|
|[Informationen zu Endpunkt-DLP](endpoint-dlp-learn-about.md)| Erweitert die DLP-Funktionen auf Elemente, die auf Windows 10-Computern verwendet und gemeinsam genutzt bzw. freigegeben werden | [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md)|
