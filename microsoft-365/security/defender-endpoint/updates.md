---
title: Verwalten des schrittweisen Rollouts für Microsoft Defender-Updates
description: Erfahren Sie mehr über den Prozess und die Steuerelemente für graduelle Aktualisierungen
keywords: update, update process, controls, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 435a77432caa9d7335a22993f85cae69eff6cd38
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52862016"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Verwalten des schrittweisen Rollouts für Microsoft Defender-Updates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)


Es ist wichtig sicherzustellen, dass Clientkomponenten auf dem neuesten Stand sind, um kritische Schutzfunktionen bereitzustellen und Angriffe zu verhindern.

Funktionen werden über mehrere Komponenten bereitgestellt: 

- [Endpunkterkennung & Antwort](overview-endpoint-detection-response.md) 
- [Schutz der nächsten Generation](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) mit über [die Cloud bereitgestellten Schutz](cloud-protection-microsoft-defender-antivirus.md) 
- [Attack Surface Reduction](overview-attack-surface-reduction.md)

Updates werden monatlich mithilfe eines schrittweisen Veröffentlichungsprozesses veröffentlicht. Dieser Prozess hilft, die frühzeitige Fehlererkennung zu ermöglichen, um die Auswirkungen abzufangen, sobald sie auftritt, und sie schnell vor einem größeren Rollout zu beheben. 

> [!NOTE]
> Weitere Informationen zum Steuern täglicher Definitionsupdates finden Sie unter [Planen Microsoft Defender Antivirus Definitionsupdates – Windows Sicherheits-| Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definitionsupdates stellen sicher, dass der Schutz der nächsten Generation vor neuen Bedrohungen schützen kann, auch wenn der über die Cloud bereitgestellte Schutz für den Endpunkt nicht verfügbar ist.

## <a name="microsoft-gradual-rollout-model"></a>Graduelles Rolloutmodell von Microsoft

Es folgt das folgende graduelle Rolloutmodell:

1. Die erste Version wird für Abonnenten des Betakanals veröffentlicht.
2. Nach Überprüfung, Feedback und Korrekturen starten wir den schrittweisen Rollout-Prozess gedrosselt und zeigen zuerst die Abonnenten des Kanals an.
3. Anschließend veröffentlichen wir das Update für die restliche Weltgesamtheit und skalieren die Skalierung von 10 bis 100 %.

Unsere Techniker überwachen die Auswirkungen kontinuierlich und eskalieren alle Probleme, um eine Korrektur nach Bedarf zu erstellen.

## <a name="how-to-customize-your-internal-deployment-process"></a>So passen Sie Ihren internen Bereitstellungsprozess an

Wenn Ihre Computer Defender-Updates von Windows Update erhalten, kann der graduelle Rolloutvorgang dazu führen, dass einige Ihrer Computer Defender-Updates früher als andere erhalten. Im folgenden Abschnitt wird erläutert, wie Sie eine Strategie definieren, die es ermöglicht, dass automatische Updates unterschiedlich zu bestimmten Gruppen von Geräten fließen, indem Sie die Updatekanalkonfiguration nutzen.

> [!NOTE]
> Stellen Sie bei der Planung Ihrer eigenen graduellen Veröffentlichung sicher, dass Sie immer eine Auswahl von Geräten haben, die die Vorschaukanäle und die mehrstufigen Kanäle abonniert haben. Dies bietet Ihrer Organisation und Microsoft die Möglichkeit, Probleme zu verhindern oder zu finden und zu beheben, die für Ihre Umgebung spezifisch sind.

Für Computer, die Updates erhalten, z. B. Windows Server Update Services (WSUS) oder Microsoft Endpoint Configuration Manager (MECM), stehen für alle Windows Updates weitere Optionen zur Verfügung, einschließlich Optionen für Microsoft Defender für Endpunkt.

- Weitere Informationen zur Verwendung einer Lösung wie WSUS, MECM zum Verwalten der Verteilung und Anwendung von Updates finden Sie unter Verwalten Microsoft Defender Antivirus Updates und Anwenden von [Basisplänen – Windows Sicherheits-| Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Aktualisieren von Kanälen für monatliche Updates

Sie können einen Computer einem Updatekanal zuweisen, um den Rhythmus zu definieren, in dem ein Computer monatliche Modul- und Plattformupdates empfängt.

Weitere Informationen zum Konfigurieren von Updates finden Sie unter [Erstellen eines benutzerdefinierten schrittweisen Rolloutprozesses für Microsoft Defender-Updates.](configure-updates.md)

Die folgenden Updatekanäle sind verfügbar:

| Kanalname  | Beschreibung  | Anwendung  |
|-|-|-|
| Betakanal – Vorabversion  | Testen von Updates vor anderen  | Geräte, die auf diesen Kanal festgelegt sind, erhalten als Erste neue monatliche Updates. Wählen Sie "Betakanal" aus, um an der Identifizierung und Meldung von Problemen an Microsoft teilzunehmen. Geräte im Windows-Insider-Programm sind standardmäßig für diesen Kanal abonniert. Nur zur Verwendung in Testumgebungen.  |
| Aktueller Kanal (Vorschau)  | Abrufen aktueller Kanalupdates **früher** während der graduellen Veröffentlichung  | Geräten, die auf diesen Kanal festgelegt sind, werden Updates frühestens während des schrittweisen Releasezyklus angeboten. Wird für Vorproduktions-/Validierungsumgebungen vorgeschlagen.  |
| Aktueller Kanal (mehrstufiger Kanal)  | Aktuelle Kanalupdates später während der graduellen Veröffentlichung abrufen  | Den Geräten werden updates später während des schrittweisen Veröffentlichungszyklus angeboten. Es wird empfohlen, einen kleinen, repräsentativen Teil der Gerätegesamtheit (ca. 10 %) anzuwenden.  |
| Aktueller Kanal (allgemein) | Updates am Ende der graduellen Veröffentlichung abrufen  | Geräte werden Updates erst nach Abschluss des schrittweisen Veröffentlichungszyklus angeboten. Es wird empfohlen, eine breite Gruppe von Geräten in Ihrer Produktionsgesamtheit anzuwenden (ca. 10-100 %).  |
| (Standard)  |   | Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, verbleibt das Gerät im aktuellen Kanal (Standard): Bleiben Sie während des schrittweisen Releasezyklus automatisch auf dem neuesten Stand. Geeignet für die meisten Geräte.  |

### <a name="update-channels-for-daily-definition-updates"></a>Aktualisieren von Kanälen für tägliche Definitionsupdates

Sie können einen Computer einem Updatekanal zuweisen, um die Häufigkeit zu definieren, in der ein Computer tägliche Definitionsupdates empfängt.
  
| Kanalname  | Beschreibung  | Anwendung  |
|-|-|-|
| Aktueller Kanal (mehrstufiger Kanal)  | Aktuelle Kanalupdates später während der graduellen Veröffentlichung abrufen  | Den Geräten werden updates später während des schrittweisen Veröffentlichungszyklus angeboten. Es wird empfohlen, einen kleinen, repräsentativen Teil der Gerätegesamtheit (ca. 10 %) anzuwenden.  |
| Aktueller Kanal (allgemein) | Updates am Ende der graduellen Veröffentlichung abrufen  | Den Geräten werden nach dem graduellen Veröffentlichungszyklus Updates angeboten. Am besten geeignet für Rechenzentrumscomputer, die nur eingeschränkte Updates erhalten. Hinweis: Diese Einstellung gilt für alle Defender-Updates.  |
| (Standard)  |   | Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, verbleibt das Gerät im aktuellen Kanal (Standard): Bleiben Sie während des schrittweisen Releasezyklus automatisch auf dem neuesten Stand. Geeignet für die meisten Geräte  |

> [!NOTE]
> Wenn Sie eine Aktualisierung der neuesten Signatur erzwingen möchten, anstatt die Zeitverzögerung zu nutzen, müssen Sie diese Richtlinie zuerst entfernen.

## <a name="update-guidance"></a>Leitfaden zum Aktualisieren

In den meisten Fällen ist die empfohlene Konfiguration bei verwendung von Windows Update, dass Endpunkte monatliche Defender-Updates empfangen und anwenden können, sobald sie eintreffen. Dies bietet die beste Balance zwischen Schutz und möglichen Auswirkungen im Zusammenhang mit den Änderungen, die sie einführen können.

Für Umgebungen, in denen ein kontrollierterer gradueller Rollout automatischer Defender-Updates erforderlich ist, sollten Sie einen Ansatz mit Bereitstellungsgruppen in Betracht ziehen:

1. Nehmen Sie am Windows Insider-Programm teil, oder weisen Sie dem Betakanal eine Gruppe von Geräten zu.
2. Legen Sie eine Pilotgruppe fest, die sich für den Vorschaukanal (in der Regel Validierungsumgebungen) entscheidet, um neue Updates frühzeitig zu erhalten.
3. Legen Sie eine Gruppe von Computern fest, die später während des graduellen Rollouts vom mehrstufigen Kanal Updates erhalten. In der Regel sind dies ca. 10 % der Grundheit.
4. Legen Sie eine Gruppe von Computern fest, die Updates erhalten, nachdem der graduelle Veröffentlichungszyklus abgeschlossen ist. Dies sind in der Regel wichtige Produktionssysteme.

Für die restlichen Geräte besteht die Standardeinstellung darin, neue Updates zu erhalten, sobald sie während des schrittweisen Rollouts von Microsoft eingehen, und es ist keine weitere Konfiguration erforderlich. 

Einführung dieses Modells:
- Ermöglicht es Ihnen, frühe Versionen zu testen, bevor sie eine Produktionsumgebung erreichen. 
- Stellen Sie sicher, dass die Produktionsumgebung weiterhin regelmäßige Updates erhält, und stellen Sie sicher, dass sie vor kritischen Bedrohungen geschützt ist.

## <a name="management-tools"></a>Verwaltungstools
Um Einen eigenen benutzerdefinierten graduellen Rolloutprozess für monatliche Updates zu erstellen, können Sie die folgenden Tools verwenden:

- Gruppenrichtlinie
- Microsoft Endpoint Manager
- PowerShell

Ausführliche Informationen zur Verwendung dieser Tools finden Sie unter [Erstellen eines benutzerdefinierten schrittweisen Rolloutprozesses für Microsoft Defender-Updates.](configure-updates.md)
