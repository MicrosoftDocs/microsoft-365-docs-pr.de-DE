---
title: Schritt 1. Triagen und Analysieren Des ersten Vorfalls
description: So triage und beginnen Sie mit der Analyse Ihres ersten Vorfalls in Microsoft 365 Defender.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1890b4f9b4c71efebe833ebaee62debedbf0fb72
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114925"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Schritt 1. Triagen und Analysieren Des ersten Vorfalls

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Während Sie einige Zeit mit der Einrichtung, Implementierung und Verwaltung von Sicherheitsmaßnahmen gemäß den Standards der Organisation verbringen, können Sie Sicherheitslösungen einrichten, um Sicherheitsrisiken und Bedrohungen schnell zu identifizieren. Microsoft 365 Defender ermöglicht Ihnen das Erkennen, Austrinken und Untersuchen von Vorfällen über die Single-Pane-of-Glass-Erfahrung, in der Sie die Informationen finden, die Sie benötigen, um zeitnahe Entscheidungen zu treffen. 

Sobald ein Sicherheitsvorfall erkannt wurde, Microsoft 365 Defender Details vor, die Sie für die Triage oder Priorisierung eines Vorfalls oder von Vorfällen gegenüber anderen Personen benötigen. Nach der Festlegung der Priorisierung können Analysten ihre Energie dann auf die Untersuchung der ihnen zugewiesenen Fälle konzentrieren.

## <a name="detection-by-microsoft-365-defender"></a>Erkennung durch Microsoft 365 Defender

Microsoft 365 Defender empfängt Warnungen und Ereignisse von mehreren Microsoft-Sicherheitsplattformen als Erkennungsquellen, um ein ganzheitliches Bild und einen Kontext bösartiger Aktivitäten zu erstellen. Dies sind die möglichen Erkennungsquellen:

- [Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md) ist eine EDR (EDR), die Microsoft Defender Antivirus sowie cloudfähigen erweiterten Bedrohungsschutz mithilfe von Microsoft Security Graph. Defender for Endpoint ist eine einheitliche Plattform für vorbeugenden Schutz, erkennung nach Sicherheitsverletzungen, automatisierte Untersuchung und Reaktion. Es schützt Endpunkte vor Cyberangriffen, erkennt erweiterte Angriffe und Datenschutzverletzungen, automatisiert Sicherheitsvorfälle und verbessert die Sicherheitslage. 
- [Microsoft Defender for Identity](https://docs.microsoft.com/defender-for-identity/what-is) ist eine cloudbasierte Sicherheitslösung, die Ihre lokalen Active Directory Domain Services (AD DS)-Signale verwendet, um erweiterte Bedrohungen, gefährdete Identitäten und böswillige Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die auf Ihre Organisation gerichtet sind. 
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) fungiert als Gatekeeper, um den Zugriff in Echtzeit zwischen Ihren Unternehmensbenutzern und den von ihnen verwendeten Cloudressourcen zu vermitteln, unabhängig davon, wo Sich Ihre Benutzer befinden und unabhängig vom verwendeten Gerät. 
- [Microsoft Defender for Office 365](../office-365-security/overview.md) schützt Ihre Organisation vor böswilligen Bedrohungen in E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. 
- [Azure Security Center ist](https://docs.microsoft.com/azure/security-center/security-center-introduction) ein einheitliches Sicherheitsverwaltungssystem für die Infrastruktur, das die Sicherheitslage Ihrer Rechenzentren verstärkt und erweiterten Bedrohungsschutz für Ihre Hybridarbeitslasten in der Cloud und lokal bietet. 

In Microsoft 365 Defender [werden Vorfälle](incidents-overview.md) durch Korrelieren von Warnungen aus diesen verschiedenen Erkennungsquellen identifiziert. Anstatt Ressourcen zu verketten oder mehrere Warnungen in ihren jeweiligen Vorfällen zu unterscheiden, können Sie sofort mit der Warteschlange für Vorfälle in Microsoft 365 Defender beginnen. Auf diese Weise können Sie Vorfälle effizient über Endpunkte, Identitäten, E-Mails und Anwendungen hinweg verdingen und den Schaden durch einen Angriff verringern.

## <a name="triage-your-incidents"></a>Triagen Ihrer Vorfälle

Die Reaktion auf Vorfälle in Microsoft 365 Defender beginnt, sobald Sie die Liste der Vorfälle mithilfe der empfohlenen Priorisierungsmethode Ihrer Organisation abarbeiten. Das Triagen bedeutet, vorfällen eine Wichtigkeits- oder Dringlichkeitsstufe zuzuordnen, die dann die Reihenfolge bestimmt, in der sie untersucht werden. 

Eine nützliche Beispielanleitung zum Bestimmen, welcher Vorfall in Microsoft 365 Defender priorisiert werden soll, kann durch die Formel zusammengefasst werden: *Schweregrad + Auswirkung = Priorität*. 

- **Schweregrad** ist die von defender Microsoft 365 integrierte Sicherheitskomponenten festgelegte Stufe. 
- **Die** Auswirkungen werden von der Organisation bestimmt und umfassen im Allgemeinen eine Schwellenanzahl betroffener Benutzer, Geräte, Dienste (oder eine Kombination davon) und sogar den Warnungstyp. 

Analysten initiieren dann Untersuchungen basierend auf den Von der Organisation festgelegten **Prioritätskriterien.**

Die Priorisierung von Vorfällen kann je nach Organisation variieren. NIST empfiehlt außerdem, die funktionalen und informationellen Auswirkungen des Vorfalls sowie die Wiederherstellbarkeit zu prüfen.  

Im Folgenden finden Sie nur einen Ansatz für die Triage: 

1. Wechseln Sie zur [Seite Vorfälle,](incidents-overview.md) um die Triage zu initiieren. Hier sehen Sie eine Liste der Vorfälle, die sich auf Ihre Organisation ausdingen. Standardmäßig werden sie vom neuesten bis zum ältesten Vorfall angeordnet. Von hier aus können Sie auch unterschiedliche Spalten für jeden Vorfall anzeigen, die unter anderem den Schweregrad, die Kategorie, die Anzahl aktiver Warnungen und betroffener Entitäten anzeigen. Sie können den Satz von Spalten anpassen und die Warteschlange für Vorfälle nach einigen dieser Spalten sortieren, indem Sie den Spaltennamen auswählen. Sie können die Warteschlange für Vorfälle auch nach Ihren Anforderungen filtern. Eine vollständige Liste der verfügbaren Filter finden Sie unter [Prioritize incidents](incident-queue.md#available-filters).
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Beispiel für die Warteschlange für Vorfälle"::: 

    Ein Beispiel dafür, wie Sie eine Triage für diese Gruppe von Vorfällen ausführen können, ist die Priorisierung von Vorfällen, die mehr Benutzer und Geräte betroffen haben. In diesem Beispiel können Sie die Vorfall-ID 6769 priorisieren, da sie die größte Anzahl von Entitäten betroffen hat: 7 Geräte, 6 Benutzer und 2 Postfächer. Darüber hinaus enthält der Vorfall Warnungen von Microsoft Defender for Identity, die auf eine identitätsbasierte Warnung und möglichen Diebstahl von Anmeldeinformationen hinweisen.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Beispiel für einen Vorfall mit hoher Auswirkung":::
 
2. Wählen Sie den Kreis neben dem Vorfallnamen aus, um die Details zu überprüfen. Auf der rechten Seite wird ein Seitenbereich angezeigt, der zusätzliche Informationen enthält, die Ihre Triage weiter unterstützen können. 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Beispiel für einen Seitenbereich für Vorfälle"::: 

   Wenn Sie beispielsweise sehen, welche [MITRE ATT&](https://attack.mitre.org/) CK-Taktiken der Angreifer basierend auf den Kategorien des Vorfalls verwendet hat, können Sie diesen Vorfall priorisieren, da der Angreifer gestohlene Anmeldeinformationen verwendet, Befehl und Steuerung eingerichtet, eine laterale Bewegung ausgeführt und einige Daten exfiltriert hat. Dies deutet darauf hin, dass der Angreifer bereits tief in das Netzwerk eingegangen ist und möglicherweise vertrauliche Informationen gestohlen hat.

   Wenn Ihre Organisation außerdem das Zero Trust-Framework implementiert hat, würden Sie den Zugriff auf Anmeldeinformationen als einen wichtigen Sicherheitsverstoß betrachten, der priorisiert werden sollte.
 
   Beim Bildlauf nach unten im Seitenbereich werden die spezifischen betroffenen Entitäten wie Benutzer, Geräte und Postfächer angezeigt. Sie können die Belichtungsstufe der einzelnen Geräte und die Besitzer betroffener Postfächer überprüfen.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Beispiel für Details zum Seitenbereich eines Vorfalls"::: 
 
3. Weiter unten im Seitenbereich finden Sie die zugeordneten Warnungen. Microsoft 365 Defender hat die Korrelation der Warnungen zu einem einzelnen Vorfall bereits ausgeführt, was Ihnen Zeit und Ressourcen einspart, um den Angriff besser zu abwehren. Warnungen sind verdächtige und daher möglicherweise bösartige Systemereignisse, die das Vorhandensein eines Angreifers in einem Netzwerk nahelegen. 

   In diesem Beispiel wurden 87 einzelne Warnungen als Teil eines Sicherheitsvorfalls ermittelt. Sie können alle Warnungen anzeigen, um eine schnelle Ansicht zu erhalten, wie der Angriff abgespielt wurde.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Beispiel für Warnungen in einem Seitenbereich für Vorfälle"::: 
 
## <a name="analyze-your-first-incident"></a>Analysieren Des ersten Vorfalls

Das Verständnis des Kontexts von Warnungen ist gleichermaßen wichtig. Häufig handelt es sich bei einer Warnung nicht um ein einzelnes unabhängiges Ereignis. Es gibt eine Kette von Prozessen, die erstellt wurden, Befehle und Aktionen, die möglicherweise nicht gleichzeitig aufgetreten sind. Daher muss ein Analyst die ersten und letzten Aktivitäten der verdächtigen Entität in Gerätezeitachsen suchen, um den Kontext der Warnungen zu verstehen.

Es gibt mehrere Möglichkeiten, Daten mithilfe von Microsoft 365 Defender zu lesen und zu analysieren, aber das Endziel für Analysten ist es, auf Vorfälle so schnell wie möglich zu reagieren. Während Microsoft 365 Defender die Mittlere Zeit bis zur Behebung [(MtTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) durch das branchenführende Feature für die automatische Korrektur erheblich reduzieren kann, gibt es immer Fälle, die eine manuelle Analyse erfordern. 

Hier ein Beispiel:

1. Nachdem die Triagepriorität ermittelt wurde, beginnt ein Analyst eine eingehende Analyse, indem er den Vorfallnamen aus wählt. Auf dieser Seite wird die **Vorfallzusammenfassung angezeigt,** in der Daten auf Registerkarten angezeigt werden, um die Analyse zu unterstützen. Auf der **Registerkarte Warnungen** wird der Benachrichtigungstyp angezeigt. Analysten können auf jede Warnung klicken, um einen Drilldown zur jeweiligen Erkennungsquelle zu erhalten. 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Beispiel für die Registerkarte Zusammenfassung eines Vorfalls"::: 
 
    Eine kurze Anleitung dazu, welche Domäne von jeder Erkennungsquelle behandelt wird, finden Sie im [Abschnitt Erkennen](#detection-by-microsoft-365-defender) dieses Artikels.

2.  Auf der **Registerkarte Warnungen** kann ein Analyst zur Erkennungsquelle pivotieren, um eine detailliertere Untersuchung und Analyse durchzuführen. Wenn Sie beispielsweise schadsoftwareerkennung mit Microsoft Cloud App Security als Erkennungsquelle auswählen, wird der Analytiker zu seiner entsprechenden Warnungsseite weitergeleitet.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Beispiel für die Auswahl einer Warnung zu einem Vorfall"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Beispiel für eine entsprechende Seite in Microsoft Cloud App Security"::: 
  
3.  Um unser Beispiel weiter zu untersuchen, scrollen Sie zum unteren Rand der Seite, um die **betroffenen Benutzer zu sehen.** Um die Aktivität und den Kontext der Schadsoftwareerkennung zu sehen, wählen Sie die Benutzerseite von "Annette Hill" aus. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Beispiel für eine Benutzerseite":::
  
4.  Auf der Benutzerseite befindet sich eine chronologische Liste von Ereignissen, die mit einer riskanten Anmeldung aus einer Benachrichtigung über die *IP-Adresse des ToR-Netzwerks beginnen.* Während die Verdächtigkeit einer Aktivität von der Art der Geschäftstätigkeit einer Organisation abhängt, kann in den meisten Fällen die Verwendung von The Onion Router (TOR), einem Netzwerk, das Benutzern das anonyme Durchsuchen des Webs ermöglicht, in einer Unternehmensumgebung als äußerst unwahrscheinlich und für reguläre Onlinevorgänge unnötig angesehen werden.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Beispiel für die chronologische Liste der Ereignisse für einen Benutzer":::
  
5.  Jede Warnung kann ausgewählt werden, um weitere Informationen zur Aktivität zu erhalten. Wenn Sie beispielsweise Aktivität **aus einer Tor-IP-Adressbenachrichtigung** auswählen, gelangen Sie zur eigenen Seite dieser Warnung. Sie ist administrator of Office 365, was bedeutet, dass sie über erhöhte Rechte verfügt und der Quellvorfall möglicherweise zum Zugriff auf vertrauliche Informationen geführt hat. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Beispiel für Benachrichtigungsdetails für Microsoft Cloud App Security"::: 
 
6.  Durch Auswählen anderer Warnungen kann ein Analyst ein vollständiges Bild des Angriffs erhalten.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 2: Informationen zur Behebung von Vorfällen](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Hier erfahren [Sie, wie Sie Vorfälle be behebungen.](first-incident-remediate.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Analysieren von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
