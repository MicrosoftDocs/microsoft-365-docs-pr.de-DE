---
title: Erste Schritte mit dem Insider-Risikomanagement
description: Konfigurieren Des Insider-Risikomanagements in Ihrer Organisation.
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
ms.openlocfilehash: 9e1b7a18bea09d10cb133ce9106df45533a72172
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445229"
---
# <a name="get-started-with-insider-risk-management"></a>Erste Schritte mit dem Insider-Risikomanagement

Verwenden Sie Insider-Risikomanagementrichtlinien, um riskante Aktivitäten und Verwaltungstools zu identifizieren, um Risikowarnungen in Ihrer Organisation zu reagieren. Führen Sie die folgenden Schritte aus, um voraussetzungen zu erstellen und eine Richtlinie für das Insiderrisikomanagement zu konfigurieren.

>[!IMPORTANT]
>Die Microsoft 365 insider risk management bietet eine Option auf Mandantenebene, mit der Kunden die interne Steuerung auf Benutzerebene vereinfachen können. Administratoren auf Mandantenebene können Berechtigungen einrichten, um Mitgliedern Ihrer Organisation Zugriff auf diese Lösung zu gewähren, und Datenconnectors im Microsoft 365 Compliance Center einrichten, um relevante Daten zu importieren, um die Identifizierung potenziell riskanter Aktivitäten auf Benutzerebene zu unterstützen. Kunden bestätigen, dass Erkenntnisse im Zusammenhang mit dem Verhalten, dem Charakter oder der Leistung des einzelnen Benutzers im Zusammenhang mit der Beschäftigung vom Administrator berechnet und anderen in der Organisation zur Verfügung stehen können. Darüber hinaus erkennen Kunden an, dass sie ihre eigenen vollständigen Untersuchungen im Zusammenhang mit dem Verhalten, dem Charakter oder der Leistung des einzelnen Benutzers im Zusammenhang mit der Beschäftigung durchführen müssen und sich nicht nur auf Erkenntnisse des Insider-Risikomanagementdiensts verlassen müssen. Kunden sind allein für die Verwendung des Microsoft 365-Insider-Risikomanagement-Diensts und aller zugehörigen Funktionen oder Dienste gemäß allen geltenden Gesetzen verantwortlich, einschließlich der Gesetze zur Identifizierung einzelner Benutzer und aller Abhilfemaßnahmen.

Weitere Informationen dazu, wie Insiderrisikorichtlinien Ihnen beim Verwalten von Risiken in Ihrer Organisation helfen können, finden Sie unter [Insider Risk Management in Microsoft 365](insider-risk-management.md).

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzierung

Bevor Sie mit insider risk management beginnen, sollten Sie Ihr Microsoft 365 und alle Add-Ons bestätigen. [](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) Für den Zugriff auf und die Verwendung des Insiderrisikomanagements muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5 Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 E3 Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3 Abonnement + das Microsoft 365 E5 Insider Risk Management-Add-On
- Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 A3-Abonnement + Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3-Abonnement + Microsoft 365 A5 Insider Risk Management-Add-On
- Microsoft 365 G5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 G3 Abonnement + das Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 G3 Abonnement + das Microsoft 365 G5 Insider Risk Management-Add-On
- Office 365 E3-Abonnement + Enterprise Mobility and Security E3 + das Microsoft 365 E5 Compliance-Add-On

Benutzern, die in Insider-Risikomanagementrichtlinien enthalten sind, muss eine der oben genannten Lizenzen zugewiesen werden.

Wenn Sie nicht über einen vorhandenen Microsoft 365 Enterprise E5-Plan verfügen und insider risk management ausprobieren möchten, [](https://www.microsoft.com/microsoft-365/enterprise) können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 registrieren.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Schritt 1: Aktivieren von Berechtigungen für das Insider-Risikomanagement

>[!Important]
>Nach dem Konfigurieren Ihrer Rollengruppen kann es bis zu 30 Minuten dauern, bis die Rollengruppenberechtigungen auf zugewiesene Benutzer in Ihrer Organisation angewendet werden.

Es gibt vier Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Insider-Risikomanagementfeatures verwendet werden. Um mit diesen Konfigurationsschritten fortzufahren, müssen Ihre Mandantenadministratoren Sie zunächst der Rollengruppe **Insider Risk Management** oder Insider Risk Management **Admin** zuweisen. Für den Zugriff auf und die Verwaltung von Insider-Risikomanagementfeatures nach der Erstkonfiguration müssen Benutzer Mitglied mindestens einer Rollengruppe für insider risk management sein.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Zum Anzeigen  der Registerkarte Berechtigungen im Office 365 Security & Compliance Center und zum Verwalten von  Rollengruppen müssen Sie der Rollengruppe "Organisationsverwaltung" oder der Rollenverwaltungsrolle *zugewiesen* werden. Wählen Sie bei der Konfiguration des Insiderrisikomanagements aus diesen Rollengruppenoptionen:

| **Rollengruppe** | **Rollenberechtigungen** |
| :------------- | :------------------- |
| **Insider Risk Management** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Auditoren können Sie Berechtigungen für das Insiderrisikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Insider-Risikomanagement-Berechtigungsrollen und zugehörige Berechtigungen. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit dem Insider-Risikomanagement zu beginnen, und ist gut geeignet für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Insider Risk Management Admin** | Verwenden Sie diese Rollengruppe, um zunächst das Insiderrisikomanagement zu konfigurieren und später Insiderrisikoadministratoren in eine definierte Gruppe zu trennen. Benutzer in dieser Rollengruppe können Analyseeinblicke aktivieren und anzeigen sowie Insider-Risikomanagementrichtlinien, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. |
| **Insider-Risikomanagement-Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen, Fälle, Analyseeinblicke und Benachrichtigungsvorlagen für Insider-Risikomanagement zugreifen und diese anzeigen. Sie können nicht auf den Insider risk Content Explorer zugreifen. |
| **Insider-Risikomanagement-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können für alle Fälle auf alle Insider-Risikomanagementwarnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer zugreifen. |
| **Insider Risk Management Auditoren** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Insider-Risikomanagementaktivitäten überwachen. Benutzer in dieser Rollengruppe können auf das Überwachungsprotokoll für Insiderrisiken zugreifen. |

> [!NOTE]
> Diese Rollengruppen werden derzeit nicht auf Privileged Identity Management (PIM) unterstützt. Weitere Informationen zu PIM finden Sie unter [Assign Azure AD roles in Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Hinzufügen von Benutzern zu einer Rollengruppe für insiders Risikomanagement

Führen Sie die folgenden Schritte aus, um Benutzer zu einer Rollengruppe für insider risk management hinzuzufügen:

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 an.

2. Wechseln Sie im Security &amp; Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365.

3. Wählen Sie die Rollengruppe insider risk management aus, der Sie Benutzer hinzufügen möchten, und wählen Sie dann **Rollengruppe bearbeiten aus.**

4. Wählen **Sie im** linken Navigationsbereich Mitglieder auswählen aus, und wählen Sie dann Bearbeiten **aus.**

5. Wählen **Sie Hinzufügen** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen **Sie Speichern** aus, um die Benutzer zur Rollengruppe hinzuzufügen. Wählen **Sie Schließen** aus, um die Schritte zu ausführen.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Schritt 2: Aktivieren des Microsoft 365 Überwachungsprotokolls

Das Insider-Risikomanagement verwendet Microsoft 365 Überwachungsprotokolle für Benutzereinblicke und Aktivitäten, die in Richtlinien und Analyseeinblicken identifiziert werden. Die Microsoft 365-Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten innerhalb Ihrer Organisation, und Insider-Risikomanagementrichtlinien können diese Aktivitäten zum Generieren von Richtlinieneinblicken verwenden.

Schrittweise Anweisungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md) Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal tun. Weitere Informationen zur Verwendung des Überwachungsprotokolls Microsoft 365 finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Schritt 3: Aktivieren und Anzeigen von Insider Risk Analytics Insights (optional)

Insider risk management analytics ermöglicht es Ihnen, eine Bewertung potenzieller Insiderrisiken in Ihrer Organisation zu führen, ohne Insiderrisikorichtlinien zu konfigurieren. Diese Bewertung kann Ihre Organisation dabei unterstützen, potenzielle Bereiche mit einem höheren Benutzerrisiko zu identifizieren und den Typ und Umfang von Insider-Risikomanagementrichtlinien zu bestimmen, die Sie möglicherweise konfigurieren möchten. Diese Bewertung kann Ihnen auch dabei helfen, die Anforderungen für eine zusätzliche Lizenzierung oder zukünftige Optimierung vorhandener Richtlinien zu ermitteln. Analysescanergebnisse können bis zu 48 Stunden dauern, bis Einblicke als Berichte zur Überprüfung verfügbar sind. Weitere Informationen zu Analyseeinblicken finden Sie unter [Insider risk management settings: Analytics (preview)](insider-risk-management-settings.md#analytics-preview) und im [Video Insider Risk Management Analytics,](https://www.youtube.com/watch?v=5c0P5MCXNXk) um zu verstehen, wie Analysen die Identifizierung potenzieller Insiderrisiken beschleunigen und Ihnen dabei helfen, schnell Maßnahmen zu ergreifen.

Um Insider risk Analytics zu aktivieren, müssen Sie Mitglied der Rollengruppe *"Insider Risk Management",* *"Insider Risk Management Admin"* oder "Microsoft 365 *Globaler* Administrator" sein.

Führen Sie die folgenden Schritte aus, um insider risk analytics zu aktivieren:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management**.
2. Wählen **Sie auf** der Registerkarte Übersicht über insider risk management die Option Überprüfung auf Insiderrisiken **auf** Ihrer Organisationskarte **ausführen** aus. Mit dieser Aktion wird die Analyseprüfung für Ihre Organisation aktiviert. Sie können die Überprüfung auch in Ihrer Organisation aktivieren, indem Sie zu Insider Risk **Settings**  >  **Analytics (Vorschau)** navigieren und die Benutzeraktivität Ihres Mandanten überprüfen aktivieren, um potenzielle **Insiderrisiken zu identifizieren.**
3. Wählen Sie **im Detailbereich** Analyse die Option Scan ausführen aus, **um die Überprüfung für Ihre Organisation zu starten.** Die Analysescanergebnisse können bis zu 24 Stunden dauern, bis Einblicke als Berichte zur Überprüfung zur Verfügung stehen.

Nachdem Sie die Analyseeinblicke überprüft haben, wählen Sie die Insider-Risikorichtlinien aus, und konfigurieren Sie die zugehörigen Voraussetzungen, die die Strategie zur Risikominderung für Insider in Ihrer Organisation am besten erfüllen.

## <a name="step-4-configure-prerequisites-for-policies"></a>Schritt 4: Konfigurieren von Voraussetzungen für Richtlinien

Die meisten Insider-Risikomanagementrichtlinien verfügen über Voraussetzungen, die konfiguriert werden müssen, damit Richtlinienindikatoren relevante Aktivitätswarnungen generieren können. Konfigurieren Sie die entsprechenden Voraussetzungen in Abhängigkeit von den Richtlinien, die Sie für Ihre Organisation konfigurieren möchten.

### <a name="configure-microsoft-365-hr-connector"></a>Konfigurieren Microsoft 365 Hr Connector

Das Insider-Risikomanagement unterstützt das Importieren von Benutzer- und Protokolldaten, die von Drittanbieter-Risikomanagement- und Personalplattformen importiert wurden. Mit dem Microsoft 365 Personaldatenconnector können Sie Personaldaten aus CSV-Dateien einziehen, z. B. Benutzerendtermine, Datum der letzten Beschäftigung, Benachrichtigungen zum Leistungsverbesserungsplan, Leistungsüberprüfungsaktionen und Änderungsstatus auf Auftragsebene. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen Personalconnector für Ihre Organisation konfigurieren, zieht das Insiderrisikomanagement automatisch Indikatoren von allen Personalconnectors ab.

Der Microsoft 365 hr connector ist erforderlich, wenn die folgenden Richtlinienvorlagen verwendet werden:

- Ausgehender Benutzerdatendiebstahl
- Sicherheitsrichtlinienverletzungen durch ausscheidende Benutzer
- Sicherheitsrichtlinienverletzungen durch verärgerte Benutzer
- Datenlecks durch unzufriedene Benutzer

Im Artikel [Einrichten eines Connectors](import-hr-data.md) zum Importieren von Personaldaten finden Sie schrittweise Anleitungen zum Konfigurieren Microsoft 365 Personalabteilungsconnector für Ihre Organisation. Nachdem Sie den Hr-Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Konfigurieren von Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Insider risk management supports using DLP policies to help identify the intentional or accidental exposure of sensitive information to unwanted parties for High severity level DLP alerts. Wenn Sie eine Insider-Risikomanagementrichtlinie mit einer der **Datenlecksvorlagen** konfigurieren, müssen Sie der Richtlinie eine bestimmte DLP-Richtlinie zuweisen.

Mithilfe von DLP-Richtlinien können Benutzer identifiziert werden, um die Risikobewertung im Insiderrisikomanagement für DLP-Warnungen mit hohem Schweregrad für vertrauliche Informationen zu aktivieren, und sind ein wichtiger Bestandteil der Konfiguration der vollständigen Risikomanagementabdeckung in Ihrer Organisation. Weitere Informationen zum Insider risk management und zu Überlegungen zur Integration und Planung von DLP-Richtlinien finden Sie unter [Insider Risk Management Policies](insider-risk-management-policies.md#general-data-leaks).

>[!IMPORTANT]
>Stellen Sie sicher, dass Sie Folgendes abgeschlossen haben:
>
>- Sie verstehen und konfigurieren die In-Scope-Benutzer sowohl in den DLP- als auch in Den-Insider-Risikomanagementrichtlinien, um die von Ihnen zu erwartende Richtlinienabdeckung zu erzeugen.
>- Stellen Sie **sicher,** dass die Einstellung Vorfallberichte in der DLP-Richtlinie für insider risk management, die mit diesen Vorlagen verwendet wird, für Warnungen mit hohem Schweregrad konfiguriert ist.  Insider risk management alerts won't be generated from DLP policies with the **Incident reports field** set at *Low* or *Medium*.

Für die Verwendung der folgenden Richtlinienvorlagen ist eine DLP-Richtlinie erforderlich:

- Allgemeine Datenlecks
- Datenlecks nach Prioritätsbenutzern

Schrittweise [Anleitungen zum](create-test-tune-dlp-policy.md) Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie im Artikel Erstellen, Testen und Optimieren eines DLP-Richtlinienartikels. Nachdem Sie eine DLP-Richtlinie konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-priority-user-groups"></a>Konfigurieren von Benutzergruppen mit Priorität

Das Insider-Risikomanagement umfasst Unterstützung für das Zuweisen von Benutzergruppen mit Priorität zu Richtlinien, um eindeutige Risikoaktivitäten für Benutzer mit kritischen Positionen, hohe Daten- und Netzwerkzugriffsebenen oder ein früheres Risikoverhalten zu identitätsieren. Erstellen einer Benutzergruppe mit Priorität und Zuweisen von Benutzern zur Gruppenhilfebereichsrichtlinien für die eindeutigen Umstände, die von diesen Benutzern dargestellt werden.

Für die Verwendung der folgenden Richtlinienvorlagen ist eine Benutzergruppe mit Priorität erforderlich:

- Sicherheitsrichtlinienverletzungen durch Prioritätsbenutzer
- Datenlecks nach Prioritätsbenutzern

Im Artikel Erste Schritte mit Insider-Risikomanagementeinstellungen finden Sie schrittweise Anleitungen zum Erstellen einer Benutzergruppe mit Priorität. [](insider-risk-management-settings.md#priority-user-groups-preview) Nachdem Sie eine Benutzergruppe mit Priorität konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-physical-badging-connector-optional"></a>Konfigurieren des Konnektors für physisches Badging (optional)

Das Insider-Risikomanagement unterstützt das Importieren von Benutzer- und Protokolldaten von physischen Kontroll- und Zugriffsplattformen. Mit dem Konnektor für physische Badging können Sie Zugriffsdaten aus JSON-Dateien einziehen, einschließlich Benutzer-IDs, Zugriffspunkt-IDs, Zugriffszeit und -datumsangaben und Zugriffsstatus. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen Physischen Badging-Connector für Ihre Organisation konfigurieren, werden vom Insiderrisikomanagement automatisch Indikatoren aus allen Physischen Badging-Connectors entfernt. Informationen aus dem Connector für physisches Badging ergänzen andere Insiderrisikosignale, wenn alle Vorlagen für Insiderrisiken verwendet werden.

>[!IMPORTANT]
>Damit Insider-Risikomanagementrichtlinien Signaldaten im Zusammenhang mit ausscheidenden und beendeten Benutzern mit Ereignisdaten aus Ihren physischen Kontroll- und Zugriffsplattformen verwenden und korrelieren können, müssen Sie auch den Microsoft 365 konfigurieren. Wenn Sie den Connector für physisches Badging aktivieren, ohne den Microsoft 365 hr-Connector zu aktivieren, verarbeiten Insider-Risikomanagementrichtlinien nur Ereignisse für nicht autorisierten physischen Zugriff für Benutzer in Ihrer Organisation.

Schritt-für-Schritt-Anleitungen zum Konfigurieren des Konnektors für physisches [Badging](import-physical-badging-data.md) für Ihre Organisation finden Sie im Artikel Einrichten eines Connectors zum Importieren von Daten zu physischen Ausräumdaten. Nachdem Sie den Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Konfigurieren von Microsoft Defender for Endpoint (optional)

[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ist eine Unternehmensendpunktsicherheitsplattform, die Unternehmensnetzwerken dabei helfen soll, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und auf sie zu reagieren. Um eine bessere Sichtbarkeit von Sicherheitsverletzungen in Ihrer Organisation zu erhalten, können Sie Defender for Endpoint-Warnungen für Aktivitäten importieren und filtern, die in Richtlinien verwendet werden, die aus Richtlinienvorlagen für Sicherheitsverletzungen des Insiderrisikomanagements erstellt wurden.

Wenn Sie Richtlinien für Sicherheitsverletzungen erstellen, müssen Sie Microsoft Defender for Endpoint in Ihrer Organisation konfigurieren und Defender for Endpoint für die Integration von Insider-Risikomanagement im Defender Security Center aktivieren, um Sicherheitsverletzungswarnungen zu importieren. Weitere Informationen zu Anforderungen finden Sie im Artikel [Mindestanforderungen für Microsoft Defender for Endpoints.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

Im Artikel [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) finden Sie schrittweise Anleitungen zum Konfigurieren von Defender for Endpoint für insider risk management integration. Kehren Sie nach der Konfiguration von Microsoft Defender for Endpoint zu diesen Konfigurationsschritten zurück.

## <a name="step-5-configure-insider-risk-settings"></a>Schritt 5: Konfigurieren von Insiderrisikoeinstellungen

[Insider-Risikoeinstellungen](insider-risk-management-settings.md) gelten für alle Richtlinien für das Insiderrisikomanagement, unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben. Die Einstellungen werden über das Steuerelement **Insider-Risiko-Einstellungen** konfiguriert, das sich oben auf allen Registerkarten des Insider-Risikomanagements befindet. Diese Einstellungen steuern Privatsphäre, Indikatoren, Überwachungsfenster und intelligente Erkennungen.

Definieren Sie vor dem Konfigurieren einer Richtlinie die folgenden Insiderrisikoeinstellungen:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie insider risk **settings** in der oberen rechten Ecke einer beliebigen Seite aus.
2. Wählen Sie **auf** der Seite Datenschutz eine Datenschutzeinstellung zum Anzeigen von Benutzernamen für Richtlinienwarnungen aus.
3. Wählen Sie **auf der** Seite Indikatoren die Warnungsindikatoren aus, die Sie auf alle Richtlinien für Insiderrisiken anwenden möchten.

    >[!IMPORTANT]
    >Um Warnungen für riskante Aktivitäten zu erhalten, die in Ihren Richtlinien definiert sind, müssen Sie einen oder mehrere Indikatoren auswählen. Wenn Indikatoren nicht in Einstellungen konfiguriert sind, sind die Indikatoren in Insiderrisikorichtlinien nicht auswählbar.

4. Wählen Sie auf der Seite [](insider-risk-management-settings.md#policy-timeframes) Zeitrahmen **für** Richtlinien die Zeitrahmen der Richtlinie aus, die für einen Benutzer wirksam werden sollen, wenn er eine Übereinstimmung für eine Insiderrisikorichtlinie auslöst.
5. Konfigurieren Sie auf der Seite Intelligente **Erkennungen** die folgenden Einstellungen für Insiderrisikorichtlinien:
    - [Dateitypausschlüsse](insider-risk-management-settings.md#file-type-exclusions)
    - [Schwellenwerte für ungewöhnliche Dateiaktivität](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Warnungsvolumeebene](insider-risk-management-settings.md#alert-volume)
    - [Microsoft Defender for Endpoint-Warnungsstatus](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Domäneneinstellungen](insider-risk-management-settings.md#domains-preview)
6. Aktivieren Sie **auf der** Seite Warnungen exportieren den Export von Insider-Risikobenachrichtigungsinformationen mithilfe der Office 365-Verwaltungs-APIs bei Bedarf.
7. Erstellen Sie **auf der** Seite Prioritätsbenutzergruppen eine Benutzergruppe mit Priorität, und fügen Sie Benutzer hinzu, wenn sie nicht in **Schritt 3 erstellt wurden.**
8. Konfigurieren Sie **Power Automate Der** Fluss aus Insider-Risikoflussvorlagen, oder erstellen Sie einen neuen Fluss. Schrittweise [Anleitungen finden](insider-risk-management-settings.md#power-automate-flows-preview) Sie im Artikel Erste Schritte mit Insider-Risikomanagementeinstellungen.
9. Konfigurieren Sie **auf der** Seite Prioritätsressourcen prioritätsressourcen so, dass Daten aus Ihrer physischen Steuerungs- und Zugriffsplattform verwendet werden, die vom Connector für physische Badging importiert wurden. Schrittweise [Anleitungen finden](insider-risk-management-settings.md#priority-physical-assets-preview) Sie im Artikel Erste Schritte mit Insider-Risikomanagementeinstellungen.
10. Aktivieren Sie **auf Microsoft Teams** Seite die Microsoft Teams In-Insider-Risikomanagement, um automatisch ein Team für die Fall- oder Benutzerzusammenarbeit zu erstellen. Schrittweise [Anleitungen finden](insider-risk-management-settings.md#microsoft-teams-preview) Sie im Artikel Erste Schritte mit Insider-Risikomanagementeinstellungen.
11. Wählen **Sie Speichern** aus, um diese Einstellungen für Ihre Insiderrisikorichtlinien zu aktivieren.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Schritt 6: Erstellen einer Insider-Risikomanagementrichtlinie

Richtlinien für das Insider-Risikomanagement umfassen die zugewiesenen Benutzer und legen fest, welche Arten von Risikoindikatoren für Warnmeldungen konfiguriert werden. Bevor Aktivitäten Warnungen auslösen können, muss eine Richtlinie konfiguriert werden. Verwenden Sie den Richtlinien-Assistenten, um neue Insider-Risikomanagementrichtlinien zu erstellen.

1. Wechseln Sie [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider Risk **Management,** und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen **Sie Richtlinie erstellen aus,** um den Richtlinien-Assistenten zu öffnen.
3. Wählen Sie **auf der Seite** Richtlinienvorlage eine Richtlinienkategorie aus, und wählen Sie dann die Vorlage für die neue Richtlinie aus. Diese Vorlagen sind aus Bedingungen und Indikatoren, die die Risikoaktivitäten definieren, die Sie erkennen und untersuchen möchten. Überprüfen Sie die Voraussetzungen der Vorlage, lösen Sie Ereignisse und erkannte Aktivitäten aus, um zu bestätigen, dass diese Richtlinienvorlage Ihren Anforderungen entspricht.

    >[!IMPORTANT]
    >Einige Richtlinienvorlagen verfügen über Voraussetzungen, die konfiguriert werden müssen, damit die Richtlinie relevante Warnungen generiert. Wenn Sie die entsprechenden Richtlinienvoraussetzungen nicht konfiguriert haben, lesen **Sie Schritt 4** weiter oben.

4. Wählen **Sie Weiter aus,** um fortzufahren.
5. Füllen Sie **auf der Seite Name** und Beschreibung die folgenden Felder aus:
    - **Name (erforderlich):** Geben Sie einen Anzeigenamen für die Richtlinie ein. Dieser Name kann nach dem Erstellen der Richtlinie nicht mehr geändert werden.
    - **Beschreibung (optional):** Geben Sie eine Beschreibung für die Richtlinie ein.

6. Wählen **Sie Weiter aus,** um fortzufahren.
7. Wählen **Sie** auf der  Seite Benutzer und  Gruppen alle Benutzer und Gruppen oder Bestimmte Benutzer und Gruppen hinzufügen aus, um zu definieren, welche Benutzer oder Gruppen in der Richtlinie enthalten sind, oder wenn Sie eine benutzerbasierte Vorlage mit Priorität ausgewählt haben. Wählen **Sie Benutzergruppen mit Priorität hinzufügen oder bearbeiten aus.** Wenn Sie Alle Benutzer und Gruppen **aktivieren,** suchen Sie nach auslösenden Ereignissen für alle Benutzer und Gruppen in Ihrer Organisation, um mit der Zuweisung von Risikobewertungen für die Richtlinie zu beginnen. Wenn **Sie bestimmte Benutzer und Gruppen auswählen,** können Sie definieren, welche Benutzer und Gruppen der Richtlinie zugewiesen werden.
8. Wählen **Sie Weiter aus,** um fortzufahren.
9. Auf der **Seite Zu priorisierende** Inhalte können Sie (bei Bedarf) die zu priorisierenden Quellen zuweisen. Dies erhöht die Wahrscheinlichkeit, dass eine Warnung mit hohem Schweregrad für diese Quellen generiert wird. Wählen Sie eine der folgenden Optionen aus:

    - **Ich möchte SharePoint, Vertraulichkeitsbezeichnungen und/oder** Typen vertraulicher Informationen als Prioritätsinhalt angeben. Wenn Sie diese Option auswählen, werden Detailseiten im Assistenten zum Konfigurieren dieser Kanäle aktiviert.
    - **Ich möchte derzeit keine Prioritätsinhalte** angeben (Sie können dies tun, nachdem die Richtlinie erstellt wurde). Wenn Sie diese Option auswählen, werden die Kanaldetailseiten im Assistenten übersprungen.

10. Wählen **Sie Weiter aus,** um fortzufahren.

11. Wenn Sie im vorherigen Schritt SharePoint Websites, Vertraulichkeitsbezeichnungen **und/oder** Typen vertraulicher Informationen als Prioritätsinhalte angeben möchten, werden die Detailseiten für *SharePoint-Websites,* Typen vertraulicher Informationen und Vertraulichkeitsbezeichnungen *angezeigt.* Verwenden Sie diese Detailseiten, um SharePoint, Typen vertraulicher Informationen und Vertraulichkeitsbezeichnungen zu definieren, die in der Richtlinie priorisiert werden.

    - **SharePoint Websites**: Wählen Sie **SharePoint hinzufügen aus,** und wählen Sie die SharePoint, auf die Sie zugriff haben und priorisieren möchten. Beispiel: *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Vertraulicher Infotyp:** Wählen Sie **Vertraulichen Informationstyp hinzufügen aus,** und wählen Sie die Vertraulichkeitstypen aus, die Sie priorisieren möchten. Beispiel: *"US-Bankkontonummer"* und *"Kreditkartennummer"*.
    - **Vertraulichkeitsbezeichnungen:** Wählen Sie **Vertraulichkeitsbezeichnung hinzufügen aus,** und wählen Sie die Bezeichnungen aus, die Sie priorisieren möchten. Beispiel: *"Vertraulich"* und *"Geheim"*.

12. Wählen **Sie Weiter aus,** um fortzufahren.
13. Auf der **Seite Indikatoren und auslösende** Ereignisse [](insider-risk-management-settings.md#indicators) werden die Indikatoren angezeigt, die Sie auf der Seite Indikatoren für **Insiderrisikoeinstellungen**  >  **als verfügbar definiert** haben. Wenn Sie  zu Beginn des Assistenten eine Vorlage für Datenlecks ausgewählt haben, müssen Sie eine DLP-Richtlinie aus der **Dropdownliste der DLP-Richtlinie** auswählen, um Auslösenindikatoren für die Richtlinie zu aktivieren oder das integrierte Auslösenereignis auszuwählen.

    >[!IMPORTANT]
    >Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien aktivieren möchten. Sie können die Schaltfläche Indikatoren **aktivieren** im Assistenten verwenden oder Indikatoren auf der Seite **Insider risk management**  >  **Einstellungen**  >  **Policy Indicators** auswählen.

    Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie die standardrichtlinienschwelleneinstellungen für diese Indikatoren nicht verwenden möchten, deaktivieren Sie die von **Microsoft** empfohlenen Standardwerte verwenden, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein.

    - Wenn Sie mindestens einen  Office oder Geräteindikator ausgewählt haben, wählen Sie die Risikopunktzahl-Verstärkungen entsprechend aus.   Risikopunkthilfen gelten nur für ausgewählte Indikatoren.
    - Wenn Sie eine  Richtlinienvorlage für Datendiebstahl oder Datenlecks ausgewählt haben, wählen Sie mindestens eine **Sequenzerkennungsmethode** und eine **kumulative Exfiltrationserkennungsmethode** aus, die auf die Richtlinie angewendet werden soll. 

14. Wählen **Sie Weiter aus,** um fortzufahren.
15. Wählen Sie **auf der Seite Schwellenwerte** des Indikators die Option aus, um Standardindikatorschwellenwerte zu verwenden oder benutzerdefinierte Schwellenwerte für einzelne Indikatoren anzugeben. Wählen Sie für jeden Indikator die entsprechende Ebene aus, um die gewünschte Stufe von Aktivitätswarnungen zu generieren.
16. Wählen **Sie Weiter aus,** um fortzufahren.
17. Überprüfen Sie **auf** der Seite Überprüfen die Einstellungen, die Sie für die Richtlinie ausgewählt haben, sowie alle Vorschläge oder Warnungen für Ihre Auswahl. Wählen **Sie Bearbeiten** aus, um einen der Richtlinienwerte zu ändern, oder wählen Sie **Senden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Insider-Risikomanagementrichtlinie abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Benachrichtigungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf mithilfe der Anleitungen in Schritt 4 dieses Artikels oder den Schritten unter [Create a new insider risk policy](insider-risk-management-policies.md#create-a-new-policy).

Weitere Informationen zum Untersuchen von Insiderrisikowarnungen und zum **Benachrichtigungsdashboard** finden Sie unter [Insider risk management alerts](insider-risk-management-alerts.md).
