---
title: 'Verantwortlichkeiten von Kunden und Cloud-Partnern im Rahmen der Sicherung der Geschäftskontinuität '
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie mehr darüber, was Microsoft bei Auftreten eines Dienstvorfalls unternimmt, um Ihre Pläne zur Sicherung der Geschäftskontinuität besser gestalten zu können.
ms.openlocfilehash: 9bbf73c736a4391a51edd451db7d23869aa36603
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122345"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>Verantwortlichkeiten von Kunden und Cloud-Partnern im Rahmen der Steuerung der Geschäftskontinuität 

Das Bereitstellen von Microsoft 365 Cloud-Diensten für Ihre Benutzer begründet eine Partnerschaft zwischen Ihrer Organisation und Microsoft. Microsoft stellt die Dienste zur Verfügung und Sie sind für die Anbindung an die Client-Endpunkte, die Verwaltung der Identitäten und Zugriffsberechtigungen sowie die Weise, wie diese Dienste genutzt werden, verantwortlich. Außerdem bestehen gemeinsame Verantwortlichkeiten, wie die Identitätsverwaltung und die Verzeichnisinfrastruktur. In diesem Artikel werden einige der wichtigsten Punkte präsentiert, auf die Sie achten müssen, damit die betriebliche Kontinuität Ihres Unternehmens im Falle eines Dienstvorfalls gewährleistet ist. Außerdem unterstützt dieser Artikel Sie dabei, Ihre Erwartungen dahingehend zu definieren, was Microsoft bei Auftreten eines Dienstvorfalls unternimmt.

## <a name="transparency-during-service-incidents"></a>Transparenz während Dienstvorfällen

Als vertrauenswürdiger Partner baut Microsoft hoch belastbare Cloud-Dienste auf und befolgt strukturierte Verfahren zur Behebung von Dienstvorfällen, wenn diese eintreten. Microsoft ist sich dessen bewusst, dass bei Auftreten eines Dienstvorfalls **zeitnahe**, **zielgerichtete** und**umfassend verfügbare** Benachrichtigungen für die Kunden entscheidend sind.

## <a name="timely"></a>Zeitnah
Microsoft benachrichtigt Microsoft 365-Administratoren mittels einer Aktualisierung des mandantenspezifischen Service Health Dashboard (SHD) zum Dienststatus im Microsoft 365-Verwaltungsportal (Admin-Center). Updates zu Dienstvorfällen werden in der Regel im Stundenrhythmus bereitgestellt. Sollte ein andere Rhythmus erforderlich sein, informieren wir Sie über die Änderung anhand von geposteten SHD-Mitteilungen.

## <a name="targeted"></a>Zielgerichtet
Wenn unsere Überwachungssysteme ein Problem erkennen, können wir in den meisten Fällen den betroffenen Kundenstamm identifizieren, egal ob es sich dabei um einen Einzelkunden, eine Region oder einen noch größeren Kundenstamm handelt, und die notwendigen Benachrichtigungen an die betreffenden Kunden weiterleiten. Auf diese Weise erhalten Sie die für Ihr Unternehmen erforderlichen Informationen und werden nicht durch Signaltöne für Benachrichtigungen, die Sie nicht betreffen, abgelenkt. Wenn z. B. eine bestimmte Mailbox-Datenbank betroffen ist, können wir genau feststellen, welche Kunden über Benutzer auf der betroffenen Infrastruktur verfügen und die Reichweite unserer Benachrichtigungen an diese anpassen. Wenn der Umfang der Auswirkungen des Vorfalls nicht eindeutig ist, erweitern wir die Reichweite unserer Benachrichtigungen auf die umfangreichste Gruppe von Kunden, die potenziell betroffen sind.

## <a name="highly-avaliable"></a>Umfassend verfügbar
Microsoft unterhält mehrere Kanäle für Statusmitteilungen zu Diensten, die Kunden nutzen können.

- Sollten das Admin-Center oder das Service Health Dashboard im Rahmen des Verwaltungsportals nicht verfügbar sein, können Sie den Status eines Dienstes über unsere [Sicherungswebsite](https://status.office365.com/) überwachen.
- Wir unterhalten einen Twitter-Account [@MSFT365Status](https://twitter.com/msft365status?lang=en), auf dem wir auf Benachrichtigungen zu Vorfällen antworten und Updates zu Vorfällen, die das SHD beeinträchtigen, posten.
- Die Admin-App für Microsoft 365 Mandantenadministratoren bietet Ihnen die Möglichkeit, auch unterwegs eine Verbindung mit dem Microsoft 365 Dienststatus Ihrer Organisation herzustellen. Mandantenadministratoren haben die Möglichkeit, Integritätsinformationen zu Diensten und Updates zum Wartungsstatus von ihren mobilen Geräten abzufragen. Weitere Informationen finden Sie unter „Häufig gestellte Fragen zur Admin-App“[Admin-App FAQ](https://docs.microsoft.com/de-DE/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide).
- Die [Microsoft 365 Service Communications API](https://docs.microsoft.com/de-DE/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) ermöglicht Ihnen den Zugriff auf Benachrichtigungen zu Microsoft-Diensten, sodass Sie Ihre Umgebung einfacher überwachen können. Sie können eine Verbindung mit der API herstellen, Echtzeit-Dienststatusdaten empfangen und die Informationen auf einem internen Dashboard veröffentlichen, um die Benutzer in Ihrem Unternehmen über Vorfälle zu informieren. Die interne Weiterleitung von Informationen kann die Zahl der Anfragen an Ihr Helpdesk bei einem Ausfalls verringern.
- Bei Vorfällen von größerem Ausmaß veröffentlicht Microsoft Post Incident Reviews (PIR) an das SHD im Rahmen des Verwaltungsportals. PIR enthalten wesentliche Informationen zu Vorfällen, die Ihnen dabei helfen, die Art des Ausfalls zu verstehen. In der Regel umfassen diese die folgenden Abschnitte:
    - Auswirkungen auf Benutzer
    - Umfang der Auswirkungen
    - Datum und Uhrzeit der Eintritts und des Endes eines Vorfalls
    - Eigentliche Ursache
    - Durchgeführte Aktionen
    - Nächste Schritte
- Zusätzliche Benachrichtigungen stehen in der Microsoft 365 Mitteilungszentrale zur Verfügung, z. B. Hinweise auf bevorstehende Änderungen, neue Features oder geplante Wartungsarbeiten.
- Weitere Informationen zu den verschiedenen Kommunikationskanälen und zur Überwachung des Dienststatus finden Sie im [Leitfaden zu Dienststatus und Verfügbarkeit (Health and Continuity Guide)](https://docs.microsoft.com/de-DE/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).
 
Das Bereitstellen von Microsoft 365 Online-Diensten begründet eine Partnerschaft zwischen Ihrer Organisation und Microsoft. Im folgenden Diagramm wird die Verteilung der Verantwortlichkeiten auf Microsoft ebenso wie auf die Kunden während eines Dienstvorfalls und während des normalen Betriebs zusammengefasst.

![Verteilung der Verantwortlichkeiten der Kunden und von Microsoft](media\ebcm\responsibilities.png)

## <a name="your-environment---service-continuity"></a>Ihre Umgebung – Dienstverfügbarkeit
Achten Sie bei der Planung Ihrer Geschäftskontinuität auf Ereignisse, die sich auf Ihr Unternehmen und dessen gesamte Kommunikationsfähigkeit auswirken können. Auf hoher Ebene gibt es drei Faktoren, die sich auf Ihr Unternehmen auswirken können.

### <a name="people"></a>Personen
Ziehen Sie Ereignisse, die Auswirkungen auf Ihre Belegschaft haben können, wie eine Naturkatastrophe oder eine Pandemie, in Betracht. Dies wird häufig übersehen, da es unwahrscheinlich ist, dass ein solches Ereignis sich umfassend auf Ihre Belegschaft auswirkt, sofern diese räumlich betrachtet stark verstreut ist. Doch was passiert, wenn ein hoher Prozentsatz Ihrer Belegschaft offline wäre? Könnten Sie Ihre betriebliche Tätigkeit fortsetzen? Wie können Sie die Folgen eines solchen Szenarios abmildern?

### <a name="location"></a>Ort
Viele Unternehmen fordern von Ihren Mitarbeitern deren Anwesenheit an bestimmten physischen Orten oder Netzwerkstandorten, um sich mit Systemen des Unternehmens und Cloud-Diensten zu verbinden.  
Microsoft veröffentlicht [Grundsätze zur Netzwerkkonnektivität](https://docs.microsoft.com/de-DE/office365/enterprise/office-365-network-connectivity-principles), die Unternehmen anhand von bewährten Methoden beim Einrichten der Netzwerkkonnektivität für Cloud-Ressourcen anleiten. Optimierungsbeispiele umfassen die Implementierung von gesplitteten Tunnel-VPN, um Verbindungen direkt vom Netzwerk eines Benutzers statt über einen VPN-Tunnel zu ermöglichen.  Obwohl diese Grundsätze zur Konnektivität für das Aufrechterhalten von Verbindungen mit geringer Latenz wichtig sind, erfordert die Sicherstellung der Dienstverfügbarkeit alternative Methoden der Anbindung von Unternehmensressourcen, die der allgemeinen Zusammenarbeit dienen.

### <a name="systems"></a>Systeme
Zahlreiche Lösungen zur Zusammenarbeit sind systemabhängig, wie z. B.von einem unternehmensweiten Netzwerk (WAN). Wie würde Ihre Organisation reagieren, wenn diese Systeme nicht verfügbar sind?
Diese Grafik bildet Probleme ab, die sich auf mehr als einen Bereich auswirken können. Die zugehörige Tabelle enthält zu berücksichtigende Beispiele

![Mengendiagramm](media\ebcm\venn-diagram.png)

Ihre Pläne zur Unternehmenskontinuität sollten jeden dieser Bereiche berücksichtigen. Zum Beispiel: Wenn Sie fordern, dass sich Benutzer im Unternehmensnetzwerk befinden und es kommt zu einem Schneesturm, wie erhalten diese Benutzer Zugriff auf die wichtigsten Ressourcen? Wenn der Schnee die Anreise in das Büro verhindert und Servicetechniker die Verbindung zum Unternehmensnetzwerk herstellen müssen, gibt es dann eine Richtlinie, die vorschreibt, dass sie die unternehmenseigenen Laptops zu Hause in Ihrem Besitz haben müssen?
