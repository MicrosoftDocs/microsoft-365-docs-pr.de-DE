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
ms.openlocfilehash: 7894a9aa38239bf661c809cce96ea2a2a96c3725
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904128"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Überprüfen und Verwalten von Abhilfemaßnahmen in Office 365

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Da automatisierte Untersuchungen an E-Mail-& Inhalten für die Zusammenarbeit zu Bewertungen führen, z. B. *bösartig* oder *verdächtig,* werden bestimmte Abhilfemaßnahmen erstellt. In Microsoft Defender für Office 365 können Korrekturaktionen Folgendes umfassen:

- Blockieren einer URL (Uhrzeit des Klickens)
- Vorläufiges Löschen von E-Mail-Nachrichten oder Clustern
- Quarantinieren von E-Mails oder E-Mail-Anlagen
- Deaktivieren der externen E-Mail-Weiterleitung

Diese Korrekturmaßnahmen werden erst ausgeführt, wenn sie von Ihrem Sicherheitsteam genehmigt wurden. Es wird empfohlen, alle ausstehenden Aktionen so bald wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden. In einigen Fällen können Sie eine Korrekturaktion rückgängigmachen.

## <a name="approve-or-reject-pending-actions"></a>Genehmigen (oder Ablehnen) ausstehender Aktionen

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **das Info-Center** aus.
3. Überprüfen Sie auf der Registerkarte **"Ausstehend"** die Liste der Aktionen, die auf die Genehmigung warten.
4. W?hlen Sie ein Element in der Liste aus. Der Flyoutbereich wird geöffnet. 
5. Überprüfen Sie die Informationen im Flyoutbereich, und führen Sie dann einen der folgenden Schritte aus:
   - Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.
   - Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.
   - Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.

## <a name="change-or-undo-one-remediation-action"></a>Ändern oder Rückgängigmachen einer Korrekturaktion

1. Wechseln Sie zum Info-Center ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.
2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie ändern oder rückgängig machen möchten.
3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig"** aus.

## <a name="change-or-undo-multiple-remediation-actions"></a>Ändern oder Rückgängigmachen mehrerer Korrekturaktionen

1. Wechseln Sie zum Info-Center ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.
2. Wählen Sie auf der Registerkarte **"Verlauf"** die Aktionen aus, die Sie ändern oder rückgängig machen möchten. Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen. Ein Flyoutbereich wird geöffnet.
3. Wählen Sie im Flyoutbereich "Rückgängig" aus.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>So entfernen Sie eine Datei aus der Quarantäne auf mehreren Geräten

1. Wechseln Sie zum Info-Center ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.
2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Datei mit dem Aktionstyp **"Quarantänedatei"** aus.
3. Klicken Sie im Bereich auf der rechten Seite des **Bildschirms auf X weitere Instanzen dieser Datei anwenden,** und wählen Sie dann **Rückgängig** aus.

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden des Bedrohungs-Explorers](threat-explorer.md)
- [So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Siehe auch

- [Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365](air-view-investigation-results.md)
