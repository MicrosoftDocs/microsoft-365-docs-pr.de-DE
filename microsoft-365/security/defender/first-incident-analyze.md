---
title: Schritt 1. Triage and analyze your first incident
description: Hier erfahren Sie, wie Sie Ihren ersten Vorfall in Microsoft 365 Defender auswerten und mit der Analyse beginnen.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
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
ms.openlocfilehash: 82e1d1b117fd8c68077a249a14f66b9915d517e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287771"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Schritt 1. Triage and analyze your first incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Während Sie einige Zeit damit verbringen, Sicherheitsmaßnahmen gemäß den Standards der Organisation einzurichten, zu implementieren und aufrechtzuerhalten, können Sie Sicherheitslösungen einrichten, die Ihnen helfen, Sicherheitsrisiken und Bedrohungen schnell zu erkennen. Microsoft 365 Defender ermöglicht es Ihnen, Vorfälle mithilfe der Single-Pane-of-Glass-Erfahrung zu erkennen, zu selektieren und zu untersuchen, wo Sie die Informationen finden können, die Sie benötigen, um rechtzeitig Entscheidungen zu treffen.

Sobald ein Sicherheitsvorfall erkannt wurde, zeigt Microsoft 365 Defender Details an, die Sie benötigen, um einen Vorfall oder Vorfälle gegenüber anderen zu selektieren oder zu priorisieren. Nach der Festlegung der Priorisierung können Analysten ihre Energie auf die Untersuchung der ihnen zugewiesenen Fälle konzentrieren.

## <a name="detection-by-microsoft-365-defender"></a>Erkennung durch Microsoft 365 Defender

Microsoft 365 Defender empfängt Warnungen und Ereignisse von mehreren Microsoft-Sicherheitsplattformen als Erkennungsquellen, um ein ganzheitliches Bild und einen Kontext bösartiger Aktivitäten zu erstellen. Dies sind die möglichen Erkennungsquellen:

- [Microsoft Defender für Endpunkt](../defender-endpoint/microsoft-defender-endpoint.md) ist eine EDR-Lösung (EDR), die Microsoft Defender Antivirus sowie cloudfähigen erweiterten Bedrohungsschutz mit Microsoft Security Graph verwendet. Defender für Endpunkt ist eine einheitliche Plattform für präventiven Schutz, Erkennung nach einem Angriff, automatisierte Untersuchung und Reaktion. Es schützt Endpunkte vor Cyberbedrohungen, erkennt fortgeschrittene Angriffe und Datenschutzverletzungen, automatisiert Sicherheitsvorfälle und verbessert den Sicherheitsstatus.
- [Microsoft Defender for Identity](/defender-for-identity/what-is) ist eine cloudbasierte Sicherheitslösung, die Ihre lokalen Active Directory Domain Services (AD DS)-Signale verwendet, um erweiterte Bedrohungen, kompromittierte Identitäten und bösartige Insideraktionen, die gegen Ihre Organisation gerichtet sind, zu identifizieren, zu erkennen und zu untersuchen.
- [Microsoft Cloud App Security](/cloud-app-security/) fungiert als Torwart, um den Zugriff in Echtzeit zwischen Ihren Unternehmensbenutzern und den von ihnen verwendeten Cloudressourcen zu vermitteln, unabhängig davon, wo sich Ihre Benutzer befinden und unabhängig vom verwendeten Gerät.
- [Microsoft Defender für Office 365](../office-365-security/overview.md) schützt Ihre Organisation vor bösartigen Bedrohungen in E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit.
- [Azure Security Center](/azure/security-center/security-center-introduction) ist ein einheitliches Infrastruktur-Sicherheitsverwaltungssystem, das den Sicherheitsstatus Ihrer Rechenzentren verstärkt und erweiterten Bedrohungsschutz für Ihre Hybridarbeitslasten sowohl in der Cloud als auch lokal bietet.

In Microsoft 365 Defender werden [Vorfälle](incidents-overview.md) identifiziert, indem Warnungen aus diesen verschiedenen Erkennungsquellen korreliert werden. Anstatt Ressourcen zusammenzubestellen oder mehrere Warnungen in den jeweiligen Vorfällen zu unterscheiden, können Sie sofort mit der Vorfallwarteschlange in Microsoft 365 Defender beginnen. Auf diese Weise können Sie Vorfälle auf effiziente Weise über Endpunkte, Identitäten, E-Mails und Anwendungen hinweg selektieren und den Schaden durch einen Angriff reduzieren.

## <a name="triage-your-incidents"></a>Triage Ihrer Vorfälle

Die Reaktion auf Vorfälle in Microsoft 365 Defender beginnt, sobald Sie die Liste der Vorfälle mithilfe der empfohlenen Priorisierungsmethode Ihrer Organisation selektieren. Die Triage bedeutet, Vorfällen eine Wichtigkeitsstufe oder Dringlichkeit zuzuweisen, die dann die Reihenfolge bestimmt, in der sie untersucht werden.

Ein hilfreicher Beispielleitfaden für die Bestimmung, welcher Vorfall in Microsoft 365 Defender priorisiert werden soll, kann anhand der Formel zusammengefasst werden: *Schweregrad + Auswirkung = Priorität.*

- **Der Schweregrad** ist die ebene, die von Microsoft 365 Defender und den integrierten Sicherheitskomponenten festgelegt wird.
- **Die Auswirkungen** werden von der Organisation bestimmt und umfassen in der Regel, aber nicht beschränkt auf, eine Schwellenwertanzahl betroffener Benutzer, Geräte, Dienste (oder eine Kombination davon) und sogar den Warnungstyp.

Analysten initiieren dann Untersuchungen basierend auf den von der Organisation festgelegten **Prioritätskriterien.**

Die Priorisierung von Vorfällen kann je nach Organisation variieren. NIST empfiehlt auch die Berücksichtigung der funktionalen und informativen Auswirkungen des Vorfalls und der Wiederherstellbarkeit.

Es folgt nur ein Ansatz für die Triage:

1. Wechseln Sie zur Seite ["Vorfälle",](incidents-overview.md) um die Triage zu initiieren. Hier sehen Sie eine Liste der Vorfälle, die Sich auf Ihre Organisation auswirken. Standardmäßig sind sie vom neuesten bis zum ältesten Vorfall angeordnet. Von hier aus können Sie unter anderem auch unterschiedliche Spalten für jeden Vorfall mit Schweregrad, Kategorie, Anzahl der aktiven Warnungen und betroffenen Entitäten anzeigen. Sie können den Satz von Spalten anpassen und die Vorfallwarteschlange nach einigen dieser Spalten sortieren, indem Sie den Spaltennamen auswählen. Sie können die Vorfallwarteschlange auch nach Ihren Anforderungen filtern. Eine vollständige Liste der verfügbaren Filter finden Sie unter Priorisieren von [Vorfällen.](incident-queue.md#available-filters)

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Beispiel für die Vorfallwarteschlange":::

    Ein Beispiel dafür, wie Sie eine Triage für diese Gruppe von Vorfällen durchführen können, ist die Priorisierung von Vorfällen, von denen mehr Benutzer und Geräte betroffen waren. In diesem Beispiel können Sie die Vorfall-ID 6769 priorisieren, da sie die größte Anzahl von Entitäten betrifft: 7 Geräte, 6 Benutzer und 2 Postfächer. Darüber hinaus enthält der Vorfall scheinbar Warnungen von Microsoft Defender for Identity, die auf eine identitätsbasierte Warnung und einen möglichen Diebstahl von Anmeldeinformationen hinweisen.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Beispiel für einen Vorfall mit hoher Auswirkung":::

2. Wählen Sie den Kreis neben dem Vorfallnamen aus, um die Details zu überprüfen. Auf der rechten Seite wird ein Seitenbereich angezeigt, der zusätzliche Informationen enthält, die Ihnen bei der weiteren Triage helfen können.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Beispiel für einen Seitenbereich eines Vorfalls":::

   Wenn Sie sich beispielsweise ansehen, welche [MITRE ATT&CK-Taktiken](https://attack.mitre.org/) verwendet hat, die der Angreifer basierend auf den Kategorien des Vorfalls verwendet hat, können Sie diesen Vorfall priorisieren, da der Angreifer gestohlene Anmeldeinformationen verwendet, Befehle und Kontrolle eingerichtet, laterale Bewegungen ausgeführt und einige Daten exfiltriert hat. Dies deutet darauf hin, dass der Angreifer bereits tief in das Netzwerk gelangt ist und möglicherweise vertrauliche Informationen gestohlen hat.

   Wenn Ihre Organisation das Zero Trust-Framework implementiert hat, würden Sie außerdem den Zugriff auf Anmeldeinformationen als wichtigen Sicherheitsverstoß betrachten, der priorisiert werden sollte.

   Wenn Sie den Seitenbereich nach unten scrollen, werden die spezifischen betroffenen Entitäten wie Benutzer, Geräte und Postfächer angezeigt. Sie können die Belichtungsstufe jedes Geräts und die Besitzer der betroffenen Postfächer überprüfen.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Beispiel für Details zum Seitenbereich eines Vorfalls":::

3. Weiter unten im Seitenbereich finden Sie die zugehörigen Warnungen. Microsoft 365 Defender hat die Korrelation dieser Warnungen bereits in einem einzigen Vorfall durchgeführt, sodass Sie Zeit und Ressourcen sparen, die sie besser für die Behebung des Angriffs aufgewendet haben. Warnungen sind verdächtige und daher möglicherweise schädliche Systemereignisse, die das Vorhandensein eines Angreifers in einem Netzwerk vorschlagen.

   In diesem Beispiel wurden 87 einzelne Warnungen als Teil eines Sicherheitsvorfalls ermittelt. Sie können alle Warnungen anzeigen, um einen schnellen Überblick darüber zu erhalten, wie der Angriff ausgespielt wurde.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Beispiel für Warnungen in einem Seitenbereich für Vorfälle":::

## <a name="analyze-your-first-incident"></a>Analysieren Ihres ersten Vorfalls

Das Verständnis des Kontexts für Warnungen ist gleichermaßen wichtig. Häufig ist eine Warnung kein einzelnes unabhängiges Ereignis. Es gibt eine Kette von Prozessen, Befehlen und Aktionen, die möglicherweise nicht gleichzeitig aufgetreten sind. Daher muss ein Analyst nach der ersten und letzten Aktivität der verdächtigen Entität in Gerätezeitachsen suchen, um den Kontext der Warnungen zu verstehen.

Es gibt mehrere Möglichkeiten, Daten mithilfe von Microsoft 365 Defender zu lesen und zu analysieren, aber das Endziel für Analysten besteht darin, so schnell wie möglich auf Vorfälle zu reagieren. Während Microsoft 365 Defender die mittlere [Korrekturzeit (Mean Time to Remediate, MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) durch das branchenführende Feature für [automatisierte Untersuchung und Reaktion](m365d-autoir.md) erheblich reduzieren kann, gibt es immer Fälle, die eine manuelle Analyse erfordern.

Hier ist ein Beispiel:

1. Nachdem die Triagepriorität ermittelt wurde, beginnt ein Analyst mit einer eingehenden Analyse, indem er den Namen des Vorfalls auswählt. Auf dieser Seite wird die **Vorfallzusammenfassung** angezeigt, in der Daten auf Registerkarten angezeigt werden, um die Analyse zu unterstützen. Auf der Registerkarte **"Warnungen"** werden die Warnungstypen angezeigt. Analysten können auf jede Warnung klicken, um einen Drilldown zur jeweiligen Erkennungsquelle anzuzeigen.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Beispiel für die Registerkarte &quot;Zusammenfassung&quot; eines Vorfalls":::

    Eine kurze Anleitung dazu, welche Domäne von den einzelnen Erkennungsquellen abgedeckt wird, finden Sie im Abschnitt ["Erkennen"](#detection-by-microsoft-365-defender) in diesem Artikel.

2. Auf der Registerkarte **"Warnungen"** kann ein Analyst zur Erkennungsquelle pivotieren, um eine ausführlichere Untersuchung und Analyse durchzuführen. Wenn Sie beispielsweise die Schadsoftwareerkennung mit Microsoft Cloud App Security als Erkennungsquelle auswählen, wird der Analyst zur entsprechenden Warnungsseite gelangen.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Beispiel für die Auswahl einer Warnung eines Vorfalls":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Beispiel für eine entsprechende Seite in Microsoft Cloud App Security":::

3. Um unser Beispiel weiter zu untersuchen, scrollen Sie nach unten auf der Seite, um die **betroffenen Benutzer** anzuzeigen. Um die Aktivitäten und den Kontext im Zusammenhang mit der Schadsoftwareerkennung anzuzeigen, wählen Sie die Benutzerseite von "Puffer Hill" aus.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Beispiel für eine Benutzerseite":::

4. Auf der Benutzerseite befindet sich eine chronologische Liste der Ereignisse, die mit einer *riskanten Anmeldung aus einer IP-Adresswarnung für das TOR-Netzwerk* beginnen. Während der Verdächtige einer Aktivität von der Art der Geschäftstätigkeit einer Organisation abhängt, kann in den meisten Fällen die Verwendung von Onion Router (TOR), einem Netzwerk, das Benutzern das anonyme Durchsuchen des Webs ermöglicht, in einer Unternehmensumgebung als äußerst unwahrscheinlich und für reguläre Onlinevorgänge unnötig betrachtet werden.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Beispiel für die chronologische Liste der Ereignisse für einen Benutzer":::

5. Jede Warnung kann ausgewählt werden, um weitere Informationen zu der Aktivität zu erhalten. Wenn Sie z. B. **"Aktivität" aus einer Tor-IP-Adresswarnung** auswählen, gelangen Sie zur eigenen Seite dieser Warnung. Er ist administrator of Office 365, was bedeutet, dass er über erhöhte Rechte verfügt und der Quellvorfall möglicherweise zum Zugriff auf vertrauliche Informationen geführt hat.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Beispiel für Warnungsdetails für Microsoft Cloud App Security":::

6. Durch Die Auswahl anderer Warnungen kann ein Analyst ein vollständiges Bild des Angriffs erhalten.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 2: Erfahren Sie, wie Sie Vorfälle beheben](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Erfahren Sie, wie [Sie Vorfälle beheben.](first-incident-remediate.md)

## <a name="see-also"></a>Weitere Informationen:

- [Übersicht über Vorfälle](incidents-overview.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
