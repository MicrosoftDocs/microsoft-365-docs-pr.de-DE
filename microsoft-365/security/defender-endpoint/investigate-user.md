---
title: Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint
description: Untersuchen Sie während einer Untersuchung ein Benutzerkonto auf potenzielle gefährdete Anmeldeinformationen oder Pivot für das zugeordnete Benutzerkonto.
keywords: investigate, account, user, user entity, alert, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 672867d107d005004201caab7d6497ceb048ac97
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587707"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Untersuchen von Benutzerkontenentitäten

Identifizieren Sie Benutzerkonten mit den aktivsten Warnungen (im Dashboard als "Gefährdete Benutzer" angezeigt), und untersuchen Sie Fälle potenzieller gefährdeter Anmeldeinformationen, oder verwenden Sie das zugehörige Benutzerkonto, wenn Sie eine Warnung oder ein Gerät untersuchen, um eine mögliche quere Bewegung zwischen Geräten mit diesem Benutzerkonto zu identifizieren.

Informationen zum Benutzerkonto finden Sie in den folgenden Ansichten:

- Dashboard
- Warnungswarteschlange
- Seite "Gerätedetails"

In diesen Ansichten ist ein klickbarer Benutzerkontolink verfügbar, über den Sie zur Seite mit den Benutzerkontodetails gelangen, auf der weitere Details zum Benutzerkonto angezeigt werden.

Wenn Sie eine Benutzerkontenentität untersuchen, sehen Sie:

- Benutzerkontodetails, Azure Advanced Threat Protection (Azure ATP)-Warnungen und angemeldete Geräte, Rolle, Anmeldetyp und andere Details
- Übersicht über vorfälle und Benutzergeräte
- Warnungen im Zusammenhang mit diesem Benutzer
- Beobachtet in der Organisation (angemeldete Geräte)

![Abbildung der Seite mit den Details der Benutzerkontenentität](images/atp-user-details-view.png)

### <a name="user-details"></a>Benutzerdetails

Der  Bereich Benutzerdetails auf der linken Seite enthält Informationen über den Benutzer, z. B. verwandte offene Vorfälle, aktive Warnungen, SAM-Name, SID, Azure ATP-Warnungen, Anzahl der Geräte, bei denen der Benutzer angemeldet ist, wann der Benutzer zuerst und zuletzt gesehen wurde, Rollen- und Anmeldetypen. Je nach den von Ihnen aktivierten Integrationsfeatures werden weitere Details zu sehen sein. Wenn Sie beispielsweise die Skype for Business-Integration aktivieren, können Sie den Benutzer über das Portal kontaktieren. Der **Abschnitt Azure ATP-Warnungen** enthält einen Link, über den Sie zur Azure ATP-Seite gelangen, wenn Sie das Azure ATP-Feature aktiviert haben und es Warnungen im Zusammenhang mit dem Benutzer gibt. Die Azure ATP-Seite enthält weitere Informationen zu den Warnungen.

>[!NOTE]
>Sie müssen die Integration in Azure ATP und Defender for Endpoint aktivieren, um dieses Feature verwenden zu können. In Defender for Endpoint können Sie dieses Feature in erweiterten Features aktivieren. Weitere Informationen zum Aktivieren erweiterter Features finden Sie unter [Turn on advanced features](advanced-features.md).

Die Registerkarten Übersicht, Warnungen und Beobachtet in der Organisation sind unterschiedliche Registerkarten, die verschiedene Attribute zum Benutzerkonto anzeigen.

### <a name="overview"></a>Übersicht

Auf **der** Registerkarte Übersicht werden die Details zu Vorfällen und eine Liste der Geräte angezeigt, bei der sich der Benutzer angemeldet hat. Sie können diese erweitern, um Details der Anmeldeereignisse für jedes Gerät anzuzeigen.

### <a name="alerts"></a>Warnungen

Die **Registerkarte Warnungen** enthält eine Liste der Warnungen, die dem Benutzerkonto zugeordnet sind. Diese Liste ist eine gefilterte Ansicht der Warnungswarteschlange [und](alerts-queue.md)zeigt Warnungen an, bei denen der Benutzerkontext das ausgewählte Benutzerkonto ist, das Datum, an dem die letzte Aktivität erkannt wurde, eine kurze Beschreibung der Warnung, das gerät, das der Warnung zugeordnet ist, den Schweregrad der Warnung, den Status der Warnung in der Warteschleife und wem die Warnung zugewiesen wurde.

### <a name="observed-in-organization"></a>Beobachtet in der Organisation

Auf der Registerkarte **Beobachtet in** der Organisation können Sie einen Datumsbereich angeben, um eine Liste der Geräte zu sehen, auf denen dieser Benutzer angemeldet war, das häufigste und am wenigsten häufig angemeldete Benutzerkonto für jedes dieser Geräte und die Gesamtzahl der beobachteten Benutzer auf jedem Gerät.

Durch Auswählen eines Elements in der Tabelle Beobachtet in der Organisation wird das Element erweitert, und es werden weitere Details zum Gerät angezeigt. Wenn Sie direkt einen Link innerhalb eines Elements auswählen, gelangen Sie zur entsprechenden Seite.

## <a name="search-for-specific-user-accounts"></a>Suchen nach bestimmten Benutzerkonten

1. Wählen **Sie im** Dropdownmenü **Suchleiste** Die Option Benutzer aus.
2. Geben Sie das Benutzerkonto in das Feld **Suchen** ein.
3. Klicken Sie auf das Suchsymbol, oder drücken Sie die **EINGABETASTE.**

Eine Liste der Benutzer, die mit dem Abfragetext übereinstimmen, wird angezeigt. Sie sehen die Domäne und den Namen des Benutzerkontos, wenn das Benutzerkonto zuletzt gesehen wurde, und die Gesamtzahl der Geräte, auf denen es in den letzten 30 Tagen angemeldet war.

Sie können die Ergebnisse nach den folgenden Zeiträumen filtern:

- 1 Tag
- 3 Tage
- 7 Tage
- 30 Tage
- 6 Monate

## <a name="related-topics"></a>Verwandte Themen

- [Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange](alerts-queue.md)
- [Verwalten von Microsoft Defender for Endpoint-Warnungen](manage-alerts.md)
- [Untersuchen von Microsoft Defender for Endpoint-Warnungen](investigate-alerts.md)
- [Untersuchen einer Datei, die einer Defender for Endpoint-Warnung zugeordnet ist](investigate-files.md)
- [Untersuchen von Geräten in der Liste "Defender for Endpoint Devices"](investigate-machines.md)
- [Untersuchen einer einer Defender for Endpoint-Warnung zugeordneten IP-Adresse](investigate-ip.md)
- [Untersuchen einer Domäne, die einer Defender for Endpoint-Warnung zugeordnet ist](investigate-domain.md)
