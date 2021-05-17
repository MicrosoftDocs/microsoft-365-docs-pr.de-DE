---
title: Erste Schritte mit dem Dashboard zur Verhinderung von Datenverlust
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
description: Beginnen Sie mit dem Definieren und Verwalten von Warnungen für Richtlinien zur Verhinderung von Datenverlust.
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760726"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Erste Schritte mit dem Dashboard zur Verhinderung von Datenverlust

Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) können Schutzmaßnahmen ergreifen, um die unbeabsichtigte Freigabe vertraulicher Elemente zu verhindern. Wenn eine Aktion für ein vertrauliches Element ergriffen wird, können Sie benachrichtigt werden, indem Sie Warnungen für DLP konfigurieren. In diesem Artikel erfahren Sie, wie Sie umfassende Warnungsrichtlinien definieren, die mit Ihren Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) verknüpft sind. Sie erfahren, wie Sie das Dashboard für die [DLP-Warnungsverwaltung](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) verwenden, um Warnungen, Ereignisse und zugehörige Metadaten für Verstöße gegen DLP-Richtlinien anzuzeigen.

Wenn Sie mit DLP-Warnungen neu sind, sollten Sie Informationen zum Dashboard für Benachrichtigungen zur Verhinderung von [Datenverlust lesen.](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die erforderlichen Voraussetzungen verfügen:

-   Lizenzierung für das DLP-Benachrichtigungsverwaltungsdashboard
-   Lizenzierung für Warnungskonfigurationsoptionen
-   Rollen

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Lizenzierung für das DLP-Warnungsverwaltungsdashboard

Alle berechtigten Mandanten für Office 365 DLP können auf das DLP-Warnungsverwaltungsdashboard zugreifen. Für die ersten Schritte sollten Sie berechtigt sein, Office 365 DLP für Exchange Online, SharePoint Online und OneDrive for Business. Weitere Informationen zu den Lizenzierungsanforderungen für Office 365 DLP finden Sie unter Welche Lizenzen bieten die Rechte für einen Benutzer, von dem Dienst [zu profitieren?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Kunden, die [Endpoint DLP](endpoint-dlp-learn-about.md) verwenden, die für Teams [DLP](dlp-microsoft-teams.md) berechtigt sind, sehen ihre DLP-Richtlinienwarnungen für Endpunkte und Teams im DLP-Warnungsverwaltungsdashboard.

Das **Feature für die** Inhaltsvorschau ist nur für diese Lizenzen verfügbar:

- Microsoft 365 (E5)
- Office 365 (E5)
- Advanced Compliance (E5) add on
- Microsoft 365 E5/A5 Information Protection and Governance
- Microsft 365 E5/A5 Compliance

### <a name="licensing-for-alert-configuration-options"></a>Lizenzierung für Warnungskonfigurationsoptionen

Konfiguration von Einzelereigniswarnungen: Organisationen mit einem E1-, F1- oder G1-Abonnement oder einem E3- oder **G3-Abonnement** können Nur dann Warnungsrichtlinien erstellen, wenn bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.

**Aggregierte Warnungskonfiguration:** Zum Konfigurieren aggregierter Warnungsrichtlinien basierend auf einem Schwellenwert müssen Sie eine der folgenden Lizenzierungskonfigurationen verwenden:

- Ein E5- oder G5-Abonnement
- Ein E1-, F1- oder G1-Abonnement oder ein E3- oder G3-Abonnement, das eine der folgenden Features umfasst:
    - Office 365 Advanced Threat Protection Plan 2
    - Microsoft 365 E5 Compliance
    - Microsoft 365 eDiscovery- und Audit-Add-On-Lizenz

### <a name="roles"></a>Rollen


Wenn Sie das Dashboard für die DLP-Warnungsverwaltung anzeigen oder die Konfigurationsoptionen für Warnungen in einer DLP-Richtlinie bearbeiten möchten, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

- Complianceadministrator
- Compliancedatenadministrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Sicherheitsleseberechtigter

Für den Zugriff auf das DLP-Warnungsverwaltungsdashboard benötigen Sie die:

- Verwalten von Warnungen

und eine der beiden folgenden Rollen:

- DLP-Complianceverwaltung
- View-Only DLP Compliance Management

Um auf das Feature für die Inhaltsvorschau und die Features für abgestimmte vertrauliche Inhalte und Kontexte zu zugreifen, müssen Sie Mitglied von:

- Inhalts-Explorer-Inhaltsanzeige-Rollengruppe

der die Rolle der Inhaltsanzeige für die Datenklassifizierung vorab zugewiesen ist.

## <a name="dlp-alert-configuration"></a>Konfiguration von DLP-Warnungen

Informationen zum Konfigurieren einer Warnung in Ihrer DLP-Richtlinie finden Sie unter [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).

### <a name="aggregate-event-alert-configuration"></a>Konfiguration von Aggregatereigniswarnungen

Wenn Ihre Organisation für aggregierte Warnungskonfigurationsoptionen lizenziert [ist,](#licensing-for-alert-configuration-options)werden diese Optionen angezeigt, wenn Sie eine DLP-Richtlinie erstellen oder bearbeiten.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für aggregierte Warnungskonfigurationsoptionen berechtigt sind." border="false":::

Mit dieser Konfiguration können Sie eine Richtlinie einrichten, um eine Warnung jedes Mal zu generieren, wenn eine Aktivität den Richtlinienbedingungen entspricht oder ein bestimmter Schwellenwert überschritten wird, basierend auf der Anzahl der Aktivitäten oder basierend auf dem Umfang der exfiltrierten Daten.

### <a name="single-event-alert-configuration"></a>Konfiguration einzelner Ereigniswarnungen

Wenn Ihre Organisation für Konfigurationsoptionen für einzelne Ereignisse lizenziert ist, werden diese Optionen angezeigt, wenn Sie eine [DLP-Richtlinie](#licensing-for-alert-configuration-options)erstellen oder bearbeiten. Verwenden Sie diese Option, um eine Warnung zu erstellen, die jedes Mal ausgelöst wird, wenn eine DLP-Regel übereinstimmung erfolgt.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für Konfigurationsoptionen für einzelne Ereignisse berechtigt sind." border="false":::

## <a name="investigate-a-dlp-alert"></a>Untersuchen einer DLP-Warnung

So arbeiten Sie mit dem DLP-Warnungsverwaltungsdashboard:

1. Wechseln Sie [Microsoft 365 Compliance Center](https://www.compliance.microsoft.com)zu Verhinderung von **Datenverlust.**
2. Wählen Sie die **Registerkarte Warnungen** aus, um das DLP-Benachrichtigungsdashboard anzuzeigen.
3. Wählen Sie eine Warnung aus, um Details anzuzeigen:

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot mit Warnungsdetails im DLP-Warnungsverwaltungsdashboard." border="false":::

4. Wählen Sie die **Registerkarte Ereignisse** aus, um alle Ereignisse zu sehen, die der Warnung zugeordnet sind. Sie können ein bestimmtes Ereignis auswählen, um dessen Details anzuzeigen. Eine Liste einiger verfügbarer Ereignisdetails finden Sie unter Informationen zum Dashboard für Warnungen zur Verhinderung von [Datenverlust.](dlp-alerts-dashboard-learn.md)
5. Wählen **Sie Details** aus, um die Seite **Übersicht** für die Warnung zu öffnen. Die Übersichtsseite enthält eine Zusammenfassung:
    1. von dem, was passiert ist
    1. Die Personen, die die Aktionen ausgeführt haben, die die Richtlinien übereinstimmung verursacht haben
    1. Informationen zur abgestimmten Richtlinie und mehr 

6. Wählen Sie die **Registerkarte Ereignisse** aus, um auf die zu zugreifen:
    1. Beteiligter Inhalt
    1. Übereinstimmende Typen vertraulicher Informationen
    1. Metadaten

7. Wählen Sie die **Registerkarte Typen** vertraulicher Informationen aus, um Details zu den im Inhalt erkannten Typen vertraulicher Informationen anzuzeigen. Details umfassen Vertrauen, Anzahl und den Inhalt, der dem Typ vertraulicher Informationen entspricht.

8. Nachdem Sie die Warnung untersucht  haben, kehren Sie zur Registerkarte Übersicht zurück, auf der Sie die Triage verwalten und die Disposition der Warnung verwalten und Kommentare hinzufügen können.

- Um den Verlauf der Workflowverwaltung zu sehen, wählen Sie **Verwaltungsprotokoll aus.**
- Nachdem Sie die erforderliche Aktion für die Warnung ergreifen, legen Sie den Status der Warnung auf **Resolved .**

## <a name="see-also"></a>Siehe auch

- [Informationen zu Warnungen zur Verhinderung von Datenverlust und zum Benachrichtigungsdashboard](dlp-alerts-dashboard-learn.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)