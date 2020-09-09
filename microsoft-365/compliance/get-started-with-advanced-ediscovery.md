---
title: Erste Schritte mit Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel wird beschrieben, wie Sie mit der Verwendung von Advanced eDiscovery in Microsoft 365 beginnen. Nachdem Sie einige kurze Schritte ausgeführt haben, ist das erweiterte eDiscovery-Tooleinsatz fähig. Der erste Schritt besteht darin, einen Fall zu erstellen und dann erweiterte eDiscovery-Funktionen und-Funktionen zu verwenden.
ms.openlocfilehash: 47647c2f4f944812fa066be272a39ded77099c75
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405419"
---
# <a name="get-started-with-advanced-ediscovery"></a>Erste Schritte mit Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 bietet einen End-to-End-Workflow zum aufbewahren, sammeln, überprüfen, analysieren und Exportieren von Daten, die auf interne und externe Untersuchungen in Ihrer Organisation reagieren. Für die Bereitstellung von Advanced eDiscovery ist nichts erforderlich, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und eDiscovery-Manager ausführen müssen, bevor Ihre Organisation mit der Erstellung und Verwendung von erweiterten eDiscovery-Fällen für die Verwaltung ihrer Untersuchungen beginnen kann.

In diesem Artikel werden die erforderlichen Schritte zum Einrichten von Advanced eDiscovery erläutert. Dies umfasst die Sicherstellung der erforderlichen Lizenzierung für den Zugriff auf Erweiterte eDiscovery sowie das Hinzufügen von Depotstellen zu Fällen sowie das Zuweisen von Berechtigungen für Ihr rechts-und Ermittlungsteam, damit Sie auf Anfragen zugreifen und diese verwalten können. Dieser Artikel bietet außerdem eine allgemeine Übersicht über die Verwendung von Fällen zum Verwalten des erweiterten eDiscovery-Workflows für eine rechtliche Untersuchung.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Schritt 1: überprüfen und zuweisen geeigneter Lizenzen

Für die Lizenzierung für Advanced eDiscovery ist das entsprechende Organisations Abonnement und die Lizenzierung pro Benutzer erforderlich.

- **Organisations Abonnement:** Um auf Advanced eDiscovery im Microsoft 365 Compliance Center oder im Security & Compliance Center zuzugreifen, muss Ihre Organisation über eine der folgenden Funktionen verfügen:

  - Microsoft 365 E5- oder Office 365 E5-Abonnement
  
  - Microsoft 365 E3-Abonnement mit E5-Compliance-Add-On

  - Microsoft 365 E3-Abonnement mit E5 eDiscovery und Überwachungs-Add-on

  Wenn Sie keinen vorhandenen Microsoft 365 E5-Plan haben und Advanced eDiscovery testen möchten, können Sie Microsoft 365 zu Ihrem vorhandenen Abonnement [Hinzufügen](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) oder [sich für eine Testversion](https://www.microsoft.com/microsoft-365/enterprise) von Microsoft 365 E5 registrieren.

- **Lizenzierung pro Benutzer:** Wenn Sie einen Benutzer als depotverwalter in einem eDiscovery-vorab Fall hinzufügen möchten, muss diesem Benutzer je nach Ihrem Organisations Abonnement eine der folgenden Lizenzen zugewiesen sein:

  - Microsoft 365: Benutzern muss eine Microsoft 365 E5-Lizenz, eine E5-Konformitäts-Add-on-Lizenz oder eine E5-eDiscovery-und-Überwachungs-Add-on-Lizenz zugewiesen werden.

  - Office 365: Benutzern muss eine Office 365 E5-Lizenz zugewiesen sein.

   Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Benutzer benötigen nur eine E5-Lizenz (oder die entsprechende Add-on-Lizenz), die als Verwalter einem erweiterten eDiscovery-Fall hinzugefügt werden soll. IT-Administratoren, eDiscovery-Manager, Juristen, Gehilfen oder Ermittler, die Advanced eDiscovery zum Verwalten von Fällen und Überprüfen von Falldaten verwenden, benötigen keine E5-oder Add-on-Lizenz.

## <a name="step-2-assign-ediscovery-permissions"></a>Schritt 2: Zuweisen von eDiscovery-Berechtigungen

Um auf Advanced eDiscovery zuzugreifen oder als Mitglied eines erweiterten eDiscovery-Falls hinzugefügt zu werden, müssen einem Benutzer die entsprechenden Berechtigungen zugewiesen werden. Insbesondere muss ein Benutzer als Mitglied der eDiscovery-Manager-Rollengruppe im Security & Compliance Center hinzugefügt werden. Mitglieder dieser Rollengruppe können erweiterte eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, Aufbewahrungen und inhaltsspeicherorte in der Warteschleife platzieren, Benachrichtigungen für legale Aufbewahrungen verwalten, Suchvorgänge in einem Fall erstellen und bearbeiten, Suchergebnisse zu einem Überprüfungs hinzufügen, Daten in einem Überprüfungs Satzes analysieren und aus einem erweiterten eDiscovery-Fall exportieren und herunterladen.

Führen Sie die folgenden Schritte aus, um Benutzer zur eDiscovery-Manager-Rollengruppe hinzuzufügen:

1. Wechseln Sie zu, [https://protection.office.com/permissions](https://protection.office.com/permissions) und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wählen Sie auf der Seite **Berechtigungen** die Rollengruppe **eDiscovery-Manager** aus.

3. Klicken Sie auf der Seite eDiscovery-Manager-Flyout neben dem Abschnitt **eDiscovery-Manager** auf **Bearbeiten** .

4. Klicken Sie auf der Seite **eDiscovery-Manager auswählen** im Assistenten zum Bearbeiten der Rollengruppe auf **Ermittlungs-Manager auswählen**.

5. Klicken Sie auf **Hinzufügen** , und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Klicken Sie auf **Hinzufügen** , um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **Fertig**.

7. Klicken Sie auf **Speichern** , um die Benutzer der Rollengruppe hinzuzufügen, und klicken Sie dann auf **Schließen** , um den Schritt abzuschließen.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Weitere Informationen zur eDiscovery-Manager-Rollengruppe

Es gibt zwei Untergruppen in der Rollengruppe "eDiscovery-Manager". Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

- **eDiscovery-Manager:** Kann die erweiterten eDiscovery-Fälle anzeigen und verwalten, in denen Sie erstellt werden oder deren Mitglied Sie sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falls hinzufügt, kann der zweite eDiscovery-Manager den Fall nicht auf der Seite "Advanced eDiscovery" im Compliance Center anzeigen oder öffnen. Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe eDiscovery-Manager hinzugefügt werden.

- **eDiscovery-Administrator:** Kann alle Fall Verwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Außerdem kann ein eDiscovery-Administrator Folgendes:

  - Anzeigen aller Fälle, die auf der Seite „ Advanced eDiscovery“ aufgeführt sind.
  
  - Verwalten aller Fälle in der Organisation, nachdem er sich selbst als Fallmitglied hinzugefügt hat.

  - Zugreifen auf und Exportieren von Falldaten für jeden Fall in der Organisation.

  Aufgrund des breit gefächerten Zugriffs sollte eine Organisation nur über wenige Administratoren verfügen, die Mitglieder der Untergruppe der eDiscovery-Administratoren sind.

Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung der einzelnen Rollen, die der Rollengruppe "eDiscovery-Manager" zugewiesen sind, finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Schritt 3: Konfigurieren globaler Einstellungen für Advanced eDiscovery

Der letzte Schritt, der abgeschlossen werden muss, bevor Personen in Ihrer Organisation mit dem Erstellen und Verwenden von Fällen beginnen, besteht darin, globale Einstellungen zu konfigurieren, die für alle Fälle in Ihrer Organisation gelten. Zu diesem Zeitpunkt ist die einzige globale Einstellung die *Berechtigung "Anwalts Clienterkennung* " (weitere globale Einstellungen werden in der Zukunft verfügbar sein). Mit dieser Einstellung kann das Anwalts-Client-Berechtigungsmodell ausgeführt werden, wenn Sie Daten in einem Überprüfungs Satzes analysieren. Das Modell verwendet Maschinelles Lernen, um die Wahrscheinlichkeit zu ermitteln, dass ein Dokumentinhalte enthält, die Natur rechtlich zulässig sind. Außerdem werden die Teilnehmer von Dokumenten mit einer anwaltsliste verglichen (die Sie beim Einrichten des Modells übermitteln), um festzustellen, ob ein Dokument mindestens einen Teilnehmer besitzt, der ein Anwalt ist.

Weitere Informationen zum Einrichten und Verwenden des Erkennungs Modells für das Anwalts Client-Recht finden Sie unter [Einrichten der Anwalts-Client-Berechtigungs Erkennung in Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Dies ist ein optionaler Schritt, den Sie jederzeit ausführen können. Wenn Sie das Ermittlungs Modell für das Attorney-Client-Recht nicht implementieren, können Sie keine erweiterten eDiscovery-Fälle erstellen und verwenden.

## <a name="step-4-create-an-advanced-ediscovery-case"></a>Schritt 4: Erstellen eines erweiterten eDiscovery-Falls

Der nächste Schritt besteht darin, einen Fall zu erstellen und mit Advanced eDiscovery zu beginnen. Führen Sie die folgenden Schritte aus, um einen Fall zu erstellen und Mitglieder hinzuzufügen. Der Benutzer, der den Fall erstellt, wird automatisch als Mitglied hinzugefügt.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und melden Sie sich mit den Anmeldeinformationen für das Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden. Mitglieder der Rollengruppe "Organisationsverwaltung" können auch erweiterte eDiscovery-Fälle erstellen.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

3. Klicken Sie auf der Seite **Erweiterte eDiscovery** auf die Registerkarte **Fälle** , und klicken Sie dann auf **Fall erstellen**.

4. Geben Sie auf der **neuen eDiscovery-Fall** -Flyout-Seite den Fall einen Namen (erforderlich) ein, und geben Sie dann eine optionale Fallnummer und eine Beschreibung ein. Der Case-Name muss in Ihrer Organisation eindeutig sein.

5. Klicken Sie auf **Speichern** , um die Anfrage zu erstellen.

   Der neue Fall wird erstellt, und die Registerkarte **Einstellungen** im neuen Fall wird angezeigt. 

6. Klicken Sie auf der Kachel **Zugriffs & Berechtigungen** auf der Registerkarte **Einstellungen** auf **auswählen**, und klicken Sie dann auf **Aktualisieren**.

7. Klicken Sie auf **Aktualisieren**.

8. Klicken Sie auf der Seite **diesen Fall Flyout verwalten** unter **Mitglieder verwalten**auf **Hinzufügen** , um der Anfrage Mitglieder hinzuzufügen.

9. Aktivieren Sie in der Liste der Personen das Kontrollkästchen neben den Namen der Personen, die der Anfrage hinzugefügt werden sollen. Wie bereits erläutert, müssen Sie sicherstellen, dass den Benutzern, die Sie dem Fall hinzufügen, die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

10. Nachdem Sie die Personen ausgewählt haben, die als Mitglieder der Anfrage hinzugefügt werden sollen, klicken Sie auf **Hinzufügen**.

11. Klicken Sie auf der Flyout-Seite **Fall verwalten** auf **Speichern**, um die neue Liste der Fallbeteiligten zu speichern.

12. Klicken Sie auf die Registerkarte **Start** , um zur Fall Startseite zu wechseln.

## <a name="explore-the-advanced-ediscovery-workflow"></a>Untersuchen des erweiterten eDiscovery-Workflows

Um den Einstieg in die Verwendung von Advanced eDiscovery zu erleichtern, finden Sie hier einen einfachen Workflow, der sich an [gängige eDiscovery-Methoden](overview-ediscovery-20.md#alignment-with-edrm)richtet. In jedem dieser Schritte werden auch einige erweiterte eDiscovery-Funktionen hervorgehoben, die Sie untersuchen können.

![Advanced eDiscovery-Workflow](../media/AeDWorkflow.png)

1. **[Hinzufügen von Verwaltern zu einem Fall](add-custodians-to-case.md)**. Der erste Schritt nach dem Erstellen eines Falls besteht darin, Verwalter hinzuzufügen. Bei einer *Depotbank* handelt es sich um eine Person, die über eine administrative Kontrolle über ein Dokument oder eine elektronische Datei verfügt, die für den Fall relevant sein kann. Hier sind einige Dinge, die passieren (oder die Sie tun können), wenn Sie Verwalter einem Fall hinzufügen:

   - Die Daten im Exchange-Postfach des Verwalters, im OneDrive-Konto und in allen Microsoft Teams-oder Jammer Gruppen, in denen die Depotbank Mitglied ist, können in dem Fall als Freiheitsentzug-Daten "gekennzeichnet" werden.
  
   - Depotdaten werden neu indiziert (durch einen Prozess mit dem Namen *Advanced Indexing*). Dies hilft beim Optimieren der Suche im nächsten Schritt.
  
   - Sie können Depotdaten aufbewahren. Dadurch werden Daten beibehalten, die für den Fall während der Untersuchung relevant sein können.
  
   - Sie können einer Depotbank andere Datenquellen zuordnen (beispielsweise können Sie eine SharePoint-Website oder eine Microsoft 365-Gruppe mit einer Depotbank verknüpfen), damit diese Daten neu indiziert, gespeichert und durchsucht werden können, genauso wie die Daten im Postfach des Depotbank-oder OneDrive-Kontos.

   - Sie können den [Kommunikations Workflow](managing-custodian-communications.md) in Advanced eDiscovery verwenden, um eine rechtliche Aufbewahrungs Benachrichtigung an Verwalter zu senden.

2. **[Durchsuchen von Freiheits Datenquellen nach Daten, die für den Fall relevant](collecting-data-for-ediscovery.md)** sind. Nachdem Sie einem Fall Verwalter hinzugefügt haben, verwenden Sie das integrierte Such Tool, um die Speicherorte der Depotdaten nach Daten zu durchsuchen, die für den Fall relevant sein können. Sie verwenden Schlüsselwörter, Eigenschaften und Bedingungen zum [Erstellen von Suchabfragen](building-search-queries.md) , die Suchergebnisse mit den Daten zurückgeben, die für den Fall wahrscheinlich relevant sind. Sie können auch Folgendes tun:

   - Anzeigen von [Suchstatistiken](search-statistics.md) , die Ihnen beim Verfeinern einer Suchabfrage helfen können, um die Ergebnisse einzugrenzen.

   - Zeigen Sie eine Vorschau der Suchergebnisse an, um schnell zu überprüfen, ob die relevanten Daten gefunden werden.

   - Überarbeiten Sie eine Abfrage, und führen Sie die Suche erneut aus.

3. **[Hinzufügen von Daten zu einem Überprüfungs Satzes](add-data-to-review-set.md)**. Nachdem Sie konfiguriert und überprüft haben, dass eine Suche die gewünschten Daten zurückgibt, besteht der nächste Schritt darin, die Suchergebnisse einer Überprüfungsgruppe hinzuzufügen. Wenn Sie einer Überprüfungsgruppe Daten hinzufügen, werden Elemente von Ihrem ursprünglichen Speicherort an einen sicheren Azure-Speicher Speicherort kopiert. Die Daten werden erneut indiziert, um Sie für eine gründliche und schnelle Suche zu optimieren, wenn Sie Elemente im Überprüfungs Satzes überprüfen und analysieren. Darüber hinaus können Sie [einer Überprüfungsgruppe auch nicht Office 365 Daten hinzufügen](load-non-office-365-data-into-a-review-set.md).

   Es gibt auch eine spezielle Art von Überprüfungs Sätzen, denen Sie Daten hinzufügen können, die als *Unterhaltungs Überprüfungs Sätze*bezeichnet werden. Diese Typen von Überprüfungs Sätzen bieten Funktionen für die Wiederherstellung von Unterhaltungen zum rekonstruieren, überprüfen und Exportieren von Thread Unterhaltungen wie denen in Microsoft Teams. Weitere Informationen finden Sie unter [Review Conversations in Advanced eDiscovery](conversation-review-sets.md).

4. **Überprüfen und Analysieren von Daten in einem Überprüfungs Satzes**. Da sich die Daten nun in einem Überprüfungs Satzes befinden, können Sie eine Vielzahl von Tools und Funktionen zum Anzeigen und Analysieren der Falldaten verwenden, um die Datenmenge auf das zu reduzieren, was für den Fall relevant ist, dass Sie untersucht werden. Im folgenden finden Sie eine Liste mit einigen Tools und Funktionen, die Sie während dieses Prozesses verwenden können.

   - [Dokumente anzeigen](view-documents-in-review-set.md). Dies umfasst das Anzeigen der Metadaten für jedes Dokument in einer Überprüfungsgruppe und das Anzeigen des Dokuments in seiner systemeigenen Version oder Textversion.

   - [Erstellen von Abfragen und Filtern](review-set-search.md) Sie erstellen Suchabfragen mithilfe einer Vielzahl von Suchkriterien (einschließlich der Möglichkeit zum Durchsuchen aller [Eigenschaften von Datei Metadaten](document-metadata-fields-in-advanced-ediscovery.md)), um die Falldaten weiter zu verfeinern und zu filtern, was für den Fall am relevantesten ist. Sie können auch Filter zum Überprüfen von Sätzen verwenden, um schnell zusätzliche Bedingungen auf die Ergebnisse einer Suchabfrage anzuwenden, um diese Ergebnisse weiter zu verfeinern. 

   - [Erstellen und Verwenden von Tags](tagging-documents.md). Sie können Tags auf Dokumente in einem Überprüfungs Satzes anwenden, um zu ermitteln, welche reaktionsfähig sind (oder nicht auf den Fall reagieren), und dann diese Tags beim Erstellen von Suchabfragen verwenden, um die markierten Dokumente einzubeziehen oder auszuschließen. Sie können auch kennzeichnen, um zu bestimmen, welche Dokumente exportiert werden sollen.

   - [Beschriften und redact von Dokumenten](view-documents-in-review-set.md#annotate-view). Sie können das Annotation-Tool in einer Überprüfung verwenden, um Dokumente und redact-Inhalte in Dokumenten als Arbeitsprodukt zu kommentieren. Wir generieren eine PDF-Version eines kommentierten oder bearbeiteten Dokuments während der Überprüfung, um das Risiko zu verringern, dass die unzensierte-systemeigene Version des Dokuments exportiert wird.

   - [Analysieren von Case-Daten](analyzing-data-in-review-set.md). Die Analysefunktionalität in Advanced eDiscovery ist leistungsfähig. Nachdem Sie Analytics für die Daten in Review-Gruppe ausgeführt haben, führen wir eine Analyse wie etwa doppelte Erkennung, e-Mail-Threading und Designs durch, die dazu beitragen können, das Volumen von Dokumenten zu reduzieren, die Sie überprüfen müssen. Außerdem generieren wir Analyseberichte, in denen das Ergebnis der Ausführung von Analysen zusammengefasst wird. Wie bereits erläutert, führt das Ausführen von Analytics auch [das Erkennungs Modell für das Anwalts Client-Privileg](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)aus.

5. **Exportieren und Herunterladen von Case-Daten**. Ein letzter Schritt nach dem sammeln, überprüfen und Analysieren von Falldaten besteht darin, die Daten aus Advanced eDiscovery für externe Überprüfungen oder zur Überprüfung durch Personen außerhalb des Ermittlungsteams zu exportieren. Das Exportieren von Daten erfolgt in einem zweistufigen Prozess. Der erste Schritt besteht darin, Daten aus der Überprüfungsgruppe zu [exportieren](export-documents-from-review-set.md) und an einen anderen Azure-Speicherort (einen von Microsoft oder eine von Ihrer Organisation verwaltete) zu kopieren. Anschließend verwenden Sie Azure Storage Explorer, um die Daten auf einen lokalen Computer [herunterzuladen](download-export-jobs.md) . Zusätzlich zu den exportierten Datendateien enthält der Inhalt des Exportpakets auch einen Exportbericht, einen Zusammenfassungsbericht und einen Fehlerbericht.
