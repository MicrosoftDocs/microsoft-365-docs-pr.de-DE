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
ms.openlocfilehash: 9fc4c99254f4f27b476930a555b237be093bff24
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950724"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

Wenn Sicherheitswarnungen ausgelöst werden, liegt es an Ihrem Sicherheits Betriebsteam, diese Warnungen zu untersuchen und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Die Priorisierung und Untersuchung von Warnungen kann sehr zeitaufwändig sein, insbesondere dann, wenn ständig neue Benachrichtigungen während einer laufenden Untersuchung eingehen. Sicherheitsteams können sich angesichts des enormen Volumens der Bedrohungen, die sie überwachen müssen, überfordert fühlen. Automatische Ermittlungs-und Antwortfunktionen (auch als *selbst Heilungs* Funktionen bezeichnet) in Microsoft Threat Protection können hilfreich sein. 

Sehen Sie sich das folgende Video an, um zu erfahren, wie automatisierte Selbstheilungsfunktionen funktionieren:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Die automatische Untersuchung und Antwort ähnelt einem virtuellen Analysten in Ihrem Security Operations Center.

## <a name="your-virtual-analyst"></a>Ihr virtueller Analyst

Stellen Sie sich vor, Sie haben in Ihrem Sicherheitsteam auf Ebene 1/Ebene 2 einen virtuellen Analysten. Der virtuelle Analyst imitiert die idealen Schritte, die das Sicherheitsteam zur Untersuchung und Behebung von Bedrohungen ausführen würde. Der virtuelle Assistent kann rund um die Uhr mit unbegrenzter Kapazität arbeiten und eine hohe Anzahl von Untersuchungen und Bedrohungen bearbeiten. Ein solcher virtueller Assistent kann die Reaktionszeit erheblich reduzieren, sodass Ihr Sicherheitsteam andere wichtige strategische Projekte übernehmen kann. Wenn dieses Szenario wie Science Fiction klingt, ist es nicht! Ein solcher virtueller Analyst ist Teil Ihrer Microsoft Threat Protection-Suite, und sein Name ist die *Automatische Untersuchung und Antwort*.

Durch die automatische Untersuchung und Antwort kann Ihr Sicherheits Betriebsteam die Kapazität Ihres Unternehmens zur Bewältigung von Sicherheitswarnungen und Vorfällen drastisch erhöhen. Mit automatisierter Untersuchung und Antwort können Sie die Kosten für den Umgang mit Ermittlungs-und Korrekturmaßnahmen senken und ihre Bedrohungsschutz-Suite optimal nutzen. die automatische Untersuchung und Antwort hilft Ihrem Security Operations-Team mit:

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
> Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen! Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response Features in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Während eine Untersuchung läuft, werden alle anderen zugehörigen Warnungen zur Untersuchung hinzugefügt, bis diese abgeschlossen ist. Wenn eine beschuldigte Entität an anderer Stelle angezeigt wird, wird auch diese Entität in die automatische Untersuchung aufgenommen, und es wird ein allgemeines Sicherheitsplaybook ausgeführt. 

> [!NOTE]
> Nicht jede Warnung löst eine automatisierte Untersuchung aus, und nicht jede Untersuchung führt zu automatisierten Korrekturaktionen. Dies hängt davon ab, wie die automatische Untersuchung und Antwort für Ihre Organisation konfiguriert ist. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Anforderungen für die automatische Untersuchung und Reaktion in Microsoft Threat Protection

|Anforderung |Details |
|--|--|
|Abonnementanforderungen |Eine der folgenden Varianten: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 a5 <br/>-Microsoft 365 E5-Sicherheit<br/>-Microsoft 365 a5-Sicherheit<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Weitere Informationen finden Sie unter [Microsoft Threat Protection License Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netzwerkanforderungen |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) muss aktiviert sein<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) muss konfiguriert sein<br/>- [MCAS muss in Azure ATP sein](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows-Computeranforderungen |-Windows 10, Version 1709 oder höher (siehe [Windows 10 – Versionsinformationen](https://docs.microsoft.com/windows/release-information/)) mit den folgenden konfigurierten Threat Protection-Diensten:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender-Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Schutz für e-Mail-Inhalte und Office-Dateien |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) konfiguriert |
|Berechtigungen |– Zum Konfigurieren der automatischen Untersuchung und Antwort muss die Rolle globaler Administrator oder Sicherheitsadministrator entweder in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) oder im Microsoft 365 Admin Center () zugewiesen sein [https://admin.microsoft.com](https://admin.microsoft.com) .<br/><br/>-Für die Verwendung von automatisierten Ermittlungs-und Antwortfunktionen siehe [erforderliche Berechtigungen für Aktionen des Aufgaben Centers](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Nächste Schritte

- [Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion](mtp-autoir-actions.md)
- [Erfahren Sie mehr über das Info-Center](mtp-action-center.md)
