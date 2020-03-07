---
title: Azure and Dynamics 365-Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO
description: Hier erfahren Sie, wie Azure und Dynamics 365 Sie vor Verletzungen des Schutzes personenbezogener Daten schützen und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Verletzung auftritt.
keywords: Azure, Microsoft 365, Dynamics 365, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: f1964d4f4406e7a7070e3cf272a1386f14528517
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558095"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Azure and Dynamics 365-Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO

Microsoft Azure nimmt seine Pflichten im Rahmen der Datenschutz-Grundverordnung (DSGVO) sehr ernst. Microsoft Azure ergreift umfassende Sicherheitsmaßnahmen, um vor Datenschutzverletzungen zu schützen. Diese umfassen sowohl physische und logische Sicherheitskontrollen als auch automatisierte Sicherheitsprozesse, umfassende Richtlinien zur Informationssicherheit und zum Datenschutz sowie Schulungen zur Sicherheit und zum Datenschutz für Mitarbeiter.

Sicherheit ist in Microsoft Azure von Grund auf integriert, beginnend mit dem [Security Development Lifecycle](https://www.microsoft.com/sdl/), einem obligatorischen Entwicklungsprozess, der benutzerdefinierte und standardmäßige Datenschutz-Methodologien umfasst. Das Leitprinzip der Sicherheitsstrategie von Microsoft besteht darin, vom Vorhandensein einer Datenschutzverletzung auszugehen, und stellt somit eine Erweiterung der Strategie für tiefgreifende, vorbeugende Sicherheit dar. Indem die Sicherheitsfunktionen von Azure ständig getestet werden, kann Microsoft neuen Bedrohungen immer einen Schritt voraus bleiben. Weitere Informationen zur Sicherheit bei Azure finden Sie in diesen [Ressourcen](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft verfügt über einen globalen, rund um die Uhr aktiven Service für die Reaktion auf Vorfälle, der daran arbeitet, die Auswirkungen von Angriffen gegen Microsoft Azure zu mindern. Microsoft nutzt in seinen Rechenzentren strenge Abläufe und Prozesse zur Verhinderung von nicht autorisiertem Zugriff, darunter 24-Stunden-Videoüberwachung, geschultes Sicherheitspersonal, Smartcards und biometrische Kontrollen. Dies wird durch mehrere Sicherheits- und Compliance-Audits bestätigt (z. B. [ISO/IEC 27018](offering-iso-27018.md)).

## <a name="detection-of-potential-breaches"></a>Erkennung potenzieller Sicherheitsverletzungen

Aufgrund der Beschaffenheit des modernen Cloud Computings beziehen sich nicht alle Datenschutzverletzungen, die in einer Cloudumgebung des Kunden auftreten, auf Dienste von Microsoft Azure. Microsoft verwendet ein Modell der gemeinsamen Verantwortung für Azure-Dienste, in dem Verantwortlichkeiten für Sicherheit und operative Abläufe definiert sind. Gemeinsame Verantwortung ist besonders dann wichtig, wenn es um die Sicherheit von Clouddiensten geht, da sowohl der Anbieter des Clouddiensts als auch die Kunden jeweils für Teile der Cloudsicherheit zuständig sind.

Microsoft ist nicht verantwortlich für die Überwachung oder Reaktion auf Sicherheitsvorfälle, die auf Seiten des Kunden auftreten. Ein Sicherheitsproblem, das nur den Kunden betrifft, wird nicht als Azure-Sicherheitsvorfall verarbeitet, sondern muss vom Mandanten des Kunden behandelt werden. Die Reaktion des Kunden auf Sicherheitsvorfälle kann eine Zusammenarbeit mit dem [Kundensupport](https://azure.microsoft.com/support/options/) von Microsoft Azure umfassen, sofern entsprechende Serviceverträge bestehen. Microsoft Azure bietet auch verschiedene Dienste an (z. B. [Azure Security Center](https://azure.microsoft.com/services/security-center/)), die Kunden zur Entwicklung und Verwaltung einer Reaktion auf Sicherheitsvorfälle verwenden können.

Azure reagiert auf eine potenzielle Datenschutzverletzung entsprechend dem Prozess für die Reaktion auf Sicherheitsvorfälle, der Teil des Vorfallmanagementplans von Microsoft Azure ist. Die Reaktion auf Sicherheitsvorfälle seitens Azure erfolgt in fünf Stufen: Erkennung, Analyse, Diagnose, Stabilisierung und Abschluss. Das Team für die Reaktion auf Sicherheitsvorfälle kann im Verlauf der Untersuchung zwischen den Stufen der Diagnose und der Stabilisierung wechseln. Nachfolgend finden Sie eine Übersicht über die Vorgehensweise bei Sicherheitsvorfällen:

|**Stufe**|**Beschreibung**|
| ------- | ------------- |
| ***1 – Erkennung*** | Erste Anzeichen für einen potenziellen Vorfall. |
| ***2 – Analyse*** | Ein abrufbereites Mitglied des Teams für die Reaktion auf Sicherheitsvorfälle analysiert die Auswirkungen und den Schweregrad des Ereignisses. Basierend auf den Nachweisen kann die Analyse zur einer Eskalation an das Sicherheitsteam führen. |
| ***3 – Diagnose*** | Sicherheitsexperten führen eine technische oder forensische Untersuchung durch und identifizieren Strategien für Eindämmung, Minderung und Abhilfe. Wenn das Sicherheitsteam der Meinung ist, dass möglicherweise Kundendaten gegenüber einer unbefugten Personen offengelegt wurden, wird parallel der Prozess zur Benachrichtigung des Kunden über den Sicherheitsvorfall in Gang gesetzt. |
| ***4 – Stabilisierung und Wiederherstellung*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt einen Wiederherstellungsplan, um das Problem zu mindern. Schritte zur Eindämmung der Auswirkungen, wie die Isolierung der betroffenen Systeme, können sofort und parallel zur Diagnose ausgeführt werden. Zudem können längerfristige Maßnahmen zur Risikominderung geplant werden, die umgesetzt werden, sobald die unmittelbare Gefahr gebannt ist. |
| ***5 – Abschluss und nachträgliche Analyse*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse, die den Vorfall detailliert untersucht, mit dem Ziel, die vorhandenen Richtlinien und Prozesse zu überarbeiten, um ein erneutes Auftreten des Ereignisses zu verhindern. |

Das Whitepaper [Microsoft Azure Security Response in the Cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) enthält weitere Informationen dazu, wie Microsoft Sicherheitsvorfälle in Azure untersucht, verwaltet und darauf reagiert.

Die Erkennungsprozesse von Microsoft Azure sind darauf ausgelegt, Ereignisse zu erkennen, welche die Vertraulichkeit, Integrität und Verfügbarkeit von Azure-Diensten gefährden. Verschiedene Ereignisse können eine Untersuchung auslösen:

- Automatisierte Systemwarnungen durch interne Überwachungs- und Warnungsframeworks. Diese Warnungen können in Form von signaturbasierten Alarmen eingehen wie Antischadsoftware oder Angriffserkennung bzw. über Algorithmen, die ein Profil der erwarteten Aktivität erstellen und bei Anomalien Warnungen ausgeben sollen.
- Erstanbieterberichte von Microsoft-Diensten, die unter Microsoft Azure und Azure Government ausgeführt werden.
- Sicherheitsrisiken werden dem [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) über [secure@microsoft.com](mailto:secure@microsoft.com) gemeldet. MSRC arbeitet mit Partnern und Sicherheitsforschern auf der ganzen Welt, um Sicherheitsvorfälle zu verhindern und die Sicherheit von Microsoft-Produkten zu erhöhen.
- Kundenberichte über das [Kundenportal](https://www.windowsazure.com/support/contact/) oder das Management Portal von Microsoft Azure und Azure Government, die der Azure-Infrastruktur zugeordnete verdächtige Aktivitäten beschreiben (im Gegensatz zu Aktivitäten, die in den Verantwortungsbereich des Kunden fallen).
- Aktivitäten der [roten und blauen Sicherheitsteams](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Bei dieser Strategie wird ein hoch qualifiziertes rotes Team aus offensiven Sicherheitsexperten von Microsoft eingesetzt, um potenzielle Schwächen in Azure aufzudecken und anzugreifen. Das blaue Sicherheitsteam muss die Aktivitäten des roten Teams erkennen und abwehren. Die Aktionen des roten wie auch des blauen Teams werden dazu verwendet, um zu überprüfen, ob die Sicherheitsmaßnahmen von Azure Sicherheitsvorfälle effektiv bewältigen. Die Aktivitäten des roten und blauen Sicherheitsteams müssen Regeln des Engagements einhalten, um den Schutz von Kundendaten zu gewährleisten.
- Eskalationen durch Mitarbeiter der Azure-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

## <a name="azures-data-breach-response"></a>Reaktion auf Datenschutzverletzungen in Azure

Microsoft weist der Untersuchung geeignete Prioritäts- und Schweregrade zu, indem die funktionellen Auswirkungen, die Wiederherstellbarkeit und die Beeinträchtigung von Daten durch den Vorfall bestimmt werden. Sowohl Prioritäten als auch Schweregrade können sich im Verlauf der Untersuchung aufgrund neuer Erkenntnisse und Schlussfolgerungen ändern. Sicherheitsereignisse, die ein unmittelbares oder bestätigtes Risiko für Kundendaten darstellen, werden als Ereignisse mit hohem Schweregrad behandelt, den deren Behebung rund um die Uhr gearbeitet wird. 

Microsoft Azure kategorisiert die Auswirkungen des Vorfalls auf die Informationen in die folgenden Kategorien von Sicherheitsverletzungen:

| **Kategorie**             | **Definition**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Keine***               | Es wurden keine Daten extrahiert, geändert, gelöscht oder anderweitig kompromittiert.                                                      |
| ***Datenschutzverletzung***     | Es wurde auf vertrauliche personenbezogene Daten von Steuerzahlern, Mitarbeitern, Begünstigten etc. zugegriffen oder diese wurden extrahiert.                                |
| ***Verletzung des Schutzes unternehmenseigener Daten*** | Es wurde auf nicht klassifizierte, unternehmenseigene Daten, z. B. geschützte kritische Infrastrukturdaten (Protected Critical Infrastructure Information, PCII), zugegriffen oder diese wurden extrahiert. |
| ***Integritätsverlust***     | Vertrauliche oder unternehmenseigene Daten wurden geändert oder gelöscht.                                                                     |

Das Sicherheitsteam arbeitet mit Sicherheitstechnikern und Sicherheitsexperten (Subject Matter Experts, SMEs) von Microsoft Azure zusammen, um das Ereignis basierend auf Fakten aus den gewonnenen Erkenntnissen zu klassifizieren. Ein Sicherheitsereignis kann wie folgt klassifiziert werden:

- **Falsch positives Ergebnis:** Ein Ereignis, das die Erkennungskriterien erfüllt, aber als Bestandteil einer normalen Geschäftspraxis gilt und möglicherweise gefiltert werden muss. Das Serviceteam ermittelt die Ursache für falsch positive Ergebnisse und behebt sie systematisch, indem Erkennungsquellen genutzt und bei Bedarf optimiert werden.
- **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf Kundendaten oder Supportdaten, die auf Geräten oder in Einrichtungen von Microsoft gespeichert sind, bzw. ein nicht autorisierter Zugriff auf diese Geräte oder Einrichtungen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat.
- **Meldepflichtiger Sicherheitsvorfall/Datenschutzvorfall (Customer-Reportable Security Incident, CRSI):** Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Einrichtungen von Microsoft bzw. eine unrechtmäßige oder nicht autorisierte Verwendung dieser Systeme, Geräte oder Einrichtungen, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat.
- **Datenschutzverletzung:** Ein Untertyp von Sicherheitsvorfällen im Zusammenhang mit personenbezogenen Daten. Die Verfahren gleichen denen bei Sicherheitsvorfällen.

Damit ein CRSPI deklariert werden kann, muss Microsoft feststellen, dass wahrscheinlich ein nicht autorisierter Zugriff auf Kundendaten stattgefunden hat und/oder dass eine gesetzliche oder vertragliche Verpflichtung zur Benachrichtigung besteht. Es ist wünschenswert, aber nicht zwingend erforderlich, dass die spezifische Auswirkung auf den Kunden, der Ressourcenzugriff und die Reparaturschritte bekannt sind. Ein Vorfall wird im Allgemeinen nach Abschluss der Diagnosestufe eines Sicherheitsvorfalls als CRSPI deklariert. Allerdings kann dies auch zu jedem beliebigen anderen Zeitpunkt stattfinden, an dem alle relevanten Informationen verfügbar sind. Der Manager für Sicherheitsvorfälle muss zweifelsfrei nachweisen, dass ein meldepflichtiges Ereignis eingetreten ist, um den Prozess der Benachrichtigung des Kunden zu starten.

Während der gesamten Untersuchung arbeitet das Sicherheitsteam eng mit weltweit tätigen Rechtsberatern zusammen, um sicherzustellen, dass die Forensik unter Einhaltung der gesetzlichen Verpflichtungen und Zusagen gegenüber dem Kunden ausgeführt wird. Es gibt zudem erhebliche Beschränkungen für das Anzeigen und Verarbeiten von System- und Kundendaten in verschiedenen Betriebsumgebungen. Sensible oder vertrauliche Daten sowie Kundendaten werden ohne explizite schriftliche Genehmigung des Managers von Sicherheitsvorfällen, der im entsprechenden Vorfallsticket angegeben ist, nicht aus der Produktionsumgebung heraus übertragen.

Microsoft überprüft, ob das Risiko für Kunden und Unternehmen erfolgreich gebannt wurde und ob Abhilfemaßnahmen implementiert wurden. Bei Bedarf werden Notfallverfahren zum Beheben unmittelbarer Sicherheitsrisiken im Zusammenhang mit dem Ereignis ausgeführt.

Microsoft führt zudem eine interne nachträgliche Analyse für Datenschutzverstöße durch. Als Teil dieser Analyse wird die Angemessenheit der Reaktions- und Betriebsprozesse ausgewertet und alle Verbesserungen, die an den Reaktions- und Betriebsprozessen für Sicherheitsvorfälle oder an zugehörigen Prozessen von Microsoft vorgenommen werden sollten, werden ermittelt und implementiert. Interne nachträgliche Analysen für Datenschutzverstöße sind streng vertrauliche Datensätze, die Kunden nicht zur Verfügung gestellt werden. Es kann jedoch vorkommen, dass die nachträglichen Vorgänge in anderen Kunden-Ereignisbenachrichtigungen zusammengefasst und einbezogen werden. Diese Berichte werden externen Auditoren zur Überprüfung als Teil des routinemäßigen Überwachungszyklus von Azure bereitgestellt.

## <a name="customer-notification"></a>Kundenbenachrichtigung

Microsoft Azure benachrichtigt Kunden und Aufsichtsbehörden vorgabengerecht über Datenschutzverletzungen. Microsoft baut auf eine starke interne Trennung des Betriebs von Azure. Datenflussprotokolle sind ebenfalls robust. Ein Vorteil dieses Designs ist, dass die meisten Vorfälle bestimmten Kunden zugeordnet werden können. Das Ziel ist, den betroffenen Kunden präzise, umsetzbare und zeitgerechte Informationen bereitzustellen, wenn der Schutz ihrer Daten verletzt wurde.

Der Benachrichtigungsprozess nach einem deklarierten CRSPI wird so rasch wie möglich in Gang gesetzt, wobei auch die Sicherheitsrisiken eines schnellen Handelns berücksichtigt werden. Im Allgemeinen erfolgt der Prozess des Benachrichtigungsentwurfs, während der Vorfall untersucht wird. Ab dem Zeitpunkt, an dem wir eine Datenschutzverletzung deklarieren, vergehen nicht mehr als 72 Stunden, bis wir unsere Kunden informieren, *außer* in den folgenden Situationen:

- Microsoft ist der Meinung, dass eine Benachrichtigung das Risiko für andere Kunden erhöht. Beispielsweise kann die Benachrichtigung an sich einen Gegenspieler über interne Abläufe informieren, wodurch es unmöglich wird, das Risiko zu beseitigen.
- Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung Corporate External and Legal Affairs (CELA) und dem leitenden Vorfall-Manager von Microsoft überprüft werden.
- Im Verlauf des 72-Stunden-Zeitlimits ergeben sich möglicherweise neue Erkenntnisse zum Vorfall. Diese werden Kunden und Aufsichtsbehörden bereitgestellt, sobald die Untersuchung fortschreitet.

Microsoft Azure stellt Kunden detaillierte Informationen bereit, sodass sie interne Untersuchungen ausführen können ihre Verpflichtungen gegenüber Endbenutzern erfüllen können, ohne den Benachrichtigungsprozess übermäßig zu verzögern.

Die Benachrichtigung zu einer Verletzung des Schutzes personenbezogener Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird der Liste der Sicherheitskontakte bereitgestellt, die im Azure Security Center hinterlegt ist und die mithilfe der [Implementierungsrichtlinien](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details) konfiguriert werden kann. Wenn keine Kontaktinformationen im Azure Security Center bereitgestellt werden, erfolgt die Benachrichtigung an einen oder mehrere Administratoren in einem Azure-Abonnement. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt werden kann, muss der Kunde dafür sorgen, dass die administrativen Kontaktinformationen in dem jeweiligen Abonnement und Onlinedienst-Portal korrekt sind.

Das Microsoft Azure- oder Azure Government-Team kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Account Manager (AM) oder Technical Account Manager (TAM) des Kunden zu benachrichtigen. Diese Personen stehen häufig in enger Beziehung zum Kunden und können eine schnellere Problembehebung realisieren.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 – Integrierte Sicherheitsfeatures

Microsoft Dynamics 365 nutzt die Cloud-Service-Infrastruktur und integrierten Sicherheitsfeatures, um Daten mithilfe von Sicherheitsmaßnahmen und -mechanismen zu schützen. Darüber hinaus bietet Dynamics 365 effizienten Datenzugriff und Zusammenarbeit plus Datenintegrität und Datenschutz in den folgenden Bereichen: [Sichere Identität, Datenschutz, rollenbasierte Sicherheit und Bedrohungsmanagement](https://www.microsoft.com/trustcenter/security/dynamics365-security).

Das Microsoft Dynamics 365-Angebot befolgt dieselben technischen und organisatorischen Maßnahmen, die ein oder mehrere Microsoft Azure-Dienstteams zur Sicherung gegen Datenverletzungsprozesse ergreifen. Daher sind alle Informationen, die im Benachrichtigungsdokument "Microsoft Azure-Datenverletzung" dokumentiert sind, analog zu Microsoft Dynamics 365.

## <a name="learn-more"></a>Weitere Informationen

[Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
