---
title: Anmerkungen zur Microsoft Compliance-Manager-Version
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
description: Der Microsoft Compliance-Manager ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft-Dienst Vertrauensstellungs Portal. Mit dem Compliance-Manager können Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services nachverfolgen, zuweisen und überprüfen.
ms.openlocfilehash: 73fa3ac2ca15d922a74e1d3ceef6cc74a3bdedca
ms.sourcegitcommit: f70f75b9dd163c00a3c6bc4b9f9b055e90c50367
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "43790568"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a>Anmerkungen zur Microsoft Compliance-Manager-Version (Vorschau)

Die Public Preview of Compliance Manager bietet Ihnen frühzeitigen Zugriff auf bevorstehende Funktionen und Updates. Diese Seite enthält Updates zu neuen Features, verbesserten Funktionen und bekannten Problemen mit der aktuellen Version.

Sie können das [Compliance-Manager-](https://servicetrust.microsoft.com/ComplianceManager) Tool im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com) zum Nachverfolgen, zuweisen und Überprüfen von behördlichen Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services verwenden.

## <a name="improved-template-creation-and-update-process"></a>Verbesserter Vorlagen Erstellungs-und Aktualisierungsprozess

Wir haben den Prozess zum Importieren, exportieren und Ändern von Vorlagen für Bewertungen aktualisiert. Dank der neuen, vereinfachten Benutzeroberfläche können Sie Ihre eigenen Bewertungen in Ihren Workflow einbringen und diese auf dem neuesten Stand halten.

### <a name="the-old-process"></a>Der alte Prozess

Es gab zwei Möglichkeiten, eine Vorlage im Compliance-Manager zu erstellen. Sie können eine vorhandene Vorlage kopieren oder Vorlagendaten aus einer Excel-Kalkulationstabelle in eine neue Vorlage importieren. Wählen Sie auf der Seite **Vorlagen** die Option **+ Vorlage hinzufügen** aus, um eine neue Vorlage zu erstellen, indem Sie einen Namen eingeben, Dimensionen auswählen und eine Excel-Datei mit einem bestimmten Format und Schema hochladen. Sie können auch das Feld **Kopie von einer vorhandenen Vorlage** überprüfen, eine zu kopierende Vorlage auswählen und die Dimensionen überprüfen. Entwurfs Anpassung die Vorlage erforderte einen mehrstufigen Prozess, der mit dem Auswählen von **benutzerdefiniertes Steuerelement hinzufügen** nach dem Erstellen der Vorlage begann.

### <a name="the-new-process"></a>Der neue Prozess

Wir haben es Ihnen erleichtert, neue Vorlagen zu erstellen. In einem schrittweisen **Erweiterungs** Prozess können Sie einer vorhandenen Microsoft-Vorlage eine Kalkulationstabelle mit ihren Aktionen und Steuerelementen hinzufügen, um Ihre eigene angepasste Version zu erstellen. Wählen Sie auf der Seite **Vorlagen** im Compliance-Manager die Option **+ Vorlage hinzufügen**aus. Aktivieren Sie im Fenster **Vorlagen** -Flyout das Kontrollkästchen **Erweiterung aus globaler Vorlage erstellen** . Sie können Anpassungen mit einem neuen Excel-Format hinzufügen, das weniger komplex ist als das vorherige. Dieser neue Prozess ersetzt die frühere **Kopie aus einer vorhandenen Vorlage** und **Fügt benutzerdefinierte Steuerelementfunktionen hinzu** .

Jedes Mal, wenn die ursprüngliche Bewertung über den unten beschriebenen Versions Verwaltungsprozess aktualisiert wird, erbt Ihre angepasste Bewertung diese Updates und behält Ihre benutzerdefinierten Steuerelemente bei.

Es ist auch einfacher, eigene vorhandene Vorlagen zu ändern. Sie können Ihre Vorlage exportieren, Änderungen in derselben Arbeitsmappe vornehmen und Sie dann mit gespeicherten Bearbeitungs speichern importieren.

Zeigen Sie detaillierte Anweisungen zum [Erstellen von Vorlagen](working-with-compliance-manager.md#templates) mit diesem neuen Prozess an.

## <a name="versioning-notice-and-control"></a>Versions Verwaltungs Hinweis und-Steuerelement

Ihre Organisation hat in der April 2020-Version von Compliance-Manager aktualisierte Bewertungen erhalten, um Sie bei der Anpassung an Zertifizierungs-und Regel Updates zu unterstützen. Wir bieten Ihnen eine klare Möglichkeit, alle zukünftigen Updates mithilfe von **Benachrichtigungen zur Versionsverwaltung**zu verstehen und zu akzeptieren.

Wenn ein Update für die Vorlage eines Assessments oder eine Verbesserungs Aktion verfügbar ist, werden Sie in einem Warnungssymbol darüber informiert, dass ein Update bereit ist. Wenn Sie auf dieses Symbol klicken, wird das Update in einem Popupfenster erläutert, und Sie werden aufgefordert, diese zu akzeptieren. Wenn Sie das Warnungssymbol auswählen, wird ein Flyout-Bereich angezeigt, in dem das Update erklärt wird, und Sie werden aufgefordert, zu akzeptieren. Erfahren Sie mehr über [das akzeptieren von Updates für Bewertungen](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).

## <a name="common-actions-will-synch-status-across-groups"></a>Häufige Aktionen synchronisieren den Status über Gruppen hinweg.

Wenn Ihre Organisation über mehrere Bewertungsgruppen verfügt, hat sich das Verhalten von **technischen** Aktionen (also Aktionen, die sich auf Ihre gesamte Organisation auswirken) geändert. Doppelte Aktionen in mehreren Gruppen wurden zu einer einzigen Aktion zusammengefasst. Diese einzelne Aktion enthält alle hochgeladenen Notizen und Beweise aus den doppelten Versionen. Durch diese Änderung verhalten sich technische Aktionen nun so, wie Sie es in der gleichen Gruppe getan haben. Alle Änderungen, die an der Aktion in einer Gruppe oder Bewertung vorgenommen werden, werden nun in allen Instanzen wiedergegeben. Der **Implementierungsstatus**, das **Implementierungsdatum**, der **Test Status**und das **Test Datum** spiegeln die neuesten Aktualisierungen wider.

## <a name="language-support"></a>Sprachunterstützung

Compliance-Manager steht nun zusätzlich zu Englisch in den folgenden Sprachen zur Verfügung: Chinesisch (vereinfacht), Chinesisch (traditionell), Französisch, Deutsch, Italienisch, Japanisch, Koreanisch, Portugiesisch (Brasilien), Russisch und Spanisch.

## <a name="known-issues-in-compliance-manager-preview"></a>Bekannte Probleme im Compliance-Manager (Vorschau)

Im folgenden Abschnitt werden bekannte Probleme in der aktuellen Version von Compliance-Manager behandelt.

### <a name="dimension-values"></a>Dimensionswerte

Infolge der Datenmigration in der Version April 2020 werden einigen Organisationen in ihren Bewertungen und Vorlagen möglicherweise ein **Produkt** oder **Zertifizierungs** Wert "Custom" angezeigt. Dieser Wert wurde automatisch eingefügt, wenn die Felder **Produkt** oder **Zertifizierung** leer waren, und es gibt keine Auswirkungen auf Daten Workflows.

### <a name="compliance-score"></a>Compliancebewertung

- Bei Aktionselementen, die als " **nicht im Bereich**" gekennzeichnet sind, wird das dem Aktionselement zugewiesene Ergebnis nicht aus der Berechnung der Konformitätsbewertung ausgeschlossen. Aktionselemente, die **nicht im Bereich** markiert sind, verbessern nicht Ihre Konformitätsbewertung.

### <a name="secure-score"></a>Sicherheitsbewertung

- Sichere Ergebnis Ergebnisse sind für einige Aktionselemente in bestimmten Microsoft 365-und Office 365-Abonnements nicht verfügbar. In diesen Fällen konnte das sichere Ergebnis Ergebnis **nicht erkannt werden** .
- Manchmal werden sichere Ergebnis Ergebnisse für die entsprechenden Richtlinien und Aktionselemente nicht abgeschlossen zurückgegeben.
- Für neue Mandanten werden sichere Bewertungs Aktualisierungen für alle Aktionen automatisch aktiviert. Der globale Administrator kann die Option für die kontinuierliche Aktualisierung sicherer Bewertungen auf aus festlegen, wodurch Updates für alle Aktionen deaktiviert werden.
  - **Hinweis**: Wenn Organisationen zunächst Microsoft 365 oder Office 365 bereitstellen, dauert es ungefähr sieben Tage, bis Secure Score Daten vollständig erfasst und Sie in Ihrer Partitur berücksichtigt. Während dieser Zeit wird durch das Festlegen der Option für die kontinuierliche Aktualisierung sicherer Bewertungen auf **aus** und das manuelle Festlegen einer Aktion auf **implementiert** festgesetzt, dass diese Aktion zur Partitur zählt. Nach den anfänglichen sieben Tagen wird durch das Drehen von Secure Score Continuous Update wieder eine kontinuierliche Überwachung von diesem Punkt aus aktiviert.
- Wenn Secure Score Updates aktiviert sind, werden Aktionen aktiv durch Secure Score überwacht, obwohl das Test Datum der Aktion nicht aktualisiert wird, um die Überwachung widerzuspiegeln.
- Wenn neue Bewertungen erstellt werden, enthalten Scores automatisch von Microsoft verwaltete Steuerpunkte und die Integration sicherer Bewertungen.
- Alle Aktionen, die nicht von der Integration von Secure Score unterstützt werden, können manuell implementiert werden. Durch eine manuelle Implementierung wird die Bewertung für die Gruppe dieser Aktion berücksichtigt.

### <a name="export"></a>Exportieren

- Der Vorlagenexport in JSON schlägt fehl, wenn der Vorlagenstatus auf " **importiert** " oder " **Ausstehende Genehmigung**" festgelegt ist.

### <a name="supported-browsers"></a>Unterstützte Browser

- Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.
- Es gibt möglicherweise Fälle, in denen aktualisierte Daten erst angezeigt werden, wenn Ihr Browser aktualisiert wurde.
- Die Preview-Version von Microsoft Edge wird nicht unterstützt, aber es sind keine bekannten Probleme aufgetreten.
- Internet Explorer wird nicht unterstützt.

### <a name="session-timeout"></a>Sitzungstimeout

- Wenn ein Timeout für eine Sitzung auftritt, wird möglicherweise der Fehler "etwas ging falsch" angezeigt. Um zu beheben, gehen Sie zu [Compliance-Manager](https://servicetrust.microsoft.com/ComplianceManager) , und melden Sie sich erneut an.
