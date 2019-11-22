---
title: Berechnung der Konformitätsbewertung
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
ms.openlocfilehash: a94b1051af383041a89fa136ae490875ea48782d
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793659"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Berechnung der Microsoft-Kompatibilitätsbewertung (Vorschau)

> [!IMPORTANT]
> Compliance Score ist kein absolutes Maß für die organisatorische Einhaltung einer bestimmten Norm oder Regulierung. Sie drückt das Ausmaß aus, in dem Sie Steuerelemente eingeführt haben, die die Risiken für personenbezogene Daten und den Schutz der Privatsphäre reduzieren können. Empfehlungen aus dem Compliance Score und dem Compliance-Manager sollten nicht als Garantie für die Compliance interpretiert werden. Dieser Dienst befindet sich derzeit in der Vorschau und unterliegt den allgemeinen Geschäftsbedingungen in den [Online Dienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910).

## <a name="overview"></a>Übersicht

Das Kompatibilitäts Bewertungs Dashboard zeigt eine Bewertung an, die den Fortschritt beim Abschließen von Verbesserungs Aktionen innerhalb von Steuerelementen misst. Ihre Punkte werden nach Abschluss der Aktionen gesammelt.

Ihre Bewertung wird basierend auf dem Abschluss von von Microsoft verwalteten Aktionen und von Kunden verwalteten Aktionen berechnet. Jede Aktion unterscheidet sich je nach den potenziellen Risiken durch eine andere Auswirkung auf Ihre Bewertung, sodass die Bewertung helfen kann, Prioritäten zu setzen, auf die Sie sich konzentrieren müssen, um Ihre allgemeine Compliance-Haltung zu verbessern.

Die angezeigten Werte für die Konformitätsbewertung für das Steuerelement werden *in ihrer Gesamtheit* auf die Gesamtpunktzahl auf Pass/Fail-Basis angewendet. Das Steuerelement ist implementiert und übergibt den nachfolgenden Bewertungstest oder nicht. Zugewiesene Punkte werden zur Konformitätsbewertung hinzugefügt, wenn das Steuerelement Folgendes besitzt:

- **Implementierungs Status** entspricht **implementiert** oder **alternative Implementierung** und,
- **Test Ergebnis** gleich **übergeben**.

Die Summe der Punkte, die durch Verbesserungs Aktionen erzielt werden, ist das Kontrollergebnis. Die Summe ihrer Kontrollpunkte ist das Bewertungsergebnis. Die Summe ihrer Bewertungsergebnisse entspricht dem Gesamtergebnis der Konformität.

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Ursprüngliche Bewertung basierend auf der Microsoft 365-Datenschutz Basis
  
Mit der Kompatibilitätsbewertung erhalten Sie eine vordefinierte Bewertung basierend auf der Microsoft 365-Datenschutz Basis, bei der es sich um eine Reihe von Steuerelementen handelt, die wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung beinhalten. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierung) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management). Program) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

## <a name="how-compliance-score-continuously-assesses-controls"></a>So beurteilt Compliance Score kontinuierlich Steuerelemente

Compliance Score scannt automatisch Ihre Microsoft 365-Umgebung und erkennt Ihre Systemeinstellungen, und aktualisiert Ihren technischen Steuerungsstatus kontinuierlich und automatisch. Wenn Sie beispielsweise die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) im Azure AD-Portal aktiviert haben, erkennt das Kompatibilitäts Ergebnis die Einstellung und gibt die Informationen in den Details des Steuerelements für den Zugriff auf die Lösung wieder. Wenn Sie sich umgekehrt nicht für MFA aktiviert haben, kennzeichnet das Konformitäts Bewertungsergebnis dies als empfohlene Aktion, die Sie ergreifen sollten.

Die Kompatibilitätsbewertung aktualisiert Ihren Steuerelementstatus alle 24 Stunden. Nachdem Sie eine Empfehlung zur Implementierung eines Steuerelements befolgt haben, wird der Status des Steuerelements am nächsten Tag aktualisiert.

Während der öffentlichen Vorschau steht eine kontinuierliche Bewertung für einen Teilsteuerelemente, jedoch nicht für alle zur Verfügung.
  
## <a name="control-types-and-points"></a>Steuerelementtypen und-Punkte

Das Kompatibilitäts Ergebnis verfolgt zwei Arten von Steuerelementen, die von Microsoft verwaltet und von Kunden verwaltet werden, von denen jede über Punkte verfügt, die zu ihrer Gesamtpunktzahl beitragen:

1. **Kunden verwaltete Punkte** tragen zur Konformitätsbewertung basierend auf Steuerelementen bei, die von Ihrer Organisation verwaltet werden.
2. Von **Microsoft verwaltete Punkte** tragen zur Konformitätsbewertung basierend auf Steuerelementen bei, die von Microsoft als Cloud-Dienstanbieter verwaltet werden.

Steuerelementen wird ein Bewertungs Wert zugewiesen, je nachdem, ob Sie obligatorisch oder diskretionäre sind und ob Sie vorbeugend, detektivisch oder Korrektiv sind – wie unten beschrieben.

### <a name="mandatory-and-discretionary-controls"></a>Obligatorische und diskretionäre Steuerelemente

 - **Zwingende Steuerelemente** sind Aktionen, die weder absichtlich noch versehentlich umgangen werden können. Ein Beispiel ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für die Kennwortlänge,-Komplexität und-Ablaufzeit festlegt. Benutzer müssen diese Anforderungen erfüllen, um auf das System zugreifen zu können.
  
 - **Diskretionäre Steuerelemente** basieren darauf, dass Benutzer Richtlinien verstehen und entsprechend handeln. Beispielsweise ist eine Richtlinie, bei der Benutzer Ihren Computer beim Verlassen des Computers Sperren müssen, ein diskretionäres Steuerelement, da es vom Benutzer abhängig ist.
  
### <a name="preventative-detective-and-corrective-controls"></a>Vorbeugende, Detektive und korrigierende Steuerelemente
  
 - **Vorbeugende Kontrollen** befassen sich mit bestimmten Risiken. Beispielsweise ist das Schützen von Informationen im Ruhezustand mithilfe von Verschlüsselung eine vorbeugende Kontrolle gegen Angriffe und Verstöße. Die Trennung von Zöllen ist eine vorbeugende Kontrolle zur Verwaltung von Interessenkonflikten und zum Schutz vor Betrug.
  
 - **Detektiv Steuerelemente** überwachen Systeme aktiv, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die Risiken darstellen oder die verwendet werden können, um Eindringversuche zu erkennen oder um festzustellen, ob ein Verstoß auftritt. Die System Zugriffsüberwachung und die Überwachung privilegierter administrativer Aktionen sind Typen von Detektiv Überwachungs Steuerelementen. Compliance-Überwachungen sind eine Art von Detektiv Steuerung, die zum Auffinden von Prozessproblemen verwendet wird.
  
- **Korrigierende Steuerelemente** versuchen, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zu ergreifen, um den unmittelbaren Effekt zu reduzieren, und den Schaden nach Möglichkeit umzukehren. Die Antwort auf Datenschutz Vorfälle ist eine Korrekturhilfe, um nach einem Verstoß Schäden zu begrenzen und Systeme auf einen Betriebszustand zurückzusetzen.
  
Jedes Steuerelement hat einen zugewiesenen Wert in Compliance Score basierend auf dem Risiko, das es darstellt:

|**Typ**|**Zugewiesene Punktzahl**|
|:-----|:-----|
| Vorbeugende Pflicht | 27 |
| Vorbeugender Ermessensspielraum | 9  |
| Detektiv erforderlich | 3  |
| Detektiv-diskretionäres | 1  |
| Korrektur Pflicht | 3  |
| Korrigierendes diskretionäre | 1  |
  