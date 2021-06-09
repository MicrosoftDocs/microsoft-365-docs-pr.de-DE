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
description: Erste Schritte mit dem Definieren und Verwalten von Warnungen für Richtlinien zur Verhinderung von Datenverlust.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843866"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Erste Schritte mit dem Dashboard zur Verhinderung von Datenverlust

Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) können Schutzmaßnahmen ergreifen, um die unbeabsichtigte Freigabe vertraulicher Elemente zu verhindern. Wenn eine Aktion für ein vertrauliches Element ausgeführt wird, können Sie benachrichtigt werden, indem Sie Warnungen für DLP konfigurieren. In diesem Artikel erfahren Sie, wie Sie umfassende Warnungsrichtlinien definieren, die mit Ihren Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) verknüpft sind. Sie sehen, wie Sie das Dashboard für die Verwaltung von [DLP-Warnungen](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) verwenden, um Warnungen, Ereignisse und zugehörige Metadaten für DLP-Richtlinienverstöße anzuzeigen.

Wenn Sie noch keine Informationen zu DLP-Warnungen haben, sollten Sie [sich das Dashboard mit Warnungen zur Verhinderung von Datenverlust](dlp-alerts-dashboard-learn.md) ansehen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über die erforderlichen Voraussetzungen verfügen:

-   Lizenzierung für das Dashboard für die Verwaltung von DLP-Warnungen
-   Lizenzierung für Konfigurationsoptionen für Warnungen
-   Rollen

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Lizenzierung für das Dashboard für die DLP-Warnungsverwaltung

Alle berechtigten Mandanten für Office 365 DLP können auf das Dashboard zur Verwaltung von DLP-Warnungen zugreifen. Um zu beginnen, sollten Sie für Office 365 DLP für Exchange Online, SharePoint Online und OneDrive for Business berechtigt sein. Weitere Informationen zu den Lizenzierungsanforderungen für Office 365 DLP finden Sie unter [Welche Lizenzen bieten einem Benutzer die Rechte, von dem Dienst zu profitieren?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)

Kunden, die [Endpunkt-DLP](endpoint-dlp-learn-about.md) verwenden, die für [Teams DLP](dlp-microsoft-teams.md) berechtigt sind, sehen ihre Endpunkt-DLP-Richtlinienwarnungen und Teams DLP-Richtlinienwarnungen im DLP-Warnungsverwaltungsdashboard.

Das Feature für die **Inhaltsvorschau** ist nur für diese Lizenzen verfügbar:

- Microsoft 365 (E5)
- Office 365 (E5)
- Advanced Compliance (E5) add on
- Microsoft 365 E5/A5 Information Protection and Governance
- Microsft 365 E5/A5 Compliance

### <a name="licensing-for-alert-configuration-options"></a>Lizenzierung für Konfigurationsoptionen für Warnungen

Konfiguration von Warnungen für einzelne Ereignisse: Organisationen, die über ein E1-, F1- oder G1-Abonnement oder ein E3- oder **G3-Abonnement** verfügen, können Warnungsrichtlinien nur erstellen, wenn bei jedem Auftreten einer Aktivität eine Warnung ausgelöst wird.

**Aggregierte Warnungskonfiguration:** Um aggregierte Warnungsrichtlinien basierend auf einem Schwellenwert zu konfigurieren, müssen Sie eine der folgenden Lizenzierungskonfigurationen verwenden:

- Ein E5- oder G5-Abonnement
- Ein E1-, F1- oder G1-Abonnement oder ein E3- oder G3-Abonnement, das eine der folgenden Features enthält:
    - Office 365 Advanced Threat Protection Plan 2
    - Microsoft 365 E5 Compliance
    - Microsoft 365 eDiscovery- und Audit-Add-On-Lizenz

### <a name="roles"></a>Rollen


Wenn Sie das Dashboard für die Verwaltung von DLP-Warnungen anzeigen oder die Konfigurationsoptionen für Warnungen in einer DLP-Richtlinie bearbeiten möchten, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

- Complianceadministrator
- Compliancedatenadministrator
- Sicherheitsadministrator
- Sicherheitsoperator
- Sicherheitsleseberechtigter

Für den Zugriff auf das Dashboard für die DLP-Warnungsverwaltung benötigen Sie Folgendes:

- Verwalten von Warnungen

und eine der beiden folgenden Rollen:

- DLP-Complianceverwaltung
- View-Only DLP Compliance Management

Um auf das Feature "Inhaltsvorschau" und die übereinstimmenden vertraulichen Inhalte und Kontextfeatures zuzugreifen, müssen Sie Mitglied der folgenden Funktionen sein:

- Rollengruppe "Inhalts-Viewer" des Inhalts-Explorers

die die Rolle der Inhaltsanzeige für die Datenklassifizierung vorab zugewiesen hat.

## <a name="dlp-alert-configuration"></a>DLP-Warnungskonfiguration

Informationen zum Konfigurieren einer Warnung in Ihrer DLP-Richtlinie finden Sie unter ["Wo sie mit der Verhinderung von Datenverlust beginnen können".](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)

### <a name="aggregate-event-alert-configuration"></a>Konfiguration der Aggregatereigniswarnung

Wenn Ihre Organisation für [aggregierte Konfigurationsoptionen](#licensing-for-alert-configuration-options)für Warnungen lizenziert ist, werden diese Optionen angezeigt, wenn Sie eine DLP-Richtlinie erstellen oder bearbeiten.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für aggregierte Konfigurationsoptionen für Warnungen berechtigt sind." border="false":::

Mit dieser Konfiguration können Sie eine Richtlinie einrichten, um eine Warnung jedes Mal zu generieren, wenn eine Aktivität den Richtlinienbedingungen entspricht oder wenn ein bestimmter Schwellenwert überschritten wird, basierend auf der Anzahl der Aktivitäten oder basierend auf dem Volumen der exfiltrierten Daten.

### <a name="single-event-alert-configuration"></a>Konfiguration einzelner Ereigniswarnungen

Wenn Ihre Organisation für Konfigurationsoptionen für Warnungen mit einem einzelnen Ereignis lizenziert ist, werden diese Optionen angezeigt, wenn Sie eine [DLP-Richtlinie](#licensing-for-alert-configuration-options)erstellen oder bearbeiten. Verwenden Sie diese Option, um eine Warnung zu erstellen, die jedes Mal ausgelöst wird, wenn eine DLP-Regelüberstimmung auftritt.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot mit Optionen für Vorfallberichte für Benutzer, die für Konfigurationsoptionen für Einzelne-Ereignisse-Warnungen berechtigt sind." border="false":::

## <a name="investigate-a-dlp-alert"></a>Untersuchen einer DLP-Warnung

So arbeiten Sie mit dem Dashboard für die DLP-Warnungsverwaltung:

1. Wechseln [Sie](https://www.compliance.microsoft.com)im Microsoft 365 Compliance Center zu **"Verhinderung von Datenverlust".**
2. Wählen Sie die Registerkarte **"Warnungen"** aus, um das Dashboard für DLP-Warnungen anzuzeigen.
3. Wählen Sie eine Warnung aus, um Details anzuzeigen:

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot mit Warnungsdetails im Dashboard für die DLP-Warnungsverwaltung." border="false":::

4. Wählen Sie die Registerkarte **"Ereignisse"** aus, um alle der Warnung zugeordneten Ereignisse anzuzeigen. Sie können ein bestimmtes Ereignis auswählen, um dessen Details anzuzeigen. Eine Liste der verfügbaren Ereignisdetails finden Sie unter ["Informationen zum Dashboard "Warnungen zur Verhinderung von Datenverlust".](dlp-alerts-dashboard-learn.md)
5. Wählen Sie **Details** aus, um die **Übersichtsseite** für die Warnung zu öffnen. Die Übersichtsseite enthält eine Zusammenfassung:
    1. was passiert ist
    1. Wer die Aktionen ausgeführt hat, die die Richtlinienüberstimmung verursacht haben
    1. Informationen zur übereinstimmende Richtlinie und mehr 

6. Wählen Sie die Registerkarte **"Ereignisse"** aus, um auf Folgendes zuzugreifen:
    1. Beteiligter Inhalt
    1. Übereinstimmende Typen vertraulicher Informationen
    1. Metadaten

7. Wählen Sie die Registerkarte **"Typen vertraulicher Informationen" aus,** um Details zu den im Inhalt erkannten Typen vertraulicher Informationen anzuzeigen. Details umfassen Konfidenz, Anzahl und den Inhalt, der dem Typ vertraulicher Informationen entspricht.

8. Kehren Sie nach der Untersuchung der Warnung zur Registerkarte **"Übersicht"** zurück, auf der Sie die Triage verwalten und die Disposition der Warnung verwalten und Kommentare hinzufügen können.

- Um den Verlauf der Workflowverwaltung anzuzeigen, wählen Sie **Verwaltungsprotokoll** aus.
- Nachdem Sie die erforderliche Aktion für die Warnung ausgeführt haben, legen Sie den Status der Warnung auf **"Gelöst"** fest.

## <a name="see-also"></a>Siehe auch

- [Erfahren Sie mehr über Warnungen zur Verhinderung von Datenverlust und das Warnungsdashboard](dlp-alerts-dashboard-learn.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)