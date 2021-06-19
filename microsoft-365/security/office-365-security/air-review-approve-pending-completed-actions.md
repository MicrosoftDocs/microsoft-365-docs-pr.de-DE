---
title: Überprüfen und Verwalten von Abhilfemaßnahmen in Microsoft Defender für Office 365
keywords: AIR, autoIR, Microsoft Defender für Endpunkt, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
description: Erfahren Sie mehr über Abhilfemaßnahmen in automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028931"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Überprüfen und Verwalten von Abhilfemaßnahmen in Office 365

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)

Da automatisierte Untersuchungen an E-Mail-& Inhalten für die Zusammenarbeit zu Bewertungen führen, z. B. *bösartig* oder *verdächtig,* werden bestimmte Korrekturaktionen erstellt. In Microsoft Defender für Office 365 können Korrekturaktionen Folgendes umfassen:

- Vorläufiges Löschen von E-Mail-Nachrichten oder Clustern
- Deaktivieren der externen E-Mail-Weiterleitung

Diese Korrekturmaßnahmen werden erst ausgeführt, wenn sie von Ihrem Sicherheitsteam genehmigt wurden. Es wird empfohlen, alle ausstehenden Aktionen so bald wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden. In einigen Fällen können Sie eingereichte Aktionen erneut prüfen.  Sie müssen Teil der Rolle "Suchen & Löschen" sein, bevor Sie Aktionen ausführen.


## <a name="approve-or-reject-pending-actions"></a>Genehmigen (oder Ablehnen) ausstehender Aktionen
Es gibt vier verschiedene Möglichkeiten, automatische Untersuchungsaktionen zu finden und auszuführen:

- [Vorfallwarteschlange](https://security.microsoft.com/incidents)
- [Info-Center](https://security.microsoft.com/action-center/pending)
- Untersuchung selbst (Zugriff über Vorfall oder über eine Warnung)
- [Untersuchungs- und Korrekturuntersuchungen in der Warteschlange](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Vorfallwarteschlange
1. Wechseln Sie zum [Microsoft 365 Security Center,](https://security.microsoft.com) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Vorfälle & Warnungen > Vorfälle aus.**
3. Wählen Sie einen Vorfallnamen aus, um die Zusammenfassungsseite zu öffnen.
4. Wählen Sie die Registerkarte **"Nachweise und Antwort"** aus.
5. W?hlen Sie ein Element in der Liste aus. Der Seitenbereich wird geöffnet.
6. Führen Sie im Seitenbereich Aktionen zum Genehmigen oder Ablehnen aus.

## <a name="investigation-queue"></a>Untersuchungswarteschlange 
1. Wechseln Sie zum [Microsoft 365 Security Center,](https://security.microsoft.com) und melden Sie sich an.
2. Navigieren Sie von der Warnungs-/Vorfallseite. 
3. Wechseln Sie auf der Seite "Untersuchung" zur Registerkarte **"Ausstehende Aktionen".** 
4. W?hlen Sie ein Element in der Liste aus. Der Seitenbereich wird geöffnet.  
5. Führen Sie im Seitenbereich Aktionen zum Genehmigen oder Ablehnen aus.

## <a name="action-center"></a>Info-Center
1. Wechseln Sie zum [Microsoft 365 Security Center,](https://security.microsoft.com) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **das Info-Center** aus.
3. Überprüfen Sie auf der Registerkarte **"Ausstehend"** die Liste der Aktionen, die auf die Genehmigung warten.
   - Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.
   - Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.

## <a name="investigation-and-remediation-investigations-queue"></a>Untersuchungs- und Korrekturuntersuchungen in der Warteschlange
1. Wechseln Sie zum [Microsoft 365 Security Center,](https://security.microsoft.com) und melden Sie sich an.
2. Offene Untersuchungen. 
3. Wechseln Sie auf der Seite "Untersuchung" zur Registerkarte **"Ausstehende Aktionen".**
4. W?hlen Sie ein Element in der Liste aus. Der Seitenbereich wird geöffnet.  
5. Führen Sie im Seitenbereich Aktionen zum Genehmigen oder Ablehnen aus.

## <a name="change-or-undo-one-remediation-action"></a>Ändern oder Rückgängigmachen einer Korrekturaktion

Es gibt zwei verschiedene Möglichkeiten, übermittelte Aktionen zu überdenken:
   - Über das [einheitliche Info-Center.](https://security.microsoft.com/action-center)
   - Obwohl das [Office Info-Center](https://security.microsoft.com/threatincidents).
   
## <a name="change-or-undo-through-the-unified-action-center"></a>Ändern oder Rückgängigmachen über das einheitliche Info-Center
1. Wechseln Sie zum [einheitlichen Info-Center,](https://security.microsoft.com/action-center) und melden Sie sich an.
2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie ändern oder rückgängig machen möchten.
3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms die entsprechende Aktion aus (**in posteingang verschieben,** **zu Junk verschieben,** **zu gelöschten Elementen verschieben,****soft delete" oder **endgültig löschen).**

 ## <a name="change-or-undo-through-the-office-action-center"></a>Ändern oder Rückgängigmachen über das Office-Info-Center 
1. Wechseln Sie zum [Office Info-Center,](https://security.microsoft.com/threatincidents) und melden Sie sich an.
2. Wählen Sie die entsprechende Korrektur aus.
3. Klicken Sie im Seitenbereich auf den Eintrag für E-Mail-Übermittlungen, und warten Sie, bis die Liste geladen wird. 
4. Warten Sie, bis die Schaltfläche Aktion oben aktiviert ist, und wählen Sie die Schaltfläche Aktion aus, um den Aktionstyp zu ändern. 
5. Dadurch werden die entsprechenden Aktionen erstellt.

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden des Bedrohungs-Explorers](threat-explorer.md) 
- [Administrator/Manuelle Aktionen](remediate-malicious-email-delivered-office-365.md)
- [So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Siehe auch

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365](air-view-investigation-results.md)
