---
title: Microsoft Information Protection in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implementieren Sie Microsoft Information Protection (MIP), um vertrauliche Informationen unabhängig davon, wo sie sich befinden oder unterwegs sind, zu schützen.
ms.openlocfilehash: 36e8e917349edd5523677112818cd39514710583
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114361"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365

>*[Lizenzierung von Microsoft 365 Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementieren Sie Microsoft Information Protection (MIP), um vertrauliche Informationen unabhängig davon, wo sie sich befinden oder unterwegs sind, zu finden, zu klassifizieren und zu schützen.

Die MIP-Funktionen sind in Microsoft 365 Compliance enthalten und bieten Ihnen die erforderlichen Instrumente, um [Ihre Daten zu kennen](#know-your-data), [sie zu schützen ](#protect-your-data)und [Datenverlust zu verhindern](#prevent-data-loss).

![Darstellung dazu, wie MIP beim Auffinden, Klassifizieren und Schützen vertraulicher Daten hilft.](../media/powered-by-intelligent-platform.png)

Informationen zum Kontrolle Ihrer Daten finden Sie unter [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Kennen Sie Ihre Daten

> [!NOTE]
> Informationen zum Klassifizieren und Beschriften von Daten in Azure Purview (aktuell als Vorschau) finden Sie unter [Automatische Beschriftung Ihrer Inhalte in Azure Purview](/azure/purview/create-sensitivity-label).
> 
> Releaseankündigungen zu Azure Purview finden Sie in den folgenden Blogbeiträgen: [Microsoft Information Protection and Microsoft Azure Purview: Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) und [Azure Purview at Spring Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).


Verwenden Sie die folgenden Funktionen, um Ihre Datenlandschaft zu verstehen und wichtige Daten in Ihrer Hybridumgebung zu ermitteln:
 
|Funktion|Welches Probleme löst es für Sie?|Erste Schritte|
|:------|:------------|:--------------------|
|[Typen vertraulicher Informationen](sensitive-information-type-learn-about.md)| Identifiziert vertrauliche Daten mithilfe von integrierten oder benutzerdefinierten regulären Ausdrücken oder einer Funktion. Bestätigende Beweise umfassen Stichwörter, Konfidenzniveaus und Nähe.| [Anpassen eines integrierten, vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md)|
|[Trainierbare Klassifizierer](classifier-learn-about.md)| Identifiziert vertrauliche Daten anhand von Beispielen für die Daten, an denen Sie interessiert sind, anstatt Elemente im Objekt zu identifizieren (Mustervergleich). Sie können integrierte Klassifizierer verwenden oder einen Klassifizierer mit Ihren eigenen Inhalten trainieren.| [Erste Schritte mit trainierbaren Klassifizierern](classifier-get-started-with.md) |
|[Datenklassifizierung](data-classification-overview.md) | Eine grafische Kennzeichnung von Objekten in Ihrer Organisation, die eine Vertraulichkeitsbezeichnung oder eine Aufbewahrungskennzeichnung haben oder klassifiziert wurden. Sie können diese Informationen auch verwenden, um Insights in die Aktionen zu erhalten, die Ihre Benutzer auf diesen Objekten ausführen. | [Erste Schritte mit dem Inhalts-Explorer](data-classification-content-explorer.md)<br /><br /> [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Schützen Sie Ihre Daten

Verwenden Sie die folgenden Funktionen, um flexible Schutzmaßnahmen wie Verschlüsselung, Zugriffsbeschränkungen und visuelle Markierungen anzuwenden:

|Funktion|Welches Probleme löst es für Sie?|Erste Schritte|
|:------|:------------|---------------------|
|[Vertraulichkeitsbezeichnungen](sensitivity-labels.md)| Eine einzige Lösung über Apps, Dienste und Geräte hinweg, um Ihre Daten zu kennzeichnen und zu schützen, während sie innerhalb und außerhalb Ihres Unternehmens übertragen werden. <br /><br />Beispielszenarien: <br /> [Verwalten von Vertraulichkeitsbezeichnungen für Office-Apps](sensitivity-labels-office-apps.md)<br /> [Verschlüsseln von Dokumenten und E-Mails](encryption-sensitivity-labels.md )<br /> [Anwenden und Anzeigen von Bezeichnungen in Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> Eine umfassende Liste von Szenarien für Vertraulichkeitsbezeichnungen finden Sie in der Dokumentation „Erste Schritte“.|[Erste Schritte mit Vertraulichkeitsbezeichnungen](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection-Client für einheitliche Bezeichnungen](/azure/information-protection/rms-client/aip-clientv2)| Erweitert auf Windows-Computern die Vertraulichkeitsbezeichnungen für zusätzliche Features und Funktionen, die das Bezeichnen und Schützen aller Dateitypen aus dem Datei-Explorer und PowerShell umfassen.<br /><br /> Beispiel für zusätzliche Features: [Benutzerdefinierte Konfigurationen für den Azure Information Protection-Client für einheitliche Bezeichnungen](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection-Client für einheitliche Bezeichnungen – Leitfaden für Administratoren](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Verschlüsselung mit Doppelschlüssel](double-key-encryption.md)| Unabhängig von den Umständen kann nur Ihre Organisation geschützte Inhalte entschlüsseln, und im Falle behördlicher Vorschriften müssen die Verschlüsselungsschlüssel innerhalb einer geographischen Region aufbewahrt werden. | [Bereitstellen der Verschlüsselung mit Doppelschlüssel](double-key-encryption.md#deploy-dke)|
|[Office 365-Nachrichtenverschlüsselung (OME)](ome.md)| Verschlüsselt E-Mail-Nachrichten und angefügte Dokumente, die an einen beliebigen Benutzer auf einem beliebigen Gerät gesendet werden, sodass nur autorisierte Empfänger die gesendeten Informationen lesen können.  <br /><br />Beispielszenario: [Widerrufen von E-Mails, die von der erweiterten Nachrichtenverschlüsselung verschlüsselt wurden](revoke-ome-encrypted-mail.md) | [Einrichten neuer Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)|
|[Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md) | Schützt vor der Anzeige von Daten durch nicht autorisierte Systeme oder das Personal und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren. | [Einrichten des Kundenschlüssels für Office 365](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Schützt SharePoint-Listen und -Bibliotheken so, dass wenn ein Benutzer ein Dokument auscheckt, die heruntergeladene Datei geschützt ist und nur von autorisierten Personen und entsprechend den von Ihnen festgelegten Richtlinien angezeigt und verwendet werden kann. | [Einrichten von Information Rights Management (IRM) im SharePoint Admin Center](set-up-irm-in-sp-admin-center.md)|
[Rights Management-Connector](/azure/information-protection/deploy-rms-connector) |Nur Schutz für vorhandene lokale Bereitstellungen, die Exchange- oder SharePoint-Server verwenden, oder Dateiserver, auf denen Windows Server und Dateiklassifizierungsinfrastruktur (File Classification Infrastructure, FCI) ausgeführt wird. | [Schritte zum Bereitstellen des RMS-Connectors](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection-Scanner für einheitliche Bezeichnungen](/azure/information-protection/deploy-aip-scanner)| Erkennt, kennzeichnet und schützt vertrauliche Informationen, die sich in lokalen Datenspeichern befinden. | [Konfigurieren und Installieren des Azure Information Protection-Scanners für einheitliche Bezeichnungen](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Erkennt, kennzeichnet und schützt vertrauliche Informationen, die sich in Datenspeichern in der Cloud befinden. | [Ermitteln, Klassifizieren, Bezeichnen und Schützen regulierter und vertraulicher Daten, die in der Cloud gespeichert sind](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection-SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|Erweitert Vertraulichkeitsbezeichnungen auf Drittanbieter-Apps und -Dienste.  <br /><br /> Beispielszenario: [Festlegen und Abrufen einer Vertraulichkeitsbezeichnung ( C++ )](/information-protection/develop/quick-file-set-get-label-cpp) |[Setup und Konfiguration des Microsoft Information Protection (MIP)-SDKs](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Verhindern von Datenverlust

Verwenden Sie die folgenden Funktionen, um die versehentliche Freigabe vertraulicher Informationen zu verhindern:


|Funktion|Welches Probleme löst es für Sie?|Erste Schritte|
|:------|:------------|:---------------------|
|[Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)| Hilft, die unbeabsichtigte Freigabe von vertraulichen Elementen zu verhindern. | [Erste Schritte mit der standardmäßigen DLP-Richtlinie](get-started-with-the-default-dlp-policy.md)|
|[Informationen zu Endpunkt-DLP](endpoint-dlp-learn-about.md)| Erweitert die DLP-Funktionen auf Elemente, die auf Windows 10-Computern verwendet und freigegeben werden. | [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md)|
|[Erfahren Sie mehr über die Microsoft Compliance-Erweiterung (Vorschau)](dlp-chrome-learn-about.md) | Erweitert DLP-Funktionen im Chrome-Browser | [Erste Schritte mit der Microsoft Compliance Erweiterung (Vorschau)](dlp-chrome-get-started.md)|
|[Informationen zum lokalen Microsoft 365-DLP-Scanner (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)](dlp-on-premises-scanner-learn.md)|Erweitert die DLP-Überwachung von Dateiaktivitäten und Schutzaktionen für diese Dateien auf lokale Dateifreigaben sowie SharePoint-Ordner und Dokumentbibliotheken.|[Erste Schritte mit dem lokalen Microsoft 365-DLP-Scanner (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)](dlp-on-premises-scanner-get-started.md)|
|[Schutz vertraulicher Informationen in Microsoft Teams-Chat- und Kanalnachrichten](dlp-microsoft-teams.md) | Erweitert einige DLP-Funktionen auf Teamchats und Kanalnachrichten | [Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>Zusätzliche Ressourcen

Viele Organisationen verwenden diese Informationsschutzfunktionen, um die Datenschutzbestimmungen einzuhalten. Um Sie dabei zu unterstützen, haben wir einen Workflow entwickelt, der Sie durch einen End-to-End-Prozess zur Planung und Implementierung von Funktionen in Microsoft 365 führt, einschließlich sicherem Zugriff, Bedrohungsschutz, Informationsschutz und Data Governance. Weiter Informationen finden Sie unter [Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 

Um Sie bei der Planung einer integrierten Strategie für die Implementierung von Informationsschutzfunktionen zu unterstützen, können Sie zusätzlich die Illustrationen zu den *Microsoft 365-Funktionen für Informationsschutz und Compliance* herunterladen.  Sie können diese Illustrationen für Ihren eigenen Gebrauch anpassen.

| Element | Beschreibung |
|:-----|:------------|
|[![Modellposter: Funktionen von Microsoft 365 Informationsschutz und Compliance](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [Als PDF herunterladen](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Als Visio herunterladen](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japanisch: [Als PDF herunterladen](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Als Visio herunterladen](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Aktualisiert im Oktober 2020|Enthält: <ul><li>  Microsoft Information Protection und Verhinderung von Datenverlust</li><li>Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen </li><li>Informationsbarrieren</li><li>Kommunikationscompliance</li><li>Insider-Risikomanagement</li><li>Datenerfassung durch Drittanbieter</li>|