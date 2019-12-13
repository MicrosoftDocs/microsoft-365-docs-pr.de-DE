---
title: Genehmigen oder Ablehnen ausstehender Aktionen nach automatisierter Untersuchung
description: Verwenden des Info-Centers zum Verwalten von Aktionen im Zusammenhang mit automatisierten Untersuchungen und Reaktionen
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 5c690d07af285b5232d383bb89071c3b64343772
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911173"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a>Genehmigen oder Ablehnen ausstehender Aktionen nach automatisierten Untersuchungen

**Gilt für:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

Wenn eine automatisierte Untersuchung ausgeführt wird, kann dies zu einer oder mehreren empfohlenen [Abhilfemaßnahmen](mtp-action-center.md#remediation-actions) führen, für die eine Genehmigung erforderlich ist. So kann beispielsweise ein Cluster von E-Mail-Nachrichten gelöscht oder eine in Quarantäne befindliche Datei entfernt werden müssen. Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können. 

Zur Überprüfung und Genehmigung ausstehender Aktionen können Sie eine der folgenden Methoden anwenden:
- [Verwenden des Info-Centers](#review-a-pending-action-in-the-action-center)
- [Verwenden der Untersuchungsdetailansicht](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> Sie müssen über [geeignete Berechtigungen verfügen](mtp-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können.

## <a name="review-a-pending-action-in-the-action-center"></a>Überprüfen einer ausstehenden Aktion im Info-Center

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus. 

    - Wenn Sie ein Element in der Spalte **Nummer der Untersuchung** auswählen, wird die Seite mit den Untersuchungsdetails geöffnet. Dort können Sie die Ergebnisse der Untersuchung anzeigen und dann die empfohlenen Aktionen genehmigen oder ablehnen.
 
    - Wenn Sie eine Zeile in der Liste auswählen, wird ein Flyout geöffnet, in dem Informationen zu dem betreffenden Element angezeigt werden. <br/>![Genehmigen oder Ablehnen einer Aktion](../images/air-actioncenter-itemselected.png)<br/>Verwenden Sie die Links, um eine zugeordnete Warnung oder eine Untersuchung anzuzeigen, und genehmigen Sie die jeweilige Aktion oder lehnen Sie diese ab.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Überprüfen einer ausstehenden Aktion in der Untersuchungsdetailansicht

![Untersuchungsdetails](../images/mtp-air-investdetails.png)

1. Wählen Sie auf der Seite [Untersuchungsdetails](mtp-autoir-results.md) die Option **Ausstehende Aktionen** (oder **Aktionen**) aus. Hier sind die Elemente aufgelistet, für die eine Genehmigung aussteht.

2. Wählen Sie ein Element in der Liste aus, und wählen Sie dann **Genehmigen** oder **Ablehnen**aus.

## <a name="next-steps"></a>Nächste Schritte

- Erfahren Sie mehr über das [Info-Center](mtp-action-center.md).
- Erfahren Sie mehr über [Vorfälle](incidents-overview.md)
- Erfahren Sie mehr zum Thema [Suche](advanced-hunting-overview.md)
