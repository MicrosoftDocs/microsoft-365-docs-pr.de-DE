---
title: Verwalten von Anträgen auf Antragstellerrechte in der Microsoft-Datenschutzverwaltung (Vorschau)
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
description: Die Lösung zur Anforderung von Betreffrechten in Microsoft Privacy Management hilft Ihnen bei der Suche nach personenbezogenen Daten und der Zusammenarbeit bei der Überprüfung von Inhalten und dem Erstellen von Berichten.
ms.openlocfilehash: b266708c97ee4b81af6ba61dfa6716c57ff6026e
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419775"
---
# <a name="manage-subject-rights-requests-in-privacy-management-preview"></a>Verwalten von Anträgen auf Rechte von Antragstellern in der Datenschutzverwaltung (Vorschau)

In diesem Artikel erfahren Sie, wie Sie die Lösung zur Anforderung von Betreffrechten verwenden, um **personenbezogene Daten** in Ihrer Umgebung zu finden, **an Rezensionen zusammenzuarbeiten,** **Berichte** zu erstellen und wichtige Aufgaben **zu automatisieren.**

## <a name="purpose-of-subject-rights-requests"></a>Zweck von Anträgen auf Rechte von Antragstellern

Die Datenschutzverwaltung bietet leistungsstarke Funktionen für Anträge betroffener Personen, mit denen Sie Anfragen von Personen bearbeiten können, die ihre personenbezogenen Daten innerhalb Ihrer Organisation verwalten möchten. Diese Anforderungen werden manchmal auch als Anträge betroffener Personen , Anträge betroffener Personen auf Zugriff oder Verbraucherrechte bezeichnet. Das Datenschutzmanagement ermöglicht Es Mitarbeitern, die für die Erfüllung von Anträgen auf Rechte betroffener Personen verantwortlich sind, die betroffenen Personen leicht zu identifizieren und ihre persönlichen Informationen zwischen den Daten Ihrer Organisation in Exchange, SharePoint, OneDrive und Teams zu finden.

Die Datenschutzverwaltung ist einzigartig in der Lage, Ihnen zu helfen, Elemente zu priorisieren, die sie innerhalb der Daten überprüfen, die Sie für diese Anforderungen sammeln. Die Lösung ist sich der Microsoft Information Protection Vertraulichkeitsbezeichnungen bewusst, die auf Inhalte hinweisen, die potenziell vertraulich sind und eine besondere Überprüfung erfordern können, und kennzeichnet Elemente mit diesen Bezeichnungen. Weitere Informationen zu Vertraulichkeitsbezeichnungen finden Sie unter [Informationen zu Vertraulichkeitsbezeichnungen.](sensitivity-labels.md) Darüber hinaus kann die Datenschutzverwaltung Elemente erkennen und kennzeichnen, die die Daten mehrerer Personen enthalten, bei denen Sie möglicherweise Inhalte bearbeiten müssen, bevor Sie sie der betroffenen Person zur Verfügung stellen.

Nachdem Daten gesammelt und ausgewertet wurden, können Sie die relevantesten Elemente auswählen, die in Ihre Berichte und Exporte aufgenommen werden sollen, und sicher mit anderen Teammitgliedern zusammenarbeiten, um die Anforderungen in Richtung Abschluss zu verschieben.

## <a name="get-started-with-subject-rights-requests"></a>Erste Schritte mit Anträgen auf Antragstellerrechte

Die Datenschutzverwaltung stellt einen zentralen Hub für Ihre Datenschutzadministratoren bereit, um Anträge betroffener Personen zu bearbeiten, die Ihre Organisation erhalten hat.

Um mit der Behandlung eines neuen Anforderungsfalls zu beginnen oder an einer laufenden Anforderung zu arbeiten, besuchen Sie die Hauptseite **für Anträge betroffener Personen.** Es bietet eine visuelle Übersicht über die Fälle, die Ihr Team in der Datenschutzverwaltung erstellt hat, deren Status (aktiv, geschlossen oder überfällig) und die Anforderungstypen sowie eine filterbare Liste aller Anforderungen. Auf dieser Seite können Sie auch eine neue Anforderung öffnen.

Wenn Sie Details zu offenen Fällen anzeigen möchten, wählen Sie eine beliebige Anforderung in der Liste aus, und wählen Sie **"Zum Anfordern von Details"** aus. Weitere Informationen finden Sie unter [Überprüfen und Ergreifen von Maßnahmen für Anforderungen.](#review-and-take-action-on-requests)

Informationen zum Öffnen einer neuen Anforderung finden Sie unter [Erstellen einer Anforderung.](#create-a-request)

## <a name="create-a-request"></a>Erstellen einer Anforderung

Administratoren der Rechteverwaltung können den Assistenten für die Datenschutzverwaltung verwenden, um Anforderungen zu erstellen. Der Assistent führt Sie durch den Prozess der Suche nach personenbezogenen Daten über eine betroffene Person und deren Erfüllung.

Die vier Hauptschritte umfassen Folgendes.

### <a name="identify-the-data-subject"></a>Identifizieren der betroffenen Person

Geben Sie den Namen des Antragstellers an, der die Anforderung gestellt hat, und geben Sie deren Beziehung zu Ihrem Unternehmen an.

### <a name="select-the-request-type"></a>Auswählen des Anforderungstyps

Wählen Sie einen Anforderungstyp basierend auf dem, was die betroffene Person mit ihren Daten tun möchte. Wenn sich ihr Antrag auf eine bestimmte Datenschutzbestimmungen bezieht, können Sie sie auch aus einer bereitgestellten Liste auswählen, um mehr Kontext hinzuzufügen. Das Festlegen eines Stichtags (erforderlich) erleichtert die Sortierung nach eingehenden oder überfälligen Anforderungen und deren zeitnahe Lösung. Anforderungstypen umfassen:

- **Zugriff:** Bietet eine Zusammenfassung der persönlichen Informationen der betroffenen Person, die von Ihrer Organisation in Microsoft 365 gespeichert sind.
- **Export:** Enthält eine Zusammenfassung und einen Export der persönlichen Informationen der betroffenen Person, die während der Überprüfung erfasst und kommentiert werden.
- **Markierte Liste für die Nachverfolgung:** Generiert eine Zusammenfassung der Dateien, die möglicherweise zusätzliche Maßnahmen außerhalb der Datenschutzverwaltung erfordern. Ein Beispielszenario kann sein, wenn Sie die Löschung der personenbezogenen Daten der betroffenen Person gemäß deren Anforderung vereinfachen müssen.

### <a name="confirm-the-request-name"></a>Bestätigen des Anforderungsnamens

In diesem Schritt können Sie den Namen dieser Anforderung bestätigen und eine optionale Beschreibung als Referenz hinzufügen.

### <a name="review-and-finish"></a>Überprüfen und fertig stellen

Eine Zusammenfassung der Eingaben, die Sie in den vorherigen Schritten eingegeben haben. Jedes Feld kann bearbeitet werden, bevor Sie **"Anforderung erstellen"** auswählen.

Auf dieser Ebene können einige Eigenschaften bearbeitet werden, nachdem die Anforderung erstellt wurde, einschließlich Stichtag, Anforderungsname und Beschreibung, aber wichtige Eigenschaften wie die Identität des Betreffs können nicht geändert werden. Um eine vorhandene Anforderung zu bearbeiten, suchen Sie sie in Ihrer Liste der Anforderungen auf der Seite "Anforderungen für Antragstellerrechte", und verwenden Sie die Aktion **"Anforderungsdetails bearbeiten".**

## <a name="review-and-take-action-on-requests"></a>Überprüfen und Ergreifen von Maßnahmen für Anforderungen

Nachdem eine Anforderung geöffnet wurde, beginnt die Datenschutzverwaltung mit der Suche ihrer Microsoft 365 Daten, um Daten zu Ihrem Betreff zu finden. Um die ersten Ergebnisse anzuzeigen, wählen Sie diese Anforderung in der Liste aus, und wählen Sie **"Zum Anfordern von Details wechseln"** aus. Hier erfahren Sie mehr über die Eigenschaften der Anforderung, die Suchergebnisse und den Status der Anforderung. Diese Seite wird auch zu Ihrem Hub, um an der Verwaltung der gefundenen Dateien, dem Erstellen von Berichten und Exporten und dem Abschließen der Anforderung zu arbeiten und zusammenzuarbeiten.

Zu den Kacheln auf dieser Seite gehören:

- **Details:** Die wichtigsten Details zu der Anforderung, einschließlich des Stichtags und des Anforderungsdatums, der Beschreibung und der zugehörigen Datenschutzbestimmungen.
- **Fortschritt:** Eine Zeitachse, die die abgeschlossenen Schritte und alle noch zu erledigenden Aufgaben angibt.
- Zusammenfassung der **Datenvorschau:** Eine Übersicht über die in Ihrer Suche ausgewerteten Daten. Weitere Informationen zu diesen Informationen finden Sie unter Anzeigen und Bearbeiten von Suchabfragen.
- **Zu überprüfende Prioritätselemente:** Falls zutreffend, werden Informationen zu wichtigen Elementen angezeigt, die von der Datenschutzverwaltung für Sie erkannt wurden, einschließlich vertraulicher Informationen, die bereits eine Microsoft-Vertraulichkeitsbezeichnung aufweisen, oder Elementen mit Daten über mehrere Personen, die möglicherweise eine Redigierung erfordern. Prioritätselemente finden Sie unter Daten, die durch Filtern nach der Spalte "Prioritätstypen" gesammelt werden.

### <a name="monitor-progress-and-complete-requests"></a>Überwachen des Fortschritts und Abschließen von Anforderungen

Anträge von Antragstellerrechten durchlaufen auf dem Weg zum Abschluss mehrere Phasen. Einige Phasen werden automatisch ausgeführt, während die Datenverwaltung ihre Datenauswertung durchführt, und andere, wenn Antragstellerrechte Administratoren und Mitwirkende auffordern, wesentliche Schritte wie das Überprüfen, Auswählen und Bearbeiten von Dateien auszuführen.

Da Anforderungen möglicherweise im Laufe der Zeit oder von mehreren Mitwirkenden bearbeitet werden müssen, bietet das Datenschutzmanagement kontinuierliche Updates zum Status einer Anforderung und Anleitungen zu den nächsten schritten. Diese Updates können auf der Übersichtsseite der Anforderung für Antragstellerrechte angezeigt werden. Die Statusphasen umfassen Folgendes.

#### <a name="data-estimate"></a>Datenvoranschlag

Die Datenvorkalkulation ist die Anfangsphase der Datenauswertung. Nachdem eine Anforderung erstellt wurde, identifiziert die Datenschutzverwaltung, wie viele Elemente in den Daten Ihrer Organisation potenzielle Übereinstimmungen mit Ihrer betroffenen Person enthalten, und notiert, wo sich diese Elemente in Microsoft 365 befinden. Sobald die Datenvorkalkulation abgeschlossen ist, können Sie eine Vorschau der Ergebnisse anzeigen und die Details Ihrer ursprünglichen Suchabfrage überprüfen. Wenn Sie Ihre Suchabfrage bearbeiten möchten, lesen Sie die Anweisungen unter Anzeigen und Bearbeiten von [Suchabfragen.](#view-and-edit-search-queries) Wenn Ihre ersten Ergebnisse zufriedenstellend aussehen, können Sie mit dem Abrufen von **Daten** fortfahren.

- Bis zu 10.000 einzelne Elemente können aus jeder Suche abgerufen werden. Dateien, die einem übereinstimmenden Element zugeordnet sind (z. B. Dateianlagen in einer E-Mail), können auf Ihre Gesamtsumme angerechnet werden. Wenn Ihre Suche den Schwellenwert für die Dateianzahl überschreitet, versuchen Sie, die Suche zu überarbeiten, um den Bereich zu verfeinern. Weitere Informationen finden Sie im Abschnitt "Anzeigen und Bearbeiten von [Suchabfragen".](#view-and-edit-search-queries) Sie können ihre Suchabfrage nicht mehr bearbeiten, nachdem Sie die Phase zum Abrufen von Daten initiiert haben.

#### <a name="retrieve-data"></a>Abrufen von Daten

Diese Phase weist darauf hin, dass die Datenverwaltung gerade dabei ist, Ihre Daten abzurufen. Nach Abschluss des Vorgangs wird automatisch die Überprüfung der **Daten** durchgeführt.

#### <a name="review-data"></a>Überprüfen von Daten

In dieser Phase sollten Ihre Mitwirkenden die Ergebnisse auf der Registerkarte "Gesammelte Daten" überprüfen. Zu den wesentlichen Schritten gehören:

- Wählen Sie aus, ob die identifizierten Elemente in Ihre Zusammenfassungen und/oder Exporte aufgenommen werden sollen. Wenn im Export oder Bericht keine gemeldete Übereinstimmung erforderlich ist, wählen Sie die Option "Ausschließen" aus. Wenn der Inhalt ein falsch positives Ergebnis zu sein scheint, können Sie "Keine Übereinstimmung" auswählen, um die Datei aus Ihren Endgültigen Berichten auszuschließen und das Element als etwas zu kennzeichnen, das von der Anforderung nicht hätte aufgenommen werden dürfen. Um den Status eines Elements festzulegen, verwenden Sie das Aktionsmenü (vertikale Ellipsen) neben seinem Namen, und wählen Sie ihre gewünschte Auswahl aus. Wenn Sie dazu aufgefordert werden, fügen Sie einen Hinweis für einen internen Verweis hinzu, um Ihre Entscheidung zu erläutern. Notizen sind erforderlich, wenn Dateien ausgeschlossen werden.
- Verwenden Sie die Option **"Tags anwenden",** um Elemente zu identifizieren, die Aufmerksamkeit erfordern. Die verfügbaren Tags umfassen vom System bereitgestellte Optionen, z. B. das Markieren eines Elements für die Nachverfolgung, und können benutzerdefinierte Tags enthalten, wie unter Einstellungen definiert.
- Verwenden Sie **Anmerkungen,** um Inlinemarkups oder -redactions für eine ausgewählte Datei zu erstellen. Wenn Sie z. B. eine Datei für eine Person einschließen müssen, die auch die persönlichen Informationen anderer enthält, können Sie die **Bereichsrotaktion** (unter der Zeichnungsschaltfläche in der Befehlsleiste) verwenden, um alle Informationen zu schwarz zu machen, die sich nicht auf die Person beziehen, die die Anforderung gestellt hat. Wenn Ihre Bearbeitungen abgeschlossen sind, wählen Sie "Einschließen" aus, um der Anforderung die bearbeitete Datei hinzuzufügen. Beachten Sie, dass die Anmerkung eine Kopie der Datei erstellt, sodass nichts in der Originaldatei geändert wird und an ihrem ursprünglichen Speicherort verbleibt. Die Kopie wird in Ihrem Azure-Blob gespeichert und verbleibt für die Dauer des angegebenen Datenaufbewahrungszeitraums. Weitere Informationen finden Sie unten unter ["Datenaufbewahrung".](#data-retention)
- Um Notizen zu einem Element zu überprüfen, wählen Sie es aus, und wechseln Sie zur Registerkarte "Dateinotizen". Sie können auch die Option "Dateinotiz hinzufügen" verwenden, um einen neuen Kommentar zu erstellen. Wenn Sie Notizen auf einer allgemeinen Fallebene überprüfen oder hinzufügen möchten, wechseln Sie zur Registerkarte "Notizen" oben, und verwenden **Sie "Fallnotiz hinzufügen".** Diese Hinweise sind für Benutzer sichtbar, die an der Anforderung arbeiten, werden jedoch nicht in den Finalbericht aufgenommen oder anderweitig für die betroffene Person freigegeben.

Wenn alle Elemente überprüft und deren Status festgelegt wurden, wählen Sie **"Vollständige Überprüfung"** aus, um einen Flyover-Bereich zu öffnen, in dem Sie eine Zusammenfassung der Daten überprüfen und alle relevanten Notizen hinzufügen können. Diese Hinweise dienen der internen Datensatzführung und werden nicht für die betroffene Person freigegeben. Wählen Sie "Überprüfung abschließen" erneut aus, um mit der nächsten Phase fortzusteigen. Zusammenfassungen Ihrer Entscheidungen werden später auf der Registerkarte "Berichte" bereitgestellt.

#### <a name="generate-reports"></a>Generieren von Berichten

Diese Phase gibt an, dass Ihre Berichte generiert werden. Wenn Sie fertig sind, finden Sie diese auf der Registerkarte **"Berichte".** Ihre fertig gestellten Dateien können zur Übermittlung an die betroffene Person exportiert werden, die den Antrag gestellt hat.

#### <a name="close-the-request"></a>Schließen der Anforderung

Wenn Sie die erforderlichen Aktionen ausgeführt haben, um ihre Anforderung zu Den Betreffrechten zu lösen, wählen Sie **"Anforderung schließen"** aus. Dadurch wird der endgültige Bericht erstellt, der verschlüsselt und auf der Registerkarte **"Berichte"** zur Verfügung gestellt wird. Je nach Anzahl der Dateien in der Anforderung kann dies eine Weile dauern.

### <a name="view-and-edit-search-queries"></a>Anzeigen und Bearbeiten von Suchabfragen

Wenn Sie detaillierte Informationen zur Datensuche hinter einer Anforderung für Betreffrechte anzeigen möchten, wählen Sie die Option **"Suchabfragedetails anzeigen"** auf der Datenvorkalkulationskarte aus. Dadurch wird ein Bereich geöffnet, in dem die Abfrage zusammengefasst und weitere Details dazu angezeigt werden, was gefunden wurde.

Hier haben Sie die Möglichkeit, **eine Vorschau** der Suchergebnisse anzuzeigen, um zu sehen, welcher Inhaltstyp für diese Abfrage zurückgegeben wird. Wenn Sie feststellen, dass Sie die Eigenschaften dieser Suche ändern möchten und die Phase "Daten abrufen" noch nicht begonnen haben, können Sie die **Suchabfrageoption** bearbeiten verwenden. Dieser Assistent bietet die Möglichkeit, Eigenschaften für die Identifizierung betroffener Personen, Ihre Suchfilter und -bedingungen sowie die Speicherorte für die Suche nach Daten (einschließlich Exchange, SharePoint, OneDrive und/oder Teams) zu ändern oder hinzuzufügen. Verwenden Sie diese Optionen, um den gewünschten Grad an Spezifität zu erreichen. Sie können die endgültige Version der neuen Abfrage überprüfen, bevor Sie auf **"Speichern"** drücken.

Wenn Sie die Bearbeitung der Suchabfrage abgeschlossen haben, wird eine neue Suche ausgeführt, um Ihre vorherigen Suchergebnisse zu ersetzen. Dadurch wird Der Status im Abschnitt "Fortschritt" auf den ersten Schritt, die Schätzung der **Daten,** zurückgesetzt. Die neue Suche kann bis zu 60 Minuten dauern. Sobald dies abgeschlossen ist, werden auf der Detailseite der Anforderung aktualisierte Ergebnisse angezeigt.

### <a name="data-retention"></a>Datenaufbewahrung

Berichte, die über dieses Tool generiert werden, und die zugehörigen Daten, z. B. in Azure gespeicherte Kommentierte Dateien, werden für einen bestimmten Zeitraum gespeichert. Diese Dauer wird auf globaler Ebene über **Einstellungen** im Abschnitt **"Datenaufbewahrungszeiträume"** definiert, sodass Sie zwischen 30 und 90 Tagen wählen können. Weitere Informationen finden Sie unter ["Erste Schritte mit der Datenschutzverwaltung".](privacy-management-setup.md)

## <a name="collaborate-on-requests-with-teams"></a>Zusammenarbeit an Anforderungen mit Teams

Das Datenschutzmanagement unterstützt die Zusammenarbeit über Microsoft Teams, damit Ihre Gruppe bei Anträgen auf Rechte von Antragstellern zusammenarbeiten kann. Wenn Sie eine neue Anforderung erstellen, wird automatisch ein Teams Kanal erstellt und ihrer Anforderung standardmäßig zugeordnet. Hier können Sie die Anforderung besprechen und Eingaben und Beiträge auf dem Weg zur Fertigstellung sicher teilen. Um an der Unterhaltung teilzunehmen, öffnen Sie Ihre Anforderung, und verwenden Sie die Option **"Mit Mitarbeitern chatten".** Dadurch werden Microsoft Teams geöffnet und Sie in den Kanal "Allgemein" für die Teamwebsite Ihrer Antragstellerrechte-Anforderung platziert.

Um die Liste der aktiven Mitarbeiter zu überprüfen, die Ihre Teamwebsite anzeigen und dazu beitragen können, öffnen Sie in Ihrer Anfrage zu den Betreffrechten die Registerkarte **"Mitarbeiter".** Um weitere Benutzer hinzuzufügen, die an dieser Anforderung zusammenarbeiten sollen, wählen Sie die Option zum Hinzufügen eines Mitarbeiters aus.

Um das Standardverhalten des Generierens von Teams Websites beim Erstellen einer Anforderung für Betreffrechte zu ändern, wählen Sie den **Einstellungen** Zahnrad in der oberen rechten Ecke der Seite zur Anforderung von Antragstellerrechten aus, und wählen Sie **Teams Zusammenarbeit** aus, um die Einstellung zu ändern.

Sie können auch die Option **"Freigeben"** in der oberen rechten Ecke innerhalb einer Anforderung für Betreffrechte verwenden, um Personen über Teams oder E-Mail einzugeben oder den Link zu der Seite in der Datenschutzverwaltung zu kopieren. Die Freigabe über Teams ermöglicht es Ihnen, eine vorhandene Teams-Website auszuwählen, die für Ihr Konto verfügbar ist, und einen bestimmten Kanal auf dieser Website auszuwählen, in dem der Link zu diesem Fall zusammen mit einer von Ihnen bereitgestellten Nachricht bereitgestellt wird.

## <a name="automate-subject-rights-request-tasks"></a>Automatisieren von Aufgaben zur Anforderung von Antragstellerrechten

Microsoft Power Automate ist ein Workflowdienst, der Aktionen über Anwendungen und Dienste hinweg automatisiert. Wenn Sie Power Automate Flüsse für die Datenschutzverwaltung aktivieren, können Sie wichtige Aufgaben für Fälle und Benutzer automatisieren. Weitere Informationen zu Power Automate finden Sie auf der [Dokumentationswebsite.](/power-automate/getting-started)

Kunden mit Microsoft 365 Abonnements, die datenschutzverwaltung enthalten, benötigen keine weiteren Power Automate Lizenzen, um die empfohlene Datenschutzverwaltung Power Automate Vorlagen zu verwenden. Diese Vorlagen können angepasst werden, um Ihre Organisation zu unterstützen und die wichtigsten Datenschutzverwaltungsszenarien abzudecken. Wenn Sie premium Power Automate Features in diesen Vorlagen verwenden, eine benutzerdefinierte Vorlage mit dem Microsoft 365 Compliance Connector erstellen oder Power Automate Vorlagen für andere Compliancebereiche in Microsoft 365 verwenden, benötigen Sie möglicherweise mehr Power Automate Lizenzen.

Die folgenden Power Automate Vorlagen sind in der Datenschutzverwaltung enthalten:

- **Erstellen eines Datensatzes für den Fall der Datenschutzverwaltung in ServiceNow:** Diese Vorlage richtet sich an Organisationen, die ihre ServiceNow-Lösung verwenden möchten, um Anfragen von Antragstellerrechten nachzuverfolgen. Sie werden aufgefordert, Ihre ServiceNow-Instanzdetails einzugeben. Sobald eine Verbindung mit Ihrer Instanz hergestellt wurde, können Administratoren von Antragstellerrechten einen Datensatz für den Fall in ServiceNow erstellen und anpassen, was die Vorlage bei Bedarf in ausgewählte Felder auffüllt. Weitere Informationen zum Connector finden Sie auf der Referenzseite des [ServiceNow-Connectors.](/connectors/service-now/)
- **Erstellen Sie eine Kalendererinnerung:** Diese Vorlage dient zum Festlegen von Fälligkeitsdatumserinnerungen in Ihrem Outlook Kalender für Anträge betroffener Personen. Das Tool füllt bestimmte Details für Sie aus den Eigenschaften der Anforderung auf, z. B. den Namen der Anforderung und das Fälligkeitsdatum. Sie können beschreibende Details hinzufügen, Empfänger angeben und andere erweiterte Einstellungen anpassen.

### <a name="create-a-new-power-automate-flow-from-a-template"></a>Erstellen eines neuen Power Automate Flusses aus einer Vorlage

Öffnen Sie zunächst die Antragstellerberechtigungsanforderung, mit der Sie arbeiten möchten, wählen Sie **"Automatisieren"** aus, und wählen Sie dann **Power Automate Flüsse** verwalten aus. Dadurch wird der Flyoutbereich Flows geöffnet. Verwenden Sie die Option "Neu", und wählen Sie die Vorlage aus den verfügbaren Optionen aus, die Sie verwenden möchten. Befolgen Sie von hier aus die Anweisungen, um das Setup abzuschließen.

Nachdem Sie eine Instanz der Vorlage gespeichert haben, müssen Sie sie auf der Detailseite der Anforderung für Betreffrechte ausführen, damit die Flussinstanz den richtigen Kontext und die richtige ID hat. Öffnen Sie die Anforderung, kehren Sie zum Menü **"Automatisieren"** zurück, wählen Sie die Vorlage aus, und wählen Sie **"Flow ausführen"** aus. Sie können Ihre früheren Aktivitäten anzeigen, indem Sie **"Aktivität zum Ausführen** des Flusses anzeigen" auswählen.

### <a name="share-a-power-automate-flow"></a>Freigeben eines Power Automate Flusses

Durch die Freigabe eines Power Automate Flusses können Sie einen anderen Besitzer hinzufügen und diesen das Bearbeiten, Aktualisieren und Löschen des Flusses ermöglichen. Alle Besitzer können auch auf den Ausführungsverlauf zugreifen und andere Besitzer hinzufügen oder entfernen. Um einen Fluss freizugeben, öffnen Sie die Anforderung zu Den Betreffrechten, mit der Sie arbeiten möchten, wählen Sie **"Automatisieren"** aus, und wählen Sie dann **Power Automate Flüsse** verwalten aus. In diesem Bereich können Sie einen vorhandenen Fluss auswählen und dann die Option "Freigeben" verwenden, um einen Benutzer oder eine Gruppe hinzuzufügen.

In diesem Bereich haben Sie auch die Möglichkeit, die eingebetteten Verbindungen mit Diensten zu verwalten, die im Power Automate-Fluss verwendet werden. Wenn Sie diese Einstellungen ändern, kann sich dies auf Die Ausführung des Flusses auswirken.

### <a name="edit-or-delete-power-automate-flow"></a>Bearbeiten oder Löschen Power Automate Flusses

Um Details eines Power Automate Flusses anzupassen, öffnen Sie die Anforderung für Betreffrechte, wählen Sie **Automatisieren** und dann **Power Automate Flüsse** verwalten aus. In diesem Bereich können Sie einen vorhandenen Fluss auswählen, um Details anzuzeigen. Verwenden Sie "Bearbeiten" in einem beliebigen Abschnitt, um die Eigenschaften zu ändern und dann zu speichern.

Um den Fluss vollständig zu entfernen, verwenden Sie die Option **"Löschen".** Er entfernt den Fluss für alle Besitzer und deinstalliert ihn für alle Benutzer. Frühere Flussinstanzen werden weiterhin ausgeführt, um Datenverluste zu vermeiden. Sie können Ihre Auswahl bestätigen, bevor der Löschvorgang abgeschlossen ist.

## <a name="data-matching"></a>Datenabgleich

Mit dem Datenabgleich können Organisationen die Datenschutzverwaltungslösung aktivieren, um betroffene Personen basierend auf genau angegebenen Datenwerten zu identifizieren. Dies kann dazu beitragen, die Genauigkeit der Suche nach Inhalten betroffener Personen sowohl für Ihr internes Personal als auch für externe Benutzer, mit denen Sie interagieren, zu erhöhen. Außerdem vereinfacht es die Notwendigkeit, Felder während der Erstellung von Anträgen auf Antrag einer Betroffenen manuell zur Verfügung zu stellen, und stellt Kontext innerhalb von Anträgen von Betreffrechten sowie für die Kachel "Übersicht" bereit, die Ihre Elemente mit den meisten Inhalten betroffener Personen anzeigt. Weitere Informationen zu dieser Ansicht finden Sie unter [Suchen und Visualisieren Ihrer Daten.](privacy-management-data-profile.md#items-with-the-most-data-subject-content)

Um die Datenabgleichsfunktion zu verwenden, müssen Sie Mitglied der Rollengruppe "Datenschutzverwaltung" sein. Wählen Sie das Zahnradsymbol für Einstellungen in der oberen rechten Ecke der Hauptseite für Anträge betroffener Personen aus, und wählen Sie **"Datenübereinstimmung"** aus. Von hier aus müssen Sie das Schema für personenbezogene Daten definieren und einen Upload personenbezogener Daten bereitstellen, wie unten dargestellt. Beachten Sie, dass Sie Elemente hinzufügen und Elemente löschen können, die Sie über die Benutzeroberfläche hinzufügen. Sie können jedoch derzeit kein Element über die Benutzeroberfläche ändern.

### <a name="prepare-for-data-import"></a>Vorbereiten des Datenimports

Bevor Sie das Schema definieren oder Daten hochladen, müssen Sie die Quelle der Informationen der betroffenen Person identifizieren. Das erforderliche Dateiformat ist .csv, das von einer Anwendung wie Microsoft Excel gelesen werden kann. Strukturieren Sie diesen Export so, dass die Spaltenüberschriften in der ersten Zeile angezeigt werden. Diese Header sollten die Namen der Attribute für Ihr Schema für personenbezogene Daten enthalten. Überprüfen Sie das Format der Daten in den einzelnen Feldern. Wenn eines der Daten Kommas enthält, umgeben Sie diese Werte mit doppelten Anführungszeichen, um sicherzustellen, dass sie nicht in separate Felder analysiert werden.

### <a name="define-the-personal-data-schema"></a>Definieren des Schemas für personenbezogene Daten

Das Schema für personenbezogene Daten beschreibt die Attribute für Ihre betroffenen Personen. Hochladen dieses Schema auf der ersten Registerkarte des Einstellungsbereichs für datenübereinstimmungen. Die erforderlichen Dateien umfassen eine XML-Datei mit dem Schema für **personenbezogene Daten** und eine REGELpaket-XML-Datei. 

#### <a name="personal-data-schema-xml"></a>XML des Schemas für personenbezogene Daten

Die Schemadatei für personenbezogene Daten ist eine XML-Datei, die definiert, welche Spaltennamen erwartet werden.

- Benennen Sie diese Schemadatei *pdm.xml.*
- Definieren Sie jeden Spaltennamen mithilfe des Feldnamentags, wie im folgenden Beispiel dargestellt.
- Verwenden Sie durchsuchbar = "true" für Felder, die durchsuchbar sein sollen, bis zu maximal fünf Felder. Mindestens einer ihrer Feldnamen muss durchsuchbar sein. Beispielsyntax: `\<Field name="" searchable=""/>` .
- Das Schema für personenbezogene Daten verfügt über einen DataStore-Tag-Abschnitt. Den Feldnamen müssen vier Pflichtfelder zugeordnet werden: primaryKeyField, upnField, firstNameField, lastNameField.

Die folgende XML-Datei definiert beispielsweise ein Beispielschema mit fünf durchsuchbaren Feldern: PatientID, MRN, SSN, Telefon und DOB. The primaryKeyField is mapped to PatientID, upnField is mapped to MRN, firstNameField is mapped to FirstName, and lastNameField is mapped to LastName.

Sie können das Beispiel kopieren, ändern und verwenden.

 ```xml
<PdmSchema xmlns="http://schemas.microsoft.com/office/2020/pdm">
      <DataStore name="Patientrecords" description="Schema for patient records" version="1" primaryKeyField="PatientID" upnField="MRN" firstNameField="FirstName" lastNameField="LastName">
            <Field name="PatientID" searchable="true"/>
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</PdmSchema>
 ```

#### <a name="rule-package-xml"></a>Regelpaket-XML

Wenn Sie das Regelpaket einrichten, müssen Sie die oben erstellte Schemadatei für personenbezogene Daten korrekt referenzieren: pdm.xml. Im folgenden Beispiel für das Regelpaket-XML müssen die folgenden Felder angepasst werden, um Daten mit dem vertraulichen Typ zu erstellen:

- **RulePack-ID**  &  **PrivacyMatch-ID:** Verwenden Sie "New-GUID", um eine GUID zu generieren.
- **Datenspeicher:** Dieses Feld gibt den zu verwendenden Nachschlagedatenspeicher für personenbezogene Daten an. Geben Sie den definierten DataStore-Namen eines konfigurierten Schemas für personenbezogene Daten an.
- **idMatch:** Dieses Feld verweist auf das primäre Element für die Übereinstimmung mit personenbezogenen Daten.
  - **Übereinstimmungen:** Gibt das Feld an, das bei der genauen Suche verwendet werden soll. Geben Sie einen durchsuchbaren Feldnamen aus dem Schema für personenbezogene Daten an.
  - **Klassifizierung:** Dieses Feld gibt die Übereinstimmung des vertraulichen Typs an, die die Suche nach Übereinstimmungen mit personenbezogenen Daten auslöst. Sie können den Namen oder die GUID eines vorhandenen integrierten oder benutzerdefinierten vertraulichen Informationstyps angeben. Um Leistungsprobleme zu vermeiden, sollten Sie, wenn Sie einen benutzerdefinierten vertraulichen Informationstyp als Klassifizierungselement in der Übereinstimmung mit personenbezogenen Daten verwenden, keinen benutzerdefinierten vertraulichen Informationstyp verwenden, der einem großen Prozentsatz des Inhalts entspricht (z. B. "beliebige Zahl" oder "ein beliebiges Fünf-Buchstaben-Wort"). Es wird empfohlen, unterstützende Schlüsselwörter hinzuzufügen oder Formatierungen in die Definition des benutzerdefinierten Vertraulichen Informationstyps für Klassifizierungen aufzunehmen.
- **Übereinstimmung:** Dieses Feld verweist auf zusätzliche Nachweise, die in der Nähe von idMatch gefunden wurden.
  - **Übereinstimmungen:** Geben Sie einen beliebigen Feldnamen im Schema für personenbezogene Daten für DataStore an.
- **Ressource:** In diesem Abschnitt werden der Name und die Beschreibung für den vertraulichen Typ in mehreren Gebietsschemas angegeben.
  - **idRef:** Geben Sie GUID für ExactMatch-ID an.
  - **Name & Beschreibungen:** Nach Bedarf anpassen.

In unserem xml-Beispiel für das Regelpaket unten verweisen wir auf die pdm.xml Beispieldatei aus dem vorherigen Schritt, die das XML-Schema für personenbezogene Daten erstellt:

- **Datastore**: Der DataStore-Name verweist auf die Schemadatei, die wir zuvor erstellt haben: dataStore = "PatientRecords".
- **idMatch**: Der idMatch-Wert verweist auf ein durchsuchbares Feld, das in der zuvor erstellten datei pdm.xml aufgeführt ist: idMatch matches = "SSN".
  - **Klassifizierung:** Der Klassifizierungswert verweist auf einen vorhandenen oder benutzerdefinierten vertraulichen Informationstyp: Klassifizierung = "U.S. Sozialversicherungsnummer (SSN)". (In diesem Fall wird der vorhandene vertrauliche Informationstyp "US-Sozialversicherungsnummer" verwendet.)

Erstellen Sie ein Regelpaket im XML-Format (mit Unicode-Codierung), wie im folgenden Beispielcode. Sie können dieses Beispiel kopieren, ändern und verwenden.

 ```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2020/pdm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b21">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care PDM Rulepack</Name>
        <Description>This rule package contains the Personal Data Match sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <PrivacyMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB381" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="6">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </PrivacyMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB381">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">PDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
 ```

### <a name="upload-personal-data"></a>Hochladen personenbezogener Daten
Nachdem Sie das Schema für personenbezogene Daten definiert haben, können Sie den **Upload personenbezogener Daten** auf der zweiten Registerkarte der Einstellungsseite für datenübereinstimmungen durchführen. Wenn Sie **"Hinzufügen"** auswählen, wählen Sie das persönliche Schema aus, das Sie im ersten Schritt definiert haben, und laden Sie dann die Datei hoch, die die personenbezogenen Daten enthält.

Sie können diese personenbezogenen Daten hochladen, indem Sie eine lokale Datei auswählen oder eine SAS-URL zu einem vorhandenen Microsoft Azure Storage Speicherort angeben, der Ihre persönliche Datendatei enthält.
Wenn Sie als ersten Schritt in diesem Prozess eine Datei vorbereitet haben, die dem erstellten Schema entspricht, können Sie diese Datei für den Upload verwenden.
