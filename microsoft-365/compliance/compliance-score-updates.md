---
title: Microsoft Compliance Score-Updates
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
description: Details zu zukünftigen Updates für Microsoft Compliance Score (Preview), ein Feature im M365 Compliance Center, das das vereinfachen und Automatisieren von Risikobewertungen erleichtert.
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857760"
---
# <a name="microsoft-compliance-score-preview-updates"></a>Updates der Microsoft-Kompatibilitätsbewertung (Vorschau)

 Dieser Artikel enthält Details zu zukünftigen Updates für [Microsoft Compliance Score](compliance-score.md) und [Microsoft Compliance Manager](compliance-manager-overview.md). Erfahren Sie mehr über Ihre [Beziehung](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="improved-template-creation-and-update-processes"></a>Verbesserte Vorlagenerstellung und Aktualisierungsprozesse

Wir vereinfachen den Prozess des Importierens, Exportierens und Änderns von Vorlagen für Bewertungen. Die neue Benutzeroberfläche erleichtert es Ihnen, eigene Bewertungen in das Konformitäts Bewertungsergebnis einzubringen und Sie auf dem neuesten Stand zu halten.

### <a name="the-current-process"></a>Der aktuelle Prozess

Es gibt zwei Möglichkeiten, eine Vorlage im Compliance-Manager zu erstellen. Sie können eine vorhandene Vorlage kopieren oder Vorlagendaten aus einer Excel-Kalkulationstabelle in eine neue Vorlage importieren. Wählen Sie auf der Seite **Vorlagen** die Option **+ Vorlage hinzufügen** aus, um eine neue Vorlage zu erstellen, indem Sie einen Namen eingeben, Dimensionen auswählen und eine Excel-Datei mit einem bestimmten Format und Schema hochladen. Sie können auch das Feld **Kopie von einer vorhandenen Vorlage** überprüfen, eine zu kopierende Vorlage auswählen und die Dimensionen überprüfen, wie in der Abbildung unten dargestellt. Zum Anpassen Ihrer Vorlage ist ein [mehrstufiger Prozess](working-with-compliance-manager.md#templates) erforderlich, der mit dem Auswählen von **benutzerdefiniertem Steuerelement** nach dem Erstellen der Vorlage beginnt.

![Compliance Score-Dashboard](../media/compliance-score-template-update-old.png "Aktueller Vorlagen Kopiervorgang")

### <a name="whats-changing"></a>Was ändert sich

Wir erleichtern Ihnen die Erstellung neuer Vorlagen. In einem schrittweisen **Erweiterungs** Prozess können Sie einer vorhandenen Microsoft-Vorlage eine Kalkulationstabelle mit ihren Aktionen und Steuerelementen hinzufügen, um Ihre eigene angepasste Version zu erstellen. Aktivieren Sie im Fenster **Vorlagen** -Flyout das Kontrollkästchen **Erweiterung aus globaler Vorlage erstellen** (siehe Abbildung unten). Anschließend fügen Sie Anpassungen mithilfe eines neuen Excel-Formats hinzu, das weniger komplex ist als die aktuelle. Dieser neue Prozess ersetzt die aktuelle **Kopie aus einer vorhandenen Vorlage** und **Fügt benutzerdefinierte Steuerelementfunktionen hinzu** .

Jedes Mal, wenn die ursprüngliche Bewertung über den unten beschriebenen Versions Verwaltungsprozess aktualisiert wird, erbt Ihre angepasste Bewertung diese Updates und behält Ihre benutzerdefinierten Steuerelemente bei.

Außerdem vereinfachen wir das Ändern Ihrer vorhandenen Vorlagen. Sie können Ihre Vorlage exportieren, Änderungen in derselben Arbeitsmappe vornehmen und Sie dann mit gespeicherten Bearbeitungs speichern importieren.

![Compliance Score-Dashboard](../media/compliance-score-template-update-new.png "Neuer Vorlagen Erstellungsprozess")

## <a name="versioning-notice-and-control"></a>Versions Verwaltungs Hinweis und-Steuerelement

Ihre Organisation erhält aktualisierte Bewertungen in der nächsten Version von Compliance Score und Compliance-Manager, um Sie bei der Anpassung an Zertifizierungs-und Regel Updates zu unterstützen.

Jedes Mal, wenn ein Update für die Vorlage eines Assessments oder eine Verbesserungs Aktion verfügbar ist, werden Sie von einem Warnungssymbol benachrichtigt, dass ein Update bereit ist. Wenn Sie auf dieses Symbol klicken, wird das Update in einem Popupfenster erläutert, und Sie werden aufgefordert, diese zu akzeptieren. Unten sehen Sie ein Beispiel für die Versions Verwaltungs Warnung für eine Bewertung:

![Kompatibilitätsbewertung – Versions Verwaltungs Warnung](../media/compliance-score-assessment-version.png "Warnung zur Versionsupdate Bewertung")

Wenn Sie das Warnsymbol auswählen, wird ein Flyout-Bereich angezeigt, in dem das Update erläutert wird, und Sie werden aufgefordert, Folgendes anzunehmen

![Kompatibilitätsbewertung-Versions Verwaltungs Flyout](../media/compliance-score-assessment-version-accept.png "Bestätigungsbereich für die Bewertungs Aktualisierung")

## <a name="common-actions-will-synch-status-across-groups"></a>Häufige Aktionen synchronisieren den Status über Gruppen hinweg.

Wenn Ihre Organisation über mehrere Bewertungsgruppen verfügt, ändert sich das Verhalten von **technischen** Aktionen (also Aktionen, die ihre gesamte Organisation betreffen). Doppelte Aktionen in mehreren Gruppen werden in einer einzigen Aktion kombiniert. Diese einzelne Aktion enthält alle hochgeladenen Notizen und Beweise aus den doppelten Versionen. Durch diese Änderung verhalten sich technische Aktionen so, wie Sie es derzeit tun, wenn Sie derselben Gruppe angehören. Alle Änderungen, die an der Aktion in einer Gruppe oder Bewertung vorgenommen werden, werden nun in allen Instanzen wiedergegeben. Der **Implementierungsstatus**, die **Implementierungs-DAT**, der **Test Status**und das **Test Datum** spiegeln die neuesten Aktualisierungen wider.

## <a name="language-support"></a>Sprachunterstützung

Das Kompatibilitäts Ergebnis steht nun zusätzlich zu Englisch in den folgenden Sprachen zur Verfügung: Chinesisch (vereinfacht), Chinesisch (traditionell), Französisch, Deutsch, Italienisch, Japanisch, Koreanisch, Portugiesisch (Brasilien), Russisch und Spanisch.
