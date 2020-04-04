---
title: FAQ zur Microsoft-Konformitätsbewertung
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
description: Hier finden Sie Antworten auf häufig gestellte Fragen zu Microsoft-Konformitäts Bewertungspunkten, die Organisationen dabei helfen, Risikobewertungen zu vereinfachen und zu automatisieren.
ms.openlocfilehash: 942de8f8cc9eeb958cb7f8e96c9e7038447ce3f1
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141560"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft Compliance Score (Preview): häufig gestellte Fragen

## <a name="what-is-compliance-score"></a>Was ist das Kompatibilitäts Ergebnis?

Microsoft Compliance Score ist eine Vorschaufunktion im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md) , die Ihnen hilft, die Compliance-Haltung ihrer Organisation zu verstehen. Es wird eine risikobasierte Bewertung berechnet, die Ihren Fortschritt bei der Durchführung von Aktionen misst, um Risiken hinsichtlich des Datenschutzes und der regulatorischen Standards zu verringern. Compliance Score bietet integrierte Steuerungs Zuordnung, die die Verbindung allgemeiner Steuerelemente zwischen den wichtigsten Regeln und Standards ermöglicht, sodass Sie eine Aktion ausführen können, um mehrere Anforderungen gleichzeitig zu erfüllen und Ihr Compliance-Programm besser zu skalieren.

## <a name="how-do-i-access-compliance-score"></a>Wie kann ich auf das Kompatibilitäts Ergebnis zugreifen?

Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) , und **melden** Sie sich mit einer Administratorrolle von Microsoft 365 Global admin, Compliance Admin oder Compliance Data an. Wählen Sie **Kompatibilitätsbewertung** im linken Navigationsbereich aus. Das [Dashboard für die Konformitätsbewertung sollte dann mit ihrer Bewertung](compliance-score-setup.md#understand-the-compliance-score-dashboard)angezeigt werden. Wenn Sie keinen entsprechenden Rollen Zugriff haben, kann Ihnen der globale Administrator Ihrer Organisation die Berechtigung erteilen.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>Welche Rollen oder Berechtigungen sind für die Verwendung der Konformitätsbewertung erforderlich?

Die Kompatibilitätsbewertung verwendet ein Berechtigungsmodell für die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC), und die Aktionen, die Sie ausführen können, hängen vom Typ der Ihnen zugewiesenen Rolle ab. Der Microsoft 365-globale Administrator Ihrer Organisation ist die Person, die die Setup Funktionen ausführen und Rollen in der Kompatibilitätsbewertung verwalten kann. Benutzer benötigen mindestens die **Azure AD globale Leser** Rolle, um Daten in der Kompatibilitätsbewertung zu lesen. Weitere Informationen zu Berechtigungen, Rollen und Setupverfahren finden Sie unter [Compliance Score Setup](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>Was ist der Unterschied zwischen Compliance Score und Compliance-Manager?

Compliance-Score und Compliance-Manager verwenden dasselbe Back-End, aber Sie befinden sich an zwei unterschiedlichen Standorten (das Kompatibilitäts Ergebnis befindet sich im Microsoft 365 Compliance Center, und der Compliance-Manager befindet sich im Microsoft-Dienst Vertrauensstellungs Portal). Stellen Sie sich die Konformitätsbewertung als vereinfachte Version von Compliance-Manager vor, damit Sie eine umfassendere Übersicht über die aktuelle Compliance-Haltung ihrer Organisation und die Schritte zum Verbessern der Richtlinien erhalten. Sie können zwar viele Aktionen direkt innerhalb der Konformitätsbewertung durchführen, doch einige Funktionen sind derzeit im Compliance-Manager vorhanden. Lesen Sie mehr über die [Beziehung zwischen Compliance Score und Compliance-Manager](compliance-score.md#relationship-to-compliance-manager).

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>Wer sollte den Kompatibilitäts Faktor verwenden, und wer sollte den Compliance-Manager verwenden?

Das Kompatibilitäts Ergebnis ist für alle Benutzer in Ihrer Organisation hilfreich, die bei der Überwachung der Compliance und der Durchführung von Maßnahmen zur Unterstützung der Einhaltung behördlicher Standards eine Rolle spielen. Mit dem Kompatibilitäts Faktor müssen Sie sich nicht mit Vorschriften und Standards vertraut machen, um den Datenschutz in Ihrer Organisation zu verbessern. Compliance Score ist der optimale Ausgangspunkt für alle Benutzer. Von hier aus können Sie das Kompatibilitäts Ergebnis sehen, erfahren, welche empfohlenen Aktionen zur Minimierung von Risiken beitragen können, und in vielen Fällen direkt in die Lösungen einführen, um diese Aktionen auszuführen.

Vorerst ist Compliance-Manager der Ort, an dem Benutzerbewertungen verwalten und benutzerdefinierte Vorlagen erstellen können, um Bewertungen zu erstellen. Erfahren Sie mehr darüber [, welche Aktionen nur von Compliance-Manager während der öffentlichen Vorschau unterstützt werden](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) .

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Wenn ich über eine hohe Punktzahl verfüge, bedeutet dies, dass ich vollständig konform bin?

Nein. Das Kompatibilitäts Ergebnis misst Ihren Fortschritt bei der Durchführung empfohlener Maßnahmen, die zur Verringerung von Risiken im Zusammenhang mit Datenschutz und behördlichen Standards beitragen. Es ist kein absolutes Maß für die organisatorische Einhaltung einer bestimmten Norm oder Regulierung. Die Konformitätsbewertung sollte nicht als Garantie in irgendeiner Weise interpretiert werden.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>Welche Vorschriften und Standards werden von der Kompatibilitätsbewertung überwacht?

Mit der Kompatibilitätsbewertung erhalten Sie eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis, bei der es sich um eine Reihe von Steuerelementen handelt, die allgemeine Branchenvorschriften und-Standards enthält. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

Organisationen können benutzerdefinierte Bewertungen erstellen und hinzufügen, die für Ihre Organisation relevanter sind. Verwenden Sie eine der [vorkonfigurierten Vorlagen](compliance-score.md#templates)der Kompatibilitätsbewertung, passen Sie eine Microsoft-Vorlage mit ihren eigenen Steuerelementen und Aktionen an, oder erstellen Sie Ihre eigene Vorlage. Lesen Sie Details zum [Arbeiten mit Vorlagen](working-with-compliance-manager.md#templates).

Erfahren Sie, wie die Ergebnisbewertung durch [das Kompatibilitäts Ergebnis berechnet](compliance-score-methodology.md)wird.

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>Was ist der Unterschied zwischen der Konformitätsbewertung und der sicheren Bewertung?

Compliance Score bietet eine umfassende Übersicht über die Datenschutz-und Compliance-Haltung ihrer Organisation. Compliance Score bietet auch integrierte Workflow-Tools; Sie ermöglicht es Organisationen, Benutzern Aufgaben zuzuweisen, die Implementierung von Steuerelementen und den Teststatus nachzuverfolgen sowie Beweise hochzuladen und Überwachungsberichte zu erstellen.

Microsoft Secure Score ist ein Tool zur Sicherheitsanalyse, mit dem Sie Ihre Sicherheitsposition besser verstehen. [Erfahren Sie mehr über Secure Score und wie es funktioniert](../security/mtp/microsoft-secure-score.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>Welche Cloud-Dienste werden von der Konformitätsbewertung abgedeckt?

Das Kompatibilitäts Ergebnis bietet derzeit Bewertungen für Office 365 und InTune. Die erweiterte Abdeckung wird in zukünftigen Versionen erwartet und wird in den Versionshinweisen zur [Konformitätsbewertung](compliance-score-release-notes.md)aufgeführt.

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>Kann ich die Konformitätsbewertung für nicht-Microsoft-Produkte verwenden?

Während die Kompatibilitätsbewertung eine kontinuierliche Überwachung und empfohlene Aktionen nur für Microsoft-Cloud-Dienste bietet, können Sie benutzerdefinierte Bewertungen im Compliance-Manager für Ihre lokalen Drittanbieterdienste hinzufügen. Auf diese Weise können Sie die Microsoft-Kompatibilitätsbewertung als SaaS-Compliance-Verwaltungstool verwenden, um Sie bei der Verwaltung aller Steuerelemente in Ihren digitalen Objekten zu unterstützen.

Sie können eine der [vorkonfigurierten Vorlagen](compliance-score.md#templates) der Kompatibilitätsbewertung verwenden, um Bewertungen für bestimmte Standards zu erstellen oder [eigene Vorlagen zu erstellen](working-with-compliance-manager.md#create-a-template).

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>Wie lösche ich eine Vorlage oder Bewertung, die ich nicht mehr brauche?

Eine Bewertung oder Vorlage kann nicht gelöscht werden, Sie können Sie jedoch aus ihrer Ansicht ausblenden. Lesen Sie die [Anweisungen zum Ausblenden von Bewertungen](working-with-compliance-manager.md#hide-a-template-or-an-assessment).

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>Welche Testverfahren werden von Microsoft für Steuerelemente befolgt?

Microsoft nimmt an jährlichen Überwachungen für Steuerelemente Teil. Sie können die Überwachungsberichte von unseren Auditoren überprüfen, die im [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3)zum Download bereit stehen.

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>Warum werden einige Steuerelemente jährlich getestet, andere werden alle drei Jahre getestet?

Die FedRAMP-Bewertung ist ein Beispiel dafür, warum dies der Fall sein könnte. Es wird jedes Jahr durchgeführt und testet einen Querschnitt von Steuerelementen zwischen wichtigen Steuerelementfamilien. FedRAMP klassifiziert Steuerelemente als **Kern** , wenn Sie wichtig genug sind, um jährliche Tests zu erfordern. Steuerelemente, die als nicht-Kern bestimmt sind, werden alle drei Jahre getestet. Eine Teilmenge der Steuerelemente, die alle wichtigen Steuerelementfamilien umfassen, werden jährlich getestet. Auf diese Weise prüft jede jährliche Überwachung die Szenarien auf der ganzen Linie, um sicherzustellen, dass die Lösung robust ist. Lesen Sie mehr über den [jährlichen Bewertungsprozess für FedRAMP](https://www.fedramp.gov/annual-assessment-guidance/).
