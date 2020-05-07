---
title: Benchmarks des Center for Internet Security (CIS)
description: Das Center for Internet Security (CIS) hat eine Reihe von Benchmarks für Microsoft-Produkte und -Dienste veröffentlicht.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 8e147e26072609a43d962b1d9fc7e71925510da4
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064694"
---
# <a name="center-for-internet-security-cis-benchmarks"></a>Benchmarks des Center for Internet Security (CIS)

## <a name="about-cis-benchmarks"></a>Informationen zu CIS-Benchmarks

Das [Center for Internet Security](https://www.cisecurity.org/) ist eine gemeinnützige Organisation, die es sich zum Ziel gesetzt hat, „Bewährte Lösungsmethoden zum Schutz vor Cyberbedrohungen zu identifizieren, zu entwickeln, zu bewerten, zu fördern und zu unterstützen“. Die Organisation macht sich dabei das Know-how zum Thema Internetsicherheit und das Wissen von IT-Experten aus Regierung, Unternehmen und Akademien auf der ganzen Welt zu Nutze. Zur Entwicklung von Standards und bewährten Methoden, einschließlich CIS-Benchmarks, Steuerungen und gehärteten Images, wird ein konsensbasiertes Entscheidungsmodell befolgt.  
  
[CIS-Benchmarks](https://www.cisecurity.org/cis-benchmarks/) sind Basispläne für Konfiguration und bewährte Methoden zur sicheren Konfiguration eines Systems. Jede Empfehlung verweist auf eine oder mehrere [CIS-Steuerungen](https://www.cisecurity.org/controls/), die entwickelt wurden, um Organisationen bei der Verbesserung ihrer Verteidigung gegen Cyberangriffe zu unterstützen. Die CIS-Steuerungen entsprechen zahlreichen etablierten Normen und aufsichtsrechtlichen Rahmenbedingungen, einschließlich des NIST Cybersecurity Framework (CSF) und des NIST-SP 800-53, der ISO 27000-Reihe von Standards, PCI DSS, HIPAA und weiteren.  
  
Jeder Benchmark unterliegt zwei Phasen der konsensbasierten Überprüfung. Die erste Phase erfolgt während der anfänglichen Entwicklung, wenn sich Experten treffen, um Arbeitsentwürfe zu besprechen, zu erstellen und zu testen, bis sie eine Einigung über den Benchmark erzielen. In der zweiten Phase, nach der Veröffentlichung des Benchmarks, überprüft das Team das Feedback der Internetcommunity im Hinblick auf die Einbindung in den Benchmark.  
  
CIS-Benchmarks bieten zwei Ebenen von Sicherheitseinstellungen:

- **Ebene 1** empfiehlt grundlegende Sicherheitsanforderungen, die in jedem System konfiguriert werden können und zu geringen oder gar keinen Dienstunterbrechungen oder eingeschränkter Funktionalität führen sollten.
- **Ebene 2** empfiehlt Sicherheitseinstellungen für Umgebungen, die mehr Sicherheit erfordern, was zu einer verringerten Funktionalität führen kann.

[Gehärtete CIS-Images](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/) sind sicher konfigurierte Images von virtuellen Maschinen basierend auf CIS-Benchmarks, die auf einem CIS-Benchmarkprofil der Ebene 1 oder Ebene 2 gehärtet wurden. Das „Härten“ ist ein Prozess, der Schutz vor unbefugtem Zugriff, Denial-of-Service-Angriffen und anderen Cyberbedrohungen bietet, indem potenzielle Schwachstellen eingeschränkt werden, die für Cyberattacken anfällig sind.

## <a name="microsoft-and-the-cis-benchmarks"></a>Microsoft und die CIS-Benchmarks

Das Center for Internet Security (CIS) veröffentlicht Benchmarks für Microsoft-Produkte und -Dienste, einschließlich der Foundation-Benchmarks für Microsoft Azure und Microsoft 365, des Benchmarks für Windows 10 und des Benchmarks für Windows Server 2016.  
  
CIS-Benchmarks werden international als Sicherheitsstandards für den Schutz von IT-Systemen und Daten vor Cyberangriffen anerkannt. Sie werden von Tausenden von Unternehmen verwendet und bieten verbindliche Anweisungen für die Einrichtung einer sicheren Basislinienkonfiguration. System- und Anwendungsadministratoren, Sicherheitsexperten und andere Personen, die Lösungen mithilfe von Microsoft-Produkten und -Diensten entwickeln, können diese bewährten Methoden verwenden, um die Sicherheit ihrer Anwendungen zu bewerten und zu verbessern.  
  
Wie alle CIS-Benchmarks wurden auch die Microsoft-Benchmarks anhand eines konsensbasierten Überprüfungsprozesses basierend auf den Beiträgen von Sachverständigen mit unterschiedlichen Hintergründen im Hinblick auf Softwareentwicklung, Überwachung und Compliance, Sicherheitsforschung, Arbeitsabläufe, Behörden und Rechtsvorschriften entwickelt. Bei diesen CIS-Bemühungen war Microsoft ein unentbehrlicher Partner. Office 365 wurde beispielsweise anhand der aufgeführten Dienste getestet, und die daraus resultierenden Benchmarks für Microsoft 365 decken ein breites Spektrum von Empfehlungen zum Einrichten geeigneter Sicherheitsrichtlinien ab, die sich auf Konten und Authentifizierung, Datenverwaltung, Anwendungsberechtigungen, Speicher und andere Bereiche von Sicherheitsrichtlinien beziehen.  
  
Zusätzlich zu den Benchmarks für Microsoft-Produkte und -Dienste hat CIS auch [gehärtete CIS-Images für die Verwendung auf virtuellen Azure-Computern veröffentlicht](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/), die so konfiguriert wurden, dass sie den CIS-Benchmarks entsprechen. Dazu gehört das gehärtete CSI-Image für Microsoft Windows Server 2016, das für die Ausführung auf Azure zertifiziert wurde. CIS gibt an, dass „alle abgesicherten CIS-Abbildungen, die im [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps?search=center%20for%20internet%20security) verfügbar sind, für die Ausführung unter Azure zertifiziert wurden. Diese wurden vorab auf deren Einsatzbereitschaft und Kompatibilität mit der öffentlichen Azure-Cloud, der Microsoft-Cloudplattform, die von den Dienstanbietern über das Netzwerk des Cloudbetriebssystems gehostet wird, und den von Kunden verwalteten Windows Server Hyper-V-Bereitstellungen der lokalen privaten Cloud getestet.“

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft-Clouddienste im Leistungsumfang

- [Azure und Azure Government](https://aka.ms/AzureCompliance)
- [Office und Microsoft 365](https://aka.ms/o365-compliance-framework)
- SQL Server
- Windows 10
- Windows Server 2016

## <a name="audits-reports-and-certificates"></a>Prüfungen, Berichte und Zertifikate

Rufen Sie eine [vollständige Liste von CIS-Benchmarks](https://www.cisecurity.org/cis-benchmarks/) für Microsoft-Produkte und -Dienste ab.

- [CIS Azure Foundations Benchmark](https://www.cisecurity.org/benchmark/azure/)
- [CIS Microsoft 365 Foundations Benchmark](https://www.cisecurity.org/benchmark/microsoft_office/)
- [Windows 10 Benchmark](https://www.cisecurity.org/benchmark/microsoft_windows_desktop/)
- [Windows Server 2016 Benchmark](https://www.cisecurity.org/benchmark/microsoft_windows_server/)

## <a name="how-to-implement"></a>Implementierung

- [CIS-Benchmark für Azure](https://azure.microsoft.com/mediahandler/files/resourcefiles/cis-microsoft-azure-foundations-security-benchmark/CIS_Microsoft_Azure_Foundations_Benchmark_v1.0.0.pdf): Hier erhalten Sie verbindliche Anweisungen für die Einrichtung einer sicheren Basislinienkonfiguration für Azure.  
- [Inhaltsübersicht für die Sicherheit von Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap): Minimieren Sie das Risiko einer Datenschutzverletzung oder eines kompromittierten Kontos, indem Sie diese Roadmap befolgen.
- [Windows-Sicherheitsbasispläne](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines): Befolgen Sie diese Richtlinien, um Sicherheitsbasislinien in Ihrer Organisation effektiv zu nutzen.
- [CIS Controls Cloud Companion Guide](https://www.cisecurity.org/white-papers/cis-controls-cloud-companion-guide/): Hier finden Sie Anweisungen zum Anwenden bewährter Sicherheitsmethoden in CIS-Steuerungen, Version 7, auf Cloudanwendungen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wird durch eine Einhaltung der CIS-Benchmarkeinstellungen die Sicherheit meiner Anwendungen gewährleistet?**

CIS-Benchmarks legen das grundlegende Maß an Sicherheit für alle Personen fest, die Microsoft-Produkte und -Dienste einführen. Diese Benchmarks sollten jedoch nicht als umfassende Liste aller möglichen Sicherheitskonfigurationen und -architekturen, sondern eher als Ausgangspunkt betrachtet werden. Jede Organisation muss weiterhin ihre spezifische Situation, Arbeitslast und Complianceanforderungen auswerten und ihre Umgebung entsprechend anpassen.

**Wie oft werden CIS-Benchmarks aktualisiert?**

Die Veröffentlichung überprüfter CSI-Benchmarks ändert sich in Abhängigkeit von der Community von IT-Experten, die den Benchmark entwickelt haben, und in Abhängigkeit vom Veröffentlichungsplan der Technologie, die der Benchmark unterstützt. CIS veröffentlicht monatliche Berichte, in denen neue Benchmarks und Aktualisierungen an vorhandenen Benchmarks angekündigt werden. Um diese zu erhalten, registrieren Sie sich für die [CIS Workbench](https://workbench.cisecurity.org/) (kostenlos), und aktivieren Sie die entsprechende Option in Ihrem Profil, um den Newsletter zu erhalten.

**Wer hat zur Entwicklung von Microsoft-CIS-Benchmarks beigetragen?**

CIS betont, dass seine „Benchmarks mithilfe der großzügigen Freiwilligenarbeit von Sachverständigen, Technologieanbietern, öffentlichen und privaten Mitgliedern der CIS-Community sowie des CIS-Benchmark-Entwicklungsteams entwickelt werden“. Unter [CIS Microsoft Azure Foundations Benchmark v1.0.0 Now Available](https://www.cisecurity.org/blog/cis-microsoft-azure-foundations-benchmark-v1-0-0-now-available/) finden Sie beispielsweise eine Liste der Personen, die an Azure mitgewirkt haben.

## <a name="resources"></a>Ressourcen

- [Bewährte CIS-Methoden zur sicheren Verwendung von Microsoft 365](https://www.microsoft.com/security/blog/2019/01/10/best-practices-for-securely-using-microsoft-365-the-cis-microsoft-365-foundations-benchmark-now-available/)
- [Sicherheitsrichtlinieneinstellungen in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/security-policy-settings)
- [Sicherheit in Windows 10 Enterprise](https://docs.microsoft.com/windows/security/index)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
