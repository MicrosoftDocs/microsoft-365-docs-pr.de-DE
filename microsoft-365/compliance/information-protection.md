---
title: Microsoft Information Protection in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Implementieren Sie Microsoft Information Protection (MIP), damit Sie vertrauliche Informationen überall dort schützen können, wo Sie leben oder Reisen.
ms.openlocfilehash: 89a11a8b94d38978a48fbc414ab5fe47fcf977a5
ms.sourcegitcommit: ca733da1ed919b286a93068b560608e82f8def05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48990540"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365

>*[Lizenzierung für Microsoft 365 Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementieren Sie Microsoft Information Protection (MIP), damit Sie vertrauliche Informationen überall dort, wo Sie leben oder Reisen, erkennen, klassifizieren und schützen können.

Die MIP-Funktionen sind in der Microsoft 365-Konformität enthalten und bieten Ihnen die Tools, um [Ihre Daten zu kennen](#know-your-data), [Ihre Daten zu schützen](#protect-your-data)und [Datenverlust zu verhindern](#prevent-data-loss).

![Abbildung der Unterstützung beim ermitteln, klassifizieren und Schützen vertraulicher Daten mithilfe von MIP](../media/powered-by-intelligent-platform.png)

Informationen zum Steuern ihrer Daten finden Sie unter [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Kennen Sie Ihre Daten

Um Ihre Datenlandschaft zu verstehen und wichtige Daten in ihrer Hybridumgebung zu identifizieren, verwenden Sie die folgenden Funktionen:
 
|Funktion|Welche Probleme werden behoben?|Erste Schritte|
|:------|:------------|:--------------------|:-----------------------------|
|[Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)| Identifiziert vertrauliche Daten mithilfe integrierter oder benutzerdefinierter regulärer Ausdrücke oder einer Funktion, zusammen mit Bestätigungs beweisen, die Schlüsselwörter, Konfidenz Stufen und Nähe enthalten.| [Anpassen eines benutzerdefinierten vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md)|
|[Trainierbare Klassifizierer (Vorschau)](classifier-learn-about.md)| Klassifizieren von Daten für Sie, indem Sie eine der integrierten Klassifizierungen verwenden oder eine Klassifizierung mit Ihrem eigenen Inhalt trainieren | [Erste Schritte mit trainierbaren Klassifizierern (Vorschau)](classifier-get-started-with.md) |
|[Datenklassifikation](data-classification-overview.md) | Identifiziert Elemente, die eine Vertraulichkeits Bezeichnung, eine Aufbewahrungs Bezeichnung aufweisen oder als vertraulicher Informationstyp in Ihrer Organisation klassifiziert wurden, sowie die Aktionen, die Ihre Benutzer für diese Unternehmen.  | [Erste Schritte mit dem Inhalts-Explorer](data-classification-content-explorer.md)<br /><br /> [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Schützen Sie Ihre Daten

Verwenden Sie die folgenden Funktionen, um flexible Schutzaktionen wie Verschlüsselung, Zugriffseinschränkungen und visuelle Markierungen anzuwenden:

|Funktion|Welche Probleme werden behoben?|Erste Schritte|
|:------|:------------|---------------------|:----------------------------|
|[Vertraulichkeitsbezeichnungen](sensitivity-labels.md)| Eine einzelne Lösung für apps, Dienste und Geräte zum bezeichnen und Schützen Ihrer Daten beim Reisen innerhalb und außerhalb Ihrer Organisation <br /><br />Beispielszenario: [anwenden und Anzeigen von Sensitivitäts Bezeichnungen in Power BI und schützen der Daten beim Export](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[ Erste Schritte mit Sensitivitäts Bezeichnungen](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Für Windows-Computer werden die Vertraulichkeits Bezeichnungen für zusätzliche Features und Funktionen erweitert, die das bezeichnen und schützen aller Dateitypen im Datei-Explorer und in PowerShell umfassen.<br /><br /> Beispiel zusätzliche Features: [benutzerdefinierte Konfigurationen für den Azure Information Protection Unified Labeling-Client](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection Unified Labeling-Client Administratorhandbuch](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Verschlüsselung mit Doppelschlüssel](double-key-encryption.md)| Unter allen Umständen können nur Sie geschützte Inhalte entschlüsseln, oder für behördliche Anforderungen müssen Sie Verschlüsselungsschlüssel in einer geografischen Grenze halten. | [Bereitstellen der doppelten Schlüssel Verschlüsselung](double-key-encryption.md#deploy-dke)|
|[Office 365 Nachrichtenverschlüsselung (OEM)](ome.md)| Verschlüsselt e-Mail-Nachrichten und angefügte Dokumente, die an einen beliebigen Benutzer auf einem Gerät gesendet werden, sodass nur autorisierte Empfänger e-Mail-Informationen lesen können.  <br /><br />Beispielszenario: [widerrufen von e-Mails, die durch erweiterte Nachrichtenverschlüsselung verschlüsselt wurden](revoke-ome-encrypted-mail.md) | [Einrichten neuer Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)|
|[Dienstverschlüsselung mit dem Kundenschlüssel](customer-key-overview.md) | Schützt vor dem Anzeigen von Daten durch nicht autorisierte Systeme oder Mitarbeiter und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren | [Einrichten des Kundenschlüssels für Office 365](customer-key-set-up.md)|
|[Verwaltung von SharePoint-Informationsrechten (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Schützt SharePoint-Listen und-Bibliotheken so, dass beim Auschecken eines Dokuments die heruntergeladene Datei geschützt ist, sodass nur autorisierte Benutzer die Datei gemäß den von Ihnen angegebenen Richtlinien anzeigen und verwenden können | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Rights Management-Verbindungsdienst](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Schutz nur für vorhandene lokale Bereitstellungen, die Exchange oder SharePoint Server verwenden, oder Dateiserver, auf denen Windows Server und die Dateiklassifizierungsinfrastruktur (FCI) ausgeführt werden | [Schritte zum Bereitstellen des RMS-Connectors](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection Unified-Beschriftungs Scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Erkennt, Bezeichnungs-und schützt vertrauliche Informationen, die sich in lokalen Daten speichern befinden. | [Konfigurieren und Installieren des einheitlichen Bezeichnungs Scanners für Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Erkennt, Bezeichnungs-und schützt vertrauliche Informationen, die sich in Daten speichern befinden, die sich in der Cloud befinden. | [Ermitteln, Klassifizieren, Bezeichnen und Schützen regulierter und sensibler Daten, die in der Cloud gespeichert werde](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Erweiterte Vertraulichkeits Bezeichnungen auf apps und Dienste von Drittanbietern  <br /><br /> Beispielszenario: [festlegen und Abrufen einer Vertraulichkeits Bezeichnung (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Setup und Konfiguration des Microsoft Information Protection (MIP)-SDKs](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Datenverlust verhindern

Um eine versehentliche übermäßige Freigabe vertraulicher Informationen zu verhindern, verwenden Sie die folgenden Funktionen:


|Funktion|Welche Probleme werden behoben?|Erste Schritte|
|:------|:------------|:---------------------|:-----------------------------|
|[Verhinderung von Datenverlust (DLP)](data-loss-prevention-policies.md)| Verhindert die unbeabsichtigte Freigabe vertraulicher Elemente <br /><br />Beispielszenario: [Schützen vertraulicher Informationen in Microsoft Teams-Chat-und Kanal Nachrichten](dlp-microsoft-teams.md) | [Erste Schritte mit der standardmäßigen DLP-Richtlinie](get-started-with-the-default-dlp-policy.md)|
|[Informationen zur Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-learn-about.md)| Erweiterte DLP-Funktionen auf Elemente, die auf Windows 10-Computern verwendet und gemeinsam genutzt werden | [Verhinderung von Datenverlust am Endpunkt – Erste Schritte](endpoint-dlp-getting-started.md)|
