---
title: FAQ zur Microsoft-Kompatibilitätsbewertung (Preview)
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
ms.openlocfilehash: 6ba71620d689e6d028b61ff24f7c837337ef60c6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016200"
---
# <a name="compliance-score-preview-frequently-asked-questions"></a>Kompatibilitätsbewertung (Vorschau): häufig gestellte Fragen

## <a name="what-is-compliance-score"></a>Was ist das Kompatibilitäts Ergebnis?

Microsoft Compliance Score ist eine Vorschaufunktion im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md) , die Ihnen hilft, die Compliance-Haltung ihrer Organisation zu verstehen. Sie berechnet eine auf Risiken basierende Bewertung, die Ihren Fortschritt bei der Durchführung von Maßnahmen misst, mit denen sich Risiken hinsichtlich des Datenschutzes und regulatorischer Standards verringern lassen. Compliance Score bietet integrierte Steuerungs Zuordnung, die die Verbindung von allgemeinen Steuerelementen zwischen den wichtigsten Vorschriften und Standards ermöglicht. Mit dieser Zuordnung können Sie eine Aktion ausführen, um mehrere Anforderungen gleichzeitig zu erfüllen und Ihnen dabei helfen, Ihr Compliance-Programm zu skalieren.

## <a name="whats-new-in-the-preview-version-of-compliance-score"></a>Was ist neu in der Vorschauversion des Kompatibilitäts Bewertungs Punkts?

In den [Anmerkungen zur Kompatibilitätsbewertung](compliance-score-release-notes.md) finden Sie Informationen zu Funktionsupdates und bekannten Problemen.

## <a name="how-do-i-access-compliance-score"></a>Wie kann ich auf das Kompatibilitäts Ergebnis zugreifen?

Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) , und **melden** Sie sich mit einer Administratorrolle von Microsoft 365 Global admin, Compliance Admin oder Compliance Data an. Wählen Sie **Kompatibilitätsbewertung** im linken Navigationsbereich aus. Das [Dashboard für die Konformitätsbewertung sollte dann mit ihrer Bewertung](compliance-score-setup.md#understand-the-compliance-score-dashboard)angezeigt werden. Wenn Sie keinen entsprechenden Rollen Zugriff haben, kann Ihnen der globale Administrator Ihrer Organisation die Berechtigung erteilen.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>Welche Rollen oder Berechtigungen sind für die Verwendung der Konformitätsbewertung erforderlich?

Bei der Kompatibilitätsbewertung wird ein RBAC-Berechtigungsmodell (Role-Based Access Control, rollenbasierte Zugriffssteuerung) verwendet. Die Aktionen, die Sie ausführen können, hängen vom Typ der Rolle ab, die Ihnen zugewiesen ist. Der Microsoft 365-globale Administrator Ihrer Organisation ist die Person, die die Setup Funktionen ausführen und Rollen in der Kompatibilitätsbewertung verwalten kann. Benutzer benötigen mindestens die **Azure AD globale Leser** Rolle, um Daten in der Kompatibilitätsbewertung zu lesen. Weitere Informationen zu Berechtigungen, Rollen und Setupverfahren finden Sie unter [Compliance Score Setup](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>Was ist der Unterschied zwischen Compliance Score und Compliance-Manager?

Compliance-Score und Compliance-Manager teilen sich dasselbe Back-End. Alles, was Sie in einem Tool ausführen, wird im anderen Tool angezeigt. Sie befinden sich an zwei unterschiedlichen Standorten: das Kompatibilitäts Ergebnis befindet sich im Microsoft 365 Compliance Center, und Compliance-Manager befindet sich im Microsoft-Dienst Vertrauensstellungs Portal. Stellen Sie sich die Konformitätsbewertung als vereinfachte Version von Compliance-Manager vor, damit Sie eine umfassendere Übersicht über die aktuelle Compliance-Haltung ihrer Organisation und die Schritte zum Verbessern der Richtlinien erhalten.

Sie können zwar viele Aktionen direkt innerhalb der Konformitätsbewertung durchführen, einige Funktionen sind jedoch während der öffentlichen Vorschau im Compliance-Manager vorhanden. Lesen Sie mehr über die [Beziehung zwischen Compliance Score und Compliance-Manager](compliance-score.md#relationship-to-compliance-manager).

Access [Compliance Manager im Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ComplianceManager/V3). Achten Sie darauf, dass **Sie den Compliance-Manager** im Dropdownmenü obere Navigation auswählen, das die aktuellsten Funktionen aufweist, und *nicht Compliance-Manager (klassisch)*, das Features der früh Version enthält.

## <a name="should-i-use-compliance-score-or-compliance-manager"></a>Sollte ich die Kompatibilitätsbewertung oder den Compliance-Manager verwenden?

Das Kompatibilitäts Ergebnis ist für alle Benutzer in Ihrer Organisation hilfreich, die bei der Compliance eine Rolle spielen. Mit dem Kompatibilitäts Faktor müssen Sie sich nicht mit Vorschriften und Standards vertraut machen, um den Datenschutz in Ihrer Organisation zu verbessern. Compliance Score ist der optimale Ausgangspunkt für alle Benutzer. Von hier aus können Sie das Kompatibilitäts Ergebnis sehen, erfahren Sie, welche empfohlenen Aktionen zum Minimieren von Risiken beitragen können, und verwalten Sie Ihre Bewertungen.

Vorerst ist Compliance-Manager der Ort, an dem Sie benutzerdefinierte Vorlagen erstellen können, um Bewertungen zu erstellen. Erfahren Sie mehr darüber [, welche Aktionen nur von Compliance-Manager während der öffentlichen Vorschau unterstützt werden](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) .

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Wenn ich über eine hohe Punktzahl verfüge, bedeutet dies, dass ich vollständig konform bin?

Nein. Das Kompatibilitäts Ergebnis misst Ihren Fortschritt bei der Durchführung empfohlener Maßnahmen, die zur Verringerung von Risiken im Zusammenhang mit Datenschutz und behördlichen Standards beitragen. Es ist kein absolutes Maß für die organisatorische Einhaltung einer bestimmten Norm oder Regulierung. Die Konformitätsbewertung sollte nicht als Garantie in irgendeiner Weise interpretiert werden.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>Welche Vorschriften und Standards werden von der Kompatibilitätsbewertung überwacht?

Mit der Kompatibilitätsbewertung erhalten Sie eine erste Bewertung basierend auf der Microsoft 365-Datenschutz Basis, bei der es sich um eine Reihe von Steuerelementen handelt, die allgemeine Branchenvorschriften und-Standards enthält. Dieser Basisplan zeichnet Elemente in erster Linie vom NIST-GFK (National Institute of Standards and Technology Cyber Framework) und ISO (International Organization for Standardisierungs) sowie von FedRAMP (Bundes Risiko-und Autorisierungs Management Programm) und dsgvo (allgemeine Datenschutzverordnung der Europäischen Union).

Organisationen können benutzerdefinierte Bewertungen erstellen und hinzufügen, die für Ihre Organisation relevanter sind. Verwenden Sie eines der Kompatibilitäts Punkte, um [Vorlagen](compliance-score-templates.md)zu verwenden, passen Sie eine Microsoft-Vorlage mit ihren eigenen Steuerelementen und Aktionen an, oder erstellen Sie Ihre eigene Vorlage. Lesen Sie Details zum [Arbeiten mit Bewertungen und Vorlagen](compliance-score-assessments.md).

## <a name="how-does-compliance-score-continuously-assess-my-environment"></a>Wie beurteilt Compliance Score kontinuierlich meine Umgebung?

Compliance Score scannt automatisch Ihre Umgebung und verwendet Secure Score, um Systemeinstellungen zu erkennen. Erfahren Sie mehr über die [kontinuierliche Bewertung](compliance-score-methodology.md#how-compliance-score-continuously-assesses-controls).

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>Was ist der Unterschied zwischen der Konformitätsbewertung und der sicheren Bewertung?

Compliance Score bietet eine umfassende Übersicht über die Datenschutz-und Compliance-Haltung ihrer Organisation. Compliance Score bietet auch integrierte Workflow-Tools; Sie ermöglicht es Organisationen, Benutzern Aufgaben zuzuweisen, die Implementierung von Steuerelementen und den Teststatus nachzuverfolgen sowie Beweise hochzuladen und Überwachungsberichte zu erstellen.

Microsoft Secure Score ist ein Tool zur Sicherheitsanalyse, mit dem Sie Ihre Sicherheitsposition besser verstehen. [Erfahren Sie mehr über Secure Score und wie es funktioniert](../security/mtp/microsoft-secure-score-new.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>Welche Cloud-Dienste werden von der Konformitätsbewertung abgedeckt?

Das Kompatibilitäts Ergebnis bietet derzeit Bewertungen für Office 365 und InTune. Die erweiterte Abdeckung wird in zukünftigen Versionen erwartet und wird in den Versionshinweisen zur [Konformitätsbewertung](compliance-score-release-notes.md)aufgeführt.

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>Kann ich die Konformitätsbewertung für nicht-Microsoft-Produkte verwenden?

Während die Kompatibilitätsbewertung eine kontinuierliche Überwachung und empfohlene Aktionen nur für Microsoft-Cloud-Dienste bietet, können Sie benutzerdefinierte Bewertungen im Compliance-Manager für Ihre lokalen Drittanbieterdienste hinzufügen. Auf diese Weise können Sie die Microsoft-Kompatibilitätsbewertung als SaaS-Compliance-Verwaltungstool verwenden, um Sie bei der Verwaltung aller Steuerelemente in Ihren digitalen Objekten zu unterstützen.

Sie können eine der Kompatibilitätsbewertungen verwenden, um mithilfe von [Vorlagen](compliance-score-templates.md) Tests für bestimmte Standards zu erstellen oder eine [eigene Vorlage zu erstellen](working-with-compliance-manager.md#create-a-template), die Sie im Compliance-Manager ausführen müssen.

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>Wie lösche ich eine Vorlage oder Bewertung, die ich nicht mehr brauche?

Um eine Bewertung zu löschen, öffnen Sie die Bewertung, die Sie löschen möchten, und wählen Sie **Bewertung löschen**aus. Beachten Sie, dass das Löschen einer Bewertung dauerhaft ist. Hier finden Sie weitere Informationen zum [Löschen von Bewertungen](compliance-score-assessments.md#delete-an-assessment). Durch das Löschen eines Assessments wird die Vorlage nicht gelöscht. Vorlagen können nicht gelöscht, aber in der Ansicht ausgeblendet werden. Lesen Sie die [Anweisungen zum Ausblenden von Vorlagen](working-with-compliance-manager.md#hide-a-template-or-an-assessment).

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>Welche Testverfahren werden von Microsoft für Steuerelemente befolgt?

Microsoft nimmt an jährlichen Überwachungen für Steuerelemente Teil. Sie können die Überwachungsberichte von unseren Auditoren überprüfen, die im [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3)zum Download bereit stehen.

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>Warum werden einige Steuerelemente jährlich getestet, andere werden alle drei Jahre getestet?

Die FedRAMP-Bewertung ist ein Beispiel dafür, warum dies der Fall sein könnte. Es wird jedes Jahr durchgeführt und testet einen Querschnitt von Steuerelementen zwischen wichtigen Steuerelementfamilien. FedRAMP klassifiziert Steuerelemente als **Kern** , wenn Sie wichtig genug sind, um jährliche Tests zu erfordern. Steuerelemente, die als nicht-Kern bestimmt sind, werden alle drei Jahre getestet. Eine Teilmenge der Steuerelemente, die alle wichtigen Steuerelementfamilien umfassen, werden jährlich getestet. Auf diese Weise prüft jede jährliche Überwachung die Szenarien auf der ganzen Linie, um sicherzustellen, dass die Lösung robust ist. Lesen Sie mehr über den [jährlichen Bewertungsprozess für FedRAMP](https://www.fedramp.gov/annual-assessment-guidance/).
