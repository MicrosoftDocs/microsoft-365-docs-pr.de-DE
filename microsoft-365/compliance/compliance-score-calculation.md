---
title: Berechnung der Compliancebewertung
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Verstehen Sie, wie Microsoft Compliance Manager eine personalisierte Bewertung basierend auf Maßnahmen berechnet, die ergriffen werden, um Risiken zu beheben und Ihren Compliancestatus zu verbessern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e1e3f4b90b0a5e83a1e068cd30f76b3a8c7bb22
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149166"
---
# <a name="compliance-score-calculation"></a>Berechnung der Compliancebewertung

**In diesem Artikel:** Erfahren Sie, wie Compliance-Manager eine Compliancebewertung für Ihre Organisation berechnet. In diesem Artikel wird erläutert, wie **Sie Ihre Bewertung interpretieren,** was die Bewertung der **Datenschutzgrundwerte** umfasst, **fortlaufende Überwachung** und wie verschiedene Arten von Aktionen verwaltet und bewertet **werden.**

> [!IMPORTANT]
> Empfehlungen des Compliance-Managers sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kundenkontrollen gemäß Ihrer regulatorischen Umgebung zu bewerten und zu überprüfen. Diese Dienste unterliegen den Geschäftsbedingungen in den Nutzungsbedingungen für [Onlinedienste.](https://go.microsoft.com/fwlink/?linkid=2108910) Siehe auch [Microsoft 365 Lizenzierungsleitfaden für Sicherheit und Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="how-to-read-your-compliance-score"></a>So lesen Sie Ihre Compliancebewertung

Das Compliance-Manager-Dashboard zeigt Ihre gesamte Compliancebewertung an. Diese Bewertung misst Ihren Fortschritt bei der Durchführung empfohlener Verbesserungsmaßnahmen innerhalb der Kontrollen. Ihre Bewertung kann Ihnen dabei helfen, Ihren aktuellen Compliancestatus zu verstehen. Es kann Ihnen auch dabei helfen, Aktionen basierend auf ihrem Risikorisiko zu priorisieren.

Ein Bewertungswert wird auf drei Ebenen zugewiesen:

1. Bewertung der **Verbesserungsmaßnahmen:** Jede Aktion hat je nach potenziellem Risiko unterschiedliche Auswirkungen auf Ihre Bewertung.

2. **Kontrollpunktzahl:** Diese Bewertung ist die Summe der Punkte, die durch Abschluss von Verbesserungsmaßnahmen innerhalb des Steuerelements erzielt werden. Diese Summe wird vollständig auf Ihre Gesamtkompatibilitätsbewertung angewendet, wenn das Steuerelement beide der folgenden Bedingungen erfüllt:
    - **Implementierungsstatus** entspricht **implementierter** oder **alternativer Implementierung** und
    - **Testergebnis** ist gleich **übergeben.**

3. **Bewertungsergebnis:** Diese Bewertung ist die Summe Ihrer Kontrollergebnisse. Sie wird mithilfe von Aktionsbewertungen berechnet. Jede Microsoft-Aktion und jede von Ihrer Organisation verwaltete Verbesserungsmaßnahme wird einmal gezählt, unabhängig davon, wie oft in einem Steuerelement darauf verwiesen wird.

Die Gesamtcompliancebewertung wird mithilfe von Aktionsergebnissen berechnet, wobei jede Microsoft-Aktion einmal gezählt wird, jede von Ihnen verwaltete technische Aktion einmal gezählt wird und jede nicht technische Aktion, die Sie verwalten, einmal pro Gruppe gezählt wird. Diese Logik ist so konzipiert, dass sie die genaueste Buchführung darüber bereitstellt, wie Aktionen in Ihrer Organisation implementiert und getestet werden. Möglicherweise stellen Sie fest, dass dies dazu führen kann, dass ihre Compliancebewertung insgesamt vom Durchschnitt Ihrer Bewertungsergebnisse abweicht. Weitere Informationen zur [Bewertung von Aktionen finden](#action-types-and-points)Sie weiter unten.

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Ausgangsbewertung basierend auf Microsoft 365 Datenschutzgrundwerte
  
Compliance-Manager bietet Ihnen eine erste Bewertung basierend auf der Microsoft 365 Datenschutzgrundlinie. Diese Baseline ist eine Reihe von Steuerelementen, die wichtige Vorschriften und Standards für Datenschutz und allgemeine Datengovernance enthalten. Diese Baseline basiert hauptsächlich auf NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) und ISO (International Organization for Standardization) sowie aus FedRAMP (Federal Risk and Authorization Management Program) und der DSGVO (General Data Protection Regulation of the European Union).

Ihre anfängliche Bewertung wird gemäß der standardmäßigen Bewertung der Datenschutzgrundwerte berechnet, die für alle Organisationen bereitgestellt wird. Bei Ihrem ersten Besuch sammelt Compliance-Manager bereits Signale von Ihren Microsoft 365 Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Verhältnis zu wichtigen Datenschutzstandards und -vorschriften funktioniert, und sehen, welche Verbesserungsmaßnahmen sie ergreifen müssen.

Da jede Organisation bestimmte Anforderungen hat, ist Compliance-Manager darauf angewiesen, dass Sie Bewertungen einrichten und verwalten, um Risiken so umfassend wie möglich zu minimieren und zu mindern.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Wie Compliance-Manager Steuerelemente kontinuierlich bewertet

Compliance-Manager durchsucht automatisch Ihre Microsoft 365-Umgebung und erkennt Ihre Systemeinstellungen, aktualisiert kontinuierlich und automatisch den Status ihrer technischen Maßnahmen. Die Microsoft-Sicherheitsbewertung ist das zugrunde liegende Modul, das die Überwachung durchführt.

Ihr Aktionsstatus wird alle 24 Stunden auf Ihrem Dashboard aktualisiert. Nachdem Sie eine Empfehlung zum Implementieren eines Steuerelements befolgt haben, wird in der Regel der Status des Steuerelements am nächsten Tag aktualisiert.

Wenn Sie beispielsweise die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) im Azure AD-Portal aktivieren, erkennt Compliance-Manager die Einstellung und spiegelt sie in den Details der Zugriffslösung wider. Wenn Sie die MFA dagegen nicht aktiviert haben, kennzeichnet compliance-Manager dies als empfohlene Aktion, die Sie ausführen sollten.

Erfahren Sie mehr über [die Sicherheitsbewertung und ihre Funktionsweise.](../security/defender/microsoft-secure-score.md)
  
## <a name="action-types-and-points"></a>Aktionstypen und -punkte

Compliance-Manager verfolgt zwei Arten von Aktionen nach:

1. **Ihre Verbesserungsmaßnahmen:** Aktionen, die Ihre Organisation verwaltet.
2. **Microsoft-Aktionen:** Von Microsoft verwalteten Aktionen.

Beide Arten von Aktionen weisen Punkte auf, die nach Abschluss ihres Abschlusses auf Ihre Gesamtbewertung angerechnet werden.

### <a name="technical-and-non-technical-actions"></a>Technische und nicht technische Aktionen

Aktionen werden nach technischer oder nicht technischer Art gruppiert. Die Bewertungsauswirkungen der einzelnen Aktionen unterscheiden sich je nach Typ.

- **Technische Aktionen** werden durch Interaktion mit der Technologie einer Lösung (z. B. Ändern einer Konfiguration) implementiert. Die Punkte für technische Aktionen werden einmal pro Aktion gewährt, unabhängig davon, zu wie vielen Gruppen sie gehört.

- **Nicht technische Aktionen** werden von Ihrer Organisation verwaltet und auf andere Weise als mit der Technologie einer Lösung implementiert. Es gibt zwei Arten von nicht technischen Aktionen: **Dokumentation** und **Betrieb.** Die Punkte für diese Aktionen werden auf Ihre Compliancebewertung auf Gruppenebene angewendet. Dies bedeutet, dass, wenn eine Aktion in mehreren Gruppen vorhanden ist, sie bei jeder Implementierung innerhalb einer Gruppe den Punktwert der Aktion erhält.

**Beispiel für die Bewertung technischer und nicht technischer Aktionen:**

Angenommen, Sie haben eine technische Aktion im Wert von 3 Punkten, die in 5 Gruppen vorhanden ist, und sie haben eine nicht technische Aktion im Wert von 3 Punkten, die in den gleichen 5 Gruppen vorhanden ist.

Wenn Sie die technische Aktion erfolgreich implementieren, beträgt die Gesamtanzahl der punkte, die Sie erhalten, 3. Dies liegt daran, dass Sie die Aktion nur einmal für Ihren Mandanten implementieren müssen. Der Implementierungs- und Teststatus für die technische Aktion wird in allen Instanzen dieser Aktion in jeder Gruppe, zu der sie gehört, gleich angezeigt.

Wenn Sie die nicht technische Aktion in jeder der fünf Gruppen erfolgreich implementieren, beträgt die Gesamtanzahl der erhaltenen Punkte 15. Dies liegt daran, dass Sie die Aktion in jeder Gruppe implementieren müssen. Der Implementierungs- und Teststatus für die nicht technische Aktion unterscheidet sich von Gruppe zu Gruppe, da die Aktion in jeder ihrer Gruppen separat implementiert wird.

Diese Bewertungslogik ist so konzipiert, dass sie die genaueste Buchführung darüber bereitstellt, wie Aktionen in Ihrer Organisation implementiert und getestet werden.

### <a name="how-score-values-are-determined"></a>Bestimmen von Bewertungswerten
 
Aktionen wird ein Bewertungswert zugewiesen, der darauf basiert, ob sie obligatorisch oder diskretionär sind und ob sie präventiv, erkennend oder korrigierend sind.

### <a name="mandatory-and-discretionary-actions"></a>Obligatorische und freie Aktionen

 - **Obligatorische Aktionen** können weder absichtlich noch versehentlich umgangen werden. Ein Beispiel für eine obligatorische Aktion ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für Die Länge, Komplexität und Ablauf von Kennwörtern festlegt. Die Benutzer müssen diese Anforderungen erfüllen, um auf das System zugreifen zu können.
  
 - **Diskretionäre Aktionen** sind darauf angewiesen, dass Benutzer eine Richtlinie verstehen und einhalten. Beispielsweise ist eine Richtlinie, die erfordert, dass Benutzer ihren Computer sperren, wenn sie sie verlassen, eine freie Aktion, da sie auf den Benutzer angewiesen ist.
  
### <a name="preventative-detective-and-corrective-actions"></a>Präventive, erkennungs- und korrekturmaßnahmen
  
 - **Mit vorbeugenden Maßnahmen werden** bestimmte Risiken behoben. Der Schutz von ruhenden Informationen mithilfe von Verschlüsselung ist beispielsweise eine vorbeugende Maßnahme gegen Angriffe und Verstöße. Die Aufgabentrennung ist eine vorbeugende Maßnahme, um Interessengruppen zu verwalten und vor Betrug zu schützen.
  
 - **Erkennungsmaßnahmen** überwachen Systeme aktiv, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die Risiken darstellen oder verwendet werden können, um Angriffe oder Verstöße zu erkennen. Beispiele hierfür sind die Systemzugriffsüberwachung und privilegierte Verwaltungsaktionen. Überwachungen der Einhaltung gesetzlicher Vorschriften sind eine Art von Erkennungsmaßnahme, die verwendet wird, um Prozessprobleme zu finden.
  
- **Korrekturmaßnahmen** versuchen, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zu ergreifen, um die sofortige Wirkung zu verringern, und den Schaden nach Möglichkeit rückgängig zu machen. Die Reaktion auf Datenschutzverletzungen ist eine Korrekturmaßnahme, um Schäden zu begrenzen und Systeme nach einer Verletzung wieder in einen Betriebszustand zu versetzen.
  
Jede Aktion hat einen zugewiesenen Wert im Compliance-Manager basierend auf dem Risiko, das sie darstellt:

|**Typ**|**Zugewiesene Bewertung**|
|:-----|:-----|
| Preventative mandatory | 27 |
| Verhinderung von Freiem Ermessen | 9  |
| Detective mandatory | 3  |
| Detective discretionary | 1  |
| Korrektur erforderlich | 3  |
| Korrektur nach freiem Ermessen | 1  |
  
![Compliance-Manager-Aktionspunktwerte](../media/compliance-score-action-scoring.png "Compliance-Manager-Aktionspunktwerte")