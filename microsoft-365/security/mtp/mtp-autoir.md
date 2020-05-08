---
title: Automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection
description: Erhalten Sie einen Überblick über die Funktionen der automatischen Untersuchung und Reaktion in Microsoft Threat Protection.
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 6ac6d74b027cc533f689c1d67c7fce246c73984f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166161"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Automatische Untersuchung und Antwort (Air)-Funktionen in Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen. Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen. Die Funktionen für die automatische Untersuchung und Reaktion (Air) in Microsoft Threat Protection können Ihnen helfen. Air ähnelt einem virtuellen Analysten in Ihrem Security Operations Center.

## <a name="your-virtual-analyst"></a>Ihr virtueller Analyst

Stellen Sie sich vor, Sie haben in Ihrem Sicherheitsteam auf Ebene 1/Ebene 2 einen virtuellen Analysten. Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde. Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten. Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann. Wenn dieses Szenario wie Science Fiction klingt, ist es nicht! Ein solcher virtueller Analyst ist Teil Ihrer Microsoft Threat Protection-Suite, und er heißt *Automatische Untersuchung und Reaktion* (AIR).

Mit AIR können Ihre Sicherheitsteams die Kapazität Ihrer Organisation im Umgang mit Sicherheitswarnungen und Vorfällen erheblich verbessern. Mit AIR können Sie die Kosten für die Bearbeitung von Untersuchungs- und Wartungsaktionen reduzieren und Ihre Threat Protection-Suite optimal nutzen. AIR unterstützt Ihr Sicherheitsteam bei folgenden Aktivitäten:

1. Ermitteln, ob eine Bedrohung eine Aktion erfordert;
2. Durchführen (oder Empfehlen) aller erforderlichen Wartungsmaßnahmen;
3. Ermitteln, welche weiteren Untersuchungen stattfinden sollten und
4. Wiederholen des Vorgangs für andere Warnungen.

## <a name="the-automated-investigation-process"></a>Der Prozess der automatischen Untersuchung

**Warnung** > **Vorfall** > **automatische Untersuchung** > **Urteil** > **Wartungsaktion**

Bei einer ausgelösten Warnung wird ein Vorfall erstellt, der eine automatisierte Untersuchung starten kann. Diese Untersuchung kann zu einer oder mehreren Wartungsaktionen führen. In Microsoft Threat Protection korreliert jede automatische Untersuchung Signale in Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) und Office 365 Advanced Threat Protection (Office 365 ATP), wie in der folgenden Tabelle zusammengefasst: 

|Entitäten |Dienste für den Bedrohungsschutz  |
|---------|---------|
|Geräte (auch als Endpunkte bezeichnet)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-Mail-Inhalte (Dateien und Nachrichten in Postfächern)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Bei jeder Untersuchung werden Urteile (*böswillige*, *verdächtige*oder *nicht gefundene Bedrohungen*) für jedes untersuchte Beweisstück generiert. Je nach Art der Bedrohung und dem daraus resultierenden Urteil werden Korrekturaktionen automatisch oder nach Genehmigung durch das Sicherheits Betriebsteam Ihrer Organisation durchgeführt. Ausstehende und abgeschlossene Aktionen werden im [Info-Center](mtp-action-center.md) aufgelistet.

> [!TIP]
> Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen! Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Funktionen in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist. Wenn eine beschuldigte Entität an anderer Stelle angezeigt wird, wird auch diese Entität in die automatische Untersuchung aufgenommen, und es wird ein allgemeines Sicherheitsplaybook ausgeführt. 

> [!NOTE]
> Nicht jede Benachrichtigung löst eine automatische Untersuchung aus, und nicht jede Untersuchung führt zu automatischen Wartungsaktionen. Dies hängt davon ab, wie AIR für Ihre Organisation konfiguriert ist. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Anforderungen für AIR in Microsoft Threat Protection

| | |
|--|--|
|Abonnementanforderungen |Eine der folgenden Varianten: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 a5 <br/>-Microsoft 365 E5-Sicherheit<br/>-Microsoft 365 a5-Sicherheit<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Weitere Informationen finden Sie unter [Microsoft Threat Protection License Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netzwerkanforderungen |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) muss aktiviert sein<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) muss konfiguriert sein<br/>- [MCAS muss in Azure ATP sein](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows-Computeranforderungen |-Windows 10, Version 1709 oder höher (siehe [Windows 10 – Versionsinformationen](https://docs.microsoft.com/windows/release-information/)) mit den folgenden konfigurierten Threat Protection-Diensten:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender-Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Schutz für e-Mail-Inhalte und Office-Dateien |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) konfiguriert |
|Berechtigungen |– Zum Konfigurieren von AIR muss Ihnen die Rolle Globaler Administrator oder Sicherheitsadministrator in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) zugewiesen sein.<br/><br/>– Wenn Sie AIR-Funktionen verwenden möchten, lesen Sie die Informationen unter [Erforderliche Berechtigungen für Info-Center-Aufgaben](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Nächste Schritte

- [Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion](mtp-autoir-actions.md)
- [Erfahren Sie mehr über das Info-Center](mtp-action-center.md)
