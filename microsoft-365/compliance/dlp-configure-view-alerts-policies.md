---
title: Benachrichtigungen für DLP-Richtlinien konfigurieren und anzeigen (Preview)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Warnungen für DLP-Richtlinien definieren und verwalten.
ms.openlocfilehash: 0594cee5208049aef16dee6fa03954faae2a1cdd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917861"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>Konfigurieren und Anzeigen von Warnungen für DLP-Richtlinien (Vorschau)

In diesem Artikel erfahren Sie, wie Sie umfassende Warnungsrichtlinien definieren, die mit Ihren Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) verknüpft sind. Sie erfahren, wie Sie das neue DLP-Warnungsverwaltungsdashboard im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) verwenden, um Warnungen, Ereignisse und zugehörige Metadaten für Verstöße gegen DLP-Richtlinien anzuzeigen.

## <a name="features"></a>Features

Die folgenden Features sind Teil dieser Vorschau:

-   **DLP-Dashboard** für die Warnungsverwaltung: Im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zeigt dieses Dashboard Warnungen für DLP-Richtlinien an, die für die folgenden Arbeitsauslastungen erzwungen werden:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Geräte
-   **Erweiterte Konfigurationsoptionen für Warnungen:** Diese Optionen sind Teil des DLP-Richtlinienerstellungsflusses. Verwenden Sie sie, um umfassende Warnungskonfigurationen zu erstellen. Sie können eine Benachrichtigung mit einem einzelnen Ereignis oder eine aggregierte Warnung basierend auf der Anzahl der Ereignisse oder der Größe der datenlecks erstellt.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die erforderlichen Voraussetzungen verfügen:

-   Lizenzierung für das DLP-Benachrichtigungsverwaltungsdashboard
-   Lizenzierung für Warnungskonfigurationsoptionen
-   Rollen

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Lizenzierung für das DLP-Warnungsverwaltungsdashboard

Alle berechtigten Mandanten für Office 365 DLP können auf das neue DLP-Warnungsverwaltungsdashboard zugreifen. Für die ersten Schritte sollten Sie für Office 365 DLP für Exchange Online, SharePoint Online und OneDrive for Business berechtigt sein. Weitere Informationen zu den Lizenzierungsanforderungen für Office 365 DLP finden Sie unter Welche Lizenzen bieten die Rechte für einen Benutzer, von dem [Dienst zu profitieren?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Kunden, die an der öffentlichen [Endpoint DLP-Vorschau](./endpoint-dlp-learn-about.md?view=o365-worldwide) teilnehmen oder für [Teams DLP](./dlp-microsoft-teams.md?view=o365-worldwide) berechtigt sind, werden ihre DLP-Richtlinienwarnungen und Teams -DLP-Richtlinienwarnungen im DLP-Warnungsverwaltungsdashboard angezeigt.

### <a name="licensing-for-alert-configuration-options"></a>Lizenzierung für Warnungskonfigurationsoptionen

-   Konfiguration von Einzelereigniswarnungen: Organisationen mit einem E1-, F1- oder G1-Abonnement oder einem E3- oder **G3-Abonnement** können Nur dann Warnungsrichtlinien erstellen, wenn bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.
-   **Aggregierte Warnungskonfiguration:** Zum Konfigurieren aggregierter Warnungsrichtlinien basierend auf einem Schwellenwert müssen Sie über eine der folgenden Konfigurationen verfügen:
    -   Ein E5- oder G5-Abonnement
    -   Ein E1-, F1- oder G1-Abonnement oder ein E3- oder G3-Abonnement, das eine der folgenden Features umfasst:
        -   Office 365 Advanced Threat Protection Plan 2
        -   Microsoft 365 E5 Compliance
        -   Microsoft 365 eDiscovery- und Audit-Add-On-Lizenz

### <a name="roles"></a>Rollen

Wenn Sie das Dashboard für die DLP-Warnungsverwaltung anzeigen oder die Konfigurationsoptionen für Warnungen in einer DLP-Richtlinie bearbeiten möchten, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

-   Complianceadministrator
-   Compliancedatenadministrator
-   Sicherheitsadministrator
-   Sicherheitsoperator
-   Sicherheitsleseberechtigter

Für den Zugriff auf das DLP-Warnungsverwaltungsdashboard benötigen Sie die Rolle Benachrichtigungen verwalten und eine der folgenden Rollen:

-   DLP-Complianceverwaltung
-   View-Only DLP Compliance Management

## <a name="alert-configuration-experience"></a>Warnungskonfigurationserfahrung

Wenn Sie für aggregierte Konfigurationsoptionen für Warnungen [berechtigt](#licensing-for-alert-configuration-options)sind, werden die folgenden Optionen inline in der DLP-Richtlinienerstellungsfunktion angezeigt.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für aggregierte Warnungskonfigurationsoptionen berechtigt sind." border="false":::

Sie können diese Warnungskonfigurationsoptionen verwenden, um eine Einstellung zu konfigurieren, die definiert, wie oft eine DLP-Regel übereinstimmung auftreten kann, bevor eine Warnung ausgelöst wird. Mit dieser Konfiguration können Sie eine Richtlinie einrichten, um eine Warnung jedes Mal zu generieren, wenn eine Aktivität den Richtlinienbedingungen entspricht oder ein bestimmter Schwellenwert überschritten wird, basierend auf der Anzahl der Aktivitäten oder basierend auf dem Umfang der exfiltrierten Daten.

Wenn Sie für [](#licensing-for-alert-configuration-options)Konfigurationsoptionen für einzelne Ereignisse berechtigt sind, wird die folgende Warnungskonfigurationsoption in der DLP-Richtlinienerstellungserfahrung angezeigt. Verwenden Sie diese Option, um eine Warnung zu erstellen, die jedes Mal ausgelöst wird, wenn eine DLP-Regel übereinstimmung aufgrund einer Benutzeraktivität erfolgt.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für Konfigurationsoptionen für einzelne Ereignisse berechtigt sind." border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP-Warnungsverwaltungsdashboard

So arbeiten Sie mit dem DLP-Warnungsverwaltungsdashboard:

1.  Wechseln Sie [im Microsoft 365 Compliance Center](https://www.compliance.microsoft.com)zu Verhinderung von **Datenverlust.**

2.  Wählen Sie die **Registerkarte Warnungen** aus, um das DLP-Benachrichtigungsdashboard anzuzeigen.

    -   Wählen Sie Filter aus, um die Liste der Warnungen zu verfeinern. Wählen **Sie Spalten anpassen** aus, um die Eigenschaften auflisten, die Angezeigt werden sollen. Sie können die Warnungen auch in aufsteigender oder absteigender Reihenfolge in einer beliebigen Spalte sortieren.
    -   Wählen Sie eine Warnung aus, um Details anzuzeigen:

        :::image type="content" source="../media/alert-details.png" alt-text="Screenshot mit Warnungsdetails im DLP-Warnungsverwaltungsdashboard." border="false":::

1.  Wählen Sie die **Registerkarte Ereignisse** aus, um alle Ereignisse zu sehen, die der Warnung zugeordnet sind. Sie können ein bestimmtes Ereignis auswählen, um dessen Details anzuzeigen.
    In der folgenden Tabelle sind einige der Ereignisdetails aufgeführt.
    
    | Kategorie          | Eigenschaftenname                 | Beschreibung                                                                | Anwendbare Ereignistypen                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Ereignisdetails*||
    |      | Id                            | Eindeutige ID, die dem Ereignis zugeordnet ist                                        | Alle Ereignisse                               |
    |                   | Speicherort                      | Arbeitsauslastung, in der das Ereignis erkannt wurde                                      | Alle Ereignisse                               |
    |                   | Zeitpunkt der Aktivität              | Zeitpunkt der Benutzeraktivität, die die DLP-Verletzung verursacht hat                    | Alle Ereignisse                               |
    |*Betroffene Entitäten*||
    |  | Benutzer                          | Benutzer, der die DLP-Verletzung verursacht hat                                          | Alle Ereignisse                               |
    |                   | Hostname                      | Hostname des Computers, auf dem die DLP-Verletzung erkannt wurde              | Geräteereignisse                           |
    |                   | IP-Adresse                    | IP-Adresse des Computers                                                  | Geräteereignisse                           |
    |                   | Dateipfad                     | Absoluter Pfad der Datei, die an der Verletzung beteiligt ist                        | SharePoint-, OneDrive- und #A0 |
    |                   | E-Mail-Empfänger              | Empfänger der E-Mails, die gegen die DLP-Richtlinie verstoßen haben                       | Exchange-Ereignisse                          |
    |                   | E-Mail-Betreff                 | Betreff der E-Mail, die gegen die DLP-Richtlinie verstoßen hat                          | Exchange-Ereignisse                          |
    |                   | E-Mail-Anlagen             | Namen der Anlagen in der E-Mail, die gegen die DLP-Richtlinie verstoßen haben         | Exchange-Ereignisse                          |
    |                   | Websitebesitzer                    | Name des Websitebesitzers                                                     | #A0 und #A1           |
    |                   | Website-URL                      | Vollständige URL der SharePoint- oder #A0                                | #A0 und #A1           |
    |                   | Datei erstellt                  | Zeitpunkt der Dateierstellung                                                      | #A0 und #A1           |
    |                   | Zuletzt geänderte Datei            | Zeitpunkt der letzten Änderung der Datei                                  | #A0 und #A1           |
    |                   | Dateigröße                     | Größe der Datei                                                           | #A0 und #A1           |
    |                   | Dateibesitzer                    | Besitzer der Datei                                                          | #A0 und #A1           |
    |*Richtliniendetails*||
    |     | Übereinstimmung der DLP-Richtlinie            | Name der übereinstimmende DLP-Richtlinie                                    | Alle Ereignisse                               |
    |                   | Regel wurde übereinstimmend                  | Name der DLP-Regel in der übereinstimmende DLP-Richtlinie                    | Alle Ereignisse                               |
    |                   | Typen vertraulicher Informationen erkannt | Typen vertraulicher Informationen, die als Teil der DLP-Richtlinie erkannt wurden | Alle Ereignisse                               |
    |                   | Durchgeführte Aktionen                 | Aktionen, die als Teil der übereinstimmende DLP-Richtlinie ergriffen werden                          | Alle Ereignisse                               |
    |                   | Benutzerüberrodungsrichtlinie          | Gibt an, ob der Benutzer die Richtlinie über den Richtlinientipp übernimmt                | Alle Ereignisse                               |
    |                   | Außerkraftsetzung des Begründungstexts   | Zur Außerkraftsetzung des Richtlinientipps bereitgestellte Begründung                          | Alle Ereignisse                               |
    
1.  Wählen Sie die **Registerkarte Typen** vertraulicher Informationen aus, um Details zu den im Inhalt erkannten Typen vertraulicher Informationen anzuzeigen. Details umfassen Vertrauen und Anzahl.

2.  Nachdem Sie die Warnung untersucht haben, wählen Sie **Warnung** verwalten aus, um den Status zu ändern (**Aktiv**, **Untersuchen**, **Verworfen** oder **Aufgelöst**). Sie können auch Kommentare hinzufügen und die Warnung einer Person in Ihrer Organisation zuweisen.

    -   Um den Verlauf der Workflowverwaltung zu sehen, wählen Sie **Verwaltungsprotokoll aus.**
    -   Nachdem Sie die erforderliche Aktion für die Warnung ergreifen, legen Sie den Status der Warnung auf **Resolved .**