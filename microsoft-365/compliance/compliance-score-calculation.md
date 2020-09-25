---
title: Berechnung der Konformitätsbewertung
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Microsoft Compliance Manager eine personalisierte Bewertung basierend auf Aktionen berechnet, die zur Behebung von Risiken und zur Verbesserung der Compliance-Haltung ergriffen werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f1707e0117d0a61f572716f21d13a02821955401
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262268"
---
# <a name="compliance-score-calculation"></a>Berechnung der Konformitätsbewertung

**In diesem Artikel:** Erfahren Sie, wie Compliance-Manager eine Konformitätsbewertung für Ihre Organisation berechnet. In diesem Artikel wird erläutert, wie **Sie Ihre Partitur interpretieren**, was die **grundlegende datenschutzbewertung** umfasst, die **kontinuierliche Überwachung**und **wie verschiedene Arten von Aktionen verwaltet und bewertet werden**.

> [!IMPORTANT]
> Empfehlungen des Compliance-Managers sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kunden Kontrollen pro ihrer regulatorischen Umgebung zu bewerten und zu validieren. Diese Dienste unterliegen den allgemeinen Geschäftsbedingungen in den [Online Dienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910). Siehe auch [Microsoft 365 Lizenzierung Leitfaden für Sicherheit und Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>Vorgehensweise zum Lesen der Konformitätsbewertung

Im Compliance-Manager-Dashboard wird Ihr allgemeines Kompatibilitäts Ergebnis angezeigt. Diese Bewertung misst Ihren Fortschritt beim Abschließen empfohlener Verbesserungs Aktionen innerhalb von Steuerelementen. Ihre Punktzahl kann Ihnen helfen, Ihre aktuelle Compliance-Haltung zu verstehen. Es kann auch helfen, Prioritäten für Aktionen basierend auf Ihrem Potenzial zur Verringerung des Risikos zu setzen.

Ein Bewertungs Wert wird auf drei Ebenen zugewiesen:

1. **Ergebnis der Verbesserungs Aktion**: jede Aktion unterscheidet sich je nach möglicher Gefahr durch eine andere Auswirkung auf Ihre Punktzahl.

2. **Kontroll**Punkte: diese Bewertung ist die Summe der Punkte, die durch das Abschließen von Verbesserungs Aktionen innerhalb des Steuerelements erzielt wurden. Diese Summe wird in ihrer Gesamtheit auf ihr allgemeines Konformitäts Ergebnis angewendet, wenn das Steuerelement die beiden folgenden Bedingungen erfüllt:
    - **Implementierungs Status** entspricht **implementiert** oder **alternative Implementierung**und
    - **Test Ergebnis** gleich **übergeben**.

3. **Bewertungsergebnis**: diese Bewertung ist die Summe ihrer Kontrollpunkte. Sie wird mithilfe von Aktionspunkten berechnet. Jede Microsoft-Aktion und jede Verbesserungs Aktion, die von Ihrer Organisation verwaltet wird, werden einmal gezählt, unabhängig davon, wie oft in einem Steuerelement auf Sie verwiesen wird.

Das Gesamtergebnis der Konformität wird mithilfe von Aktionspunkten berechnet, wobei jede Microsoft-Aktion einmal gezählt wird, jede technische Aktion, die Sie verwalten, einmal gezählt wird und jede nicht technische Aktion, die Sie verwalten, einmal pro Gruppe gezählt wird. Diese Logik wurde entwickelt, um die genaue Bilanzierung der Implementierung und Erprobung von Aktionen in Ihrer Organisation zu ermöglichen. Dies kann dazu führen, dass sich das Gesamtergebnis der Konformität vom Durchschnitt der Bewertungsergebnisse unterscheidet. Lesen Sie weiter unten, [wie Aktionen bewertet werden](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Ursprüngliche Bewertung basierend auf der Microsoft 365-Datenschutz Basis
  
Compliance-Manager gibt Ihnen eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis. Dieser Basisplan umfasst eine Reihe von Steuerelementen, die wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung beinhalten. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

Ihr anfängliches Ergebnis wird gemäß der standardmäßigen Datenschutz-Basisbewertung für alle Organisationen berechnet. Bei Ihrem ersten Besuch sammelt Compliance-Manager bereits Signale von Ihren Microsoft 365-Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Verhältnis zu wichtigen Datenschutzstandards und-Vorschriften arbeitet, und wie Sie die vorgeschlagenen Verbesserungsmaßnahmen durchführen.

Da jede Organisation spezifische Anforderungen hat, setzt Compliance-Manager darauf, dass Sie Assessments einrichten und verwalten, um das Risiko möglichst umfassend zu minimieren und zu mindern.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>So beurteilt Compliance-Manager Steuerelemente kontinuierlich

Compliance-Manager scannt automatisch Ihre Microsoft 365-Umgebung und erkennt Ihre Systemeinstellungen, und aktualisiert Ihren technischen Aktionsstatus kontinuierlich und automatisch. Microsoft Secure Score ist das zugrunde liegende Modul, das die Überwachung ausführt.

Ihr Aktionsstatus wird alle 24 Stunden auf dem Dashboard aktualisiert. Nachdem Sie eine Empfehlung zur Implementierung eines Steuerelements befolgt haben, wird der Status des Steuerelements in der Regel am nächsten Tag aktualisiert angezeigt.

Wenn Sie beispielsweise die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) im Azure AD-Portal aktivieren, erkennt Compliance-Manager die Einstellung und gibt Sie in den Details zur Steuerung der Zugriffslösung wieder. Wenn Sie sich umgekehrt nicht für MFA aktiviert haben, kennzeichnet Compliance-Manager dies als empfohlene Aktion, die Sie ergreifen sollten.

Erfahren Sie mehr über [Secure Score und wie es funktioniert](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Aktionstypen und-Punkte

Compliance-Manager verfolgt zwei Arten von Aktionen:

1. **Ihre Verbesserungs Aktionen**: Aktionen, die von Ihrer Organisation verwaltet werden.
2. **Microsoft-Aktionen**: von Microsoft verwaltete Aktionen.

Beide Arten von Aktionen weisen nach Abschluss Punkte auf, die für die Gesamtpunktzahl gelten.

### <a name="technical-and-non-technical-actions"></a>Technische und nicht technische Aktionen

Die Aktionen werden nach dem technischen oder nicht technischen Charakter gruppiert. Der Bewertungs Effekt jeder Aktion unterscheidet sich je nach Typ.

- **Technische Aktionen** werden durch Interaktion mit der Technologie einer Lösung implementiert (beispielsweisedurch Ändern einer Konfiguration). Die Punkte für Technische Aktionen werden einmal pro Aktion erteilt, unabhängig davon, zu wie viele Gruppen Sie gehört.

- **Nicht technische Aktionen** werden von Ihrer Organisation verwaltet und auf andere Weise als das Arbeiten mit der Technologie einer Lösung implementiert. Es gibt zwei Arten von nicht technischen Aktionen: **Dokumentation** und **Betrieb**. Die Punkte für diese Aktionen werden auf Ihrer Konformitätsbewertung auf Gruppenebene angewendet. Dies bedeutet, dass Sie bei einer Aktion, die in mehreren Gruppen vorhanden ist, bei jeder Implementierung innerhalb einer Gruppe den Punkte Wert der Aktion erhalten.

**Beispiel für die Bewertung technischer und nicht technischer Aktionen:**

Angenommen, Sie haben eine technische Aktion im Wert von 3 Punkten, die in 5 Gruppen vorhanden ist, und Sie haben eine nicht technische Aktion im Wert von 3 Punkten, die in den gleichen 5 Gruppen vorhanden ist.

Wenn Sie die technische Aktion erfolgreich implementiert haben, beträgt die Gesamtzahl der Punkte, die Sie erhalten, 3. Dies liegt daran, dass Sie die Aktion nur einmal für Ihren Mandanten implementieren müssen. Die Implementierung und der Teststatus für die technische Aktion werden in allen Instanzen dieser Aktion in jeder Gruppe angezeigt, der Sie angehört.

Wenn Sie die nicht technische Aktion in jeder der 5 Gruppen erfolgreich implementieren, beträgt die Gesamtzahl der Punkte, die Sie erhalten, 15. Dies liegt daran, dass Sie die Aktion in jeder Gruppe implementieren müssen. Der Implementierungs-und Teststatus für die nicht-technische Aktion unterscheidet sich in Gruppen, da die Aktion in jeder ihrer Gruppen separat implementiert wird.

Diese Bewertungslogik wurde entwickelt, um die genaue Bilanzierung der Implementierung und Erprobung von Aktionen in Ihrer Organisation zu ermöglichen.

### <a name="how-score-values-are-determined"></a>Bestimmen der Bewertungswerte
 
Aktionen werden basierend darauf, ob Sie obligatorisch oder diskretionäre sind, einen Bewertungs Wert zugewiesen und ob Sie vorbeugend, detektivisch oder Korrektiv sind.

### <a name="mandatory-and-discretionary-actions"></a>Obligatorische und diskretionäre Aktionen

 - **Obligatorische Aktionen** können weder absichtlich noch versehentlich umgangen werden. Ein Beispiel für eine obligatorische Aktion ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für die Länge, Komplexität und den Ablauf von Kennwörtern festlegt. Benutzer müssen diese Anforderungen für den Zugriff auf das System befolgen.
  
 - **Diskretionäre Aktionen** basieren darauf, dass Benutzer eine Richtlinie verstehen und einhalten. Beispielsweise ist eine Richtlinie, bei der Benutzer Ihren Computer beim Verlassen des Computers Sperren müssen, eine Ermessens Maßnahme, da Sie vom Benutzer abhängig ist.
  
### <a name="preventative-detective-and-corrective-actions"></a>Vorbeugende, detektivische und korrigierende Aktionen
  
 - **Vorbeugende Aktionen** adressieren bestimmte Risiken. Beispielsweise ist das Schützen von Informationen im Ruhezustand mithilfe der Verschlüsselung vorbeugende Maßnahmen gegen Angriffe und Verstöße. Die Trennung von Zöllen ist eine vorbeugende Maßnahme zur Verwaltung von Interessenkonflikten und zum Schutz vor Betrug.
  
 - **Detektiv Aktionen** überwachen Systeme aktiv, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die ein Risiko darstellen oder die zum Erkennen von Eindringlingen oder Verstößen verwendet werden können. Beispiele hierfür sind die Systemzugriffs Überwachung und privilegierte Verwaltungsaktionen. Compliance-Überwachungen sind eine Art Detektiv Aktion, die verwendet wird, um Prozessprobleme zu finden.
  
- **Korrekturmaßnahmen** versuchen Sie, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zu ergreifen, um den unmittelbaren Effekt zu reduzieren, und den Schaden nach Möglichkeit umzukehren. Die Antwort auf Datenschutz Vorfälle ist eine Korrekturmaßnahme zum Begrenzen von Beschädigungen und zur Wiederherstellung von Systemen in einem Betriebszustand nach einer Verletzung.
  
Jede Aktion hat einen zugewiesenen Wert im Compliance-Manager basierend auf dem Risiko, das Sie darstellt:

|**Typ**|**Zugewiesene Punktzahl**|
|:-----|:-----|
| Vorbeugende Pflicht | 27 |
| Vorbeugender Ermessensspielraum | 9  |
| Detektiv erforderlich | 3 |
| Detektiv-diskretionäres | 1 |
| Korrektur Pflicht | 3 |
| Korrigierendes diskretionäre | 1 |
  
![Action Points-Werte für Compliance-Manager](../media/compliance-score-action-scoring.png "Action Points-Werte für Compliance-Manager")