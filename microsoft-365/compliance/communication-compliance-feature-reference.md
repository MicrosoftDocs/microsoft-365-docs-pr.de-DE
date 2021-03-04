---
title: Referenz zu Kommunikationskonformitätsfeatures
description: Featurereferenz für die Kommunikationskonformität in Microsoft 365. Erfahren Sie mehr über Details und Spezifikationen für jede Featurekomponenten.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4cd6e62fd236bf9fd3683425b1e98315fc26dd71
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421692"
---
# <a name="communication-compliance-feature-reference"></a>Referenz zu Kommunikationskonformitätsfeatures

## <a name="policies"></a>Richtlinien

>[!Important]
>Die Verwendung von PowerShell zum Erstellen und Verwalten von Richtlinien zur Kommunikationscompliance wird nicht unterstützt. Zum Erstellen und Verwalten dieser Richtlinien müssen Sie die Richtlinienverwaltungssteuerelemente in der [Microsoft 365 Communication Compliance-Lösung verwenden.](https://compliance.microsoft.com/supervisoryreview)

Im Microsoft 365 Compliance Center erstellen Sie Richtlinien zur Kommunikationscompliance für Microsoft 365-Organisationen. Richtlinien zur Kommunikationskonformität definieren, welche Kommunikationen und Benutzer in Ihrer Organisation überprüft werden müssen, definieren, welche benutzerdefinierten Bedingungen die Kommunikation erfüllen muss, und geben an, wer Rezensionen anfertigen soll. Benutzer, *denen* die Administratorrolle "Kommunikationskonformität" zugewiesen wurde,  können Richtlinien einrichten, und jeder Benutzer, dem diese Rolle zugewiesen ist, kann auf die Seite "Kommunikationskonformität" und die globalen Einstellungen im Microsoft 365 Compliance Center zugreifen. Bei Bedarf können Sie den Verlauf von Änderungen an einer Richtlinie in eine CSV-Datei (durch Kommas getrennte Werte) exportieren, die auch den Status der ausstehenden Überprüfungswarnungen, eskalierten Elementen und aufgelösten Elementen enthält. Richtlinien können nicht umbenannt und gelöscht werden, wenn sie nicht mehr benötigt werden.

>[!NOTE]
>Aufsichtsrichtlinien, die im Security & Compliance Center für Office 365-Abonnements erstellt wurden, können nicht zu Microsoft 365 migriert werden. Wenn Sie von einem Office 365-Abonnement zu einem Microsoft 365-Abonnement migrieren, müssen Sie neue Richtlinien zur Kommunikationskonformität erstellen, um vorhandene Aufsichtsrichtlinien zu ersetzen.

## <a name="policy-templates"></a>Richtlinienvorlagen

Richtlinienvorlagen sind vordefinierte Richtlinieneinstellungen, mit denen Sie schnell Richtlinien für häufige Complianceszenarien erstellen können. Jede dieser Vorlagen hat Unterschiede in Bedingungen und Umfang, und alle Vorlagen verwenden die gleichen Arten von Überprüfungssignalen. Sie können aus den folgenden Richtlinienvorlagen auswählen:

|**Bereich**|**Richtlinienvorlage**|**Details**|
|:-----|:-----|:-----|
| **Anstößige Sprache und Anti-Mobbing** | Überwachen der Kommunikation auf anstößige Sprache | - Standorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Eingehende, ausgehende, interne <br> - Prozentsatz der Überprüfung: 100 % <br> - Bedingungen: Anstößiger Sprachklassifikator |
| **Vertrauliche Informationen** | Überwachen der Kommunikation auf vertrauliche Informationen | - Standorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Eingehende, ausgehende, interne <br> - Prozentsatz der Überprüfung: 10 % <br> - Bedingungen: Vertrauliche Informationen, out-of-the-Box-Inhaltsmuster und -typen, benutzerdefinierte Wörterbuchoption, Anlagen größer als 1 MB |
| **Einhaltung gesetzlicher Bestimmungen** | Überwachen der Kommunikation auf Informationen im Zusammenhang mit der Einhaltung gesetzlicher Vorschriften | - Standorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Eingehende, ausgehende <br> - Prozentsatz der Überprüfung: 10 % <br> - Bedingungen: benutzerdefinierte Wörterbuchoption, Anlagen größer als 1 MB |
| **Interessenkonflikt** | Überwachen der Kommunikation zwischen zwei Gruppen oder zwei Benutzern, um Interessenkonflikte zu vermeiden | - Standorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Intern <br> - Prozentsatz der Überprüfung: 100 % <br> - Bedingungen: Keine |

Die Kommunikation wird alle 24 Stunden nach dem Erstellen von Richtlinien überprüft. Wenn Sie beispielsweise um 11:00 Uhr eine anstößige Sprachrichtlinie erstellen, sammelt die Richtlinie kommunikationskonformitätssignale alle 24 Stunden um 11:00 Uhr. Das Bearbeiten einer Richtlinie ändert sich dieses Mal nicht. Zum Anzeigen des Datums und der Uhrzeit der letzten Überprüfung für eine Richtlinie navigieren Sie zur Spalte *Letzte* Richtlinienscan auf der **Seite** Richtlinie. Nach dem Erstellen einer neuen Richtlinie kann es bis zu 24 Stunden dauern, bis das erste Datum und die Uhrzeit der ersten Richtlinienscans angezeigt werden. Datum und Uhrzeit der letzten Überprüfung werden in die Zeitzone Ihres lokalen Systems konvertiert.

## <a name="permissions"></a>Berechtigungen

>[!Important]
>Standardmäßig haben globale Administratoren keinen Zugriff auf Kommunikationskonformitätsfeatures. Die in diesem Schritt zugewiesenen Rollen sind erforderlich, bevor auf Kommunikationskonformitätsfeatures zugegriffen werden kann.

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationskonformitätsfeatures verwendet werden. Um die **Kommunikationskonformität** als Menüoption im Microsoft 365 Compliance Center verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, müssen Sie den Rollengruppen *Kommunikationskonformität* oder Kommunikationskonformität *administrator* zugewiesen werden. Um nach der Erstkonfiguration auf Kommunikationskonformitätsfeatures zu zugreifen und diese zu verwalten, müssen Benutzer Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.

Je nachdem, wie Sie Kommunikationsrichtlinien und Warnungen verwalten möchten, müssen Sie Benutzer bestimmten Rollengruppen zuweisen. Sie haben die Möglichkeit, Bestimmten Rollengruppen Benutzer mit unterschiedlichen Compliance-Verantwortlichkeiten zuzuordnen, um verschiedene Bereiche von Kommunikations-Compliance-Features zu verwalten. Sie können auch alle Benutzerkonten für designierte Administratoren, Analysten, Ermittler  und Betrachter der Rollengruppe Kommunikationskonformität zuweisen. Verwenden Sie eine einzelne Rollengruppe oder mehrere Rollengruppen, um Ihre Anforderungen an die Complianceverwaltung optimal zu erfüllen.

Wählen Sie beim Konfigurieren der Kommunikationskonformität aus den folgenden Rollengruppenoptionen aus:

|**Rollengruppe**|**Rollengruppenberechtigungen**|
|:-----|:-----|
| **Kommunikationskonformität** | Verwenden Sie diese Rollengruppe, um die Kommunikationskonformität für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Viewer können Sie Berechtigungen für die Kommunikationskonformität in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationskonformität. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationskonformität zu beginnen und ist für Organisationen geeignet, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikations-Compliance-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationskonformität zu konfigurieren und später Administratoren der Kommunikationskonformität in eine definierte Gruppe zu trennen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Kommunikationskonformitätsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Benachrichtigungen anzeigen. |
| **Communication Compliance Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Kommunikations-Compliance-Analysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, in denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten (nicht Nachrichteninhalte) anzeigen, an andere Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht auflösen. |
| **Kommunikations-Compliance-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Ermittler für die Kommunikationskonformität fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und -inhalte anzeigen, an andere Prüfer eskalieren, zu einem Erweiterten eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Communication Compliance Viewer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Homepage der Kommunikationskonformität auf alle Berichts-Widgets zugreifen und alle Berichte zur Kommunikationskonformität anzeigen. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Für Organisationen, die die ursprünglichen Berechtigungen und Rollengruppen verwenden

Die neue Rollengruppenstruktur ersetzt die anfängliche Rollengruppenstruktur für die Kommunikationskonformität. Für Organisationen, die bereits Kommunikationskonformität verwenden, musste Ihnen die Rolle "Aufsichtsüberprüfungsadministrator" zugewiesen werden, um mit der Kommunikationskonformität im Microsoft 365 Compliance Center zu beginnen. Darüber hinaus mussten Sie eine neue Rollengruppe für Prüfer mit den Rollen Supervisory Review Administrator, Case Management, Compliance Administrator und Review erstellen, um Nachrichten mit Richtlinien übereinstimmungen zu untersuchen und zu beaufsichtigungen. Im Wesentlichen waren alle Administratoren und Prüfer in einer einzelnen Rollengruppe, und alle Benutzer hatten dieselben Zugriffs- und Verwaltungsberechtigungen. Mit den neuesten Updates für die Kommunikationskonformität sollten Sie die Migration von der vorherigen Rollengruppenstruktur zur neuen Rollengruppenstruktur planen. Die Unterstützung für die vorherige Rollengruppenstruktur wird schrittweise schrittweise durchgeführt.

Berücksichtigen Sie das folgende Beispiel, um Ihre Migrationsplanung zu unterstützen. Derzeit haben Sie drei Arten von Benutzern in Ihrer Organisation: IT-Administratoren, Triage und Prüfer. Diese drei Benutzertypen befinden sich in der vorherigen Rollengruppenstruktur und sind alle Mitglieder einer einzelnen Rollengruppe, denen die folgenden Rollen zugewiesen sind:

- Aufsichtsüberprüfungsadministrator
- Fallverwaltung
- Complianceadministrator
- Überprüfung

Zum Aktualisieren der Rollen für diese Benutzer für die neue Rollengruppenstruktur und zum Trennen der Zugriffs- und Verwaltungsberechtigungen für die Benutzer können Sie drei neue Gruppen und die zugeordneten neuen Rollengruppenzuweisungen in Betracht ziehen:

- **IT-Administratoren**: Der neuen Rollengruppe *"Kommunikations-Compliance-Administrator"* zugewiesen.
- **Triage**: Der Rollengruppe *Communication Compliance Analyst* zugewiesen.
- **Prüfer**: Der neuen Rollengruppe *"Communication Compliance Investigator"* zugewiesen.

## <a name="supervised-users"></a>Überwachte Benutzer

Bevor Sie mit der Kommunikationscompliance beginnen, müssen Sie feststellen, wer die Überprüfung der Kommunikation benötigt. In der Richtlinie identifizieren die E-Mail-Adressen der Benutzer Einzelpersonen oder Personengruppen, die überwacht werden sollen. Einige Beispiele für diese Gruppen sind Microsoft 365-Gruppen, Exchange-basierte Verteilerlisten, Yammer Communitys und Microsoft Teams-Kanäle. Sie können auch bestimmte Benutzer oder Gruppen mit einer bestimmten Ausschlussgruppe oder einer Liste von Gruppen vom Überprüfen ausschließen.

>[!IMPORTANT]
>Benutzer, für die Richtlinien zur Kommunikationskonformität gilt, müssen entweder über eine Microsoft 365 E5-Compliancelizenz, eine Office 365 Enterprise E3-Lizenz mit dem Advanced Compliance-Add-On oder über ein Office 365 Enterprise E5-Abonnement verfügen. Wenn Sie nicht über einen vorhandenen Enterprise E5-Plan verfügen und kommunikationskonform sein möchten, können Sie sich für eine Testversion von [Office 365 Enterprise E5 registrieren.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="reviewers"></a>Prüfer

Wenn Sie eine Kommunikationskonformitätsrichtlinie erstellen, müssen Sie bestimmen, wer die Nachrichten der überwachten Benutzer überprüft. In der Richtlinie identifizieren die E-Mail-Adressen der Benutzer Einzelpersonen oder Personengruppen, welche die überwachte Kommunikation überprüfen sollen. Alle Prüfer müssen über Postfächer verfügen, die in Exchange Online gehostet werden, und sie müssen entweder den Rollen *Communication Compliance Analysis* oder Communication Compliance Investigation *zugewiesen* werden. Prüfern (entweder Analysten oder Ermittlern) muss auch die Rolle *Kommunikationskonformitätsfallverwaltung zugewiesen* sein. Wenn Prüfer einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuordnung zur Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess enthält.

## <a name="groups-for-supervised-users-and-reviewers"></a>Gruppen für überwachte Benutzer und Prüfer

Um das Setup zu vereinfachen, erstellen Sie Gruppen für Personen, die ihre Kommunikation überprüfen müssen, und Gruppen für Personen, die diese Kommunikation überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Zum Beispiel, wenn Sie die Kommunikation zwischen zwei verschiedenen Personengruppen überprüfen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Wenn Sie eine Verteilergruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails von jedem Benutzer in der Verteilergruppe. Wenn Sie eine Microsoft 365-Gruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails, die an diese Gruppe gesendet werden, nicht die einzelnen E-Mails, die von jedem Gruppenmitglied empfangen werden.

Das Hinzufügen von Gruppen und Verteilerlisten zu Kommunikationskonformitätsrichtlinien ist Teil der allgemeinen Bedingungen und Regeln, sodass die maximale Anzahl von Gruppen und Verteilerlisten, die von einer Richtlinie unterstützt werden, abhängig von der Anzahl der Bedingungen variiert, die der Richtlinie ebenfalls hinzugefügt wurden. Jede Richtlinie sollte ungefähr 20 Gruppen oder Verteilerlisten unterstützen, abhängig von der Anzahl der zusätzlichen Bedingungen, die in der Richtlinie vorhanden sind.

## <a name="supported-communication-types"></a>Unterstützte Kommunikationstypen

Mit Kommunikationskonformitätsrichtlinien können Sie Nachrichten in einer oder mehreren der folgenden Kommunikationsplattformen als Gruppe oder als eigenständige Quellen überprüfen. Die über diese Plattformen erfasste Kommunikation wird für jede Richtlinie standardmäßig sieben Jahre lang aufbewahrt, auch wenn Benutzer Ihre Organisation verlassen und ihre Postfächer gelöscht werden.

- **Microsoft Teams**: Chatkommunikation in öffentlichen und privaten Microsoft Teams-Kanälen und einzelnen Chats kann überprüft werden. Wenn Benutzern eine Kommunikationskonformitätsrichtlinie mit ausgewählter Microsoft Teams-Abdeckung zugewiesen ist, wird die Chatkommunikation für die Benutzer automatisch in allen Microsoft Teams überwacht, in denen die Benutzer Mitglied sind. Die Microsoft Teams-Abdeckung wird automatisch für vordefinierte Richtlinienvorlagen einbezogen und standardmäßig in der benutzerdefinierten Richtlinienvorlage ausgewählt. Es kann bis zu 48 Stunden dauern, bis Teams-Chats mit den Richtlinienbedingungen für die Kommunikationskonformität übereinstimmen. Verwenden Sie die folgenden Gruppenverwaltungskonfigurationen, um einzelne Benutzerchats und Kanalkommunikation in Teams zu überwachen:

    - **Für Teams-Chatkommunikation:** Weisen Sie der Kommunikationskonformitätsrichtlinie einzelne Benutzer [zu,](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) oder weisen Sie der Kommunikationskonformitätsrichtlinie eine Verteilergruppe zu. Diese Einstellung gilt für Eins-zu-eins- oder Eins-zu-viele-Benutzer/Chat-Beziehungen.
    - **Für die Kommunikation im Teams-Kanal:** Weisen Sie jedem Microsoft Teams-Kanal oder jeder Microsoft 365-Gruppe, die Sie überprüfen möchten, einen bestimmten Benutzer zu, die Kommunikationskonformitätsrichtlinie zu. Wenn Sie denselben Benutzer zu anderen Microsoft Teams-Kanälen oder Microsoft 365-Gruppen hinzufügen, stellen Sie sicher, dass Sie diese neuen Kanäle und Gruppen in die Richtlinie zur Kommunikationscompliance aufnehmen.
    - **Für Teams Chatkommunikation** mit Hybrid-E-Mail-Umgebungen: Kommunikationskonformität kann Chatnachrichten für Benutzer für Organisationen mit einer lokalen Exchange-Bereitstellung oder einem externen E-Mail-Anbieter überwachen, der Microsoft Teams aktiviert hat. Sie müssen eine Verteilergruppe für die Benutzer mit lokalen oder externen Postfächern erstellen, die überwacht werden sollen. Beim Erstellen einer Kommunikationskonformitätsrichtlinie weisen Sie  diese Verteilergruppe als Auswahl überwachter Benutzer und Gruppen im Richtlinien-Assistenten zu.

    >[!IMPORTANT]
    >Sie müssen eine Anforderung beim Microsoft-Support stellen, damit Ihre Organisation die grafische Benutzeroberfläche im Security & Compliance Center verwenden kann, um für lokale Benutzer nach Teams-Chatdaten zu suchen. Weitere Informationen finden Sie unter [Durchsuchen cloudbasierter Postfächer für lokale Benutzer](search-cloud-based-mailboxes-for-on-premises-users.md).

Sie müssen eine Anforderung beim Microsoft-Support stellen, damit Ihre Organisation die grafische Benutzeroberfläche im Security & Compliance Center verwenden kann, um in den cloudbasierten Postfächern für lokale Benutzer nach Teams-Chatdaten zu suchen.

- **Exchange-E-Mail:** Postfächer, die im Rahmen Ihres Microsoft 365- oder Office 365-Abonnements in Exchange Online gehostet werden, sind alle für die Nachrichtenprüfung berechtigt. Es kann bis zu 24 Stunden dauern, bis Exchange-E-Mail-Nachrichten und Anlagen mit den Richtlinienbedingungen für die Kommunikationskonformität übereinstimmen. Die für die Kommunikationscompliance unterstützten Anlagetypen sind die gleichen wie die [Dateitypen, die für die Inhaltsüberprüfung von Exchange-Mailflussregeln unterstützt werden](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer**: Private Nachrichten und öffentliche Unterhaltungen und zugehörige Anlagen in Yammer Communitys können überprüft werden. Wenn ein Benutzer der Kommunikationskonformitätsrichtlinie hinzugefügt wird, die Yammer als definierten Kanal enthält, wird die Kommunikation über alle Yammer-Communitys hinweg, in denen der Benutzer Mitglied ist, in den Überprüfungsprozess einbezogen. Yammer chats and attachments matching communication compliance policy conditions may take up to 24 hours to process. Yammer muss sich im [nativen Modus befinden,](/yammer/configure-your-yammer-network/overview-native-mode) damit Kommunikationskonformitätsrichtlinien für die Überwachung Yammer und Anlagen verwendet werden können. Im nativen Modus befinden sich alle Yammer-Benutzer in Azure Active Directory (AAD), alle Gruppen sind Office 365-Gruppen, und alle Dateien werden in SharePoint Online gespeichert.

- **Skype for Business Online**: Chatnachrichten und zugehörige Anlagen in Skype for Business Online können überwacht werden. Die Bearbeitung von Skype for Business Online-Chats, in denen die Bedingungen für die Richtlinien zur Kommunikationscompliance erfüllt werden, kann bis zu 24 Stunden dauern. Überwachte Chatunterhaltungen stammen aus [vorherigen Unterhaltungen, die in Skype for Business Online gespeichert wurden.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Verwenden Sie die folgende Gruppenverwaltungskonfiguration, um die Benutzerchatkommunikation in Skype for Business Online zu überwachen:

    - **Für Skype for Business Online-Chatkommunikation:** Weisen Sie einzelne Benutzer zu oder weisen Sie der Kommunikationskonformitätsrichtlinie [eine](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) Verteilergruppe zu. Diese Einstellung gilt für Eins-zu-eins- oder Eins-zu-viele-Benutzer/Chat-Beziehungen.

- **Drittanbieterquellen:** Sie können die Kommunikation auf Daten überprüfen, die in Postfächer in Ihrer Microsoft 365-Organisation importiert wurden, aus Drittanbieterquellen wie [Instant Bloomberg,](archive-instant-bloomberg-data.md) [Slack,](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS und vielen anderen. Eine vollständige Liste der connectors, die in der Kommunikationskonformität unterstützt werden, finden Sie unter [Archivieren von Drittanbieterdaten](archiving-third-party-data.md).

    Sie müssen einen Drittanbieterconnector für Ihre Microsoft 365-Organisation konfigurieren, bevor Sie den Connector einer Kommunikationskonformitätsrichtlinie zuweisen können. Im **Abschnitt Quellen von Drittanbietern** des Assistenten für Kommunikationskonformitätsrichtlinien werden nur aktuell konfigurierte Drittanbieterconnectors angezeigt.

## <a name="transitioning-from-supervision-in-office-365"></a>Übergang von der Aufsicht in Office 365

Organisationen, die Aufsichtsrichtlinien in Office 365 verwenden und den Übergang zu Kommunikationskonformitätsrichtlinien in Microsoft 365 planen, müssen die folgenden wichtigen Punkte verstehen:

- Beide Lösungen können in Ihrer Organisation nebeneinander verwendet werden, aber die in jeder Lösung verwendeten Richtlinien müssen eindeutige Richtliniennamen haben. aufweisen. Gruppen und benutzerdefinierte Schlüsselwortwörterbücher können während einer Übergangszeit von Lösungen gemeinsam genutzt werden.
- Nachrichten, die in der Aufsicht in Office 365-Richtlinien übereinstimmungen gespeichert sind, können nicht verschoben oder in die Kommunikationskonformität in Microsoft 365 freigegeben werden.
- Die Aufsichtslösung in Office 365 wird vollständig durch die Kommunikationskonformitätslösung in Microsoft 365 ersetzt. Es wird empfohlen, neue Richtlinien für die Kommunikationskonformität zu erstellen, die die gleichen Einstellungen wie vorhandene Aufsichtsrichtlinien haben, um die neuen Verbesserungen bei Untersuchung und Behebung zu nutzen. Beim Übergang zur Kommunikationscompliance in Microsoft 365 sollten Sie planen, Berichtsdaten aus der Aufsicht in Office 365 zu exportieren, wenn Sie interne Richtlinien zur Aufbewahrung von Compliance-Anforderungen haben.

Weitere Informationen zur Aufsicht in Office 365 finden Sie in [der Microsoft 365 Roadmap.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="policy-settings"></a>Richtlinieneinstellungen

### <a name="users"></a>Benutzer

Sie haben die Möglichkeit, Alle Benutzer **auszuwählen** oder bestimmte Benutzer in einer Kommunikationskonformitätsrichtlinie zu definieren. Durch Auswahl von **Alle Benutzer** wird die Richtlinie auf alle Benutzer und alle Gruppen angewendet, in denen ein Benutzer als Mitglied enthalten ist. Das Festlegen bestimmter Benutzer wendet die Richtlinie auf die festgelegten Benutzer und alle Gruppen an, in denen die festgelegten Benutzer als Mitglied enthalten sind.

### <a name="direction"></a>Direction

Standardmäßig wird die **Direction-Bedingung** angezeigt und kann nicht entfernt werden. Kommunikationsrichtungseinstellungen in einer Richtlinie werden einzeln oder gemeinsam ausgewählt:

- **Eingehende Nachrichten:** Sie können eingehende Nachrichten  **auswählen,** um die Kommunikation zu überprüfen, die Sie an die Personen gesendet haben, die Sie überwacht haben.
- **Ausgehend:** Sie können ausgehend **auswählen,** wenn  Sie die kommunikation überprüfen möchten, die von den Personen gesendet wurde, die Sie überwacht haben.
- **Intern:** Sie können Internal **auswählen,** um die Kommunikation zwischen den Personen zu überprüfen, die Sie in der Richtlinie identifiziert haben. 

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Sie haben die Möglichkeit, vertrauliche Informationstypen als Teil Ihrer Kommunikationskonformitätsrichtlinie zu verwenden. Vertrauliche Informationstypen sind entweder vordefinierte oder benutzerdefinierte Datentypen, mit deren Hilfe Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr identifiziert und geschützt werden können. Als Bestandteil von [Verhinderung von Datenverlust (Data Loss Prevention, DLP)](data-loss-prevention-policies.md), kann die Konfiguration vertraulicher Informationen Muster, Zeichennähe, Vertrauensniveaus und sogar benutzerdefinierte Datentypen verwenden, um möglicherweise vertrauliche Inhalte zu identifizieren und zu kennzeichnen. Die standardmäßigen Typen vertraulicher Informationen sind:

- Finanzwesen
- Medizin und Gesundheit
- Datenschutz
- Benutzerdefinierter Informationstyp

Weitere Informationen zu Details zu vertraulichen Informationen und zu den Mustern in den Standardtypen finden Sie unter Entitätsdefinitionen des Typs ["Vertrauliche Informationen".](sensitive-information-type-entity-definitions.md)

### <a name="custom-keyword-dictionaries"></a>Benutzerdefinierte Schlüsselwortwörterbücher

Konfigurieren Sie benutzerdefinierte Schlüsselwortwörterbücher (oder Lexika), um eine einfache Verwaltung von Schlüsselwörtern zu ermöglichen, die für Ihre Organisation oder Branche spezifisch sind. Schlüsselwortwörterbücher unterstützen bis zu 100 KB Begriffe (nach der Komprimierung) im Wörterbuch und unterstützen jede Sprache. Der Mandantengrenzwert beträgt nach der Komprimierung ebenfalls 100 KB. Bei Bedarf können Sie mehrere benutzerdefinierte Schlüsselwortwörterbücher auf eine einzelne Richtlinie anwenden oder über ein einzelnes Schlüsselwortwörterbuch pro Richtlinie verfügen. Diese Wörterbücher werden in einer Kommunikationskonformitätsrichtlinie zugewiesen und können aus einer Datei (z. B. einer CSV- oder TXT-Liste) oder aus einer Liste stammen, die Sie im [Compliance Center importieren können.](create-a-keyword-dictionary.md) Verwenden Sie benutzerdefinierte Wörterbücher, wenn Sie spezifisch für Ihre Organisation und Richtlinien spezifische Begriffe oder Sprachen unterstützen müssen.

### <a name="classifiers"></a>Klassifizierungen

Integrierte trainierbare und globale Klassifikatoren überprüfen gesendete oder empfangene Nachrichten über alle Kommunikationskanäle in Ihrer Organisation auf unterschiedliche Arten von Kompatibilitätsproblemen. Klassifizierer verwenden eine Kombination aus künstlicher Intelligenz und Schlüsselwörtern, um Sprache in Botschaften zu identifizieren, die wahrscheinlich gegen die Antibelästigungsrichtlinien verstoßen. Integrierte Klassifikatoren unterstützen derzeit die Identifikation von Nachrichtenschlüsselwörtern in mehreren Sprachen:

- Chinesisch (vereinfacht)
- Englisch
- Französisch
- Deutsch
- Italienisch
- Japanisch
- Portugiesisch
- Spanisch

Kommunikationskonformität integrierte trainierbare und globale Klassifikatoren überprüfen die Kommunikation auf Begriffe, Bilder und Stimmungen für die folgenden Arten von Sprache und Inhalten:

- **Bedrohung:** Sucht nach Bedrohungen, die eine Person oder Eigenschaft mit Gewalt oder physischer Schädigung begehen.
- **Gezielte Belästigung:** Scans auf beleidigende Verhaltensweisen, die auf Personen in Bezug auf Die Rasse, Farbe, Herkunft, Nationale Herkunft ausgerichtet sind.
- **Profanity**: Sucht nach profanen Ausdrücken, die die meisten Personen in Verlegenheit nischen.
- **Bilder für Erwachsene:** Sucht nach Bildern, die sexuell explizit sind.
- **Racy images**: Scans for images that are sexually suggestive in nature, but contain less explicit content than images deemed Adult.
- **Gory images**: Scans for images that depict violence and gore.

Die Bildklassifikatoren *Adult,* *Racy* und *Gory* scannen Dateien in den Formaten JPEG, PNG, GIF und BMP. Die Größe für Bilddateien muss kleiner als 4 MB sein, und die Abmessungen der Bilder müssen größer als 50 x 50 Pixel und größer als 50 KB sein, damit das Bild für die Auswertung qualifiziert werden kann. Die Bildidentifizierung wird für Exchange Online-E-Mail-Nachrichten und Microsoft Teams-Kanäle und -Chats unterstützt.

Die integrierten trainierbaren und globalen Klassifikatoren bieten keine vollständige Liste der Begriffe oder Bilder in diesen Bereichen. Darüber hinaus ändern sich die Sprach- und Kulturstandards ständig, und angesichts dieser Realität behält sich Microsoft das Recht vor, Klassifikatoren nach eigenem Ermessen zu aktualisieren. Während Klassifikatoren Ihre Organisation bei der Überwachung dieser Bereiche unterstützen können, sind Klassifikatoren nicht dafür vorgesehen, die einzigen Mittel ihrer Organisation zur Überwachung oder Behandlung dieser Sprache oder Bilder zur Verfügung zu stellen. Ihre Organisation, nicht Microsoft, bleibt für alle Entscheidungen im Zusammenhang mit der Überwachung, Überprüfung und Sperrung von Sprache und Bildern in diesen Bereichen verantwortlich, einschließlich der Einhaltung des lokalen Datenschutzes und anderer anwendbarer Gesetze. Microsoft ermuntert die Beratung mit Rechtsberatern vor der Bereitstellung und Verwendung.

>[!NOTE]
>Richtlinien, die Klassifikatoren verwenden, überprüfen und bewerten Nachrichten mit einer Wortanzahl von sechs oder mehr. Nachrichten mit weniger als sechs Wörtern werden in Richtlinien nicht mithilfe von Klassifizierungen ausgewertet. Um kürzere Nachrichten mit unangemessenen Inhalten zu identifizieren und maßnahmen zu ergreifen, empfehlen wir die Einbeziehung eines benutzerdefinierten Schlüsselwortwörterbuchs in die Überwachung von Kommunikationskonformitätsrichtlinien für diese Art von Inhalten.

Informationen zu trainierbaren Klassifizierungen in Microsoft 365 finden Sie unter Erste Schritte [mit trainierbaren Klassifizierungen](classifier-get-started-with.md).

### <a name="optical-character-recognition-ocr-preview"></a>Optische Zeichenerkennung (OCR) (Vorschau)

Konfigurieren Sie integrierte oder benutzerdefinierte Richtlinien für die Kommunikationskonformität, um gedruckten oder handschriftlichen Text aus Bildern zu überprüfen und zu identifizieren, die in Ihrer Organisation möglicherweise unangemessen sind. Integrierte Azure Cognitive Services und optische Überprüfungsunterstützung zum Identifizieren von Text in Bildern helfen Analysten und Ermittlern dabei, Fälle zu erkennen und zu handeln, bei denen unangemessenes Verhalten in der Kommunikation, die in erster Linie nicht textlich ist, übersehen werden kann.

Sie können die optische Zeichenerkennung (Optical Character Recognition, OCR) in neuen Richtlinien aus Vorlagen, benutzerdefinierten Richtlinien aktivieren oder vorhandene Richtlinien aktualisieren, um die Unterstützung für die Verarbeitung eingebetteter Bilder und Anlagen zu erweitern. Wenn sie in einer Richtlinie aktiviert ist, die aus einer Richtlinienvorlage erstellt wurde, wird die automatische Überprüfung für eingebettete oder angefügte Bilder in E-Mail- und Microsoft Teams-Chatnachrichten unterstützt. Für benutzerdefinierte Richtlinien müssen eine oder mehrere bedingte Einstellungen, die Schlüsselwörtern, integrierten Klassifizierungen oder typen vertraulicher Informationen zugeordnet sind, in der Richtlinie konfiguriert werden, um die Auswahl der OCR-Überprüfung zu aktivieren.

Bilder von 50 KB bis 4 MB in den folgenden Bildformaten werden gescannt und verarbeitet:

- .jpg/.jpeg (gemeinsame Expertengruppe für Fotofotos)
- .png (portable Netzwerkgrafiken)
- .bmp (Bitmap)
- .tiff (Tag-Bild-Dateiformat)
- .pdf (portables Dokumentformat)

>[!NOTE]
>Das Scannen und Extrahieren von eingebetteten und angefügten .pdf-Bildern wird derzeit nur für E-Mail-Nachrichten unterstützt.

Beim Überprüfen ausstehender Warnungen für Richtlinien mit aktivierter OCR werden Bilder, die identifiziert und den Richtlinienbedingungen entsprechen, als untergeordnete Elemente für zugeordnete Warnungen angezeigt. Sie können das Originalbild anzeigen, um den identifizierten Text im Kontext mit der ursprünglichen Nachricht auszuwerten. Es kann bis zu 48 Stunden dauern, bis erkannte Bilder mit Warnungen verfügbar sind.

### <a name="conditional-settings"></a>Bedingte Einstellungen
<a name="ConditionalSettings"> </a>

Die Bedingungen, die Sie für die Richtlinie auswählen, gelten für die Kommunikation von E-Mail- und Drittanbieterquellen in Ihrer Organisation (z. B. von Instant Bloomberg).

In der folgenden Tabelle werden weitere Informationen zu den einzelnen Bedingungen erläutert.
  
|**Bedingung**|**Verwendung**|
|:-----|:-----|
| **Inhalt entspricht einem dieser Klassifizierungen** | Gilt für die Richtlinie, wenn Klassifikatoren in einer Nachricht eingeschlossen oder ausgeschlossen werden. Einige Klassifizierungen sind in Ihrem Mandanten vorab definiert, und benutzerdefinierte Klassifizierungen müssen separat konfiguriert werden, bevor sie für diese Bedingung verfügbar sind. In einer Richtlinie kann nur ein Klassifikator als Bedingung definiert werden. Weitere Informationen zum Konfigurieren von Klassifikatoren finden Sie [unter Learn about trainable classifiers (preview)](classifier-learn-about.md). |
| **Inhalt enthält einen der folgenden Typen vertraulicher Informationen** | Gilt für die Richtlinie, wenn vertrauliche Informationstypen in einer Nachricht eingeschlossen oder ausgeschlossen werden. Einige Klassifikatoren sind in Ihrem Mandanten vorab definiert, und benutzerdefinierte Klassifizierungen können separat oder als Teil des Bedingungszuweisungsprozesses konfiguriert werden. Jeder vertrauliche Informationstyp, den Sie auswählen, wird separat angewendet, und nur einer dieser Typen vertraulicher Informationen muss angewendet werden, damit die Richtlinie auf die Nachricht angewendet wird. Weitere Informationen zu benutzerdefinierten Typen vertraulicher Informationen finden Sie [unter Learn about sensitive information types](sensitive-information-type-learn-about.md). |
| **Nachricht wird von einer dieser Domänen empfangen**  <br><br> **Nachricht wird von keinem dieser Domänen empfangen** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder E-Mail-Adressen in empfangene Nachrichten ein- oder auszuschließen. Geben Sie jede Domäne oder E-Mail-Adresse ein, und trennen Sie mehrere Domänen oder E-Mail-Adressen mit einem Komma. Jede eingegebene Domäne oder E-Mail-Adresse wird separat angewendet, es muss nur eine Domäne oder E-Mail-Adresse gelten, damit die Richtlinie auf die Nachricht angewendet wird. <br><br> Wenn Sie alle E-Mails aus einer bestimmten Domäne überprüfen möchten, aber Nachrichten ausschließen möchten, die nicht überprüft  werden müssen (Newsletter, Ankündigungen und so weiter), müssen Sie eine Nachricht von einer dieser Domänenbedingung, die die E-Mail-Adresse ausschließt, konfigurieren (Beispiel "newsletter@contoso.com"). |
| **Nachricht wird an eine dieser Domänen gesendet**  <br><br> **Nachricht wird nicht an diese Domänen gesendet** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder E-Mail-Adressen in gesendete Nachrichten ein- oder auszuschließen. Geben Sie jede Domäne oder E-Mail-Adresse ein, und trennen Sie mehrere Domänen oder E-Mail-Adressen mit einem Komma. Jede Domäne oder E-Mail-Adresse wird separat angewendet, nur eine Domäne oder E-Mail-Adresse muss gelten, damit die Richtlinie auf die Nachricht angewendet wird. <br><br> Wenn Sie alle an eine bestimmte Domäne gesendeten E-Mails überprüfen, aber gesendete Nachrichten ausschließen möchten, die keine Überprüfung benötigen, müssen Sie zwei Bedingungen konfigurieren: <br> – Eine Nachricht wird an eine dieser Domänen **gesendet,** die die Domäne definiert ("contoso.com"), UND <br> – Eine **Nachricht wird nicht an eine** dieser Domänen gesendet, die die E-Mail-Adresse ("subscriptions@contoso.com") ausschließt. |
| **Nachricht wird mit einer der folgenden Bezeichnungen klassifiziert**  <br><br> **Nachricht wird nicht mit diesen Bezeichnungen klassifiziert** | So wenden Sie die Richtlinie an, wenn bestimmte Aufbewahrungsbezeichnungen in einer Nachricht eingeschlossen oder ausgeschlossen werden. Aufbewahrungsbezeichnungen müssen separat konfiguriert werden, und konfigurierte Bezeichnungen werden als Teil dieser Bedingung ausgewählt. Jede von Ihnen unterschiedliche Bezeichnung wird separat angewendet (nur eine dieser Bezeichnungen muss gelten, damit die Richtlinie auf die Nachricht angewendet wird). Weitere Informationen zu Aufbewahrungsbezeichnungen finden Sie [unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)|
| **Nachricht enthält eines dieser Wörter**  <br><br> **Nachricht enthält keines dieser Wörter** | Um die Richtlinie anzuwenden, wenn bestimmte Wörter oder Ausdrücke in einer Nachricht eingeschlossen oder ausgeschlossen werden, geben Sie jedes Wort durch ein Komma getrennt ein. Verwenden Sie für Ausdrücke mit zwei oder mehr Wörtern Anführungszeichen um den Ausdruck. Jedes wort oder ausdruck, das Sie eingeben, wird separat angewendet (nur ein Wort muss gelten, damit die Richtlinie auf die Nachricht angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Anlage enthält eines dieser Wörter**  <br><br> **Anlage enthält keines dieser Wörter** | Um die Richtlinie anzuwenden, wenn bestimmte Wörter oder Ausdrücke in einer Nachrichtenanlage (z. B. einem Word-Dokument) eingeschlossen oder ausgeschlossen werden, geben Sie jedes Wort durch ein Komma getrennt ein. Verwenden Sie für Ausdrücke mit zwei oder mehr Wörtern Anführungszeichen um den Ausdruck. Jedes wort oder ausdruck, das Sie eingeben, wird separat angewendet (nur ein Wort muss angewendet werden, damit die Richtlinie auf die Anlage angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Anlage ist einer dieser Dateitypen**  <br><br> **Anlage ist keiner dieser Dateitypen** | Geben Sie zum Überwachen der Kommunikation, die bestimmte Anlagentypen einschließt oder ausschließt, die Dateierweiterungen ein (z. B. EXE oder .pdf). Wenn Sie mehrere Dateierweiterungen hinzufügen oder ausschließen möchten, geben Sie diese in separaten Zeilen ein. Nur eine Anlagenerweiterung muss übereinstimmen, damit die Richtlinie angewendet wird.|
| **Nachricht ist größer als**  <br><br> **Die Nachrichtengröße ist nicht größer als** | Verwenden Sie diese Bedingungen, um Nachrichten basierend auf einer bestimmten Größe zu überprüfen, um die maximale oder minimale Größe einer Nachricht anzugeben, bevor sie überprüft werden kann. Wenn Sie beispielsweise  angeben, dass die Nachrichtengröße größer als \> **1,0 MB** ist, werden alle Nachrichten, die 1,01 MB und größer sind, überprüft. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
| **Anlage ist größer als**  <br><br> **Anlage ist nicht größer als** | Um Nachrichten basierend auf der Größe ihrer Anlagen zu überprüfen, geben Sie die maximale oder minimale Größe einer Anlage an, bevor die Nachricht und ihre Anlagen überprüft werden können. Wenn Sie z. B. **Anlage** größer als \> **2,0 MB** angeben, werden alle Nachrichten mit Anlagen ab 2,01 MB überprüft. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Übereinstimmende Wörter und Ausdrücke in E-Mails oder Anlagen
<a name="Matchwords"> </a>

Jedes Wort, das Sie eingeben und mit einem Komma trennen, wird separat angewendet (nur ein Wort muss gelten, damit die Richtlinienbedingung auf die E-Mail oder Anlage angewendet wird). Verwenden wir beispielsweise die Bedingung **Message** enthält eines dieser Wörter mit den Schlüsselwörtern "Banker", "vertraulich" und "Insiderhandel" getrennt durch ein Komma (Banker, vertraulich, Insiderhandel). Die Richtlinie gilt für alle Nachrichten, die das Wort "Banker", "vertraulich" oder den Ausdruck "Insiderhandel" enthalten. Nur eins der Wörter oder einer der Ausdrücke muss vorkommen, damit die Richtlinienbedingung zutrifft. Wörter in der Nachricht oder Anlage müssen genau mit dem übereinstimmen, was Sie eingeben.

>[!IMPORTANT]
>Beim Importieren einer benutzerdefinierten Wörterbuchdatei muss jedes Wort oder jeder Ausdruck durch eine Wagenrücklauf- und eine separate Zeile getrennt werden. <br> Beispiel: <br><br>
>*Banker* <br>
>*vertraulich* <br>
>*Insiderhandel*

Um E-Mail-Nachrichten und Anlagen auf [](create-test-tune-dlp-policy.md) dieselben Schlüsselwörter zu [](create-a-keyword-dictionary.md) überprüfen, erstellen Sie eine Richtlinie zur Verhinderung von Datenverlust mit einem benutzerdefinierten Schlüsselwortwörterbuch für die Begriffe, die Sie in Nachrichten scannen möchten. Diese Richtlinienkonfiguration identifiziert definierte Schlüsselwörter, die in der E-Mail-Nachricht **ODER** in der E-Mail-Anlage angezeigt werden. Verwenden der standardmäßigen bedingten Richtlinieneinstellungen *(* Nachricht enthält eines dieser Wörter und *Attachment* enthält eines dieser Wörter ) zum Identifizieren von Begriffen in Nachrichten und in Anlagen erfordert, dass die Begriffe **sowohl** in der Nachricht als auch in der Anlage vorhanden sind.
  
#### <a name="enter-multiple-conditions"></a>Eingeben mehrerer Bedingungen

Wenn Sie mehrere Bedingungen eingeben, verwendet Microsoft 365 alle Bedingungen zusammen, um zu bestimmen, wann die Kommunikationskonformitätsrichtlinie auf Kommunikationselemente angewendet werden soll. Wenn Sie mehrere Bedingungen einrichten, müssen alle Bedingungen erfüllt sein, damit die Richtlinie angewendet wird, es sei denn, Sie geben eine Ausnahme ein. Sie benötigen beispielsweise eine Richtlinie, die gilt, wenn eine Nachricht das Wort "Trade" enthält und größer als 2 MB ist. Wenn die Nachricht jedoch auch die Wörter "Genehmigt von Contoso financial" enthält, sollte die Richtlinie nicht gelten. In diesem Beispiel werden die drei Bedingungen wie folgt definiert:
  
- **Nachricht enthält eines dieser Wörter** mit dem Schlüsselwort "Trade"
- **Die Nachrichtengröße ist größer als**, mit dem Wert 2 MB.
- **Message contains none of these words**, with the keywords "Approved by Contoso financial team"

### <a name="review-percentage"></a>Überprüfen des Prozentsatzes

Wenn Sie die zu überprüfende Menge an Inhalten reduzieren möchten, können Sie einen Prozentsatz aller Kommunikationen angeben, die von einer Kommunikationskonformitätsrichtlinie geregelt werden. Eine zufällige Stichprobe von Inhalten wird in Echtzeit aus dem Gesamtprozentsatz der Inhalte ausgewählt, die den gewählten Richtlinienbedingungen entsprechen. Wenn Sie möchten, dass Prüfer alle Elemente prüfen, können Sie in einer Richtlinie zur Kommunikationscompliance **100 %** konfigurieren.

## <a name="privacy"></a>Datenschutz

Der Schutz des Datenschutzes von Benutzern, die richtlinienkonform sind, ist wichtig und kann zur Förderung der Objektivität bei Der Untersuchung und Analyse von Daten für Kommunikationskonformitätswarnungen beitragen. Diese Einstellung gilt nur für Benutzernamen, die in der Kommunikationskonformitätslösung angezeigt werden. Es hat keine Auswirkungen darauf, wie Namen in anderen Compliancelösungen oder im Admin Center angezeigt werden.

Für Benutzer mit einer Übereinstimmung mit der Kommunikationskonformität können Sie unter Kommunikationskonformitätseinstellungen eine der **folgenden Einstellungen auswählen:**

- **Anonymisierte Versionen** von Benutzernamen anzeigen: Benutzernamen werden anonymisiert, um zu verhindern, dass Benutzer in der Rollengruppe *Communication Compliance Analyst* sehen, wer Richtlinienwarnungen zugeordnet ist. Benutzern in der *Rollengruppe "Kommunikations-Compliance-Prüfer"* werden immer Benutzernamen angezeigt, nicht die anonymisierten Versionen. Beispielsweise würde ein Benutzer "Grace Taylor" in allen Bereichen der Kommunikationskonformität mit einem randomisierten Pseudonym wie "AnonIS8-988" angezeigt. Wenn Sie diese Einstellung wählen, werden alle Benutzer mit aktuellen und früheren Richtlinienübereinstimmungen anonymisiert und gelten für alle Richtlinien. Benutzerprofilinformationen in den Kommunikationskonformitätsbenachrichtigungsdetails stehen bei Auswahl dieser Option nicht zur Verfügung. Benutzernamen werden jedoch beim Hinzufügen neuer Benutzer zu vorhandenen Richtlinien oder beim Zuweisen von Benutzern zu neuen Richtlinien angezeigt. Wenn Sie diese Einstellung deaktivieren möchten, werden Benutzernamen für alle Benutzer mit aktuellen oder früheren Richtlinien übereinstimmungen angezeigt.
- **Anonymisierte Versionen von Benutzernamen** nicht anzeigen: Benutzernamen werden für alle aktuellen und vergangenen Richtlinien übereinstimmungen für Kommunikationskonformitätswarnungen angezeigt. Benutzerprofilinformationen (Name, Titel, Alias sowie Organisation oder Abteilung) werden für den Benutzer für alle Warnungen zur Kommunikationskonformität angezeigt.

## <a name="notice-templates"></a>Benachrichtigungsvorlagen

Sie können Benachrichtigungsvorlagen erstellen, wenn Sie Benutzern eine E-Mail-Erinnerungsbenachrichtigung für Richtlinien übereinstimmungen als Teil des Problembe behebens senden möchten. Benachrichtigungen können nur an die E-Mail-Adresse des Benutzers gesendet werden, die der Richtlinien übereinstimmung zugeordnet ist, die die spezifische Warnung zur Behebung generiert hat. Wenn Sie eine Benachrichtigungsvorlage auswählen, die auf einen Richtlinienverstoß als Teil des Korrekturworkflows angewendet werden soll, können Sie die in der Vorlage definierten Feldwerte akzeptieren oder die Felder bei Bedarf überschreiben.

Hinweisvorlagen sind benutzerdefinierte E-Mail-Vorlagen, in denen Sie die folgenden Meldungsfelder im Bereich Kommunikationskonformitätseinstellungen **definieren** können:

|**Field**|**Erforderlich**| **Details** |
|:-----|:-----|:-----|
|**Vorlagenname** | Ja | Anzeigename für die Benachrichtigungsvorlage, die Sie im Benachrichtigungsworkflow während der Korrektur auswählen, unterstützt Textzeichen. |
| **Absenderadresse** | Ja | Die Adresse eines oder mehrerer Benutzer oder Gruppen, die die Nachricht an den Benutzer mit einer Richtlinienab übereinstimmung senden, ausgewählt aus Active Directory für Ihr Abonnement. |
| **CC- und BCC-Adressen** | Nein | Optionale Benutzer oder Gruppen, die über die Richtlinienab übereinstimmung benachrichtigt werden sollen, ausgewählt aus Active Directory für Ihr Abonnement. |
| **Betreff** | Ja | Informationen, die in der Betreffzeile der Nachricht angezeigt werden, unterstützen Textzeichen. |
| **Nachrichtentext** | Ja | Informationen, die im Nachrichtentext angezeigt werden, unterstützen Text- oder HTML-Werte. |

### <a name="html-for-notices"></a>HTML für Hinweise

Wenn Sie mehr als eine einfache textbasierte E-Mail-Nachricht für Benachrichtigungen erstellen möchten, können Sie eine ausführlichere Nachricht mithilfe von HTML im Nachrichtentextfeld einer Benachrichtigungsvorlage erstellen. Das folgende Beispiel enthält das Nachrichtentextformat für eine einfache HTML-basierte E-Mail-Benachrichtigungsvorlage:

```HTML
<!DOCTYPE html>
<html>
    <body>
        <h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
        <p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
        <p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
        <p>Thank you,</p>
        <p><em>Human Resources</em></p>
    </body>
</html>
```

>[!NOTE]
>Die Html href-Attributimplementierung in den Benachrichtigungsvorlagen zur Kommunikationskonformität unterstützt derzeit nur einfache Anführungszeichen anstelle doppelter Anführungszeichen für URL-Verweise.

## <a name="filters"></a>Filter

Kommunikationskonformitätsfilter ermöglichen das Filtern und Sortieren von Warnmeldungen für schnellere Untersuchungs- und Korrekturaktionen. Die Filterung ist auf  den Registerkarten **Ausstehend** und Aufgelöst für jede Richtlinie verfügbar. Um einen Filter oder Filtersatz als gespeicherte Filterabfrage zu speichern, müssen mindestens ein Wert als Filterauswahl konfiguriert werden. In der folgenden Tabelle sind Filterdetails aufgeführt:

|**Filter**|**Details**|
|:-----|:-----|
| **Date** | Das Datum, an dem die Nachricht von einem Benutzer in Ihrer Organisation gesendet oder empfangen wurde. Um nach einem einzelnen Tag zu filtern, wählen Sie einen Datumsbereich aus, der mit dem Tag beginnt, an dem Ergebnisse erzielt werden sollen, und enden mit dem folgenden Tag. Wenn Sie beispielsweise Ergebnisse für den 20.09.2020 filtern möchten, würden Sie einen Filterdatumsbereich vom 20.09.2020-21.09.2020 auswählen.|
| **Dateiklasse** | Die Klasse der Nachricht basierend auf dem Nachrichtentyp, entweder *Nachricht* oder *Anlage*. |
| **Verfügt über Eine Anlage** | Die Anlagenpräsenz in der Nachricht. |
| **Elementklasse** | Die Quelle der Nachricht basierend auf dem Nachrichtentyp, E-Mail, Microsoft Team Chat, Bloomberg usw. Weitere Informationen zu allgemeinen Elementtypen und Nachrichtenklassen finden Sie unter [Elementtypen und Nachrichtenklassen](/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Empfängerdomänen** | Die Domäne, an die die Nachricht gesendet wurde. Diese Domäne ist in der Regel Standardmäßig Ihre Microsoft 365-Abonnementdomäne. |
| **Empfänger** | Der Benutzer, an den die Nachricht gesendet wurde. |
| **Sender** | Die Person, die die Nachricht gesendet hat. |
| **Absenderdomäne** | Die Domäne, die die Nachricht gesendet hat. |
| **Größe** | Die Größe der Nachricht in KB. |
| **Betreff/Titel** | Der Betreff der Nachricht oder der Chattitel. |
| **Tags** | Die einer Nachricht zugewiesenen Tags, entweder *"Questionable",* *"Compliant"* oder *"Non-compliant".* |
| **Eskaliert an** | Der Benutzername der Person, die teil einer Nachrichteneskalationsaktion ist. |
| **Klassifizierungen** | Der Name der integrierten und benutzerdefinierten Klassifizierungen, die für die Nachricht gelten. Beispiele hierfür sind *Anstößige Sprache,* *gezielte Belästigung,* *Profanität,* *Bedrohung* und vieles mehr.

## <a name="alert-policies"></a>Warnungsrichtlinien

Nachdem Sie eine Richtlinie konfiguriert haben, wird automatisch eine entsprechende Warnungsrichtlinie erstellt, und es werden Warnungen für Nachrichten generiert, die den in der Richtlinie definierten Bedingungen entsprechen. Standardmäßig wird allen Richtlinienauslösern in der zugeordneten Warnungsrichtlinie ein Mittlerer Schweregrad zugewiesen. Warnungen werden für eine Kommunikationskonformitätsrichtlinie generiert, sobald der Schwellenwert für aggregationsauslöser in der zugeordneten Warnungsrichtlinie erreicht ist.

Für Kommunikationskonformitätsrichtlinien sind die folgenden Warnungsrichtlinienwerte standardmäßig konfiguriert:

|**Warnungsrichtlinienauslöser**|**Standardwert**|
|:-----|:-----|
| Aggregation | Einfache Aggregation |
| Schwellenwert | 4 Aktivitäten |
| Fenster | 60 Minuten |

>[!Note]
>Die Schwellenwertauslösereinstellungen für Die Warnungsrichtlinie für Aktivitäten unterstützen einen Mindestwert von 3 oder höher für Richtlinien zur Kommunikationskonformität.

Sie können die Standardeinstellungen für Trigger für die Anzahl der Aktivitäten, den Zeitraum  für die Aktivitäten und für bestimmte Benutzer in Warnungsrichtlinien auf der Seite Warnungsrichtlinien im Security & Compliance Center ändern.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Ändern des Schweregrads für eine Warnungsrichtlinie

Wenn Sie den schweregrad ändern möchten, der in einer Warnungsrichtlinie für eine bestimmte Kommunikationskonformitätsrichtlinie zugewiesen ist, führen Sie die folgenden Schritte aus:

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Richtlinien**.

3. Wählen Sie auf der Seite  Richtlinien die  Option Office **365-Warnung** aus, um die Seite Benachrichtigungsrichtlinien im **Office 365 Security & Compliance Center zu öffnen.**

4. Aktivieren Sie das Kontrollkästchen für die Kommunikationskonformitätsrichtlinie, die Sie aktualisieren möchten, und wählen Sie **dann Richtlinie bearbeiten aus.**

5. Wählen Sie **auf der Registerkarte** Beschreibung die Dropdownliste **Schweregrad aus,** um die Richtlinienwarnstufe zu konfigurieren.

6. Wählen **Sie Speichern** aus, um den neuen Schweregrad auf die Richtlinie anzuwenden.

7. Wählen **Sie Schließen** aus, um die Seite warnungsrichtliniendetails zu beenden.

## <a name="power-automate-flows"></a>Power Automate-Flüsse

[Microsoft Power Automate ist](/power-automate/getting-started) ein Workflowdienst, der Aktionen in verschiedenen Anwendungen und Diensten automatisiert. Durch die Verwendung von Vorlagenflüssen oder manuell erstellten Aufgaben können Sie allgemeine Aufgaben automatisieren, die diesen Anwendungen und Diensten zugeordnet sind. Wenn Sie Power Automate-Flüsse für die Kommunikationskonformität aktivieren, können Sie wichtige Aufgaben für Warnungen und Benutzer automatisieren. Sie können Power Automate-Flüsse so konfigurieren, dass Manager benachrichtigt werden, wenn Benutzer Benachrichtigungen zur Kommunikationskonformität und andere Anwendungen haben.

Kunden mit Microsoft 365-Abonnements, die kommunikationskonform sind, benötigen keine zusätzlichen Power Automate-Lizenzen, um die empfohlene Standardmäßige Power Automate-Vorlage zur Kommunikationskonformität zu verwenden. Die Standardvorlage kann angepasst werden, um Ihre Organisation zu unterstützen und zentrale Szenarien für die Kommunikationskonformität zu abdecken. Wenn Sie premium Power Automate-Features in diesen Vorlagen verwenden, eine benutzerdefinierte Vorlage mit dem Microsoft 365-Complianceconnector erstellen oder Power Automate-Vorlagen für andere Compliancebereiche in Microsoft 365 verwenden, benötigen Sie möglicherweise zusätzliche Power Automate-Lizenzen.

>[!IMPORTANT]
>Erhalten Sie Beim Testen von Power Automate-Flüssen Aufforderungen zur zusätzlichen Lizenzüberprüfung? Ihre Organisation hat möglicherweise noch keine Dienstupdates für dieses Vorschaufeature erhalten. Updates werden bereitgestellt, und alle Organisationen mit Microsoft 365-Abonnements, die kommunikationskonform sind, sollten bis zum 30. Oktober 2020 über Lizenzunterstützung für Flüsse verfügen, die aus den empfohlenen Power Automate-Vorlagen erstellt wurden.

![Kommunikationskonformität Power Automate](../media/communication-compliance-power-automate.png)

Die folgende Power Automate-Vorlage wird Kunden bereitgestellt, um die Prozessautomatisierung für Kommunikationskonformitätswarnungen zu unterstützen:

- **Benachrichtigen des Managers,** wenn ein Benutzer eine Warnung zur Kommunikationskonformität hat: Einige Organisationen benötigen möglicherweise eine sofortige Verwaltungsbenachrichtigung, wenn ein Benutzer eine Warnung zur Kommunikationskonformität hat. Wenn dieser Fluss konfiguriert und ausgewählt ist, wird dem Vorgesetzten für den Fallbenutzer eine E-Mail mit den folgenden Informationen zu allen Warnungen gesendet:
    - Anwendbare Richtlinie für die Warnung
    - Datum/Uhrzeit der Warnung
    - Schweregrad der Warnung

### <a name="create-a-power-automate-flow"></a>Erstellen eines Power Automate-Ablaufs

Um einen Power Automate-Fluss aus einer empfohlenen Standardvorlage zu erstellen, verwenden Sie die Option Power **Automate-Flüsse** verwalten über das **Steuerelement Automatisieren,** wenn Sie direkt in einer Warnung arbeiten. Um einen Power Automate-Fluss mit **Power Automate-Flüssen** verwalten zu erstellen, müssen Sie Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss aus einer Standardvorlage zu erstellen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu Richtlinien zur Kommunikationskonformität, und wählen Sie die Richtlinie mit der Warnung aus, die  >   Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **Ausstehend** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen **Sie power Automate** im Menü Warnungsaktion aus.
4. Wählen Sie **auf der Seite Power**  Automate eine Standardvorlage aus dem Abschnitt Kommunikationskonformitätsvorlagen aus, die Ihnen auf der Seite gefällt.
5. Der Fluss listet die für den Fluss erforderlichen eingebetteten Verbindungen auf und zeigt an, ob die Verbindungsstatus verfügbar sind. Aktualisieren Sie bei Bedarf alle Verbindungen, die nicht als verfügbar angezeigt werden. Wählen Sie **Weiter** aus.
6. Standardmäßig sind die empfohlenen Flüsse mit den empfohlenen Kommunikationskonformitäts- und Microsoft 365-Dienstdatenfeldern vorkonfiguriert, die zum Abschließen der zugewiesenen Aufgabe für den Fluss erforderlich sind. Passen Sie bei Bedarf die  Flusskomponenten mithilfe des Steuerelements Erweiterte Optionen anzeigen an und konfigurieren Sie die verfügbaren Eigenschaften für die Flusskomponente.
7. Fügen Sie bei Bedarf weitere Schritte zum Fluss hinzu, indem Sie die Schaltfläche **Neuer Schritt** auswählen. In den meisten Fällen sollte diese Änderung für die empfohlenen Standardvorlagen nicht erforderlich sein.
8. Wählen **Sie Entwurf speichern** aus, um den Fluss für weitere Konfiguration zu einem späteren Zeitpunkt zu speichern, oder wählen Sie **Speichern** aus, um die Konfiguration für den Fluss zu vervollständigen.
9. Wählen **Sie Schließen** aus, um zur Power Automate-Flussseite zurückzukehren. Die neue Vorlage wird als Fluss  auf der Registerkarte Meine Flüsse aufgeführt und steht automatisch über das Power Automate-Steuerelement für den Benutzer zur Verfügung, der den Fluss beim Arbeiten mit Kommunikationskonformitätswarnungen erstellt hat.

### <a name="share-a-power-automate-flow"></a>Freigeben eines Power Automate-Ablaufs

Standardmäßig sind von einem Benutzer erstellte Power Automate-Flüsse nur für diesen Benutzer verfügbar. Damit andere Benutzer der Kommunikationskonformität Zugriff haben und einen Fluss verwenden können, muss der Fluss vom Flussersteller freigegeben werden. Wenn Sie einen Fluss freigeben möchten, verwenden Sie das **Power Automate-Steuerelement,** wenn Sie direkt in einer Warnung arbeiten.

Um einen Power Automate-Fluss freigeben zu können, müssen Sie Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.
Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss zu teilen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu Richtlinien zur Kommunikationskonformität, und wählen Sie die Richtlinie mit der Warnung aus, die  >   Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **Ausstehend** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen **Sie power Automate** im Menü Warnungsaktion aus.
4. Wählen Sie **auf der Seite Power Automate Flows** die Registerkarte Meine **Flüsse** oder **Teamflüsse** aus.
5. Wählen Sie den zu teilende Fluss aus, und wählen Sie **dann im** Menü Flussoptionen die Option Freigeben aus.
6. Geben Sie auf der Seite Flussfreigabe den Namen des Benutzers oder der Gruppe ein, den Sie als Besitzer für den Fluss hinzufügen möchten.
7. Wählen Sie **im Dialogfeld Verbindung verwendet** **ok** aus, um zu bestätigen, dass der hinzugefügte Benutzer oder die hinzugefügte Gruppe Vollzugriff auf den Fluss hat.

### <a name="edit-a-power-automate-flow"></a>Bearbeiten eines Power Automate-Ablaufs

Wenn Sie einen Fluss bearbeiten müssen, verwenden Sie das **Power Automate-Steuerelement,** wenn Sie direkt in einer Warnung arbeiten. Zum Bearbeiten eines Power Automate-Ablaufs müssen Sie Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss zu bearbeiten:

1. Wechseln Sie im Microsoft 365 Compliance Center zu Richtlinien zur Kommunikationskonformität, und wählen Sie die Richtlinie mit der Warnung aus, die  >   Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **Ausstehend** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen **Sie power Automate** im Menü Warnungsaktion aus.
4. Wählen Sie **auf der Seite Power Automate Flows** die Option Zu bearbeitende Fluss aus. Wählen **Sie im** Menü Flusssteuerelement bearbeiten aus.
5. Wählen Sie **die Auslassungseinstellungen** aus, um eine Flusskomponenteneinstellung zu ändern, oder die  >   **Auslassungspunkte**  >  **Löschen,** um eine Flusskomponente zu löschen.
6. Wählen **Sie Speichern** und dann Schließen **aus,** um die Bearbeitung des Ablaufs zu abschließen.

### <a name="delete-a-power-automate-flow"></a>Löschen eines Power Automate-Ablaufs

Wenn Sie einen Fluss löschen müssen, verwenden Sie das **Power Automate-Steuerelement,** wenn Sie direkt in einer Warnung arbeiten. Um einen Power Automate-Fluss zu löschen, müssen Sie Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss zu löschen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu Richtlinien zur Kommunikationskonformität, und wählen Sie die Richtlinie mit der Warnung aus, die  >   Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **Ausstehend** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen **Sie power Automate** im Menü Warnungsaktion aus.
4. Wählen Sie **auf der Seite Power Automate Flows** den zu löschende Fluss aus. Wählen **Sie im** Menü Flusssteuerelement die Option Löschen aus.
5. Wählen Sie im Dialogfeld Löschbestätigung die Option **Löschen** aus, um den Fluss zu entfernen, oder wählen Sie **Abbrechen** aus, um die Löschaktion zu beenden.

## <a name="reports-preview"></a>Berichte (Vorschau)

Das neue **Dashboard Berichte** ist der zentrale Ort zum Anzeigen aller Berichte zur Kommunikationskonformität. Berichts-Widgets bieten eine schnelle Ansicht der Einblicke, die am häufigsten für eine allgemeine Bewertung des Status von Kommunikations-Compliance-Aktivitäten benötigt werden. Informationen, die in den Berichts-Widgets enthalten sind, können nicht exportiert werden. Detaillierte Berichte enthalten ausführliche Informationen zu bestimmten Bereichen der Kommunikationskonformität und bieten die Möglichkeit, Informationen während der Überprüfung zu filtern, zu gruppieren, zu sortieren und zu exportieren.

![Dashboard für Kommunikationskonformitätsberichte](../media/communication-compliance-reports-dashboard.png)

Das **Berichtsdashboard** enthält die folgenden Berichts-Widgets und detaillierte Berichtslinks:

- **Widget für zuletzt verwendete** Richtlinienüber übereinstimmungen: Zeigt die Anzahl der Übereinstimmungen nach aktiver Richtlinie im Laufe der Zeit an.
- **Aufgelöste Elemente nach** Richtlinien-Widget: Zeigt die Anzahl von Richtlinienübersingwarnungen an, die nach Richtlinie im Laufe der Zeit aufgelöst wurden.
- **Benutzer mit den meisten Richtlinien-Übereinstimmungs-Widget:** zeigt die Benutzer (oder anonymisierten Benutzernamen) und die Anzahl der Richtlinien übereinstimmungen für einen bestimmten Zeitraum an.
- **Richtlinie mit den meisten Übereinstimmungs-Widget:** zeigt die Richtlinien und die Anzahl der Übereinstimmungen für einen bestimmten Zeitraum an, die für Übereinstimmungen am höchsten bis untersten Rang rangieren.
- **Eskalationen nach Richtlinien-Widget:** Zeigt die Anzahl der Eskalationen pro Richtlinie über einen bestimmten Zeitraum an.
- **Richtlinieneinstellungen und detaillierter** Statusbericht: bietet einen detaillierten Blick auf die Richtlinienkonfiguration und -einstellungen sowie den allgemeinen Status für jede Richtlinie (Übereinstimmungen und Aktionen) für Nachrichten. Enthält Richtlinieninformationen und die Art und Weise, wie Richtlinien Benutzern und Gruppen, Speicherorten, Prozentsätze, Prüfern, Status und wann die Richtlinie zuletzt geändert wurde, zugeordnet sind. Verwenden Sie *die Option Export,* um eine CSV-Datei mit den Berichtsdetails zu erstellen.
- **Detaillierter Bericht** zu Elementen und Aktionen pro Richtlinie: Überprüfen und Exportieren übereinstimmender Elemente und Korrekturaktionen pro Richtlinie. Enthält Richtlinieninformationen und die Art und Weise, wie Richtlinien zugeordnet sind:

    - Übereinstimmende Elemente
    - Eskalierte Elemente
    - Aufgelöste Elemente
    - Als kompatibel markiert
    - Als nicht kompatibel gekennzeichnet
    - Als fragwürdig markiert
    - Ausstehende Überprüfung von Elementen
    - Benutzer benachrichtigt
    - Fall erstellt
    
    Verwenden Sie *die Option Export,* um eine CSV-Datei mit den Berichtsdetails zu erstellen.
- **Detaillierter** Bericht zu Elementen und Aktionen pro Standort: Überprüfen und Exportieren übereinstimmender Elemente und Korrekturaktionen pro Microsoft 365-Speicherort. Enthält Informationen dazu, wie Arbeitsauslastungsplattformen zugeordnet sind:

    - Übereinstimmende Elemente
    - Eskalierte Elemente
    - Aufgelöste Elemente
    - Als kompatibel markiert
    - Als nicht kompatibel gekennzeichnet
    - Als fragwürdig markiert
    - Ausstehende Überprüfung von Elementen
    - Benutzer benachrichtigt
    - Fall erstellt

    Verwenden Sie *die Option Export,* um eine CSV-Datei mit den Berichtsdetails zu erstellen.
- **Aktivität nach detailliertem** Bericht des Benutzers: Überprüfen und Exportieren übereinstimmender Elemente und Korrekturaktionen pro Benutzer. Enthält Informationen dazu, wie Benutzern zugeordnet wird:

    - Übereinstimmende Elemente
    - Eskalierte Elemente
    - Aufgelöste Elemente
    - Als kompatibel markiert
    - Als nicht kompatibel gekennzeichnet
    - Als fragwürdig markiert
    - Ausstehende Überprüfung von Elementen
    - Benutzer benachrichtigt
    - Fall erstellt

    Verwenden Sie *die Option Export,* um eine CSV-Datei mit den Berichtsdetails zu erstellen.

## <a name="audit"></a>Überwachung

In einigen Fällen müssen Sie Aufsichts- oder Compliance-Auditoren Informationen bereitstellen, um die Überwachung von Benutzeraktivitäten und -kommunikationen nachzuweisen. Diese Informationen können eine Zusammenfassung aller Aktivitäten im Zusammenhang mit einer definierten Organisationsrichtlinie oder zu jeder Zeit sein, in der sich eine Kommunikationskonformitätsrichtlinie ändert. Kommunikationskonformitätsrichtlinien verfügen über integrierte Überwachungsprotokolle für die vollständige Bereitschaft für interne oder externe Prüfungen. Detaillierte Überwachungsverläufe jeder Erstellungs-, Bearbeitungs- und Löschaktion werden von Ihren Kommunikationsrichtlinien erfasst, um Einen Nachweis für Aufsichtsverfahren zu bieten.

>[!Important]
>Die Überwachung muss für Ihre Organisation aktiviert sein, bevor Kommunikationskonformitätsereignisse aufgezeichnet werden. Informationen zum Aktivieren der Überwachung finden Sie [unter Aktivieren des Überwachungsprotokolls](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Wenn Sie Aktualisierungsaktivitäten für Kommunikationskonformitätsrichtlinien anzeigen möchten, wählen Sie auf der Hauptseite das Steuerelement **Richtlinienupdates** exportieren für alle Richtlinien aus. Ihnen müssen die Rollen *Globaler Administrator* oder *Kommunikations-Compliance-Administrator zugewiesen* sein, um Updateaktivitäten exportieren zu können. Mit dieser Aktion wird eine Überwachungsdatei im CSV-Format generiert, die die folgenden Informationen enthält:

|**Field**|**Details**|
|:-----|:-----|
| **CreationDate** | Das Datum, an dem die Aktualisierungsaktivität in einer Richtlinie ausgeführt wurde. |
| **UserIds** | Der Benutzer, der die Aktualisierungsaktivität in einer Richtlinie ausgeführt hat. |
| **Operations** | Die aktualisierungsvorgänge, die für die Richtlinie ausgeführt werden. |
| **AuditData** | Dieses Feld ist die Wichtigste Datenquelle für alle Richtlinienaktualisierungsaktivitäten. Alle Aktualisierungsaktivitäten werden aufgezeichnet und durch Trennzeichen getrennt. |

Wenn Sie Aktivitäten zur Überprüfung der  Kommunikationskonformität für  eine Richtlinie anzeigen möchten, wählen Sie auf der Seite Übersicht für eine bestimmte Richtlinie das Steuerelement Überprüfungsaktivitäten exportieren aus. Ihnen müssen die Rollen *Globaler Administrator* oder *Kommunikations-Compliance-Administrator zugewiesen* sein, um Überprüfungsaktivitäten exportieren zu können. Mit dieser Aktion wird eine Überwachungsdatei im CSV-Format generiert, die die folgenden Informationen enthält:

|**Field**|**Details**|
|:-----|:-----|
| **CreationDate** | Das Datum, an dem die Überprüfungsaktivität in einer Richtlinie ausgeführt wurde. |
| **UserIds** | Der Benutzer, der die Überprüfungsaktivität in einer Richtlinie ausgeführt hat. |
| **Operations** | Die für die Richtlinie ausgeführten Überprüfungsvorgänge. |
| **AuditData** | Dieses Feld ist die wichtigste Datenquelle für alle Richtlinienüberprüfungsaktivitäten. Alle Überprüfungsaktivitäten werden aufgezeichnet und durch Kommatrennzeichen getrennt. |

Sie können überwachungsaktivitäten auch im einheitlichen Überwachungsprotokoll oder mit dem [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell-Cmdlet anzeigen.

Im folgenden Beispiel werden beispielsweise die Aktivitäten für alle Aufsichtsüberprüfungsaktivitäten (Richtlinien und Regeln) zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

In diesem Beispiel werden die Updateaktivitäten für Ihre Kommunikationskonformitätsrichtlinien zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Informationen zum Konfigurieren der Kommunikationskonformität für Ihre Microsoft 365-Organisation finden Sie unter [Configure communication compliance for your Microsoft 365 organization](communication-compliance-configure.md).
