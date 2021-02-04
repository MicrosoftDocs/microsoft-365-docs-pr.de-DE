---
title: Erste Schritte mit dem Insider-Risikomanagement
description: Konfigurieren Sie das Insider-Risikomanagement in Ihrer Organisation.
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
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 3eaa6481c2f1b0d41066a8cea1b28d776f786a1b
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094776"
---
# <a name="get-started-with-insider-risk-management"></a>Erste Schritte mit dem Insider-Risikomanagement

Verwenden Sie Richtlinien für das Insider-Risikomanagement, um riskante Aktivitäten und Verwaltungstools zu identifizieren, die auf Risikowarnungen in Ihrer Organisation reagieren. Führen Sie die folgenden Schritte aus, um voraussetzungen zu erstellen und eine Richtlinie für das Insiderrisikomanagement zu konfigurieren.

>[!IMPORTANT]
>Die Microsoft 365-Insider-Risikomanagement-Lösung bietet eine Option auf Mandantenebene, mit der Kunden die interne Governance auf Benutzerebene vereinfachen können. Administratoren auf Mandantenebene können Berechtigungen einrichten, um Mitgliedern Ihrer Organisation Zugriff auf diese Lösung zu gewähren, und Datenconnectors im Microsoft 365 Compliance Center einrichten, um relevante Daten zu importieren, um die Identifizierung potenziell riskanter Aktivitäten auf Benutzerebene zu unterstützen. Kunden bestätigen, dass Erkenntnisse im Zusammenhang mit dem Verhalten, dem Charakter oder der Leistung des einzelnen Benutzers im Zusammenhang mit der Beschäftigung vom Administrator berechnet und anderen personen in der Organisation zur Verfügung stehen. Darüber hinaus bestätigen Die Kunden, dass sie eine eigene vollständige Untersuchung im Zusammenhang mit dem Verhalten, dem Charakter oder der Leistung des einzelnen Benutzers im Zusammenhang mit der Beschäftigung durchführen müssen, und verlassen sich nicht nur auf Erkenntnisse des Insider-Risikomanagementdiensts. Kunden sind ausschließlich für die Verwendung des Microsoft 365-Insider-Risikomanagementdiensts und aller zugehörigen Features oder Dienste in Übereinstimmung mit allen geltenden Gesetzen verantwortlich, einschließlich Gesetzen im Zusammenhang mit der Identifizierung einzelner Benutzer und allen Abhilfemaßnahmen.

Weitere Informationen dazu, wie Richtlinien für Insiderrisiken Ihnen bei der Risikoverwaltung in Ihrer Organisation helfen können, finden Sie unter ["Insider-Risikomanagement" in Microsoft 365.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzierung

Bevor Sie mit dem Insider-Risikomanagement beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Um auf das Insiderrisikomanagement zugreifen und es verwenden zu können, muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5 Insider Risk Management-Add-On
- Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Insider Risk Management-Add-On

Benutzern, die in den Richtlinien für das Insiderrisikomanagement enthalten sind, muss eine der oben genannten Lizenzen zugewiesen werden.

Wenn Sie nicht über einen vorhandenen Microsoft 365 Enterprise E5-Plan verfügen und das Insiderrisikomanagement ausprobieren [](https://www.microsoft.com/microsoft-365/enterprise) möchten, können Sie [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 registrieren.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Schritt 1: Aktivieren von Berechtigungen für das Insider-Risikomanagement

>[!Important]
>Nach dem Konfigurieren ihrer Rollengruppen kann es bis zu 30 Minuten dauern, bis die Rollengruppenberechtigungen auf zugewiesene Benutzer in Ihrer Organisation angewendet werden.

Es gibt vier Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Funktionen für das Insiderrisikomanagement verwendet werden. Um mit diesen Konfigurationsschritten fortzufahren, müssen Ihre Mandantenadministratoren Sie zuerst der Rollengruppe **"Insider Risk Management"** oder **"Insider Risk Management Admin"** zuweisen. Um nach der Erstkonfiguration auf Funktionen des Insider-Risikomanagements zugreifen und diese verwalten zu können, müssen Benutzer Mitglied mindestens einer Rollengruppe für das Insider-Risikomanagement sein.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Wählen Sie bei der Konfiguration des Insider-Risikomanagements aus diesen Rollengruppenoptionen:

| **Rollengruppe** | **Rollenberechtigungen** |
| :---- | :---------------- |
| **Insider Risk Management** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Wenn Sie alle Benutzerkonten für designierte Administratoren, Analytiker und Prüfer hinzufügen, können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für Insider-Risikomanagement. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit dem Insider-Risikomanagement zu beginnen, und ist gut geeignet für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind.|
| **Administrator des Insider-Risikomanagements** | Verwenden Sie diese Rollengruppe, um zunächst das Insider-Risikomanagement zu konfigurieren und später Insider-Risikoadministratoren in eine definierte Gruppe zu untergtrennen.  Benutzer in dieser Rollengruppe können Verwaltungsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen für Insiderrisiken erstellen, lesen, aktualisieren und löschen. |
| **Insider-Risikomanagement-Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungs-, Falll- und Benachrichtigungsvorlagen für Insiderrisiken zugreifen. Sie könne nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen. |
| **Insider-Risikomanagement-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Insider-Risikomanagement-Warnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |

> [!NOTE]
> Diese Rollengruppen werden derzeit von Privileged Identity Management (PIM) nicht unterstützt. Weitere Informationen zu PIM finden Sie unter [Zuweisen von Azure AD-Rollen in Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Hinzufügen von Benutzern zu einer Rollengruppe für das Insiderrisikomanagement

Führen Sie die folgenden Schritte aus, um Benutzer zu einer Rollengruppe für das Insider-Risikomanagement hinzuzufügen:

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **"Berechtigungen".** Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie die Rollengruppe "Insider-Risikomanagement" aus, der Sie Benutzer hinzufügen möchten, und wählen Sie dann **"Rollengruppe bearbeiten" aus.**

4. Wählen **Sie im** linken Navigationsbereich "Mitglieder auswählen" und dann "Bearbeiten" **aus.**

5. Wählen **Sie "Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen **Sie "Speichern"** aus, um die Benutzer zur Rollengruppe hinzuzufügen. Wählen **Sie "Schließen"** aus, um die Schritte ausführen zu können.

## <a name="step-2-enable-the-audit-log"></a>Schritt 2: Aktivieren des Überwachungsprotokolls

Das Insider-Risikomanagement verwendet Audit-Protokolle für Einblicke der Benutzer und Aktivitäten, die in Richtlinien konfiguriert sind. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten im Zusammenhang mit einer Richtlinie für das Insiderrisikomanagement oder bei jeder Änderung einer Richtlinie.

Schrittweise Anweisungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md) Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal tun. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-configure-prerequisites-for-templates"></a>Schritt 3: Konfigurieren der Voraussetzungen für Vorlagen

Die meisten Vorlagen für das Insiderrisikomanagement müssen für Richtlinienindikatoren konfiguriert werden, um relevante Aktivitätswarnungen zu generieren. Konfigurieren Sie die erforderlichen Komponenten in Abhängigkeit von den Richtlinien, die Sie für Ihre Organisation konfigurieren möchten.

### <a name="configure-microsoft-365-hr-connector"></a>Konfigurieren des Microsoft 365 -HR-Connectors

Das Insider-Risikomanagement unterstützt das Importieren von Benutzer- und Protokolldaten, die von Risikomanagement- und Personalplattformen von Drittanbietern importiert wurden. Mit dem Microsoft 365 Personaldatenconnector können Sie Personaldaten aus den CSV-Dateien einziehen, z. B. Datum der Kündigung von Benutzern, Datum der letzten Anstellung, Benachrichtigungen zum Leistungsverbesserungsplan, Leistungsüberprüfungsaktionen und Änderungsstatus auf Auftragsebene. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen Personalconnector für Ihre Organisation konfigurieren, zieht das Insiderrisikomanagement automatisch Indikatoren von allen Personalconnectors.

Der Microsoft 365 -PERSONAL-Connector ist erforderlich, wenn die folgenden Richtlinienvorlagen verwendet werden:

- Verlassener Benutzerdatendiebstahl
- Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer
- Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer
- Datenlecks von verärgerten Benutzern

Schritt-für-Schritt-Anleitungen zum Konfigurieren des Microsoft 365 -PERSONAL-Connectors für Ihre Organisation finden Sie im Artikel zum Einrichten eines Connectors zum Importieren von Personaldaten. [](import-hr-data.md) Nachdem Sie den Connector für die Personalabteilung konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Konfigurieren von Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Das Insiderrisikomanagement unterstützt die Verwendung von DLP-Richtlinien, um die beabsichtigte oder versehentliche Gefährdung vertraulicher Informationen durch unerwünschte Parteien für Warnungen mit hohem Schweregrad zu identifizieren. Wenn Sie eine Richtlinie für das Insiderrisikomanagement mit einer der Vorlagen für **Datenlecks** konfigurieren, müssen Sie der Richtlinie eine bestimmte DLP-Richtlinie zuweisen.

Mithilfe von DLP-Richtlinien können Benutzer identifiziert werden, die die Risikobewertung im Insider-Risikomanagement für vertrauliche Informationen mit hohem Schweregrad aktivieren, und sind ein wichtiger Bestandteil der Konfiguration einer vollständigen Risikomanagementabdeckung in Ihrer Organisation. Weitere Informationen zur Integration und Planung von Insider-Risikomanagement- und -DLP-Richtlinien finden Sie unter Richtlinien für [das Insider-Risikomanagement.](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Stellen Sie sicher, dass Sie Folgendes abgeschlossen haben:
>
>- Sie verstehen und konfigurieren die Benutzer im Bereich sowohl in den DLP- als auch in den Insider-Risikomanagement-Richtlinien, um die von Ihnen zu erwartende Richtlinienabdeckung zu erzeugen.
>- Stellen Sie  sicher, dass die Einstellung für Vorfallberichte in der  DLP-Richtlinie für das Insider-Risikomanagement, die mit diesen Vorlagen verwendet wird, für Warnungen mit hohem Schweregrad konfiguriert ist. Warnungen zum Risikomanagement von Insidern werden nicht aus den DLP-Richtlinien generiert, wenn das Feld **"Vorfallberichte"** auf *"Niedrig"* oder *"Mittel" festgelegt ist.*

Bei Verwendung der folgenden Richtlinienvorlagen ist eine DLP-Richtlinie erforderlich:

- Allgemeine Datenlecks
- Datenlecks nach Prioritätsbenutzern

Schrittweise [Anleitungen zum Konfigurieren von DLP-Richtlinien](create-test-tune-dlp-policy.md) für Ihre Organisation finden Sie im Artikel zum Erstellen, Testen und Optimieren eines DLP-Richtlinienartikels. Nachdem Sie eine DLP-Richtlinie konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-priority-user-groups"></a>Konfigurieren von Benutzergruppen mit Priorität

Das Insider-Risikomanagement umfasst Unterstützung für das Zuweisen von Benutzergruppen mit Priorität zu Richtlinien, um eindeutige Risikoaktivitäten für Benutzer mit kritischen Positionen, ein hohes Datenniveau und netzwerkzugriff oder einen früheren Verlauf des Risikoverhaltens zu unterstützen. Erstellen einer Benutzergruppe mit Priorität und Zuweisen von Benutzern zu den Gruppenhilferichtlinien für die eindeutigen Umstände, die von diesen Benutzern dargestellt werden.

Bei Verwendung der folgenden Richtlinienvorlagen ist eine Benutzergruppe mit Priorität erforderlich:

- Sicherheitsrichtlinienverletzungen nach Prioritätsbenutzern
- Datenlecks nach Prioritätsbenutzern

Schrittweise [Anleitungen zum](insider-risk-management-settings.md#priority-user-groups-preview) Erstellen einer Benutzergruppe mit Priorität finden Sie im Artikel "Erste Schritte mit Einstellungen für das Insider-Risikomanagement". Nachdem Sie eine Benutzergruppe mit Priorität konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-physical-badging-connector-optional"></a>Konfigurieren des Konnektors für physische Badging (optional)

Das Insiderrisikomanagement unterstützt das Importieren von Benutzer- und Protokolldaten, die von physischen Kontroll- und Zugriffsplattformen importiert wurden. Mit dem Connector für physische Badging können Sie Zugriffsdaten aus JSON-Dateien, einschließlich Benutzer-IDs, Zugriffspunkt-IDs, Zugriffszeit und -datumsangaben und Zugriffsstatus, einziehen. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen Connector für physische Badging für Ihre Organisation konfigurieren, zieht das Insiderrisikomanagement automatisch Indikatoren von allen physischen Badging-Connectors. Informationen vom Connector für physische Badging ergänzen andere Insider-Risikosignale, wenn sie alle Vorlagen für Insiderrisiken verwenden.

>[!IMPORTANT]
>Damit Richtlinien für das Insiderrisikomanagement Signaldaten im Zusammenhang mit abwesenden und beendeten Benutzern mit Ereignisdaten von Ihren physischen Kontroll- und Zugriffsplattformen verwenden und korrelieren können, müssen Sie auch den Microsoft 365 -HR-Connector konfigurieren. Wenn Sie den Connector für physische Badging aktivieren, ohne den Microsoft 365 -PERSONAL-Connector zu aktivieren, verarbeiten Richtlinien des Insiderrisikomanagements nur Ereignisse für nicht autorisierten physischen Zugriff für Benutzer in Ihrer Organisation.

Schrittweise [Anleitungen](import-physical-badging-data.md) zum Konfigurieren des Connectors für physische Badging für Ihre Organisation finden Sie im Artikel "Einrichten eines Connectors zum Importieren von Daten zu physischen Badging". Nachdem Sie den Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

## <a name="step-4-configure-insider-risk-settings"></a>Schritt 4: Konfigurieren von Einstellungen für Insiderrisiken

[Einstellungen für Insiderrisiken](insider-risk-management-settings.md) gelten für alle Richtlinien für das Insider-Risikomanagement, unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben. Die Einstellungen werden über das Steuerelement **Insider-Risiko-Einstellungen** konfiguriert, das sich oben auf allen Registerkarten des Insider-Risikomanagements befindet. Diese Einstellungen steuern Privatsphäre, Indikatoren, Überwachungsfenster und intelligente Erkennungen.

Definieren Sie vor dem Konfigurieren einer Richtlinie die folgenden Insider-Risikoeinstellungen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)  zu Insider-Risikomanagement, und wählen Sie die Einstellungen für das Insider-Risiko in der oberen rechten Ecke einer beliebigen Seite aus. 
2. Wählen Sie **auf der** Seite "Datenschutz" eine Datenschutzeinstellung zum Anzeigen von Benutzernamen für Richtlinienwarnungen aus.
3. Wählen Sie **auf der Seite** "Indikatoren" die Warnindikatoren aus, die Sie auf alle Richtlinien für Insiderrisiken anwenden möchten.

    >[!IMPORTANT]
    >Um Warnungen für riskante Aktivitäten zu erhalten, die in Ihren Richtlinien definiert sind, müssen Sie einen oder mehrere Indikatoren auswählen.

4. Wählen Sie auf der Seite [](insider-risk-management-settings.md#policy-timeframes) "Zeitrahmen **für** Richtlinien" die Zeitrahmen für die Richtlinie aus, die für einen Benutzer in Kraft treten sollen, wenn er eine Übereinstimmung für eine Insiderrisikorichtlinie auslöst.
5. Konfigurieren Sie **auf der Seite "Intelligente Erkennungen"** die folgenden Einstellungen für Insider-Risikorichtlinien:
    - [Anomalie-Erkennungen](insider-risk-management-settings.md#anomaly-detections)
    - [Warnungsvolumenebene](insider-risk-management-settings.md#alert-volume)
    - [Warnungsstatus von Microsoft Defender für Endpunkte](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Domäneneinstellungen](insider-risk-management-settings.md#domains-preview)
6. Aktivieren Sie **auf der Seite "Benachrichtigungen** exportieren" den Export von Informationen zu Insiderrisiken bei Bedarf mithilfe der Office 365-Verwaltungs-APIs.
7. Erstellen Sie auf der Seite **Benutzergruppen** mit Priorität eine Benutzergruppe mit Priorität, und fügen Sie Benutzer hinzu, wenn sie nicht in **Schritt 3 erstellt wurden.**
8. Konfigurieren Sie **auf der Power Automate-Flussseite** einen Fluss aus Vorlagen für Insiderrisiken, oder erstellen Sie einen neuen Fluss. Schrittweise [Anleitungen finden](insider-risk-management-settings.md#power-automate-flows-preview) Sie im Artikel "Erste Schritte mit Einstellungen für das Insider-Risikomanagement".
9. Konfigurieren Sie **auf der Seite "Prioritätsressourcen"** Prioritätsressourcen für die Verwendung von Daten aus Ihrer physischen Steuerungs- und Zugriffsplattform, die vom physischen Badgingconnector importiert wurden. Schrittweise [Anleitungen finden](insider-risk-management-settings.md#priority-physical-assets-preview) Sie im Artikel "Erste Schritte mit Einstellungen für das Insider-Risikomanagement".
10. Aktivieren Sie auf der **Microsoft Teams-Seite** die Integration von Microsoft Teams in das Insider-Risikomanagement, um automatisch ein Team für fall- oder benutzerzusammenarbeit zu erstellen. Schrittweise [Anleitungen finden](insider-risk-management-settings.md#microsoft-teams-preview) Sie im Artikel "Erste Schritte mit Einstellungen für das Insider-Risikomanagement".
11. Wählen **Sie "Speichern"** aus, um diese Einstellungen für Ihre Richtlinien für Insiderrisiken zu aktivieren.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Schritt 5: Erstellen einer Richtlinie für das Insiderrisikomanagement

Richtlinien für das Insider-Risikomanagement umfassen die zugewiesenen Benutzer und legen fest, welche Arten von Risikoindikatoren für Warnmeldungen konfiguriert werden. Bevor Aktivitäten Warnungen auslösen können, muss eine Richtlinie konfiguriert werden.

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Registerkarte **"Richtlinien"** aus. 
2. Wählen **Sie "Richtlinie erstellen"** aus, um den Richtlinienassistenten zu öffnen.
3. Füllen Sie auf der Seite "Neue **Insider-Risikorichtlinie"** die folgenden Felder aus:
    - **Name (erforderlich):** Geben Sie einen Anzeigenamen für die Richtlinie ein.
    - **Beschreibung (optional):** Geben Sie eine Beschreibung für die Richtlinie ein.
    - **Richtlinienvorlage auswählen (erforderlich):** Wählen Sie eine der [Richtlinienvorlagen](insider-risk-management-policies.md#policy-templates) aus, um zu definieren, welche Arten von Risikoindikatoren von der Richtlinie überwacht werden.

    >[!IMPORTANT]
    >Die meisten Richtlinienvorlagen verfügen über Voraussetzungen, die konfiguriert werden müssen, damit die Richtlinie relevante Warnungen generiert. Wenn Sie die entsprechenden Richtlinienvoraussetzungen nicht konfiguriert haben, lesen Sie **Schritt 3** weiter oben.

4. Wählen Sie **"Weiter"** aus, um fortzufahren.
5. Wählen Sie **auf**  der Seite "Benutzer" die Option "Benutzer oder Gruppe hinzufügen" oder "Priorität" aus, um zu definieren, welche Benutzer oder Benutzergruppen mit Priorität in der Richtlinie enthalten sind, je nach ausgewählter Richtlinienvorlage.  Aktivieren **Sie ggf. das** Kontrollkästchen Alle Benutzer und E-Mail-aktivierte Gruppen (wenn Sie keine benutzerbasierte Vorlage mit Priorität ausgewählt haben). Wählen Sie **"Weiter"** aus, um fortzufahren.
6. Auf der Seite "Angeben, welcher Inhalt priorisiert werden soll **(optional)"** können Sie die Quellen zuweisen, um höhere Risikobewertungen zu priorisieren. Einige Aktivitäten generieren jedoch keine Warnung, es sei denn, der zugehörige Inhalt enthält integrierte oder benutzerdefinierte Typen vertraulicher Informationen oder wurde auf dieser Seite als Priorität angegeben:
    - **SharePoint-Websites:** Wählen **Sie "SharePoint-Website hinzufügen"** aus, und wählen Sie die SharePoint-Organisationen aus, die Sie priorisieren möchten. Beispiel: *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Vertraulicher Informationstyp:** Wählen Sie **"Vertraulichen Informationstyp hinzufügen"** aus, und wählen Sie die Vertraulichkeitstypen aus, die Sie priorisieren möchten. Beispiel: *"US-Bankkontonummer"* und *"Kreditkartennummer"*.
    - **Vertraulichkeitsbezeichnungen:** Wählen Sie **"Vertraulichkeitsbezeichnung hinzufügen"** aus, und wählen Sie die Bezeichnungen aus, die Sie priorisieren möchten. Beispiel: *"Vertraulich"* und *"Geheim".*
7. Wählen Sie **"Weiter"** aus, um fortzufahren.
8. Auf der **Seite "Richtlinienindikatoren** auswählen" [](insider-risk-management-settings.md#indicators) werden die Indikatoren angezeigt, die Sie auf der Seite "Indikatoren für Insider-Risikoeinstellungen" als verfügbar   >  **definiert** haben. Wenn Sie  zu Beginn des Assistenten eine Vorlage für Datenlecks ausgewählt haben, müssen Sie eine DLP-Richtlinie aus der Dropdownliste der **DLP-Richtlinien** auswählen, um Triggering Indicators für die Richtlinie zu aktivieren. Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die Standardmäßigen Richtlinienschwelleneinstellungen für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die von **Microsoft** empfohlenen Standardschwellenwerte, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein. Wenn Sie mindestens einen *Office-* oder Geräteindikator ausgewählt haben, wählen Sie die **Risikobewertungen** entsprechend aus.  Risikobewertungsindikatoren gelten nur für ausgewählte Indikatoren.

    >[!IMPORTANT]
    >Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien auf der Seite **"Richtlinienindikatoren** für Einstellungen für das Insider-Risikomanagement"  >    >  **aktivieren** möchten.

9. Wählen Sie **"Weiter"** aus, um fortzufahren.
10. Auf der **Seite "Zeitrahmen für Richtlinien"** werden die Bedingungen des [](insider-risk-management-settings.md#policy-timeframes) Aktivierungsfensters für die Richtlinie angezeigt, die auf der Seite "Richtlinien für Insider-Risikoeinstellungen" angezeigt   >   wird.
11. Wählen Sie **"Weiter"** aus, um fortzufahren.
12. Überprüfen Sie **auf** der Seite "Überprüfen" die Einstellungen, die Sie für die Richtlinie ausgewählt haben. Wählen **Sie "Bearbeiten"** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **"Senden"** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Richtlinie für das Insiderrisikomanagement abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Benachrichtigungen von Aktivitätsindikatoren. Konfigurieren Sie nach Bedarf zusätzliche Richtlinien mithilfe der Anleitungen in Schritt 4 dieses Artikels oder der Schritte unter [Erstellen einer neuen Insider-Risikorichtlinie.](insider-risk-management-policies.md#create-a-new-policy)

Weitere Informationen zur Untersuchung von Warnungen zu Insiderrisiken und **zum Dashboard** für Warnungen finden Sie unter [Warnungen zum Insider-Risikomanagement.](insider-risk-management-alerts.md)
