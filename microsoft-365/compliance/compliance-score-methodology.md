---
title: Berechnung der Microsoft-Kompatibilitätsbewertung (Vorschau)
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
description: Erfahren Sie, wie Microsoft Compliance Score eine personalisierte Bewertung basierend auf Aktionen berechnet, die zur Behebung von Risiken und zur Verbesserung Ihrer Compliance-Haltung ergriffen werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024675"
---
# <a name="compliance-score-preview-calculation"></a>Berechnung der Kompatibilitätsbewertung (Vorschau)

> [!IMPORTANT]
> Empfehlungen der Compliancebewertung und vom Compliance-Manager sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kunden Kontrollen pro ihrer regulatorischen Umgebung zu bewerten und zu validieren. Diese Dienste befinden sich derzeit in der Vorschau und unterliegen den allgemeinen Geschäftsbedingungen in den [Online Dienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910). Siehe auch [Microsoft 365 Lizenzierung Leitfaden für Sicherheit und Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-compliance-score-works"></a>Funktionsweise der Kompatibilitätsbewertung

Das Kompatibilitäts Bewertungs Dashboard zeigt eine Bewertung an, die den Fortschritt beim Abschließen von Verbesserungs Aktionen innerhalb von Steuerelementen misst. Jede Aktion hat eine andere Auswirkung auf Ihre Punktzahl, je nach den potenziellen Risiken. Ihre Punktzahl kann helfen, Prioritäten zu setzen, auf die Sie sich konzentrieren müssen, um Ihre allgemeine Compliance-Haltung zu verbessern.

Die angezeigten Werte für die Konformitätsbewertung für das Steuerelement werden *in ihrer Gesamtheit* auf die Gesamtpunktzahl auf Pass/Fail-Basis angewendet. Entweder ist das Steuerelement implementiert und übergibt den nachfolgenden Bewertungstest oder nicht. 

Wenn das Steuerelement über Folgendes verfügt, werden der Konformitätsbewertung Punkte hinzugefügt:

- **Implementierungs Status** entspricht **implementiert** oder **alternative Implementierung**und
- **Test Ergebnis** gleich **übergeben**.

Eine Steuerelement Bewertung ist die Summe der Punkte, die durch Verbesserungs Aktionen erzielt wurden. Die Summe ihrer Kontrollpunkte ist das Bewertungsergebnis. **Die Summe ihrer Bewertungsergebnisse entspricht dem Gesamtergebnis der Konformität.**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Ursprüngliche Bewertung basierend auf der Microsoft 365-Datenschutz Basis
  
Mit der Kompatibilitätsbewertung erhalten Sie eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis. Dieser Basisplan umfasst eine Reihe von Steuerelementen, die wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung beinhalten. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

Die Datenschutz-Basisbewertung (standardmäßig für alle Organisationen bereitgestellt) wird verwendet, um die anfängliche Bewertung zu berechnen, bevor Sie andere Bewertungen konfigurieren. Bei Ihrem ersten Besuch sammelt Compliance Score bereits Signale von Ihren Microsoft 365-Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Verhältnis zu wichtigen Datenschutzstandards und-Vorschriften arbeitet, und wie Sie die vorgeschlagenen Verbesserungsmaßnahmen durchführen.

Da jede Organisation spezifische Anforderungen hat, beruht Compliance Score darauf, dass Sie eigene Bewertungen einrichten und verwalten, um das Risiko so umfassend wie möglich zu minimieren und möglichst weit zu mindern.

## <a name="how-compliance-score-continuously-assesses-controls"></a>So beurteilt Compliance Score kontinuierlich Steuerelemente

Compliance Score scannt automatisch Ihre Microsoft 365-Umgebung und erkennt Ihre Systemeinstellungen, und aktualisiert Ihren technischen Steuerungsstatus kontinuierlich und automatisch. Secure Score ist das zugrunde liegende Modul, das die Überwachung ausführt.

Ihr Steuerelementstatus wird alle 24 Stunden auf dem Dashboard für die Konformitätsbewertung aktualisiert. Nachdem Sie eine Empfehlung zur Implementierung eines Steuerelements befolgt haben, wird der Steuerelementstatus am nächsten Tag aktualisiert.

Wenn Sie beispielsweise die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) im Azure AD-Portal aktivieren, erkennt die Konformitätsbewertung die Einstellung und spiegelt diese in den Details des Steuerelements für den Zugriff auf die Lösung wider. Wenn Sie sich umgekehrt nicht für MFA aktiviert haben, kennzeichnet das Konformitäts Bewertungsergebnis dies als empfohlene Aktion, die Sie ergreifen sollten.

Während der öffentlichen Vorschau steht eine kontinuierliche Bewertung für einen Teil der Steuerelemente, jedoch nicht für alle zur Verfügung.

#### <a name="learn-more"></a>Weitere Informationen
[Lesen Sie über Secure Score und wie es funktioniert](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Aktionstypen und-Punkte

Das Kompatibilitäts Ergebnis verfolgt zwei Arten von Aktionen: von Ihnen verwaltete Aktionen und Aktionen, die von Microsoft verwaltet werden. Beide Arten von Aktionen weisen bei der Fertigstellung Punkte auf, die auf die Gesamtpunktzahl zählen:

1. **Ihre Punkte** tragen zur Konformitätsbewertung basierend auf Steuerelementen bei, die von Ihrer Organisation verwaltet werden.
2. **Microsoft Managed Points** tragen zur Konformitätsbewertung basierend auf Aktionen bei, die von Microsoft als Cloud-Dienstanbieter verwaltet werden.

Aktionen werden basierend darauf, ob Sie obligatorisch oder diskretionäre sind, einen Bewertungs Wert zugewiesen und ob Sie vorbeugend, detektivisch oder Korrektiv sind.

### <a name="mandatory-and-discretionary-actions"></a>Obligatorische und diskretionäre Aktionen

 - **Obligatorische Aktionen** können weder absichtlich noch versehentlich umgangen werden. Ein Beispiel ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für die Kennwortlänge,-Komplexität und-Ablaufzeit festlegt. Benutzer müssen diese Anforderungen für den Zugriff auf das System befolgen.
  
 - **Diskretionäre Aktionen** basieren darauf, dass Benutzer Richtlinien verstehen und entsprechend handeln. Beispielsweise ist eine Richtlinie, bei der Benutzer Ihren Computer beim Verlassen des Computers Sperren müssen, eine Ermessens Maßnahme, da Sie vom Benutzer abhängig ist.
  
### <a name="preventative-detective-and-corrective-actions"></a>Vorbeugende, detektivische und korrigierende Aktionen
  
 - **Vorbeugende Aktionen** adressieren bestimmte Risiken. Beispielsweise ist das Schützen von Informationen im Ruhezustand mithilfe der Verschlüsselung vorbeugende Maßnahmen gegen Angriffe und Verstöße. Die Trennung von Zöllen ist eine vorbeugende Maßnahme zur Verwaltung von Interessenkonflikten und zum Schutz vor Betrug.
  
 - **Detektiv Aktionen** überwachen Systeme aktiv, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die ein Risiko darstellen oder die zum Erkennen von Eindringlingen oder Verstößen verwendet werden können. Beispiele hierfür sind die Systemzugriffs Überwachung und privilegierte Verwaltungsaktionen. Compliance-Überwachungen sind eine Art Detektiv Aktion, die verwendet wird, um Prozessprobleme zu finden.
  
- **Korrekturmaßnahmen** versuchen Sie, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zu ergreifen, um den unmittelbaren Effekt zu reduzieren, und den Schaden nach Möglichkeit umzukehren. Die Antwort auf Datenschutz Vorfälle ist eine Korrekturmaßnahme zum Begrenzen von Beschädigungen und zur Wiederherstellung von Systemen in einem Betriebszustand nach einer Verletzung.
  
Jede Aktion hat einen zugewiesenen Wert in Compliance Score basierend auf dem Risiko, das Sie darstellt:

|**Typ**|**Zugewiesene Punktzahl**|
|:-----|:-----|
| Vorbeugende Pflicht | 27 |
| Vorbeugender Ermessensspielraum | 9  |
| Detektiv erforderlich | 3  |
| Detektiv-diskretionäres | 1  |
| Korrektur Pflicht | 3  |
| Korrigierendes diskretionäre | 1  |
  
![Konformitätsbewertung steuert Punktwerte](../media/compliance-score-controls-scoring.png "Konformitätsbewertung steuert Punktwerte")