---
title: Methodik der Konformitätsbewertung
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
description: Der Microsoft Compliance-Manager ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft-Dienst Vertrauensstellungs Portal. Mit dem Compliance-Manager können Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services nachverfolgen, zuweisen und überprüfen.
ms.openlocfilehash: eb6e79d840439acec007fef54bf6cb5ca5633f1e
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417494"
---
# <a name="compliance-score-methodology-preview"></a>Methodik der Konformitätsbewertung (Vorschau)

> [!NOTE]
> Die Compliance-Bewertung drückt kein absolutes Maß für die Einhaltung eines bestimmten Standards oder einer bestimmten Vorschrift in der Organisation aus. Sie drückt vielmehr den Umfang aus, in dem Sie Steuerelemente einsetzen, durch die die Risiken für persönliche Daten und den Datenschutz reduziert werden können. Kein Dienst kann garantieren, dass Sie einen Standard oder eine Vorschrift einhalten. Die Compliance-Bewertung sollte in keinster Weise als eine Garantie verstanden werden.

Im Compliance-Manager-Dashboard wird ein Gesamt Kompatibilitäts Faktor für Bewertungen in den einzelnen Bewertungs Kacheln angezeigt. Dies ist das Gesamtergebnis der Konformität für die Bewertung und ist die Akkumulation von Punkten, die für jedes implementierte und getestete Steuerelement in der Bewertung erhalten wurden. Für eine neue Bewertung weist das Kompatibilitäts Ergebnis einen anfänglichen Wert für die enthaltenen von unabhängigen Drittanbietern getesteten von Microsoft verwalteten Steuerelemente auf. Das Kompatibilitäts Ergebnis wird basierend auf von Microsoft verwalteten Aktions Ergebnissen und von Kunden verwalteten Aktionspunkten berechnet. Compliance Score kann helfen, Prioritäten zu setzen, auf welche Bewertungen und Kontrollen Sie sich konzentrieren müssen, um Ihre allgemeine Compliance-Haltung zu verbessern.

Die angezeigten Kompatibilitäts Bewertungswerte für das Steuerelement werden *in ihrer Gesamtheit* auf das Gesamtergebnis der Konformitätsbewertung auf Pass/Fail-Basis angewendet. Das Steuerelement ist implementiert und übergibt den nachfolgenden Bewertungstest oder nicht. Zugewiesene Punkte werden zur Kompatibilitätsbewertung hinzugefügt, wenn das Steuerelement Folgendes besitzt:

- **Implementierungs Status** entspricht **implementiert** oder **alternative Implementierung** und,
- **Test Ergebnis** gleich **übergeben**.

## <a name="compliance-score"></a>Kompatibilitätsbewertung
  
Im Compliance-Manager werden Baseline-Bewertungen von der Steuerelementebene in die Aktionselement Ebene verlagert. Die Ergebnisse basieren auf dem Zweck (Detektiv, vorbeugend oder Korrektiv) und der Erzwingung (diskretionäre oder obligatorisch) des Aktionselements.

Aktionselemente werden Steuerelementen zugeordnet, und wenn ein Steuerelement mehreren Aktionselementen zugeordnet wird, ist die Summe der Ergebnisse des Aktionselements das Kontrollergebnis. Die Summe der Steuerelement Bewertung für alle Steuerelemente in einer bestimmten Bewertung ist das Bewertungsergebnis. Die durchschnittliche Punktzahl aller Bewertungen in einer Gruppe ist die Konformitätsbewertung für diese Gruppe.
  
### <a name="mandatory-or-discretionary-controls"></a>Obligatorische oder diskretionäre Steuerelemente
  
 **Zwingende Steuerelemente** sind Aktionen, die weder absichtlich noch versehentlich umgangen werden können. Ein Beispiel für ein allgemeines obligatorisches Steuerelement ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für die Länge, Komplexität und den Ablauf von Kennwörtern festlegt. Benutzer müssen diese Anforderungen erfüllen, um auf das System zugreifen zu können.
  
 **Diskretionäre Steuerelemente** basieren darauf, dass Benutzer Richtlinien verstehen und entsprechend handeln. Beispielsweise ist eine Richtlinie, bei der Benutzer Ihren Computer beim Verlassen des Computers Sperren müssen, ein diskretionäres Steuerelement, da es vom Benutzer abhängig ist.
  
### <a name="preventative-detective-or-corrective-controls"></a>Vorbeugende, Detektive oder korrigierende Steuerelemente
  
 **Vorbeugende Steuerelemente** sind Aktionen, die bestimmte Risiken verhindern. Beispielsweise ist das Schützen von Informationen im Ruhezustand mithilfe von Verschlüsselung eine vorbeugende Kontrolle gegen Angriffe und Verstöße. Die Trennung von Zöllen ist eine präventive Kontrolle zur Verwaltung von Interessenkonflikten und zum Schutz vor Betrug.
  
 **Detektiv Steuerelemente** sind Aktionen, die Systeme aktiv überwachen, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die Risiken darstellen oder die verwendet werden können, um Eindringversuche zu erkennen oder um festzustellen, ob ein Verstoß aufgetreten ist. Die System Zugriffsüberwachung und die Überwachung privilegierter administrativer Aktionen sind Typen von Detektiv Überwachungs Steuerelementen. Compliance-Überwachungen sind eine Art von Detektiv Steuerung, die zum Auffinden von Prozessproblemen verwendet wird.
  
**Korrektur Steuerelemente** sind Steuerelemente, die versuchen, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zur Verringerung des unmittelbaren Effekts zu ergreifen und den Schaden nach Möglichkeit umzukehren. Die Antwort auf Datenschutz Vorfälle ist eine Korrekturhilfe, um nach einem Verstoß Schäden zu begrenzen und Systeme auf einen Betriebszustand zurückzusetzen.
  
Jedes Steuerelement besitzt einen zugewiesenen Wert im Compliance-Manager basierend auf dem Risiko, das es darstellt:

|**Typ**|**Zugewiesene Punktzahl**|
|:-----|:-----|
| Vorbeugende Pflicht | 27 |
| Vorbeugender Ermessensspielraum | 9 |
| Detektiv erforderlich | 3 |
| Detektiv-diskretionäres | 1 |
| Korrektur Pflicht | 3 |
| Korrigierendes diskretionäre | 1 |
  
## <a name="action-item-workflow"></a>Aktionselement Workflow

Hier ist der grundlegende Workflow für ein typisches Aktionselement:
  
1. Der Compliance-, Risiko-, Datenschutz-und/oder Datenschutzbeauftragte einer Organisation weist einer Person in der Organisation eine Aufgabe zu, um ein Steuerelement zu implementieren. Diese Person kann Folgendes sein:

    - Ein Geschäftsrichtlinien Besitzer.
    - Ein IT-Implementierer.
    - Eine andere Person in der Organisation, die für die Ausführung der Aufgabe zuständig ist.

2. Diese Person führt die Aufgaben aus, die für die Implementierung der Steuerung erforderlich sind, lädt den Nachweis der Implementierung in Compliance-Manager hoch und markiert das an das Aktionselement gebundene Steuerelement als implementiert. Sobald diese Aufgaben abgeschlossen sind, weisen Sie das Aktionselement einem Gutachter zur Überprüfung zu.

    Prüfer können sein:

    - Interne Prüfer, die die Validierung von Steuerelementen in einer Organisation durchführen.
    - Externe Prüfer, die die Konformität prüfen, überprüfen und zertifizieren, beispielsweise die unabhängigen Drittanbieter Organisationen, die die Cloud-Dienste von Microsoft überwachen.

3. Der Assessor überprüft das Steuerelement und untersucht den Beweis und kennzeichnet das Steuerelement als bewertet und die Ergebnisse der Bewertung.

Nachdem alle einem Assessment zugeordneten Steuerelemente bewertet wurden, ist die Bewertung abgeschlossen.