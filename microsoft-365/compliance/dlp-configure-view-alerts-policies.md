---
title: Konfigurieren und Anzeigen von Warnungen für DLP-Richtlinien (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
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
description: Hier erfahren Sie, wie Sie Warnungen für DLP-Richtlinien definieren und verwalten.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651460"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>Konfigurieren und Anzeigen von Warnungen für DLP-Richtlinien (Vorschau)

In diesem Artikel erfahren Sie, wie Sie umfangreiche Warnungsrichtlinien definieren, die mit den DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) verknüpft sind. In diesem Artikel erfahren Sie, wie Sie mithilfe des neuen DLP Alert Management-Dashboards im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) Warnungen, Ereignisse und zugehörige Metadaten für DLP-Richtlinienverletzungen anzeigen können.

## <a name="features"></a>Features

Die folgenden Features sind Teil dieser Vorschau:

-   **DLP Alert Management-Dashboard**: im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zeigt dieses Dashboard Warnungen für DLP-Richtlinien an, die für die folgenden Arbeitslasten erzwungen werden:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Geräte
-   **Erweiterte Warnungs Konfigurationsoptionen**: Diese Optionen sind Bestandteil des DLP-Richtlinien Erstellungs Flusses. Verwenden Sie diese, um umfangreiche Warnungskonfigurationen zu erstellen. Sie können eine einzelne Ereignis Warnung oder eine aggregierte Warnung basierend auf der Anzahl der Ereignisse oder der Größe der Daten, die durchgesickert sind, erstellen.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die erforderlichen Voraussetzungen verfügen:

-   Lizenzierung für das Verwaltungs Dashboard für DLP-Warnungen
-   Lizenzierung für Warnungs Konfigurationsoptionen
-   Rollen

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Lizenzierung für das DLP-Warnungs Verwaltungs Dashboard

Alle berechtigten Mandanten für Office 365 DLP können auf das neue DLP Alert Management Dashboard zugreifen. Für die ersten Schritte sollten Sie für Exchange Online, SharePoint Online und OneDrive für Unternehmen Office 365 DLP in Betracht kommen. Weitere Informationen zu den Lizenzierungsanforderungen für Office 365 DLP finden Sie unter [welche Lizenzen bieten die Rechte, damit ein Benutzer vom Dienst profitieren kann?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Kunden, die an der öffentlichen [Endpunkt-DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) -Vorschau teilnehmen oder für [Teams DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) geeignet sind, sehen ihre Endpunkt-DLP-Richtlinienwarnungen und DLP-Richtlinienwarnungen für Teams im DLP-Warnungs Verwaltungs Dashboard.

### <a name="licensing-for-alert-configuration-options"></a>Lizenzierung für Warnungs Konfigurationsoptionen

-   **Konfiguration mit einem einzelnen Ereignis**: Organisationen, die über ein E1-, F1-oder G1-Abonnement oder ein E3-oder G3-Abonnement verfügen, können Warnungsrichtlinien nur dann erstellen, wenn bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.
-   **Aggregierte Warnungskonfiguration**: um aggregierte Warnungsrichtlinien basierend auf einem Schwellenwert zu konfigurieren, müssen Sie eine der folgenden Konfigurationen haben:
    -   Ein E5-oder G5-Abonnement
    -   Ein E1-, F1-oder G1-Abonnement oder ein E3-oder G3-Abonnement mit einem der folgenden Features:
        -   Office 365 Advanced Threat Protection Plan 2
        -   Microsoft 365 E5 Compliance
        -   Microsoft 365 eDiscovery-und Audit-Add-on-Lizenz

### <a name="roles"></a>Rollen

Wenn Sie das DLP-Warnungs Verwaltungs Dashboard anzeigen oder die Warnungs Konfigurationsoptionen in einer DLP-Richtlinie bearbeiten möchten, müssen Sie Mitglied einer dieser Rollengruppen sein:

-   Complianceadministrator
-   Kompatibilitätsdaten Administrator
-   Sicherheitsadministrator
-   Sicherheitsoperator
-   Sicherheitsleseberechtigter

Um auf das DLP-Warnungs Verwaltungs Dashboard zuzugreifen, benötigen Sie die Rolle "Warnungen verwalten" und eine der folgenden Rollen:

-   DLP-Konformitätsverwaltung
-   View-Only DLP-Konformitätsverwaltung

## <a name="alert-configuration-experience"></a>Warnungs Konfigurations Erfahrung

Wenn Sie für [aggregierte Warnungs Konfigurationsoptionen](#licensing-for-alert-configuration-options)berechtigt sind, sehen Sie die folgenden Optionen Inline in der Erstellungsumgebung für DLP-Richtlinien.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot mit Optionen für vorfallberichte für Benutzer, die für aggregierte Warnungs Konfigurationsoptionen berechtigt sind." border="false":::

Sie können diese Warnungs Konfigurationsoptionen verwenden, um eine Einstellung zu konfigurieren, die festlegt, wie oft eine DLP-Regelübereinstimmung auftreten kann, bevor eine Warnung ausgelöst wird. Mit dieser Konfiguration können Sie eine Richtlinie einrichten, um eine Warnung zu generieren, sobald eine Aktivität mit den Richtlinienbedingungen übereinstimmt oder wenn ein bestimmter Schwellenwert basierend auf der Anzahl der Aktivitäten oder basierend auf dem Volumen der extrahiert-Daten überschritten wird.

Wenn Sie für [Konfigurationsoptionen mit einem einzelnen Ereignis](#licensing-for-alert-configuration-options)in Frage kommen, wird in der DLP-Richtlinien Erstellungsumgebung die folgende Warnungs Konfigurationsoption angezeigt. Verwenden Sie diese Option, um eine Warnung zu erstellen, die jedes Mal ausgelöst wird, wenn eine DLP-Regelübereinstimmung aufgrund einer Benutzeraktivität auftritt.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot mit Optionen für vorfallberichte für Benutzer, die für aggregierte Warnungs Konfigurationsoptionen berechtigt sind." border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP-Warnungs Verwaltungs Dashboard

So arbeiten Sie mit dem DLP Alert Management-Dashboard:

1.  Wechseln Sie im [Microsoft 365 Compliance Center](https://www.compliance.microsoft.com)zu **Verhinderung von Datenverlust**.

2.  Wählen Sie die Registerkarte **Warnungen** aus, um das DLP-Warnungs Dashboard anzuzeigen.

    -   Wählen Sie Filter aus, um die Liste der Warnungen zu verfeinern. Wählen Sie **Spalten anpassen** aus, um die Eigenschaften aufzulisten, die angezeigt werden sollen. Sie können die Benachrichtigungen auch in aufsteigender oder absteigender Reihenfolge in einer beliebigen Spalte sortieren.
    -   Wählen Sie eine Warnung aus, um Details anzuzeigen:

        :::image type="content" source="../media/alert-details.png" alt-text="Screenshot mit Optionen für vorfallberichte für Benutzer, die für aggregierte Warnungs Konfigurationsoptionen berechtigt sind." border="false":::

1.  Wählen Sie die Registerkarte **Ereignisse** aus, um alle der Warnung zugeordneten Ereignisse anzuzeigen. Sie können ein bestimmtes Ereignis auswählen, um seine Details anzuzeigen.
    In der folgenden Tabelle sind einige der Ereignisdetails aufgeführt.
    
    | Kategorie          | Eigenschaftenname                 | Beschreibung                                                                | Zutreffende Ereignistypen                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Ereignisdetails*||
    |      | Id                            | Dem Ereignis zugeordnete eindeutige ID                                        | Alle Ereignisse                               |
    |                   | Standort                      | Arbeitsauslastung, in der das Ereignis erkannt wurde                                      | Alle Ereignisse                               |
    |                   | Zeitpunkt der Aktivität              | Zeitpunkt der Benutzeraktivität, die die DLP-Verletzung verursacht hat                    | Alle Ereignisse                               |
    |*Betroffene Entitäten*||
    |  | Benutzer                          | Benutzer, der die DLP-Verletzung verursacht hat                                          | Alle Ereignisse                               |
    |                   | Hostname                      | Hostname des Computers, auf dem die DLP-Verletzung erkannt wurde              | Devices-Ereignisse                           |
    |                   | IP-Adresse                    | IP-Adresse des Computers                                                  | Devices-Ereignisse                           |
    |                   | Dateipfad                     | Absoluter Pfad der Datei, die an der Verletzung beteiligt ist                        | SharePoint-, OneDrive-und Devices-Ereignisse |
    |                   | E-Mail-Empfänger              | Empfänger der e-Mail, die die DLP-Richtlinie verletzt hat                       | Exchange-Ereignisse                          |
    |                   | E-Mail-Betreff                 | Betreff der e-Mail, die die DLP-Richtlinie verletzt hat                          | Exchange-Ereignisse                          |
    |                   | E-Mail-Anlagen             | Namen der Anlagen in der e-Mail, die die DLP-Richtlinie verletzen         | Exchange-Ereignisse                          |
    |                   | Websitebesitzer                    | Name des Websitebesitzers                                                     | SharePoint-und OneDrive-Ereignisse           |
    |                   | Website-URL                      | Vollständige URL der SharePoint-oder OneDrive-Website                                | SharePoint-und OneDrive-Ereignisse           |
    |                   | Datei erstellt                  | Zeitpunkt der Dateierstellung                                                      | SharePoint-und OneDrive-Ereignisse           |
    |                   | Datei zuletzt geändert            | Zeitpunkt der letzten Änderung der Datei                                  | SharePoint-und OneDrive-Ereignisse           |
    |                   | Dateigröße                     | Größe der Datei                                                           | SharePoint-und OneDrive-Ereignisse           |
    |                   | Dateibesitzer                    | Besitzer der Datei                                                          | SharePoint-und OneDrive-Ereignisse           |
    |*Richtliniendetails*||
    |     | DLP-Richtlinie abgeglichen            | Name der DLP-Richtlinie, die abgeglichen wurde                                    | Alle Ereignisse                               |
    |                   | Regelübereinstimmung                  | Name der DLP-Regel in der DLP-Richtlinie, die abgeglichen wurde                    | Alle Ereignisse                               |
    |                   | Vertrauliche Informationstypen erkannt | Vertrauliche Informationstypen, die als Teil der DLP-Richtlinie erkannt wurden | Alle Ereignisse                               |
    |                   | Durchgeführte Aktionen                 | Im Rahmen der übereinstimmenden DLP-Richtlinie ausgeführte Aktionen                          | Alle Ereignisse                               |
    |                   | Richtlinie für Benutzer overrode          | Gibt an, ob der Benutzer die Richtlinie über den richtlinientipp überlaufen hat                | Alle Ereignisse                               |
    |                   | Ausrichtungs Text außer Kraft setzen   | Begründung zum außer Kraft setzen des Richtlinien Tipps                          | Alle Ereignisse                               |
    
1.  Wählen Sie die Registerkarte **vertrauliche Informationstypen** aus, um Details zu den im Inhalt gefundenen Typen vertraulicher Informationen anzuzeigen. Details umfassen Vertrauen und Anzahl.

2.  Nachdem Sie die Warnung überprüft haben, wählen Sie **Alert verwalten** aus, um den Status zu ändern (**aktiv**, unter **Suchen**, **entlassen**oder **aufgelöst**). Sie können auch Kommentare hinzufügen und die Benachrichtigung einer Person in Ihrer Organisation zuweisen.

    -   Um den Verlauf der Workflowverwaltung anzuzeigen, wählen Sie **Verwaltungsprotokoll**aus.
    -   Nachdem Sie die erforderliche Aktion für die Warnung ausgeführt haben, legen Sie den Status der Warnung auf **aufgelöst**fest.
