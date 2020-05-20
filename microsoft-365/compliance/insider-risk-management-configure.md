---
title: Erste Schritte mit dem Insider-Risikomanagement
description: Konfigurieren Sie das Insider Risikomanagement in Ihrer Organisation.
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 68e8f432008a6322921ef440878a1cca1354e196
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292473"
---
# <a name="get-started-with-insider-risk-management"></a>Erste Schritte mit dem Insider-Risikomanagement

Verwenden Sie Richtlinien für das Insider-Risikomanagement, um riskante Aktivitäten und Verwaltungstools zu identifizieren, um Maßnahmen bei Risikoalarmen in Ihrer Organisation zu ergreifen. Führen Sie die folgenden Schritte aus, um Voraussetzungen einzurichten und eine Richtlinie für Insider-Risikomanagement zu konfigurieren.

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

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Schritt 1 (erforderlich): Aktivieren von Berechtigungen für das Insider Risikomanagement

Es gibt vier Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Funktionen für das Insider Risikomanagement verwendet werden. Um diese Konfigurationsschritte fortzusetzen, müssen ihre mandantenadministratoren Sie zunächst der Administratorrollengruppe " **Insider Risk Management** **" oder "Insider Risk Management"** zuweisen. Für den Zugriff auf und die Verwaltung von Funktionen für das Insider-Risikomanagement nach der Erstkonfiguration müssen Benutzer Mitglied mindestens einer Rollengruppe für das Risikomanagement für Insider sein.

Je nach Struktur Ihres Compliance-Verwaltungsteams haben Sie die Möglichkeit, Benutzer bestimmten Rollengruppen zuzuweisen, um verschiedene Gruppen von Insider Risikomanagement-Features zu verwalten. Wählen Sie unter diese Rollengruppen Optionen beim Konfigurieren des Insider Risikomanagements:

| **Rollengruppe** | **Rollenberechtigungen** |
| :---- | :---------------- |
| **Insider Risiko Management** | Verwenden Sie diese Rollengruppe, um das Insider Risikomanagement für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten und Ermittler können Sie die Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungen für das Insider Risk Management. Diese Konfiguration ist die einfachste Möglichkeit, um schnell mit dem Insider Risiko-Management zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert werden.|
| **Insider Risk Management-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst das Insider Risikomanagement zu konfigurieren und später Insider Risiko Administratoren in eine definierte Gruppe zu unter trennen.  Benutzer in dieser Rollengruppe können Richtlinien für die Verwaltung von Insider Risiken, globale Einstellungen und Rollengruppen Zuordnungen erstellen, lesen, aktualisieren und löschen. |
| **Insider Risk Management Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Risikoanalysten für Insider Risiken fungieren sollen. Benutzer in dieser Rollengruppe können auf alle Alerts-, Cases-und Notices-Vorlagen für Insider-Risikomanagement zugreifen. Sie können nicht auf den Insider Risiko-Inhalts-Explorer zugreifen. |
| **Insider Risk Management Investigators** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Insider Risiko-Daten Ermittler fungieren sollen. Benutzer in dieser Rollengruppe können in allen Fällen auf alle Alerts für Insider-Risikomanagement,-Fälle,-Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Hinzufügen von Benutzern zu einer Rollengruppe "Insider Risk Management"

Führen Sie die folgenden Schritte aus, um Benutzer zu einer Rollengruppe "Insider Risk Management" hinzuzufügen:

1. Melden [https://protection.office.com/permissions](https://protection.office.com/permissions) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an. "" "" "" ""

2. &amp;Wechseln Sie im Security Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie die Rollengruppe "Insider Risk Management" aus, der Sie Benutzer hinzufügen möchten, und wählen Sie dann **Rollengruppe bearbeiten**aus.

4. Wählen Sie im linken Navigationsbereich **Elemente** auswählen aus, und wählen Sie dann **Bearbeiten**aus.

5. Wählen Sie **Hinzufügen** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen**und dann **Fertig**aus.

7. Wählen Sie **Speichern** aus, um die Benutzer der Rollengruppe hinzuzufügen. Wählen Sie **Schließen** aus, um die Schritte abzuschließen.

## <a name="step-2-required-enable-the-audit-log"></a>Schritt 2 (erforderlich): Aktivieren des Überwachungsprotokolls

Das Insider Risikomanagement verwendet Überwachungsprotokolle für Benutzer Einblicke und in Richtlinien konfigurierte Aktivitäten. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die einer Richtlinie für Insider Risiken zugeordnet sind, oder wenn sich eine Richtlinie ändert.

Eine Schritt-für-Schritt-Anleitung zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](turn-audit-log-search-on-or-off.md). Nachdem Sie die Überwachung aktiviert haben, wird eine Meldung angezeigt, die besagt, dass das Überwachungsprotokoll vorbereitet wird und dass Sie eine Suche in einigen Stunden nach Abschluss der Vorbereitung ausführen können. Sie müssen diese Aktion nur einmal ausführen. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-configure-prerequisites-for-templates"></a>Schritt 3 (optional): Konfigurieren der Voraussetzungen für Vorlagen

Einige Vorlagen für Insider Risikomanagement haben Voraussetzungen, die für Richtlinien Indikatoren konfiguriert werden müssen, um relevante Aktivitäts Warnungen zu generieren. Konfigurieren Sie die entsprechenden Voraussetzungen in Abhängigkeit von den Richtlinien, die Sie für Ihre Organisation konfigurieren möchten.

### <a name="configure-microsoft-365-hr-connector"></a>Konfigurieren des Microsoft 365 HR-Connectors

Das Insider Risk Management unterstützt das Importieren von Benutzer-und Protokolldaten, die von 3rd-Party-Risikomanagement-und Personalressourcen Plattformen importiert wurden. Mit dem Microsoft 365-Datenconnector für Humanressourcen (HR) können Sie Daten aus der CSV-Datei in der Personalabteilung einbinden, einschließlich Benutzer Beendigung und Datum der letzten Arbeit. Diese Daten helfen, Warnindikatoren in Richtlinien für das Insider Risikomanagement zu unterstützen, und sind ein wichtiger Bestandteil der Konfiguration der vollständigen Risikomanagement Abdeckung in Ihrer Organisation.

Lesen Sie den Abschnitt [Einrichten eines Connectors zum Importieren von HR-Daten](import-hr-data.md) , um Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten. Wenn Sie den HF-Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

>[!IMPORTANT]
>Wenn Sie eine Richtlinie mithilfe der *Datendiebstahl* Vorlage für den abgehenden Mitarbeiter konfigurieren, müssen Sie den HR-Connector so konfigurieren, dass er die vollständigen Signal Erkennungsfunktionen der Richtlinienvorlage verwendet. Wenn Sie mehr als einen HF-Connector für Ihre Organisation konfigurieren, ruft das Insider Risikomanagement automatisch Indikatoren von allen HR-Connectors ab.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Konfigurieren von Richtlinien zur Verhinderung von Datenverlust (DLP)

Das Insider Risikomanagement unterstützt die Verwendung von DLP-Richtlinien, um die absichtliche oder versehentliche Exposition vertraulicher Informationen an unerwünschte Personen zu identifizieren. Wenn Sie eine Richtlinie für Insider-Risikomanagement mit der Vorlage *Datenlecks* konfigurieren, müssen Sie der Richtlinie eine bestimmte DLP-Richtlinie zuweisen.

Diese Richtlinie unterstützt das Risikomanagement von Insider-Indikatoren für DLP-Warnungen mit hohem Schweregrad für vertrauliche Informationen und ist ein wichtiger Bestandteil der Konfiguration der vollständigen Risikomanagement Abdeckung in Ihrer Organisation. Wenn Sie mehr als eine DLP-Richtlinie für Ihre Organisation konfigurieren, müssen Sie pro DLP-Richtlinie eine Richtlinie für Insider-Risikomanagement zuweisen.

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Themas. Wenn Sie eine DLP-Richtlinie konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

>[!IMPORTANT]
>Stellen Sie sicher, dass die Einstellung **vorfallberichte** in der DLP-Richtlinie für das Insider Risikomanagement, die mit dieser Vorlage verwendet wird, für Warnungen mit *hohem* Schweregrad konfiguriert ist. Warnungen beim Insider-Risikomanagement werden nicht aus DLP-Richtlinien generiert, wenn das Feld " **vorfallberichte** " auf *niedrig* oder *Mittel*festgelegt ist.

## <a name="step-4-required-configure-insider-risk-settings"></a>Schritt 4 (erforderlich): Konfigurieren von Einstellungen für Insider Risiken

Die [Einstellungen für Insider Risiken](insider-risk-management-policies.md#policy-settings) gelten unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben, für alle Insider Risiko-Verwaltungsrichtlinien. Einstellungen werden mit dem Steuerelement " **Insider Risk Settings** " konfiguriert, das sich oben auf allen Registerkarten für das Insider Risikomanagement befindet. Mit diesen Einstellungen werden Datenschutz, Indikatoren, Überwachungsfenster und intelligente Erkennungen gesteuert.

Definieren Sie vor dem Konfigurieren einer Richtlinie die folgenden Einstellungen für das Insider Risiko:

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie in der rechten oberen Ecke jeder Seite die Option **Einstellungen für Insider Risiken** aus.
2. Wählen Sie auf der Seite **Datenschutz** eine Datenschutzeinstellung zum Anzeigen von Benutzernamen für Richtlinienwarnungen aus.
3. Wählen Sie auf der Seite **Indikatoren** die Warnungsindikatoren aus, die Sie auf alle Insider Risikorichtlinien anwenden möchten.

    >[!IMPORTANT]
    >Um Warnungen für riskante Aktivitäten zu erhalten, die in ihren Richtlinien definiert sind, müssen Sie ein oder mehrere Indikatoren auswählen.

4. Wählen Sie auf der Seite **Richtlinienzeit Rahmen** die [Richtlinien Zeiträume](insider-risk-management-policies.md#policy-timeframes) aus, die für einen Benutzer wirksam werden sollen, wenn eine Übereinstimmung mit einer Insider Risiko Richtlinie ausgelöst wird.
5. Konfigurieren Sie auf der Seite **intelligente Erkennungen** die [Anomalie-Erkennung, die Erkennung anstößiger Sprachen und die Warnstufe für Warnmeldungen](insider-risk-management-policies.md#intelligent-detections) für Insider Risikorichtlinien.
6. Wählen Sie **Speichern** aus, um diese Einstellungen für ihre Insider Risikorichtlinien zu aktivieren.

## <a name="step-5-required-create-an-insider-risk-management-policy"></a>Schritt 5 (erforderlich): Erstellen einer Richtlinie für das Insider Risikomanagement

Die Richtlinien für das Insider Risikomanagement umfassen zugewiesene Benutzer und definieren, welche Arten von Risikoindikatoren für Warnungen konfiguriert sind. Bevor Aktivitäten Warnungen auslösen können, muss eine Richtlinie konfiguriert werden.

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den richtlinienassistenten zu öffnen
3. Füllen Sie auf der Seite **neue Insider Risiko Richtlinie** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Description (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich)**: Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um die Arten von Risikoindikatoren zu definieren, die von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Wenn Sie die *Datenlecks* -Vorlage auswählen, müssen Sie mindestens eine DLP-Richtlinie konfigurieren, die Sie später im Assistenten zuweisen. Wenn Sie die *Datendiebstahl Vorlage "departing Employee* " auswählen, müssen Sie den HR-Connector so konfigurieren, dass er die vollständigen Signal Erkennungsfunktionen der Richtlinienvorlage verwendet.

4. Wählen Sie **weiter** aus, um fortzufahren.
5. Wählen Sie auf der Seite **Benutzer** die Option **Benutzer oder Gruppe hinzufügen** aus, um zu definieren, welche Benutzer in das Kontrollkästchen Richtlinie eingeschlossen sind, oder **alle Benutzer und e-Mail-aktivierten Gruppen** auswählen. Wählen Sie **weiter** aus, um fortzufahren.
6. Auf der Seite geben Sie an, **welche Inhalte priorisiert werden sollen (optional)** , können Sie die Quellen zuweisen, um riskante Benutzeraktivitäten zu priorisieren:
    - **SharePoint-Websites**: Wählen Sie **SharePoint-Website hinzufügen** und die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.SharePoint.com/Sites/Group1"*.
    - **Typ vertraulicher Informationen**: Wählen Sie **vertraulichen Infotyp hinzufügen** aus, und wählen Sie die Vertraulichkeits Typen aus, die Sie priorisieren möchten. Beispiel: *"US Bank Account Number"* und *"Kreditkartennummer"*.
    - **Vertraulichkeits Bezeichnungen**: Wählen Sie **Vertraulichkeits Bezeichnung hinzufügen** aus, und wählen Sie die Beschriftungen aus, die Sie priorisieren möchten. Beispiel: *"vertraulich"* und *"geheim"*.
7. Wählen Sie **weiter** aus, um fortzufahren.
8. Auf der Seite mit den **Warnungsindikatoren** werden die Indikatoren angezeigt, die Sie auf der Seite Indikatoren für **Insider Risiko Einstellungen**definiert haben  >  **Indicators** . Wenn Sie die *Datenlecks* -Vorlage zu Beginn des Assistenten ausgewählt haben, müssen Sie in der Dropdownliste DLP- **Richtlinie** eine DLP-Richtlinie auswählen.
9. Auf der Seite **Überwachungsfenster auswählen** werden die Bedingungen für das [Überwachungsfenster](insider-risk-management-policies.md#policy-timeframes) für die Richtlinie angezeigt, die auf der Seite mit den Richtlinien für die Richtlinienzeit für **Insider Risiken**angezeigt wird  >  **Policy timeframes** . Wenn Sie die Datendiebstahl Richtlinienvorlage für *departs-Mitarbeiter* ausgewählt haben, können Sie das Kontrollkästchen nach *Beendigung der Aktivität nach Abschluss überprüfen* aktivieren, um die Aktivität nach dem vom Microsoft 365 HR-Connector importierten Beendigungsdatum zu erkennen.
10. Wählen Sie **weiter** aus, um fortzufahren.
11. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Richtlinie für die Verwaltung von Insider Risiken abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Warnungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf anhand der Anleitungen in Schritt 4 dieses Themas oder der Schritte unter [Create a New Insider Risk Policy](insider-risk-management-policies.md#create-a-new-policy).
