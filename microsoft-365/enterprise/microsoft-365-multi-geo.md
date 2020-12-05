---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In diesem Artikel erfahren Sie, wie Sie Ihre Microsoft 365-Präsenz in mehreren geografischen Regionen mit Microsoft 365 Multi-Geo erweitern können.
ms.openlocfilehash: cf5f655e2b205001c6c16ed05abc33d68324ff15
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580697"
---
# <a name="microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo

Mit Microsoft 365 Multi-Geo kann Ihr Unternehmen seine Microsoft 365-Präsenz auf mehrere geografische Regionen und/oder Länder innerhalb des vorhandenen Mandanten erweitern. Wenden Sie sich an Ihr Microsoft-Kontoteam, um Ihr multinationales Unternehmen für Microsoft 365 Multi-Geo anzumelden.
  
Mit Microsoft 365 Multi-Geo können Sie ruhende Daten an den Datenresistenz-Anforderungen entsprechenden geografischen Speicherorten bereitstellen und speichern und gleichzeitig die globale Bereitstellung moderner Produktivitätserfahrungen für Ihre Mitarbeiter in Gang setzen.

Eine Video Einführung in Microsoft 365 Multi-Geo finden Sie unter [SharePoint Online und OneDrive Multi-Geo, um zu steuern, wo sich Ihre Daten befinden](https://www.youtube.com/watch?v=Do9U3JuROhk).

## <a name="multi-geo-architecture"></a>Multi-Geo-Architektur

In einer Multi-Geo-Umgebung verfügt Ihr Microsoft 365-Mandant über einen zentralen Standort (an dem Ihr Microsoft 365-Abonnement ursprünglich bereitgestellt wurde) und über einen oder mehrere Satellitenstandort(e). Die Informationen über geografische Standorte, Gruppen und Benutzer eines Multi-Geo-Mandanten werden in Azure Active Directory (AAD) verwaltet. Da Ihre Mandanteninformationen zentral verwaltet und an jedem geografischen Speicherort synchronisiert werden, wird das globale Bewusstsein durch das Teilen von Informationen und Erfahrungen im gesamten Unternehmen erhöht.

![Screenshot der Multi-Geo-Zuordnung aus der SharePoint-Admin Center](../media/multi-geo-world-map.png)

Beachten Sie, dass Microsoft 365 Multi-Geo nicht zur Leistungsoptimierung entwickelt wurde, sondern zur Einhaltung von Datenaufbewahrungsrichtlinien. Informationen zur Leistungsoptimierung vom Microsoft 365 finden Sie unter [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) oder kontaktieren Sie Ihre Supportgruppe.

## <a name="terminology"></a>Begrifflichkeiten

Dies sind die wichtigsten Begriffe für die Beschreibung von Microsoft 365 Multi-Geo:

- **Zentraler Standort** – Der geografische Standort, an dem Ihr Mandant ursprünglich bereitgestellt wurde.
- **Geo-Administrator** – Ein Administrator, der einen oder mehrere der angegebenen Satellitenstandorte verwalten kann.
- **Geo-Code** – Eine Code aus drei Buchstaben für einen bestimmten Geo-Standort.
- **Geo-Standort** – Ein geografischer Standort, der in einem Multi-Geo-Mandanten verwendet werden kann, um Daten zu hosten, einschließlich Exchange-Postfächer und OneDrive- und SharePoint-Seiten.
- **Bevorzugter Datenspeicherort (PLD)** – Eine vom Administrator festgelegte Benutzereigenschaft, die angibt, an welchem geographischen Standort das Exchange-Postfach des Benutzers und OneDrive bereitgestellt werden sollen. Der PLD gibt außerdem an, wo vom Benutzer erstellte SharePoint-Seiten bereitgestellt werden.
- **Satelliten-Standort** – Der geographische Standort, an dem die Geo-fähigen Microsoft 365-Arbeitslasten (SharePoint, OneDrive und Exchange) in einem Multi-Geo-Mandanten aktiviert sind.
- **Mandant** – Darstellung einer Organisation in der Microsoft 365-Cloud, mit der in der Regel eine oder mehrere Domäne(n) verknüpft ist/sind (zum Beispiel contoso.com).

## <a name="licensing"></a>Lizenzierung

Microsoft 365 Multi-Geo wird als Add-On bei den folgenden Microsoft 365-Abonnementplänen für EA-Kunden mit mindestens 250 Microsoft 365-Arbeitsplätzen im Mandanten und mindestens 5 % der Arbeitsplätze für die Nutzung von Multi-Geo bereitgestellt. Wenden Sie sich für weitere Informationen an Ihr Microsoft-Team.

- Microsoft 365 F1, F3, E3 oder E5
- Office 365 F3, E1, E3 oder E5
- Exchange Online Plan 1 oder Plan 2
- OneDrive for Business Plan 1 oder Plan 2
- SharePoint Online Plan 1 oder Plan 2

## <a name="microsoft-365-multi-geo-availability"></a>Verfügbarkeit von Microsoft 365 Multi-Geo

Microsoft 365 Multi-Geo wird derzeit in diesen Regionen und Ländern angeboten:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a>Erste Schritte

Gehen Sie folgendermaßen vor, um mit Multi-Geo loszulegen:

1. Arbeiten Sie mit Ihrem Kontoteam, um den Serviceplan für _Multi-Geo-Funktionen in Microsoft 365_ hinzuzufügen. Sie werden angeleitet, die benötigten Lizenzen hinzuzufügen. Multi-Geo ist für EA/Bestandskunden mit mindestens 250 Microsoft 365-Abonnements verfügbar.

   Bevor Sie mit der Verwendung von Microsoft 365 Multi-Geo beginnen können, muss Ihr Exchange Online-Mandant durch Microsoft für die Unterstützung von Multi-Geo konfiguriert werden. Dieser einmalige Konfigurationsprozess wird ausgelöst, nach dem Sie den Service-Plan für *Multi-Geo-Funktionen in Microsoft 365* bestellt haben und die Lizenzen in Ihrem Mandanten angezeigt werden. Sie erhalten Arbeits Auslastungs spezifische Benachrichtigungen im [Microsoft 365-Nachrichtencenter](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) , sobald Ihr Mandant den Konfigurationsprozess für jede Arbeitsauslastung abgeschlossen hat, und Sie können dann mit der Konfiguration und Verwendung Ihrer Microsoft 365 Multi-Geo-Funktionen beginnen. Die für die Konfiguration eines Mandanten für die Multi-Geo-Unterstützung erforderliche Zeit variiert von Mandanten zu Mandanten, aber die meisten Mandanten werden innerhalb eines Monats nach Erhalt der Funktions Lizenzen fertig gestellt. Größere oder komplexere Mandanten benötigen möglicherweise mehr Zeit, um den Konfigurationsprozess abzuschließen. Wenden Sie sich bei Bedarf an Ihr Konto Team, um Details zu ihrem jeweiligen Mandanten zu erhalten.

2. Lesen Sie den Abschnitt [Planen Ihrer Multi-Geo-Umgebung](plan-for-multi-geo.md).

3. Erfahren Sie mehr über das [Verwalten einer Multi-Geo-Umgebung](administering-a-multi-geo-environment.md) und darüber, [wie Ihre Benutzer die Umgebung erleben](multi-geo-user-experience.md).

4. Wenn Sie für die Einrichtung von Microsoft 365 Multi-Geo bereit sind, [konfigurieren Sie Ihren Mandanten für Multi-Geo](multi-geo-tenant-configuration.md).

5. [Einrichten der Suche](configure-search-for-multi-geo.md).

## <a name="see-also"></a>Siehe auch

[Multi-Geo in Exchange Online und OneDrive](https://Aka.ms/GoMultiGeo)

[Multi-Geo-Funktionen in OneDrive und SharePoint Online](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[Multi-Geo-Funktionen in Exchange Online](multi-geo-capabilities-in-exchange-online.md)

[Teams in einer Multi-Geo-Umgebung](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
