---
title: Berechnung der Compliance-Bewertung
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
description: Erfahren Sie, wie Microsoft Compliance Manager eine personalisierte Bewertung basierend auf Maßnahmen berechnet, die zur Behandlung von Risiken und zur Verbesserung Ihrer Compliancehaltung ergriffen wurden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 756ce207b1e9583bf63f19351e85955950487404
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052113"
---
# <a name="compliance-score-calculation"></a>Berechnung der Compliance-Bewertung

**In diesem Artikel:** Erfahren Sie, wie Der Compliance-Manager eine Compliance-Bewertung für Ihre Organisation berechnet. In diesem Artikel wird erläutert, wie Sie Ihre Bewertung **interpretieren,** was die **Datenschutzgrundbewertung** **umfasst,** wie sie kontinuierlich überwacht wird und wie verschiedene Arten von Aktionen verwaltet und mit einer Bewertung **erzielt werden.**

> [!IMPORTANT]
> Empfehlungen des Compliance-Managers sollten nicht als eine Garantie für Compliance interpretiert werden. Es liegt an Ihnen, die Effektivität von Kundenkontrollen nach Ihrer gesetzlichen Umgebung zu bewerten und zu überprüfen. Diese Dienste unterliegen den Allgemeinen Geschäftsbedingungen in den [Onlinedienstbedingungen](https://go.microsoft.com/fwlink/?linkid=2108910). Siehe auch [Microsoft 365 Lizenzierungsanleitung für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>So lesen Sie Ihre Compliance-Bewertung

Das Compliance-Manager-Dashboard zeigt Ihre Gesamt-Compliance-Bewertung an. Diese Bewertung misst Ihren Fortschritt beim Abschließen empfohlener Verbesserungsmaßnahmen in Steuerelementen. Ihre Bewertung kann Ihnen helfen, Ihre aktuelle Compliance-Position zu verstehen. Es kann Ihnen auch helfen, Aktionen basierend auf ihrem Potenzial zur Risiko reduzierung priorisieren.

Ein Bewertungswert wird auf drei Ebenen zugewiesen:

1. **Bewertung der** Verbesserungsaktion: Jede Aktion hat je nach potenziellem Risiko unterschiedliche Auswirkungen auf Ihre Bewertung.

2. **Kontrollpunktzahl:** Diese Punktzahl ist die Summe der Punkte, die durch Abschließen von Verbesserungsmaßnahmen innerhalb des Steuerelements erzielt werden. Diese Summe wird vollständig auf Die Gesamtkonformitätsnote angewendet, wenn das Steuerelement beide der folgenden Bedingungen erfüllt:
    - **Implementierungsstatus** gleich **Implementierte** oder **Alternative Implementierung** und
    - **Testergebnis** gleich **Passed**.

3. **Bewertungsbewertung:** Diese Bewertung ist die Summe Ihrer Kontrollergebnisse. Sie wird mithilfe von Aktionsergebnissen berechnet. Jede Microsoft-Aktion und jede von Ihrer Organisation verwaltete Verbesserungsaktion wird einmal gezählt, unabhängig davon, wie oft in einem Steuerelement darauf verwiesen wird.

Die Gesamtkonformitätsnote wird mithilfe von Aktionsergebnissen berechnet, wobei jede Microsoft-Aktion einmal gezählt wird, jede von Ihnen verwaltete technische Aktion einmal gezählt wird und jede nicht technische Aktion, die Sie verwalten, einmal pro Gruppe gezählt wird. Diese Logik ist so konzipiert, dass sie die genaueste Buchhaltung darüber bietet, wie Aktionen in Ihrer Organisation implementiert und getestet werden. Möglicherweise können Sie feststellen, dass dies dazu führen kann, dass sich Die Gesamtbewertung der Compliance vom Durchschnitt Ihrer Bewertungsbewertung unterscheidet. Weitere Informationen zur [Bewertung von Aktionen finden Sie weiter unten.](#action-types-and-points)

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Anfängliche Bewertung basierend auf Microsoft 365 Datenschutzgrundlinie
  
Der Compliance-Manager gibt Ihnen eine erste Bewertung basierend auf der Microsoft 365 Datenschutzgrundlinie. Diese Basislinie umfasst eine Reihe von Kontrollen, die wichtige Vorschriften und Standards für den Datenschutz und die allgemeine Datenkontrolle umfassen. Diese Basislinie bezieht elemente hauptsächlich aus NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) und ISO (International Organization for Standardization), sowie aus FedRAMP (Federal Risk and Authorization Management Program) und DSGVO (General Data Protection Regulation of the European Union).

Ihre anfängliche Bewertung wird gemäß der standardmäßigen Data Protection Baseline-Bewertung berechnet, die für alle Organisationen bereitgestellt wird. Bei Ihrem ersten Besuch sammelt Der Compliance-Manager bereits Signale von Ihren Microsoft 365 Lösungen. Sie sehen auf einen Blick, wie Ihre Organisation im Vergleich zu wichtigen Datenschutzstandards und -vorschriften funktioniert, und sehen sich verbesserungswürdige Maßnahmen an.

Da jede Organisation bestimmte Anforderungen hat, ist compliance Manager darauf angewiesen, dass Sie Bewertungen einrichten und verwalten, um Risiken so umfassend wie möglich zu minimieren und zu mindern.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>So bewertet Der Compliance-Manager die Steuerelemente kontinuierlich

Der Compliance-Manager überprüft ihre Umgebung Microsoft 365 und erkennt Ihre Systemeinstellungen und aktualisiert ihren technischen Aktionsstatus kontinuierlich und automatisch. Microsoft Secure Score ist das zugrunde liegende Modul, das die Überwachung durchführt.

Der Aktionsstatus wird alle 24 Stunden auf Ihrem Dashboard aktualisiert. Sobald Sie einer Empfehlung zum Implementieren eines Steuerelements folgen, wird der Steuerelementstatus in der Regel am nächsten Tag aktualisiert.

Wenn Sie beispielsweise die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) im Azure AD-Portal aktivieren, erkennt der Compliance-Manager die Einstellung und spiegelt sie in den Details der Steuerelementzugriffslösung wider. Wenn Sie MFA nicht aktivieren, gibt der Compliance-Manager dies als empfohlene Aktion an.

Erfahren Sie mehr [über Secure Score und deren Funktionsweise.](../security/defender/microsoft-secure-score.md)
  
## <a name="action-types-and-points"></a>Aktionstypen und -punkte

Der Compliance-Manager verfolgt zwei Arten von Aktionen:

1. **Ihre Verbesserungsmaßnahmen:** Aktionen, die Von Ihrer Organisation verwaltet werden.
2. **Microsoft-Aktionen:** Von Microsoft verwaltete Aktionen.

Beide Arten von Aktionen haben Punkte, die auf Ihre Gesamtpunktzahl zählen, wenn sie abgeschlossen sind.

### <a name="technical-and-non-technical-actions"></a>Technische und nicht technische Aktionen

Aktionen werden nach technischer oder nicht technischer Natur gruppieren. Die Bewertungswirkung der einzelnen Aktionen unterscheidet sich je nach Typ.

- **Technische Aktionen** werden durch Interaktion mit der Technologie einer Lösung (z. B. Ändern einer Konfiguration) implementiert. Die Punkte für technische Aktionen werden einmal pro Aktion gewährt, unabhängig davon, zu wie vielen Gruppen sie gehört.

- **Nicht technische Aktionen** werden von Ihrer Organisation verwaltet und auf andere Weise implementiert, als mit der Technologie einer Lösung zu arbeiten. Es gibt zwei Arten von nicht technischen Aktionen: **Dokumentation und** **Betrieb**. Die Punkte für diese Aktionen werden auf Ihre Compliance-Bewertung auf Gruppenebene angewendet. Das bedeutet, wenn eine Aktion in mehreren Gruppen vorhanden ist, erhalten Sie den Punktwert der Aktion jedes Mal, wenn Sie sie in einer Gruppe implementieren.

**Beispiel für die Bewertung technischer und nicht technischer Aktionen:**

Angenommen, Sie haben eine technische Aktion im Wert von 3 Punkten, die in 5 Gruppen vorhanden ist, und Sie haben eine nicht technische Aktion im Wert von 3 Punkten, die in den gleichen 5 Gruppen vorhanden ist.

Wenn Sie die technische Aktion erfolgreich implementieren, erhalten Sie insgesamt 3 Punkte. Dies liegt daran, dass Sie die Aktion nur einmal für Ihren Mandanten implementieren müssen. Der Implementierungs- und Teststatus der technischen Aktion wird in allen Instanzen dieser Aktion, in jeder Gruppe, zu der sie gehört, identisch angezeigt.

Wenn Sie die nicht technische Aktion erfolgreich in jeder der 5 Gruppen implementieren, erhalten Sie insgesamt 15 Punkte. Dies liegt daran, dass Sie die Aktion in jeder Gruppe implementieren müssen. Die Implementierung und der Teststatus der nicht technischen Aktion unterscheiden sich gruppenübergreifend, da die Aktion in den einzelnen Gruppen separat implementiert wird.

Diese Bewertungslogik ist so konzipiert, dass sie die genaueste Buchhaltung darüber bietet, wie Aktionen in Ihrer Organisation implementiert und getestet werden.

### <a name="how-score-values-are-determined"></a>Bestimmen von Bewertungswerten
 
Aktionen wird ein Bewertungswert zugewiesen, der darauf basiert, ob sie obligatorisch oder diskretionär sind und ob sie präventiv, detektivisch oder korrektiv sind.

### <a name="mandatory-and-discretionary-actions"></a>Obligatorische und diskretionäre Aktionen

 - **Obligatorische Aktionen** können weder absichtlich noch versehentlich umgangen werden. Ein Beispiel für eine obligatorische Aktion ist eine zentral verwaltete Kennwortrichtlinie, die Anforderungen für Kennwortlänge, Komplexität und Ablauf festlegen. Die Benutzer müssen diese Anforderungen erfüllen, um auf das System zugreifen zu können.
  
 - **Diskretionäre Aktionen** verlassen sich darauf, dass Benutzer eine Richtlinie verstehen und einhalten. Eine Richtlinie, nach der Benutzer ihren Computer sperren müssen, wenn sie ihn verlassen, ist beispielsweise eine diskretionäre Aktion, da sie auf dem Benutzer basiert.
  
### <a name="preventative-detective-and-corrective-actions"></a>Vorbeugende, detektive und Korrekturmaßnahmen
  
 - **Vorbeugende Aktionen adressieren** bestimmte Risiken. Beispielsweise ist der Schutz von ruhenden Informationen mithilfe der Verschlüsselung eine vorbeugende Maßnahme gegen Angriffe und Verstöße. Die Aufgabentrennung ist eine vorbeugende Maßnahme zur Verwaltung von Interessenkonflikten und zum Schutz vor Betrug.
  
 - **Detektivaktionen** überwachen Systeme aktiv, um unregelmäßige Bedingungen oder Verhaltensweisen zu identifizieren, die Risiken darstellen oder zur Erkennung von Einbrüchen oder Verstößen verwendet werden können. Beispiele hierfür sind die Systemzugriffsüberwachung und privilegierte Administrative Aktionen. Überwachungen der Einhaltung gesetzlicher Vorschriften sind eine Art Von-Detektiv-Aktion, die zum Aufspüren von Prozessproblemen verwendet wird.
  
- **Korrekturmaßnahmen** versuchen, die negativen Auswirkungen eines Sicherheitsvorfalls auf ein Minimum zu beschränken, Korrekturmaßnahmen zur Reduzierung der unmittelbaren Auswirkung zu ergreifen und den Schaden nach Möglichkeit rückgängig zu machen. Die Reaktion auf Datenschutzvorfälle ist eine Korrekturmaßnahme, um Schäden zu begrenzen und Systeme nach einer Verletzung betriebsbereit zu machen.
  
Jede Aktion hat einen zugewiesenen Wert im Compliance-Manager basierend auf dem Risiko, das sie darstellt:

|**Typ**|**Zugewiesene Bewertung**|
|:-----|:-----|
| Vorbeugendes Obligatorisches | 27 |
| Vorbeugende Diskretion | 9  |
| Detektiv verpflichtend | 3 |
| Detektiv-Diskretion | 1 |
| Korrekturen verpflichtend | 3 |
| Berichtigungsspielräume | 1 |
  
![Compliance-Manager-Aktionspunktwerte](../media/compliance-score-action-scoring.png "Compliance-Manager-Aktionspunktwerte")