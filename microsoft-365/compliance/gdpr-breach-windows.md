---
title: Benachrichtigungen des Datenauftragsverarbeiterdiensts für Windows gemäß DSGVO
description: Wie der Datenauftragsverarbeiterdienst für Windows Schutz vor Datenschutzverletzungen für persönliche Daten bietet und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Datenschutzverletzung auftritt.
keywords: Datenauftragsverarbeiterdienst für Windows, Microsoft 365, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: bfadeae0f4f0b01197f58f0610d1040da3080922
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023608"
---
# <a name="data-processor-service-for-windows-breach-notification-under-the-gdpr"></a>Benachrichtigung des Datenauftragsverarbeiterdiensts für Windows über eine Datenschutzverletzung gemäß DSGVO

>[!NOTE]
>Dieser Artikel richtet sich an Teilnehmer am Vorschauprogramm „Datenauftragsverarbeiterdienst für Windows“ und setzt die Zustimmung zu bestimmten Nutzungsbedingungen voraus. Wenn Sie mehr über das Programm erfahren und den Nutzungsbedingungen zustimmen möchten, wechseln Sie zu [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview).

Der Microsoft-Datenauftragsverarbeiterdienst für Windows nimmt seine Verpflichtungen gemäß der Datenschutz-Grundverordnung (DSGVO) ernst. Der Microsoft-Datenauftragsverarbeiterdienst für Windows ergreift umfangreiche Sicherheitsmaßnahmen zum Schutz vor Datenschutzverletzungen. Diese umfassen dedizierte Threat Management-Teams, die in der Lage sind, böswillige Zugriffe proaktiv vorherzusehen, zu verhindern und abzuschwächen.Interne Sicherheitsmaßnahmen, z. B. Portüberwachung, Prüfung des Perimeters auf Sicherheitslücken und Erkennung von Eindringversuchen, erkennen und verhindern böswilligen Zugriff als auch automatisierte Sicherheitsprozesse, umfassende Informationen zu Sicherheits- und Datenschutzrichtlinien sowie Sicherheits- und Datenschutzschulungen für alle Mitarbeiter. 

Sicherheit ist in den Microsoft-Datenauftragsverarbeiterdienst für Windows von Grund auf integriert, beginnend mit dem [Security Development Lifecycle](https://www.microsoft.com/sdl/), einem obligatorischen Entwicklungsprozess, der Methoden für entwurfsgemäßen und standardmäßigen Datenschutz umfasst. Das Leitprinzip der Sicherheitsstrategie von Microsoft besteht darin, vom „Vorhandensein einer Datenschutzverletzung auszugehen“, und stellt somit eine Erweiterung der Strategie für tiefgreifende, vorbeugende Sicherheit dar. Indem die Sicherheitsfunktionen des Datenauftragsverarbeiterdiensts für Windows ständig getestet werden, kann Microsoft neuen Bedrohungen immer einen Schritt voraus bleiben. Weitere Informationen zur Sicherheit des Datenauftragsverarbeiterdiensts für Windows finden Sie in [diesen Ressourcen](https://www.microsoft.com/TrustCenter/Security/windows10-security). Der Datenauftragsverarbeiterdienst für Windows reagiert auf eine potenzielle Datenschutzverletzung gemäß dem Prozess für die Reaktion auf Sicherheitsvorfälle. Die Reaktion des Datenauftragsverarbeiterdiensts für Windows auf einen Sicherheitsvorfall ist in Form eines fünfstufigen Prozesses implementiert: Erkennen, Bewerten, Diagnostizieren, Stabilisieren und Schließen. Im Verlauf der Untersuchung kann das Reaktionsteam für Sicherheitsvorfälle zwischen den Stufen der Diagnose und Stabilisierung wechseln. Eine Übersicht des Prozesses für die Reaktion auf Sicherheitsvorfälle finden Sie im Folgenden: 

|**Stage**|**Beschreibung**|
| ------- | ------------- |
| ***1 – Erkennung*** | Erste Anzeichen für einen potenziellen Vorfall. |
| ***2 – Analyse*** | An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team. |
| ***3 – Diagnose*** | Sicherheitsexperten führen eine technische oder forensische Untersuchung durch und identifizieren Strategien für Eindämmung, Minderung und Abhilfe. Wenn das Sicherheitsteam der Meinung ist, dass möglicherweise Kundendaten gegenüber einer unbefugten Personen offengelegt wurden, wird parallel der Prozess zur Benachrichtigung des Kunden über den Sicherheitsvorfall in Gang gesetzt. |
| ***4 – Stabilisierung und Wiederherstellung*** | The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed. |
| ***5 – Abschluss und nachträgliche Analyse*** | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse mit den Details des Vorfalls, anhand dessen Richtlinien, Verfahren und Prozesse geprüft werden sollen, um ein erneutes Auftreten des Ereignisses zu verhindern. |

Die Erkennungsprozesse, die der Datenauftragsverarbeiterdienst für Windows verwendet, sind darauf ausgelegt, Ereignisse zu erkennen, die die Vertraulichkeit, Integrität und Verfügbarkeit des Datenauftragsverarbeiterdiensts für Windows gefährden. Verschiedene Ereignisse können eine Untersuchung auslösen: 

 - Automatisierte Systemwarnungen durch interne Überwachungs- und Warnungsframeworks. Diese Warnungen können in Form von signaturbasierten Alarmen eingehen wie Antischadsoftware oder Angriffserkennung bzw. über Algorithmen, die ein Profil der erwarteten Aktivität erstellen und bei Anomalien Warnungen ausgeben sollen.
 - Erstanbieterberichte von Microsoft-Diensten, die unter Microsoft Azure und Azure Government ausgeführt werden.
 - Sicherheitslücken werden dem [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) über [secure@microsoft.com] (mailto:secure@microsoft.com) gemeldet. MSRC arbeitet mit Partnern und Sicherheitsforschern auf der ganzen Welt, um Sicherheitsvorfälle zu verhindern und die Sicherheit von Microsoft-Produkten zu erhöhen.
 - Kundenberichte über das Kundenportal oder das Management Portal von Microsoft Azure und Azure Government, die der Azure-Infrastruktur zugeordnete verdächtige Aktivitäten beschreiben (im Gegensatz zu Aktivitäten, die in den Verantwortungsbereich des Kunden fallen).
 - Aktivitäten der [roten und blauen Sicherheitsteams](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Bei dieser Strategie wird ein hoch qualifiziertes rotes Team aus offensiven Sicherheitsexperten von Microsoft eingesetzt, um potenzielle Schwächen in Azure aufzudecken und anzugreifen. Das blaue Sicherheitsteam muss die Aktivitäten des roten Teams erkennen und abwehren. Die Aktionen des roten wie auch des blauen Teams werden dazu verwendet, um zu überprüfen, ob die Sicherheitsmaßnahmen von Azure Sicherheitsvorfälle effektiv bewältigen. Die Aktivitäten des roten und blauen Sicherheitsteams müssen Regeln des Engagements einhalten, um den Schutz von Kundendaten zu gewährleisten.
 - Eskalationen durch Mitarbeiter der Azure-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

 ## <a name="data-processor-service-for-windows-data-breach-response"></a>Reaktion des Datenauftragsverarbeiterdiensts für Windows auf eine Datenschutzverletzung 

 Microsoft weist der Untersuchung geeignete Prioritäts- und Schweregrade zu, indem die funktionellen Auswirkungen, die Wiederherstellbarkeit und die Beeinträchtigung von Daten durch den Vorfall bestimmt werden. Sowohl Prioritäten als auch Schweregrade können sich im Verlauf der Untersuchung aufgrund neuer Erkenntnisse und Schlussfolgerungen ändern. Sicherheitsereignisse, die ein unmittelbares oder bestätigtes Risiko für Kundendaten darstellen, werden als Ereignisse mit hohem Schweregrad behandelt, den deren Behebung rund um die Uhr gearbeitet wird. Der Datenauftragsverarbeiterdienst für Windows kategorisiert die Auswirkungen des Vorfalls auf die Informationen in die folgenden Kategorien von Datenschutzverletzungen: 

| **Kategorie**             | **Definition**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Keine***               | Es wurden keine Daten extrahiert, geändert, gelöscht oder anderweitig kompromittiert. |
| ***Datenschutzverletzung***     | Es wurde auf vertrauliche personenbezogene Daten von Steuerzahlern, Mitarbeitern, Begünstigten etc. zugegriffen oder diese wurden extrahiert. |
| ***Verletzung des Schutzes unternehmenseigener Daten*** | Es wurde auf nicht klassifizierte, unternehmenseigene Daten, z. B. geschützte kritische Infrastrukturdaten (Protected Critical Infrastructure Information, PCII), zugegriffen oder diese wurden extrahiert. |
| ***Integritätsverlust***     | Vertrauliche oder unternehmenseigene Daten wurden geändert oder gelöscht. |

Das Sicherheitsreaktionsteam arbeitet mit Sicherheitstechnikern und Sicherheitsexperten (Subject Matter Experts, SMEs) des Datenauftragsverarbeiterdiensts für Windows zusammen, um das Ereignis basierend auf Fakten aus den gewonnenen Erkenntnissen zu klassifizieren. Ein Sicherheitsereignis kann wie folgt klassifiziert werden: 

 - **Falsch positives Ergebnis:** Ein Ereignis, das die Erkennungskriterien erfüllt, aber als Bestandteil einer normalen Geschäftspraxis gilt und möglicherweise gefiltert werden muss. Das Serviceteam ermittelt die Ursache für falsch positive Ergebnisse und behebt sie systematisch, indem Erkennungsquellen genutzt und bei Bedarf optimiert werden. 
 - **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf Kundendaten oder Supportdaten, die auf Geräten oder in Einrichtungen von Microsoft gespeichert sind, bzw. ein nicht autorisierter Zugriff auf diese Geräte oder Einrichtungen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat. 
 - **Meldepflichtiger Sicherheitsvorfall (Customer-Reportable Security Incident, CRSI)**: Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Anlagen von Microsoft bzw. deren Verwendung, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat. 
 - **Datenschutzverletzung:** Ein Untertyp von Sicherheitsvorfällen im Zusammenhang mit personenbezogenen Daten. Die Verfahren gleichen denen bei Sicherheitsvorfällen. 

 For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process. 

Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket. 

Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken. 

Microsoft führt zudem eine interne nachträgliche Analyse für Datenschutzverstöße durch. Als Teil dieser Analyse wird die Angemessenheit der Reaktions- und Betriebsprozesse ausgewertet und alle Verbesserungen, die an den Reaktions- und Betriebsprozessen für Sicherheitsvorfälle oder an zugehörigen Prozessen von Microsoft vorgenommen werden sollten, werden ermittelt und implementiert. Interne nachträgliche Analysen für Datenschutzverstöße sind streng vertrauliche Datensätze, die Kunden nicht zur Verfügung gestellt werden. Sie können aber zusammengefasst und in andere Ereignisbenachrichtigungen für Kunden eingeschlossen werden. Diese Berichte werden externen Auditoren zur Überprüfung als Teil des routinemäßigen Überwachungszyklus des Datenauftragsverarbeiterdiensts für Windows bereitgestellt. 

## <a name="customer-notice"></a>Kundenbenachrichtigung

Der Microsoft-Datenauftragsverarbeiterdienst für Windows benachrichtigt Kunden und Aufsichtsbehörden vorgabegerecht über Datenschutzverstöße. Microsoft baut auf eine hochgradige interne Trennung beim Betrieb des Datenauftragsverarbeiterdiensts für Windows. Datenflussprotokolle sind ebenfalls robust. Ein Vorteil dieses Designs ist, dass die meisten Vorfälle bestimmten Kunden zugeordnet werden können. Das Ziel ist, den betroffenen Kunden präzise, umsetzbare und zeitgerechte Informationen bereitzustellen, wenn der Schutz ihrer Daten verletzt wurde. 

Der Benachrichtigungsprozess nach einem deklarierten CRSI wird so rasch wie möglich in Gang gesetzt, wobei auch die Sicherheitsrisiken eines schnellen Handelns berücksichtigt werden. Im Allgemeinen erfolgt der Prozess des Benachrichtigungsentwurfs, während der Vorfall untersucht wird. Ab dem Zeitpunkt, an dem wir eine Datenschutzverletzung deklarieren, vergehen nicht mehr als 72 Stunden, bis wir unsere Kunden informieren, mit Ausnahme der folgenden Situationen: 

 - Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate. 
 - Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung Corporate External and Legal Affairs (CELA) und dem leitenden Vorfall-Manager von Microsoft überprüft werden. 

 Der Microsoft-Datenauftragsverarbeiterdienst für Windows bietet Kunden ausführliche Informationen, sodass sie interne Untersuchungen ausführen können und die Erfüllung von Verpflichtungen gegenüber Endbenutzern erleichtert wird, ohne den Benachrichtigungsprozess übermäßig zu verzögern. 

Die Benachrichtigung zu einer Verletzung des Schutzes personenbezogener Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird der Liste der Sicherheitskontakte bereitgestellt, die im Azure Security Center hinterlegt ist und die mithilfe der [Implementierungsrichtlinien](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details) konfiguriert werden kann. Wenn keine Kontaktinformationen im Azure Security Center bereitgestellt werden, erfolgt die Benachrichtigung an einen oder mehrere Administratoren in einem Azure-Abonnement. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt werden kann, muss der Kunde dafür sorgen, dass die administrativen Kontaktinformationen in dem jeweiligen Abonnement und Onlinedienst-Portal korrekt sind.

Das Team des Datenauftragsverarbeiterdiensts für Windows kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Account Manager (AM) oder Technical Account Manager (TAM) des Kunden zu benachrichtigen. Diese Personen stehen häufig in enger Beziehung zum Kunden und können eine schnellere Problembehebung realisieren. 

Weitere Informationen darüber, wie Microsoft eine Verletzung des Schutzes personenbezogener Daten erkennt und darauf reagiert, finden Sie im Service Trust Portal unter [Benachrichtigung bei Datenschutzverletzungen im Rahmen der DSGVO](https://servicetrust.microsoft.com/ViewPage/GDPRBreach).