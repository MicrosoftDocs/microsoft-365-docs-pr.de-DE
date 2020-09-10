---
title: Benachrichtigung des Datenauftragsverarbeiterdiensts für Windows Enterprise gemäß DSGVO
description: Wie der Datenauftragsverarbeiterdienst für Windows Enterprise Schutz vor Datenschutzverletzungen für persönliche Daten bietet und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Datenschutzverletzung auftritt.
keywords: Datenauftragsverarbeiterdienst für Windows Enterprise, Microsoft 365, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: fcf3aff200d65c71538975533cb110c89f3bb92d
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417949"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Benachrichtigung des Datenauftragsverarbeiterdiensts für Windows Enterprise über eine Datenschutzverletzung gemäß DSGVO

>[!NOTE]
>Dieser Artikel richtet sich an Teilnehmer am Vorschauprogramm „Datenauftragsverarbeiterdienst für Windows Enterprise“ und setzt die Zustimmung zu bestimmten Nutzungsbedingungen voraus. Wenn Sie mehr über das Programm erfahren und den Nutzungsbedingungen zustimmen möchten, wechseln Sie zu [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Der Microsoft-Datenauftragsverarbeiterdienst für Windows Enterprise nimmt seine Verpflichtungen gemäß der Datenschutz-Grundverordnung (DSGVO) ernst. Der Microsoft-Datenauftragsverarbeiterdienst für Windows Enterprise ergreift umfangreiche Sicherheitsmaßnahmen zum Schutz vor Datenschutzverletzungen. Diese umfassen dedizierte Threat Management-Teams, die in der Lage sind, böswillige Zugriffe proaktiv vorherzusehen, zu verhindern und abzuschwächen.Interne Sicherheitsmaßnahmen, z. B. Portüberwachung, Prüfung des Perimeters auf Sicherheitslücken und Erkennung von Eindringversuchen, erkennen und verhindern böswilligen Zugriff als auch automatisierte Sicherheitsprozesse, umfassende Informationen zu Sicherheits- und Datenschutzrichtlinien sowie Sicherheits- und Datenschutzschulungen für alle Mitarbeiter. 

Sicherheit ist in den Microsoft-Datenauftragsverarbeiterdienst für Windows Enterprise von Grund auf integriert, beginnend mit dem [Security Development Lifecycle](https://www.microsoft.com/sdl/), einem obligatorischen Entwicklungsprozess, der Methoden für entwurfsgemäßen und standardmäßigen Datenschutz umfasst. Das Leitprinzip der Sicherheitsstrategie von Microsoft besteht darin, vom „Vorhandensein einer Datenschutzverletzung auszugehen“, und stellt somit eine Erweiterung der Strategie für tiefgreifende, vorbeugende Sicherheit dar. Indem die Sicherheitsfunktionen des Datenauftragsverarbeiterdiensts für Windows Enterprise ständig getestet werden, kann Microsoft neuen Bedrohungen immer einen Schritt voraus bleiben. Weitere Informationen zur Sicherheit des Datenauftragsverarbeiterdiensts für Windows Enterprise finden Sie in [diesen Ressourcen](https://www.microsoft.com/TrustCenter/Security/windows10-security). Der Datenauftragsverarbeiterdienst für Windows Enterprise reagiert auf eine potenzielle Datenschutzverletzung gemäß dem Prozess für die Reaktion auf Sicherheitsvorfälle. Die Reaktion des Datenauftragsverarbeiterdiensts für Windows Enterprise auf einen Sicherheitsvorfall ist in Form eines fünfstufigen Prozesses implementiert: Erkennen, Bewerten, Diagnostizieren, Stabilisieren und Schließen. Im Verlauf der Untersuchung kann das Reaktionsteam für Sicherheitsvorfälle zwischen den Stufen der Diagnose und Stabilisierung wechseln. Eine Übersicht des Prozesses für die Reaktion auf Sicherheitsvorfälle finden Sie im Folgenden: 

|**Stage**|**Beschreibung**|
| ------- | ------------- |
| ***1 – Erkennung*** | Erste Anzeichen für einen potenziellen Vorfall. |
| ***2 – Analyse*** | Ein abrufbereites Mitglied des Teams für die Reaktion auf Sicherheitsvorfälle analysiert die Auswirkungen und den Schweregrad des Ereignisses. Basierend auf den Nachweisen kann die Analyse zur einer Eskalation an das Sicherheitsteam führen. |
| ***3 – Diagnose*** | Sicherheitsexperten führen eine technische oder forensische Untersuchung durch und identifizieren Strategien für Eindämmung, Minderung und Abhilfe. Wenn das Sicherheitsteam der Meinung ist, dass möglicherweise Kundendaten gegenüber einer unbefugten Personen offengelegt wurden, wird parallel der Prozess zur Benachrichtigung des Kunden über den Sicherheitsvorfall in Gang gesetzt. |
| ***4 – Stabilisierung und Wiederherstellung*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt einen Wiederherstellungsplan, um das Problem zu mindern. Schritte zur Eindämmung der Auswirkungen, wie die Isolierung der betroffenen Systeme, können sofort und parallel zur Diagnose ausgeführt werden. Zudem können längerfristige Maßnahmen zur Risikominderung geplant werden, die umgesetzt werden, sobald die unmittelbare Gefahr gebannt ist. |
| ***5 – Abschluss und nachträgliche Analyse*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse mit den Details des Vorfalls, anhand dessen Richtlinien, Verfahren und Prozesse geprüft werden sollen, um ein erneutes Auftreten des Ereignisses zu verhindern. |

Die Erkennungsprozesse, die der Datenauftragsverarbeiterdienst von Microsoft für Windows Enterprise verwendet, sind darauf ausgelegt, Ereignisse zu erkennen, die die Vertraulichkeit, Integrität und Verfügbarkeit des Datenauftragsverarbeiterdiensts für Windows Enterprise gefährden. Verschiedene Ereignisse können eine Untersuchung auslösen: 

 - Automatisierte Systemwarnungen durch interne Überwachungs- und Warnungsframeworks. Diese Warnungen können in Form von signaturbasierten Alarmen eingehen wie Antischadsoftware oder Angriffserkennung bzw. über Algorithmen, die ein Profil der erwarteten Aktivität erstellen und bei Anomalien Warnungen ausgeben sollen.
 - Erstanbieterberichte von Microsoft-Diensten, die unter Microsoft Azure und Azure Government ausgeführt werden.
 - Sicherheitslücken werden dem [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) über [secure@microsoft.com] (mailto:secure@microsoft.com) gemeldet. MSRC arbeitet mit Partnern und Sicherheitsforschern auf der ganzen Welt, um Sicherheitsvorfälle zu verhindern und die Sicherheit von Microsoft-Produkten zu erhöhen.
 - Kundenberichte über das Kundenportal oder das Management Portal von Microsoft Azure und Azure Government, die der Azure-Infrastruktur zugeordnete verdächtige Aktivitäten beschreiben (im Gegensatz zu Aktivitäten, die in den Verantwortungsbereich des Kunden fallen).
 - Aktivitäten der [roten und blauen Sicherheitsteams](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Bei dieser Strategie wird ein hoch qualifiziertes rotes Team aus offensiven Sicherheitsexperten von Microsoft eingesetzt, um potenzielle Schwächen in Azure aufzudecken und anzugreifen. Das blaue Sicherheitsteam muss die Aktivitäten des roten Teams erkennen und abwehren. Die Aktionen des roten wie auch des blauen Teams werden dazu verwendet, um zu überprüfen, ob die Sicherheitsmaßnahmen von Azure Sicherheitsvorfälle effektiv bewältigen. Die Aktivitäten des roten und blauen Sicherheitsteams müssen Regeln des Engagements einhalten, um den Schutz von Kundendaten zu gewährleisten.
 - Eskalationen durch Mitarbeiter der Azure-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Reaktion des Datenauftragsverarbeiterdiensts für Windows Enterprise auf eine Datenschutzverletzung 

 Microsoft weist der Untersuchung geeignete Prioritäts- und Schweregrade zu, indem die funktionellen Auswirkungen, die Wiederherstellbarkeit und die Beeinträchtigung von Daten durch den Vorfall bestimmt werden. Sowohl Prioritäten als auch Schweregrade können sich im Verlauf der Untersuchung aufgrund neuer Erkenntnisse und Schlussfolgerungen ändern. Sicherheitsereignisse, die ein unmittelbares oder bestätigtes Risiko für Kundendaten darstellen, werden als Ereignisse mit hohem Schweregrad behandelt, den deren Behebung rund um die Uhr gearbeitet wird. Der Datenauftragsverarbeiterdienst von Microsoft für Windows Enterprise kategorisiert die Auswirkungen des Vorfalls auf die Informationen in die folgenden Kategorien von Datenschutzverletzungen: 

| **Kategorie**             | **Definition**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Keine***               | Es wurden keine Daten entfernt, geändert, gelöscht oder anderweitig kompromittiert. |
| ***Datenschutzverletzung***     | Es wurde auf vertrauliche personenbezogene Daten von Steuerzahlern, Mitarbeitern, Begünstigten etc. zugegriffen oder diese wurden entfernt. |
| ***Verletzung des Schutzes unternehmenseigener Daten*** | Es wurde auf nicht klassifizierte, unternehmenseigene Daten, z. B. geschützte kritische Infrastrukturdaten (Protected Critical Infrastructure Information, PCII), zugegriffen oder diese wurden entfernt. |
| ***Integritätsverlust***     | Vertrauliche oder unternehmenseigene Daten wurden geändert oder gelöscht. |

Das Sicherheitsreaktionsteam arbeitet mit Sicherheitstechnikern und Sicherheitsexperten (Subject Matter Experts, SMEs) des Datenauftragsverarbeiterdiensts von Microsoft für Windows Enterprise zusammen, um das Ereignis basierend auf Fakten aus den gewonnenen Erkenntnissen zu klassifizieren. Ein Sicherheitsereignis kann wie folgt klassifiziert werden: 

 - **Falsch positives Ergebnis:** Ein Ereignis, das die Erkennungskriterien erfüllt, aber als Bestandteil einer normalen Geschäftspraxis gilt und möglicherweise gefiltert werden muss. Das Serviceteam ermittelt die Ursache für falsch positive Ergebnisse und behebt sie systematisch, indem Erkennungsquellen genutzt und bei Bedarf optimiert werden. 
 - **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf Kundendaten oder Supportdaten, die auf Geräten oder in Einrichtungen von Microsoft gespeichert sind, bzw. ein nicht autorisierter Zugriff auf diese Geräte oder Einrichtungen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat. 
 - **Meldepflichtiger Sicherheitsvorfall (Customer-Reportable Security Incident, CRSI)**: Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Anlagen von Microsoft bzw. deren Verwendung, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat. 
 - **Datenschutzverletzung:** Ein Untertyp von Sicherheitsvorfällen im Zusammenhang mit personenbezogenen Daten. Die Verfahren gleichen denen bei Sicherheitsvorfällen. 

 Damit ein CRSI erklärt werden kann, muss Microsoft bestimmen, dass ein nicht autorisierter Zugriff auf Kundendaten erfolgt ist oder sehr wahrscheinlich erfolgt ist und/oder dass eine rechtliche oder vertragliche Meldepflicht besteht. Es ist wünschenswert, aber nicht erforderlich, dass bestimmte Kundenauswirkungen, Ressourcenzugriff und Schritte zur Behebung bekannt sind. Ein Vorfall wird im Allgemeinen nach Abschluss der Diagnosestufe eines Sicherheitsvorfalls zu einem CRSI erklärt. Die Erklärung kann aber zu einem beliebigen Zeitpunkt erfolgen, sofern alle relevanten Informationen zur Verfügung stehen. Der Manager des Sicherheitsvorfalls muss zweifelsfrei nachweisen, dass ein meldepflichtiges Ereignis aufgetreten ist, um mit der Ausführung des Prozesses zur Benachrichtigung des Kunden über den Sicherheitsvorfall zu beginnen. 

Während der Untersuchung arbeitet das Sicherheitsteam eng mit globalen Rechtsberatern zusammen, um sicherzustellen, dass die Forensik entsprechend den gesetzlichen Verpflichtungen und Pflichten gegenüber dem Kunden ausgeführt wird. Es gibt zudem erhebliche Beschränkungen für das Anzeigen und Behandeln von System- und Kundendaten in verschiedenen Betriebsumgebungen. Sensible oder vertrauliche Daten sowie Kundendaten werden ohne explizite schriftliche Genehmigung des Vorfall-Managers, die im entsprechenden Vorfallsticket aufgezeichnet wird, nicht aus der Produktionsumgebung heraus übertragen. 

Microsoft überprüft, ob das Risiko für Kunden und Unternehmen erfolgreich gebannt wurde und ob Abhilfemaßnahmen implementiert wurden. Bei Bedarf werden Notfallverfahren zum Beheben unmittelbarer Sicherheitsrisiken im Zusammenhang mit dem Ereignis ausgeführt. 

Microsoft führt zudem eine interne nachträgliche Analyse für Datenschutzverstöße durch. Als Teil dieser Analyse wird die Angemessenheit der Reaktions- und Betriebsprozesse ausgewertet und alle Verbesserungen, die an den Reaktions- und Betriebsprozessen für Sicherheitsvorfälle oder an zugehörigen Prozessen von Microsoft vorgenommen werden sollten, werden ermittelt und implementiert. Interne nachträgliche Analysen für Datenschutzverstöße sind streng vertrauliche Datensätze, die Kunden nicht zur Verfügung gestellt werden. Sie können aber zusammengefasst und in andere Ereignisbenachrichtigungen für Kunden eingeschlossen werden. Diese Berichte werden externen Auditoren zur Überprüfung als Teil des routinemäßigen Überwachungszyklus des Datenauftragsverarbeiterdiensts für Windows Enterprise bereitgestellt. 

## <a name="customer-notice"></a>Kundenbenachrichtigung

Der Microsoft-Datenauftragsverarbeiterdienst für Windows Enterprise benachrichtigt Kunden und Aufsichtsbehörden vorgabegerecht über Datenschutzverstöße. Microsoft baut auf eine hochgradige interne Trennung beim Betrieb des Datenauftragsverarbeiterdiensts für Windows Enterprise. Datenflussprotokolle sind ebenfalls robust. Ein Vorteil dieses Designs ist, dass die meisten Vorfälle bestimmten Kunden zugeordnet werden können. Das Ziel ist, den betroffenen Kunden präzise, umsetzbare und zeitgerechte Informationen bereitzustellen, wenn der Schutz ihrer Daten verletzt wurde. 

Der Benachrichtigungsprozess nach einem deklarierten CRSI wird so rasch wie möglich in Gang gesetzt, wobei auch die Sicherheitsrisiken eines schnellen Handelns berücksichtigt werden. Im Allgemeinen erfolgt der Prozess des Benachrichtigungsentwurfs, während der Vorfall untersucht wird. Ab dem Zeitpunkt, an dem wir eine Datenschutzverletzung deklarieren, vergehen nicht mehr als 72 Stunden, bis wir unsere Kunden informieren, mit Ausnahme der folgenden Situationen: 

 - Microsoft ist der Meinung, dass eine Benachrichtigung das Risiko für andere Kunden erhöht. Beispielsweise wenn durch die Benachrichtigung der Übeltäter gewarnt und der Schaden daraufhin nicht mehr behoben werden kann. 
 - Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung Corporate External and Legal Affairs (CELA) und dem leitenden Vorfall-Manager von Microsoft überprüft werden. 

 Der Microsoft-Datenauftragsverarbeiterdienst für Windows Enterprise bietet Kunden ausführliche Informationen, sodass sie interne Untersuchungen ausführen können und die Erfüllung von Verpflichtungen gegenüber Endbenutzern erleichtert wird, ohne den Benachrichtigungsprozess übermäßig zu verzögern. 

Die Benachrichtigung zu einer Verletzung des Schutzes personenbezogener Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird der Liste der Sicherheitskontakte bereitgestellt, die im Azure Security Center hinterlegt ist und die mithilfe der [Implementierungsrichtlinien](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details) konfiguriert werden kann. Wenn keine Kontaktinformationen im Azure Security Center bereitgestellt werden, erfolgt die Benachrichtigung an einen oder mehrere Administratoren in einem Azure-Abonnement. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt werden kann, muss der Kunde dafür sorgen, dass die administrativen Kontaktinformationen in dem jeweiligen Abonnement und Onlinedienst-Portal korrekt sind.

Das Team des Datenauftragsverarbeiterdiensts für Windows Enterprise kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Account Manager (AM) oder Technical Account Manager (TAM) des Kunden zu benachrichtigen. Diese Personen stehen häufig in enger Beziehung zum Kunden und können eine schnellere Problembehebung realisieren. 

Weitere Informationen darüber, wie Microsoft eine Verletzung des Schutzes personenbezogener Daten erkennt und darauf reagiert, finden Sie im Service Trust Portal unter [Benachrichtigung bei Datenschutzverletzungen im Rahmen der DSGVO](https://servicetrust.microsoft.com/ViewPage/GDPRBreach).
