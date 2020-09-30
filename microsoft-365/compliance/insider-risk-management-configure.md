---
title: Erste Schritte mit dem Insider-Risikomanagement
description: Konfigurieren Sie das Insider Risikomanagement in Ihrer Organisation.
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f944933be4ce4d3a755ba54dd68856362bba9a0b
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304869"
---
# <a name="get-started-with-insider-risk-management"></a>Erste Schritte mit dem Insider-Risikomanagement

Verwenden Sie Richtlinien für Insider Risk Management, um riskante Aktivitäten und Verwaltungstools zu identifizieren, die auf Risikowarnungen in Ihrer Organisation reagieren. Führen Sie die folgenden Schritte aus, um Voraussetzungen einzurichten und eine Richtlinie für Insider-Risikomanagement zu konfigurieren.

>[!IMPORTANT]
>Die Microsoft 365 Insider Risk Management-Lösung bietet eine Mandantenebene, mit der Kunden die interne Steuerung auf Benutzerebene vereinfachen können. Administratoren auf Mandantenebene können Berechtigungen einrichten, um Zugriff auf diese Lösung für Mitglieder Ihrer Organisation bereitzustellen und Daten-Konnektoren im Microsoft 365 Compliance Center einzurichten, um relevante Daten zu importieren, um die Identifizierung potenziell riskanter Aktivitäten auf Benutzerebene zu unterstützen. Kunden bestätigen Einblicke in Bezug auf das Verhalten, den Charakter oder die Leistung der einzelnen Benutzer, die wesentlich im Zusammenhang mit der Beschäftigung stehen, können vom Administrator berechnet und anderen Benutzern in der Organisation zur Verfügung gestellt werden.

Weitere Informationen dazu, wie Sie mit Insider Risikorichtlinien Risiken in Ihrer Organisation verwalten können, finden Sie unter [Insider Risk Management in Microsoft 365](insider-risk-management.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie mit dem Insider Risk Management beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-ons bestätigen. Für den Zugriff auf und die Verwendung des Insider Risikomanagements muss Ihre Organisation über eines der folgenden Abonnements oder Add-ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5-Compliance-Add-on
- Microsoft 365 E3-Abonnement + Microsoft 365 E5 Insider Risk Management-Add-on
- Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 a3-Abonnement + das Microsoft 365 A5-Konformitäts-Add-on
- Microsoft 365 a3-Abonnement + Microsoft 365 A5 Insider Risk Management-Add-on

Benutzern, die in Richtlinien für das Insider Risikomanagement enthalten sind, muss eine der oben genannten Lizenzen zugewiesen sein.

Wenn Sie keinen vorhandenen Microsoft 365 Enterprise E5-Plan haben und das Insider Risk Management testen möchten, können Sie Microsoft 365 zu Ihrem vorhandenen Abonnement [Hinzufügen](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) oder [sich für eine Testversion](https://www.microsoft.com/microsoft-365/enterprise) von Microsoft 365 Enterprise E5 registrieren.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Schritt 1: Aktivieren von Berechtigungen für das Insider Risikomanagement

Es gibt vier Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Funktionen für das Insider Risikomanagement verwendet werden. Um diese Konfigurationsschritte fortzusetzen, müssen ihre mandantenadministratoren Sie zunächst der Administratorrollengruppe " **Insider Risk Management** **" oder "Insider Risk Management"** zuweisen. Für den Zugriff auf und die Verwaltung von Funktionen für das Insider-Risikomanagement nach der Erstkonfiguration müssen Benutzer Mitglied mindestens einer Rollengruppe für das Risikomanagement für Insider sein.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Wählen Sie unter diese Rollengruppen Optionen beim Konfigurieren des Insider Risikomanagements:

| **Rollengruppe** | **Rollenberechtigungen** |
| :---- | :---------------- |
| **Insider Risiko Management** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Wenn Sie alle Benutzerkonten für designierte Administratoren, Analytiker und Prüfer hinzufügen, können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für Insider-Risikomanagement. Diese Konfiguration ist die einfachste Möglichkeit, um schnell mit dem Insider Risiko-Management zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert werden.|
| **Insider Risk Management-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst das Insider Risikomanagement zu konfigurieren und später Insider Risiko Administratoren in eine definierte Gruppe zu unter trennen.  Benutzer in dieser Rollengruppe können Verwaltungsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen für Insiderrisiken erstellen, lesen, aktualisieren und löschen. |
| **Insider Risk Management Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken zugreifen. Sie könne nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen. |
| **Insider Risk Management Investigators** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen im Insider-Risikomanagement, auf Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |

> [!NOTE]
> Diese Rollengruppen werden zurzeit nicht für die Verwaltung von privilegierter Identität (PIM) unterstützt. Weitere Informationen zu PIM finden Sie unter [assign Azure AD Roles in Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Hinzufügen von Benutzern zu einer Rollengruppe "Insider Risk Management"

Führen Sie die folgenden Schritte aus, um Benutzer zu einer Rollengruppe "Insider Risk Management" hinzuzufügen:

1. Melden [https://protection.office.com/permissions](https://protection.office.com/permissions) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. &amp;Wechseln Sie im Security Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie die Rollengruppe "Insider Risk Management" aus, der Sie Benutzer hinzufügen möchten, und wählen Sie dann **Rollengruppe bearbeiten**aus.

4. Wählen Sie im linken Navigationsbereich **Elemente** auswählen aus, und wählen Sie dann **Bearbeiten**aus.

5. Wählen Sie **Hinzufügen** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen Sie **Speichern** aus, um die Benutzer der Rollengruppe hinzuzufügen. Wählen Sie **Schließen** aus, um die Schritte abzuschließen.

## <a name="step-2-enable-the-audit-log"></a>Schritt 2: Aktivieren des Überwachungsprotokolls

Das Insider-Risikomanagement verwendet Audit-Protokolle für Einblicke der Benutzer und Aktivitäten, die in Richtlinien konfiguriert sind. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die einer Richtlinie für Insider Risiken zugeordnet sind, oder wenn eine Richtlinie immer geändert wird.

Eine Schritt-für-Schritt-Anleitung zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](turn-audit-log-search-on-or-off.md). Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal ausführen. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-configure-prerequisites-for-templates"></a>Schritt 3: Konfigurieren der Voraussetzungen für Vorlagen

Die meisten Vorlagen für Insider Risikomanagement haben Voraussetzungen, die für Richtlinien Indikatoren konfiguriert werden müssen, um relevante Aktivitäts Warnungen zu generieren. Konfigurieren Sie die entsprechenden Voraussetzungen in Abhängigkeit von den Richtlinien, die Sie für Ihre Organisation konfigurieren möchten.

Wenn Sie eine Richtlinie mit der Vorlage *anstößige Sprache in e-Mail-* Richtlinie konfigurieren, können Sie diesen Schritt überspringen und direkt zu **Schritt 4**wechseln.

### <a name="configure-microsoft-365-hr-connector"></a>Konfigurieren des Microsoft 365 HR-Connectors

Das Insider Risk Management unterstützt das Importieren von Benutzer-und Protokolldaten, die von 3rd-Party-Risikomanagement-und Personalressourcen Plattformen importiert wurden. Mit dem Microsoft 365-Datenconnector für Human Resources (HR) können Sie Daten aus der Datenverarbeitung aus CSV-Dateien abrufen, einschließlich Benutzer Terminierungsdaten, Datum der letzten Arbeit, Benachrichtigungen zur Leistungsverbesserungsplan, Leistungs Überprüfungsaktionen und Änderungsstatus auf Auftragsebene. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen HF-Connector für Ihre Organisation konfigurieren, ruft das Insider Risikomanagement automatisch Indikatoren von allen HR-Connectors ab.

Der Microsoft 365 HR-Connector ist erforderlich, wenn die folgenden Richtlinienvorlagen verwendet werden:

- Abtrennen von Benutzerdaten Diebstahl
- Sicherheitsrichtlinienverletzungen durch Benutzer, die abgemeldet werden
- Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer
- Datenverluste durch verärgerte Benutzer

Lesen Sie den Artikel [Einrichten eines Connectors zum Importieren von HR-Daten](import-hr-data.md) , um Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten. Wenn Sie den HF-Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Konfigurieren von Richtlinien zur Verhinderung von Datenverlust (DLP)

Das Insider Risikomanagement unterstützt die Verwendung von DLP-Richtlinien, um die absichtliche oder versehentliche Exposition vertraulicher Informationen an unerwünschte Personen für DLP-Warnungen mit hohem Schweregrad zu identifizieren. Wenn Sie eine Richtlinie für das Insider Risikomanagement mit einer der **Datenlecks** -Vorlagen konfigurieren, müssen Sie der Richtlinie eine bestimmte DLP-Richtlinie zuweisen.

DLP-Richtlinien helfen Benutzern, die Risikobewertung im Insider-Risikomanagement für DLP-Warnungen mit hohem Schweregrad für vertrauliche Informationen zu aktivieren, und stellen einen wichtigen Bestandteil der vollständigen Risikomanagement Abdeckung in Ihrer Organisation dar. Weitere Informationen zu Insider Risikomanagement und DLP-Richtlinien Integration und Planungsüberlegungen finden Sie unter [Insider Risk Management Policies](insider-risk-management-policies.md#general-data-leaks).

>[!IMPORTANT]
>Stellen Sie sicher, dass Sie Folgendes abgeschlossen haben:
>
>- Sie verstehen und konfigurieren die in-Scope-Benutzer sowohl in den DLP-als auch im Insider Risk Management-Richtlinien, um die von Ihnen erwartete Richtlinien Abdeckung zu erstellen.
>- Stellen Sie sicher, dass die Einstellung **vorfallberichte** in der DLP-Richtlinie für das Insider Risikomanagement, die mit diesen Vorlagen verwendet wird, für Warnungen mit *hohem* Schweregrad konfiguriert ist. Warnungen beim Insider-Risikomanagement werden nicht aus DLP-Richtlinien generiert, wenn das Feld " **vorfallberichte** " auf *niedrig* oder *Mittel*festgelegt ist.

Eine DLP-Richtlinie ist erforderlich, wenn die folgenden Richtlinienvorlagen verwendet werden:

- Allgemeine Datenlecks
- Datenverluste nach Prioritäts Benutzern

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Artikels. Wenn Sie eine DLP-Richtlinie konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-priority-user-groups"></a>Konfigurieren von Prioritäts Benutzergruppen

Das Insider Risikomanagement umfasst die Unterstützung für die Zuweisung von Prioritäts Benutzergruppen zu Richtlinien, um die Identität eindeutiger Risiko Aktivitäten für Benutzer mit kritischen Positionen, hohen Datenmengen und Netzwerkzugriff oder einer vergangenen Geschichte des Risikoverhaltens zu unterstützen. Das Erstellen einer Priorität-Benutzergruppe und das Zuweisen von Benutzern zur Gruppe helfen Bereichs Richtlinien den von diesen Benutzern vorgestellten eindeutigen Umständen.

Bei Verwendung der folgenden Richtlinienvorlagen ist eine Prioritäts Benutzergruppe erforderlich:

- Sicherheitsrichtlinienverletzungen nach Prioritäts Benutzern
- Datenverluste nach Prioritäts Benutzern

Eine schrittweise Anleitung zum Erstellen einer Prioritäts Benutzergruppe finden Sie im Artikel [Erste Schritte mit Insider Risk Management-Einstellungen](insider-risk-management-settings.md#priority-user-groups-preview) . Wenn Sie eine Prioritäts Benutzergruppe konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-physical-badging-connector-optional"></a>Konfigurieren des physischen Badges-Konnektors (optional)

Das Insider Risk Management unterstützt das Importieren von Benutzer-und Protokolldaten, die von physikalischen Steuerelementen und Zugriffs Plattformen importiert wurden. Der physische Badges-Connector ermöglicht das Abrufen von Access-Daten aus JSON-Dateien, einschließlich Benutzer-IDs, Zugriffspunkt-IDs, Zugriffszeiten und-Daten und Zugriffsstatus. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen physischen Badges-Connector für Ihre Organisation konfigurieren, zieht das Insider-Risikomanagement automatisch Indikatoren aus allen physikalischen Badges-Konnektoren. Informationen aus dem physischen Badges Connector ergänzen andere Insider risikosignale bei Verwendung aller Vorlagen für Insider Risikorichtlinien.

>[!IMPORTANT]
>Damit Richtlinien für das Insider-Risiko-Management Signaldaten im Zusammenhang mit absteigenden und abgebrochenen Benutzern mit Ereignisdaten von ihren physikalischen Steuerungs-und Zugriffs Plattformen verwenden und korrelieren, müssen Sie auch den Microsoft 365 HR-Connector konfigurieren. Wenn Sie den physischen Badges-Connector aktivieren, ohne den Microsoft 365 HR-Connector zu aktivieren, verarbeiten Richtlinien für Insider-Risikomanagement nur Ereignisse für nicht autorisierten physischen Zugriff für Benutzer in Ihrer Organisation.

Lesen Sie den Artikel [Einrichten eines Connectors zum Importieren von physischen Badges-Daten](import-physical-badging-data.md) , um schrittweise Anleitungen zum Konfigurieren des physischen Badges-Connectors für Ihre Organisation zu erhalten. Wenn Sie den Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

## <a name="step-4-configure-insider-risk-settings"></a>Schritt 4: Konfigurieren von Einstellungen für Insider Risiken

Die [Einstellungen für Insider Risiken](insider-risk-management-settings.md) gelten unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben, für alle Insider Risiko-Verwaltungsrichtlinien. Die Einstellungen werden über das Steuerelement **Insider-Risiko-Einstellungen** konfiguriert, das sich oben auf allen Registerkarten des Insider-Risikomanagements befindet. Diese Einstellungen steuern Privatsphäre, Indikatoren, Überwachungsfenster und intelligente Erkennungen.

Definieren Sie vor dem Konfigurieren einer Richtlinie die folgenden Einstellungen für das Insider Risiko:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie in der rechten oberen Ecke jeder Seite die Option **Einstellungen für Insider Risiken** aus.
2. Wählen Sie auf der Seite **Datenschutz** eine Datenschutzeinstellung zum Anzeigen von Benutzernamen für Richtlinienwarnungen aus.
3. Wählen Sie auf der Seite **Indikatoren** die Warnungsindikatoren aus, die Sie auf alle Insider Risikorichtlinien anwenden möchten.

    >[!IMPORTANT]
    >Um Warnungen für riskante Aktivitäten zu erhalten, die in ihren Richtlinien definiert sind, müssen Sie ein oder mehrere Indikatoren auswählen.

4. Wählen Sie auf der Seite **Richtlinienzeit Rahmen** die [Richtlinien Zeiträume](insider-risk-management-settings.md#policy-timeframes) aus, die für einen Benutzer wirksam werden sollen, wenn eine Übereinstimmung mit einer Insider Risiko Richtlinie ausgelöst wird.
5. Konfigurieren Sie auf der Seite **intelligente Erkennungen** die folgenden Einstellungen für Insider Risikorichtlinien:
    - [Anomalie-Erkennungen](insider-risk-management-settings.md#anomaly-detections)
    - [Erkennung anstößiger Sprache](insider-risk-management-settings.md#offensive-language-detections)
    - [Warnstufe auf dem Alert-Volume](insider-risk-management-settings.md#alert-volume)
    - [Microsoft 365 Defender Advanced Threat Protection-Warnungsstatus](insider-risk-management-settings.md#microsoft-defender-advanced-threat-protection-preview)
    - [Domäneneinstellungen](insider-risk-management-settings.md#domains-preview)
6. Aktivieren Sie auf der Seite **Warnungen exportieren** den Export von Warnungsinformationen für Insider Risiken mithilfe der Office 365-Verwaltungs-APIs, falls erforderlich.
7. Erstellen Sie auf der Seite **Priority User** Groups eine Prioritäts Benutzergruppe, und fügen Sie Benutzer hinzu, wenn Sie nicht in **Schritt 3**erstellt wurden.
8. Konfigurieren Sie auf der Seite **Strom Automatisierungs Flüsse** einen Fluss aus Insider Risiko Fluss Vorlagen, oder erstellen Sie einen neuen Fluss. Schritt-für-Schritt-Anleitungen finden Sie im Artikel [Erste Schritte mit Insider-Risikomanagement Einstellungen](insider-risk-management-settings.md#power-automate-flows-preview) .
9. Konfigurieren Sie auf der **Seite Priority Assets**Priority Assets für die Verwendung von Daten aus ihrer physikalischen Steuerung und Zugriffsplattform, die vom physischen Badges-Connector importiert wurden. Schritt-für-Schritt-Anleitungen finden Sie im Artikel [Erste Schritte mit Insider-Risikomanagement Einstellungen](insider-risk-management-settings.md#priority-physical-assets-preview) .
10. Aktivieren Sie auf der **Microsoft Teams** -Seite die Integration von Microsoft Teams in das Insider Risikomanagement, um automatisch ein Team für die Zusammenarbeit bei Fall oder Benutzer zu erstellen. Schritt-für-Schritt-Anleitungen finden Sie im Artikel [Erste Schritte mit Insider-Risikomanagement Einstellungen](insider-risk-management-settings.md#microsoft-teams-preview) .
11. Wählen Sie **Speichern** aus, um diese Einstellungen für ihre Insider Risikorichtlinien zu aktivieren.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Schritt 5: Erstellen einer Richtlinie für das Insider Risikomanagement

Richtlinien für das Insider-Risikomanagement umfassen die zugewiesenen Benutzer und legen fest, welche Arten von Risikoindikatoren für Warnmeldungen konfiguriert werden. Bevor Aktivitäten Warnungen auslösen können, muss eine Richtlinie konfiguriert werden.

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den Richtlinien-Assistenten zu öffnen.
3. Füllen Sie auf der Seite **neue Insider Risiko Richtlinie** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Description (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich)**: Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um die Arten von Risikoindikatoren zu definieren, die von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Die meisten Richtlinienvorlagen verfügen über Voraussetzungen, die für die Richtlinie konfiguriert werden müssen, um relevante Warnungen zu generieren. Wenn Sie die entsprechenden Richtlinien Voraussetzungen nicht konfiguriert haben, finden Sie weitere Informationen unter **Schritt 3** .

    >[!CAUTION]
    >Ab dem 16. Oktober 2020 können Sie keine Richtlinien mehr mit der beleidigenden Sprache in der e-Mail-Vorlage erstellen. Alle aktiven Richtlinien, die diese Vorlage verwenden, funktionieren, bis Sie im Januar 2021 endgültig entfernt werden.

4. Wählen Sie **weiter** aus, um fortzufahren.
5. Wählen Sie auf der Seite **Benutzer** die Option **Benutzer oder Gruppe hinzufügen** oder Benutzer **Gruppen mit Priorität auswählen** aus, um festzulegen, welche Benutzer oder Prioritäts Benutzergruppen in der Richtlinie enthalten sind, je nachdem, welche Richtlinienvorlage Sie ausgewählt haben. Aktivieren Sie gegebenenfalls **alle Benutzer und e-Mail-aktivierten Gruppen** (sofern Sie keine benutzerbasierte Prioritäts Vorlage ausgewählt haben). Wählen Sie **weiter** aus, um fortzufahren.
6. Auf der Seite geben Sie an, **welche Inhalte priorisiert werden sollen (optional)** , können Sie die Quellen zuweisen, um höhere Risikobewertungen zu priorisieren. Einige Aktivitäten generieren jedoch nur dann eine Warnung, wenn der zugehörige Inhalt integrierte oder benutzerdefinierte vertrauliche Informationstypen enthält oder als Priorität auf dieser Seite angegeben wurde:
    - **SharePoint-Websites**: Wählen Sie **SharePoint-Website hinzufügen** und die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - **Typ vertraulicher Informationen**: Wählen Sie **vertraulichen Infotyp hinzufügen** aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - **Vertraulichkeits Bezeichnungen**: Wählen Sie **Vertraulichkeits Bezeichnung hinzufügen** aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
7. Wählen Sie **weiter** aus, um fortzufahren.
8. Auf der Seite **Richtlinien Indikatoren auswählen** werden die [Indikatoren](insider-risk-management-settings.md#indicators) angezeigt, die Sie auf der Seite Indikatoren für **Insider Risiko Einstellungen**als verfügbar definiert haben  >  **Indicators** . Wenn Sie zu Beginn des Assistenten eine Vorlage *Datenverlust* ausgewählt haben, müssen Sie in der Dropdownliste **DLP-Richtlinie** eine DLP-Richtlinie auswählen, um auslösende Indikatoren für die Richtlinie zu aktivieren. Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die Standardeinstellungen für den Richtlinien Schwellenwert für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die **von Microsoft empfohlenen Standardschwellen** Werte und geben Sie die Schwellenwerte für jedes ausgewählte Kennzeichen ein. Wenn Sie mindestens ein *Office* -oder Gerätekennzeichen ausgewählt haben, wählen Sie je nach Bedarf das **Risiko Bewertungs** *Modul* aus. Risiko Bewertungs Verstärker gelten nur für ausgewählte Indikatoren.

    >[!IMPORTANT]
    >Wenn keine Indikatoren auf dieser Seite ausgewählt werden können, müssen Sie die Indikatoren auswählen, die für alle Richtlinien auf der Seite mit **Insider risk management**den  >  **Settings**  >  **Richtlinien Indikatoren** für Insider Risk Management-Einstellungen aktiviert werden sollen.

9. Wählen Sie **weiter** aus, um fortzufahren.
10. Auf der Seite " **Richtlinienzeit Rahmen** " werden die Bedingungen für das [Aktivierungsfenster](insider-risk-management-settings.md#policy-timeframes) für die Richtlinie angezeigt, die auf der Seite mit den Richtlinien für die Richtlinienzeit für **Insider Risiken**vorliegt  >  **Policy timeframes** .
11. Wählen Sie **weiter** aus, um fortzufahren.
12. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Richtlinie für die Verwaltung von Insider Risiken abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Warnungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf mit den Anleitungen in Schritt 4 dieses Artikels oder den Schritten unter [Create a New Insider Risk Policy](insider-risk-management-policies.md#create-a-new-policy).

Weitere Informationen zur Untersuchung von Insider Risikowarnungen und des **Alerts-Dashboards**finden Sie unter [Insider Risk Management Alerts](insider-risk-management-alerts.md).
