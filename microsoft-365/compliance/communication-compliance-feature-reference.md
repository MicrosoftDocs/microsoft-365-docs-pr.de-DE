---
title: Referenz zu Kommunikationscompliancefeatures
description: Featurereferenz zur Kommunikationscompliance in Microsoft 365. Erfahren Sie mehr über Details und Spezifikationen für die einzelnen Featurekomponenten.
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
ms.openlocfilehash: f94d2bbb8a65a4004ee05b9d740f94ae841f9a4e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227375"
---
# <a name="communication-compliance-feature-reference"></a>Referenz zu Kommunikationscompliancefeatures

## <a name="policies"></a>Richtlinien

> [!IMPORTANT]
> Die Verwendung von PowerShell zum Erstellen und Verwalten von Richtlinien zur Kommunikationscompliance wird nicht unterstützt. Um diese Richtlinien zu erstellen und zu verwalten, müssen Sie die Richtlinienverwaltungssteuerelemente in der [Microsoft 365 Kommunikationscompliancelösung](https://compliance.microsoft.com/supervisoryreview)verwenden.

Im Microsoft 365 Compliance Center erstellen Sie Richtlinien zur Kommunikationscompliance für Microsoft 365-Organisationen. Richtlinien für die Kommunikationscompliance definieren, welche Kommunikationen und Benutzer in Ihrer Organisation überprüft werden sollen, definieren, welche benutzerdefinierten Bedingungen die Kommunikation erfüllen muss, und geben an, wer Überprüfungen durchführen soll. Benutzer, denen die Administratorrolle *"Kommunikationscompliance"* zugewiesen ist, können Richtlinien einrichten, und jeder Benutzer, dem diese Rolle zugewiesen ist, kann auf die Seite **"Kommunikationscompliance"** und die globalen Einstellungen im Microsoft 365 Compliance Center zugreifen. Bei Bedarf können Sie den Änderungsverlauf an einer Richtlinie in eine .csv datei (durch Trennzeichen getrennte Werte) exportieren, die auch den Status von warnungen ausstehenden Überprüfungen, eskalierten Elementen und aufgelösten Elementen enthält. Richtlinien können nicht umbenannt und gelöscht werden, wenn sie nicht mehr benötigt werden.

> [!NOTE]
> Aufsichtsrichtlinien, die im Security & Compliance Center für Office 365 Abonnements erstellt wurden, können nicht zu Microsoft 365 migriert werden. Wenn Sie von einem Office 365-Abonnement zu einem Microsoft 365-Abonnement migrieren, müssen Sie neue Richtlinien zur Kommunikationscompliance erstellen, um vorhandene Aufsichtsrichtlinien zu ersetzen.

## <a name="policy-templates"></a>Richtlinienvorlagen

Richtlinienvorlagen sind vordefinierte Richtlinieneinstellungen, mit denen Sie schnell Richtlinien für gängige Complianceszenarien erstellen können. Jede dieser Vorlagen weist Unterschiede in Bezug auf Bedingungen und Umfang auf, und alle Vorlagen verwenden die gleichen Arten von Scansignalen. Sie können aus den folgenden Richtlinienvorlagen auswählen:

|**Bereich**|**Richtlinienvorlage**|**Details**|
|:-----|:-----|:-----|
| **Anstößige Sprache und Anti-Belästigung** | Überwachen der Kommunikation auf anstößige Sprache | - Speicherorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Eingehend, Ausgehend, Intern <br> - Prozentsatz der Überprüfung: 100 % <br> - Bedingungen: Klassifizierer für anstößige Sprache |
| **Vertrauliche Informationen** | Überwachen der Kommunikation auf vertrauliche Informationen | - Speicherorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Eingehend, Ausgehend, Intern <br> - Prozentsatz der Überprüfung: 10 % <br> - Bedingungen: Vertrauliche Informationen, out-of-the-box-Inhaltsmuster und -typen, Benutzerwörterbuchoption, Anlagen größer als 1 MB |
| **Einhaltung gesetzlicher Bestimmungen** | Überwachen der Kommunikation auf Informationen im Zusammenhang mit der Einhaltung gesetzlicher Vorschriften | - Speicherorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Eingehend, Ausgehend <br> - Prozentsatz der Überprüfung: 10 % <br> - Bedingungen: Benutzerwörterbuchoption, Anlagen größer als 1 MB |
| **Interessengruppen** | Überwachen der Kommunikation zwischen zwei Gruppen oder zwei Benutzern, um Interessengruppen zu vermeiden | - Speicherorte: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Richtung: Intern <br> - Prozentsatz der Überprüfung: 100 % <br> - Bedingungen: Keine |

Die Kommunikation wird alle 24 Stunden ab dem Zeitpunkt der Erstellung von Richtlinien überprüft. Wenn Sie beispielsweise um 11:00 Uhr eine Richtlinie für anstößige Sprachen erstellen, sammelt die Richtlinie alle 24 Stunden um 11:00 Uhr die Kommunikationscompliancesignale. Das Bearbeiten einer Richtlinie ändert sich dieses Mal nicht. Navigieren Sie zur Spalte *"Letzte Richtlinienüberprüfung"* auf der Seite "Richtlinie", um das Datum und die Uhrzeit der letzten Überprüfung für eine **Richtlinie** anzuzeigen. Nach dem Erstellen einer neuen Richtlinie kann es bis zu 24 Stunden dauern, bis das Datum und die Uhrzeit der ersten Richtlinienüberprüfung angezeigt werden. Datum und Uhrzeit der letzten Überprüfung werden in die Zeitzone Ihres lokalen Systems konvertiert.

## <a name="pausing-a-policy-preview"></a>Anhalten einer Richtlinie (Vorschau)

Nachdem Sie eine Richtlinie zur Kommunikationscompliance erstellt haben, wird die Richtlinie bei Bedarf möglicherweise vorübergehend angehalten. Das Anhalten einer Richtlinie kann zum Testen oder Beheben von Richtlinienüberstimmungen oder zum Optimieren von Richtlinienbedingungen verwendet werden. Anstatt eine Richtlinie unter diesen Umständen zu löschen, behält das Anhalten einer Richtlinie auch vorhandene Richtlinienwarnungen und Nachrichten für laufende Untersuchungen und Überprüfungen bei. Das Anhalten einer Richtlinie verhindert die Überprüfung und Generierung von Warnungen für alle in der Richtlinie definierten Benutzernachrichtenbedingungen für den Zeitraum, an dem die Richtlinie angehalten wird. Um eine Richtlinie anzuhalten oder neu zu starten, müssen Benutzer Mitglied der Rollengruppe *"Kommunikationscompliance-Administrator"* sein.

Navigieren Sie zum Anhalten einer Richtlinie zur Seite **"Richtlinie",** wählen Sie eine Richtlinie aus, und wählen Sie dann auf der Symbolleiste "Aktionen" die Option **"Richtlinie anhalten"** aus. Bestätigen Sie im **Bereich "Richtlinie anhalten",** dass Sie die Richtlinie anhalten möchten, indem Sie **"Anhalten"** auswählen. In einigen Fällen kann es bis zu 24 Stunden dauern, bis eine Richtlinie angehalten wurde. Nachdem die Richtlinie angehalten wurde, werden keine Warnungen für Nachrichten erstellt, die mit der Richtlinie übereinstimmen. Nachrichten, die Warnungen zugeordnet sind, die vor dem Anhalten der Richtlinie erstellt wurden, bleiben jedoch zur Untersuchung, Überprüfung und Behebung verfügbar.

Der Richtlinienstatus für angehaltene Richtlinien weist möglicherweise auf mehrere Zustände hin:

- **Aktiv:** Die Richtlinie ist aktiv
- **Angehalten:** Die Richtlinie ist vollständig angehalten.
- **Anhalten:** Die Richtlinie wird gerade angehalten.
- **Fortsetzen:** Die Richtlinie, die gerade fortgesetzt wird.
- **Fehler beim Fortsetzen:** Beim Fortsetzen der Richtlinie ist ein Fehler aufgetreten. Zeigen Sie für die Fehlerstapelablaufverfolgung mit der Maus auf den *Status "Fehler beim Fortsetzen"* in der Spalte "Status" auf der Seite "Richtlinie".
- **Fehler beim Anhalten:** Beim Anhalten der Richtlinie ist ein Fehler aufgetreten. Zeigen Sie für die Fehlerstapelablaufverfolgung mit der Maus auf den *Status "Fehler beim Anhalten"* in der Spalte "Status" auf der Seite "Richtlinie".

Um eine Richtlinie fortzusetzen, navigieren Sie zur Seite **"Richtlinie",** wählen Sie eine Richtlinie aus, und wählen Sie dann auf der Symbolleiste "Aktionen" die Option **"Richtlinie fortsetzen"** aus. Bestätigen Sie im Bereich **"Richtlinie fortsetzen",** dass Sie die Richtlinie fortsetzen möchten, indem Sie **"Fortsetzen"** auswählen. In einigen Fällen kann es bis zu 24 Stunden dauern, bis eine Richtlinie fortgesetzt wird. Nachdem die Richtlinie fortgesetzt wurde, werden Warnungen für Nachrichten erstellt, die mit der Richtlinie übereinstimmen, und sie stehen zur Untersuchung, Überprüfung und Behebung zur Verfügung.

## <a name="permissions"></a>Berechtigungen

> [!IMPORTANT]
> Standardmäßig haben globale Administratoren keinen Zugriff auf Kommunikationscompliancefeatures. Die in diesem Schritt zugewiesenen Rollen sind erforderlich, bevor auf Kommunikationscompliancefeatures zugegriffen werden kann.

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationscompliancefeatures verwendet werden. Um **die Kommunikationscompliance** als Menüoption in Microsoft 365 Compliance Center verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, müssen Sie den Rollengruppen *"Kommunikationscompliance"* oder *"Kommunikationscompliance-Administrator"* zugewiesen werden. Um nach der anfänglichen Konfiguration auf Kommunikationscompliancefeatures zuzugreifen und diese zu verwalten, müssen Benutzer Mitglied mindestens einer Rollengruppe für die Kommunikationscompliance sein.

Je nachdem, wie Sie Kommunikationsrichtlinien und -warnungen verwalten möchten, müssen Sie Benutzern bestimmte Rollengruppen zuweisen. Sie können bestimmten Rollengruppen Benutzer mit unterschiedlichen Compliance-Verantwortlichkeiten zuweisen, um unterschiedliche Bereiche der Kommunikationscompliancefeatures zu verwalten. Sie können auch alle Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Betrachter der Rollengruppe *"Kommunikationscompliance"* zuweisen. Verwenden Sie eine einzelne Rollengruppe oder mehrere Rollengruppen, um Ihre Compliance-Verwaltungsanforderungen am besten zu erfüllen.

Wählen Sie bei der Konfiguration der Kommunikationscompliance aus den folgenden Rollengruppenoptionen aus:

|**Rollengruppe**|**Rollengruppenberechtigungen**|
|:-----|:-----|
| **Kommunikationscompliance** | Verwenden Sie diese Rollengruppe, um die Kommunikationscompliance für Ihre Organisation in einer einzigen Gruppe zu verwalten. Indem Sie alle Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Betrachter hinzufügen, können Sie Kommunikationscomplianceberechtigungen in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationscompliance. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationscompliance zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikationscompliance-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationscompliance zu konfigurieren und später die Administratoren der Kommunikationscompliance in eine definierte Gruppe zu unterteilen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien zur Kommunikationscompliance, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Meldungswarnungen anzeigen. |
| **Kommunikationscompliance-Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Kommunikationscomplianceanalysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten anzeigen (nicht Nachrichteninhalte), an andere Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht auflösen. |
| **Kommunikationscompliance-Ermittler** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Ermittler für die Kommunikationscompliance fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und Inhalte anzeigen, an andere Prüfer eskalieren, zu einem Advanced eDiscovery Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Kommunikationscompliance-Anzeigender** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Startseite zur Kommunikationscompliance auf alle Berichterstellungs-Widgets zugreifen und alle Kommunikationscomplianceberichte anzeigen. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Für Organisationen, die die ursprünglichen Berechtigungen und Rollengruppen verwenden

Die neue Rollengruppenstruktur ersetzt die anfängliche Rollengruppenstruktur für die Kommunikationscompliance. Organisationen, die die Kommunikationscompliance bereits verwenden, mussten die Administratorrolle "Aufsichtsüberprüfung" zugewiesen werden, um mit der Kommunikationscompliance im Microsoft 365 Compliance Center zu beginnen. Darüber hinaus mussten Sie eine neue Rollengruppe für Prüfer mit den Rollen "Supervisory Review Administrator", "Case Management", "Compliance Administrator" und "Review" erstellen, um Nachrichten mit Richtlinienübereinstimmungen zu untersuchen und zu beheben. Im Wesentlichen befanden sich alle Administratoren und Prüfer in einer einzigen Rollengruppe, und jeder Benutzer verfügte über die gleichen Zugriffs- und Verwaltungsberechtigungen. Mit den neuesten Updates für die Kommunikationscompliance sollten Sie planen, von der vorherigen Rollengruppenstruktur zur neuen Rollengruppenstruktur zu migrieren. Die Unterstützung für die vorherige Rollengruppenstruktur wird eingestellt.

Sehen Sie sich das folgende Beispiel an, um Sie bei der Migrationsplanung zu unterstützen. Derzeit haben Sie drei Arten von Benutzern in Ihrer Organisation, IT-Administratoren, Triage und Prüfer. Diese drei Benutzertypen befinden sich in der vorherigen Rollengruppenstruktur und sind alle Mitglieder einer einzelnen Rollengruppe mit den folgenden zugewiesenen Rollen:

- Administrator der Aufsichtsüberprüfung
- Fallverwaltung
- Complianceadministrator
- Überprüfung

Um die Rollen für diese Benutzer für die neue Rollengruppenstruktur zu aktualisieren und die Zugriffs- und Verwaltungsberechtigungen für die Benutzer zu trennen, können Sie drei neue Gruppen und die zugeordneten neuen Rollengruppenzuweisungen in Betracht ziehen:

- **IT-Administratoren:** Der neuen Rollengruppe *"Kommunikationscompliance-Administrator"* zugewiesen.
- **Triage**: Zugewiesen der Rollengruppe *"Kommunikationscomplianceanalyst".*
- **Prüfer:** Zugewiesen der neuen Rollengruppe *"Kommunikationscompliance-Ermittler".*

## <a name="supervised-users"></a>Überwachte Benutzer

Bevor Sie mit der Kommunikationscompliance beginnen, müssen Sie feststellen, wer die Überprüfung der Kommunikation benötigt. In der Richtlinie identifizieren die E-Mail-Adressen der Benutzer Einzelpersonen oder Personengruppen, die überwacht werden sollen. Beispiele für diese Gruppen sind Microsoft 365 Gruppen, Exchange-basierte Verteilerlisten, Yammer Communitys und Microsoft Teams Kanäle. Sie können auch bestimmte Benutzer oder Gruppen mit einer bestimmten Ausschlussgruppe oder einer Liste von Gruppen vom Überprüfen ausschließen. Weitere Informationen zu Gruppentypen, die in Richtlinien zur Kommunikationscompliance unterstützt werden, finden Sie unter ["Erste Schritte mit der Kommunikationscompliance".](communication-compliance-configure.md#step-3-optional-set-up-groups-for-communication-compliance)

> [!IMPORTANT]
> Benutzer, die von Kommunikationscompliancerichtlinien abgedeckt werden, müssen entweder über eine Microsoft 365 E5 Compliance-Lizenz, eine Office 365 Enterprise E3-Lizenz mit dem Advanced Compliance-Add-On oder über ein Office 365 Enterprise E5-Abonnement verfügen. Wenn Sie nicht über einen vorhandenen Enterprise E5-Plan verfügen und die Kommunikationscompliance testen möchten, können Sie [sich für eine Testversion von Office 365 Enterprise E5 registrieren.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="reviewers"></a>Prüfer

Wenn Sie eine Richtlinie zur Kommunikationscompliance erstellen, müssen Sie bestimmen, wer die Nachrichten der überwachten Benutzer überprüft. In der Richtlinie identifizieren die E-Mail-Adressen der Benutzer Einzelpersonen oder Personengruppen, welche die überwachte Kommunikation überprüfen sollen. Alle Prüfer müssen über Postfächer verfügen, die auf Exchange Online gehostet werden, und sie müssen entweder den Rollen *"Kommunikationscomplianceanalyse"* oder "Untersuchung der *Kommunikationscompliance"* zugewiesen werden. Prüfern (Analysten oder Ermittlern) muss auch die Rolle *"Kommunikationscompliance Case Management"* zugewiesen sein. Wenn Prüfer zu einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuweisung zur Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess bereitstellt.

## <a name="groups-for-supervised-users-and-reviewers"></a>Gruppen für überwachte Benutzer und Prüfer

Um Ihre Einrichtung zu vereinfachen, erstellen Sie Gruppen für Personen, deren Kommunikation überprüft werden muss, und Gruppen für Personen, die diese Kommunikation überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Zum Beispiel, wenn Sie die Kommunikation zwischen zwei verschiedenen Personengruppen überprüfen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Wenn Sie eine Verteilergruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails von jedem Benutzer in der Verteilergruppe. Wenn Sie eine Microsoft 365 Gruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails, die an diese Gruppe gesendet werden, nicht die einzelnen E-Mails, die von jedem Gruppenmitglied empfangen werden.

Das Hinzufügen von Gruppen und Verteilerlisten zu Kommunikationscompliancerichtlinien ist Teil der allgemeinen Bedingungen und Regeln, sodass die maximale Anzahl von Gruppen und Verteilerlisten, die von einer Richtlinie unterstützt werden, von der Anzahl der Bedingungen abhängt, die der Richtlinie ebenfalls hinzugefügt wurden. Jede Richtlinie sollte ca. 20 Gruppen oder Verteilerlisten unterstützen, je nachdem, wie viele zusätzliche Bedingungen in der Richtlinie vorhanden sind.

## <a name="supported-communication-types"></a>Unterstützte Kommunikationstypen

Mit Richtlinien zur Kommunikationscompliance können Sie auswählen, ob Nachrichten auf einer oder mehreren der folgenden Kommunikationsplattformen als Gruppe oder als eigenständige Quellen gescannt werden sollen. Auf diesen Plattformen erfasste Kommunikationen werden für jede Richtlinie standardmäßig sieben Jahre lang aufbewahrt, auch wenn Benutzer Ihre Organisation verlassen und ihre Postfächer gelöscht werden.

- **Microsoft Teams:** Chatkommunikation in öffentlichen und privaten Microsoft Teams Kanälen und einzelnen Chats kann gescannt werden. Wenn Benutzer einer Richtlinie zur Kommunikationscompliance mit ausgewählter Microsoft Teams Abdeckung zugewiesen werden, wird die Chatkommunikation für die Benutzer automatisch in allen Microsoft Teams überwacht, in denen die Benutzer Mitglied sind. Microsoft Teams Abdeckung wird automatisch für vordefinierte Richtlinienvorlagen eingeschlossen und standardmäßig in der benutzerdefinierten Richtlinienvorlage ausgewählt. Teams Chats, die den Kommunikationscompliance-Richtlinienbedingungen entsprechen, können bis zu 48 Stunden dauern. Verwenden Sie die folgenden Gruppenverwaltungskonfigurationen, um einzelne Benutzerchats und Kanalkommunikation in Teams zu überwachen:

    - **Für Teams Chatkommunikation:** Weisen Sie der Richtlinie zur Kommunikationscompliance einzelne Benutzer oder eine [Verteilergruppe](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) zu. Diese Einstellung gilt für Eins-zu-eins- oder Eins-zu-viele-Benutzer/Chat-Beziehungen.
    - **Für Teams Kanalkommunikation:** Weisen Sie jeder Microsoft Teams Kanal oder Microsoft 365 Gruppe, die Sie überprüfen möchten, die einen bestimmten Benutzer enthält, der Richtlinie zur Kommunikationscompliance zu. Wenn Sie denselben Benutzer zu anderen Microsoft Teams-Kanälen oder Microsoft 365-Gruppen hinzufügen, stellen Sie sicher, dass Sie diese neuen Kanäle und Gruppen in die Richtlinie zur Kommunikationscompliance aufnehmen. Wenn ein Mitglied des Kanals ein überwachter Benutzer innerhalb einer Richtlinie ist und die *Eingehende* Richtung in einer Richtlinie konfiguriert ist, unterliegen alle nachrichten, die innerhalb des Kanals gesendet werden, der Überprüfung und potenziellen Richtlinienüberstimmungen (auch für Benutzer im Kanal, die nicht explizit überwacht werden). Beispielsweise ist Benutzer A der Besitzer oder ein Mitglied eines Kanals. Benutzer B und Benutzer C sind Mitglieder desselben Kanals und verwenden die Sprache, die mit der Richtlinie für anstößige Sprachen übereinstimmt, die nur Benutzer A überwacht. Benutzer B und Benutzer C erstellen Richtlinienübersprechungen für Unterhaltungen innerhalb des Kanals, obwohl sie nicht direkt in der Richtlinie für anstößige Sprachen überwacht werden. Teams Unterhaltungen zwischen Benutzer B und Benutzer C, die sich außerhalb des Kanals befinden, der Benutzer A enthält, unterliegen nicht der Richtlinie für anstößige Sprache, die Benutzer A enthält. Um Kanalmitglieder von der Aufsicht auszuschließen, wenn andere Mitglieder des Kanals explizit überwacht werden, deaktivieren Sie die Einstellung für die Richtung der *eingehenden* Kommunikation in der geltenden Richtlinie zur Kommunikationscompliance.
    - **Für Teams Chatkommunikation mit hybriden E-Mail-Umgebungen:** Kommunikationscompliance kann Chatnachrichten für Benutzer für Organisationen mit einer Exchange lokalen Bereitstellung oder einem externen E-Mail-Anbieter überwachen, die Microsoft Teams aktiviert haben. Sie müssen eine Verteilergruppe für die Benutzer mit lokalen oder externen Postfächern erstellen, die überwacht werden sollen. Beim Erstellen einer Kommunikationscompliancerichtlinie weisen Sie diese Verteilergruppe im Richtlinien-Assistenten als Auswahl für **überwachte Benutzer und Gruppen** zu. Weitere Informationen zu den Anforderungen und Einschränkungen für die Aktivierung von cloudbasiertem Speicher und Teams Unterstützung für lokale Benutzer finden Sie unter [Suchen nach Teams Chatdaten für lokale Benutzer.](search-cloud-based-mailboxes-for-on-premises-users.md)

- **Exchange E-Mail:** Postfächer, die im Rahmen Ihres Microsoft 365- oder Office 365-Abonnements auf Exchange Online gehostet werden, sind alle für die Überprüfung von Nachrichten berechtigt. Exchange E-Mail-Nachrichten und Anlagen, die den Richtlinienbedingungen für die Kommunikationscompliance entsprechen, kann bis zu 24 Stunden dauern. Die für die Kommunikationscompliance unterstützten Anlagetypen sind die gleichen wie die [Dateitypen, die für die Inhaltsüberprüfung von Exchange-Mailflussregeln unterstützt werden](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer:** Private Nachrichten und öffentliche Unterhaltungen und zugehörige Anlagen in Yammer Communitys können gescannt werden. Wenn ein Benutzer zur Kommunikationscompliance-Richtlinie hinzugefügt wird, die Yammer als definierten Kanal umfasst, wird die Kommunikation über alle Yammer Communitys hinweg, in denen der Benutzer Mitglied ist, in den Scanvorgang einbezogen. Yammer Chats und Anlagen, die den Richtlinienbedingungen für die Kommunikationscompliance entsprechen, können bis zu 24 Stunden dauern. Yammer müssen sich im [nativen Modus](/yammer/configure-your-yammer-network/overview-native-mode) befinden, damit Richtlinien zur Kommunikationscompliance Yammer Kommunikation und Anlagen überwacht werden können. Im nativen Modus befinden sich alle Yammer-Benutzer in Azure Active Directory (AAD), alle Gruppen sind Office 365-Gruppen, und alle Dateien werden in SharePoint Online gespeichert.

- **Skype for Business Online**: Chatnachrichten und zugehörige Anlagen in Skype for Business Online können überwacht werden. Die Bearbeitung von Skype for Business Online-Chats, in denen die Bedingungen für die Richtlinien zur Kommunikationscompliance erfüllt werden, kann bis zu 24 Stunden dauern. Überwachte Chatunterhaltungen stammen aus [vorherigen Unterhaltungen,](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)die in Skype for Business Online gespeichert wurden.  Verwenden Sie die folgende Gruppenverwaltungskonfiguration, um die Benutzerchatkommunikation in Skype for Business Online zu überwachen:

    - **Für Skype for Business Onlinechatkommunikation:** Weisen Sie der Kommunikationscompliancerichtlinie einzelne Benutzer oder eine [Verteilergruppe](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) zu. Diese Einstellung gilt für Eins-zu-eins- oder Eins-zu-viele-Benutzer/Chat-Beziehungen.

- **Drittanbieterquellen:** Sie können die Kommunikation auf Daten überprüfen, die in Postfächer in Ihrer Microsoft 365 Organisation aus Drittanbieterquellen wie [Instant Bloomberg,](archive-instant-bloomberg-data.md) [Slack,](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS und vielen anderen importiert wurden. Eine vollständige Liste der Connectors, die bei der Kommunikationscompliance unterstützt werden, finden Sie unter Archivieren von [Drittanbieterdaten.](archiving-third-party-data.md)

    Sie müssen einen Drittanbieter-Connector für Ihre Microsoft 365 Organisation konfigurieren, bevor Sie den Connector einer Kommunikationscompliancerichtlinie zuweisen können. Im Abschnitt **"Drittanbieterquellen"** des Assistenten für kommunikationscompliance-Richtlinien werden nur derzeit konfigurierte Drittanbieterconnectors angezeigt.

## <a name="policy-settings"></a>Richtlinieneinstellungen

### <a name="users"></a>Benutzer

Sie können **"Alle Benutzer"** auswählen oder bestimmte Benutzer in einer Richtlinie zur Kommunikationscompliance definieren. Durch Auswahl von **Alle Benutzer** wird die Richtlinie auf alle Benutzer und alle Gruppen angewendet, in denen ein Benutzer als Mitglied enthalten ist. Das Festlegen bestimmter Benutzer wendet die Richtlinie auf die festgelegten Benutzer und alle Gruppen an, in denen die festgelegten Benutzer als Mitglied enthalten sind.

### <a name="direction"></a>Richtung

Standardmäßig wird die **Bedingung "Richtung"** angezeigt und kann nicht entfernt werden. Kommunikationsrichtungseinstellungen in einer Richtlinie werden einzeln oder gemeinsam ausgewählt:

- **Eingehend:** Erkennt Kommunikationen, die von externen und internen Absendern **an** überwachte Benutzer gesendet werden, einschließlich anderer überwachter Benutzer in der Richtlinie.
- **Ausgehend:** Erkennt **Kommunikationen,** die von überwachten Benutzern an externe und interne Empfänger gesendet werden, einschließlich anderer überwachter Benutzer in der Richtlinie.
- **Intern:** Erkennt die Kommunikation **zwischen** den überwachten Benutzern oder Gruppen in der Richtlinie.

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Sie haben die Möglichkeit, vertrauliche Informationstypen als Teil Ihrer Kommunikationscompliance-Richtlinie zu verwenden. Typen vertraulicher Informationen sind entweder vordefinierte oder benutzerdefinierte Datentypen, mit denen Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr identifiziert und geschützt werden können. Im Rahmen von Informationen zur Verhinderung von [Datenverlust](dlp-learn-about-dlp.md)kann die Konfiguration vertraulicher Informationen Muster, Zeichennähe, Konfidenzniveaus und sogar benutzerdefinierte Datentypen verwenden, um vertrauliche Inhalte zu identifizieren und zu kennzeichnen. Die standardmäßigen Typen vertraulicher Informationen sind:

- Finanzwesen
- Gesundheit und Gesundheit
- Datenschutz
- Benutzerdefinierter Informationstyp

Weitere Informationen zu details zu vertraulichen Informationen und den Mustern in den Standardtypen finden Sie unter [Entitätsdefinitionen für Typen vertraulicher Informationen.](sensitive-information-type-entity-definitions.md)

### <a name="custom-keyword-dictionaries"></a>Benutzerdefinierte Schlüsselwörterbücher

Konfigurieren Sie benutzerdefinierte Schlüsselwörterbücher (oder Lexika), um eine einfache Verwaltung von spezifischen Schlüsselwörtern für Ihre Organisation oder Branche bereitzustellen. Schlüsselwörterbücher unterstützen bis zu 100 KB Ausdrücke (nach der Komprimierung) im Wörterbuch und unterstützen jede Sprache. Der Mandantengrenzwert liegt nach der Komprimierung ebenfalls bei 100 KB. Bei Bedarf können Sie mehrere benutzerdefinierte Schlüsselwörterbücher auf eine einzelne Richtlinie anwenden oder über ein einzelnes Schlüsselwortwörterbuch pro Richtlinie verfügen. Diese Wörterbücher werden in einer Kommunikationscompliancerichtlinie zugewiesen und können aus einer Datei (z. B. einer .csv oder .txt Liste) oder aus einer Liste stammen, die Sie [im Compliance Center importieren](create-a-keyword-dictionary.md)können. Verwenden Sie Benutzerwörterbücher, wenn Sie ausdrücke oder Sprachen unterstützen müssen, die für Ihre Organisation und Richtlinien spezifisch sind.

### <a name="classifiers"></a>Klassifizierungen

Integrierte trainierbare und globale Klassifizierer überprüfen gesendete oder empfangene Nachrichten über alle Kommunikationskanäle in Ihrer Organisation auf verschiedene Arten von Complianceproblemen. Klassifizierer verwenden eine Kombination aus künstlicher Intelligenz und Schlüsselwörtern, um Sprache in Botschaften zu identifizieren, die wahrscheinlich gegen die Antibelästigungsrichtlinien verstoßen. Integrierte Klassifizierer unterstützen derzeit die Nachrichtenschlüsselwortidentifikation in mehreren Sprachen:

- Chinesisch (vereinfacht)
- Englisch
- Französisch
- Deutsch
- Italienisch
- Japanisch
- Portugiesisch
- Spanisch

Integrierte trainierbare und globale Klassifizierer überprüfen die Kommunikation nach Begriffen, Bildern und Gefühlen für die folgenden Arten von Sprache und Inhalten:

- **Bedrohung:** Sucht nach Bedrohungen, um Gewalt oder physischen Schaden an einer Person oder einem Eigentum zu begehen.
- **Gezielte Belästigung:** Sucht nach anstößigem Verhalten, das auf Personen in Bezug auf Rasen, Farbe, Herkunft, nationale Herkunft ausgerichtet ist.
- **Profanität:** Sucht nach profanen Ausdrücken, die die meisten Menschen verungifizieren.
- **Bilder für Erwachsene:** Sucht nach Bildern, die sexueller Art sind.
- **Rassige Bilder:** Sucht nach Bildern, die sexuelle Suggestivität aufweisen, aber weniger explizite Inhalte enthalten als Bilder, die als nicht jugendfrei eingestuft werden.
- **Graue Bilder:** Sucht nach Bildern, die Gewalt und Grauen darstellen.

Die Bildklassifizierungen *"Adult",* *"Racy"* und *"Gory"* scannen Dateien im JPEG-, .png-, .gif- und .bmp-Format. Die Größe für Bilddateien muss kleiner als 4 MB sein, und die Abmessungen der Bilder müssen größer als 50 x 50 Pixel und größer als 50 KB sein, damit das Bild für die Auswertung qualifiziert ist. Die Bildidentifikation wird für Exchange Online E-Mail-Nachrichten und Microsoft Teams Kanäle und Chats unterstützt.

Die integrierten trainierbaren und globalen Klassifizierer bieten keine vollständige Liste der Begriffe oder Bilder in diesen Bereichen. Darüber hinaus ändern sich die Sprach- und Kulturstandards ständig, und angesichts dieser Umstände behält sich Microsoft das Recht vor, Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während Klassifizierer Ihre Organisation bei der Überwachung dieser Bereiche unterstützen können, sind Klassifizierer nicht dafür vorgesehen, die einzigen Mittel Ihrer Organisation zur Überwachung oder Behandlung dieser Sprache oder Bilder bereitzustellen. Ihre Organisation, nicht Microsoft, bleibt für alle Entscheidungen im Zusammenhang mit der Überwachung, Überprüfung und Sperrung von Sprache und Bildern in diesen Bereichen verantwortlich, einschließlich der Einhaltung des lokalen Datenschutzes und anderer anwendbarer Gesetze. Microsoft empfiehlt die Beratung von Rechtsberatern vor der Bereitstellung und Verwendung.

> [!NOTE]
> Richtlinien, die Klassifizierer verwenden, überprüfen und bewerten Nachrichten mit einer Wortanzahl von mindestens sechs. Nachrichten mit weniger als sechs Wörtern werden in Richtlinien nicht mithilfe von Klassifizierern ausgewertet. Um kürzere Nachrichten zu identifizieren und Maßnahmen zu ergreifen, die unangemessene Inhalte enthalten, empfehlen wir, ein benutzerdefiniertes Schlüsselwortverzeichnis in die Überwachung der Kommunikationscompliancerichtlinien für diese Art von Inhalten aufzunehmen.

Informationen zu trainierbaren Klassifizierern in Microsoft 365 finden Sie unter [Erste Schritte mit trainierbaren Klassifizierern.](classifier-get-started-with.md)

### <a name="optical-character-recognition-ocr"></a>Optical Character Recognition (OCR; optische Zeichenerkennung)

Konfigurieren Sie integrierte oder benutzerdefinierte Richtlinien für die Kommunikationscompliance, um gedruckten oder handschriftlichen Text aus Bildern zu scannen und zu identifizieren, die in Ihrer Organisation möglicherweise unangemessen sind. Integrierte [Azure Cognitive Services und optische Scanunterstützung](/azure/cognitive-services/computer-vision/overview-ocr) zum Identifizieren von Text in Bildern helfen Analysten und Ermittlern dabei, Fälle zu erkennen und zu bearbeiten, in denen unangemessenes Verhalten in Kommunikationen, die in erster Linie nicht textbezogen sind, übersehen wird.

Sie können die optische Zeichenerkennung (OCR) in neuen Richtlinien aus Vorlagen, benutzerdefinierten Richtlinien aktivieren oder vorhandene Richtlinien aktualisieren, um die Unterstützung für die Verarbeitung eingebetteter Bilder und Anlagen zu erweitern. Wenn dies in einer Richtlinie aktiviert ist, die anhand einer Richtlinienvorlage erstellt wurde, wird die automatische Überprüfung für eingebettete oder angefügte Bilder in E-Mails und Microsoft Teams Chatnachrichten unterstützt. Für benutzerdefinierte Richtlinien müssen eine oder mehrere bedingte Einstellungen, die Schlüsselwörtern, integrierten Klassifizierungen oder Typen vertraulicher Informationen zugeordnet sind, in der Richtlinie konfiguriert werden, um die Auswahl der OCR-Überprüfung zu ermöglichen.

Bilder von 50 KB bis 4 MB in den folgenden Bildformaten werden gescannt und verarbeitet:

- .jpg/.jpeg (gemeinsame Gruppe von Experten)
- .png (portable Netzwerkgrafiken)
- .bmp (Bitmap)
- TIFF (Tagbilddateiformat)
- .pdf (portierbares Dokumentformat)

> [!NOTE]
> Das Scannen und Extrahieren eingebetteter und angefügter .pdf Bilder wird derzeit nur für E-Mail-Nachrichten unterstützt.

Bei der Überprüfung ausstehender Warnungen für Richtlinien mit aktivierter OCR werden Bilder, die mit Richtlinienbedingungen übereinstimmen, als untergeordnete Elemente für zugeordnete Warnungen angezeigt. Sie können das Originalbild anzeigen, um den identifizierten Text im Kontext der ursprünglichen Nachricht auszuwerten. Es kann bis zu 48 Stunden dauern, bis erkannte Bilder mit Warnungen verfügbar sind.

### <a name="conditional-settings"></a>Bedingte Einstellungen
<a name="ConditionalSettings"> </a>

Die Bedingungen, die Sie für die Richtlinie auswählen, gelten für Kommunikationen aus E-Mail- und Drittanbieterquellen in Ihrer Organisation (z. B. von Instant Bloomberg).

In der folgenden Tabelle werden weitere Informationen zu den einzelnen Bedingungen erläutert.

|**Bedingung**|**Verwendung**|
|:-----|:-----|
| **Inhalt entspricht einer dieser Klassifizierer** | Wenden Sie die Richtlinie an, wenn Klassifizierungen in einer Nachricht enthalten oder ausgeschlossen werden. Einige Klassifizierer sind in Ihrem Mandanten vordefiniert, und benutzerdefinierte Klassifizierer müssen separat konfiguriert werden, bevor sie für diese Bedingung verfügbar sind. Es kann nur ein Klassifizierer als Bedingung in einer Richtlinie definiert werden. Weitere Informationen zum Konfigurieren von Klassifizierern finden Sie unter [Informationen zu trainierbaren Klassifizierern (Vorschau).](classifier-learn-about.md) |
| **Inhalt enthält einen dieser vertraulichen Informationstypen** | Wenden Sie die Richtlinie an, wenn vertrauliche Informationstypen in eine Nachricht eingeschlossen oder ausgeschlossen werden. Einige Klassifizierer sind in Ihrem Mandanten vordefiniert, und benutzerdefinierte Klassifizierer können separat oder als Teil des Bedingungszuweisungsprozesses konfiguriert werden. Jeder typ vertraulicher Informationen, den Sie auswählen, wird separat angewendet, und nur einer dieser Typen vertraulicher Informationen muss gelten, damit die Richtlinie auf die Nachricht angewendet wird. Weitere Informationen zu benutzerdefinierten Typen vertraulicher Informationen finden Sie unter [Informationen zu Typen vertraulicher Informationen.](sensitive-information-type-learn-about.md) |
| **Nachricht wird von einer dieser Domänen empfangen**  <br><br> **Nachricht wird von keiner dieser Domänen empfangen** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder E-Mail-Adressen in empfangene Nachrichten einzu- oder auszuschließen. Geben Sie jede Domäne oder E-Mail-Adresse ein, und trennen Sie mehrere Domänen oder E-Mail-Adressen durch ein Komma. Jede eingegebene Domäne oder E-Mail-Adresse wird separat angewendet, es muss nur eine Domäne oder E-Mail-Adresse gelten, damit die Richtlinie auf die Nachricht angewendet wird. <br><br> Wenn Sie alle E-Mails aus einer bestimmten Domäne überprüfen möchten, aber Nachrichten ausschließen möchten, die keine Überprüfung erfordern (Newsletter, Ankündigungen usw.), müssen Sie konfigurieren, dass eine Nachricht nicht von einer dieser Domänen empfangen **wird,** die die E-Mail-Adresse ausschließt (beispiel: "newsletter@contoso.com"). |
| **Nachricht wird an eine dieser Domänen gesendet**  <br><br> **Nachricht wird nicht an eine dieser Domänen gesendet** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder E-Mail-Adressen in gesendete Nachrichten einzu- oder auszuschließen. Geben Sie jede Domäne oder E-Mail-Adresse ein, und trennen Sie mehrere Domänen oder E-Mail-Adressen durch ein Komma. Jede Domäne oder E-Mail-Adresse wird separat angewendet, es muss nur eine Domäne oder E-Mail-Adresse gelten, damit die Richtlinie auf die Nachricht angewendet wird. <br><br> Wenn Sie alle an eine bestimmte Domäne gesendeten E-Mails überprüfen, gesendete Nachrichten jedoch ausschließen möchten, die keine Überprüfung erfordern, müssen Sie zwei Bedingungen konfigurieren: <br> – Eine **Nachricht wird an eine dieser Domänen** gesendet, die die Domäne ("contoso.com"), UND <br> - Eine **Nachricht wird nicht an eine dieser Domänen gesendet,** die die E-Mail-Adresse ("subscriptions@contoso.com") ausschließt. |
| **Nachricht wird mit einer dieser Bezeichnungen klassifiziert**  <br><br> **Nachricht ist nicht mit einer dieser Bezeichnungen klassifiziert** | So wenden Sie die Richtlinie an, wenn bestimmte Aufbewahrungsbezeichnungen in einer Nachricht enthalten oder ausgeschlossen werden. Aufbewahrungsbezeichnungen müssen separat konfiguriert werden, und konfigurierte Bezeichnungen werden als Teil dieser Bedingung ausgewählt. Jede bezeichnung, die Sie auswählen, wird separat angewendet (nur eine dieser Bezeichnungen muss gelten, damit die Richtlinie auf die Nachricht angewendet wird). Weitere Informationen zu Aufbewahrungsbezeichnungen finden Sie unter [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)|
| **Nachricht enthält eines dieser Wörter**  <br><br> **Nachricht enthält keines dieser Wörter** | Um die Richtlinie anzuwenden, wenn bestimmte Wörter oder Ausdrücke in eine Nachricht eingeschlossen oder ausgeschlossen werden, geben Sie jedes Wort getrennt durch ein Komma ein. Verwenden Sie für Ausdrücke mit zwei oder mehr Wörtern Anführungszeichen um den Ausdruck. Jedes eingegebene Wort oder jeder Ausdruck wird separat angewendet (es muss nur ein Wort gelten, damit die Richtlinie auf die Nachricht angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Anlage enthält eines dieser Wörter**  <br><br> **Anlage enthält keines dieser Wörter** | Um die Richtlinie anzuwenden, wenn bestimmte Wörter oder Ausdrücke in eine Nachrichtenanlage (z. B. ein Word-Dokument) eingeschlossen oder ausgeschlossen werden, geben Sie jedes Wort durch ein Komma getrennt ein. Verwenden Sie für Ausdrücke mit zwei oder mehr Wörtern Anführungszeichen um den Ausdruck. Jedes eingegebene Wort oder jeder Ausdruck wird separat angewendet (es muss nur ein Wort gelten, damit die Richtlinie auf die Anlage angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment ist einer dieser Dateitypen**  <br><br> **Anlage ist keiner dieser Dateitypen** | Um Kommunikationen zu überwachen, die bestimmte Anlagentypen enthalten oder ausschließen, geben Sie die Dateierweiterungen ein (z. B. .exe oder .pdf). Wenn Sie mehrere Dateierweiterungen einschließen oder ausschließen möchten, geben Sie diese in separaten Zeilen ein. Damit die Richtlinie angewendet werden kann, muss nur eine Anlagenerweiterung übereinstimmen.|
| **Nachricht ist größer als**  <br><br> **Nachrichtengröße ist nicht größer als** | Um Nachrichten basierend auf einer bestimmten Größe zu überprüfen, verwenden Sie diese Bedingungen, um die maximale oder minimale Größe einer Nachricht anzugeben, bevor sie überprüft werden kann. Wenn Sie beispielsweise angeben, dass die **Nachrichtengröße größer als** \> **1,0 MB** ist, können alle Nachrichten, die 1,01 MB und größer sind, überprüft werden. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
| **Anlage ist größer als**  <br><br> **Anlage ist nicht größer als** | Um Nachrichten basierend auf der Größe ihrer Anlagen zu überprüfen, geben Sie die maximale oder minimale Größe einer Anlage an, bevor die Nachricht und ihre Anlagen überprüft werden können. Wenn Sie z. B. angeben, dass **"Anlage" größer als** \> **2,0 MB** ist, können alle Nachrichten mit Anlagen ab einer Größe von 2,01 MB überprüft werden. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|

#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Übereinstimmende Wörter und Ausdrücke in E-Mails oder Anlagen
<a name="Matchwords"> </a>

Jedes eingegebene und durch Komma getrennte Wort wird separat angewendet (es muss nur ein Wort gelten, damit die Richtlinienbedingung auf die E-Mail oder Anlage angewendet wird). Verwenden wir beispielsweise die Bedingung: **"Nachricht" enthält eines dieser Wörter,** wobei die Schlüsselwörter "Banker", "vertraulich" und "Insider-Handel" durch ein Komma getrennt sind (Banker, vertraulich,"Insider-Handel"). Die Richtlinie gilt für alle Nachrichten, die das Wort "Banker", "vertraulich" oder den Ausdruck "Insider-Handel" enthalten. Nur eins der Wörter oder einer der Ausdrücke muss vorkommen, damit die Richtlinienbedingung zutrifft. Wörter in der Nachricht oder Anlage müssen genau mit der Eingabe übereinstimmen.

> [!IMPORTANT]
>
> Beim Importieren einer Benutzerwörterbuchdatei muss jedes Wort oder jeder Ausdruck mit einem Wagenrücklauf und in einer separaten Zeile getrennt werden. Beispiel:
>
> *Banker* <br>
> *Vertraulich* <br>
> *Insiderhandel*

Um sowohl E-Mail-Nachrichten als auch Anlagen auf dieselben Schlüsselwörter zu überprüfen, erstellen Sie eine [Richtlinie zur Verhinderung von Datenverlust](create-test-tune-dlp-policy.md) mit einem [benutzerdefinierten Schlüsselwortverzeichnis](create-a-keyword-dictionary.md) für die Ausdrücke, die Sie in Nachrichten überprüfen möchten. Diese Richtlinienkonfiguration identifiziert definierte Schlüsselwörter, die entweder in der E-Mail-Nachricht **oder** in der E-Mail-Anlage angezeigt werden. Die Verwendung der standardmäßigen Einstellungen für bedingte Richtlinien (*Nachricht enthält eines dieser Wörter* und Anlage enthält eines dieser Wörter ) zum Identifizieren *von* Begriffen in Nachrichten und in Anlagen erfordert, dass die Begriffe sowohl in der Nachricht **als auch** in der Anlage vorhanden sind.

#### <a name="enter-multiple-conditions"></a>Mehrere Bedingungen eingeben

Wenn Sie mehrere Bedingungen eingeben, verwendet Microsoft 365 alle Bedingungen zusammen, um zu bestimmen, wann die Richtlinie zur Kommunikationscompliance auf Kommunikationselemente angewendet werden soll. Wenn Sie mehrere Bedingungen einrichten, müssen alle Bedingungen erfüllt sein, damit die Richtlinie angewendet werden kann, es sei denn, Sie geben eine Ausnahme ein. Sie benötigen beispielsweise eine Richtlinie, die gilt, wenn eine Nachricht das Wort "Trade" enthält und größer als 2 MB ist. Wenn die Nachricht jedoch auch die Wörter "Genehmigt von Contoso financial" enthält, sollte die Richtlinie nicht angewendet werden. In diesem Beispiel würden die drei Bedingungen wie folgt definiert:

- **Message contains any of these words**, with the keyword "trade"
- **Nachrichtengröße ist größer als**, mit dem Wert 2 MB
- **Nachricht enthält keines dieser Wörter** mit den Schlüsselwörtern "Genehmigt von Contoso-Finanzteam"

### <a name="review-percentage"></a>Prozentsatz der Überprüfung

Wenn Sie die Menge der zu überprüfenden Inhalte reduzieren möchten, können Sie einen Prozentsatz aller Kommunikationen angeben, die durch eine Richtlinie zur Kommunikationscompliance geregelt sind. Eine zufällige Stichprobe von Inhalten wird in Echtzeit aus dem Gesamtprozentsatz der Inhalte ausgewählt, die den gewählten Richtlinienbedingungen entsprechen. Wenn Sie möchten, dass Prüfer alle Elemente prüfen, können Sie in einer Richtlinie zur Kommunikationscompliance **100 %** konfigurieren.

## <a name="privacy"></a>Datenschutz

Der Schutz des Datenschutzes von Benutzern, die Richtlinienüberstimmungen haben, ist wichtig und kann dazu beitragen, die Objektivität bei der Untersuchung und Analyse von Daten für Warnungen zur Kommunikationscompliance zu fördern. Diese Einstellung gilt nur für Benutzernamen, die in der Kommunikationscompliancelösung angezeigt werden. Es hat keinen Einfluss darauf, wie Namen in anderen Compliancelösungen oder im Admin Center angezeigt werden.

Für Benutzer mit einer Übereinstimmung mit der Kommunikationscompliance können Sie eine der folgenden Einstellungen in den **Kommunikationscomplianceeinstellungen** auswählen:

- **Anonymisierte Versionen von Benutzernamen** anzeigen: Benutzernamen werden anonymisiert, um zu verhindern, dass Benutzer in der Rollengruppe *"Kommunikationscomplianceanalyst"* sehen, wer Richtlinienwarnungen zugeordnet ist. Benutzern in der Rollengruppe *"Kommunikationscompliance-Ermittler"* werden immer Benutzernamen angezeigt, nicht die anonymisierten Versionen. Beispielsweise würde ein Benutzer "Grace Wieder" mit einem zufälligen Pseudonym wie "AnonIS8-988" in allen Bereichen der Kommunikationscompliance angezeigt. Wenn Sie diese Einstellung wählen, werden alle Benutzer mit aktuellen und früheren Richtlinienübereinstimmungen anonymisiert und gelten für alle Richtlinien. Benutzerprofilinformationen in den Kommunikationscompliance-Warnungsdetails sind nicht verfügbar, wenn diese Option ausgewählt wird. Benutzernamen werden jedoch beim Hinzufügen neuer Benutzer zu vorhandenen Richtlinien oder beim Zuweisen von Benutzern zu neuen Richtlinien angezeigt. Wenn Sie diese Einstellung deaktivieren, werden Benutzernamen für alle Benutzer angezeigt, die aktuelle oder frühere Richtlinienüberstimmungen haben.
- **Anonymisierte Versionen von Benutzernamen nicht anzeigen:** Benutzernamen werden für alle aktuellen und früheren Richtlinienüberstimmungen für Warnungen zur Kommunikationscompliance angezeigt. Benutzerprofilinformationen (Name, Titel, Alias und Organisation oder Abteilung) werden für den Benutzer für alle Kommunikationscompliancewarnungen angezeigt.

## <a name="notice-templates"></a>Benachrichtigungsvorlagen

Sie können Benachrichtigungsvorlagen erstellen, wenn Sie Benutzern im Rahmen des Problemlösungsprozesses eine E-Mail-Erinnerung für Richtlinienüberstimmungen senden möchten. Benachrichtigungen können nur an die E-Mail-Adresse des Benutzers gesendet werden, die der Richtlinienüberstimmung zugeordnet ist, die die spezifische Warnung zur Behebung generiert hat. Wenn Sie eine Benachrichtigungsvorlage auswählen, die im Rahmen des Korrekturworkflows auf einen Richtlinienverstoß angewendet werden soll, können Sie die in der Vorlage definierten Feldwerte akzeptieren oder die Felder nach Bedarf überschreiben.

Hinweisvorlagen sind benutzerdefinierte E-Mail-Vorlagen, in denen Sie die folgenden Nachrichtenfelder im Bereich **"Kommunikationscomplianceeinstellungen"** definieren können:

|**Feld**|**Required**| **Details** |
|:-----|:-----|:-----|
|**Vorlagenname** | Ja | Der Anzeigename für die Benachrichtigungsvorlage, die Sie während der Wartung im Benachrichtigungsworkflow auswählen werden, unterstützt Textzeichen. |
| **Absenderadresse** | Ja | Die Adresse eines oder mehrerer Benutzer oder Gruppen, die die Nachricht mit einer Richtlinienüberstimmung an den Benutzer senden, ausgewählt aus dem Active Directory für Ihr Abonnement. |
| **CC- und BCC-Adressen** | Nein | Optionale Benutzer oder Gruppen, die über die Richtlinienüberstimmung benachrichtigt werden sollen, ausgewählt aus dem Active Directory für Ihr Abonnement. |
| **Betreff** | Ja | Informationen, die in der Betreffzeile der Nachricht angezeigt werden, unterstützen Textzeichen. |
| **Nachrichtentext** | Ja | Informationen, die im Nachrichtentext angezeigt werden, unterstützen Text- oder HTML-Werte. |

### <a name="html-for-notices"></a>HTML für Hinweise

Wenn Sie mehr als eine einfache textbasierte E-Mail-Nachricht für Benachrichtigungen erstellen möchten, können Sie eine detailliertere Nachricht mithilfe von HTML im Nachrichtentextfeld einer Benachrichtigungsvorlage erstellen. Im folgenden Beispiel wird das Nachrichtentextformat für eine einfache HTML-basierte E-Mail-Benachrichtigungsvorlage bereitgestellt:

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

> [!NOTE]
> Die Implementierung des HTML-Href-Attributs in den Kommunikationscompliance-Benachrichtigungsvorlagen unterstützt derzeit nur einfache Anführungszeichen anstelle doppelter Anführungszeichen für URL-Verweise.

## <a name="filters"></a>Filter

Kommunikationscompliancefilter ermöglichen es Ihnen, Warnmeldungen zu filtern und zu sortieren, um schnellere Untersuchungs- und Korrekturaktionen zu ermöglichen. Die Filterung ist auf den Registerkarten **"Ausstehend"** und **"Aufgelöst"** für jede Richtlinie verfügbar. Um einen Filter oder einen Filtersatz als gespeicherte Filterabfrage zu speichern, müssen mindestens ein Wert als Filterauswahl konfiguriert werden. In der folgenden Tabelle werden Filterdetails beschrieben:

|**Filter**|**Details**|
|:-----|:-----|
| **Date** | Das Datum, an dem die Nachricht von einem Benutzer in Ihrer Organisation gesendet oder empfangen wurde. Um nach einem einzelnen Tag zu filtern, wählen Sie einen Datumsbereich aus, der mit dem Tag beginnt, für den Ergebnisse erzielt werden sollen, und mit dem folgenden Tag enden. Wenn Sie z. B. Ergebnisse nach dem 20.09.2020 filtern möchten, wählen Sie einen Filterdatumsbereich vom 20.09.2020 bis 21.09.2020 aus.|
| **Dateiklasse** | Die Klasse der Nachricht basierend auf dem Nachrichtentyp, entweder *Nachricht* oder *Anlage.* |
| **Hat Anlage** | Die Anlagenanwesenheit in der Nachricht. |
| **Elementklasse** | Die Quelle der Nachricht basierend auf dem Nachrichtentyp, der E-Mail, dem Microsoft Team-Chat, Bloomberg usw. Weitere Informationen zu allgemeinen Elementtypen und Nachrichtenklassen finden Sie unter [Elementtypen und Nachrichtenklassen.](/office/vba/outlook/concepts/forms/item-types-and-message-classes) |
| **Empfängerdomänen** | Die Domäne, an die die Nachricht gesendet wurde. Diese Domäne ist normalerweise Standardmäßig Ihre Microsoft 365 Abonnementdomäne. |
| **Empfänger** | Der Benutzer, an den die Nachricht gesendet wurde. |
| **Sender** | Die Person, die die Nachricht gesendet hat. |
| **Absenderdomäne** | Die Domäne, die die Nachricht gesendet hat. |
| **Size** | Die Größe der Nachricht in KB. |
| **Betreff/Titel** | Der Nachrichtenbetreff oder Chattitel. |
| **Tags** | Die einer Nachricht zugewiesenen Tags, entweder *"Questionable",* *"Compliant"* oder *"Non-compliant".* |
| **Sprache** | Die erkannte Sprache des Texts in der Nachricht. Die Nachricht wird gemäß der Sprache des Großteils des Nachrichtentexts klassifiziert. Für eine Nachricht, die sowohl deutschen als auch einen deutschen Text enthält, der Großteil des Texts jedoch Deutsch ist, wird die Nachricht als Deutsch (DE) klassifiziert. Die folgenden Sprachen werden unterstützt: Chinesisch (vereinfacht - ZH), Englisch (EN), Französisch (FR), Deutsch (DE), Italienisch (IT), Japanisch (JP), Portugiesisch (PT) und Spanisch (ES). Wenn Sie beispielsweise Nachrichten filtern möchten, die als Deutsch und Italienisch klassifiziert wurden, geben Sie "DE,IT" (die zweistelligen Sprachcodes) in das Suchfeld "Sprachfilter" ein. Um die erkannte Sprachklassifizierung für eine Nachricht anzuzeigen, wählen Sie eine Nachricht aus, wählen Sie Nachrichtendetails anzeigen aus, und scrollen Sie zum Feld EmailDetectedLanguage. |
| **Eskaliert an** | Der Benutzername der Person, die im Rahmen einer Nachrichteneskalationsaktion enthalten ist. |
| **Klassifizierungen** | Der Name der integrierten und benutzerdefinierten Klassifizierer, die für die Nachricht gelten. Einige Beispiele sind *Anstößige Sprache,* *gezielte Belästigung,* *Anstößigkeit,* *Bedrohung* und vieles mehr.

## <a name="alert-policies"></a>Warnungsrichtlinien

Nachdem Sie eine Richtlinie konfiguriert haben, wird automatisch eine entsprechende Warnungsrichtlinie erstellt und Warnungen für Nachrichten generiert, die den in der Richtlinie definierten Bedingungen entsprechen. Standardmäßig wird allen Richtlinienübereinstimmungs-Warnungsauslösern in der zugeordneten Warnungsrichtlinie der Schweregrad "Mittel" zugewiesen. Warnungen werden für eine Richtlinie zur Kommunikationscompliance generiert, sobald der Schwellenwert für den Aggregationsauslöser in der zugehörigen Warnungsrichtlinie erreicht ist.

Für Richtlinien zur Kommunikationscompliance sind die folgenden Warnungsrichtlinienwerte standardmäßig konfiguriert:

|**Warnungsrichtlinienauslöser**|**Standardwert**|
|:-----|:-----|
| Aggregation | Einfache Aggregation |
| Schwellenwert | 4 Aktivitäten |
| Fenster | 60 Minuten |

> [!NOTE]
> Die Schwellenwert-Triggereinstellungen für Warnungsrichtlinien für Aktivitäten unterstützen einen Mindestwert von 3 oder höher für Kommunikationscompliancerichtlinien.

Sie können die Standardeinstellungen für triggers on number of activities, period for the activities, and for specific users in alert policies on the **Alert policies** page in the Security & Compliance Center ändern.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Ändern des Schweregrads für eine Warnungsrichtlinie

Wenn Sie den Schweregrad ändern möchten, der in einer Warnungsrichtlinie für eine bestimmte Kommunikationscompliancerichtlinie zugewiesen ist, führen Sie die folgenden Schritte aus:

1. Melden Sie sich [https://compliance.microsoft.com](https://compliance.microsoft.com) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **"Richtlinien".**

3. Wählen Sie **Office 365 Warnung** auf der Seite **"Richtlinien"** aus, um die Seite **"Warnungsrichtlinien"** im **Office 365 Security & Compliance Center** zu öffnen.

4. Aktivieren Sie das Kontrollkästchen für die Richtlinie zur Kommunikationscompliance, die Sie aktualisieren möchten, und wählen Sie dann **Richtlinie bearbeiten** aus.

5. Wählen Sie auf der Registerkarte **"Beschreibung"** die Dropdownliste **"Schweregrad"** aus, um die Richtlinienwarnungsstufe zu konfigurieren.

6. Wählen Sie **"Speichern"** aus, um den neuen Schweregrad auf die Richtlinie anzuwenden.

7. Wählen Sie **"Schließen"** aus, um die Seite "Warnungsrichtliniendetails" zu beenden.

## <a name="power-automate-flows"></a>Power Automate Flüsse

[Microsoft Power Automate](/power-automate/getting-started) ist ein Workflowdienst, der Aktionen über Anwendungen und Dienste hinweg automatisiert. Durch die Verwendung von Flüssen aus Vorlagen oder manuell erstellte, können Sie allgemeine Aufgaben im Zusammenhang mit diesen Anwendungen und Diensten automatisieren. Wenn Sie Power Automate Flüsse für die Kommunikationscompliance aktivieren, können Sie wichtige Aufgaben für Warnungen und Benutzer automatisieren. Sie können Power Automate Flüsse so konfigurieren, dass Manager benachrichtigt werden, wenn Benutzer über Warnungen zur Kommunikationscompliance und andere Anwendungen verfügen.

Kunden mit Microsoft 365 Abonnements, die Kommunikationscompliance enthalten, benötigen keine zusätzlichen Power Automate Lizenzen, um die empfohlene Standard-Kommunikationscompliance Power Automate Vorlage zu verwenden. Die Standardvorlage kann angepasst werden, um Ihre Organisation zu unterstützen und die wichtigsten Kommunikationscomplianceszenarien abzudecken. Wenn Sie premium Power Automate Features in diesen Vorlagen verwenden, eine benutzerdefinierte Vorlage mit dem Microsoft 365 Compliance Connector erstellen oder Power Automate Vorlagen für andere Compliancebereiche in Microsoft 365 verwenden, benötigen Sie möglicherweise zusätzliche Power Automate Lizenzen.

> [!IMPORTANT]
> Erhalten Sie beim Testen Power Automate Flüsse Aufforderungen zur zusätzlichen Lizenzüberprüfung? Möglicherweise hat Ihre Organisation noch keine Dienstupdates für dieses Vorschaufeature erhalten. Updates werden bereitgestellt, und alle Organisationen mit Microsoft 365 Abonnements, die Kommunikationscompliance enthalten, sollten bis zum 30. Oktober 2020 Lizenzunterstützung für Flüsse haben, die aus den empfohlenen Power Automate Vorlagen erstellt wurden.

![Kommunikationscompliance Power Automate](../media/communication-compliance-power-automate.png)

Die folgende Power Automate Vorlage wird Kunden bereitgestellt, um die Prozessautomatisierung für Kommunikationscompliancewarnungen zu unterstützen:

- **Benachrichtigen Sie den Vorgesetzten, wenn ein Benutzer über eine Kommunikationscompliancewarnung verfügt:** Einige Organisationen müssen möglicherweise eine sofortige Verwaltungsbenachrichtigung erhalten, wenn ein Benutzer über eine Kommunikationscompliancewarnung verfügt. Wenn dieser Fluss konfiguriert und ausgewählt ist, wird dem Vorgesetzten für den Fallbenutzer eine E-Mail-Nachricht mit den folgenden Informationen zu allen Warnungen gesendet:
  - Anwendbare Richtlinie für die Warnung
  - Datum/Uhrzeit der Warnung
  - Schweregrad der Warnung

### <a name="create-a-power-automate-flow"></a>Erstellen eines Power Automate Flusses

Zum Erstellen eines Power Automate Flusses aus einer empfohlenen Standardvorlage verwenden Sie die Option **"Verwalten Power Automate Flüsse"** aus dem **Steuerelement "Automatisieren",** wenn Sie direkt in einer Warnung arbeiten. Um einen Power Automate Fluss mit **manage Power Automate flows** zu erstellen, müssen Sie Mitglied mindestens einer Gruppe von Kommunikationscompliance-Rollen sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate Fluss aus einer Standardvorlage zu erstellen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **"Kommunikationscompliancerichtlinien",** und wählen Sie die Richtlinie mit der Warnung aus,  >   die Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **"Ausstehend"** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen Sie im Warnungsaktionsmenü **Power Automate** aus.
4. Wählen Sie auf der **Seite Power Automate** eine Standardvorlage aus den **Kommunikationscompliancevorlagen** aus, die Ihnen auf der Seite möglicherweise gefällt.
5. Der Fluss listet die eingebetteten Verbindungen auf, die für den Fluss erforderlich sind, und zeigt an, ob die Verbindungsstatus verfügbar sind. Aktualisieren Sie bei Bedarf alle Verbindungen, die nicht als verfügbar angezeigt werden. Wählen Sie **Weiter**.
6. Standardmäßig sind die empfohlenen Flüsse mit der empfohlenen Kommunikationscompliance und Microsoft 365 Dienstdatenfeldern vorkonfiguriert, die zum Ausführen der zugewiesenen Aufgabe für den Fluss erforderlich sind. Passen Sie bei Bedarf die Flusskomponenten an, indem Sie das Steuerelement **"Erweiterte Optionen anzeigen"** verwenden und die verfügbaren Eigenschaften für die Flusskomponente konfigurieren.
7. Fügen Sie ggf. zusätzliche Schritte zum Fluss hinzu, indem Sie die Schaltfläche **"Neuer Schritt"** auswählen. In den meisten Fällen sollte diese Änderung für die empfohlenen Standardvorlagen nicht erforderlich sein.
8. Wählen Sie **"Entwurf speichern"** aus, um den Fluss später zur weiteren Konfiguration zu speichern, oder wählen Sie **"Speichern"** aus, um die Konfiguration für den Fluss abzuschließen.
9. Wählen Sie **"Schließen"** aus, um zur Power Automate Flussseite zurückzukehren. Die neue Vorlage wird als Fluss auf der Registerkarte **"Meine Flüsse"** aufgeführt und ist automatisch über das Power Automate-Steuerelement für den Benutzer verfügbar, der den Fluss beim Arbeiten mit Kommunikationscompliancewarnungen erstellt hat.

### <a name="share-a-power-automate-flow"></a>Freigeben eines Power Automate Flusses

Standardmäßig sind Power Automate von einem Benutzer erstellten Flüsse nur für diesen Benutzer verfügbar. Damit andere Kommunikationscompliance-Benutzer Zugriff auf einen Flow haben und diesen verwenden können, muss der Fluss vom Flowersteller gemeinsam genutzt werden. Um einen Fluss freizugeben,  verwenden Sie das Power Automate-Steuerelement, wenn Sie direkt in einer Warnung arbeiten.

Um einen Power Automate Fluss freizugeben, müssen Sie Mitglied mindestens einer Gruppe von Kommunikationscompliance-Rollen sein.
Führen Sie die folgenden Schritte aus, um einen Power Automate Fluss freizugeben:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **"Kommunikationscompliancerichtlinien",** und wählen Sie die Richtlinie mit der Warnung aus,  >   die Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **"Ausstehend"** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen Sie im Warnungsaktionsmenü **Power Automate** aus.
4. Wählen Sie auf der Seite **Power Automate Flüsse** die Registerkarte **Meine** Flüsse oder Teamflüsse aus. 
5. Wählen Sie den zu teilenden Fluss aus, und wählen Sie dann im Menü "Flussoptionen" die Option **"Freigeben"** aus.
6. Geben Sie auf der Seite "Flussfreigabe" den Namen des Benutzers oder der Gruppe ein, den Sie als Besitzer für den Fluss hinzufügen möchten.
7. Klicken Sie im Dialogfeld **"Verbindung verwendet"** auf **"OK",** um zu bestätigen, dass der hinzugefügte Benutzer oder die hinzugefügte Gruppe voll auf den Fluss zugreifen kann.

### <a name="edit-a-power-automate-flow"></a>Bearbeiten eines Power Automate Flusses

Wenn Sie einen Fluss bearbeiten müssen,  verwenden Sie das Power Automate-Steuerelement, wenn Sie direkt in einer Warnung arbeiten. Zum Bearbeiten eines Power Automate Flusses müssen Sie Mitglied mindestens einer Kommunikationscompliance-Rollengruppe sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate Fluss zu bearbeiten:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **"Kommunikationscompliancerichtlinien",** und wählen Sie die Richtlinie mit der Warnung aus,  >   die Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **"Ausstehend"** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen Sie im Warnungsaktionsmenü **Power Automate** aus.
4. Wählen Sie auf der **Seite Power Automate Flüsse** den zu bearbeitenden Fluss aus. Wählen Sie im Flusssteuerungsmenü die Option **"Bearbeiten"** aus.
5. Wählen Sie die **Auslassungszeichen**  >  **Einstellungen** aus, um eine Flusskomponenteneinstellung zu ändern, oder löschen Sie die **Auslassungszeichen,**  >   um eine Flusskomponente zu löschen.
6. Wählen Sie **"Speichern"** und dann **"Schließen"** aus, um die Bearbeitung des Flusses abzuschließen.

### <a name="delete-a-power-automate-flow"></a>Löschen eines Power Automate Flusses

Wenn Sie einen Fluss löschen müssen,  verwenden Sie das Power Automate-Steuerelement, wenn Sie direkt in einer Warnung arbeiten. Um einen Power Automate Ablauf zu löschen, müssen Sie Mitglied mindestens einer Kommunikationscompliance-Rollengruppe sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate Fluss zu löschen:

1. Wechseln Sie im Microsoft 365 Compliance Center zu **"Kommunikationscompliancerichtlinien",** und wählen Sie die Richtlinie mit der Warnung aus,  >   die Sie überprüfen möchten.
2. Wählen Sie in der Richtlinie die Registerkarte **"Ausstehend"** aus, und wählen Sie eine ausstehende Warnung aus.
3. Wählen Sie im Warnungsaktionsmenü **Power Automate** aus.
4. Wählen Sie auf der **Seite Power Automate Flüsse** den zu löschenden Fluss aus. Wählen Sie im Flusssteuerungsmenü die Option **"Löschen"** aus.
5. Wählen Sie im Dialogfeld zur Bestätigung des Löschvorgangs **"Löschen"** aus, um den Fluss zu entfernen, oder wählen Sie **"Abbrechen"** aus, um die Löschaktion zu beenden.

## <a name="reports"></a>Berichte

Das neue **Dashboard "Berichte"** ist der zentrale Ort zum Anzeigen aller Kommunikationscomplianceberichte. Berichts-Widgets bieten eine schnelle Übersicht über Einblicke, die am häufigsten für eine allgemeine Bewertung des Status von Kommunikationscomplianceaktivitäten benötigt werden. Informationen, die in den Berichts-Widgets enthalten sind, können nicht exportiert werden. Detaillierte Berichte enthalten ausführliche Informationen zu bestimmten Kommunikationscompliancebereichen und bieten die Möglichkeit, Informationen während der Überprüfung zu filtern, zu gruppieren, zu sortieren und zu exportieren.

![Dashboard für Kommunikationscomplianceberichte](../media/communication-compliance-reports-dashboard.png)

Das **Dashboard "Berichte"** enthält die folgenden Berichts-Widgets und detaillierten Berichtslinks:

- **Aktuelle Richtlinie gleicht** Widget ab: Zeigt die Anzahl der Übereinstimmungen nach aktiver Richtlinie im Laufe der Zeit an.
- **Behobene Elemente nach** Richtlinien-Widget: Zeigt die Anzahl der Richtlinienübereinstimmungswarnungen an, die von der Richtlinie im Laufe der Zeit aufgelöst wurden.
- **Benutzer mit den meisten Richtlinienübersprechungs-Widgets:** Zeigt die Benutzer (oder anonymisierten Benutzernamen) und die Anzahl der Richtlinienübersprechungen für einen bestimmten Zeitraum an.
- **Richtlinie mit den meisten Übereinstimmungen:** Zeigt die Richtlinien und die Anzahl der Übereinstimmungen für einen bestimmten Zeitraum an, die bei Übereinstimmungen am höchsten bis niedrigsten eingestuft werden.
- **Eskalationen nach** Richtlinien-Widget: Zeigt die Anzahl der Eskalationen pro Richtlinie über einen bestimmten Zeitraum an.
- **Richtlinieneinstellungen und detaillierter Statusbericht:** Bietet einen detaillierten Überblick über die Richtlinienkonfiguration und -einstellungen sowie den allgemeinen Status für jede Richtlinie (Übereinstimmungen und Aktionen) für Nachrichten. Enthält Richtlinieninformationen und wie Richtlinien Benutzern und Gruppen, Speicherorten, Prüfprozentsätzen, Prüfern, Status und dem Zeitpunkt der letzten Änderung der Richtlinie zugeordnet werden. Verwenden Sie die *Exportoption,* um eine .csv Datei mit den Berichtsdetails zu erstellen.
- **Elemente und Aktionen pro detailliertem Bericht:** Überprüfen und Exportieren übereinstimmender Elemente und Korrekturaktionen pro Richtlinie. Enthält Richtlinieninformationen und die Art und Weise, wie Richtlinien verknüpft sind:

    - Übereinstimmende Elemente
    - Eskalierte Elemente
    - Aufgelöste Elemente
    - Als kompatibel markiert
    - Als nicht konform markiert
    - Als fragebar markiert
    - Ausstehende Überprüfung von Elementen
    - Benutzer benachrichtigt
    - Fall erstellt

    Verwenden Sie die *Exportoption,* um eine .csv Datei mit den Berichtsdetails zu erstellen.
- **Element und Aktionen pro detailliertem Standortbericht:** Überprüfen und Exportieren übereinstimmender Elemente und Korrekturaktionen pro Microsoft 365 Speicherort. Enthält Informationen dazu, wie Workloadplattformen verknüpft sind:

    - Übereinstimmende Elemente
    - Eskalierte Elemente
    - Aufgelöste Elemente
    - Als kompatibel markiert
    - Als nicht konform markiert
    - Als fragebar markiert
    - Ausstehende Überprüfung von Elementen
    - Benutzer benachrichtigt
    - Fall erstellt

    Verwenden Sie die *Exportoption,* um eine .csv Datei mit den Berichtsdetails zu erstellen.
- **Aktivität nach detailliertem Bericht des Benutzers:** Überprüfen und Exportieren übereinstimmender Elemente und Korrekturaktionen pro Benutzer. Enthält Informationen dazu, wie Benutzer zugeordnet sind:

    - Übereinstimmende Elemente
    - Eskalierte Elemente
    - Aufgelöste Elemente
    - Als kompatibel markiert
    - Als nicht konform markiert
    - Als fragebar markiert
    - Ausstehende Überprüfung von Elementen
    - Benutzer benachrichtigt
    - Fall erstellt

    Verwenden Sie die *Exportoption,* um eine .csv Datei mit den Berichtsdetails zu erstellen.

- **Typ vertraulicher Informationen pro detailliertem Standortbericht** (Vorschau): Überprüfen und exportieren Sie Informationen zur Erkennung vertraulicher Informationstypen und der zugehörigen Quellen in Kommunikationscompliancerichtlinien. Enthält die Gesamtsumme und die spezifische Aufschlüsselung von Instanzen vertraulicher Informationstypen in den in Ihrer Organisation konfigurierten Quellen. Beispiele:

    - **E-Mail:** Typen vertraulicher Informationen, die in Exchange E-Mail-Nachrichten erkannt werden.
    - **Teams:** Typen vertraulicher Informationen, die in Microsoft Teams Kanälen und Chatnachrichten erkannt werden.
    - **Skype for Business:** Typen vertraulicher Informationen, die in Skype für die Unternehmenskommunikation erkannt werden.
    - **Yammer:** Typen vertraulicher Informationen, die in Yammer Postfächern, Beiträgen, Chats und Antworten erkannt werden.
    - **Drittanbieterquellen:** Typen vertraulicher Informationen, die für Aktivitäten im Zusammenhang mit drittanbieterkonnektoren erkannt werden, die in Ihrer Organisation konfiguriert sind. Um die Aufschlüsselung von Drittanbieterquellen für einen bestimmten vertraulichen Informationstyp im Bericht anzuzeigen, zeigen Sie mit der Maus auf den Wert für den vertraulichen Informationstyp in der Spalte "Drittanbieterquelle".
    - **Andere:** Typen vertraulicher Informationen, die für die interne Systemverarbeitung verwendet werden. Das Auswählen oder Aufheben der Auswahl dieser Quelle für den Bericht wirkt sich nicht auf Werte aus.

    Verwenden Sie die *Exportoption,* um eine .csv Datei mit den Berichtsdetails zu erstellen. Die Werte für jede Drittanbieterquelle werden in separaten Spalten in der .csv Datei angezeigt.

## <a name="audit"></a>Überwachung

In einigen Fällen müssen Sie Informationen für regulatorische oder Compliance-Auditoren bereitstellen, um die Überwachung von Benutzeraktivitäten und Kommunikation nachzuweisen. Diese Informationen können eine Zusammenfassung aller Aktivitäten im Zusammenhang mit einer definierten Organisationsrichtlinie oder jederzeit eine Änderung einer Kommunikationscompliancerichtlinie sein. Richtlinien für die Kommunikationscompliance verfügen über integrierte Überwachungsprotokolle für die vollständige Bereitschaft für interne oder externe Audits. Detaillierte Überwachungsverläufe jeder Erstellungs-, Bearbeitungs- und Löschaktion werden von Ihren Kommunikationsrichtlinien erfasst, um Denknachweise für Aufsichtsverfahren bereitzustellen.

> [!IMPORTANT]
> Die Überwachung muss für Ihre Organisation aktiviert sein, bevor Kommunikationscomplianceereignisse aufgezeichnet werden. Informationen zum Aktivieren der Überwachung finden Sie unter [Aktivieren des Überwachungsprotokolls.](communication-compliance-configure.md#step-2-required-enable-the-audit-log) Wenn Aktivitäten Ereignisse auslösen, die im Microsoft 365 Überwachungsprotokoll erfasst werden, kann es bis zu 48 Stunden dauern, bis diese Ereignisse in Den Kommunikationscompliancerichtlinien angezeigt werden können.

Wählen Sie zum Anzeigen von Updateaktivitäten für Die Kommunikationscompliancerichtlinien auf der Hauptseite für eine beliebige Richtlinie das Steuerelement **"Richtlinienupdates exportieren"** aus. Ihnen müssen die Rollen *"Globaler Administrator"* oder *"Kommunikationscompliance-Administrator"* zugewiesen sein, um Updateaktivitäten zu exportieren. Diese Aktion generiert eine Überwachungsdatei im .csv Format, das die folgenden Informationen enthält:

|**Feld**|**Details**|
|:-----|:-----|
| **CreationDate** | Das Datum, an dem die Aktualisierungsaktivität in einer Richtlinie ausgeführt wurde. |
| **UserIds** | Der Benutzer, der die Aktualisierungsaktivität in einer Richtlinie ausgeführt hat. |
| **Operations** | Die Aktualisierungsvorgänge, die für die Richtlinie ausgeführt wurden. |
| **Auditdata** | Dieses Feld ist die Hauptdatenquelle für alle Richtlinienaktualisierungsaktivitäten. Alle Updateaktivitäten werden aufgezeichnet und durch Kommatrennzeichen getrennt. |

Um die Aktivitäten zur Überprüfung der Kommunikationscompliance für eine Richtlinie anzuzeigen, wählen Sie das Steuerelement **"Überprüfungsaktivitäten exportieren"** auf der Seite **"Übersicht"** für eine bestimmte Richtlinie aus. Ihnen müssen die Rollen *"Globaler Administrator"* oder *"Kommunikationscompliance-Administrator"* zugewiesen sein, um Überprüfungsaktivitäten zu exportieren. Diese Aktion generiert eine Überwachungsdatei im .csv Format, das die folgenden Informationen enthält:

|**Feld**|**Details**|
|:-----|:-----|
| **CreationDate** | Das Datum, an dem die Überprüfungsaktivität in einer Richtlinie ausgeführt wurde. |
| **UserIds** | Der Benutzer, der die Überprüfungsaktivität in einer Richtlinie ausgeführt hat. |
| **Operations** | Die für die Richtlinie ausgeführten Überprüfungsvorgänge. |
| **Auditdata** | Dieses Feld ist die Hauptdatenquelle für alle Richtlinienüberprüfungsaktivitäten. Alle Überprüfungsaktivitäten werden aufgezeichnet und durch Kommatrennzeichen getrennt. |

Sie können Überwachungsaktivitäten auch im einheitlichen Überwachungsprotokoll oder mit dem [PowerShell-Cmdlet "Search-UnifiedAuditLog"](/powershell/module/exchange/search-unifiedauditlog) anzeigen. Weitere Informationen zu Aufbewahrungsrichtlinien für Überwachungsprotokolle finden Sie unter Verwalten von Aufbewahrungsrichtlinien für [Überwachungsprotokolle.](audit-log-retention-policies.md)

Im folgenden Beispiel werden beispielsweise die Aktivitäten für alle Aufsichtsüberprüfungsaktivitäten (Richtlinien und Regeln) zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

In diesem Beispiel werden die Updateaktivitäten für Ihre Kommunikationscompliancerichtlinien zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

In diesem Beispiel werden Aktivitäten zurückgegeben, die Ihren aktuellen Kommunikationscompliancerichtlinien entsprechen:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch
```

Übereinstimmungen der Kommunikationscompliancerichtlinien werden für jede Richtlinie in einem Aufsichtspostfach gespeichert. In einigen Fällen müssen Sie möglicherweise die Größe Ihres Aufsichtspostfachs für eine Richtlinie überprüfen, um sicherzustellen, dass Sie sich nicht dem aktuellen Grenzwert von 50 GB nähern. Wenn das Postfachlimit erreicht ist, werden Richtlinienüberstimmungen nicht erfasst, und Sie müssen eine neue Richtlinie (mit denselben Einstellungen) erstellen, um weiterhin Übereinstimmungen für dieselben Aktivitäten zu erfassen.

Führen Sie die folgenden Schritte aus, um die Größe eines Aufsichtspostfachs für eine Richtlinie zu überprüfen:

1. Verwenden Sie das Cmdlet [Verbinden-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) im Exchange Online PowerShell V2-Modul, um mithilfe der modernen Authentifizierung eine Verbindung mit Exchange Online PowerShell herzustellen.
2. Führen Sie den folgenden Befehl in PowerShell aus:

    ```PowerShell
    ForEach ($p in Get-SupervisoryReviewPolicyV2 | Sort-Object Name)
    {
       "<Name of your communication compliance policy>: " + $p.Name
       Get-MailboxStatistics $p.ReviewMailbox | ft ItemCount,TotalItemSize
    }
    ```

## <a name="transitioning-from-supervision-in-office-365"></a>Übergang von der Aufsicht in Office 365

Organisationen, die Aufsichtsrichtlinien in Office 365 verwenden, sollten sofort planen, in Microsoft 365 auf Richtlinien zur Kommunikationscompliance umgestellt zu werden, und müssen die folgenden wichtigen Punkte verstehen:

- Die Aufsichtslösung in Office 365 wurde in Microsoft 365 vollständig durch die Lösung zur Kommunikationscompliance ersetzt. Es wird empfohlen, neue Richtlinien für die Kommunikationscompliance zu erstellen, die dieselben Einstellungen wie vorhandene Aufsichtsrichtlinien haben, um die neuen Verbesserungen bei Untersuchung und Behebung zu nutzen.
- Nachrichten, die in Office 365 Richtlinienüberlegungen unter Aufsicht gespeichert wurden, können in Microsoft 365 nicht verschoben oder in die Kommunikationscompliance freigegeben werden.
- Für Organisationen mit beiden Lösungen, die während des Übergangsprozesses nebeneinander verwendet werden, müssen die in jeder Lösung verwendeten Richtlinien eindeutige Richtliniennamen aufweisen. Gruppen und benutzerdefinierte Schlüsselwortwörterbücher können während einer Übergangszeit von Lösungen gemeinsam genutzt werden.

Ausführliche Informationen zur Einstellung der Aufsicht in Office 365 finden Sie in der [Microsoft 365 Roadmap.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="ready-to-get-started"></a>Sind Sie bereit loszulegen?

Informationen zum Konfigurieren der Kommunikationscompliance für Ihre Microsoft 365 Organisation finden Sie unter Konfigurieren der [Kommunikationscompliance für Ihre Microsoft 365 Organisation.](communication-compliance-configure.md)
