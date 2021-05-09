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
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259298"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365

>*[Lizenzierung von Microsoft 365 Security & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementieren Sie Microsoft Information Protection (MIP), um vertrauliche Informationen unabhängig davon, wo sie sich befinden oder unterwegs sind, zu finden, zu klassifizieren und zu schützen.

Die MIP-Funktionen sind in Microsoft 365 Compliance enthalten und bieten Ihnen die erforderlichen Instrumente, um [Ihre Daten zu kennen](#know-your-data), [sie zu schützen ](#protect-your-data)und [Datenverlust zu verhindern](#prevent-data-loss).

![Darstellung dazu, wie MIP beim Auffinden, Klassifizieren und Schützen vertraulicher Daten hilft.](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="Kennen Sie Ihre Daten":::

Informationen zum Kontrolle Ihrer Daten finden Sie unter [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Kennen Sie Ihre Daten

> [!NOTE]
> Informationen zum Klassifizieren und Beschriften von Daten in Azure Purview (aktuell als Vorschau) finden Sie unter [Automatische Beschriftung Ihrer Inhalte in Azure Purview](/azure/purview/create-sensitivity-label).
> 
> Releaseankündigungen zu Azure Purview finden Sie in den folgenden Blogbeiträgen: [Microsoft Information Protection and Microsoft Azure Purview: Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) und [Azure Purview at Spring Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).

Verwenden Sie die folgenden Funktionen, um Ihre Datenlandschaft zu verstehen und wichtige Daten in Ihrer Hybridumgebung zu ermitteln:

:::image type="content" source="../media/knowyourdata-new.png" alt-text="Kennen Sie Ihre Daten"::: 


|**Funktionalität**|**Welche Probleme werden gelöst?**|**Erste Schritte**|**Lizenzierung**|
|--|--|--|--|
|[Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)| Identifiziert vertrauliche Daten mithilfe von integrierten oder benutzerdefinierten regulären Ausdrücken oder einer Funktion, zusammen mit bestätigenden Belegen, die Stichwörter, Konfidenzniveau und Nähe umfassen. Verwenden Sie Typen vertraulicher Informationen, um bestimmte Datentypen in Ihrer Organisation zu identifizieren. Verwenden Sie die vorgefertigten Typen vertraulicher Informationen, um standardisierte Datentypen zu finden, z. B. Reisepassnummern. Erstellen Sie einen benutzerdefinierten Informationstyp, um Informationen zu identifizieren, die für Ihre Umgebung einzigartig sind, wie z. B. Teilenummern. | [Anpassen eines benutzerdefinierten vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md)| |
|[Trainierbare Klassifizierer (Vorschau)](classifier-learn-about.md)| Klassifiziert Daten für Sie mit einer der integrierten Klassifizierungen oder trainiert eine Klassifizierung anhand Ihrer Inhalte. | [Erste Schritte mit trainierbaren Klassifizierern (Vorschau)](classifier-get-started-with.md)| |
|[Datenklassifizierung](data-classification-overview.md) | Identifiziert Elemente mit einer Vertraulichkeitsbezeichnung, einer Aufbewahrungsbezeichnung oder die in Ihrer Organisation als vertraulicher Informationstyp klassifiziert wurden sowie die daran durch Ihre Benutzer vorgenommenen Aktionen.  | [Erste Schritte mit dem Inhalts-Explorer](data-classification-content-explorer.md)<br /><br /> [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>Schützen Sie Ihre Daten

Verwenden Sie die folgenden Funktionen, um flexible Schutzmaßnahmen wie Verschlüsselung, Zugriffsbeschränkungen und visuelle Markierungen anzuwenden:


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="Schützen Sie Ihre Daten":::

|**Funktionalität**|**Welche Probleme werden gelöst?**|**Erste Schritte**|**Lizenzierung**|
|--|--|--|--|
|[Vertraulichkeitsbezeichnungen](sensitivity-labels.md)| Eine einzige Lösung über Apps, Dienste und Geräte hinweg, um Ihre Daten zu kennzeichnen und zu schützen, während sie innerhalb und außerhalb Ihres Unternehmens unterwegs sind. <br /><br />Beispielszenario: [Anwenden und Anzeigen von Vertraulichkeitsbezeichnungen in Power BI und Schutz der Daten beim Export](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Erste Schritte mit Vertraulichkeitsbezeichnungen](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Entdeckt, bezeichnet und schützt vertrauliche Informationen, die sich in Datenspeichern in der Cloud befinden | [Entdecken, Klassifizieren, Bezeichnen und Schützen regulierter und vertraulicher Daten, die in der Cloud gespeichert sind](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Azure Information Protection-Scanner für einheitliche Bezeichnungen](/azure/information-protection/deploy-aip-scanner)| Erkennt, kennzeichnet und schützt vertrauliche Informationen, die sich in lokalen Datenspeichern befinden. | [Konfigurieren und Installieren des Azure Information Protection-Scanners für einheitliche Bezeichnungen](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Aktivitätenexplorer]()||||


## <a name="transition-from-aip-to-mip"></a>Übergang von AIP zu MIP
Die klassische Administratorerfahrung und der Client in Azure Information Protection werden Anfang nächsten Jahres veraltet sein. Es wird empfohlen, auf Microsoft Information Protection zu wechseln. Dies bedeutet, dass Sie alle Ihre vorhandenen Bezeichnungen und Richtlinien migrieren müssen. 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="Übergang von AIP zu MIP":::

## <a name="additional-capabilities"></a>Zusätzliche Funktionalitäten
Microsoft 365 enthält diese Funktionalitäten, um beim Schützen der Daten zu helfen:

|**Funktionalität**|**Welche Probleme werden gelöst?**|**Erste Schritte**|
|--|--|--|
| Office 365-Nachrichtenverschlüsselung (Office 365 Message Encryption, OME) | Verschlüsselt E-Mail-Nachrichten und angefügte Dokumente, die an einen beliebigen Benutzer auf einem beliebigen Gerät gesendet werden, sodass nur autorisierte Empfänger die gesendeten Informationen lesen können. <br /><br /> Beispielszenario: Widerrufen von E-Mails, die von der erweiterten Nachrichtenverschlüsselung verschlüsselt wurden | Einrichten neuer Nachrichtenverschlüsselungsfunktionen |
| Verschlüsselung mit Doppelschlüssel | Unter allen Umständen können nur Sie geschützte Inhalte jemals entschlüsseln, und für gesetzliche Anforderungen müssen die Verschlüsselungsschlüssel innerhalb einer geographischen Region aufbewahrt werden. | Bereitstellen der Verschlüsselung mit Doppelschlüssel |  
| Dienstverschlüsselung mit Kundenschlüssel | Schützt vor der Anzeige von Daten durch nicht autorisierte Systeme oder das Personal und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren | Einrichten des Kundenschlüssels für Office 365 |
| SharePoint-Information Rights Management (IRM) | Schützt SharePoint-Listen und -Bibliotheken so, dass wenn ein Benutzer ein Dokument auscheckt, die heruntergeladene Datei geschützt ist, und nur autorisierten Personen die Datei entsprechend den von Ihnen festgelegten Richtlinien anzeigen und verwenden können. | Einrichten von Information Rights Management (IRM) im SharePoint Admin Center |
| Rights Management-Connector | Nur Schutz für vorhandene lokale Bereitstellungen, die Exchange- oder SharePoint-Server und Dateiklassifizierungsinfrastruktur (File Classification Infrastructure, FCI) verwenden | Schritte zum Bereitstellen des RMS-Connectors |



## <a name="prevent-data-loss"></a>Verhindern von Datenverlust

Verwenden Sie die folgenden Funktionen, um die versehentliche Freigabe vertraulicher Informationen zu verhindern:

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="Verhindern von Datenverlust":::

|**Schritt**|**Beschreibung**|**Weitere Informationen**|
|--|--|--|
|[Entwerfen von DLP-Richtlinien](data-loss-prevention-policies.md)| Planen für den Modus zur Identifikation von Informationen (Typ vertraulicher Informationen, Bezeichnung, andere) <br /><br /> Planen, wohin die Richtlinien abzielen werden (Dienste, Client, Drittanbieter-Apps) <br /><br /> Planen von Richtlinientipps, andere||
||||




|**Funktionalität**|**Welche Probleme werden gelöst?**|**Erste Schritte**|
|--|--|--|
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

