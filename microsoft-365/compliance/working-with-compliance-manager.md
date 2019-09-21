---
title: Arbeiten mit dem Microsoft Compliance-Manager (Vorschau)
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
ms.openlocfilehash: 07aee08c8929443b8b4f4805d22a94b0ad9db27a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082034"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a>Arbeiten mit dem Microsoft Compliance-Manager (Vorschau)

> [!IMPORTANT]
> Microsoft Compliance Manager ist ein Dashboard und Verwaltungstool, das eine Zusammenfassung Ihrer Datenschutz-und Compliance-Größe sowie Empfehlungen zur Verbesserung des Datenschutzes und der Compliance bietet. Die im Compliance-Manager bereitgestellten Kundenaktionen sind Empfehlungen; Es liegt in Ihrer Organisation, die Wirksamkeit dieser Empfehlungen in ihrem jeweiligen regulatorischen Umfeld vor der Implementierung zu bewerten. Im Compliance-Manager gefundene Empfehlungen sollten nicht als Garantie für die Compliance interpretiert werden.

## <a name="access-compliance-manager"></a>Zugriff auf Compliance-Manager

Sie können über das Service Trust Portal auf den Compliance-Manager zugreifen. Alle Personen mit einem Microsoft-Konto oder mit einem Azure Active Directory-Organisationskonto können auf den Compliance-Manager zugreifen.
  
1. Wechseln Sie zu [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).

2. Melden Sie sich mit Ihrem Microsoft-Dienstkonto an. Dies ist Ihr Office 365-, Microsoft 365-oder Azure Active Directory (Azure AD)-Benutzerkonto.

3. Wählen Sie im Dienst Vertrauensstellungs Portal **Compliance-Manager**aus. Dies ist die Vorschauversion von Compliance-Manager. **Compliance-Manager (klassisch)** ist der Link zur vorherigen Version von Compliance-Manager.

4. Wenn die Geheimhaltungsvereinbarung angezeigt wird, lesen Sie Sie, und wählen Sie **bestätigen** aus, um den Vorgang fortzusetzen. Sie müssen einmal zustimmen, und dann wird das Compliance-Manager-Dashboard angezeigt.

Um Ihnen den Einstieg zu erleichtern, wird eine ISO/IEC 27001:2103-Bewertung für Office 365 standardmäßig für Ihre Organisation angezeigt.

## <a name="administration"></a>Verwaltung

Es gibt bestimmte administrative Funktionen, die nur für den mandantenadministrator verfügbar sind und nur sichtbar sind, wenn Sie mit einem globalen Administratorkonto angemeldet sind. Solange der Administrator den Benutzern jedoch keine Compliance-Manager-Rollen zuweist, sind die Daten im Compliance-Manager für alle Benutzer in Ihrer Organisation sichtbar. Es wird empfohlen, die rollenbasierte Zugriffssteuerung zu implementieren, um zu bestimmen, wer im Compliance-Manager auf Aktionen zugreifen und diese ausführen kann.
  
### <a name="assigning-compliance-manager-roles-to-users"></a>Zuweisen von Compliance-Manager-Rollen zu Benutzern

Jede Compliance-Manager-Rolle verfügt über geringfügig unterschiedliche Berechtigungen. Sie können die jeder Rolle zugewiesenen Berechtigungen anzeigen, ermitteln, welche Benutzer sich in welchen Rollen befinden, und Benutzer aus dieser Rolle über das Dienst Vertrauensstellungs Portal hinzufügen oder entfernen. Wählen Sie das Menüelement **Admin** aus, und wählen Sie die anzuzeigenden **Einstellungen** aus.
  
![STP-Verwaltungsmenü: ausgewählte Einstellungen](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
Hinzufügen oder Entfernen von Benutzern aus Compliance-Manager-Rollen
  
1. Wechseln Sie zu [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).

2. Melden Sie sich mit Ihrem globalen Azure Active Directory-Administratorkonto an.

3. Wählen Sie in der oberen Menüleiste des Dienst Vertrauensstellungs Portals die Option **Administrator** aus, und wählen Sie dann **Einstellungen**aus.

4. Wählen Sie in der Dropdownliste **Rolle auswählen** die Rolle aus, die Sie verwalten möchten.

5. Benutzer, die jeder Rolle hinzugefügt wurden, werden auf der Seite **Rolle auswählen** aufgeführt.

6. Um Benutzer zu dieser Rolle hinzuzufügen, wählen Sie **Hinzufügen**aus. Wählen Sie im Dialogfeld **Benutzer hinzufügen** das Feld Benutzer aus. Sie können in der Liste der verfügbaren Benutzer einen Bildlauf durchführen oder mit der Eingabe des Benutzernamens beginnen, um die Liste basierend auf Ihrem Suchbegriff zu filtern. Wählen Sie den Benutzer aus, der dieses Konto der mit dieser Rolle bereitgestellten Liste **Benutzer** hinzufügen hinzugefügt werden soll. Wenn Sie mehrere Benutzer gleichzeitig hinzufügen möchten, beginnen Sie mit der Eingabe eines Benutzernamens, um die Liste zu filtern, und wählen Sie dann den Benutzer aus, der der Liste hinzugefügt werden soll. Wählen Sie **Speichern** aus, um die ausgewählte Rolle für diese Benutzer festzustellen. 

    ![Compliance-Manager – hinzufügen von Benutzern](media/compliance-manager-add-users.png)
  
7. Wenn Sie Benutzer aus dieser Rolle entfernen möchten, wählen Sie die Benutzer aus, und klicken Sie dann auf **Löschen**.

    ![Compliance-Manager – Löschen von Benutzern](media/compliance-manager-delete-users.png)

## <a name="groups"></a>Gruppen

Mit Gruppen können Sie Bewertungen logisch organisieren und gemeinsame Informations-und Workflowaufgaben Zwischenbewertungen mit denselben oder Verwandten, vom Kunden verwalteten Steuerelementen freigeben. Sie können Bewertungen nach Jahr, Standard, Dienst, Team, Abteilung oder Agenturen in Ihrer Organisation gruppieren, um die von Kunden verwalteten Aktionen zu minimieren:
  
- **FFIEC ist Assessments 2019**
  - Office 365 + FFIEC ist
  - InTune + FFIEC ist
- **Datenschutzbewertungen**
  - Office 365 + ISO 27001:2013
  - Office 365 + ISO 27018:2014

Wenn Sie eine neue Bewertung erstellen, müssen Sie eine neue Gruppe für die Bewertung erstellen oder die Bewertung einer vorhandenen Gruppe zuweisen. Gruppen können nicht als eigenständige Entitäten erstellt werden. Es wird empfohlen, *vor* dem Hinzufügen neuer Bewertungen eine Gruppierungs Strategie für Ihre Organisation zu ermitteln. Standardmäßig steht für Ihre anfänglichen Bewertungen eine Gruppe mit dem Namen "Default Group" zur Verfügung. Gruppen haben keine Sicherheitseigenschaften. Alle Berechtigungen sind Assessments zugeordnet.

Beachten Sie beim Arbeiten mit Gruppen Folgendes:
  
- Zugehörige bewertungssteuerelemente in unterschiedlichen Bewertungen innerhalb derselben Gruppe werden automatisch aktualisiert, wenn Sie abgeschlossen werden.
- Neue Gruppen können Informationen aus einer vorhandenen Gruppe kopieren, wenn Sie eine neue Bewertung erstellen. Alle Informationen, die den Implementierungs Details und Test Plan-und Verwaltungs Antwortfeldern von von Kunden verwalteten Steuerelementen aus Bewertungen in der Gruppe hinzugefügt wurden, von der Sie kopieren, werden in die gleichen (oder verwandten) von Kunden verwalteten Steuerelemente in der neuen Bewertung. Wenn Sie einer vorhandenen Gruppe eine neue Bewertung hinzufügen, werden allgemeine Informationen aus Bewertungen in dieser Gruppe in die neue Bewertung kopiert.
- Gruppennamen (auch *Gruppen-IDs*genannt) müssen innerhalb Ihrer Organisation eindeutig sein.
- Gruppen können Bewertungen für die gleiche Zertifizierung/Regulierung enthalten, aber jede Gruppe kann nur eine Bewertung für ein bestimmtes Cloud Service/Zertifizierungs Paar enthalten. Beispielsweise kann eine Gruppe keine zwei Bewertungen für Office 365 und das NIST-GfK enthalten. Eine Gruppe kann nur dann mehrere Bewertungen für denselben clouddienst enthalten, wenn die entsprechende Zertifizierung/Regulierung für jede einzelne unterschiedlich ist.
- Nachdem eine Bewertung zu einer Bewertungsgruppe hinzugefügt wurde, kann die Gruppierung nicht mehr geändert werden. Sie können die Bewertungsgruppe umbenennen, die den Namen der Bewertungs Gruppierung für alle dieser Gruppe zugeordneten Bewertungen ändert. Sie können eine Bewertung und eine neue Bewertungsgruppe erstellen und Informationen aus einer vorhandenen Bewertung kopieren, wodurch effektiv ein Duplikat dieser Bewertung in einer anderen Bewertungsgruppe erstellt wird.
- Durch das Archivieren einer Bewertung wird die Beziehung zwischen dieser Bewertung und der Gruppe unterbrochen. Weitere Aktualisierungen anderer verwandter Bewertungen werden nicht mehr in der archivierten Bewertung wiedergegeben.

## <a name="tenant-management"></a>Mandantenverwaltung

Compliance-Manager (Preview) enthält eine neue Schnittstelle zum Verwalten neuer Datenelemente, die als **Mandantenverwaltung**bezeichnet werden. Mit dieser Schnittstelle können Sie Mandantenweite Einstellungen verwalten:

- **Dimensionen:** Anzeigen, hinzufügen und Anpassen von Metadaten für Vorlagen, BEWERTUNGEN und Aktionselemente, mit denen Sie benutzerdefinierte Pivots für Filter erstellen können.
- **Besitzer:** Geben Sie einen Besitzer für jedes Aktionselement an.
- **Aktionen für Kunden:** Verwalten Sie die vollständige Liste der Aktionen, die in Compliance-Manager (Preview) enthalten sind, und aktivieren/deaktivieren Sie die Secure Score-Überwachung für Aktionen, die mit Secure Score integriert sind.

Wählen Sie **Mandantenverwaltung** aus, um die Verwaltungsschnittstelle zu öffnen, und führen Sie die folgenden Schritte aus, um **Dimensionen**, **Besitzer**und **Kundenaktionen**zu verwalten.

### <a name="dimensions"></a>Maße

Dimensionen sind Satz von Metadaten, die Informationen zu einer Vorlage, einer Bewertung oder einem Aktionselement bereitstellen. Dimensionen verwenden das Konzept von Schlüsseln und Werten, wobei der Dimensionsschlüssel eine Eigenschaft darstellt, und Dimensionswert gültige Werte für die Eigenschaft darstellt. Beispielsweise gibt es im Compliance-Manager drei Arten von Aktionen. Sie werden durch einen Dimensionsschlüssel des **Aktionstyps** und der Dimensionswerte der Dokumentation, der **Betriebs**-und der **technischen** **Beschreibung**definiert. Sie können vorhandene Dimensionen ändern oder eigene Bemaßungen hinzufügen. Das Hinzufügen von Dimensionen ist häufig beim Importieren benutzerdefinierter Vorlagen erforderlich.

#### <a name="add-a-dimension"></a>Hinzufügen einer Dimension

1. Öffnen Sie die **Mandantenverwaltung** , und wählen Sie **Dimensionen**aus.
2. Wählen Sie **+ Dimension hinzufügen**aus.
3. Geben Sie im Feld **Schlüssel** einen eindeutigen Namen ein.
4. Aktivieren Sie optional mehrere Werte, die gleichzeitig für dieselbe Taste verwendet werden sollen, und schieben Sie die Umschaltfläche für die Option **Mehrfachauswahl für Bemaßungen** auf ein.
5. Wählen Sie **+ Hinzufügen** aus, um einen Wert hinzuzufügen, indem Sie einen eindeutigen Namen angeben und auf das Symbol Speichern klicken.
6. Wiederholen Sie Schritt 5 für jeden Wert, den Sie hinzufügen möchten.
7. Wählen Sie **Speichern** aus, um die neue Dimension zu speichern.

#### <a name="edit-a-dimension"></a>Bearbeiten einer Dimension

Sie können einen Dimensionsschlüssel umbenennen, aber Sie können die Werte für benutzerdefinierte Bemaßungen ändern.

1. Öffnen Sie die **Mandantenverwaltung** , und wählen Sie **Dimensionen**aus.
2. Suchen Sie die Dimension, die Sie bearbeiten möchten, wählen Sie daneben die Auslassungspunkte (...) aus, und wählen Sie **Bearbeiten**aus.
3. Wählen Sie **+ Hinzufügen** aus, um einen Wert hinzuzufügen, indem Sie einen eindeutigen Namen angeben und auf das Symbol Speichern klicken, oder wählen Sie den Wert aus, den Sie bearbeiten oder löschen möchten, und wählen Sie **Entfernen** oder **Bearbeiten**aus.
4. Klicken Sie auf **Speichern** , wenn Sie die Änderungen abgeschlossen haben.

#### <a name="delete-a-dimension"></a>Löschen einer Dimension

Sie können benutzerdefinierte Dimensionen bei Bedarf löschen.

1. Öffnen Sie die **Mandantenverwaltung** , und wählen Sie **Dimensionen**aus.
2. Suchen Sie die Dimension, die Sie löschen möchten, wählen Sie daneben die Ellipsen (...) aus, und wählen Sie dann **Löschen**aus.
3. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **Löschen**aus.

### <a name="owners"></a>Besitzer

Besitzer werden verwendet, um die zuständige Partei für jedes Steuerelement zu identifizieren. Alle integrierten Steuerelemente befinden sich im Besitz von Microsoft, von Kunden oder von beiden. Sie können benutzerdefinierte Werte für Besitzer erstellen, die verwendet werden können, um mehr granulare Zuständigkeiten innerhalb Ihrer Organisation anzugeben. Sie können beispielsweise Besitzer erstellen, die bestimmte Gruppen, Teams oder Unternehmenseinheiten in Ihrer Organisation darstellen.

#### <a name="add-an-owner"></a>Hinzufügen eines Besitzers

1. Öffnen Sie die **Mandantenverwaltung** , und wählen Sie **Besitzer**aus.
2. Wählen Sie **+ Besitzer hinzufügen**aus.
3. Geben Sie einen Namen und eine Beschreibung für den Besitzer an, und wählen Sie **Speichern**aus. Die Beschreibung wird in der Spalte Besitzer angezeigt.

#### <a name="edit-an-owner"></a>Bearbeiten eines Besitzers

Ein Besitzername kann nicht bearbeitet werden, aber Sie können die Beschreibung ändern, die in der Spalte Besitzer angezeigt wird.

1. Öffnen Sie die **Mandantenverwaltung** , und wählen Sie **Besitzer**aus.
2. Suchen Sie den Besitzer, den Sie bearbeiten möchten, wählen Sie daneben die Auslassungspunkte (...) aus, und klicken Sie dann auf **Bearbeiten**.
3. Ändern Sie die Beschreibung nach Bedarf, und wählen Sie **Speichern**aus.

#### <a name="delete-an-owner"></a>Löschen eines Besitzers

1. Öffnen Sie die **Mandantenverwaltung** , und wählen Sie **Besitzer**aus.
2. Suchen Sie den Besitzer, den Sie löschen möchten, wählen Sie daneben die Auslassungspunkte (...) aus, und wählen Sie dann **Löschen**aus.
3. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **Löschen**aus.

### <a name="customer-actions"></a>Kundenaktionen

Im Bereich Kundenaktionen werden alle Kundenaktionen für alle Vorlagen und Bewertungen im Compliance-Manager (Preview) angezeigt.

![Compliance-Manager – hinzufügen von Benutzern](media/compliance-manager-customer-actions.png)

Auf einen Blick können Sie den Titel, den Besitzer, die Kategorie, die Erzwingung und das Ergebnis einer Aktion anzeigen und ermitteln, ob Sie mit Secure Score integriert ist. Sie können eine Aktion erweitern und dann **Read More** auswählen, um die Beschreibung der Aktion zu lesen und auf Links in der Beschreibung zuzugreifen. Sie können diese Schnittstelle auch verwenden, um die sichere Ergebnis Integration auf Aktionsbasis zu aktivieren und zu deaktivieren und benutzerdefinierte Aktionen hinzuzufügen. Aktionen mit einer Secure Score-Integrationsfunktion haben neben Ihnen ein Auslassungszeichen (...) (Beachten Sie, dass in benutzerdefinierten Aktionen neben Ihnen auch ein Auslassungszeichen steht).

#### <a name="enable-or-disable-secure-score-integration"></a>Aktivieren oder Deaktivieren der Integration sicherer Bewertungen

1. Wählen Sie die Auslassungspunkte (...) für die Aktion aus, die Sie ändern möchten, und wählen Sie **Bearbeiten**aus.
2. Wechseln Sie zur Option Secure Score Continuous Update auf ein oder aus, um die kontinuierliche Überwachung mithilfe von Secure Score zu aktivieren oder zu deaktivieren.
3. Klicken Sie auf **Speichern**.

#### <a name="add-a-customer-action"></a>Hinzufügen einer Kunden Aktion

1. Wählen Sie **+ Kunden Aktion hinzufügen**aus.
2. Geben Sie einen eindeutigen Titel für die Aktion im Feld **Title** an.
3. Geben Sie im Feld **Maximale Konformitätsbewertung** eine Konformitätsbewertung für die Aktion an (Dies kann eine beliebige Zahl von 1-99 sein).
4. Geben Sie mithilfe der Dropdownliste **Aktionstyp** den Typ der Aktion an, die Sie hinzufügen möchten. Wenn der Aktionstyp nicht vorhanden ist, können Sie ihn hinzufügen, indem Sie den Wert dem Dimensionsschlüssel Aktion hinzufügen.
5. Verwenden Sie das Dropdown-Menü **Dimensionen** , um Dimensionsschlüssel und Werte für die Aktion anzugeben oder hinzuzufügen.
6. Verwenden Sie die Dropdownliste **Besitzer** , um den Besitzer für Aktion anzugeben.
7. Wählen **+** Sie diese Option aus, um eine Beschreibung und einen Beschreibungstitel für die Aktion hinzuzufügen.
8. Wählen Sie das **X** aus, um das Blatt Beschreibung zu schließen.
9. Wählen Sie **Speichern** aus, um die Aktion Kunden zu speichern.

#### <a name="edit-a-customer-action"></a>Bearbeiten einer Kunden Aktion

1. Wählen Sie die Auslassungspunkte (...) für die Aktion aus, die Sie ändern möchten, und wählen Sie **Bearbeiten**aus.
2. Bearbeiten Sie die Aktion wie gewünscht, und wählen Sie **Speichern**aus.

#### <a name="delete-a-customer-action"></a>Löschen einer Kunden Aktion

1. Wählen Sie die Auslassungspunkte (...) für die Aktion aus, die Sie ändern möchten, und wählen Sie **Löschen**aus.
2. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **Löschen**aus.

## <a name="assessments"></a>Bewertungen

### <a name="add-an-assessment"></a>Hinzufügen eines Assessments
  
1. Wählen Sie im Dashboard Assessments die Option **+ Assessment hinzufügen**aus.

2. Wenn das Blade geöffnet wird, geben Sie die folgenden Informationen ein:

    - **Title (erforderlich):** Geben Sie einen Titel für Ihre Bewertung ein.
    - **Wählen Sie eine Vorlage aus (erforderlich):** Auswählen einer Standard-oder benutzerdefinierten Vorlage
    - **Wählen Sie eine Gruppe aus, oder fügen Sie eine neue Gruppe hinzu (erforderlich):** Wählen Sie eine vorhandene Gruppe aus, oder wählen Sie aus, um eine neue Gruppe hinzuzufügen, und geben Sie einen eindeutigen Gruppennamen an.
    - Möchten **Sie die Daten aus einer vorhandenen Gruppe kopieren? (optional):** Umschalten des Steuerelements zum Aktivieren der Gruppen Kopie und dann:
        - **Wählen Sie eine Gruppe aus (optional):** Wenn die Gruppen Kopie aktiviert ist, wählen Sie die Gruppe aus, aus der kopiert werden soll.
            - **Implementierungs Details (optional):** Auswählen, um Implementierungsdetails in die neue Gruppe zu kopieren
            - **Testplan #a0 zusätzliche Informationen (optional):** Wählen Sie diese Option aus, um den Testplan und weitere Informationsdetails in die neue Gruppe zu kopieren.
            - **Dokumente (optional):** Auswählen, um Dokumente in die neue Gruppe zu kopieren

3. Wählen Sie **Speichern** aus, um die Bewertung zu erstellen.

 Die neue Bewertung wird im Assessment-Dashboard angezeigt und zeigt die folgenden Informationen an:

- Der Titel der Bewertung.
- Die Dimensionen der Bewertung, einschließlich Zertifizierung, Umgebung und Produkt, die auf die Bewertung angewendet wurden.
- Das Datum, an dem es erstellt wurde, und das Datum, an dem es zuletzt geändert wurde.
- Das Bewertungsergebnis wird als Prozentsatz angezeigt.
- Fortschrittsindikatoren, die die Anzahl der beurteilten von Microsoft verwalteten und vom Kunden verwalteten Steuerelemente anzeigen.

### <a name="copying-information-from-existing-assessments"></a>Kopieren von Informationen aus vorhandenen Bewertungen

Wenn Sie eine Bewertung erstellen, haben Sie die Möglichkeit, Informationen aus einer vorhandenen Gruppe zu kopieren. Auf diese Weise können Sie die in die kopierte Bewertung eingegebenen Informationen auf dieselben Steuerelemente in der neuen Bewertung anwenden. Wenn Sie beispielsweise eine Gruppe für alle FFIEC-bezogenen Bewertungen in Ihrer Organisation haben, können Sie die folgenden Informationen aus vorhandenen Bewertungen kopieren:

- Implementierungs Details
- Testplan #a0 zusätzliche Informationen
- Dokumente

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a>Kopieren von Informationen aus einer vorhandenen Bewertung in eine neue Bewertung
  
1. Wählen Sie im Assessment-Dashboard die Option **+ Add Assessment**aus.
    
2. Füllen Sie im Fenster **Bewertung hinzufügen** die folgenden Informationen aus.

    - **Title (erforderlich):** Geben Sie einen Titel für Ihre Bewertung ein.
    - **Wählen Sie eine Vorlage aus (erforderlich):** Wählen Sie eine Standard-oder benutzerdefinierte Vorlage aus.
    - **Wählen Sie eine Gruppe aus, oder fügen Sie eine neue Gruppe hinzu (erforderlich):** Wählen Sie **neue Gruppe hinzufügen** aus, und geben Sie einen eindeutigen Gruppennamen an.
    - Möchten **Sie die Daten aus einer vorhandenen Gruppe kopieren? (optional):** schalten Sie das Steuerelement in ein ein, um die Gruppen Kopie zu aktivieren, und klicken Sie dann auf:- **Wählen Sie eine Gruppe aus (optional):** wenn Gruppen Kopie aktiviert ist, wählen Sie die Gruppe aus, aus der kopiert werden soll.
            - **Implementierungs Details (optional):** Wählen Sie diese Option aus, um Implementierungsdetails in die neue Gruppe zu kopieren.
            - **Testplan #a0 zusätzliche Informationen (optional):** Wählen Sie diese Option aus, um den Testplan und weitere Informationsdetails in die neue Gruppe zu kopieren.
            - **Dokumente (optional):** Wählen Sie diese Option aus, um Dokumente in die neue Gruppe zu kopieren.

3. Wählen Sie **Speichern** aus, um die Bewertung zu erstellen.

### <a name="viewing-assessments"></a>Anzeigen von Bewertungen

#### <a name="view-an-assessment"></a>Anzeigen einer Bewertung
  
1. Wählen Sie im Dashboard Assessments den Bewertungs Namen aus, um ihn zu öffnen, und zeigen Sie die Informationen zu Aktionselementen und Steuerelementen an.

Hier ist ein Beispiel für die Bewertung für Office 365 und ISO 27001. Die erste Ansicht zeigt die neue Ansicht "Aktionselemente" im Compliance-Manager (Preview).

![Ansicht "Compliance-Manager-Aktionselemente"](media/compliance-manager-action-items.png)

Die Aktionen werden in alphabetischer Reihenfolge aufgeführt, und jeder Aktion wird ein Ergebnis und ein Besitzer zugewiesen. Klicken Sie auf den Link **Read More** , um die Details der einzelnen Aktionen zu lesen. 

![Ansicht "Compliance-Manager-Aktionselemente"](media/compliance-manager-actions-read-more.png)

Wählen Sie den Link **überprüfen** aus, um die Aktion zu verwalten, zuzuweisen, zu implementieren und zu testen. Unten sehen Sie eine Beispielaktion.

![Aktionsansicht für Compliance-Manager](media/compliance-manager-action.png)

In früheren Versionen von Compliance-Manager wurde der Workflow zur Implementierung von Anforderungen auf der Ebene der Steuerung ausgeführt. Ein Compliance Officer würde einem Benutzer ein Steuerelement zuweisen, um das Steuerelement zu implementieren. Es gab zwei Nachteile:

- Steuerelementen wurden häufig mehrere Aktionen zugeordnet, und der Benutzer, dem ein Steuerelement zugewiesen wurde, ist möglicherweise nicht die richtige Person, um alle Aktionen abzuschließen, die zum Implementieren des Steuerelements erforderlich waren.
- Durch die Kombination von getrennten Vorgängen in einer einzigen Aktion wurde die Sammlung der Signale und Telemetrie verhindert, die zum automatischen Aufzeichnen von Mandanten Konfigurationsänderungen im Compliance-Manager (Preview) verwendet werden.

Im Compliance-Manager (Preview) wurde der Workflowprozess von der Steuerelementebene zur Aktionsebene verschoben. Wenn Sie eine Aktion überprüfen, können Sie die folgenden Felder verwenden, um den Aktions Workflow zu verwalten:

- **Benutzer zuweisen:** Wählen Sie dieses Feld aus, um den Benutzer auszuwählen oder einzugeben, dem diese Aktion zugewiesen werden soll. Sie können in der Liste einen Bildlauf durchführen oder einen Namen eingeben, um ihn zu finden, und dann auswählen.
- **Dokumente verwalten:** Sie können einen Nachweis über die Implementierung in Form von Office-Dokumenten, Bilddateien und Screenshots, PowerShell-Ausgaben in CSV oder txt und PDFs hochladen.
- **Implementierungs Status:** Wird verwendet, um den aktuellen Implementierungsstatus der Aktion anzugeben. Mögliche Werte sind nicht implementiert, implementiert, alternative Implementierung, geplant und nicht im Bereich.
- **Implementierungsdatum:** Das Datum, an dem die Aktion ausgeführt wurde.
- **Test Ergebnis:** Wird verwendet, um die Ergebnisse der Implementierungs Überprüfung anzugeben. Mögliche Werte werden nicht bewertet, übergeben, fehlgeschlagen – niedriges Risiko, Fehler – mittleres Risiko, Fehler – hohes Risiko und nicht im Bereich.
- **Test Datum:** Das Datum, an dem die Überprüfung stattgefunden hat.
- **Anmerkungen zur Implementierung:** Geben Sie Implementierungsdetails für Ihre Organisation sowie alle Notizen ein, die Sie einschließen möchten.
- **Testplan:** Geben Sie die Details des Testplans für diese Aktion sowie alle Notizen ein, die Sie einschließen möchten.
- **Zusätzliche Informationen:** Geben Sie zusätzliche Informationen zu dieser Aktion oder deren Implementierung in Ihrer Organisation sowie alle Notizen ein, die Sie einschließen möchten.

Compliance-Manager (Preview) enthält auch den Steuerelement basierten Pivot, der in früheren Versionen gefunden wurde. Wählen Sie das Dashboard **Steuerelemente Info** aus, um es anzuzeigen. Sie können Informationen zu Steuerelementen auf der Bewertungs-und Vorlagenebene anzeigen. Unten sehen Sie ein Beispiel für das Steuerelement-Info-Dashboard für Bewertungen.

![Compliance-Manager-Steuerelement-Info-Ansicht](media/compliance-manager-controls-info.png)

Für Bewertungen wird im Dashboard Informationen für Steuerelemente angezeigt:

- Eine **Gruppen** -Dropdownliste zum Auswählen der anzuzeigenden Gruppe (wenn mehrere Gruppen verwendet werden).
- Eine **Bewertungs** Dropdownliste zur Auswahl der anzuzeigenden Bewertung.
- Metadaten zur ausgewählten Bewertung, einschließlich:
    - Eine Statusanzeige für **bewertete Steuer** Elemente, die die Anzahl der beurteilten Steuerelemente über die Gesamtzahl der Steuerelemente angibt.
    - Die aktuelle **Konformitäts** Bewertung für die Bewertung wird als Prozentsatz angezeigt.
    - Details zur **Zertifizierung** und dem **Produkt** , die bei der Bewertung verwendet werden.
    - Der aktuelle **Status** und das Datum der letzten **Änderung** für die Bewertung.
- Eine Liste der **in-Bereichs Dienste** für die Bewertung.
- Details zu den Steuerelementen, gruppiert nach Steuerelement Familie, mit Links zu Kundenaktionen und Details zur Microsoft-Implementierung:
    - **Ihre Aktionen** zeigt die Kundenaktionen an, die Sie ausführen können, um einige oder alle Anforderungen des Steuerelements zu erfüllen. Vielen Steuerelementen sind mehrere Aktionen zugeordnet, und alle einem Steuerelement zugeordneten Aktionen werden hier angezeigt. Die hier aufgeführten Aktionen weisen dieselbe Benutzeroberfläche auf wie die im Dashboard Aktionen.
    - **Microsoft-Aktionen** zeigt die Liste der Steuerelemente aus dem internen Microsoft-Framework an, die für das ausgewählte Zertifizierungs Steuerelement gelten. Wählen Sie für jedes interne Steuerelement **implementiert** aus, um die Implementierungs-und Testdetails von Microsoft sowie das Testergebnis und das Test Datum anzuzeigen, wie unten dargestellt.

![Compliance-Manager-Microsoft-Aktionsansicht](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a>Exportieren einer Bewertung

Sie können eine Bewertung in eine Excel-Datei für Compliance-Beteiligte in Ihrer Organisation oder für externe Prüfer und Regulierer exportieren. Der Bericht ist eine Momentaufnahme der Bewertung ab dem Datum und der Uhrzeit der Erstellung des Berichts. Der Bericht enthält die Details für alle von Microsoft und vom Kunden verwalteten Steuerelemente für die Bewertung, den Status der Implementierung, das Kontrolltest Datum, Testergebnisse und stellt Links zu hochgeladenen Beweisdokumenten bereit. Sie sollten den Bewertungsbericht vor dem Archivieren einer Bewertung exportieren, da Archivierte Bewertungen keine Links zu hochgeladenen Dokumenten beibehalten.
  
### <a name="export-an-assessment-report"></a>Exportieren eines Bewertungsberichts
  
1. Wählen Sie im Compliance-Manager-Dashboard die Registerkarte **Steuerelemente Info** aus.
2. Wählen Sie die **Gruppe** und die **Bewertung** in den Dropdownmenüs für die Bewertung aus, die Sie exportieren möchten.
3. Klicken Sie auf die Schaltfläche **exportieren** .

Der Bewertungsbericht wird als Excel-Datei in ihrer Browsersitzung heruntergeladen. Der Name der Datei für die Excel-Datei ist standardmäßig der Titel der Bewertung.

### <a name="archive-a-template-or-an-assessment"></a>Archivieren einer Vorlage oder eines Assessments

Wenn Sie mit einer Vorlage oder Bewertung fertig sind und diese nicht mehr für Compliance-Zwecke benötigen, können Sie Sie archivieren. Wenn eine Vorlage oder Bewertung archiviert wird, wird Sie aus der Standardansicht entfernt, und Sie müssen das Kontrollkästchen archiviert anzeigen aktivieren, um Sie anzuzeigen.

![Compliance-Manager-Microsoft-Aktionsansicht](media/compliance-manager-archive-assessment-view.png)
  
> [!IMPORTANT]
> Archivierte Bewertungen behalten Ihre Links zu hochgeladenen Beweisdokumenten nicht bei. Es wird dringend empfohlen, dass Sie den Test vor der Archivierung exportieren, um Links zu den Beweisdokumenten im Bericht beizubehalten.
  
#### <a name="archive-a-template"></a>Archivieren einer Vorlage

1. Öffnen Sie das Dashboard **Vorlagen** .
2. Suchen Sie nach der zu archivierenden Vorlage, und wählen Sie das Archiv Symbol aus.
3. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **archivieren**aus.

#### <a name="archive-an-assessment"></a>Archivieren einer Bewertung

1. Öffnen Sie das Dashboard **Assessments** .
2. Wählen Sie die **Gruppe** aus der Dropdownliste aus, die die Bewertung enthält, die Sie archivieren möchten.
3. Suchen Sie nach der Bewertung, die Sie archivieren möchten, und wählen Sie das Archiv Symbol aus.
4. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **archivieren**aus.

#### <a name="view-archived-assessments"></a>Anzeigen archivierter Bewertungen
  
1. Öffnen Sie die Registerkarte **Assessments** Dashboard, und aktivieren Sie das Kontrollkästchen **archiviert anzeigen** .
2. Die archivierten Bewertungen werden im Abschnitt **Archivierte Bewertungen** angezeigt.
3. Wählen Sie den zu öffnenden Bewertungs Namen aus, und zeigen Sie die Bewertung an.

#### <a name="activate-an-archived-assessment"></a>Aktivieren einer archivierten Bewertung

1. Klicken Sie auf der Registerkarte **Assessments** auf das Kontrollkästchen **archiviert anzeigen** .
2. Die archivierten Bewertungen werden im Abschnitt **Archivierte Bewertungen** angezeigt.
3. Suchen Sie nach der Bewertung, die Sie aktivieren möchten, und wählen Sie das Symbol aktivieren aus.
4. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **aktivieren**aus.

## <a name="controls-and-actions"></a>Steuerelemente und Aktionen

Steuerelemente und Aktionen sind die primären Daten Pivots, die in Compliance-Manager (Preview) verwendet werden. Der in früheren Versionen von Compliance-Manager vorhandene Steuerelement-Pivot wurde erweitert, um die Microsoft-und Kunden Steuerelemente in denselben Steuerelementfamilien anzuzeigen. Diese konsolidierte Ansicht erleichtert das Anzeigen des vollständigen Modells für die gemeinsame Verantwortung pro Steuerelement. Der Aktions Pivot ist neu im Compliance-Manager (Preview) und soll eine optimierte Übersicht über alle von Microsoft empfohlenen Aktionen bieten.

### <a name="controls"></a>Steuerelemente

Steuerelemente können im Steuerelement-Info-Dashboard angezeigt werden. Steuerelemente stellen die Anforderungen aus Standard, Zertifizierung, Regulierung oder Framework dar. Um diese Anforderungen über mehrere Standards, Verordnungen usw. hinweg zuzuordnen und Aktionen zuzuordnen, wird alles so behandelt, als ob es sich um ein Steuerungsframework handeln würde. Beispielsweise sind wie ein Steuerelement Framework Regeln wie HIPAA nach Abschnitt aufgeschlüsselt worden, und die HIPAA-Steuerelemente im Compliance-Manager verwenden dasselbe Nummernschema wie in den folgenden Abschnitten dargestellt:

![Details zu Compliance-Manager-Microsoft-Steuerelementen](media/compliance-manager-control-details.png)

Es gibt drei Arten von Steuerelementen. Zwei von Microsoft werden in den integrierten Vorlagen bereitgestellt, und die dritte wird von Kunden in benutzerdefinierten Vorlagen erstellt und verwaltet. Die drei Typen sind:

1. Von **Microsoft verwaltete Steuerelemente (mm):** Dies sind Steuerelemente, für die nur Microsoft zuständig ist. Sie werden in den in-Box-Vorlagen angezeigt und werden dem Compliance-Manager von Microsoft hinzugefügt.
2. Vom **Kunden verwaltete Steuerelemente (cm):** Dies sind Steuerelemente, für die nur Kunden verantwortlich sind. Sie werden in den in-Box-Vorlagen angezeigt und werden dem Compliance-Manager von Microsoft oder Kunden hinzugefügt. Der Kunde kann auch von Microsoft bereitgestellte vom Kunden verwaltete Steuerelemente bearbeiten oder deaktivieren.
3. **Shared Controls (SM):** Dies sind Steuerelemente, bei denen Verantwortung zwischen Microsoft und dem Kunden freigegeben wird. Diese werden in den in-Box-Vorlagen angezeigt und werden dem Compliance-Manager von Microsoft hinzugefügt.

### <a name="actions-items"></a>Aktionen Elemente

Aktionen Elemente sind die empfohlenen Aufgaben zum Implementieren der Anforderungen einer Norm oder einer Verordnung oder zum Testen, überprüfen und Dokumentieren der Implementierungsanforderungen Ihrer Organisation. Aktionen sind einem oder mehreren Steuerelementen zugeordnet. Jedem Steuerelement ist eine oder mehrere Aktionen zugeordnet, und jede Aktion kann einem oder mehreren Steuerelementen zugeordnet werden. Aktionen sind Teil des Haupt Workflows im Compliance-Manager (Preview), da es sich um Objekte handelt, die von Ihrer Organisation zugewiesen, verfolgt und überprüft werden.

#### <a name="assign-action-items"></a>Zuweisen von Aktionselementen
  
1. Wählen Sie im Dashboard **Aktionselemente** die **Gruppe** aus, die die Bewertung (en) enthält, deren Aktion Sie zuweisen möchten.
2. Wählen Sie in der Dropdownliste **Bewertung** die Bewertung aus, deren Aktion Sie zuweisen möchten, oder wählen Sie im Dropdownmenü **alle** Optionen aus, um alle verfügbaren Aktionen anzuzeigen.
3. Suchen Sie die Aktion, die Sie zuweisen möchten, und wählen Sie in der Spalte **Besitzer** den Link zur **Überprüfung**, **Implementierung** oder **Test**aus.
4. Wählen Sie das Feld **Benutzer zuweisen** aus, und eine Liste der Benutzer in Ihrer Organisation wird angezeigt. Scrollen Sie in der Liste, und wählen Sie Benutzer oder Filtern Sie die Liste aus, um einen Benutzer auszuwählen, indem Sie den Namen des Benutzers eingeben.
5. Geben Sie im Feld Anmerkungen zur Implementierung alle Notizen ein, die Sie dem zugewiesenen Benutzer übermitteln möchten.
6. Wählen Sie **Speichern** aus, um die Aktion zuzuweisen.

#### <a name="reassign-action-items"></a>Aktionselemente neu zuweisen

Mit dieser Funktion kann eine Organisation alle aktiven oder ausstehenden Abhängigkeiten des Benutzerkontos entfernen, indem eine Aktion einem neuen Benutzer zugewiesen wird.

1. Wählen Sie im Dashboard **Aktionselemente** die **Gruppe** mit den Bewertungen aus, deren Aktion Sie neu zuweisen möchten.
2. Wählen Sie im Dropdown-Menü **Bewertung** die Bewertung aus, deren Aktion Sie neu zuweisen möchten, oder wählen Sie **alle** in der Dropdownliste aus, um alle verfügbaren Aktionen anzuzeigen.
3. Suchen Sie nach der Aktion, die Sie neu zuweisen möchten, und wählen Sie in der Spalte **Besitzer** den Link zur **Überprüfung**, **Implementierung**oder **Test**aus.
4. Löschen Sie den vorhandenen Benutzer aus dem Feld **Benutzer zuweisen** , und wählen Sie entweder einen anderen Benutzer in der Liste der Benutzer aus, oder Filtern Sie die Liste, um einen Benutzer auszuwählen, indem Sie den Namen des Benutzers eingeben.
5. Geben Sie im Feld Anmerkungen zur Implementierung alle Notizen ein, die Sie dem Benutzer übermitteln möchten.
6. Wählen Sie **Speichern** aus, um die Aktion neu zuzuweisen.

## <a name="templates"></a>Vorlagen

Eine Vorlage ist das Basisobjekt im Compliance-Manager (Preview), das einem Produkt und einer Zertifizierung (beispielsweise Standard, Regulierung, Steuerelement Framework usw.) zugeordnet ist. Vorlagen können angezeigt und aus dem Dashboard Vorlagen hinzugefügt werden.

![Microsoft Template-Dashboard für Compliance-Manager](media/compliance-manager-template-dashboard.png)
 
Das Dashboard zeigt jede Vorlage zusammen mit der Zertifizierung und dem Produkt, das der Vorlage zugeordnet ist, den Datumsangaben, an denen die Vorlage erstellt und zuletzt geändert wurde, die Anzahl der von Kunden und von Microsoft verwalteten Steuerelemente, die maximale Konformitätsbewertung für den Vorlage und den Status der Vorlage (beispielsweise genehmigt, ausstehende Genehmigung, importiert).

Die integrierten Vorlagen verfügen jeweils über eine integrierte Bewertung, aber Sie können zusätzliche Bewertungen basierend auf integrierten Vorlagen erstellen, und Sie können eigene Vorlagen importieren und benutzerdefinierte Bewertungen basierend auf diesen erstellen.

### <a name="create-a-template"></a>Erstellen einer Vorlage

Sie können eine Vorlage erstellen, indem Sie eine vorhandene Vorlage kopieren oder eine benutzerdefinierte Vorlage importieren. Es gibt ein bestimmtes Format und Schema, das für Vorlagendaten verwendet werden muss, oder es wird nicht in den Compliance-Manager importiert. Eine Datei mit den richtigen Schema-und Beispieldaten kann hier heruntergeladen werden.
Jede benutzerdefinierte Vorlage sollte sich in einer separaten Excel-Arbeitsmappe (im XLS-oder XLSX-Format) befinden, die fünf Registerkarten enthält:

1. Vorlage – Bewertung
2. ControlFamily
3. Aktionen
4. Besitz
5. Maße

Das Schema, das innerhalb der einzelnen Registerkarten verwendet wird, ist unten aufgeführt.

#### <a name="template-assessment-tab"></a>Registerkarte "Vorlagen Bewertung"

Diese Registerkarte hat eine einzelne Spalte:

- **inScopeServices**: durch trennzeichengetrennte Liste von Produkten oder Diensten, die im Bereich der Vorlage liegen.

#### <a name="controlfamily-tab"></a>Registerkarte "ControlFamily"

Diese Registerkarte enthält Spalten, die die Steuerelemente definieren, die den auf der Registerkarte Aktionen aufgeführten Aktionen zugeordnet sind, und enthält Details wie Steuerelementname, Familie, Titel und Beschreibung.  Die Spalten für diese Registerkarte, die innerhalb von Excel in der unten aufgeführten Reihenfolge sortiert werden müssen, lauten wie folgt: 

- **Steuer Elementname:** Steuerelementname aus Zertifizierung/Norm/Regulierung usw.
- **controlFamily:** Kontroll Familie aus Zertifizierung/Standard, Regulierung usw.
- **controlTitle:** Kontroll Titel aus Zertifizierung/Norm/Regulierung usw.
- **controlDescription:** Kontroll Beschreibung aus Zertifizierung/Norm/Regulierung usw.
- **controlVersion:** Optionale Steuerelement Versionsinformationen.  Beispiel: für NIST 800-53 ist der aktuelle Wert Rev 4, sodass der controlVersion 4 ist.  Für CSA ccm ist es 3.0.1.
- **isDisabled:** Verwenden Sie true oder false, um anzugeben, ob das Steuerelement deaktiviert wurde.
- **ControlType:** Verwenden Sie cm, um anzugeben, dass es sich um vom Kunden verwaltete Steuerelemente handelt.
- **controlComplianceScore:** Summe der Punktzahl aller Aktionen, die dem Steuerelement zugewiesen sind.
- **controlActionTitle:** Doppelte durch Semikolons getrennte Liste aller actionTitles für dieses Steuerelement, wie auf der Registerkarte Aktionen aufgeführt. 

#### <a name="actions-tab"></a>Registerkarte "Aktionen"

Diese Registerkarte enthält Spalten, die einzelne Aktionen definieren, und enthält Details wie Aktionstitel, Besitz und Dimensionen. Die Spalten für diese Registerkarte, die innerhalb von Excel in der unten aufgeführten Reihenfolge sortiert werden müssen, lauten wie folgt: 

- **actionTitle:** Titel der Aktion. Jeder Titel muss eindeutig sein, und wir empfehlen die Verwendung von Pascal Case.
- **actionRelatedODVs:** Doppelte durch Semikolons getrennte Liste von actionTitles, die übergeordnete Elemente des in der actionTitle-Spalte aufgeführten untergeordneten Elements sind. In einer Parent/Child-Beziehung stellt das übergeordnete Element das hohe Wasserzeichen dar. Wenn Sie also eine übergeordnete Aktion ausführen, werden auch alle untergeordneten Aktionen ausgeführt. Wenn Sie beispielsweise über ähnliche Anforderungen, aber unterschiedliche Standardwerte verfügen, beispielsweise die Kennwortlänge, wobei eine Norm/Regel mindestens 15 Zeichen erfordert und eine andere mindestens 12 oder 10. 15 wäre in diesem Beispiel das übergeordnete Element, und wenn Sie mindestens 15 Zeichen konfigurieren, erfüllen Sie auch die Aktionen, die 12 oder 10 Zeichen in anderen Bewertungen empfehlen.

    > [!NOTE]
    > Die actionRelatedODVs-Spalte ist eine erforderliche Spalte für das Schema; Das Feature (zugehörige Aktionen) steht jedoch im Compliance-Manager (Preview) nicht zur Verfügung.  Es ist geplant, in einer späteren Version hinzugefügt zu werden.

- **actionDimensionValues:** Doppelte durch Semikolons getrennte Liste der entsprechenden Dimensionen auf der Registerkarte Dimensionen mit folgendem Format:

    ```
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    Beispiel:

    ```
    Product::Office 365;;Certification::NIST CSF
    ```

    Alle Dimensionen, die in einer benutzerdefinierten Vorlage verwendet werden, müssen auf der Registerkarte Dimensionen der Importdatei aufgeführt werden, auch wenn diese bereits im Dashboard Dimensionen aufgeführt sind. Wenn Sie neue Dimensionsschlüssel oder-Werte hinzufügen, müssen Sie diese zuerst dem Dimensions-Dashboard hinzufügen.
- **actionScore:** Numerischer Wert für jede Aktion, der die Bewertung für diese Aktion darstellt. Es wird empfohlen, das von den integrierten Bewertungen verwendete Bewertungsmodell zu verwenden, das auf dem Zweck und der Erzwingung der einzelnen Aktionen basiert.
- **actionOwnership:** Doppelte durch Semikolons getrennte Liste der Besitzer. Alle aufgeführten Besitzer müssen auf der Registerkarte "Besitz" enthalten sein.
- **actionDescription:** Text jeder Aktion, die eindeutig sein muss. Dieses Feld unterstützt die unten beschriebene Absprache.

#### <a name="ownership-tab"></a>Registerkarte "Besitz"

Diese Registerkarte enthält Spalten, die die Besitzer für jede Aktion definieren.  Die Spalten für diese Registerkarte, die innerhalb von Excel in der unten aufgeführten Reihenfolge sortiert werden müssen, lauten wie folgt:

- **Eigentümername:** Eindeutiger Name des Besitzers/der verantwortlichen Partei.
- **ownershipDescription:** Beschreibung des Besitzers/der verantwortlichen Partei.

#### <a name="dimensions-tab"></a>Registerkarte Dimensionen

Diese Registerkarte enthält Spalten, in denen die Dimensionen definiert werden, die einer Aktion zugeordnet werden können.  Die Spalten für diese Registerkarte, die innerhalb von Excel in der unten aufgeführten Reihenfolge sortiert werden müssen, lauten wie folgt:

- **dimensionKey:** Liste der für Dimensionen verwendeten Schlüssel. Beispielsweise Produkt, Zertifizierung usw.
- **dimensionvalue:** Eindeutiger Wert für jeden Dimensionsschlüssel. Beispielsweise Office 365, InTune, Azure, benutzerdefiniertes Produkt usw.
- **allowMultiSelect:** Verwenden Sie true oder false, um anzugeben, dass mehrere Dimensionswerte für einen einzelnen Dimensionsschlüssel ausgewählt werden können.

#### <a name="using-markdown-language-in-description-fields"></a>Verwenden von Abzugs Sprache in Beschreibungsfeldern

Vorlagen und Bewertungen unterstützen die Verwendung von Abschriften Sprache für einige Textelemente und Formatierungen.  Es gibt drei Formatierungselemente der Abzugs Sprache, die im Compliance-Manager verwendet werden:

- Aufzählungszeichen und nummerierte Listen
- Hyperlinks
- Fettdruck

Aufzählungszeichen werden als Sternchen anstelle von Word-oder Excel-Aufzählungszeichen dargestellt. Beispiel:

```
* Item A
* Item B
* Item C
```

Zahlen werden als Zahlen dargestellt, jedoch mit Leerzeichen für Einzug (drei Leerzeichen pro Ebene) und nur für alle Unterebenen (beispielsweise keine Buchstaben).  Beispiel:
   1. Element A
   2. Element B
      1. Unterelement A
      2. Unterelement B
   3. Element C
   4. Element D
      1. Unterelement A
      2. Unterelement B
   5. Element E

Hyperlinks werden durch Platzieren von Klammern um den Hyperlinktext und den Hyperlink selbst in Klammern unmittelbar neben der schließenden Klammer erstellt.  Beispiel:

```
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
Dieser Text wird wie folgt gerendert: Klicken Sie [hier](https://www.microsoft.com) , um zur Startseite von Microsoft zu gelangen.
Wie im obigen Beispiel dargestellt, rendert Compliance Manager keine URLs mit Unterstreichung.

Fett formatierter Text ist nur zwei Sternchen auf jeder Seite des Texts, der fett formatiert werden soll.  Beispiel:

```
**This text will render in bold**
```
**Dieser Text wird fett dargestellt**

### <a name="create-a-template"></a>Erstellen einer Vorlage

Sie können eine Vorlage erstellen, indem Sie eine vorhandene Vorlage kopieren oder Vorlagendaten aus Excel importieren. Beim Importieren von Daten aus Excel benötigt die Vorlage zwei verschiedene Compliance-Manager-Administratoren, um die Daten zu veröffentlichen (eine zur Veröffentlichung und eine, die genehmigt werden soll).

#### <a name="create-a-template-by-copying-an-existing-template"></a>Erstellen einer Vorlage durch Kopieren einer vorhandenen Vorlage

1. Öffnen Sie das Dashboard **Vorlagen** , und wählen Sie **+ Vorlage hinzufügen**aus.
2. Geben Sie im Feld **Vorlagenname eingeben** einen eindeutigen Namen für die Vorlage ein.
3. Aktivieren Sie das Kontrollkästchen **Kopie von einer vorhandenen Vorlage** , und wählen Sie die Vorlage aus der Dropdownliste aus, die Sie kopieren möchten.
4. Optional können Sie zusätzliche Bemaßungen hinzufügen.
5. Wählen Sie **zum Dashboard hinzufügen**aus.

#### <a name="create-a-template-by-importing-data"></a>Erstellen einer Vorlage durch Importieren von Daten

1. Öffnen Sie das Dashboard **Vorlagen** , und wählen Sie **+ Vorlage hinzufügen**aus.
2. Geben Sie im Feld **Vorlagenname eingeben** einen eindeutigen Namen für die Vorlage ein.
3. Fügen Sie eine oder mehrere Dimensionen hinzu. Selbst wenn die Dimensionen, die Sie verwenden, bereits im Dimensions-Dashboard aufgeführt sind, müssen Sie weiterhin in der Importdatei aufgeführt werden.
4. Wählen Sie **Durchsuchen** aus, um zum Speicherort der Importdatei zu navigieren, wählen Sie Sie aus, und wählen Sie **Öffnen**aus.
5. Die Importdatei wird überprüft und gibt die Anzahl der Steuerelemente und Kontroll Familien an, die erkannt wurden. Wenn Fehler vorliegen, wird eine Verknüpfung für eine geänderte Version der Importdatei bereitgestellt, die Fehlerdetails enthält. Alle Fehler müssen aufgelöst werden, bevor die Daten importiert werden.
6. Nachdem die Daten validiert wurden, wählen Sie **zum Dashboard hinzufügen**aus.
7. Die importierte Vorlage wird im Dashboard **Vorlagen** angezeigt und hat den Status **importiert**. Wählen Sie die Ellipsen (...) aus, und wählen Sie **veröffentlichen** aus, um die Vorlage zu veröffentlichen. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **veröffentlichen**aus. Der Vorlagenstatus wird in **Ausstehende Genehmigung**geändert.
8. Ein anderer Benutzer mit der Rolle Compliance-Manager-Administrator muss die Vorlage im Dashboard Vorlagen genehmigen. Sie müssen die Ellipsen (...) auswählen und **genehmigen**auswählen. Wenn die Bestätigungsmeldung angezeigt wird, wählen Sie **genehmigen**aus. Die Vorlage kann nun verwendet werden.

### <a name="customize-a-template"></a>Anpassen einer Vorlage

Vorlagen können mithilfe der zusätzlichen benutzerdefinierten Steuerelemente angepasst werden. Alle benutzerdefinierten Steuerelemente werden als vom Kunden verwaltete Steuerelemente betrachtet.

#### <a name="add-a-custom-control-to-a-template"></a>Hinzufügen eines benutzerdefinierten Steuerelements zu einer Vorlage

1. Öffnen Sie die **Vorlage** , die Sie ändern möchten.
2. Wählen Sie + benutzerdefiniertes Steuerelement **Hinzufügen** .
3. Wählen Sie in der Dropdownliste eine **Steuerelement Familie** aus, oder geben Sie eine neue Steuerelement Familie ein, falls Sie nicht vorhanden ist.
4. Geben Sie im Feld **Steuerelement-ID** einen eindeutigen Namen oder eine eindeutige ID für das Steuerelement an.
5. Geben Sie im Feld **Titel** den Titel des Steuerelements an.
6. Geben Sie im Feld **Beschreibung** die Anforderungen und andere Informationen für das Steuerelement an.
7. Klicken Sie auf **Kunden Aktion zuweisen** .
8. Suchen Sie die Aktion (en), die Sie dem Steuerelement zuweisen möchten:
    - Verwenden Sie **Filter nach Dimension** , um Dimensionen zu verwenden, die den Aktionen zugewiesen sind, um Sie zu suchen und aufzulisten.
    - Verwenden Sie den **Filter nach Besitzer** , um die der Aktion zugewiesenen Besitzer (n) zu verwenden, um Sie zu suchen und aufzulisten.
    - Wählen Sie im Dropdownmenü einen **Aktionstyp** aus, um Aktionen nach Typ aufzulisten.
    - Geben Sie den Titel der zu suchenden Aktion ein, und führen Sie eine Liste aus.
9. Anhand der Kriterien in Schritt 8 wird eine Liste der **übereinstimmenden Aktion (en)** angezeigt. Wählen Sie die erste Aktion aus, die Sie dem Steuerelement zuweisen möchten.
10. Die Details der Aktion werden angezeigt. Wählen Sie die **Beschreibung** aus, die Sie verwenden möchten, und klicken Sie auf **Fertig**.
11. Wiederholen Sie die Schritte 9 und 10 für jede zusätzliche Aktion, die Sie zuweisen möchten.
12. Wenn alle anwendbaren Aktionen ausgewählt wurden, wählen Sie **zuweisen**aus.
13. Wählen Sie **Speichern** aus, um das neue Steuerelement zu speichern.

### <a name="export-a-template-to-json"></a>Exportieren einer Vorlage in JSON

Compliance-Manager (Preview) unterstützt auch das Exportieren von Vorlagen in JavaScript Object Notation (JSON) Format. Auf diese Weise können Sie Compliance-Manager-Daten mit anderen Systemen austauschen, die JSON unterstützen.

## <a name="reports"></a>Berichte

Sie können eine Bewertung in eine Excel-Datei für Compliance-Beteiligte in Ihrer Organisation oder für externe Prüfer und Regulierer exportieren. Der Bericht ist eine Momentaufnahme der Bewertung zum Datum und zur Uhrzeit des Exports. Der Bericht enthält die Details für Microsoft und von Kunden verwaltete Steuerelemente für die Bewertung, den Status der Implementierung, das Kontrolltest Datum, Testergebnisse und Links zu hochgeladenen Beweisdokumenten. Sie sollten Bewertungen exportieren, bevor Sie Sie archivieren, da Archivierte Bewertungen keine Links zu hochgeladenen Dokumenten beibehalten.

### <a name="export-an-assessment"></a>Exportieren einer Bewertung

1. Wählen Sie im Compliance-Manager-Dashboard die Registerkarte **Steuerelemente Info** aus.
2. Wählen Sie die Gruppe und die Bewertung in den Dropdownmenüs für die Bewertung aus, die Sie exportieren möchten.
3. Wählen Sie exportieren aus. Der Bewertungsexport wird als Excel-Datei heruntergeladen.

![Kompatibilitäts-Manager-Bewertung – Excel-Bericht](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a>Berechtigungen

In der folgenden Tabelle werden die einzelnen Compliance-Manager-Berechtigungen beschrieben, und welche Aktionen der Benutzer zulässt. Die Tabelle gibt auch die Rolle an, der jede Berechtigung zugewiesen ist.

||**Compliance Manager Reader**|**Compliance Manager Contributor**|**Compliance Manager Assessor**|**Compliance Manager Administrator**|**Portal Admin**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Daten lesen:** Benutzer können Daten lesen, aber nicht bearbeiten (außer für Vorlagendaten und Mandantenverwaltung).  <br> | X | X | X | X  | X |
|**Bearbeiten von Daten:** Benutzer können alle Felder mit Ausnahme der Felder Testergebnis und Test Datum bearbeiten (außer für Vorlagendaten und Mandantenverwaltung).  <br> || X | X  | X | X |
|**Bearbeiten von Testergebnissen:** Benutzer können die Felder Testergebnis und Test Datum bearbeiten.  <br> ||| X | X | X |
|**Verwalten von Bewertungen:** Benutzer können Bewertungen erstellen, archivieren und löschen.  <br> |||| X | X |
|**Verwalten von Masterdaten:** Benutzer können Vorlagendaten und Mandanten Verwaltungsdaten anzeigen, bearbeiten und löschen.  <br> |||| X | X |
|**Verwalten von Benutzern:** Benutzer können andere Benutzer in Ihrer Organisation zu den Rollen Leser, Mitwirkenden, Assessoren und Administrator hinzufügen. Nur Benutzer mit der globalen Administrator Rolle in Ihrer Organisation können Benutzer aus der Portal Administratorrolle hinzufügen oder entfernen.  <br> ||||| X |

### <a name="guest-access"></a>Gastzugriff
  
Nachdem der Zugriff auf den Compliance-Manager konfiguriert wurde, befindet sich jeder Benutzer, der über keine bereitgestellte Rolle verfügt, standardmäßig in der Rolle " **Gastzugriff** " (Dies ist auch die Erfahrung aller nicht von der Organisation bereitgestellten Konten wie persönliche Microsoft-Konten). Gastzugriffs Benutzer haben nicht Vollzugriff auf alle Compliance-Manager-Funktionen. Sie können keine der Kompatibilitätsbewertungsdaten der Organisation sehen, jedoch können Sie den Compliance-Manager verwenden, um die Kompatibilitäts Bewertungsberichte und Dienst Vertrauensstellungs Dokumente von Microsoft anzuzeigen.