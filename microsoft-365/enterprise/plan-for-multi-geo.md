---
title: Plan für Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Informationen zu Microsoft 365 Multi-Geo, zur Funktionsweise von Multi-Geo und zu für Datenspeicher verfügbaren geografischen Standorten.
ms.openlocfilehash: ce8b752cc6a335249f9d8e03289fd16b04756ce9
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712342"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Plan für Microsoft 365 Multi-Geo

Dieser Leitfaden wurde für Administratoren von multinationalen Unternehmen (MNCs) entwickelt, die den Microsoft 365-Mandanten für die Erweiterung auf weitere geografische Standorte entsprechend den Unternehmensanforderungen in Bezug auf die Datenaufbewahrung vorbereiten.

In einer Multi-Geo-Konfiguration besteht Ihr Microsoft 365-Mandant aus einem zentralen Standort und einem oder mehreren Satellitenstandorten. Dies ist ein einzelner Mandant, der mehrere Geo-Standorte umfasst. Ihre Mandanteninformationen, einschließlich der geografischen Standorte, werden in Azure Active Directory (AAD) verwaltet.

Im Folgenden werden einige wichtige Begriffe in Bezug auf Multi-Geo erläutert, die beim Verständnis der grundlegenden Konzepte der Konfiguration hilfreich sind:

-   **Mandant** – Darstellung einer Organisation in der Microsoft 365-Cloud, mit der in der Regel eine oder mehrere Domäne(n) verknüpft ist/sind (zum Beispiel https://contoso.sharepoint.com)). 

-   **Geografische Standorte** – Die geografischen Standorte, die zum Hosten von Daten in einem Microsoft 365-Mandanten verfügbar sind.

-   **Satellitenstandorte** – Die zusätzlichen geografischen Standorte, die Sie für das Daten-Hosting in Ihrem Microsoft 365-Mandanten konfiguriert haben. Multi-Geo-Mandanten umfassen mehr als einen geografischen Standort, z. B. Nordamerika und Europa.

-   **Bevorzugter Datenspeicherort (Preferred Data Location, PDL)** – Die geografische Adresse, an der die Exchange- und OneDrive-Daten eines einzelnen Benutzers gespeichert werden. Dieser kann vom Administrator unter Auswahl eines der für den Mandanten konfigurierten geografischen Standorte festgelegt werden. Bitte beachten Sie, dass bei Änderung des bevorzugten Datenspeicherorts eines Benutzers, der bereits über eine OneDrive-Website verfügt, die OneDrive-Daten dieses Benutzers nicht automatisch an den neuen geografischen Standort verschoben werden. Weitere Informationen finden Sie unter [Verschieben einer OneDrive-Bibliothek an einen anderen geografischen Standort](move-onedrive-between-geo-locations.md). Wenn sie über ein Exchange-Postfach verfügen, wird das Postfach automatisch an den neuen bevorzugten Datenspeicherort verschoben.

Für die Aktivierung von Multi-Geo müssen Sie die folgenden Schritte durchführen:

1.  Arbeiten Sie mit Ihrem Kontoteam, um den Serviceplan für _Multi-Geo-Funktionen in Microsoft 365_ hinzuzufügen.

2.  Wählen Sie die gewünschten Satellitenstandorte aus, und fügen Sie sie Ihrem Mandanten hinzu.

3.  Legen Sie den gewünschten Satellitenstandort als bevorzugten Datenspeicherort Ihrer Benutzer fest. Neue OneDrive-Websites oder Exchange-Postfächer werden an den PDL des betreffenden Benutzers bereitgestellt.

4.  Migrieren Sie bei Bedarf vorhandene OneDrive-Websites der Benutzer von dem zentralen Standort zu dem bevorzugten Datenspeicherort. (Exchange-Postfächer werden automatisch migriert, wenn Sie den PDL eines Benutzers festlegen.)

Weitere Informationen zu den einzelnen Schritten finden Sie unter [Konfigurieren von Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md).

> [!IMPORTANT]
> Beachten Sie, dass Microsoft 365 Multi-Geo nicht zur Leistungsoptimierung entwickelt wurde, sondern zur Einhaltung von Datenaufbewahrungsrichtlinien. Informationen zur Leistungsoptimierung vom Microsoft 365 finden Sie unter [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) oder kontaktieren Sie Ihre Supportgruppe.

Sie können jegliche der folgenden Standorte als Satellitenstandorte konfigurieren, um darüber OneDrive- und SharePoint-Websites sowie Exchange-Postfächer hosten zu können. Erstellen Sie während der Multi-Geo-Planung eine Liste der Standorte, die Sie Ihrem Microsoft 365-Mandanten hinzufügen möchten. Wir empfehlen, mit ein oder zwei Satellitenstandorten zu beginnen und dann bei Bedarf weitere geografische Standorte hinzuzufügen.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Beim Konfigurieren von Multi-Geo sollten Sie auch eine Konsolidierung der lokalen Infrastruktur während der Migration zu Microsoft 365 berücksichtigen. Wenn Sie zum Beispiel über lokale Farmen in Singapur und Malaysia verfügen, können Sie sie an dem Satellitenstandort APC zusammenführen, wenn dies entsprechend den Datenaufbewahrungsanforderungen möglich ist.

## <a name="best-practices"></a>Bewährte Methoden

Wir empfehlen, dass Sie für anfängliche Tests ein Testbenutzerkonto in Microsoft 365 erstellen. Über dieses Konto führen Sie einige Test- und Prüfschritte durch, bevor Sie mit dem Onboarding von Benutzern in Microsoft 365 Multi-Geo fortfahren.

Nachdem Sie die Tests über das Testbenutzerkonto abgeschlossen haben, wählen Sie eine Pilotgruppe aus – beispielsweise aus Ihrer IT-Abteilung –, die als Erstes Zugriff auf OneDrive und Exchange an einem neuen geografischen Standort erhalten. Wählen Sie für diese erste Gruppe Benutzer aus, die noch nicht über eine OneDrive-Umgebung verfügen. Wir empfehlen, nicht mehr als fünf Personen zu dieser ersten Gruppe hinzuzufügen und diese anhand eines Rollouts im Batch zu erweitern.

Für jeden Benutzer muss ein *bevorzugter Datenspeicherort* festgelegt werden, damit Microsoft 365 den geografischen Standort für die Bereitstellung von OneDrive ermitteln kann. Der bevorzugte Datenspeicherort des Benutzers muss mit einem der ausgewählten Satellitenstandorte oder dem zentralen Standort übereinstimmen. Obwohl das Feld für den bevorzugten Datenspeicherort kein Pflichtfeld ist, wird empfohlen, einen bevorzugten Datenspeicherort für alle Benutzer festzulegen. Workloads eines Benutzers ohne bevorzugten Datenspeicherort werden an dem zentralen Standort bereitgestellt.

Erstellen Sie eine Liste Ihrer Benutzer mit den entsprechenden Benutzerprinzipalnamen und den Codes für die entsprechenden bevorzugten Datenspeicherorte. Fügen Sie Ihren Testbenutzer und die erste Pilotgruppe hinzu. Sie benötigen diese Liste für die Konfigurationsverfahren.

Wenn Ihre Benutzer aus einem lokalen Active Directory-System mit Azure Active Directory synchronisiert werden, müssen Sie den bevorzugten Datenspeicherort als Active Directory-Attribut festlegen und mithilfe von Azure Active Directory Connect eine Synchronisierung vornehmen. Sie können den bevorzugten Datenspeicherort für synchronisierte Benutzer nicht direkt mithilfe von Azure AD PowerShell konfigurieren. Informationen zu den Schritten für die Einrichtung eines PDL in Active Directory und die entspreche Synchronisierung finden Sie in [Azure Active Directory Connect-Synchronisierung: Konfigurieren von bevorzugten Datenspeicherorten für Microsoft 365-Ressourcen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

Die Verwaltung eines Multi-Geo-Mandanten kann von der eines Nicht-Multi-Geo-Mandanten abweichen, da viele SharePoint- und OneDrive-Einstellungen und -Dienste über Multi-Geo-Funktionen verfügen. Es wird empfohlen, den Artikel [Verwalten einer Multi-Geo-Umgebung](administering-a-multi-geo-environment.md) zu lesen, bevor Sie mit der Konfiguration fortfahren.

Weitere Informationen zur Benutzererfahrung in einer [Multi-Geo-Umgebung](multi-geo-user-experience.md) finden Sie unter Benutzererfahrung in einer Multi-Geo-Umgebung.

Ausführliche Informationen zur Teams-Erfahrung in einer Multi-Geo-fähigen Microsoft 365-Mandanteneinheit finden Sie unter [Teams-Umgebung in einer Microsoft 365 OneDrive und SharePoint Online Multi-Geo-fähigen Mandanteneinheit](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo).

Um mit der Konfigurierung von Microsoft 365 Multi-Geo zu beginnen, lesen Sie bitte [Konfigurieren von Microsoft 365-Multi-Geo](multi-geo-tenant-configuration.md).

Denken Sie nach Abschluss der Konfiguration daran, [die OneDrive-Bibliotheken Ihrer Benutzer](move-onedrive-between-geo-locations.md) bei Bedarf zu migrieren, damit Benutzer an ihren bevorzugten Datenspeicherorten arbeiten können.

## <a name="related-topics"></a>Verwandte Themen

[Konfiguration von Microsoft 365 Multi-Geo eDiscovery](https://docs.microsoft.com/microsoft-365/enterprise/multi-geo-ediscovery-configuration)
