---
title: Bewerten und testen Sie Microsoft 365 Defender, einen XDR, um Endpunkte, Identitäten, Apps, E-Mails, Anwendungen für die Zusammenarbeit, Daten zu verhindern, zu erkennen, zu untersuchen, zu beantworten.
description: Planen Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung, um eine Sicherheitslösung zum Schutz von Geräten, Identität, Daten und Anwendungen zu testen und zu erleben.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 06/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ade3087543f45439664868fbe02f1746e1f5e762
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458333"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>Auswerten und Testen Microsoft 365 Defender

**Gilt für:**

- Microsoft 365 Defender

Microsoft 365 Defender ist eine erweiterte Erkennungs- und Antwortlösung (Extended Detection and Response, XDR), die automatisch Signal-, Bedrohungs- und Warnungsdaten aus Ihrer Microsoft 365 Umgebung erfasst, korreliert und analysiert, einschließlich Endpunkt, E-Mail, Anwendungen und Identitäten. Sie nutzt umfassende KI und Automatisierung, um Angriffe automatisch zu stoppen und betroffene Objekte in einen sicheren Zustand zu versetzen. Die folgenden Artikel führen Sie durch den Prozess des Einrichtens einer Testumgebung, damit Sie die Features und Funktionen von Microsoft 365 Defender bewerten können. 

Während Sie durch diese Artikel gehen, werden die Schritte veranschaulichen, wie Sie jede Komponente aktivieren, Einstellungen konfigurieren und mit der Überwachung mit einer Pilotgruppe beginnen. Wenn Sie fertig sind, können Sie fertig sein, indem Sie Ihre Evaluierungsumgebung direkt in die Produktion umwandeln. 

Microsoft empfiehlt, die Auswertung in einem vorhandenen Produktionsabonnement von Office 365 zu erstellen. Auf diese Weise erhalten Sie sofort Einblicke in die Praxis und können Einstellungen so optimieren, dass sie auf aktuelle Bedrohungen in Ihrer Umgebung angewendet werden. Nachdem Sie Erfahrung gesammelt haben und mit der Plattform vertraut sind, bewerben Sie einfach jede Komponente nacheinander für die Produktion. 


## <a name="the-anatomy-of-an-attack"></a>Die Anatomie eines Angriffs

Microsoft 365 Defender ist eine cloudbasierte, einheitliche Verteidigungssuite vor und nach der Verletzung des Unternehmens. Sie koordiniert *die Verhinderung,* *Erkennung,* *Untersuchung* und *Reaktion* über Endpunkte, Identitäten, Apps, E-Mails, Anwendungen für die Zusammenarbeit und alle ihre Daten hinweg.

In dieser Abbildung wird ein Angriff ausgeführt. Phishing-E-Mails werden im Posteingang eines Mitarbeiters in Ihrer Organisation eintreffen, der die E-Mail-Anlage unwissentlich öffnet. Dadurch wird Schadsoftware installiert, die zu einer Kette von Ereignissen führt, die mit dem Diebstahl vertraulicher Daten enden könnten. In diesem Fall ist Defender für Office 365 jedoch in Betrieb.

![So stoppt Microsoft 365 Defender eine Reihe von Bedrohungen](../../media/defender/m365-defender-eval-threat-chain.png)

In der Abbildung sehen Sie Folgendes:

- **Exchange Online Protection**, Teil von Microsoft Defender für Office 365, kann die Phishing-E-Mail erkennen und E-Mail-Flussregeln verwenden, um sicher zu stellen, dass sie nie im Posteingang eintrifft.
- **Defender für Office 365** sichere Anlagen testet die Anlage und ermittelt, dass sie schädlich ist, sodass die eingehende E-Mail vom Benutzer nicht bearbeitet werden kann oder Richtlinien verhindern, dass die E-Mails überhaupt eintreffen.
- **Defender für Endpunkt** verwaltet Geräte, die eine Verbindung mit dem Unternehmensnetzwerk herstellen und Geräte- und Netzwerkschwachstellen erkennen, die andernfalls möglicherweise ausgenutzt werden.
- **Defender for Identity** nimmt plötzliche Kontoänderungen wie die Rechteeskalation oder die laterale Bewegung mit hohem Risiko zur Kenntnis. Es meldet auch leicht ausgenutzte Identitätsprobleme wie die uneingeschränkte Kerberos-Delegierung zur Korrektur durch das Sicherheitsteam.
- **Microsoft Cloud App Security** bemerkt anomales Verhalten wie unmögliche Reise, Zugriff auf Anmeldeinformationen und ungewöhnliche Download-, Dateifreigabe- oder E-Mail-Weiterleitungsaktivitäten und meldet diese an das Sicherheitsteam.

### <a name="microsoft-365-defender-components"></a>Microsoft 365 Defender Komponenten

Microsoft 365 Defender besteht aus diesen Sicherheitstechnologien, die zusammen ausgeführt werden. Sie benötigen nicht alle diese Komponenten, um von den Funktionen von XDR und Microsoft 365 Defender zu profitieren. Sie werden auch durch die Verwendung von ein oder zwei Vorteilen und Effizienzsteigerungen profitieren. 

|Komponente  |Beschreibung  |Referenzmaterial  |
|---------|---------|---------|
|Microsoft Defender for Identity     |      Microsoft Defender for Identity verwendet Active Directory-Signale, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insideraktionen gegen Ihre Organisation zu identifizieren, zu erkennen und zu untersuchen.     |     [Was ist Microsoft Defender for Identity?](/defender-for-identity/what-is)   |
|Exchange Online Protection     |      Exchange Online Protection ist der systemeigene cloudbasierte SMTP-Relay- und Filterdienst, der Ihre Organisation vor Spam und Schadsoftware schützt.      |   [Übersicht über Exchange Online Protection (EOP) – Office 365](../office-365-security/overview.md)     |
|Microsoft Defender für Office 365     |     Microsoft Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit.      |    [Microsoft Defender für Office 365 – Office 365](../office-365-security/overview.md)    |
|Microsoft Defender für Endpunkt     |     Microsoft Defender für Endpunkt ist eine einheitliche Plattform für Geräteschutz, Erkennung nach Einer Sicherheitsverletzung, automatisierte Untersuchung und empfohlene Reaktion.      |   [Microsoft Defender für Endpunkt – Windows Sicherheit](../defender-endpoint/microsoft-defender-endpoint.md)    |
|Microsoft Cloud App Security     |      Microsoft Cloud App Security ist eine umfassende SaaS-übergreifende Lösung, die umfassende Sichtbarkeit, starke Datenkontrollen und verbesserten Bedrohungsschutz für Ihre Cloud-Apps bietet.       |    [Was ist Microsoft Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)    |
|Azure AD Identity Protection|Azure AD Identity Protection wertet Risikodaten aus Milliarden von Anmeldeversuchen aus und verwendet diese Daten, um das Risiko jeder Anmeldung in Ihrer Umgebung zu bewerten. Diese Daten werden von Azure AD verwendet, um den Kontozugriff zuzulassen oder zu verhindern, je nachdem, wie Richtlinien für bedingten Zugriff konfiguriert sind. Azure AD Identity Protection wird separat von Microsoft 365 Defender lizenziert. Es ist in Azure Active Directory Premium P2 enthalten.|[Was ist Identitätsschutz?](/azure/active-directory/identity-protection/overview-identity-protection)|
| | | |

## <a name="microsoft-365-defender-architecture"></a>Microsoft 365 Defender Architektur

Das folgende Diagramm veranschaulicht die allgemeine Architektur für wichtige Microsoft 365 Defender Komponenten und Integrationen. *Detaillierte* Architektur für jede Defender-Komponente und Anwendungsszenarien finden Sie in dieser Artikelreihe.

![Microsoft 365 Defender allgemeine Architektur](../../media/defender/m365-defender-eval-architecture.png)

In dieser Abbildung:

- Microsoft 365 Defender kombiniert die Signale aller Defender-Komponenten, um die erweiterte Erkennung und Reaktion (Extended Detection and Response, XDR) domänenübergreifend bereitzustellen. Dazu gehören eine einheitliche Vorfallwarteschlange, automatisierte Reaktion auf das Beenden von Angriffen, Selbstkorrektur (für kompromittierte Geräte, Benutzeridentitäten und Postfächer), bedrohungsübergreifende Suche und Bedrohungsanalyse.
- Microsoft Defender schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Sie teilt Signale, die sich aus diesen Aktivitäten ergeben, mit Microsoft 365 Defender. Exchange Online Protection (EOP) ist integriert, um einen End-to-End-Schutz für eingehende E-Mails und Anlagen bereitzustellen.
- Microsoft Defender for Identity sammelt Signale von Servern, auf denen Active Directory-Verbunddienste (AD FS) und lokale Active Directory Domain Services (AD DS) ausgeführt werden. Sie verwendet diese Signale, um Ihre Hybrididentitätsumgebung zu schützen, einschließlich des Schutzes vor Hackern, die kompromittierte Konten verwenden, um sich seitlich über Arbeitsstationen in der lokalen Umgebung zu bewegen.
- Microsoft Defender für Endpunkt sammelt Signale von Geräten, die von Ihrer Organisation verwendet werden, und schützt sie.
- Microsoft Cloud App Security sammelt Signale aus der Verwendung von Cloud-Apps in Ihrer Organisation und schützt den Datenfluss zwischen Ihrer Umgebung und diesen Apps, einschließlich sanktionierten und nicht genehmigten Cloud-Apps.
- Azure AD Identity Protection wertet Risikodaten aus Milliarden von Anmeldeversuchen aus und verwendet diese Daten, um das Risiko jeder Anmeldung in Ihrer Umgebung zu bewerten. Diese Daten werden von Azure AD verwendet, um den Kontozugriff zuzulassen oder zu verhindern, je nachdem, wie Richtlinien für bedingten Zugriff konfiguriert sind. Azure AD Identity Protection wird separat von Microsoft 365 Defender lizenziert. Es ist in Azure Active Directory Premium P2 enthalten.  

Zusätzliche optionale Architekturkomponenten, die nicht in dieser Abbildung enthalten sind:

- Detaillierte Signaldaten aus allen Microsoft Defender-Komponenten können in Azure Sentinel integriert und mit anderen Protokollierungsquellen kombiniert werden, um vollständige SIEM- und SOAR-Funktionen und -Einblicke zu bieten.

## <a name="the-evaluation-process"></a>Der Evaluierungsprozess

Microsoft empfiehlt, die Komponenten von Microsoft 365 in der folgenden Reihenfolge zu aktivieren:

![Microsoft 365 Defender allgemeinen Bewertungsprozess](../../media/defender/m365-defender-eval-process.png)

In der folgenden Tabelle wird diese Abbildung beschrieben.

|      |Schritt  |Beschreibung  |
|------|---------|---------|
|1     | [Erstellen der Evaluierungsumgebung](eval-create-eval-environment.md)       |Mit diesem Schritt wird sichergestellt, dass Sie über die Testlizenz für Microsoft 365 Defender verfügen.         |
|2     | [Aktivieren von Defender for Identity](eval-defender-identity-overview.md)        | Überprüfen Sie die Architekturanforderungen, aktivieren Sie die Auswertung, und durchlaufen Sie Lernprogramme zum Identifizieren und Beheben verschiedener Angriffstypen.   |
|3     | [Aktivieren von Defender für Office 365](eval-defender-office-365-overview.md)       | Stellen Sie sicher, dass Sie die Architekturanforderungen erfüllen, aktivieren Sie die Auswertung, und erstellen Sie dann die Pilotumgebung. Diese Komponente enthält Exchange Online Protection, sodass Sie *beide* wertet.      |
|4      | [Aktivieren von Defender für Endpunkt ](eval-defender-endpoint-overview.md)       | Stellen Sie sicher, dass Sie die Architekturanforderungen erfüllen, aktivieren Sie die Auswertung, und erstellen Sie dann die Pilotumgebung.         |
|5      | [Aktivieren Microsoft Cloud App Security](eval-defender-mcas-overview.md)        |  Stellen Sie sicher, dass Sie die Architekturanforderungen erfüllen, aktivieren Sie die Auswertung, und erstellen Sie dann die Pilotumgebung.        |
|6      | [Untersuchen und Reagieren auf Bedrohungen](eval-defender-investigate-respond.md)        |   Simulieren Sie einen Angriff und beginnen Sie mit der Verwendung von Vorfallreaktionsfunktionen.      |
|7      | [Bewerben der Testversion zur Produktion](eval-defender-promote-to-production.md)        | Höherstufen sie die Microsoft 365 Komponenten nacheinander in die Produktion.        |
| | | |

Dies ist eine allgemein empfohlene Reihenfolge, die entwickelt wurde, um den Nutzen der Funktionen schnell basierend darauf zu gewinnen, wie viel Aufwand in der Regel erforderlich ist, um die Funktionen bereitzustellen und zu konfigurieren. Beispielsweise kann Defender für Office 365 viel schneller konfiguriert werden, als für die Registrierung von Geräten für Defender für Endpunkt erforderlich ist. Natürlich können Sie die Komponenten priorisieren, um Ihre Geschäftlichen Anforderungen zu erfüllen und diese in einer anderen Reihenfolge zu aktivieren.

## <a name="next-steps"></a>Nächste Schritte

[Erstellen der Microsoft 365 Defender-Evaluierungsumgebung](eval-create-eval-environment.md)
