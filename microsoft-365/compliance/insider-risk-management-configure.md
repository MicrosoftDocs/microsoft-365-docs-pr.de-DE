---
title: Erste Schritte mit dem Insider-Risikomanagement
description: Konfigurieren Sie das Insider-Risikomanagement in Ihrer Organisation.
keywords: Microsoft 365, Insider-Risikomanagement, Compliance
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
ms.openlocfilehash: 8bcd9577308e31eb4bd48a5b1e0ad5748ef738e9
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256327"
---
# <a name="get-started-with-insider-risk-management"></a>Erste Schritte mit dem Insider-Risikomanagement

Verwenden Sie Insider-Risikomanagementrichtlinien, um riskante Aktivitäten und Verwaltungstools zu identifizieren, um auf Risikowarnungen in Ihrer Organisation zu reagieren. Führen Sie die folgenden Schritte aus, um voraussetzungen einzurichten und eine Richtlinie für das Insider-Risikomanagement zu konfigurieren.

> [!IMPORTANT]
> Die Microsoft 365 Insider-Risikomanagementlösung bietet eine Option auf Mandantenebene, die Kunden dabei hilft, die interne Governance auf Benutzerebene zu vereinfachen. Administratoren auf Mandantenebene können Berechtigungen einrichten, um Mitgliedern Ihrer Organisation Zugriff auf diese Lösung zu gewähren, und Datenconnectors in der Microsoft 365 Compliance Center einrichten, um relevante Daten zu importieren, um die Identifizierung potenziell riskanter Aktivitäten auf Benutzerebene zu unterstützen. Kunden bestätigen, dass Einblicke in Bezug auf das Verhalten, den Charakter oder die Leistung des einzelnen Benutzers, die in wesentlichem Zusammenhang mit der Anstellung stehen, vom Administrator berechnet und anderen Personen in der Organisation zur Verfügung gestellt werden können. Darüber hinaus bestätigen Kunden, dass sie ihre eigene vollständige Untersuchung im Zusammenhang mit dem Verhalten, dem Charakter oder der Leistung des einzelnen Benutzers durchführen müssen, die in wesentlichem Zusammenhang mit der Anstellung steht, und sich nicht nur auf Erkenntnisse aus dem Insider-Risikomanagementdienst verlassen müssen. Kunden sind allein dafür verantwortlich, den Microsoft 365 Insider-Risikomanagementdienst und alle zugehörigen Features oder Dienste in Übereinstimmung mit allen geltenden Gesetzen zu verwenden, einschließlich Gesetzen zur individuellen Benutzeridentifikation und etwaigen Abhilfemaßnahmen.

Weitere Informationen dazu, wie Richtlinien für Insider-Risiken Ihnen bei der Verwaltung von Risiken in Ihrer Organisation helfen können, finden Sie [unter Insider-Risikomanagement in Microsoft 365.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzierung

Bevor Sie mit dem Insider-Risikomanagement beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Für den Zugriff auf und die Verwendung des Insider-Risikomanagements muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 E3 Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3 Abonnement und das Add-On Microsoft 365 E5 Insider-Risikomanagement
- Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 A3 Abonnement und das Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3 Abonnement und das Add-On Microsoft 365 A5 Insider-Risikomanagement
- Microsoft 365 G5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 G3 Abonnement + das Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 G3 Abonnement und das Add-On Microsoft 365 G5 Insider Risk Management
- Office 365 E3 Abonnement + Enterprise Mobility and Security E3 + das Microsoft 365 E5 Compliance-Add-On

Benutzern, die in Insider-Risikomanagementrichtlinien enthalten sind, muss eine der oben genannten Lizenzen zugewiesen werden.

Wenn Sie über keinen vorhandenen Microsoft 365 Enterprise E5-Plan verfügen und das Insider-Risikomanagement ausprobieren möchten, können Sie Ihrem vorhandenen Abonnement [Microsoft 365 hinzufügen](/office365/admin/try-or-buy-microsoft-365) oder sich für eine Testversion von Microsoft 365 Enterprise E5 [registrieren.](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Schritt 1: Aktivieren von Berechtigungen für das Insider-Risikomanagement

> [!IMPORTANT]
> Nach dem Konfigurieren Ihrer Rollengruppen kann es bis zu 30 Minuten dauern, bis die Rollengruppenberechtigungen für zugewiesene Benutzer in Ihrer Organisation gelten.

Es gibt vier Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Insider-Risikomanagementfeatures verwendet werden. Um mit diesen Konfigurationsschritten fortzufahren, müssen Ihre Mandantenadministratoren Sie zuerst der Rollengruppe **"Insider-Risikomanagement"** oder **"Administrator für Insider-Risikomanagement"** zuweisen. Um nach der anfänglichen Konfiguration auf Insider-Risikomanagementfeatures zuzugreifen und diese zu verwalten, müssen Benutzer Mitglied mindestens einer Rollengruppe für das Insider-Risikomanagement sein.

Abhängig von der Struktur Ihres Compliance Management-Teams haben Sie Optionen, um Benutzern bestimmte Rollengruppen zuzuweisen, um unterschiedliche Gruppen von Funktionen zum Verwalten von Insiderrisiken zu verwalten. Um die Registerkarte **"Berechtigungen"** im Office 365 Security & Compliance Center anzuzeigen und Rollengruppen zu verwalten, müssen Sie der Rollengruppe *"Organisationsverwaltung"* oder der *Rollenverwaltungsrolle* zugewiesen werden. Wählen Sie bei der Konfiguration des Insider-Risikomanagements aus den folgenden Rollengruppenoptionen aus:

| **Rollengruppe** | **Rollenberechtigungen** |
| :------------- | :------------------- |
| **Insider-Risikomanagement** | Verwenden Sie diese Rollengruppe zum Verwalten des Risikomanagements für Ihr Unternehmen in einer einzigen Gruppe. Durch Hinzufügen aller Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Auditoren können Sie Berechtigungen für das Insider-Risikomanagement in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für das Insider-Risikomanagement und zugehörige Berechtigungen. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit dem Insider-Risikomanagement zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. Wenn Sie diese Konfiguration verwenden, sollten Sie sicherstellen, dass dieser Rollengruppe immer mindestens ein Benutzer zugewiesen ist, um sicherzustellen, dass Ihre Richtlinien wie erwartet funktionieren, damit der Benutzer Richtlinien erstellen und bearbeiten, Lösungseinstellungen konfigurieren und Warnungen zur Richtlinienintegrität überprüfen kann.|
| **Administrator für Insider-Risikomanagement** | Verwenden Sie diese Rollengruppe, um zunächst das Insider-Risikomanagement zu konfigurieren und später Insider-Risikoadministratoren in eine definierte Gruppe zu untergliedern. Benutzer in dieser Rollengruppe können Analyseerkenntnisse aktivieren und anzeigen sowie Richtlinien für das Insider-Risikomanagement, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Wenn Sie diese Konfiguration verwenden, sollten Sie sicherstellen, dass dieser Rollengruppe immer mindestens ein Benutzer zugewiesen ist, um sicherzustellen, dass Ihre Richtlinien wie erwartet funktionieren, damit der Benutzer Richtlinien erstellen und bearbeiten, Lösungseinstellungen konfigurieren und Warnungen zur Richtlinienintegrität überprüfen kann. |
| **Insider-Risikomanagement-Analysten** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Analysten im Falle eines Insiderrisikos fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen, Fälle, Analyseerkenntnisse und Benachrichtigungsvorlagen des Insider-Risikomanagements zugreifen und diese anzeigen. Sie können nicht auf den Inhalts-Explorer für Insider-Risiken zugreifen. |
| **Insider-Risikomanagement-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Datenprüfer für Insiderrisiken fungieren. Benutzer in dieser Rollengruppe können auf alle Warnungen, Fälle, Benachrichtigungsvorlagen und den Inhalts-Explorer für alle Fälle zugreifen. |
| **Auditoren des Insider-Risikomanagements** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die Aktivitäten des Insider-Risikomanagements überwachen. Benutzer in dieser Rollengruppe können auf das Überwachungsprotokoll für Insider-Risiken zugreifen. |

> [!NOTE]
> Diese Rollengruppen werden derzeit in Privileged Identity Management (PIM) nicht unterstützt. Weitere Informationen zu PIM finden Sie unter [Zuweisen von Azure AD-Rollen in Privileged Identity Management.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Hinzufügen von Benutzern zu einer Rollengruppe für das Insider-Risikomanagement

Führen Sie die folgenden Schritte aus, um Benutzer zu einer Rollengruppe für das Insider-Risikomanagement hinzuzufügen:

1. Melden Sie sich [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **"Berechtigungen".** Wählen Sie den Link aus, um Rollen in Office 365 anzuzeigen und zu verwalten.

3. Wählen Sie die Rollengruppe für das Insider-Risikomanagement aus, der Sie Benutzer hinzufügen möchten, und wählen Sie dann **Rollengruppe bearbeiten** aus.

4. Wählen Sie Im linken Navigationsbereich **"Mitglieder auswählen"** und dann **"Bearbeiten"** aus.

5. Wählen Sie **"Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen Sie **"Speichern"** aus, um die Benutzer der Rollengruppe hinzuzufügen. Wählen Sie **"Schließen"** aus, um die Schritte auszuführen.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Schritt 2: Aktivieren des Microsoft 365 Überwachungsprotokolls

Das Insider-Risikomanagement verwendet Microsoft 365 Überwachungsprotokolle für Benutzerinblicke und -aktivitäten, die in Richtlinien und Analyse-Insights identifiziert werden. Die Microsoft 365 Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten innerhalb Ihrer Organisation, und Richtlinien für das Insider-Risikomanagement können diese Aktivitäten verwenden, um Richtlinienerkenntnisse zu generieren.

Schritt-für-Schritt-Anleitungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md) Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal ausführen. Weitere Informationen zur Verwendung des Microsoft 365 Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Schritt 3: Aktivieren und Anzeigen von Einblicken in Insider-Risikoanalysen (optional)

Mithilfe von Insider-Risikomanagementanalysen können Sie eine Bewertung potenzieller Insider-Risiken in Ihrer Organisation durchführen, ohne Insider-Risikorichtlinien zu konfigurieren. Diese Auswertung kann Ihrer Organisation dabei helfen, potenzielle Bereiche mit höherem Benutzerrisiko zu identifizieren und den Typ und Umfang von Insider-Risikomanagement-Richtlinien zu bestimmen, die Sie konfigurieren sollten. Diese Auswertung kann Ihnen auch dabei helfen, die Anforderungen für zusätzliche Lizenzierung oder zukünftige Optimierungen vorhandener Richtlinien zu ermitteln. Analysescanergebnisse können bis zu 48 Stunden dauern, bis Einblicke als Berichte zur Überprüfung verfügbar sind. Weitere Informationen zu Analyseerkenntnissen finden Sie in den [Insider-Risikomanagementeinstellungen: Analysen (Vorschau)](insider-risk-management-settings.md#analytics-preview) und im Video zu [Insider Risk Management Analytics,](https://www.youtube.com/watch?v=5c0P5MCXNXk) um zu verstehen, wie Analysen die Identifizierung potenzieller Insider-Risiken beschleunigen und Ihnen helfen können, schnell Maßnahmen zu ergreifen.

Um die Insider-Risikoanalyse zu aktivieren, müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement",* *"Insider-Risikomanagement-Administrator"* oder Microsoft 365 *"Globaler Administrator"* sein.

Führen Sie die folgenden Schritte aus, um Insider-Risikoanalysen zu ermöglichen:

1. Wechseln [Sie](https://compliance.microsoft.com)im Microsoft 365 Compliance Center zum **Insider-Risikomanagement.**
2. Wählen Sie auf der Registerkarte **"Übersicht über** Insider-Risikomanagement" die Option **"Scan** auf **Insider-Risiken in Ihrer Organisationskarte** überprüfen" aus. Diese Aktion aktiviert die Analyseüberprüfung für Ihre Organisation. Sie können die Überprüfung auch in Ihrer Organisation aktivieren, indem Sie zu **Insider Risk Settings** Analytics  >  **(Vorschau)** navigieren und die **Benutzeraktivität Ihres Mandanten überprüfen, um potenzielle Insider-Risiken zu identifizieren.**
3. Wählen Sie im Bereich **"Analysedetails"** die Option **"Scan ausführen" aus, um die Überprüfung für Ihre Organisation zu starten.** Analysescanergebnisse können bis zu 24 Stunden dauern, bis Einblicke als Berichte zur Überprüfung verfügbar sind.

Nachdem Sie die Analyseerkenntnisse überprüft haben, wählen Sie die Insider-Risikorichtlinien aus, und konfigurieren Sie die zugehörigen Voraussetzungen, die die Insider-Risikominderungsstrategie Ihrer Organisation am besten erfüllen.

## <a name="step-4-configure-prerequisites-for-policies"></a>Schritt 4: Konfigurieren der Voraussetzungen für Richtlinien

Die meisten Insider-Risikomanagementrichtlinien verfügen über Voraussetzungen, die für Richtlinienindikatoren konfiguriert werden müssen, um relevante Aktivitätswarnungen zu generieren. Konfigurieren Sie die entsprechenden Voraussetzungen abhängig von den Richtlinien, die Sie für Ihre Organisation konfigurieren möchten.

### <a name="configure-microsoft-365-hr-connector"></a>Konfigurieren Microsoft 365 HR-Connectors

Das Insider-Risikomanagement unterstützt den Import von Benutzer- und Protokolldaten, die aus Risikomanagement- und Personalplattformen von Drittanbietern importiert wurden. Mit dem Datenkonnektor für Microsoft 365 Personalwesen (HR) können Sie Personaldaten aus CSV-Dateien abrufen, einschließlich Datumsangaben für die Beendigung des Benutzers, datumsangaben für das letzte Anstellungsverhältnis, Benachrichtigungen zu Leistungsverbesserungsplan, Leistungsüberprüfungsaktionen und Status von Arbeitsplatzebenenänderungen. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen HR-Connector für Ihre Organisation konfigurieren, ruft das Insider-Risikomanagement automatisch Indikatoren aus allen HR-Connectors ab.

Der Microsoft 365 HR-Connector ist bei Verwendung der folgenden Richtlinienvorlagen erforderlich:

- Datendiebstahl bei verlassenden Benutzern
- Verstöße gegen Sicherheitsrichtlinien durch ausscheidende Benutzer
- Verstöße gegen Sicherheitsrichtlinien durch verärgerte Benutzer
- Datenlecks durch verärgerte Benutzer

Eine schrittweise Anleitung zum Konfigurieren des Microsoft 365 HR-Connectors für Ihre Organisation finden Sie im Artikel "Einrichten eines Connectors zum Importieren von [HR-Daten".](import-hr-data.md) Nachdem Sie den HR-Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Konfigurieren von DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust)

Das Insider-Risikomanagement unterstützt die Verwendung von DLP-Richtlinien, um die absichtliche oder versehentliche Offenlegung vertraulicher Informationen für unerwünschte Parteien für DLP-Warnungen mit hohem Schweregrad zu identifizieren. Beim Konfigurieren einer Insider-Risikomanagementrichtlinie mit einer der Vorlagen für **Datenlecks** müssen Sie der Richtlinie eine bestimmte DLP-Richtlinie zuweisen.

DLP-Richtlinien helfen bei der Identifizierung von Benutzern bei der Aktivierung der Risikobewertung im Insider-Risikomanagement für DLP-Warnungen mit hohem Schweregrad für vertrauliche Informationen und sind ein wichtiger Bestandteil der Konfiguration der vollständigen Risikomanagementabdeckung in Ihrer Organisation. Weitere Informationen zum Insider-Risikomanagement und zur Integration und Planung von DLP-Richtlinien finden Sie unter ["Insider-Risikomanagementrichtlinien".](insider-risk-management-policies.md#general-data-leaks)

> [!IMPORTANT]
>Stellen Sie sicher, dass Sie Folgendes abgeschlossen haben:
>
>- Sie verstehen und konfigurieren die In-Scope-Benutzer sowohl in den DLP- als auch in der Insider-Risikomanagement-Richtlinie ordnungsgemäß, um die erwartete Richtlinienabdeckung zu erzielen.
>- Stellen Sie sicher, dass die Einstellung für **Vorfallberichte** in der DLP-Richtlinie für insider-Risikomanagement, die mit diesen Vorlagen verwendet wird, für Warnungen mit *hohem* Schweregrad konfiguriert ist. Warnungen des Insider-Risikomanagements werden nicht aus DLP-Richtlinien generiert, wobei das Feld **"Vorfallberichte"** auf *"Niedrig"* oder *"Mittel"* festgelegt ist.

Bei Verwendung der folgenden Richtlinienvorlagen ist eine DLP-Richtlinie erforderlich:

- Allgemeine Datenlecks
- Datenlecks durch prioritäre Benutzer

Eine schrittweise Anleitung zum Konfigurieren von DLP-Richtlinien für Ihre Organisation finden Sie im Artikel zum [Erstellen, Testen und Optimieren einer DLP-Richtlinie.](create-test-tune-dlp-policy.md) Nachdem Sie eine DLP-Richtlinie konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-priority-user-groups"></a>Konfigurieren von Benutzergruppen mit Priorität

Das Insider-Risikomanagement umfasst Die Unterstützung für die Zuweisung von Benutzergruppen mit Priorität zu Richtlinien, um eindeutige Risikoaktivitäten für Benutzer mit kritischen Positionen, hohen Daten- und Netzwerkzugriffsebenen oder einer früheren Verlauf des Risikoverhaltens zu identifizieren. Das Erstellen einer Benutzergruppe mit Priorität und das Zuweisen von Benutzern zu der Gruppe helfen, Richtlinien auf die von diesen Benutzern dargestellten eindeutigen Umstände zu beschränken.

Bei Verwendung der folgenden Richtlinienvorlagen ist eine Benutzergruppe mit Priorität erforderlich:

- Verstöße gegen Sicherheitsrichtlinien durch prioritäre Benutzer
- Datenlecks durch prioritäre Benutzer

Eine schrittweise Anleitung zum Erstellen einer Benutzergruppe mit Priorität finden Sie im Artikel ["Erste Schritte mit Insider-Risikomanagementeinstellungen".](insider-risk-management-settings.md#priority-user-groups-preview) Nachdem Sie eine Benutzergruppe mit Priorität konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-physical-badging-connector-optional"></a>Konfigurieren des Konnektors für physisches Fehlerhaftes (optional)

Das Insider-Risikomanagement unterstützt den Import von Benutzer- und Protokolldaten aus physischen Kontroll- und Zugriffsplattformen. Mit dem Connector für physisches Fehlerhaftes können Sie Zugriffsdaten aus JSON-Dateien abrufen, einschließlich Benutzer-IDs, Zugriffspunkt-IDs, Zugriffszeit und -datum sowie Zugriffsstatus. Diese Daten helfen bei der Entwicklung von Warnindikatoren für Insider-Risikomanagement-Richtlinien und sind ein wichtiger Bestandteil bei der Konfiguration einer vollständigen Risikomanagement-Abdeckung in Ihrer Organisation. Wenn Sie mehr als einen Konnektor für physische Übelung für Ihre Organisation konfigurieren, ruft das Insider-Risikomanagement automatisch Indikatoren aus allen physischen Konnektoren ab. Informationen vom Connector für physisches Badging ergänzen andere Insider-Risikosignale bei Verwendung aller Vorlagen für Insider-Risikorichtlinien.

> [!IMPORTANT]
> Damit Richtlinien für das Insider-Risikomanagement Signaldaten im Zusammenhang mit verlassenden und beendeten Benutzern mit Ereignisdaten von Ihren physischen Kontroll- und Zugriffsplattformen verwenden und korrelieren können, müssen Sie auch den Microsoft 365 HR-Connector konfigurieren. Wenn Sie den Connector für physisches Fehlerhaftes Aktivieren aktivieren, ohne den Microsoft 365 HR-Connector zu aktivieren, verarbeiten Richtlinien für insider-Risikomanagement nur Ereignisse für nicht autorisierten physischen Zugriff für Benutzer in Ihrer Organisation.

Schritt-für-Schritt-Anleitungen zum Konfigurieren des Konnektors für physisches Fehlerhaftes für Ihre Organisation finden Sie im Artikel ["Einrichten eines Connectors zum Importieren von physischen](import-physical-badging-data.md) Fehlerhaften Daten". Nachdem Sie den Connector konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Konfigurieren von Microsoft Defender für Endpunkt (optional)

[Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ist eine Sicherheitsplattform für Endpunkte für Unternehmen, die Unternehmensnetzwerke dabei unterstützt, fortgeschrittene Bedrohungen zu verhindern, zu erkennen, zu untersuchen und darauf zu reagieren. Um eine bessere Sichtbarkeit von Sicherheitsverstößen in Ihrer Organisation zu erhalten, können Sie Defender für Endpunkt-Warnungen für Aktivitäten importieren und filtern, die in Richtlinien verwendet werden, die aus Richtlinienvorlagen für Insider-Risikomanagement-Sicherheitsverletzungen erstellt wurden.

Wenn Sie Richtlinien für Sicherheitsverletzungen erstellen, müssen Sie Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und Defender für Endpunkt für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverstößen zu importieren. Weitere Informationen zu den Anforderungen finden Sie im Artikel ["Mindestanforderungen für Microsoft Defender für Endpunkte".](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

Eine schrittweise Anleitung zum Konfigurieren von Defender für Endpunkt für die Integration des Insider-Risikomanagements finden Sie im Artikel ["Konfigurieren erweiterter Features in Defender](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) für Endpunkt". Nachdem Sie Microsoft Defender für Endpunkt konfiguriert haben, kehren Sie zu diesen Konfigurationsschritten zurück.

## <a name="step-5-configure-insider-risk-settings"></a>Schritt 5: Konfigurieren von Einstellungen für Insider-Risiken

[Einstellungen für Insider-Risiken](insider-risk-management-settings.md) gelten für alle Richtlinien für das Insider-Risikomanagement, unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben. Die Einstellungen werden über das Steuerelement **Insider-Risiko-Einstellungen** konfiguriert, das sich oben auf allen Registerkarten des Insider-Risikomanagements befindet. Diese Einstellungen steuern Privatsphäre, Indikatoren, Überwachungsfenster und intelligente Erkennungen.

Definieren Sie vor dem Konfigurieren einer Richtlinie die folgenden Einstellungen für Insider-Risiken:

1. Wechseln [Sie im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zum **Insider-Risikomanagement,** und wählen Sie die **Einstellungen für Insider-Risiken** in der oberen rechten Ecke einer beliebigen Seite aus.
2. Wählen Sie auf der Seite **"Datenschutz"** eine Datenschutzeinstellung zum Anzeigen von Benutzernamen für Richtlinienwarnungen aus.
3. Wählen Sie auf der Seite **"Indikatoren"** die Warnungsindikatoren aus, die Sie auf alle Richtlinien für Insider-Risiken anwenden möchten.

    > [!IMPORTANT]
    > Um Warnungen für riskante Aktivitäten zu erhalten, die in Ihren Richtlinien definiert sind, müssen Sie einen oder mehrere Indikatoren auswählen. Wenn Indikatoren in Einstellungen nicht konfiguriert sind, können die Indikatoren in Insider-Risikorichtlinien nicht ausgewählt werden.

4. Wählen Sie auf der Seite **"Richtlinien-Zeitrahmen"** die [Richtlinien-Zeitrahmen](insider-risk-management-settings.md#policy-timeframes) aus, die für einen Benutzer wirksam werden sollen, wenn er eine Übereinstimmung für eine Insider-Risikorichtlinie auslöst.
5. Konfigurieren Sie auf der Seite **"Intelligente Erkennungen"** die folgenden Einstellungen für Insider-Risikorichtlinien:
    - [Dateitypausschlüsse](insider-risk-management-settings.md#file-type-exclusions)
    - [Schwellenwerte für ungewöhnliche Dateiaktivitäten](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Warnungsvolumestufe](insider-risk-management-settings.md#alert-volume)
    - [Warnungsstatus von Microsoft Defender für Endpunkt](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Domäneneinstellungen](insider-risk-management-settings.md#domains-preview)
6. Aktivieren Sie auf der Seite **"Warnungen exportieren"** bei Bedarf den Export von Informationen zu Insider-Risikowarnungen mithilfe der Office 365-Verwaltungs-APIs.
7. Erstellen Sie auf der Seite **"Prioritätsbenutzergruppen"** eine Benutzergruppe mit Priorität, und fügen Sie Benutzer hinzu, wenn sie nicht in **Schritt 3** erstellt wurden.
8. Konfigurieren **Sie** auf der Seite Power Automate Flüsse einen Fluss aus Vorlagen für Insider-Risikoflüsse, oder erstellen Sie einen neuen Fluss. Schritt-für-Schritt-Anleitungen finden Sie im Artikel ["Erste Schritte mit Insider-Risikomanagementeinstellungen".](insider-risk-management-settings.md#power-automate-flows-preview)
9. Konfigurieren Sie auf der **Seite "Prioritätsressourcen"** Prioritätsressourcen, um Daten aus Ihrer physischen Steuerungs- und Zugriffsplattform zu verwenden, die vom Connector für physisches Fehlerhaftes importiert wurden. Schritt-für-Schritt-Anleitungen finden Sie im Artikel ["Erste Schritte mit Insider-Risikomanagementeinstellungen".](insider-risk-management-settings.md#priority-physical-assets-preview)
10. Aktivieren **Sie auf** der Microsoft Teams Seite Microsoft Teams Integration in das Insider-Risikomanagement, um automatisch ein Team für die Fall- oder Benutzerzusammenarbeit zu erstellen. Schritt-für-Schritt-Anleitungen finden Sie im Artikel ["Erste Schritte mit Insider-Risikomanagementeinstellungen".](insider-risk-management-settings.md#microsoft-teams-preview)
11. Wählen Sie **"Speichern"** aus, um diese Einstellungen für Ihre Insider-Risikorichtlinien zu aktivieren.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Schritt 6: Erstellen einer Insider-Risikomanagementrichtlinie

Richtlinien für das Insider-Risikomanagement umfassen die zugewiesenen Benutzer und legen fest, welche Arten von Risikoindikatoren für Warnmeldungen konfiguriert werden. Bevor Aktivitäten Warnungen auslösen können, muss eine Richtlinie konfiguriert werden. Verwenden Sie den Richtlinien-Assistenten, um neue Richtlinien für das Insider-Risikomanagement zu erstellen.

1. Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Insider-Risikomanagement**, und wählen Sie die Registerkarte **Richtlinien** aus.
2. Wählen Sie **Richtlinie erstellen** aus, um den Richtlinien-Assistenten zu öffnen.
3. Wählen Sie auf der Seite **Richtlinienvorlage** eine Richtlinienkategorie aus, und wählen Sie dann die Vorlage für die neue Richtlinie aus. Diese Vorlagen bestehen aus Bedingungen und Indikatoren, die die zu erkennenden und zu untersuchenden Risikoaktivitäten definieren. Überprüfen Sie die Vorlagenvoraussetzungen, die auslösenden Ereignisse und die erkannten Aktivitäten, um zu bestätigen, dass diese Richtlinienvorlage Ihren Anforderungen entspricht.

    > [!IMPORTANT]
    > Für einige Richtlinienvorlagen gibt es Voraussetzungen, die für die Richtlinie konfiguriert werden müssen, damit sie relevante Warnungen generiert. Wenn Sie die anwendbaren Richtlinienvoraussetzungen nicht konfiguriert haben, sehen Sie weiter oben unter **Schritt 4** nach.

4. Wählen Sie **Weiter** aus, um fortzufahren.
5. Füllen Sie auf der Seite **Name und Beschreibung** die folgenden Felder aus:
    - **Name (erforderlich)**: Geben Sie einen Anzeigenamen für die Richtlinie ein. Dieser Name kann nach dem Erstellen der Richtlinie nicht mehr geändert werden.
    - **Beschreibung (optional)**: Geben Sie eine Beschreibung für die Richtlinie ein.

6. Wählen Sie **Weiter** aus, um fortzufahren.
7. Wählen Sie auf der Seite **Benutzer und Gruppen** die Option **Alle Benutzer und Gruppen einschließen** oder **Bestimmte Benutzer und Gruppen einschließen** aus, um zu definieren, welche Benutzer oder Gruppen in die Richtlinie einbezogen werden, oder wenn Sie eine auf prioritären Benutzern basierende Vorlage ausgewählt haben, wählen Sie **Gruppen prioritärer Benutzer hinzufügen oder bearbeiten** aus. Wenn Sie **Alle Benutzer und Gruppen einschließen** auswählen, wird nach auslösenden Ereignissen für alle Benutzer und Gruppen in Ihrer Organisation gesucht, um mit dem Zuweisen von Risikobewertungen für die Richtlinie zu beginnen. Wenn Sie **Bestimmte Benutzer und Gruppen einschließen** auswählen, können Sie definieren, welche Benutzer und Gruppen der Richtlinie zugewiesen werden sollen.
8. Wählen Sie **Weiter** aus, um fortzufahren.
9. Auf der Seite **Zu priorisierende Inhalte** können Sie (bei Bedarf) die zu priorisierenden Quellen zuweisen, wodurch sich die Wahrscheinlichkeit erhöht, dass eine Warnung mit hohem Schweregrad für diese Quellen generiert wird. Wählen Sie eine der folgenden Optionen aus:

    - **Ich möchte SharePoint-Sites, Vertraulichkeitsbezeichnungen und/oder Typen vertraulicher Informationen als Inhalte mit Priorität angeben**. Wenn Sie diese Option auswählen, werden Detailseiten im Assistenten aktiviert, um diese Kanäle zu konfigurieren.
    - **Ich möchte jetzt keine Inhalte mit Priorität angeben (Sie können dies nach der Erstellung der Richtlinie tun)**. Wenn Sie diese Option auswählen, werden die Kanaldetailseiten im Assistenten übersprungen.

10. Wählen Sie **Weiter** aus, um fortzufahren.

11. Wenn Sie im vorherigen Schritt **Ich möchte SharePoint-Sites, Vertraulichkeitsbezeichnungen und/oder Typen vertraulicher Informationen als Inhalte mit Priorität angeben** ausgewählt haben, werden die Detailseiten für *SharePoint-Sites*, *Typen vertraulicher Informationen* und *Vertraulichkeitsbezeichnungen* angezeigt. Auf diesen Detailseiten können Sie die SharePoint-Sites, die Typen vertraulicher Informationen und die Vertraulichkeitsbezeichnungen definieren, die in der Richtlinie priorisiert werden sollen.

    - **SharePoint-Sites**: Wählen Sie **SharePoint-Site hinzufügen** und dann die SharePoint-Sites aus, auf die Sie Zugriff haben und die Sie priorisieren möchten. Beispiel: *„group1@contoso.sharepoint.com/sites/group1“*.
    - **Typ vertraulicher Informationen**: Wählen Sie **Typ vertraulicher Informationen hinzufügen** und dann die Typen vertraulicher Informationen aus, die Sie priorisieren möchten. Beispiel: *„US-Bankkontonummer“* oder *„Kreditkartennummer“*.
    - **Vertraulichkeitsbezeichnungen**: Wählen Sie **Vertraulichkeitsbezeichnung hinzufügen** und dann die Vertraulichkeitsbezeichnungen aus, die Sie priorisieren möchten. Beispiel: *„Vertraulich“* oder *„Geheim“*.

12. Wählen Sie **Weiter** aus, um fortzufahren.
13. Auf der Seite **Indikatoren und auslösende Ereignisse** werden die [Indikatoren](insider-risk-management-settings.md#indicators) angezeigt, die Sie auf der Seite **Insider-Risikoeinstellungen** > **Indikatoren** als verfügbar definiert haben. Wenn Sie am Anfang des Assistenten eine *Datenleck* vorlage ausgewählt haben, müssen Sie aus der Dropdownliste **DLP-Richtlinie** eine DLP-Richtlinie auswählen, um das Auslösen von Indikatoren für die Richtlinie zu aktivieren, oder das integrierte auslösende Ereignis auswählen.

    > [!IMPORTANT]
    > Wenn Indikatoren auf dieser Seite nicht ausgewählt werden können, müssen Sie die Indikatoren auswählen, die Sie für alle Richtlinien aktivieren möchten. Sie können die Schaltfläche **Indikatoren aktivieren** im Assistenten verwenden oder Indikatoren auf der Seite **Insider-Risikomanagement** > **Einstellungen** > **Richtlinienindikatoren** auswählen.

    Wählen Sie die Indikatoren aus, die Sie auf die Richtlinie anwenden möchten. Wenn Sie für diese Indikatoren lieber nicht die Standardeinstellungen für Richtlinienschwellenwerte verwenden möchten, deaktivieren Sie **Von Microsoft empfohlene Standardschwellenwerte verwenden**, und geben Sie die Schwellenwerte für jeden ausgewählten Indikator ein.

    - Wenn Sie mindestens einen *Office*- oder *Geräte*-Indikator ausgewählt haben, wählen Sie die entsprechenden **Risikobewertungsverstärker** aus. Risikobewertungsverstärker sind nur auf ausgewählte Indikatoren anwendbar.
    - Wenn Sie eine *Datendiebstahl*- oder *Datenleck*-Richtlinienvorlage ausgewählt haben, wählen Sie eine oder mehrere **Sequenzerkennungs** methoden sowie eine Methode für die **Erkennung kumulativer Exfiltration** aus, die auf die Richtlinie angewendet werden sollen.

14. Wählen Sie **Weiter** aus, um fortzufahren.
15. Wählen Sie auf der Seite **Indikatorschwellenwerte** die Option aus, um Standardschwellenwerte für Indikatoren zu verwenden, oder die, um benutzerdefinierte Schwellenwerte für einzelne Indikatoren anzugeben. Wählen Sie für jeden Indikator die geeignete Stufe aus, um den gewünschten Schwergrad von Aktivitätswarnungen zu generieren.
16. Wählen Sie **Weiter** aus, um fortzufahren.
17. Überprüfen Sie auf der Seite **Überprüfen** die Einstellungen, die Sie für die Richtlinie ausgewählt haben, sowie alle Vorschläge oder Warnungen zu Ihrer Auswahl. Wählen Sie **Bearbeiten** aus, um die Richtlinienwerte zu ändern, oder wählen Sie **Absenden** aus, um die Richtlinie zu erstellen und zu aktivieren.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Insider-Risikomanagementrichtlinie abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Warnungen von Aktivitätsindikatoren. Konfigurieren Sie nach Bedarf zusätzliche Richtlinien mithilfe der Anleitungen in Schritt 4 dieses Artikels oder der Schritte unter ["Erstellen einer neuen Richtlinie für Insider-Risiken".](insider-risk-management-policies.md#create-a-new-policy)

Weitere Informationen zur Untersuchung von Warnungen zu Insider-Risiken und des **Warnungs-Dashboards** finden Sie unter [Insider-Risikomanagementwarnungen.](insider-risk-management-alerts.md)
