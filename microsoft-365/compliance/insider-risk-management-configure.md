---
title: Erste Schritte mit dem Insider Risikomanagement (Vorschau)
description: Konfigurieren Sie das Insider Risikomanagement in Ihrer Organisation.
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5d32e28d53fccbb16d935bbd9348ad7c12bac365
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259843"
---
# <a name="get-started-with-insider-risk-management-preview"></a>Erste Schritte mit dem Insider Risikomanagement (Vorschau)

Verwenden Sie Richtlinien für Insider-Risikomanagement, um riskante Aktivitäten und Verwaltungstools zu identifizieren, mit denen Aktionen für Risikowarnungen in Ihrer Organisation durchführen werden. Weitere Informationen dazu, wie Sie mit Insider Risikorichtlinien Risiken in Ihrer Organisation verwalten können, finden Sie unter [Insider Risk Management in Microsoft 365](insider-risk-management.md).

>[!IMPORTANT]
>Die Microsoft 365 Insider Risk Management-Lösung bietet eine Mandantenebene, mit der Kunden die interne Steuerung auf Benutzerebene vereinfachen können. Administratoren auf Mandantenebene können Berechtigungen einrichten, um den Zugriff auf diese Lösung für Mitglieder Ihrer Organisation bereitzustellen und Daten-Konnektoren im Microsoft 365 Compliance Center einzurichten, um relevante Daten zu importieren, um die Identifizierung von potentiellen Benutzern auf Benutzerebene zu unterstützen. riskante Aktivität. Kunden bestätigen Einblicke in Bezug auf das Verhalten, den Charakter oder die Leistung der einzelnen Benutzer, die wesentlich im Zusammenhang mit der Beschäftigung stehen, können vom Administrator berechnet und anderen Benutzern in der Organisation zur Verfügung gestellt werden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie mit dem Insider Risk Management beginnen, sollten Sie Ihr Microsoft 365-Abonnement bestätigen. Benutzer, die in Richtlinien für das Insider Risikomanagement enthalten sind, müssen über eine Microsoft 365 E5-Konformitäts Lizenz verfügen oder in einem Microsoft 365 E5-Abonnement enthalten sein.

Wenn Sie keinen vorhandenen Microsoft 365 Enterprise E5-Plan haben und das Insider Risk Management ausprobieren möchten, können Sie Microsoft 365 zu Ihrem vorhandenen Office 365-Abonnement [Hinzufügen](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) oder [sich für eine Testversion](https://www.microsoft.com/microsoft-365/enterprise) von Microsoft 365 Enterprise E5 registrieren.

Führen Sie die folgenden Schritte aus, um das Insider Risikomanagement in Ihrer Microsoft 365-Organisation einzurichten und zu verwenden:

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Schritt 1 (erforderlich): Aktivieren von Berechtigungen für das Insider Risikomanagement

Es gibt vier Berechtigungsrollen, die zum Konfigurieren und Verwalten des Insider Risikomanagements verwendet werden. Um diese Konfigurationsschritte fortzusetzen, müssen ihre mandantenadministratoren Ihnen zunächst die **Administratorrolle "Insider Risk Management"** zuweisen.

| **Rolle** | **Rollenberechtigungen** |
| ---- | ---------------- |
| **Insider Risk Management-Administrator** | Erstellen, lesen, aktualisieren und Löschen von Richtlinien für Insider-Risikomanagement <br> Erstellen, lesen, aktualisieren und Löschen von Berechtigungen und Rollen für das Insider Risikomanagement |
| **Insider Risk Management Analysten** | Zugriff auf alle Warnungen im Insider-Risikomanagement, Fälle und Benachrichtigungen |
| **Insider Risk Management Investigators** | Zugriff auf alle Insider Risk Management-Warnungen,-Fälle,-Benachrichtigungen und den Inhalts-Explorer für alle Fälle |
| **Insider Risk Management Viewer** | Zugriff auf alle Insider Risk Management-Warnungen, Fälle, Benachrichtigungen und den Inhalts-Explorer für alle Fälle anzeigen |

Je nach Struktur Ihres Compliance-Verwaltungsteams haben Sie zwei Berechtigungsoptionen zum Konfigurieren von Rollen zum Verwalten von Funktionen für das Insider-Risikomanagement. Wählen Sie eine der folgenden Rollen Verwaltungsoptionen aus, wenn Sie das Insider Risikomanagement konfigurieren:

1. **Verwenden Sie die Standardrollengruppe "Insider Risk Management**": Verwenden Sie diese Rollengruppe, um das Insider Risikomanagement für Ihre Organisation zu verwalten, indem Sie alle Benutzerkonten für designierte Administratoren, Analysten und Ermittler in einer einzigen Gruppe hinzufügen. Diese Rollengruppe enthält alle Berechtigungen für das Insider Risk Management. Dies ist die einfachste Möglichkeit, um schnell mit dem Insider Risiko-Management zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für getrennte Benutzergruppen definiert werden.
2. **Erstellen Sie unterschiedliche Gruppen für unterschiedliche Verwaltungsrollen**: für Organisationen, die Berechtigungen zum Konfigurieren und Verwalten des Insider Risikomanagements trennen müssen, müssen Sie neue Rollengruppen erstellen und den neuen Gruppen entsprechende Rollen und Benutzer zuweisen. Wenn Sie beispielsweise andere Berechtigungen für die Analyse und Untersuchungen bei Insider Risk Management wünschen, müssen Sie eine Gruppe für Analysten und eine separate Gruppe für Ermittler erstellen. Für jede Gruppe weisen Sie die erforderlichen Rollen für diese Zuständigkeiten zu und fügen dann die Benutzer hinzu, die der Gruppe zugewiesen werden sollen.

Wenn Sie verschiedene Gruppen für unterschiedliche Rollen konfigurieren möchten, verwenden Sie die folgende Tabelle, um jeder Rollengruppe die erforderlichen Rollen zuzuweisen:

| **Gruppen Beispiel** | **Erforderliche Rollen** |
| ---- | ---------------- |
| **Administratoren** | Administratorrolle für das *Insider Risiko Management* |
| **Analysten** | Rolle " *Insider Risk Management Analysts* " <br> *Fall Verwaltungs* Rolle |
| **Ermittler** | Rolle " *Insider Risk Management Investigators* " <br> *Fall Verwaltungs* Rolle |

### <a name="option-1-add-users-to-the-insider-risk-management-role-group"></a>Option 1: Hinzufügen von Benutzern zur Rollengruppe "Insider Risk Management"

Wenn Sie eine Rollengruppe für alle Benutzer verwenden möchten, die das Insider Risikomanagement konfigurieren und verwalten, führen Sie die folgenden Schritte aus, um Benutzer der Standardrollengruppe " **Insider Risk Management** " hinzuzufügen:

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft Office 365 Security and Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie die Rollengruppe *Insider Risk Management* aus, und wählen Sie dann **Rollengruppe bearbeiten**aus.

4. Wählen Sie im linken Navigationsbereich **Elemente** auswählen aus, und wählen Sie dann **Bearbeiten**aus.

5. Wählen Sie **Hinzufügen** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen**und dann **Fertig**aus.

7. Wählen Sie **Speichern** aus, um die Benutzer der Rollengruppe hinzuzufügen. Wählen Sie **Schließen** aus, um die Schritte abzuschließen.

### <a name="option-2-create-a-new-role-group"></a>Option 2: Erstellen einer neuen Rollengruppe

Wenn Sie separate Rollengruppen für unterschiedliche Verwaltungsrollen erstellen müssen, führen Sie die folgenden Schritte aus, um jede neue Gruppe zu erstellen:

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft Office 365 Security and Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie **Erstellen** aus.

4. Geben Sie der neuen Rollengruppe im Feld **Name** einen Anzeigenamen. Wählen Sie **Weiter** aus.

5. Wählen Sie **Rollen auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für die Rollen, die Sie zuweisen müssen. Wenn diese Gruppe beispielsweise für Insider Risikoanalysten gilt, wählen Sie die Rolle *Insider Risk Management Analysts* und die *Fall Management* Rolle aus, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

6. Wählen Sie **Mitglieder auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für alle Benutzer und Gruppen, für die Sie Richtlinien erstellen und Nachrichten mit Richtlinien Übereinstimmungen verwalten möchten, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

7. Wählen Sie **Rollengruppe erstellen** aus, um abzuschließen.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter [Berechtigungen im Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-optional-configure-the-microsoft-365-human-resources-data-connector"></a>Schritt 2 (optional): Konfigurieren des Microsoft 365-datenconnectors für Humanressourcen

Das Insider Risk Management unterstützt das Importieren von Benutzer-und Protokolldaten, die von 3rd-Party-Risikomanagement-und Personalressourcen Plattformen importiert wurden. Mit dem Microsoft 365-Datenconnector für Humanressourcen (HR) können Sie Daten aus der CSV-Datei in der Personalabteilung einbinden, einschließlich Benutzer Beendigung und Datum der letzten Arbeit. Diese Daten helfen, die Warnindikatoren in Richtlinien für das Insider Risiko zu steuern, und sind ein wichtiger Bestandteil der Konfiguration des vollständigen Risikomanagements in Ihrer Organisation.

Lesen Sie den Abschnitt [Einrichten eines Connectors zum Importieren von HR-Daten](import-hr-data.md) , um Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation zu erhalten. Wenn Sie den HF-Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

>[!IMPORTANT]
>Wenn Sie planen, eine Richtlinie mithilfe der *Datendiebstahl* Vorlage für den abgehenden Mitarbeiter zu konfigurieren, müssen Sie den HR-Connector so konfigurieren, dass er die vollständigen Signal Erkennungsfunktionen der Richtlinienvorlage verwendet. Wenn Sie mehr als einen HF-Connector für Ihre Organisation konfigurieren, ruft das Insider Risikomanagement automatisch Indikatoren von allen HR-Connectors ab.

## <a name="step-3-optional-configure-data-loss-prevention-dlp-policies"></a>Schritt 3 (optional): Konfigurieren von Richtlinien zur Verhinderung von Datenverlust (DLP)

Das Insider Risikomanagement unterstützt die Verwendung von DLP-Richtlinien, um die absichtliche oder versehentliche Exposition vertraulicher Informationen an unerwünschte Personen zu identifizieren. Wenn Sie eine Richtlinie für Insider-Risikomanagement mit der Vorlage *Datenlecks* konfigurieren, müssen Sie der Richtlinie eine bestimmte DLP-Richtlinie zuweisen. Diese Richtlinie hilft, die Warnindikatoren für vertrauliche Informationen zu konfigurieren, ist ein wichtiger Bestandteil der Konfiguration der vollständigen Risikomanagement Abdeckung in Ihrer Organisation.

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie unter [erstellen, testen und Optimieren eines DLP-Richtlinien](create-test-tune-dlp-policy.md) Themas. Wenn Sie eine DLP-Richtlinie konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

>[!IMPORTANT]
>Wenn Sie planen, eine Richtlinie mithilfe der *Datenlecks* -Vorlage zu konfigurieren, müssen Sie mindestens eine DLP-Richtlinie konfigurieren, um die vollständigen Signal Erkennungs Features der Richtlinienvorlage zu verwenden. Wenn Sie mehr als eine DLP-Richtlinie für Ihre Organisation konfigurieren, müssen Sie pro DLP-Richtlinie eine Richtlinie für Insider-Risikomanagement zuweisen.

## <a name="step-4-required-create-an-insider-risk-management-policy"></a>Schritt 4 (erforderlich): Erstellen einer Richtlinie für das Insider Risikomanagement

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
8. Auf der Seite **Warnungsindikatoren auswählen** werden die Indikatoren angezeigt, die in der Vorlage enthalten sind, die Sie für diese Richtlinie ausgewählt haben. Wenn Sie die *Datenlecks* -Vorlage zu Beginn des Assistenten ausgewählt haben, müssen Sie in der Dropdownliste DLP- **Richtlinie** eine DLP-Richtlinie auswählen.
9. Auf der Seite **Überwachungsfenster auswählen** definieren Sie die Bedingungen für das [Überwachungsfenster](insider-risk-management-policies.md#monitoring-windows) für die Richtlinie. Konfigurieren Sie die Überwachungsfenster entsprechend.
10. Wählen Sie **weiter** aus, um fortzufahren.
11. Überprüfen Sie auf der Seite **überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen Sie **Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Richtlinie für die Verwaltung von Insider Risiken abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Warnungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf anhand der Anleitungen in Schritt 4 dieses Themas oder der Schritte unter [Create a New Insider Risk Policy](insider-risk-management-policies.md#create-a-new-policy).
