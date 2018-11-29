---
title: Azure und Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO
description: Wie Azure Schutz vor Datenschutzverletzungen für persönliche Daten bietet und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Verletzung auftritt.
keywords: Azure, Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 8b2a0bd52054a3228ba8c9536e6db552735b1f33
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867970"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a>Azure und Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO

Microsoft Azure nimmt seine Pflichten im Rahmen der Datenschutz-Grundverordnung (DSGVO) sehr ernst. Microsoft Azure ergreift umfassende Sicherheitsmaßnahmen, um Daten vor Sicherheitsverletzungen zu schützen. Diese umfassen sowohl physische und logische Sicherheitskontrollen als auch automatisierte Sicherheitsprozesse, umfassende Richtlinien zur Informationssicherheit und zum Datenschutz sowie Schulungen zur Sicherheit und zum Datenschutz für Mitarbeiter.

Sicherheit ist in Microsoft Azure von Grund auf integriert, beginnend mit dem [Security Development Lifecycle](https://www.microsoft.com/sdl/), einem obligatorischen Entwicklungsprozess, der benutzerdefinierte und standardmäßige Datenschutz-Methodologien umfasst. Das Leitprinzip der Sicherheitsstrategie von Microsoft besteht darin, vom Vorhandensein einer Datenschutzverletzung auszugehen, und stellt somit eine Erweiterung der Strategie für tiefgreifende, vorbeugende Sicherheit dar. Indem die Sicherheitsfunktionen von Azure ständig getestet werden, kann Microsoft neuen Bedrohungen immer einen Schritt voraus bleiben. Weitere Informationen zur Sicherheit bei Azure finden Sie in diesen [Ressourcen](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft verfügt über einen globalen, rund um die Uhr aktiven Service für die Reaktion auf Vorfälle, der daran arbeitet, die Auswirkungen von Angriffen gegen Microsoft Azure zu mindern. Microsoft nutzt in seinen Rechenzentren strenge Abläufe und Prozesse zur Verhinderung von nicht autorisiertem Zugriff, darunter 24-Stunden-Videoüberwachung, geschultes Sicherheitspersonal, Smartcards und biometrische Kontrollen. Dies wird durch mehrere Sicherheits- und Compliance-Audits bestätigt (z. B. [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)).

#### <a name="detection-of-potential-breaches"></a>Erkennung potenzieller Datenschutzverletzungen
-------------------------------

Aufgrund der Beschaffenheit des modernen Cloud Computings beziehen sich nicht alle Datenschutzverletzungen, die in einer Cloudumgebung des Kunden auftreten, auf Dienste von Microsoft Azure. Microsoft verwendet ein Modell der gemeinsamen Verantwortung für Azure-Dienste, in dem Verantwortlichkeiten für Sicherheit und operative Abläufe definiert sind. Gemeinsame Verantwortung ist besonders dann wichtig, wenn es um die Sicherheit von Clouddiensten geht, da sowohl der Anbieter des Clouddiensts als auch die Kunden jeweils für Teile der Cloudsicherheit zuständig sind.

Microsoft ergreift keine Überwachungs- oder Reaktionsmaßnahmen für Sicherheitsvorfälle, die im Verantwortlichkeitsbereich des Kunden auftreten. Ein Sicherheitsproblem, das nur den Kunden betrifft, wird nicht als Azure-Sicherheitsvorfall verarbeitet, sondern erfordert die Verwaltung der Reaktionsverfahren durch den Kundenmandanten. Die Reaktion auf Sicherheitsvorfälle durch den Kunden kann eine Zusammenarbeit mit dem [Kundensupport](https://azure.microsoft.com/support/options/) von Microsoft Azure umfassen, sofern entsprechende Service-Verträge bestehen. Microsoft Azure bietet auch verschiedene Dienste an (z. B. [Azure Security Center](https://azure.microsoft.com/services/security-center/)), die Kunden zur Entwicklung und Verwaltung einer Reaktion auf Sicherheitsvorfälle verwenden können.

Azure reagiert auf eine potenzielle Datenschutzverletzung entsprechend dem Prozess für die Reaktion auf Sicherheitsvorfälle, der Teil des Vorfallmanagementplans von Microsoft Azure ist. Die Reaktion auf Sicherheitsvorfälle seitens Azure erfolgt in fünf Stufen: Erkennung, Analyse, Diagnose, Stabilisierung und Abschluss. Das Team für die Reaktion auf Sicherheitsvorfälle kann im Verlauf der Untersuchung zwischen den Stufen der Diagnose und der Stabilisierung wechseln. Nachfolgend finden Sie eine Übersicht über die Vorgehensweise bei Sicherheitsvorfällen:

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Stufe</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Erkennung</td>
<td align="left">Erste Anzeichen für einen potenziellen Vorfall.</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Analyse</td>
<td align="left">Ein abrufbereites Mitglied des Teams für die Reaktion auf Sicherheitsvorfälle analysiert die Auswirkungen und den Schweregrad des Ereignisses. Basierend auf den Nachweisen kann die Analyse zur Eskalation an das Sicherheitsteam führen.</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Diagnose</td>
<td align="left"><p>Sicherheitsexperten führen eine technische oder forensische Untersuchung durch und identifizieren Strategien für Eindämmung, Minderung und Abhilfe.</p>
<p>Wenn das Sicherheitsteam der Meinung ist, dass möglicherweise Kundendaten gegenüber einer unbefugten Personen offengelegt wurden, wird parallel der Prozess zur Benachrichtigung des Kunden über den Sicherheitsvorfall in Gang gesetzt.</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Stabilisierung und Wiederherstellung</td>
<td align="left">Das Team für die Reaktion auf Sicherheitsvorfälle erstellt einen Wiederherstellungsplan, um das Problem zu mindern. Schritte zur Eindämmung der Krise, wie die Isolierung der betroffenen Systeme, können sofort und parallel zur Diagnose ausgeführt werden. Zudem können längerfristige Minderungen geplant werden, die ausgeführt werden, wenn die unmittelbare Gefahr gebannt ist.</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Abschluss und nachträgliche Analyse</td>
<td align="left">Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse mit den Details des Vorfalls, anhand dessen Richtlinien, Verfahren und Prozesse geprüft werden sollen, um ein erneutes Auftreten des Ereignisses zu verhindern.</td>
</tr>
</tbody>
</table>

Das Whitepaper [Reaktion auf Sicherheitsvorfälle in der Cloud bei Microsoft Azure](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) enthält weitere Informationen dazu, wie Microsoft bei Sicherheitsvorfällen in Azure untersucht, verwaltet und reagiert.

Die Erkennungsprozesse von Microsoft Azure sind darauf ausgelegt, Ereignisse zu erkennen, die die Vertraulichkeit, Integrität und Verfügbarkeit von Azure-Diensten gefährden. Verschiedene Ereignisse können eine Untersuchung auslösen:

-   Automatisierte Systembenachrichtigungen über interne Überwachungs- und Warnungs-Frameworks. Diese Warnungen können in Form von signaturbasierten Alarmen eingehen wie Malwareschutz oder Eindringungserkennung oder über Algorithmen, die bei Anomalien ein Profil der erwarteten Aktivität oder Warnung erstellen.

-   Erstparteiberichte von Microsoft Services, die auf Microsoft Azure und Azure Government ausgeführt werden.

-   Sicherheitsrisiken werden dem [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) über <secure@microsoft.com> gemeldet. MSRC arbeitet mit Partnern und Sicherheitsforschern auf der ganzen Welt, um Sicherheitsvorfälle zu verhindern und die Sicherheit von Microsoft-Produkten zu erhöhen.

-   Kundenberichte über das [Kundenportal](http://www.windowsazure.com/support/contact/) oder das Management Portal von Microsoft Azure und Azure Government, die der Azure-Infrastruktur zugeordnete verdächtige Aktivitäten beschreiben (im Gegensatz zu Aktivitäten, die in den Verantwortungsbereich des Kunden fallen).

-   Aktivität der [roten und blauen Sicherheitsteams](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Bei dieser Strategie wird ein hochqualifiziertes rotes Team aus offensiven Microsoft-Sicherheitsexperten eingesetzt, um mögliche Schwachstellen in Azure aufzudecken und anzugreifen. Das blaue Sicherheitsteam muss die Aktivität des roten Teams erkennen und abwehren. Anhand der Aktionen beider Teams soll überprüft werden, ob die Maßnahmen zur Reaktion auf Sicherheitsvorfälle von Azure Sicherheitsvorfälle effektiv beheben können. Für die Aktivitäten des roten und blauen Sicherheitsteams gelten Einsatzregeln, um den Schutz von Kundendaten sicherzustellen.

-   Eskalationen von Operatoren der Azure-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

#### <a name="azures-data-breach-response"></a>Reaktion auf Datenschutzverletzungen in Azure
----------------------------

Microsoft weist der Untersuchung entsprechende Prioritäts- und Schweregrade zu, indem die vorfallsbedingten Auswirkungen auf die Funktionsfähigkeit, die Wiederherstellbarkeit und die Daten ermittelt werden. Priorität und Schweregrad können sich im Laufe der Untersuchung basierend auf neuen Erkenntnissen und Schlussfolgerungen ändern. Sicherheitsrelevante Ereignisse, von denen bevorstehende oder bestätigte Gefahren für Kundendaten ausgehen, erhalten hohe Priorität und werden bis zur Lösung rund um die Uhr bearbeitet. Microsoft Azure ordnet den Vorfall anhand der Auswirkungen auf die Daten in eine der folgenden Kategorien ein:

<table>
<thead>
<tr class="header">
<th align="left">Kategorie</th>
<th align="left">Definition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Keine</td>
<td align="left">Es wurden keine Daten extrahiert, geändert, gelöscht oder anderweitig kompromittiert.</td>
</tr>
<tr class="even">
<td align="left">Datenschutzverletzung</td>
<td align="left">Es wurde auf vertrauliche personenbezogene Daten von Steuerzahlern, Mitarbeitern, Begünstigten etc. zugegriffen oder diese wurden extrahiert.</td>
</tr>
<tr class="odd">
<td align="left">Verletzung des Schutzes unternehmenseigener Daten</td>
<td align="left">Es wurde auf nicht klassifizierte, unternehmenseigene Daten, z. B. geschützte kritische Infrastrukturdaten (Protected Critical Infrastructure Information, PCII), zugegriffen oder diese wurden extrahiert.</td>
</tr>
<tr class="even">
<td align="left">Integritätsverlust</td>
<td align="left">Vertrauliche oder unternehmenseigene Daten wurden geändert oder gelöscht.</td>
</tr>
</tbody>
</table>

Das Sicherheitsteam arbeitet mit Sicherheitstechnikern und SMEs von Microsoft Azure, um das Ereignis basierend auf sachbezogenen Daten aus den Beweisen zu klassifizieren. Ein Sicherheitsereignis kann klassifiziert werden als:

-   **Falsch positives Ereignis:** Ein Ereignis, das die Erkennungskriterien erfüllt, aber Teil der normalen Geschäftsabläufe ist und möglicherweise gefiltert werden muss. Das Serviceteam identifiziert die Ursache für falsch positive Ereignisse und behandelt sie auf systematische Weise unter Verwendung von Erkennungsquellen und bedarfsgerechter<span id="_Toc350859432" class="anchor"></span> Optimierung.

-   **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf in Geräten oder Anlagen von Microsoft gespeicherte Kundendaten oder Supportdaten oder ein nicht autorisierter Zugriff auf solche Geräte oder Anlagen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat.

-   **Meldepflichtiger Sicherheitsvorfall (Customer-Reportable Security Incident, CRSI):** Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Anlagen von Microsoft bzw. deren Verwendung, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat.

-   **Datenschutzverletzung:** Ein Untertyp von Sicherheitsvorfällen im Zusammenhang mit persönlichen Daten. Die Verfahren gleichen denen bei Sicherheitsvorfällen.

Damit ein CRSI erklärt werden kann, muss Microsoft bestimmen, dass ein nicht autorisierter Zugriff auf Kundendaten erfolgt ist oder sehr wahrscheinlich erfolgt ist und/oder dass eine rechtliche oder vertragliche Meldepflicht besteht. Es ist wünschenswert, aber nicht erforderlich, dass bestimmte Kundenauswirkungen, Ressourcenzugriff und Schritte zur Behebung bekannt sind. Ein Vorfall wird im Allgemeinen nach Abschluss der Diagnosestufe eines Sicherheitsvorfalls zu einem CRSI erklärt. Die Erklärung kann aber zu einem beliebigen Zeitpunkt erfolgen, sofern alle relevanten Informationen zur Verfügung stehen. Der Manager des Sicherheitsvorfalls muss zweifelsfrei nachweisen, dass ein meldepflichtiges Ereignis aufgetreten ist, um mit der Ausführung des Prozesses zur Benachrichtigung des Kunden über den Sicherheitsvorfall zu beginnen.

Während der Untersuchung arbeitet das Sicherheitsteam eng mit globalen Rechtsberatern zusammen, um sicherzustellen, dass die Forensik entsprechend den gesetzlichen Verpflichtungen und Pflichten gegenüber dem Kunden ausgeführt wird. Es gibt zudem erhebliche Beschränkungen für das Anzeigen und Behandeln von System- und Kundendaten in verschiedenen Betriebsumgebungen. Sensible oder vertrauliche Daten sowie Kundendaten werden ohne explizite schriftliche Genehmigung des Vorfall-Managers, die im entsprechenden Vorfallsticket aufgezeichnet wird, nicht aus der Produktionsumgebung heraus übertragen.

Microsoft überprüft, ob das Risiko für Kunden und Unternehmen erfolgreich gebannt wurde und ob Abhilfemaßnahmen implementiert wurden. Bei Bedarf werden Notfallverfahren zum Beheben unmittelbarer Sicherheitsrisiken im Zusammenhang mit dem Ereignis ausgeführt.

Microsoft nimmt auch eine interne nachträgliche Analyse zu Datenschutzverletzungen vor. Im Rahmen dieser Übung wird die Angemessenheit von Reaktions- und Betriebsverfahren bewertet und es werden etwaige notwendige Updates an dem SOP für die Reaktion auf Sicherheitsvorfälle oder zugehörigen Prozessen identifiziert und implementiert. Interne nachträgliche Analysen zu Datenschutzverletzungen sind streng vertrauliche Datensätze, auf die Kunden keinen Zugriff haben. Diese Analysen können allerdings in zusammengefasster Form in andere Kundenbenachrichtigungen zu Ereignissen aufgenommen werden. Die Analysen werden im Rahmen des routinemäßigen Auditzyklus von Azure durch externe Auditoren geprüft.

#### <a name="customer-notification"></a>Kundenbenachrichtigung
---------------------

Microsoft Azure benachrichtigt den Kunden und Aufsichtsbehörden entsprechend den Vorschriften über Datenschutzverletzungen. Microsoft baut auf eine umfangreiche interne Trennung im Betrieb von Azure-Diensten. Datenflussprotokolle sind ebenfalls robust. Ein Vorteil dieses Entwurfs besteht darin, dass die meisten Vorfälle auf bestimmte Kunden eingegrenzt werden können. Das Ziel besteht darin, betroffenen Kunden genaue, umsetzbare und zeitgerechte Informationen bereitzustellen, wenn Datenschutzverletzungen im Hinblick auf ihre Daten aufgetreten sind.

Der Benachrichtigungsprozess bei einem deklarierten CRSI wird so rasch wie möglich in Gang gesetzt, wobei auch die Sicherheitsrisiken eines schnellen Handelns berücksichtigt werden. Im Allgemeinen wird der Prozess des Benachrichtigungsentwurfs durchgeführt, während der Vorfall untersucht wird. Kundenbenachrichtigungen werden ab dem Zeitpunkt, an dem wir einen Verstoß deklarieren, innerhalb von 72 Stunden übermittelt, *mit Ausnahme * der folgenden Situationen:

-   Microsoft ist der Meinung, dass eine Benachrichtigung das Risiko für andere Kunden erhöht. Beispielsweise kann durch das Benachrichtigen ein Widersacher informiert und eine Abhilfe verhindert werden.

-   Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung Corporate External and Legal Affairs (CELA) und dem leitenden Vorfall-Manager von Microsoft überprüft werden.

Microsoft Azure bietet Kunden ausführliche Informationen, sodass sie interne Untersuchungen ausführen können und die Erfüllung von Verpflichtungen gegenüber Endbenutzern erleichtert wird, ohne den Benachrichtigungsprozess übermäßig zu verzögern.

Die Benachrichtigung über eine Verletzung im Hinblick auf personenbezogene Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird an die in Azure Security Center hinterlegte Liste der Sicherheitskontakte übermittelt, die gemäß der [Implementierungsanleitung](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details) konfiguriert werden kann. Wenn in Azure Security Center keine Kontaktdaten angegeben werden, wird die Benachrichtigung an einen oder mehrere Administratoren des Azure-Abonnements gesendet. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt werden kann, muss der Kunde sicherstellen, dass die administrativen Kontaktinformationen für jedes geltende Abonnement und im Online Services-Portal korrekt sind.

Das Team von Microsoft Azure oder Azure Government kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Konto-Manager oder technischen Konto-Manager des Kunden zu benachrichtigen. Diese Personen haben häufig enge Beziehungen zum Kunden und können eine schnellere Problembehebung erzielen.<span id="_Appendix_A" class="anchor"></span>

#### <a name="microsoft-intune-data-breach"></a>Datenschutzverletzungen in Microsoft Intune
----------------------------

Microsoft Intune ist eine Schlüsselkomponente des Clouddienst-Angebots Microsoft Enterprise Mobility and Security Suite. Zur Unterstützung der Data-Governance-Strategie  werden alle Microsoft Cloud Services mit den Microsoft-Methodologien Privacy and Security by Design und Privacy and Security by Default entwickelt.

Daher folgt das Clouddienst-Angebot von Microsoft Intune den gleichen technischen und organisatorischen Maßnahmen, die das Serviceteam von Microsoft Azure zum Schutz gegen Datenschutzverletzungen ergreift. Daher entsprechen sämtliche Informationen in dem hier aufgeführten Benachrichtigungsdokument  „Microsoft Azure Data Breach“  ebenfalls dem Microsoft Intune-Dienst. Beispielsweise verfügt Microsoft Intune über den gleichen Prozess und Lebenszyklus für die Reaktion auf Sicherheitsvorfälle (Stufe 1: Erkennung bis Stufe 5<strong>:</strong> Abschluss und nachträgliche Analyse) und auch denselben Prozess zur Kundenbenachrichtigung über Sicherheitsvorfälle. Darüber hinaus erfüllt Microsoft Intune die Anforderungen an die Benachrichtigung bei Sicherheitsverletzungen für Kunden von Microsoft O365, die Intune verwenden, durch eine direkte Zusammenarbeit mit dem Team von Microsoft O365.

Weitere Informationen darüber, wie Microsoft eine Verletzung von personenbezogenen Daten erkennt und darauf reagiert, finden Sie im Service Trust Portal unter [Benachrichtigung bei Datenschutzverletzungen im Rahmen der DSGVO](https://servicetrust.microsoft.com/ViewPage/GDPRBreach).


#### <a name="learn-more"></a>Weitere Informationen
[Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
