---
title: Überprüfen und Verwalten von Wartungsaktionen in Microsoft Defender für Office 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Problembehebung, Bedrohungen, erweitert, Bedrohung, Schutz
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
description: Erfahren Sie mehr über Abhilfemaßnahmen bei automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142693"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Überprüfen und Verwalten von Wartungsaktionen in Office 365

Da automatisierte Untersuchungen von E-mail-& zusammenarbeitsinhalten  zu Bekündungen führen, z. B. bösartig oder verdächtig, werden bestimmte Abhilfemaßnahmen erstellt. In Microsoft Defender für Office 365 können Wiederherstellungsaktionen Folgendes umfassen:
- Blockieren einer URL (Zeitpunkt des Klicks)
- Soft deleting email messages or clusters
- Quarantining von E-Mail- oder E-Mail-Anlagen
- Deaktivieren der externen E-Mail-Weiterleitung

Diese Abhilfemaßnahmen werden erst dann ergriffen, wenn sie vom Sicherheitsteam genehmigt werden. Es wird empfohlen, alle ausstehenden Aktionen so bald wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden. In einigen Fällen können Sie eine Korrekturaktion rückgängig machen.

## <a name="approve-or-reject-pending-actions"></a>Genehmigen (oder Ablehnen) ausstehender Aktionen

1. Wechseln Sie zum Microsoft 365 Security [https://security.microsoft.com](https://security.microsoft.com) Center, und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **"Aktionscenter" aus.**
3. Überprüfen Sie **auf der Registerkarte** "Ausstehend" die Liste der Aktionen, die auf eine Genehmigung warten.
4. W?hlen Sie ein Element in der Liste aus. Der Flyoutbereich wird geöffnet. 
5. Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:
   - Wählen **Sie die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.
   - Wählen **Sie "Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen **Sie "Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion abgeschlossen wird.

## <a name="undo-one-remediation-action"></a>Rückgängig machen einer Wartungsaktion

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.
2. Wählen Sie **auf der** Registerkarte "Verlauf" eine Aktion aus, die Rückgängig gemacht werden soll.
3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig" aus.**

## <a name="undo-multiple-remediation-actions"></a>Rückgängig machen mehrerer Wartungsaktionen

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.
2. Wählen Sie **auf der** Registerkarte "Verlauf" die Aktionen aus, die Rückgängig gemacht werden sollen. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.
3. Wählen Sie im Flyoutbereich "Rückgängig" aus.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne

1. Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.
2. Wählen Sie **auf der Registerkarte** "Verlauf" eine Datei mit dem Aktionstyp **"Quarantäne" aus.**
3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Auf X** weitere Instanzen dieser Datei anwenden" und dann **"Rückgängig" aus.**

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden des Bedrohungs-Explorers](threat-explorer.md)
- [So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Siehe auch

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365](air-view-investigation-results.md)
