---
title: Office 365 Benachrichtigungen bei Datenschutzverletzungen im Rahmen der DSGVO
description: Wie Microsoft Schutz vor Datenschutzverletzungen für personenbezogene Daten bietet und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Verletzung auftritt.
keywords: Office 365, Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 6b91b489d8d69faffa0852c3e352a6b2e9e9d496
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286365"
---
# <a name="office-365-breach-notification-under-the-gdpr"></a>Office 365 Benachrichtigungen bei Datenschutzverletzungen im Rahmen der DSGVO

Als Datenverarbeiter stellt Office 365 sicher, dass unsere Kunden als Datenverantwortliche die Anforderungen an Benachrichtigungen bei Datenschutzverletzungen im Rahmen der DSGVO einhalten. Zu diesem Zweck sind wir bestrebt, Folgendes zu tun:

-   unseren Kunden eine Möglichkeit zu bieten, einen dedizierten Datenschutzkontakt anzugeben, der im Falle einer Verletzung benachrichtigt wird. Kunden können diesen Kontakt in Azure Active Directory (AAD) angeben.

-   Kunden innerhalb von 72 Stunden über eine Datenschutzverletzung bei personenbezogenen Daten zu benachrichtigen. Die Benachrichtigung erfolgt per E-Mail an den Kontakt, der von dem Kunden angegeben wurde.

-   Die erste Benachrichtigung umfasst mindestens eine Beschreibung der Art der Verletzung, eine  Schätzung der Auswirkungen auf die Benutzer und Schritte zur Minderung der Auswirkungen (falls zutreffend). Wenn unsere Untersuchung zum Zeitpunkt der ersten Benachrichtigung nicht abgeschlossen ist, werden wir in unserer ersten Benachrichtigung nächste Schritte und Zeitrahmen für die nachfolgende Kommunikation aufführen.

Microsoft ist sich bewusst, dass Datenverantwortliche die Verantwortung für die Durchführung von Risikobewertungen tragen und dafür, zu bestimmen, ob eine Verletzung die Benachrichtigung der Datenschutzbehörde des Kunden erfordert. Unsere Benachrichtigung an Kunden enthält die Informationen, die zur Durchführung dieser Bewertung erforderlich sind. Microsoft wird Kunden daher über eine Datenschutzverletzung bei personenbezogenen Daten benachrichtigen, außer in Fällen, in denen personenbezogene Daten als unverständlich gelten (z. B. stark verschlüsselte Daten, bei denen die Integrität des Schlüssels bestätigt wurde).

## <a name="office-365-investments-in-data-security"></a>Office 365 Investitionen in Datensicherheit

Zusätzlich zu unserer Verpflichtung, rechtzeitig über Datenschutzverletzungen zu benachrichtigen, investiert Office 365 in Systeme, Prozesse und Mitarbeiter, um die Wahrscheinlichkeit von Verletzungen bei personenbezogenen Daten zu verringern, und Verletzungen, wenn sie auftreten, schnell zu erkennen und ihre Auswirkungen zu mindern.

Hier finden Sie eine Beschreibung einiger unserer Investitionen in diesem Bereich:

-   **Zugriffskontrollsysteme.** Office 365 befolgt eine Richtlinie des „Zero-standing-Zugriffs“, was bedeutet, dass Techniker nicht auf den Dienst zugreifen können, bis ihnen der Zugriff als Reaktion auf einen bestimmten Vorfall, der eine Ausweitung des Zugriffs erfordert, explizit gewährt wird. Zugriff wird jedes Mal nach dem  Prinzip der geringsten Rechte gewährt: Die Berechtigung für eine bestimmte Anforderung ermöglicht nur einen minimalen Satz von Aktionen, die erforderlich sind, um diese Anforderung zu bedienen. Zu diesem Zweck behält Office 365 eine strikte Trennung zwischen „erweiterten Rollen“ bei, von denen jede Rolle lediglich bestimmte vordefinierte Aktionen ermöglicht. Die Rolle  „Zugang zu Kundendaten“ unterscheidet sich von anderen Rollen, die häufiger zum Verwalten des Dienstes verwendet werden, und wird vor der Genehmigung am stärksten geprüft. Zusammengenommen reduzieren diese Investitionen in die Zugriffskontrolle die Wahrscheinlichkeit, dass ein Techniker missbräuchlich auf Kundendaten in Office 365 zugreift, erheblich.

-   **Sicherheitsüberwachungssysteme und Automatisierung:** Office 365 verfügt über zuverlässige Sicherheitsüberwachungssysteme in Echtzeit. Unter anderem lösen diese Systeme Warnungen aus bei versuchtem unrechtmäßigen Zugriff auf Kundendaten oder bei Versuchen, Daten unrechtmäßig aus unserem Dienst heraus zu übertragen. Im Zusammenhang mit den oben genannten Zugriffskontrollsystemen verwalten unsere Sicherheitsüberwachungssysteme detaillierte Einträge zu Erweiterungsanforderungen und die Aktionen, die aufgrund einer bestimmten Anforderung ausgeführt werden. Zudem unterhält Office 365 automatische Investitionen in die Auflösung, die automatisch handeln, um als Reaktion auf erkannte Gefahren Bedrohungen zu mindern, sowie dedizierte Teams zur Reaktion auf Warnungen, die nicht automatisch aufgelöst werden können. Zur Überprüfung unserer Sicherheitsüberwachungssysteme führt Office 365 regelmäßig Übungen mit roten Teams durch, in denen ein internes Team für Penetrationstests Angreiferverhalten in der Live-Umgebung simuliert. Diese Übungen haben regelmäßige Verbesserungen unserer Fähigkeiten zur Sicherheitsüberwachung und Reaktion zur Folge.

-   **Personal und Prozesse:** Zusätzlich zu der oben beschriebenen Automatisierung verfügt Office 365 über Prozesse und Teams, die für die Weiterbildung des gesamten Unternehmens zum Thema Datenschutz und Vorfallmanagement-Prozesse sowie für die Durchführung dieser Prozesse im Falle einer Datenschutzverletzung zuständig sind. Beispielsweise wird ein detailliertes Standardverfahren (Standard Operating Procedure, SOP) für Datenschutzverletzungen aufrechterhalten und an die Teams innerhalb des Unternehmens weitergegeben. Dieses Standardverfahren beschreibt detailliert die Rollen und Verantwortlichkeiten der einzelnen Teams in Office 365 und der zentralen Teams für die Reaktion auf Sicherheitsvorfälle. Dazu gehören sowohl Aufgaben, die Teams erfüllen müssen, um ihre eigene Sicherheitsposition zu verbessern (Sicherheitsüberprüfungen durchführen, mit zentralen Sicherheitsüberwachungssystemen und anderen Best Practices integrieren), und Aufgaben, die Teams im Falle einer tatsächlichen Datenschutzverletzung erfüllen müssten (schnelle Eskalation zur Reaktion auf Vorfälle, bestimmte Datenquellen verwalten und bereitstellen, die verwendet werden, um den Reaktionsprozess zu beschleunigen). Teams werden außerdem regelmäßig zur Klassifizierung von Daten und zur richtigen Handhabung und Speicherung personenbezogener Daten geschult.

Die wichtigsten Schlussfolgerung ist, dass Office 365 stark in die Verringerung der Wahrscheinlichkeit und Auswirkungen von Datenschutzverletzungen investiert, die unsere Kunden betreffen. Wenn solche Verletzungen bei personenbezogenen Daten auftreten, benachrichtigen wir unsere Kunden unverzüglich darüber, sobald die Verletzung bestätigt wurde.

## <a name="what-to-expect-in-the-event-of-breach"></a>Was Sie im Falle einer Datenschutzverletzung erwarten können

Im Abschnitt oben werden die Investitionen beschrieben, die Office 365 tätigt, um die Wahrscheinlichkeit von Datenschutzverletzungen zu verringern. In dem unwahrscheinlichen Fall, dass eine Verletzung auftritt, sollten Kunden ein vorhersagbares Erlebnis im Hinblick auf die folgenden Punkte erwarten:

-   Konsistenter Lebenszyklus für die Reaktion auf Vorfälle in Office 365. Wie zuvor beschrieben, verwaltet Office 365 detaillierte SOPs für die Reaktion auf Vorfälle, in denen beschrieben wird, wie sich Teams auf Datenschutzverletzungen vorbereiten sollten und wie sie sich verhalten sollten, wenn eine Verletzung auftritt. Dadurch wird sichergestellt, dass unsere Schutzfunktionen und Prozesse über den gesamten Dienst angewendet werden.

-   Einheitliche Kriterien für die Benachrichtigung von Kunden. Unsere Benachrichtigungskriterien konzentrieren sich auf die Vertraulichkeit, Integrität und Verfügbarkeit von Kundendaten. Office 365  benachrichtigt  Kunden direkt, wenn die Vertraulichkeit oder Integrität von Kundendaten beeinträchtigt ist. D. h. wir benachrichtigen Kunden, wenn ohne ordnungsgemäße Autorisierung auf ihre Daten zugegriffen wird oder wenn es zu einer unangemessenen Löschung oder einem Verlust von Daten gekommen ist. Office 365 meldet auch Probleme, die die Verfügbarkeit der Daten beeinträchtigen, obwohl diese Benachrichtigung in der Regel durch das Service Health Dashboard (SHD) erfolgt.

-   Einheitliche Benachrichtigungsinformationen. Wenn Office 365 Kunden über Datenschutzverletzungen benachrichtigt, können Kunden davon ausgehen, dass bestimmte Informationen kommuniziert werden: Wir stellen mindestens die folgenden Informationen bereit:

    -   Dauer der Verletzung und Zeitpunkt, zu dem die Verletzung bekannt wurde

    -   Die ungefähre Anzahl der betroffenen Benutzer

    -   Die Art von Benutzerdaten, die betroffen ist

    -   Aktionen, die vom Datenverantwortlichen oder Datenverarbeiter ausgeführt werden müssen, um die Auswirkungen der Datenschutzverletzung zu mindern

Kunden sollten auch beachten, dass Office 365 als Datenverarbeiter nicht das Risiko einer Datenschutzverletzung bewertet. Wenn eine Datenschutzverletzung erkannt wird, benachrichtigen wir unsere Kunden und stellen ihnen die Informationen bereit, die sie benötigen, um das Risiko für die betroffenen Benutzer genau zu bewerten und zu entscheiden, ob weitere Berichte an Aufsichtsbehörden erforderlich sind. Zu diesem Zweck müssen Datenverantwortliche Folgendes ermitteln:

-   Schweregrad der Verletzung (d. h. Risikobewertung)

-   Ob Endbenutzer benachrichtigt werden müssen

-   Ob Aufsichtsbehörden (Datenschutzbehörden) benachrichtigt werden müssen

-   Bestimmte Schritte, die vom Datenverantwortlichen ergriffen werden, um die Auswirkungen der Verletzung zu mindern

## <a name="contacting-microsoft"></a>Kontaktaufnahme mit Microsoft

In einigen Szenarien wird ein Kunde möglicherweise auf eine Datenschutzverletzung aufmerksam und möchte Microsoft darüber benachrichtigen. Das aktuelle Protokoll sieht vor, dass Kunden den Microsoft-Support, benachrichtigen, welcher dann wiederum Kontakt zu den Entwicklerteams aufnimmt.  In diesem Szenario sind die Microsoft-Entwicklerteams ebenso dafür verantwortlich, Kunden über ihren Support-Kontakt rechtzeitig die benötigten Informationen zu übermitteln.

## <a name="call-to-action-for-customers"></a>Handlungsaufforderung für Kunden

Wie bereits oben erwähnt, benachrichtigt Office 365 Kunden innerhalb von 72 Stunden über eine Datenschutzverletzung. Der Mandantenadministrator des Kunden wird ebenfalls benachrichtigt. Darüber hinaus empfiehlt Office 365, dass Kunden einen Alias als globalen Datenschutzkontakt festlegen; diese Aktion kann im Portal Azure Active Directory (AAD) ausgeführt werden. Im Falle einer Datenschutzverletzung kann neben den Administratoren auch dieser Alias per E-Mail benachrichtigt werden.

Der Datenschutzkontakt des Kunden kann eine Person in dem Unternehmen, eine Verteilerliste (Distribution List, DL) oder eine Person außerhalb des Unternehmens sein. Office 365 fordert lediglich, dass Kunden eine E-Mail-Adresse für diesen Kontakt angeben; Kunden können diese im AAD-Portal im Feld „Globaler Datenschutzkontakt“ eingeben. Beachten Sie, dass dieses Feld mit dem vorhandenen Feld „Technischer Kontakt“ in AAD zusammenhängt, sich jedoch davon unterscheidet. Wenn Kunden eine Verteilerliste für diesen Kontakt angeben, sollten sie sicherstellen, dass die Verteilerliste für den Empfang von Nachrichten von externen Absendern konfiguriert ist.

Office 365 bittet Kunden also, folgende Handlungen auszuführen, um von den Vorteilen unserer Prozesse zur Benachrichtigung bei Datenschutzverletzungen zu profitieren:

-   Entscheiden Sie sich für einen Kontakt, der E-Mail-Benachrichtigungen über Datenschutzverletzungen empfängt. Dieser Kontakt sollte die Anforderungen an Datenverantwortliche gemäß der DSGVO kennen und bereit für die Kontaktaufnahme mit dem Datenschutzbeauftragten des Unternehmens und womöglich auch der Datenschutzbehörde nach Erhalt der Benachrichtigung sein. Mandantenadministratoren werden ebenfalls  Benachrichtigungen über Datenschutzverletzungen erhalten und sollten die Anforderungen an Datenverantwortliche gemäß der DSGVO kennen.

-   Geben Sie die E-Mail-Adresse des Datenschutzkontakts in das AAD-Portal ein. Wenn kein globaler Datenschutzkontakt angegeben wurde, benachrichtigt Microsoft lediglich den Mandantenadministrator.
- <!-- note that there is missing text clipped from the original Word doc -->
