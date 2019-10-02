---
title: Bereitstellungsstrategien für die Foundation-Infrastruktur von Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie mehr darüber, wie Sie die Phasen der Foundation-Infrastruktur für Microsoft 365 Enterprise bereitstellen können.
ms.openlocfilehash: 0c700c10969142116cc73fc90e8fd283fa6fc6dc
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369436"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a>Bereitstellungsstrategien für die Foundation-Infrastruktur von Microsoft 365 Enterprise

Es gibt viele Möglichkeiten, die Phasen der [Foundation-Infrastruktur](deploy-foundation-infrastructure.md) von Microsoft 365 Enterprise zu nutzen und ihre Funktionen, Software und Dienste für Ihre Benutzer bereitzustellen. Um mit dem Projektmanagement dieses Vorhabens zu beginnen, das je nach Größe Ihres Unternehmens und der vorhandenen Infrastruktur groß und komplex sein kann, sollten Sie die folgenden Bereitstellungsstrategien in Betracht ziehen:

- Serielle Bereitstellung
- Parallele Bereitstellung mit nicht überlappendem Benutzerrollout
- Parallele Bereitstellung mit überlappendem Benutzerrollout
- Vorabinfrastruktur und Rollout der End-to-End-Konfiguration

Nutzen Sie diese Strategien für Ideen, wie Sie das Gesamtprojekt verwalten und die Geschäftsvorteile von Microsoft 365 Enterprise schneller nutzen können.

>[!Note]
>Dieser Artikel enthält Annahmen und Vereinfachungen für eine einheitliche Beschreibung der Bereitstellungsstrategien. Diese Bereitstellungsstrategien sind verallgemeinert und sollen weder einen bestimmten Zeitrahmen implizieren, noch sollen sie für alle Organisationen und Situationen gelten.
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a>Elemente des IT-Projektmanagements für typische Unternehmensorganisationen

Die IT-Infrastruktur umfasst sowohl Back-End-Dienste als auch die Einführung neuer oder verbesserter Funktionen oder installierter Software für Endbenutzer. IT-Abteilungen setzen in der Regel Elemente einer IT-Infrastruktur methodisch ein. Ein Ansatz für die erfolgreiche Bereitstellung eines Elements der IT-Infrastruktur berücksichtigt die folgenden Aspekte:

- Eine Pilotbereitstellung 

  Dazu gehören die anfängliche Infrastrukturkonfiguration und das Rollout für eine Pilotgruppe von Benutzern, das Testen und spätere Änderungen der Infrastrukturkonfiguration.

- Eine Benutzerbereitstellung

  Dazu gehört auch das Rollout für den Rest Ihres Unternehmens basierend auf Regionen, Abteilungen, Gruppen oder anderen Arten der systematischen Verteilung von Konfiguration oder Software.

Die Benutzergruppe im Pilotrollout ist nicht identisch mit derjenigen im Benutzerrollout.

Dieser Artikel verwendet die folgenden Grafikelemente, um diese Definitionen darzustellen: 

![Die Grafik zur Darstellung der Definitionen von Pilot- und Benutzerrollout](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

Die Schattierung für die Benutzerrolloutgrafik zeigt den Prozentanteil in Ihrem Unternehmen von 0 % bis 100 % mit einem strukturierten oder methodischen Ansatz wie Gruppen, Abteilungen oder Regionen.

## <a name="deployment-strategies"></a>Bereitstellungsstrategien

Ziehen Sie die folgenden Bereitstellungsstrategien in Betracht:

- Serielle Bereitstellung
- Parallele Bereitstellung mit nicht überlappendem Benutzerrollout
- Parallele Bereitstellung mit überlappendem Benutzerrollout
- Vorabinfrastruktur und Rollout der End-to-End-Konfiguration

### <a name="serial-deployment"></a>Serielle Bereitstellung

Bei einer seriellen Bereitstellung führen Sie eine Phase vollständig aus, sodass die Phase einen 100%igen Abschluss der Bereitstellung für alle Ihre Benutzer erreicht, bevor Sie zur nächsten Phase übergehen. Im Folgenden finden Sie einige der Gründe, warum Sie diese Art der Bereitstellung wählen sollten:

- Risikominderung
- Ressourceneinschränkungen
- Finanzierungszyklen der IT-Abteilung
- IT-Technologieabhängigkeiten
- Geschäftsänderungsverwaltung und Endbenutzerresistenz

Dieses Gantt-Diagramm zeigt eine vereinfachte serielle Bereitstellung der Phasen 2 bis 6 der Foundation-Infrastruktur für Microsoft 365 Enterprise.

![Die serielle Bereitstellung der Phasen 2 bis 6 der Foundation-Infrastruktur](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
Um die Erläuterung und das Beispiel zu vereinfachen, wird davon ausgegangen, dass jede Phase und jedes Einsatzsegment innerhalb jeder Phase die gleiche Zeit in Anspruch nimmt.

>[!Note]
>Phase 1: Die Vernetzung der Microsoft 365 Enterprise Foundation-Infrastruktur ist eine reine Phase der IT-Abteilung. Benutzer profitieren von den Vorteilen einer optimierten Konnektivität mit den Cloudressourcen von Microsoft, werden aber nicht dazu gezwungen.
>

Hier finden Sie ein Beispiel für eine vereinfachte Pilotbenutzeroberfläche:

- Im Dezember muss ich mein Smartphone für MFA verwenden. (Identität)
- Im März wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)
- Im Juni wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)
- Im September erfolgt die Geräteregistrierung, und es werden App- und Geräterichtlinien angewendet. (Verwaltung mobiler Geräte)
- Im Dezember wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)

Das Ergebnis ist eine Kadenz von 90 Tagen zwischen den aufeinanderfolgenden Pilotrollouts.

Hier finden Sie ein Beispiel für eine vereinfachte Endbenutzeroberfläche:

- Im Januar muss ich mein Smartphone für MFA verwenden. (Identität)
- Im April wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)
- Im Juli wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)
- Im Oktober erfolgt die Geräteregistrierung, und es werden App- und Geräterichtlinien angewendet. (Verwaltung mobiler Geräte)
- Im Januar des Folgejahres wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)

Das Ergebnis ist eine Kadenz von 90 Tagen zwischen den aufeinanderfolgenden Benutzerrollouts.

Der Nachteil dieser Bereitstellungsstrategie besteht darin, dass es lange dauern kann, bis die Microsoft 365 Enterprise Foundation-Infrastruktur vollständig bereitgestellt wurde.

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a>Parallele Bereitstellung mit nicht überlappendem Benutzerrollout (Parallel 1)

Für diese Bereitstellungsstrategie starten Sie das Pilotrollout der nächsten Phase im letzten Teil des Benutzerrollouts der aktuellen Phase. Hier findet die Bereitstellung der Phasen 2 bis 6 statt, wenn das Pilotrollout stattfindet, während das Benutzerrollout der vorherigen Phase abgeschlossen ist.

![Parallele Bereitstellung der Phasen 2 bis 6 mit nicht überlappendem Benutzerrollout](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
Das Endergebnis ist, dass das Benutzerrollout für die aktuelle Phase in Ihrem Unternehmen abgeschlossen ist, bevor die nächste Phase beginnt. Benutzer, die sich nicht in Pilotrollouts befinden, befassen sich nicht gleichzeitig mit den Rollouts mehrerer Phasen, aber Pilotrollouts werden parallel zu Benutzerrollouts durchgeführt.

Hier finden Sie ein Beispiel für eine vereinfachte Pilotbenutzeroberfläche:

- Im Dezember muss ich mein Smartphone für MFA verwenden. (Identität)
- Im Februar wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)
- Im April wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)
- Im Juni erfolgt die Geräteregistrierung, und es werden App- und Geräterichtlinien angewendet. (Verwaltung mobiler Geräte)
- Im August wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)

Das Ergebnis ist eine Kadenz von 60 Tagen zwischen den aufeinanderfolgenden Pilotrollouts.

Hier finden Sie ein Beispiel für eine vereinfachte Endbenutzeroberfläche:

- Im Januar muss ich mein Smartphone für MFA verwenden. (Identität)
- Im März wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)
- Im Mai wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)
- Im Juli erfolgt die Geräteregistrierung, und es werden App- und Geräterichtlinien angewendet. (Verwaltung mobiler Geräte)
- Im September wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)

Das Ergebnis ist eine Kadenz von 60 Tagen zwischen den aufeinanderfolgenden Benutzerrollouts.

Der Vorteil dieser Bereitstellungsstrategie besteht darin, dass die vollständige Bereitstellung der Microsoft 365 Enterprise Foundation-Infrastruktur in kürzerer Zeit erfolgen kann, ohne dass Ihre IT-Abteilung und Benutzer mehrere Rollouts gleichzeitig durchführen müssen.

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a>Parallele Bereitstellung mit überlappendem Benutzerrollout (Parallel 2)

Für diese Bereitstellungsstrategie beginnen Sie:

- Das Pilotrollout der nächsten Phase während des letzten Teils des Benutzerrollouts der aktuellen Phase.
- Benutzerrollout der nächsten Phase während des Benutzerrollouts der aktuellen Phase, sodass sich kein Benutzer mit dem Rollout mehrerer Phasen gleichzeitig befassen muss. Dies setzt voraus, dass das Rollout der einzelnen Phasen der Foundation-Infrastruktur auf die gleiche Weise wie Regionen, Abteilungen oder andere Gruppierungen erfolgt.

Dies ist ein vereinfachter Vergleich zwischen den verschiedenen Bereitstellungsstrategien.

![Parallele Bereitstellung der Phasen 2 bis 6 mit überlappendem Benutzerrollout](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

Für das Endergebnis gilt Folgendes:

- Pilotrollouts gehen ohne Unterbrechung von einer Phase in die nächste über.
- Das Benutzerrollout für eine Phase beginnt vor Abschluss des Benutzerrollouts der vorherigen Phase, aber kein einzelner Benutzer führt mehr als eine Phase gleichzeitig aus.

Hier finden Sie ein Beispiel für eine vereinfachte Pilotbenutzeroberfläche:

- Im Dezember muss ich mein Smartphone für MFA verwenden. (Identität)
- Im Januar wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)
- Im Februar wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)
- Im März erfolgt die Geräteregistrierung, und es werden App- und Geräterichtlinien angewendet. (Verwaltung mobiler Geräte)
- Im April wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)

Das Ergebnis ist eine Kadenz von 30 Tagen zwischen den aufeinanderfolgenden Pilotrollouts.

Hier finden Sie ein Beispiel für eine vereinfachte Endbenutzeroberfläche:

- Im Januar muss ich mein Smartphone für MFA verwenden. (Identität)
- Im Februar wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)
- Im März wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)
- Im April erfolgt die Geräteregistrierung, und es werden App- und Geräterichtlinien angewendet. (Verwaltung mobiler Geräte)
- Im Mai wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)

Das Ergebnis ist eine Kadenz von 30 Tagen zwischen den aufeinanderfolgenden Benutzerrollouts.

Der Vorteil dieser Bereitstellungsstrategie besteht darin, dass die vollständige Bereitstellung der Microsoft 365 Enterprise Foundation-Infrastruktur in noch kürzerer Zeit erfolgen kann, Ihre Benutzer aber trotzdem nicht mehrere Rollouts gleichzeitig durchführen müssen. Allerdings erhalten die Benutzer keine Pause zwischen den aufeinanderfolgenden Phasen.

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a>Vorabinfrastruktur und Rollout der End-to-End-Konfiguration

Für kleinere Unternehmen mit der Möglichkeit, die Phasen 2 bis 6 in einem einzigen Bereitstellungssegment zu komprimieren, sieht die sich ergebende Bereitstellung folgendermaßen aus:
 
![Vorabinfrastruktur und Rollout der End-to-End-Konfiguration](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

Die IT-Abteilung konfiguriert die Infrastruktur für die Phasen 2 bis 6 und stellt sie dann für die Pilotbenutzer bereit, um die End-to-End-Funktionalität zu überprüfen. Beispielsweise erhalten Pilotbenutzer alle diese Funktionen gleichzeitig:

- MFA und andere Identitätsfeatures (Identität)
- Windows 10 Enterprise auf Windows-Geräten (Windows 10 Enterprise)
- Office 365 ProPlus für die Office-Suite (Office 365 ProPlus)
- App und Geräterichtlinien (Verwaltung mobiler Geräte)
- Installation des Azure Information Protection-Clients und Schulung, wie Bezeichnungen auf Dokumente angewendet werden (Information Protection)

Nach Abschluss des Pilotrollouts beginnt das Benutzerrollout, bei dem jeder Benutzer alle Funktionen gleichzeitig erhält.

## <a name="next-step"></a>Nächster Schritt

Starten der Bereitstellung von Microsoft 365 Enterprise mit der [Foundation-Infrastruktur](deploy-foundation-infrastructure.md).
