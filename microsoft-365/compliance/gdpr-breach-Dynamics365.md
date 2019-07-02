---
title: Dynamics 365 und Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO
description: Wie Dynamics 365 Sie vor Verletzungen des Schutzes personenbezogener Daten schützt und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Verletzung auftritt.
keywords: Dynamics 365, Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 7fbe7f277825905326a1234249e5bccf7082658d
ms.sourcegitcommit: 6e2a54ec395eaef4c4658ca52322c3d0f184ca02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "34698317"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>Dynamics 365 und Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO

Dynamics 365 nimmt die Verpflichtungen im Rahmen der Datenschutz-Grundverordnung (DSGVO) ernst und ergreift umfangreiche Sicherheitsmaßnahmen zum Schutz vor Datenschutzverletzungen. Microsoft arbeitet kontinuierlich an der Bereitstellung äußerst sicherer Unternehmensdienste für Dynamics 365-Kunden. Die Informationen in diesem Abschnitt geben einen Überblick darüber, wie Microsoft Dynamics 365 vor Sicherheitsvorfällen/Datenschutzverletzungen schützt, sowie über den Prozess zur Reaktion und Benachrichtigung unserer Kunden.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 – Integrierte Sicherheitsfeatures

Microsoft Dynamics 365 nutzt die Cloud-Service-Infrastruktur und integrierten Sicherheitsfeatures, um Daten mithilfe von Sicherheitsmaßnahmen und -mechanismen zu schützen. Darüber hinaus bietet Dynamics 365 effizienten Datenzugriff und Zusammenarbeit plus Datenintegrität und Datenschutz in den folgenden Bereichen: [Sichere Identität, Datenschutz, rollenbasierte Sicherheit und Bedrohungsmanagement](https://www.microsoft.com/trustcenter/security/dynamics365-security).

## <a name="incident-response-training"></a>Schulung zur Reaktion auf Sicherheitsvorfälle

Jeder Mitarbeiter, der mit Microsoft Dynamics 365 arbeitet, wird zu Sicherheitsvorfällen und möglichen Reaktionen für seine Rolle geschult. Alle Mitarbeiter von Microsoft Dynamics 365 bekommen eine Schulung, wenn sie im Unternehmen anfangen, sowie jährliche Auffrischungsschulungen. Die Schulungen sollen den Mitarbeitern ein grundlegendes Verständnis des Sicherheitsansatzes von Microsoft vermitteln, sodass sich alle Mitarbeiter nach Abschluss der Schulungen mit Folgendem auskennen:

- Der Definition eines Sicherheitsvorfalls
- Der Verantwortung aller Mitarbeiter hinsichtlich der Meldung von Sicherheitsvorfällen
- Wie sie einen potenziellen Sicherheitsvorfall an das Team für die Reaktion auf Sicherheitsvorfälle von Dynamics 365 eskalieren
- Wie das Team für die Reaktion auf Sicherheitsvorfälle von Dynamics 365 auf Sicherheitsvorfälle reagiert
- Spezielle Überlegungen hinsichtlich des Datenschutzes, insbesondere des Schutzes von Kundendaten
- Wo sich weitere Informationen zu Sicherheit und Datenschutz sowie Kontakten für die Eskalation finden lassen

## <a name="how-does-microsoft-dynamics-365-define-security-incidentpotential-breaches"></a>So definiert Microsoft Dynamics 365 Sicherheitsvorfälle/potenzielle Sicherheitsverletzungen

Sicherheitsvorfälle/Datenschutzverletzungen beziehen sich auf Ereignisse wie den unrechtmäßigen Zugriff auf Kundendaten, die in Microsoft-Geräten oder Microsoft-Einrichtungen gespeichert sind, oder den nicht autorisierten Zugriff auf solche Geräte oder Einrichtungen, der zu Verlust, Offenlegung oder Änderung von Kundendaten führen kann. Das Ziel von Microsoft bei der Reaktion auf Sicherheitsvorfälle/Datenschutzverletzungen ist der Schutz der Kundendaten und der Dynamics 365-Dienste. Der Microsoft-Ansatz für die Verwaltung von Sicherheitsvorfällen entspricht der Sonderveröffentlichung [800-61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) des [National Institute of Standards und Technology](https://www.nist.gov/) (NIST).

Microsoft ist nicht verantwortlich für die Überwachung oder Reaktion auf Sicherheitsvorfälle, die auf Seiten des Kunden auftreten. Ein Sicherheitsproblem, das nur den Kunden betrifft, wird nicht als Dynamics 365-Sicherheitsvorfall verarbeitet, sondern muss vom Mandanten des Kunden behandelt werden. Die Reaktion des Kunden auf Sicherheitsvorfälle kann eine Zusammenarbeit mit dem Kundensupport von Microsoft Dynamics 365 umfassen, sofern entsprechende Serviceverträge bestehen.

## <a name="detection-of-potential-breaches"></a>Erkennung potenzieller Sicherheitsverletzungen

Dynamics 365 reagiert auf eine potenzielle Datenschutzverletzung entsprechend dem Prozess für die Reaktion auf Sicherheitsvorfälle, der Teil des Vorfallsmanagementplans von Microsoft Dynamics 365 ist. Die Reaktion auf Sicherheitsvorfälle seitens Dynamics 365 erfolgt in fünf Stufen: Erkennung, Analyse, Diagnose, Stabilisierung und Abschluss. Das Team für die Reaktion auf Sicherheitsvorfälle kann im Verlauf der Untersuchung zwischen den Stufen der Diagnose und der Stabilisierung wechseln. Nachfolgend finden Sie eine Übersicht über die Vorgehensweise bei Sicherheitsvorfällen:

|**Stufe**|**Beschreibung**|
|:-----|:-----|
| ***1 – Erkennung*** | Erste Anzeichen für einen potenziellen Vorfall. |
| ***2 – Analyse*** | Ein abrufbereites Mitglied des Teams für die Reaktion auf Sicherheitsvorfälle analysiert die Auswirkungen und den Schweregrad des Ereignisses. Basierend auf den Nachweisen kann die Analyse zu einer Eskalation an das Sicherheitsteam führen. |
| ***3 – Diagnose*** | Sicherheitsexperten führen eine technische oder forensische Untersuchung durch und identifizieren Strategien für Eindämmung, Minderung und Abhilfe. Wenn das Sicherheitsteam der Meinung ist, dass möglicherweise Kundendaten gegenüber einer unbefugten Personen offengelegt wurden, wird parallel der Prozess zur Benachrichtigung des Kunden über den Sicherheitsvorfall in Gang gesetzt.|
| ***4 – Stabilisierung und Wiederherstellung*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt einen Wiederherstellungsplan, um das Problem zu mindern. Schritte zur Eindämmung der Auswirkungen, wie die Isolierung der betroffenen Systeme, können sofort und parallel zur Diagnose ausgeführt werden. Zudem können längerfristige Maßnahmen zur Risikominderung geplant werden, die umgesetzt werden, sobald die unmittelbare Gefahr gebannt ist. |
| ***5 – Abschluss und nachträgliche Analyse*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse, die den Vorfall detailliert untersucht, mit dem Ziel, die vorhandenen Richtlinien und Prozesse zu überarbeiten, um ein erneutes Auftreten des Ereignisses zu verhindern. |

Das Whitepaper [Dynamics Security Incident Management](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) enthält weitere Informationen dazu, wie Microsoft Sicherheitsvorfälle in Dynamics 365 untersucht, verwaltet und darauf reagiert.

Die Erkennungsprozesse von Microsoft Dynamics 365 sind darauf ausgelegt, Ereignisse zu finden, welche die Vertraulichkeit, Integrität und Verfügbarkeit von Dynamics 365-Diensten gefährden. Verschiedene Ereignisse können eine Untersuchung auslösen:

- Automatisierte Systembenachrichtigungen über interne Überwachungs- und Warnungsframeworks. Diese Warnungen können in Form von signaturbasierten Alarmen eingehen wie Antischadsoftware oder Angriffserkennung bzw. über Algorithmen, die ein Profil der erwarteten Aktivität erstellen und bei Anomalien Warnungen ausgeben sollen.
- Erstanbieterberichte, die Microsoft Dynamics 365-Dienste ausführen, die in der Public Cloud und in der Sovereign Cloud implementiert sind.
- Sicherheitsrisiken werden dem [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) über <secure@microsoft.com> gemeldet. MSRC arbeitet mit Partnern und Sicherheitsforschern auf der ganzen Welt, um Sicherheitsvorfälle zu verhindern und die Sicherheit von Microsoft-Produkten zu erhöhen.
- Kundenberichte, in denen verdächtige Aktivitäten im Zusammenhang mit Microsoft Dynamics 365-Diensten beschrieben werden (im Gegensatz zu Aktivitäten, die im Verantwortungsbereich des Kunden auftreten).
- Aktivitäten der [roten und blauen Sicherheitsteams](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Bei dieser Strategie wird ein hoch qualifiziertes rotes Team aus offensiven Sicherheitsexperten eingesetzt, um potenzielle Schwächen in Microsoft Dynamics 365-Diensten aufzudecken und anzugreifen. Das blaue Sicherheitsteam muss die Aktivitäten des roten Teams erkennen und abwehren. Die Aktionen des roten wie auch des blauen Teams werden dazu verwendet, um zu überprüfen, ob die Sicherheitsmaßnahmen von Microsoft Dynamics 365 Sicherheitsvorfälle effektiv bewältigen. Die Aktivitäten des roten und blauen Sicherheitsteams müssen Verantwortlichkeiten berücksichtigen, um den Schutz von Kundendaten zu gewährleisten.
- Eskalationen durch Mitarbeiter der Microsoft Dynamics 365-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

## <a name="microsoft-dynamics-365-data-breach-response"></a>Microsoft Dynamics 365 – Reaktion auf Datenschutzverletzungen

Microsoft weist der Untersuchung entsprechende Prioritäts- und Schweregrade zu, indem die vorfallsbedingten Auswirkungen auf die Funktionsfähigkeit, die Wiederherstellbarkeit und die Daten ermittelt werden. Priorität und Schweregrad können sich im Laufe der Untersuchung basierend auf neuen Erkenntnissen und Schlussfolgerungen ändern. Sicherheitsrelevante Ereignisse, von denen bevorstehende oder bestätigte Gefahren für Kundendaten ausgehen, erhalten hohe Priorität und werden bis zur Lösung rund um die Uhr bearbeitet. Microsoft Dynamics 365 definiert eine Datenschutzverletzung als eine Verletzung des Schutzes der personenbezogenen Daten eines Endbenutzers von Onlinediensten oder eines Microsoft-Mitarbeiters.

Das Sicherheitsteam arbeitet mit Sicherheitstechnikern und Sicherheitsexperten (Subject Matter Experts, SMEs) von Microsoft Dynamics 365 zusammen, um das Ereignis basierend auf Fakten aus den gewonnenen Erkenntnissen zu klassifizieren. Ein Sicherheitsereignis kann wie folgt klassifiziert werden:

- **Falsch positives Ereignis:** Ein Ereignis, das die Kriterien zur Erkennung von Sicherheitsvorfällen erfüllt, sich aber als Teil der gängigen Geschäftsprozesse herausstellt und möglicherweise herausgefiltert werden muss. Das Serviceteam ermittelt die Ursache falsch positiver Ereignisse und behandelt sie auf systematische Weise, wobei es Erkennungsquellen zurate zieht und bei Bedarf<span id="_Toc350859432" class="anchor"></span> überarbeitet.
- **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf Kundendaten oder Supportdaten, die auf Geräten oder in Einrichtungen von Microsoft gespeichert sind, bzw. ein nicht autorisierter Zugriff auf diese Geräte oder Einrichtungen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat.
- **Meldepflichtiger Sicherheitsvorfall (Customer-Reportable Security Incident, CRSI):** Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Einrichtungen von Microsoft bzw. eine unrechtmäßige oder nicht autorisierte Verwendung dieser Systeme, Geräte oder Einrichtungen, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat.
- **Datenschutzvorfall:** Ein Untertyp von Sicherheitsvorfällen im Zusammenhang mit personenbezogenen Daten. Die Verfahren gleichen denen bei Sicherheitsvorfällen.

Damit ein CRSI deklariert werden kann, muss Microsoft feststellen, dass ein nicht autorisierter Zugriff auf Kundendaten (sehr wahrscheinlich) stattgefunden hat und/oder dass eine gesetzliche oder vertragliche Verpflichtung zur Benachrichtigung besteht. Es ist wünschenswert, aber nicht zwingend erforderlich, dass die spezifische Auswirkung auf den Kunden, der Ressourcenzugriff und die Reparaturschritte bekannt sind. Ein Vorfall wird im Allgemeinen nach Abschluss der Diagnosestufe eines Sicherheitsvorfalls als CRSI deklariert. Allerdings kann dies auch zu jedem beliebigen anderen Zeitpunkt stattfinden, an dem alle relevanten Informationen verfügbar sind. Der Manager für Sicherheitsvorfälle muss zweifelsfrei nachweisen, dass ein meldepflichtiges Ereignis eingetreten ist, um den Prozess der Benachrichtigung des Kunden zu starten.

Während der gesamten Untersuchung arbeitet das Sicherheitsteam eng mit weltweit tätigen Rechtsberatern zusammen, um sicherzustellen, dass die Forensik unter Einhaltung der gesetzlichen Verpflichtungen und Zusagen gegenüber dem Kunden ausgeführt wird. Es gibt zudem erhebliche Beschränkungen für das Anzeigen und Verarbeiten von System- und Kundendaten in verschiedenen Betriebsumgebungen. Sensible oder vertrauliche Daten sowie Kundendaten werden ohne explizite schriftliche Genehmigung des Managers von Sicherheitsvorfällen, der im entsprechenden Vorfallsticket angegeben ist, nicht aus der Produktionsumgebung heraus übertragen.

Microsoft überprüft, ob das Risiko für Kunden und Unternehmen erfolgreich gebannt wurde und ob Abhilfemaßnahmen implementiert wurden. Bei Bedarf werden Notfallverfahren zum Beheben unmittelbarer Sicherheitsrisiken im Zusammenhang mit dem Ereignis ausgeführt.

Microsoft führt zudem eine interne nachträgliche Analyse für Datenschutzverstöße durch. Als Teil dieser Analyse wird die Angemessenheit der Reaktions- und der Betriebsprozesse ausgewertet und alle Verbesserungen, die an den internen Sicherheitsrichtlinien oder zugehörigen Prozessen von Microsoft vorgenommen werden sollten, werden ermittelt und implementiert. Interne nachträgliche Analysen für Datenschutzverstöße sind streng vertrauliche Datensätze, die Kunden nicht zur Verfügung gestellt werden. Sie können aber zusammengefasst und in andere Ereignisbenachrichtigungen für Kunden eingeschlossen werden. Diese Berichte werden externen Auditoren zur Überprüfung als Teil des routinemäßigen Überwachungszyklus von Dynamics 365 bereitgestellt.

## <a name="customer-notification"></a>Kundenbenachrichtigung

Microsoft Dynamics 365 benachrichtigt Kunden und Aufsichtsbehörden vorgabengerecht über Datenschutzverletzungen. Microsoft baut auf eine starke interne Trennung des Betriebs der verschiedenen Dynamics 365-Dienste. Datenflussprotokolle sind ebenfalls robust. Ein Vorteil dieses Designs ist, dass die meisten Vorfälle bestimmten Kunden zugeordnet werden können. Das Ziel ist, den betroffenen Kunden präzise, umsetzbare und zeitgerechte Informationen bereitzustellen, wenn der Schutz ihrer Daten verletzt wurde.

Sobald ein CRSI deklariert wurde, wird der Benachrichtigungsprozess so rasch wie möglich gestartet, wobei auch die Sicherheitsrisiken eines zu schnellen Handelns berücksichtigt werden. Im Allgemeinen wird die Benachrichtigung bereits entworfen, während der Vorfall untersucht wird. Ab dem Zeitpunkt, an dem wir eine Datenschutzverletzung deklarieren, werden unsere Kunden umgehend informiert, *mit Ausnahme* der folgenden Situationen:

- Microsoft ist der Meinung, dass eine Benachrichtigung das Risiko für andere Kunden erhöht. Beispielsweise wenn durch die Benachrichtigung der Übeltäter gewarnt und der Schaden daraufhin nicht mehr behoben werden kann.
- Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung und dem leitenden Vorfall-Manager von Microsoft überprüft werden.

Microsoft Dynamics 365 stellt Kunden detaillierte Informationen bereit, sodass sie interne Untersuchungen ausführen können ihre Verpflichtungen gegenüber Endbenutzern erfüllen können, ohne den Benachrichtigungsprozess übermäßig zu verzögern.

Die Benachrichtigung zu einer Verletzung des Schutzes personenbezogener Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird an die in Office Security Center hinterlegte Liste der Kundenkontakte/Administratoren übermittelt (nur betroffene Mandanten), die vom Kunden-/Mandantenadministrator konfiguriert werden kann. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt werden kann, muss der Kunde dafür sorgen, dass die administrativen Kontaktinformationen in dem jeweiligen Abonnement und Onlinedienst-Portal korrekt sind.

Das Microsoft Dynamics 365-Team kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Account Manager (AM) oder Technical Account Manager (TAM) des Kunden zu benachrichtigen. Diese Personen stehen häufig in enger Beziehung zum Kunden und können eine schnellere Problembehebung realisieren.<span id="_Appendix_A" class="anchor"></span>

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)