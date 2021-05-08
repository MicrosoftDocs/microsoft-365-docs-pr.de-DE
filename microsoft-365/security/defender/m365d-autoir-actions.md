---
title: Anzeigen und Verwalten von Aktionen im Aktionscenter
description: Anzeigen und Verwalten von Korrekturaktionen mithilfe des Aktionscenters
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f3dba2116e0f13f265937ef65fd3b69bcb1e725b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274652"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Anzeigen und Verwalten von Aktionen im Aktionscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Bedrohungsschutzfeatures in Microsoft 365 Defender können zu bestimmten Abhilfemaßnahmen führen. Im Folgenden finden Sie einige Beispiele:

- [Automatisierte Untersuchungen](m365d-autoir.md) können zu Korrekturmaßnahmen führen, die automatisch ausgeführt werden oder auf Ihre Genehmigung warten.
- Antivirus-, Antischamalware- und andere Bedrohungsschutzfeatures können zu Abhilfemaßnahmen führen, z. B. das Blockieren einer Datei, URL oder eines Prozesses oder das Senden eines Artefakts in Quarantäne.
- Ihr Sicherheitsteam kann Korrekturaktionen manuell ausführen, [](advanced-hunting-overview.md) z. B. während der erweiterten Suche oder bei der Untersuchung von [Warnungen](investigate-alerts.md) oder [Vorfällen.](investigate-incidents.md)

> [!NOTE]
> Sie müssen über [geeignete Berechtigungen verfügen](m365d-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können. Weitere Informationen finden Sie unter [Voraussetzungen](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

## <a name="review-pending-actions-in-the-action-center"></a>Überprüfen ausstehender Aktionen im Aktionscenter

Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können. 

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus. Der Flyoutbereich wird geöffnet. Im Folgenden sehen Sie ein Beispiel.

   ![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)

4. Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:
   - Wählen **Sie Die Seite Untersuchung öffnen aus,** um weitere Details zur Untersuchung anzuzeigen.
   - Wählen **Sie Genehmigen** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen **Sie Ablehnen** aus, um zu verhindern, dass eine ausstehende Aktion ergriffen wird.
   - Wählen **Sie Auf Die Suche gehen** aus, um zu Erweiterte Suche zu [wechseln.](advanced-hunting-overview.md) 

## <a name="undo-completed-actions"></a>Rückgängig machen abgeschlossener Aktionen

Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung darstellt, können Sie die ergriffenen Korrekturaktionen rückgängig machen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden. Im Aktionscenter können Sie auf der Registerkarte **Verlauf** eine der folgenden Aktionen rückgängig machen:  

| Aktionsquelle | Unterstützte Aktionen |
|:---|:---|
| – Automatisierte Untersuchung <br/>- Microsoft Defender Antivirus <br/>– Manuelle Reaktionsaktionen | - Gerät isolieren <br/>- Einschränken der Codeausführung <br/>– Isolieren einer Datei <br/>- Entfernen eines Registrierungsschlüssels <br/>- Beenden eines Diensts <br/>- Deaktivieren eines Treibers <br/>– Entfernen eines geplanten Vorgangs |

### <a name="undo-one-remediation-action"></a>Rückgängig machen einer Korrekturaktion

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.

2. Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll.

3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **Rückgängig aus.**

### <a name="undo-multiple-remediation-actions"></a>Rückgängig machen mehrerer Korrekturaktionen

1. Wechseln Sie zum Aktionscenter ( https://security.microsoft.com/action-center) und melden Sie sich an.

2. Wählen Sie **auf der Registerkarte** Verlauf die Aktionen aus, die Rückgängig gemacht werden sollen. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.

3. Wählen Sie im Flyoutbereich **Rückgängig aus.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne 

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.

2. Wählen Sie **auf der Registerkarte** Verlauf eine Datei mit dem Aktionstyp **Quarantänedatei** aus.

3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms Anwenden auf **X** weitere Instanzen dieser Datei aus, und wählen Sie **dann Rückgängig aus.**

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](m365d-autoir-results.md)
- [Adress false positives oder false negatives)](m365d-autoir-report-false-positives-negatives.md)
