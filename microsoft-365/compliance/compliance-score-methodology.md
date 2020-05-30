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
description: Erfahren Sie, wie Microsoft Compliance Score eine personalisierte Bewertung basierend auf Aktionen berechnet, die zur Behebung von Risiken und zur Verbesserung Ihrer Compliance-Haltung ergriffen werden.
ms.openlocfilehash: e1a13cee8086e158f3869a00384166366c0a63dc
ms.sourcegitcommit: 436841236dc41390a3be9f8936d19d3d017fa35c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2020
ms.locfileid: "44429190"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Berechnung der Microsoft-Kompatibilitätsbewertung (Vorschau)

> [!IMPORTANT]
> Empfehlungen der Compliancebewertung und vom Compliance-Manager sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kunden Kontrollen pro ihrer regulatorischen Umgebung zu bewerten und zu validieren. Diese Dienste befinden sich derzeit in der Vorschau und unterliegen den allgemeinen Geschäftsbedingungen in den [Online Dienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910). Siehe auch [Microsoft 365 Lizenzierung Leitfaden für Sicherheit und Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="overview"></a>Übersicht

Das Kompatibilitäts Bewertungs Dashboard zeigt eine Bewertung an, die den Fortschritt beim Abschließen von Verbesserungs Aktionen innerhalb von Steuerelementen misst. Ihre Punkte werden nach Abschluss der Aktionen gesammelt.

Ihre Bewertung wird basierend auf dem Abschluss von von Microsoft verwalteten Aktionen und von Kunden verwalteten Aktionen berechnet. Jede Aktion hat eine andere Auswirkung auf Ihre Punktzahl, je nach den potenziellen Risiken. Ihre Punktzahl kann helfen, Prioritäten zu setzen, auf die Sie sich konzentrieren müssen, um Ihre allgemeine Compliance-Haltung zu verbessern.

Die angezeigten Werte für die Konformitätsbewertung für das Steuerelement werden *in ihrer Gesamtheit* auf die Gesamtpunktzahl auf Pass/Fail-Basis angewendet. Entweder wird das Steuerelement implementiert und übergibt den nachfolgenden Bewertungstest oder nicht. Zugewiesene Punkte werden zur Konformitätsbewertung hinzugefügt, wenn das Steuerelement Folgendes besitzt:

- **Implementierungs Status** entspricht **implementiert** oder **alternative Implementierung** und,
- **Test Ergebnis** gleich **übergeben**.

Die Summe der Punkte, die durch Verbesserungs Aktionen erzielt werden, ist das Kontrollergebnis. Die Summe ihrer Kontrollpunkte ist das Bewertungsergebnis. Die Summe ihrer Bewertungsergebnisse entspricht dem Gesamtergebnis der Konformität.

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Ursprüngliche Bewertung basierend auf der Microsoft 365-Datenschutz Basis
  
Mit der Kompatibilitätsbewertung erhalten Sie eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis, bei der es sich um eine Reihe von Steuerelementen handelt, die wichtige Regeln und Standards für den Datenschutz und die allgemeine Datensteuerung beinhalten. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

## <a name="how-compliance-score-continuously-assesses-controls"></a>So beurteilt Compliance Score kontinuierlich Steuerelemente

Compliance Score scannt automatisch Ihre Microsoft 365-Umgebung und erkennt Ihre Systemeinstellungen, und aktualisiert Ihren technischen Steuerungsstatus kontinuierlich und automatisch. Secure Score ist das zugrunde liegende Modul, das die Überwachung ausführt. [Erfahren Sie mehr über Secure Score und wie es funktioniert](../security/mtp/microsoft-secure-score.md).

Ihr Steuerelementstatus wird alle 24 Stunden auf dem Dashboard für die Konformitätsbewertung aktualisiert. Nachdem Sie eine Empfehlung zur Implementierung eines Steuerelements befolgt haben, wird der Steuerelementstatus am nächsten Tag aktualisiert.

Wenn Sie beispielsweise die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) im Azure AD-Portal aktivieren, erkennt die Konformitätsbewertung die Einstellung und spiegelt diese in den Details des Steuerelements für den Zugriff auf die Lösung wider. Wenn Sie sich umgekehrt nicht für MFA aktiviert haben, kennzeichnet das Konformitäts Bewertungsergebnis dies als empfohlene Aktion, die Sie ergreifen sollten.

Während der öffentlichen Vorschau steht eine kontinuierliche Bewertung für einen Teil der Steuerelemente, jedoch nicht für alle zur Verfügung.
  
## <a name="control-types-and-points"></a>Steuerelementtypen und-Punkte

Das Kompatibilitäts Ergebnis verfolgt zwei Arten von Steuerelementen, die von Microsoft verwaltet und von Kunden verwaltet werden, von denen jede über Punkte verfügt, die zu ihrer Gesamtpunktzahl beitragen:

1. **Kunden verwaltete Punkte** tragen zur Konformitätsbewertung basierend auf Steuerelementen bei, die von Ihrer Organisation verwaltet werden.
2. Von **Microsoft verwaltete Punkte** tragen zur Konformitätsbewertung basierend auf Steuerelementen bei, die von Microsoft als Cloud-Dienstanbieter verwaltet werden.

Steuerelementen wird ein Bewertungs Wert zugewiesen, je nachdem, ob Sie obligatorisch oder diskretionäre sind und ob Sie vorbeugend, detektivisch oder Korrektiv sind.

### <a name="mandatory-and-discretionary-controls"></a>Obligatorische und diskretionäre Steuerelemente

 - **Zwingende Steuerelemente** sind Aktionen, die weder absichtlich noch versehentlich umgangen werden können. Ein Beispiel ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für die Kennwortlänge,-Komplexität und-Ablaufzeit festlegt. Benutzer müssen diese Anforderungen für den Zugriff auf das System befolgen.
  
 - **Diskretionäre Steuerelemente** basieren darauf, dass Benutzer Richtlinien verstehen und entsprechend handeln. Beispielsweise ist eine Richtlinie, bei der Benutzer Ihren Computer beim Verlassen des Computers Sperren müssen, ein diskretionäres Steuerelement, da es vom Benutzer abhängig ist.
  
### <a name="preventative-detective-and-corrective-controls"></a>Vorbeugende, Detektive und korrigierende Steuerelemente
  
 - **Vorbeugende Kontrollen** befassen sich mit bestimmten Risiken. Beispielsweise ist das Schützen von Informationen im Ruhezustand mithilfe von Verschlüsselung eine vorbeugende Kontrolle gegen Angriffe und Verstöße. Die Trennung von Zöllen ist eine vorbeugende Kontrolle zur Verwaltung von Interessenkonflikten und zum Schutz vor Betrug.
  
 - **Detektiv Steuerelemente** überwachen Systeme aktiv, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die Risiken darstellen oder die zum Erkennen von Eindringlingen oder Verstößen verwendet werden können. Die System Zugriffsüberwachung und die Überwachung privilegierter administrativer Aktionen sind Typen von Detektiv Überwachungs Steuerelementen. Compliance-Überwachungen sind eine Art von Detektiv Steuerung, die zum Auffinden von Prozessproblemen verwendet wird.
  
- **Korrigierende Steuerelemente** versuchen, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zu ergreifen, um den unmittelbaren Effekt zu reduzieren, und den Schaden nach Möglichkeit umzukehren. Die Antwort auf Datenschutz Vorfälle ist eine Korrekturhilfe, um nach einem Verstoß Schäden zu begrenzen und Systeme auf einen Betriebszustand zurückzusetzen.
  
Jedes Steuerelement hat einen zugewiesenen Wert in Compliance Score basierend auf dem Risiko, das es darstellt:

|**Type**|**Zugewiesene Punktzahl**|
|:-----|:-----|
| Vorbeugende Pflicht | 27 |
| Vorbeugender Ermessensspielraum | 9  |
| Detektiv erforderlich | 3 |
| Detektiv-diskretionäres | 1  |
| Korrektur Pflicht | 3 |
| Korrigierendes diskretionäre | 1  |
  
![Konformitätsbewertung steuert Punktwerte](../media/compliance-score-controls-scoring.png "Konformitätsbewertung steuert Punktwerte")