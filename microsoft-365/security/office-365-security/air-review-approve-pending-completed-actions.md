---
title: Überprüfen und Verwalten von Korrekturaktionen in Microsoft Defender für Office 365
keywords: AIR, AutoIR, Microsoft Defender for Endpoint, automatisiert, Untersuchung, Antwort, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie mehr über Korrekturaktionen in automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: ce6cfd920845f5a85dbc7d7d48cfefdd6209ec3a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933649"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Überprüfen und Verwalten von Korrekturaktionen in Office 365

Da automatisierte Untersuchungen zu E-Mail-& Zusammenarbeitsinhalte zu  Urteilen führen, z. B. "Bösartig" oder "Verdächtig", werden bestimmte Korrekturaktionen erstellt. In Microsoft Defender for Office 365 können Korrekturaktionen Folgendes umfassen:
- Blockieren einer URL (Klickzeit)
- Weiches Löschen von E-Mail-Nachrichten oder Clustern
- Quarantining von E-Mail- oder E-Mail-Anlagen
- Deaktivieren der externen E-Mail-Weiterleitung

Diese Korrekturaktionen werden nur dann ergriffen, wenn das Sicherheitsteam sie genehmigt hat. Es wird empfohlen, alle ausstehenden Aktionen so schnell wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden. In einigen Fällen können Sie eine Korrekturaktion rückgängig machen.

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a>Genehmigen (oder Ablehnen) ausstehender Aktionen

1. Wechseln Sie zum Microsoft 365 Security Center ( <https://security.microsoft.com> ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Aktionscenter aus.**
3. Überprüfen Sie **auf der Registerkarte** Ausstehend die Liste der Aktionen, die auf die Genehmigung warten.
4. W?hlen Sie ein Element in der Liste aus. Der Flyoutbereich wird geöffnet. 
5. Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:
   - Wählen **Sie Die Seite Untersuchung öffnen aus,** um weitere Details zur Untersuchung anzuzeigen.
   - Wählen **Sie Genehmigen** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen **Sie Ablehnen** aus, um zu verhindern, dass eine ausstehende Aktion ergriffen wird.

## <a name="undo-one-remediation-action"></a>Rückgängig machen einer Korrekturaktion

1. Wechseln Sie zum Aktionscenter ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.
2. Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll.
3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **Rückgängig aus.**

## <a name="undo-multiple-remediation-actions"></a>Rückgängig machen mehrerer Korrekturaktionen

1. Wechseln Sie zum Aktionscenter ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.
2. Wählen Sie **auf der Registerkarte** Verlauf die Aktionen aus, die Rückgängig gemacht werden sollen. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.
3. Wählen Sie im Flyoutbereich Rückgängig aus.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne

1. Wechseln Sie zum Aktionscenter ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.
2. Wählen Sie **auf der Registerkarte** Verlauf eine Datei mit dem Aktionstyp **Quarantänedatei aus.**
3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms Anwenden auf **X** weitere Instanzen dieser Datei aus, und wählen Sie **dann Rückgängig aus.**

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden des Bedrohungs-Explorers](threat-explorer.md)
- [Melden falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Siehe auch

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365](air-view-investigation-results.md)
