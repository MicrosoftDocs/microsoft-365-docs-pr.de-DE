---
title: Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung
description: Verwenden des Info-Centers zum Verwalten von Aktionen im Zusammenhang mit automatisierten Untersuchungen und Reaktionen
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: dd7ded318c5ab0cf9aad47054ac04d5a2d353943
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199805"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Genehmigen oder Ablehnen ausstehender Aktionen im Anschluss an eine automatisierte Untersuchung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection

Wenn eine automatisierte Untersuchung ausgeführt wird, kann dies zu einer oder mehreren empfohlenen [Abhilfemaßnahmen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) führen, für die eine Genehmigung erforderlich ist. So kann beispielsweise ein Cluster von E-Mail-Nachrichten gelöscht oder eine in Quarantäne befindliche Datei entfernt werden müssen. Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können. 

> [!TIP]
> Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen! Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Funktionen in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Ausstehende Aktionen können mithilfe des [Aktions Centers](#review-a-pending-action-in-the-action-center) oder der [Ansicht Details der Untersuchung](#review-a-pending-action-in-the-investigation-details-view)überprüft und genehmigt werden.

> [!NOTE]
> Sie müssen über [geeignete Berechtigungen verfügen](mtp-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können.

## <a name="review-a-pending-action-in-the-action-center"></a>Überprüfen einer ausstehenden Aktion im Info-Center

1. Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an. 

2. Wählen Sie im Navigationsbereich **Info-Center** aus. 

3. Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus. 

    - Wenn Sie ein Element in der Spalte **Nummer der Untersuchung** auswählen, wird die Seite mit den Untersuchungsdetails geöffnet. Dort können Sie die Ergebnisse der Untersuchung anzeigen und dann die empfohlenen Aktionen genehmigen oder ablehnen.
 
    - Wenn Sie eine Zeile in der Liste auswählen, wird ein Flyout geöffnet, in dem Informationen zu dem betreffenden Element angezeigt werden. <br/>![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)<br/>Verwenden Sie die Links, um eine zugeordnete Warnung oder eine Untersuchung anzuzeigen, und genehmigen Sie die jeweilige Aktion oder lehnen Sie diese ab.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Überprüfen einer ausstehenden Aktion in der Untersuchungsdetailansicht

![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

1. Wählen Sie auf der Seite [Untersuchungsdetails](mtp-autoir-results.md) die Option **Ausstehende Aktionen** (oder **Aktionen**) aus. Hier sind die Elemente aufgelistet, für die eine Genehmigung aussteht.

2. Wählen Sie ein Element in der Liste aus, und wählen Sie dann **Genehmigen** oder **Ablehnen**aus.

## <a name="next-steps"></a>Nächste Schritte

- [Anzeigen der Details und Ergebnisse einer automatischen Untersuchung](mtp-autoir-results.md)
- [Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen](mtp-autoir-report-false-positives-negatives.md)
