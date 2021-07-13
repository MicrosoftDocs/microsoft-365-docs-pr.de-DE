---
title: Erstellen und Verwalten von Richtlinien in Microsoft Privacy Management (Vorschau)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Richtlinien für den Umgang mit personenbezogenen Daten Ihrer Organisation in Microsoft 365 erstellen und verwalten, auf Warnungen reagieren und Probleme beheben.
ms.openlocfilehash: f9df027d01ffe4629654db1ddd006d141d57e387
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378572"
---
# <a name="create-and-manage-policies-in-privacy-management-preview"></a>Erstellen und Verwalten von Richtlinien in der Datenschutzverwaltung (Vorschau)

In diesem Artikel erfahren Sie, wie Sie **Richtlinien** für den Umgang mit personenbezogenen Daten erstellen und anpassen, **Benachrichtigungen** zu Richtlinienübereinstimmungen erhalten und **Probleme** beheben.

## <a name="purpose-of-policies"></a>Zweck von Richtlinien

Richtlinien ermöglichen es Ihnen, die Arten von Datenschutzrisiken zu definieren, nach denen Sie in den Microsoft 365 Daten Ihres Unternehmens suchen sollten, und die bevorzugten Ergebnisse für Szenarien festzulegen, in denen Übereinstimmungen gefunden werden. Ihre Organisation kann anhand der resultierenden Warnungen alle übereinstimmenden Daten überprüfen und Probleme beheben, alles aus der Datenschutzverwaltungslösung heraus.

Die Datenschutzverwaltung bietet Vorlagen, die Ihnen einen einfachen Einstieg in die Erstellung von Richtlinien bieten, und ermöglicht es Ihnen, Ihren Ansatz durch umfassende Anpassungsoptionen zu optimieren. Die wichtigsten Szenarien, die von den Vorlagen für die Datenschutzverwaltung abgedeckt werden, umfassen Folgendes:

- **Datenüberlastung:** Erkennt überlastete personenbezogene Daten und fordert Benutzer auf, sie zu schützen.
- **Datenübertragung:** Orte und hilft bei der Begrenzung der Übertragung personenbezogener Daten über Abteilungen oder regionale Grenzen hinweg.
- **Datenminimierung:** Hilft Benutzern, nicht verwendete personenbezogene Daten zu identifizieren und zu reduzieren.

Weitere Informationen zu den Funktionen der einzelnen Vorlagen finden Sie weiter unten.

## <a name="policy-types"></a>Richtlinientypen

### <a name="data-overexposure"></a>Datenüberlastung

Die Datenschutzverwaltung kann Ihnen helfen, Situationen zu erkennen und zu behandeln, in denen die von Ihnen gespeicherten Daten nicht ausreichend sicher sind. Wenn beispielsweise der Zugriff auf eine interne Website für eine zu breite Gruppe offen ist oder Ihre Berechtigungseinstellungen nicht auf dem neuesten Stand gehalten wurden, können personenbezogene Daten, die auf dieser Website gespeichert sind, anfällig für eine Verletzung sein. Sie können die Datenrichtlinienvorlage der Datenverwaltung verwenden, um Ihre Daten auszuwerten und Sie auf potenzielle Probleme hinzuweisen.

### <a name="data-transfer"></a>Datenübertragung

Das Übertragen von Daten über Abteilungen oder regionale Grenzen hinweg kann das Risiko einer Datenexposition erhöhen, z. B. wenn sie über unverschlüsselte E-Mails oder an nicht autorisierte Empfänger gesendet werden. Solche Aktionen können rechtliche Auswirkungen haben oder gegen bestehende Datenschutzpraktiken verstößt. Die Verwendung der Datenübertragungsvorlage zum Erstellen von Datenschutzverwaltungsrichtlinien kann solche Übertragungen erkennen und einschränken.

> [!NOTE]
> Während der öffentlichen Vorschau können bei einigen Mandanten, die Datenübertragungsrichtlinien ausführen, um Übertragungen über Regionen hinweg zu erkennen, Synchronisierungsprobleme auftreten, die sich auf die Sichtbarkeit von Richtlinienübereinstimmungen in Exchange- und Teams-Daten auswirken. Es wird empfohlen, sich bei der Vorschau dieses Richtlinientyps auf SharePoint und OneDrive Daten zu konzentrieren. Ein Update für dieses Problem wird im Herbst 2021 erwartet.

### <a name="data-minimization"></a>Datenminimierung

Im Laufe der Zeit können Unternehmen große Mengen personenbezogener Daten von Kunden oder Mitarbeitern erfassen. Dies umfasst manchmal Daten, die übermäßig benötigt wurden oder anderweitig nicht verwendet werden und reduziert werden sollten, um die Datenschutzrisiken im Zusammenhang mit diesen Informationen zu begrenzen. Die Datenminimierungsvorlage kann verwendet werden, um Risiken dieses Typs zu beheben.

## <a name="get-started-with-default-templates"></a>Erste Schritte mit Standardvorlagen

Die Datenschutzverwaltung hilft Ihnen, den Prozess der Datenauswertung zu starten, indem drei Richtlinien mit Standardeinstellungen erstellt werden, wobei die Vorlagen für die Datenminimierung, Datenüberlichtung und Datenübertragung verwendet werden. Diese Richtlinien sind standardmäßig aktiviert, lösen jedoch nicht automatisch Benachrichtigungs-E-Mails oder Wartungsaufforderungen aus. Nach der Ersteinrichtung können Sie mit dem Erstellen und Anpassen Ihrer eigenen Richtlinien fortfahren.

## <a name="create-a-privacy-management-policy"></a>Erstellen einer Datenschutzrichtlinie

Es gibt zwei Pfade zum Erstellen von Datenschutzverwaltungsrichtlinien. Die erste Option besteht darin, aus dem Satz vordefinierter Vorlagen auszuwählen. Sie können auch Ihre eigene Richtlinie anpassen, indem Sie eine dieser Vorlagen als Ausgangspunkt verwenden.

### <a name="create-a-policy-from-a-template"></a>Erstellen einer Richtlinie anhand einer Vorlage

Um sofort mit einer Richtlinie zu beginnen, wählen Sie einen der drei vordefinierten Richtlinientypen aus. Wenn Sie Details zu einem dieser Elemente überprüfen möchten, können Sie einstellungen anzeigen auswählen, um die spezifischen Eigenschaften der Richtlinie anzuzeigen, einschließlich Datentypen, Datenspeicherorten und bedingungen, die Richtlinienüberstimmungen auslösen.

Wenn Sie eine Richtlinie direkt aus einer Vorlage erstellen, werden viele Einstellungen automatisch für Sie ausgewählt. Dazu gehört auch das standardmäßige Aktivieren der Richtlinie. Wenn Sie eine Vorschau der Richtlinie in Aktion anzeigen möchten, bevor Sie sie vollständig aktivieren, suchen Sie sie nach der Erstellung in Ihrer Liste, bearbeiten Sie die Richtlinie, und schalten Sie sie in den Testmodus um. Weitere Informationen finden Sie unter [Testen Ihrer Richtlinie.](#test-your-policy)

### <a name="create-custom-policy"></a>Erstellen einer benutzerdefinierten Richtlinie

Um die Einstellungen einer Richtlinie präzise zu steuern, können Sie eine angepasste Richtlinie mithilfe einer der vorhandenen Vorlagen als Basislinie erstellen. Die Datenschutzverwaltung bietet einen Assistenten, der Sie durch diese Schritte führt.

Zu den anpassbaren Eigenschaften gehören:

- **Name und Typ:** Wählen Sie die Vorlage aus, auf der Die Richtlinie erstellt werden soll, benennen und beschreiben Sie Ihre Version.
- **Zu überwachende Daten:** Wählen Sie den Typ der personenbezogenen Daten aus, die Ihre Richtlinie überwacht. Wählen Sie entweder aus den verfügbaren Klassifizierungsgruppen oder aus der Liste der einzelnen Typen vertraulicher Informationen aus. Weitere Informationen finden Sie unter "Datenüberwachungsoptionen auswählen" weiter unten.
- **Benutzer:** Wählen Sie aus, ob diese Richtlinie für alle Benutzer oder für ausgewählte Benutzer gilt. Wenn Sie die zweite Option auswählen, können Sie in der bereitgestellten Liste bis zu 300 Benutzer Ihrer Wahl auswählen.
- **Speicherorte:** Wählen Sie die Speicherorte in Microsoft 365 aus, die ihre Richtlinie abdecken soll, z. B. die SharePoint oder Exchange Daten Ihrer Organisation.
- **Bedingungen:** Wählen Sie die relevanten Bedingungen für Ihren Richtlinientyp aus. Sie können beispielsweise angeben, nach welchen Arten von Übertragungen eine Datenübertragungsrichtlinie suchen soll oder wie kürzlich Daten für eine Datenminimierungsrichtlinie verwendet wurden.
- **Ergebnisse:** Definieren sie Ergebnisse, wenn eine Richtlinienübersprechung erkannt wird. Ihre Optionen hängen von dem Richtlinientyp ab, mit dem Sie beginnen. Mögliche Ergebnisse sind:
  - **E-Mail-Benachrichtigungen:** Mit dieser Einstellung können Sie Digest-E-Mail-Benachrichtigungen auslösen, einschließlich Links zu verwandten Schulungen. Weitere Informationen finden Sie unten unter "Festlegen von Benutzer-E-Mail-Benachrichtigungen".
  - **Teams:** Geben Sie Benutzern Tipps und Empfehlungen zu Teams Richtlinien sowie Links zu verwandten Schulungen. Diese Option ist für Datenübertragungsrichtlinien verfügbar.
- **Warnungen:** Festlegen der Häufigkeit von Warnungen an Administratoren, wenn eine Richtlinienüberstimmung erkannt wird. Zu den Optionen gehören keine Warnungen, Warnungen für jede Richtlinienüberstimmung oder Warnungen, wenn ein bestimmter Schwellenwert erreicht wird. Wenn Sie die Schwellenwertoption auswählen, legen Sie die gewünschten Parameter fest.
- **Modus:** Entscheiden Sie, ob eine Richtlinie zuerst im Testmodus ausgeführt oder sofort aktiviert werden soll. Weitere Informationen finden Sie unter "Testen Ihrer Richtlinie".
Wenn Sie alle Einstellungen im Assistenten durchlaufen haben, überprüfen Sie Ihre Einstellungen, nehmen Sie ggf. abschließende Änderungen vor, und speichern Sie Ihre Richtlinie.

#### <a name="choose-data-monitoring-options"></a>Auswählen von Datenüberwachungsoptionen

Beim Einrichten einer benutzerdefinierten Richtlinie werden Sie aufgefordert, auszuwählen, welche Datentypen Ihre Richtlinie überwachen soll. Folgende Optionen stehen zur Verfügung:

- **Klassifizierungsgruppen:** Eine durchsuchbare Liste von Datensätzen basierend auf wichtigen Datenschutzbestimmungen, z. B. DSGVO oder HIPAA. Zeigen Sie Details zu einer beliebigen Gruppe an, um zu sehen, welche Arten von vertraulichen Informationen behandelt werden. Wählen Sie eine oder mehrere dieser Gruppen aus, um sie wie besehen zu verwenden. Die derzeit verfügbaren Gruppen sind wie folgt:
  - Australia Health Records Act (HRIP Act) Enhanced
  - Australia Privacy Act Enhanced
  - (EU) Datenschutz-Grundverordnung (DSGVO) verbessert
  - Daten zu personenbezogenen Informationen (PII) in Japan verbessert
  - Japan – Erweiterter Schutz personenbezogener Informationen
  - U.S. Gramm-Leach-Bliley Act (GLBA) Enhanced
  - U.S. Health Insurance Act (HIPAA) Enhanced
  - U.S. Mof Act Enhanced
  - Daten zu personenbezogenen Informationen (PII) in den USA verbessert
  - U.S. State Breach Notification Laws Enhanced
- **Einzelne Typen vertraulicher Informationen:** Indem Sie bestimmte typen vertraulicher Informationen selbst auswählen, z. B. Sozialversicherungsnummern oder Führerscheininformationen, können Sie Ihre eigene Gruppe oder Gruppen von Daten anpassen, nach denen Sie suchen möchten. Mit diesem Assistenten können Sie aus der vollständigen Liste der Typen vertraulicher Informationen innerhalb der Datenschutzverwaltung auswählen. Jeder Informationstyp hat seine eigenen Eigenschaften. Verwenden Sie die Infoschaltfläche neben einer dieser Schaltflächen, um Details und Hinweise zu den empfohlenen Einstellungen zu erhalten. Wenn Sie mehrere Gruppen erstellen, können Sie mit dem Assistenten boolesche Operatoren anwenden, um diese zu verknüpfen und deren Reihenfolge der Vorgänge zu definieren.

Wenn Sie vordefinierte Klassifizierungsgruppen verwenden, können Sie nicht auch einzelne Typen auswählen oder eigene Gruppen erstellen. Wählen Sie aus Gründen der Flexibilität individuelle Typen vertraulicher Informationen aus. Um die gängigsten Standards zu verwenden, wählen Sie aus den Klassifizierungsgruppen aus.

#### <a name="test-your-policy"></a>Testen Der Richtlinie

Wenn Sie eine neue Richtlinie bewerten möchten, bevor Sie sie vollständig aktivieren, legen Sie die Richtlinie auf den Testmodus fest. Im Testmodus können Sie nach Übereinstimmungen aus den letzten 30 Tagen suchen, das Verhalten der Richtlinie messen und die Art der generierten Warnungen überprüfen. Es wird empfohlen, mindestens fünf Tage lang Testrichtlinien auszuführen, um repräsentative Ergebnisse zu erhalten. Während der Testphase haben Sie die Möglichkeit, die Einstellungen der Richtlinie zu bearbeiten und anzupassen. Nachdem Sie erkenntnisse aus der Ausführung des Tests gewonnen haben, können Sie mit dem Aktivieren der Richtlinie fortfahren. Während eine Richtlinie im Testmodus ausgeführt wird, werden keine Benutzerbenachrichtigungs-E-Mails zugestellt.

#### <a name="set-user-email-notifications"></a>Festlegen von Benutzer-E-Mail-Benachrichtigungen

Mit E-Mail-Benachrichtigungen erhalten Benutzer direkte Benachrichtigungen zu Richtlinienübereinstimmungen und wichtigen Aufgaben, die ausgeführt werden müssen. Die Empfänger erhalten E-Mail-Digests, in denen die zu überprüfenden Daten und mögliche Aktionen zusammengefasst werden, z. B. das Privatemachen von Dokumenten, das Beibehalten der Dateien in einer Datei, das Melden falsch positiver Übereinstimmungen und das Hinzufügen von Notizen für zukünftige Verweise. Diese E-Mails enthalten auch Links für Schulungsempfänger zum Umgang mit diesen Fällen. Das Bereitstellen dieser Links ist beim anfänglichen Einrichten von Benachrichtigungen erforderlich und sollte auf Ihre eigene interne Dokumentation zu Prozessen und bewährten Methoden verweisen.

Benachrichtigungen können für einzelne Richtlinien während der Erstellung einer benutzerdefinierten Richtlinie oder beim Bearbeiten einer Richtlinie aktiviert werden. Verwenden Sie den Abschnitt "Ergebnisse", um zu definieren, was passiert, wenn eine Richtlinienübersprechung erkannt wird, einschließlich der Option zum Aktivieren dieser Benachrichtigungen, und legen Sie fest, wie oft diese Digests übermittelt werden sollen.

Die E-Mail-Benachrichtigungsfunktion wird auf globaler Ebene innerhalb Einstellungen gesteuert. Diese Anwendung ist standardmäßig aktiviert. Wenn Sie diese Einstellung deaktivieren, werden alle E-Mails beendet, auch wenn bestimmte Benachrichtigungen auf einer einzelnen Richtlinienebene konfiguriert wurden. Weitere Informationen finden Sie unter Konfigurieren von Einstellungen unter [Erste Schritte mit der Datenschutzverwaltung.](privacy-management-setup.md#configure-settings)

## <a name="view-policy-details"></a>Anzeigen von Richtliniendetails

Nachdem Ihre Richtlinie erstellt wurde, wählen Sie sie auf der Hauptseite **"Richtlinien" aus,** um die vollständige Übersicht anzuzeigen. Die Seite "Richtliniendetails" bietet Einblicke in Ihre Daten, ermöglicht es Ihnen, Inhalte zu bestimmten Richtlinienüberstimmungen anzuzeigen und Sie bei den nächsten Schritten zu beraten. Wenn Ihre Richtlinie im Testmodus ausgeführt wird, können Sie die Richtlinie auch auf dieser Seite aktivieren, wenn die Tests abgeschlossen sind.

Nachdem Ihre Richtlinie aktiv ist, können Sie die Seite mit den Richtliniendetails weiterhin überprüfen, um fortlaufende Erkenntnisse zu Problembereichen, Warnungsschweregrad und -trends sowie zu ergriffenen Korrekturmaßnahmen zu erhalten.

## <a name="resolve-policy-alerts-and-issues"></a>Beheben von Richtlinienwarnungen und Problemen

Nachdem Ihre Richtlinien aktiviert wurden, werden Sie von der Datenschutzverwaltung auf wichtige Ermittlungen aufmerksam gemacht, indem Sie über Richtlinienübereinstimmungen informiert werden, deren Schweregrad benotet wird und Ihnen die Möglichkeit gegeben wird, Maßnahmen zu ergreifen, indem Sie Probleme erstellen und beheben.

Die Übersichtsseite des Datenschutzmanagements bietet eine Übersicht über diese Ergebnisse mit dynamischen Updates zu wichtigen Bereichen, wie z. B. den Richtlinien mit den meisten Übereinstimmungen und Ihren derzeit aktiven Richtlinienwarnungen. Sie können auch auf Details zu Ihren Warnungen und Problemen über die Hauptseite "Richtlinien" zugreifen.

### <a name="alerts"></a>Warnungen

Um Ihre aktiven Warnungen zu bewerten und anzugeben, welche Probleme nachbereiten müssen, greifen Sie auf die Seite **"Warnungen"** zu. Es enthält eine filterbare Liste von Warnungen, die von Ihren Richtlinien generiert werden, die Sie einzeln überprüfen können, um die Umstände zu ermitteln, unter denen sie ausgelöst wurden.

Wenn Sie eine Warnung auswählen, wird ein Flyover-Bereich mit zusätzlichen Details geöffnet, z. B. der Richtlinientyp, die Anzahl der übereinstimmenden Elemente und der Schweregrad, der von den Richtlinieneinstellungen als nicht erfüllt eingestuft wird. Auf der Registerkarte **"Inhalt"** können Sie die Dateien überprüfen, die an dieser Warnung beteiligt sind. Diese Informationen können zusätzliche Einblicke in das spezifische Ereignis liefern, das die Warnung ausgelöst hat, wo sich die Dateien befinden und welche Arten von personenbezogenen Daten beteiligt sind. Trigger für Warnungen werden durch die spezifischen Bedingungen der einzelnen Richtlinien bestimmt. Beispielsweise kann eine Warnung für eine Datenübertragungsrichtlinie ausgelöst werden, wenn die Datenverwaltung eine Übertragung zwischen den angegebenen Abteilungen oder Regionen der Richtlinie erkennt.

Nachdem Sie eine Warnung in der Liste bewertet haben, können Sie die **Problemaktion** erstellen verwenden, um weitere Untersuchungen und Maßnahmen zu ergreifen. Sie werden aufgefordert, das Problem zu benennen und alle relevanten Kommentare für den Kontext hinzuzufügen. Sie können Warnungen hier auch schließen, wenn keine Nachverfolgung erforderlich ist.

### <a name="issues"></a>Probleme

Wie im Abschnitt "Warnungen" beschrieben, werden Beim Bewerten von Warnungen zu Richtlinienübersprechungen Probleme erstellt. Um die angegebenen Bedenken zu verfolgen und zu beheben, besuchen Sie die Seite "Probleme". Von hier aus können Sie einzelne Probleme überprüfen, die anstiftenden Bedingungen untersuchen, die Daten überprüfen und die erforderlichen Schritte ausführen, um den Fall zu schließen.

Diese Seite enthält eine Liste aller offenen Probleme. Probleme werden nach Name aufgelistet und nach Schweregrad sortiert, damit Sie Fälle priorisieren können, einschließlich der Kategorien "Hoch", "Mittel" und "Niedrig" sowie "Nicht zugewiesen". Wählen Sie ein Problem in der Liste aus, um dessen Inhalt zu überprüfen, und ergreifen Sie Maßnahmen, um es zu beheben. Sie können nicht zugewiesenen Problemen während der Überprüfung eine Bewertung des Schweregrads zuweisen.

#### <a name="issue-overview"></a>Problemübersicht

Problemdetailseiten helfen Ihnen dabei, die identifizierten Datenschutzrisiken zu behandeln und die angegebenen Dateien ordnungsgemäß zu behandeln. Auf der Registerkarte **"Übersicht"** sehen Sie den aktuellen Schritt, der den Status des Problems und die nächsten empfohlenen Aktionen angibt. Sie können auch wichtige Informationen über den betreffenden Inhalt, die zugeordnete Richtlinie, Details zur Warnung und die Zeitachse überprüfen.

Nachfolgende Registerkarten enthalten weitere Details zu den zugehörigen Warnungen und Inhalten sowie alle Notizen von anderen Personen in Ihrem Team, die an dem Problem arbeiten. Sie können die Liste der aktiven Mitwirkenden über die Registerkarte **"Mitarbeiter"** verwalten.

#### <a name="share-the-issue"></a>Freigeben des Problems

Wenn Sie Personen als Mitarbeiter hinzufügen, können Sie das Problem mit zusätzlichen Mitgliedern Ihres Unternehmens über einen sicheren Microsoft Teams Kanal, eine Unternehmens-E-Mail oder durch direktes Freigeben eines Links zur Seite des Problems in der Datenschutzverwaltung teilen. Diese Optionen sind unter der Schaltfläche **"Freigeben"** verfügbar. Bei der Freigabe über Teams werden Sie aufgefordert, aus den verfügbaren Teams in Ihrer Organisation auszuwählen, den spezifischen Kanal auszuwählen und eine Nachricht zu dem Problem zu hinterlassen, das für den angegebenen Kanal freigegeben wird.

#### <a name="review-content-and-remediate"></a>Überprüfen von Inhalten und Korrigieren

Wenn Sie den mit einem Problem verbundenen Inhalt überprüfen möchten, wählen Sie die **Aktion "Inhalt überprüfen"** aus, wenn Sie dazu aufgefordert werden, oder öffnen Sie die Registerkarte "Inhalt". Wählen Sie eine beliebige Datei in der Liste aus, um sie vollständig anzuzeigen. Hier sehen Sie Details zu der Datei, zu allen aufgezeichneten Aktivitäten und zum Wartungsverlauf, wenn vorherige Schritte zum Verwalten dieser Datei ausgeführt wurden.

Verwenden Sie die Schaltfläche **"Korrigieren",** um ihre eigenen Entscheidungen zur Datenverarbeitung für diese Inhalte zu treffen. Wenn Sie die Schaltfläche auswählen, können Sie eine oder mehrere Korrekturaktionen auswählen. Die folgenden Optionen stehen zur Verfügung:

**Alle Richtlinien**

- **Benachrichtigen:** Benachrichtigen Sie den Inhaltsbesitzer über das erkannte Problem.
- Anwenden einer **Aufbewahrungsbezeichnung:** Fügen Sie eine Bezeichnung zur Datenaufbewahrung für dieses Element hinzu. 
- Anwenden einer **Vertraulichkeitsbezeichnung:** Fügen Sie eine Bezeichnung zur Vertraulichkeit der Daten dieses Elements hinzu.
- **Als keine Übereinstimmung kennzeichnen:** Identifizieren Sie ein Suchergebnis als falsch positives Ergebnis, um das Inhaltselement aus der Überlegung zu entfernen.

**Datenminimierung**

- **Wiederverwenden/Löschen:** Verwenden Sie diese Option zum vorläufigen Löschen der Daten. Inhalte werden in den Ordner "Gelöschte Elemente" oder "Wiederverwenden" (Exchange, SharePoint, OneDrive) verschoben oder mit einer Option zum Wiederherstellen (Teams Nachrichten) gelöscht. Der Löschvorgang kann innerhalb eines festgelegten Zeitraums rückgängig gemacht werden, abhängig von den Einstellungen des Diensts.

**Datenüberlastung und Datenübertragung**

- **Freigabe** aufheben: Beenden sie die Freigabe eines Links zu diesem Inhaltselement.

Bei jeder Option werden Sie aufgefordert, Kommentare und alle anderen erforderlichen unterstützenden Informationen für den Inhaltsbesitzer zu hinterlassen, bevor Sie Ihre Auswahl bestätigen.

Nachdem alle Korrekturschritte ausgeführt wurden und das Problem geschlossen werden kann, verwenden Sie die Schaltfläche "Beheben", und fügen Sie Ihre endgültigen Kommentare hinzu, bevor Sie es übermitteln.

## <a name="delete-a-policy"></a>Löschen einer Richtlinie

Wenn Sie eine vorhandene Datenschutzrichtlinie entfernen müssen, suchen Sie sie in der Liste auf der Seite "Richtlinien", wählen Sie das Aktionsmenü (vertikale Auslassungspunkte) aus, und wählen Sie die Aktion "Richtlinie löschen" aus. Sie werden aufgefordert, Ihre Auswahl zu bestätigen, bevor der Löschvorgang abgeschlossen ist und die Richtlinie endgültig entfernt wird. Das Löschen einer Richtlinie wirkt sich nicht auf Dateien aus, die zuvor von der Richtlinie ausgewertet wurden, und Probleme und Warnungen, die von der Richtlinie generiert wurden, bleiben erhalten.
