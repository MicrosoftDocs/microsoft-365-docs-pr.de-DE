---
title: Anzeigen und Verwalten von Aktionen im Info-Center
description: Verwenden des Info-Centers zum Anzeigen und Verwalten von Wartungsaktionen
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
ms.openlocfilehash: 95c82f815c794662f7eb0ffaabcfb5f81df3e828
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782993"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Anzeigen und Verwalten von Aktionen im Info-Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Features zum Schutz vor Bedrohungen in Microsoft 365 Defender können zu bestimmten Abhilfemaßnahmen führen. Im Folgenden finden Sie einige Beispiele:

- [Automatisierte Untersuchungen](m365d-autoir.md) können zu Korrekturmaßnahmen führen, die automatisch ausgeführt werden oder auf Ihre Genehmigung warten.
- Antivirus-, Antischadsoftware- und andere Bedrohungsschutzfeatures können zu Abhilfemaßnahmen führen, z. B. das Blockieren einer Datei, einer URL oder eines Prozesses oder das Senden eines Artefakts zur Quarantäne.
- Ihr Sicherheitsteam kann manuell Abhilfemaßnahmen ergreifen, z. B. während der [erweiterten Suche](advanced-hunting-overview.md) oder während der Untersuchung von [Warnungen](investigate-alerts.md) oder [Vorfällen.](investigate-incidents.md)

> [!NOTE]
> Sie müssen über [geeignete Berechtigungen verfügen](m365d-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können. Weitere Informationen finden Sie unter den [Voraussetzungen.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-pending-actions-in-the-action-center"></a>Überprüfen ausstehender Aktionen im Info-Center

Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können. 

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie im Info-Center auf der Registerkarte **"Ausstehend"** ein Element in der Liste aus. Der Flyoutbereich wird geöffnet. Im Folgenden sehen Sie ein Beispiel.

   ![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)

4. Überprüfen Sie die Informationen im Flyoutbereich, und führen Sie dann einen der folgenden Schritte aus:
   - Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.
   - Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.
   - Wählen Sie **"Gehe Auf Suche"** aus, um zur [erweiterten Suche](advanced-hunting-overview.md)zu gelangen. 

## <a name="undo-completed-actions"></a>Abgeschlossene Aktionen rückgängigmachen

Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung ist, können Sie die durchgeführten Abhilfemaßnahmen rückgängigmachen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden. Im Info-Center können Sie auf der Registerkarte **"Verlauf"** eine der folgenden Aktionen rückgängigmachen:  

| Aktionsquelle | Unterstützte Aktionen |
|:---|:---|
| – Automatisierte Untersuchung <br/>- Microsoft Defender Antivirus <br/>– Manuelle Reaktionsaktionen | – Gerät isolieren <br/>– Einschränken der Codeausführung <br/>– Isolieren einer Datei <br/>– Entfernen eines Registrierungsschlüssels <br/>- Beenden eines Diensts <br/>– Deaktivieren eines Treibers <br/>- Entfernen einer geplanten Aufgabe |

### <a name="undo-one-remediation-action"></a>Rückgängigmachen einer Korrekturaktion

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.

2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie rückgängig machen möchten.

3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig"** aus.

### <a name="undo-multiple-remediation-actions"></a>Rückgängigmachen mehrerer Korrekturaktionen

1. Wechseln Sie zum Info-Center ( https://security.microsoft.com/action-center) und melden Sie sich an.

2. Wählen Sie auf der Registerkarte **"Verlauf"** die Aktionen aus, die Sie rückgängig machen möchten. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.

3. Wählen Sie im Flyoutbereich **"Rückgängig"** aus.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei aus der Quarantäne auf mehreren Geräten 

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.

2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Datei mit dem Aktionstyp **"Quarantänedatei"** aus.

3. Klicken Sie im Bereich auf der rechten Seite des **Bildschirms auf X weitere Instanzen dieser Datei anwenden,** und wählen Sie dann **Rückgängig** aus.

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](m365d-autoir-results.md)
- [Adressen falsch positiver oder falsch negativer Ergebnisse](m365d-autoir-report-false-positives-negatives.md)
