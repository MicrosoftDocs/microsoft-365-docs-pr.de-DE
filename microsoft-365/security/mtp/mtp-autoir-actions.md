---
title: Genehmigen oder Ablehnen ausstehender Aktionen nach einer automatischen Untersuchung
description: Verwenden des Info-Centers zum Verwalten von Aktionen im Zusammenhang mit automatisierten Untersuchungen und Reaktionen
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930378"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Genehmigen oder Ablehnen ausstehender Aktionen nach einer automatischen Untersuchung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Wenn eine automatisierte Untersuchung ausgeführt wird, kann dies zu einer oder mehreren empfohlenen [Abhilfemaßnahmen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) führen, für die eine Genehmigung erforderlich ist. So kann beispielsweise ein Cluster von E-Mail-Nachrichten gelöscht oder eine in Quarantäne befindliche Datei entfernt werden müssen. Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können. 

> [!TIP]
> Wenn Sie denken, dass etwas von automatisierten Untersuchungs- und Antwortfeatures in Microsoft 365 Defender übersehen oder falsch erkannt wurde, lassen Sie es uns wissen! Erfahren [Sie, wie Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen (AIR) in Microsoft 365 Defender melden.](mtp-autoir-report-false-positives-negatives.md)

Ausstehende Aktionen können mithilfe des [](#review-a-pending-action-in-the-action-center) Aktionscenters oder der Ansicht "Untersuchungsdetails" überprüft [und genehmigt werden.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> Sie müssen über [geeignete Berechtigungen verfügen](mtp-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können. Weitere Informationen finden Sie unter [Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

## <a name="review-a-pending-action-in-the-action-center"></a>Überprüfen einer ausstehenden Aktion im Info-Center

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus. 

    - Wenn Sie ein Element in der Spalte **Nummer der Untersuchung** auswählen, wird die Seite mit den Untersuchungsdetails geöffnet. Dort können Sie die Ergebnisse der Untersuchung anzeigen und dann die empfohlenen Aktionen genehmigen oder ablehnen.
 
    - Wenn Sie eine Zeile in der Liste auswählen, wird ein Flyout geöffnet, in dem Informationen zu dem betreffenden Element angezeigt werden. <br/>![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)<br/>Verwenden Sie die Links, um eine zugeordnete Warnung oder eine Untersuchung anzuzeigen, und genehmigen Sie die jeweilige Aktion oder lehnen Sie diese ab.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Überprüfen einer ausstehenden Aktion in der Untersuchungsdetailansicht

![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

1. Wählen Sie auf der Seite [Untersuchungsdetails](mtp-autoir-results.md) die Option **Ausstehende Aktionen** (oder **Aktionen**) aus. Hier sind die Elemente aufgelistet, für die eine Genehmigung aussteht.

2. Wählen Sie ein Element in der Liste aus, und wählen Sie dann **Genehmigen** oder **Ablehnen** aus.

## <a name="undo-completed-actions"></a>Abgeschlossene Aktionen rückgängig machen

Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung darstellt, können Sie die ergriffenen Abhilfemaßnahmen rückgängig machen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden. Im Aktionscenter können Sie auf **der** Registerkarte "Verlauf" eine der folgenden Aktionen rückgängig machen:  

| Aktionsquelle | Unterstützte Aktionen |
|:---|:---|
| – Automatisierte Untersuchung <br/>– Microsoft Defender Antivirus <br/>– Manuelle Reaktionsaktionen | - Gerät isolieren <br/>– Einschränken der Codeausführung <br/>– Isolieren einer Datei <br/>– Entfernen eines Registrierungsschlüssels <br/>– Beenden eines Diensts <br/>– Deaktivieren eines Treibers <br/>– Entfernen eines geplanten Vorgangs |

### <a name="to-undo-a-remediation-action"></a>So machen Sie eine Wartungsaktion rückgängig

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.

2. Wählen Sie **auf der** Registerkarte "Verlauf" eine Aktion aus, die Rückgängig gemacht werden soll.

3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig" aus.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne 

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.

2. Wählen Sie **auf der Registerkarte** "Verlauf" eine Datei mit dem Aktionstyp **"Quarantäne" aus.**

3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Auf X** weitere Instanzen dieser Datei anwenden" und dann **"Rückgängig" aus.**

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)
- [Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](mtp-autoir-report-false-positives-negatives.md)
