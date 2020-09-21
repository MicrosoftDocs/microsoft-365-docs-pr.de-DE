---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104534"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop

Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie mit der Seite Bereitstellungsstatus die Bereitstellung Ihrer Einstellungen für Gruppen beginnen. Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt. Wenn Sie eine Einstellungskategorie öffnen, können Sie Einstellungen für Gruppen bereitstellen und den Status dieser Bereitstellungen nachverfolgen.

## <a name="deployment-statuses"></a>Bereitstellungsstatus 

Dies sind die Status, die Sie für jede Bereitstellung sehen.

Status  | Erklärung 
--- | --- 
Bereitstellen | Ihre Änderung wartet auf die Bereitstellung für diese Gruppe.
In Arbeit | Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet. 
Abschließen | Die Änderung, die für alle aktiven Geräte in dieser Gruppe abgeschlossen wurde. 
Fehlgeschlagen | Die Änderung konnte auf 10 Prozent der aktiven Geräte in der Gruppe nicht ausgeführt werden, sodass die Bereitstellung angehalten wurde.<br><br> Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop Operations geöffnet, um die Bereitstellung zu beheben. 
Zurückgesetzt | Die Änderung wurde auf die letzte Änderung zurückgesetzt, die für alle Bereitstellungsgruppen erfolgreich bereitgestellt wurde.

## <a name="deploy-changes"></a>Bereitstellen von Änderungen

In diesen Anweisungen wird ein Desktop Hintergrundbild angezeigt. Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie die Änderungen auf der Seite Bereitstellungsstatus bereit. 

**So stellen Sie Änderungen bereit**

1. Melden Sie sich bei [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) an, und navigieren Sie zum Menü **Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, und wählen Sie **Einstellungen**aus.
3. Wählen Sie im Bereich **Bereitstellungsstatus** die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung aus.
4. Wählen Sie **Bereitstellen** aus, um die Änderung an einer der Bereitstellungsgruppen bereitzustellen.

> [!NOTE] 
> Das orangefarbene Warnsymbol zeigt an, dass für die Bereitstellung eine frühere Gruppe zur Verfügung steht, da es empfehlenswert ist, das Rollout in der richtigen Reihenfolge auszuführen. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Wir empfehlen die Bereitstellung in Bereitstellungsgruppen in dieser Reihenfolge: Test, erste, schnelle und dann breit. 

Wenn Änderungen in jeder Gruppe abgeschlossen werden, ändert sich der Status in **abgeschlossen**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Wiederherstellen der Bereitstellung

Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen. Wenn Sie eine gerade **ausgeführte** oder **abgeschlossene**Änderung wiederherstellen, wird die aktuelle Bereitstellung angehalten. Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Gruppen bereitgestellt wurde. 

Wir zeigen die Schritte zum Rückgängigmachen einer Änderung mithilfe des Desktop Hintergrundbilds als Beispiel. 

**So stellen Sie eine Änderung wieder her**
1. Melden Sie sich bei [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) an, und navigieren Sie zum Menü **Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, und wählen Sie **Einstellungen**aus.
3. Wählen Sie im Arbeitsbereich **Bereitstellungsstatus** die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung aus, die wiederhergestellt werden soll.
4. Wählen Sie unter **Notwendigkeit, diese Änderung wiederherzustellen?** die Option **Bereitstellung rückgängig**machen aus.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Weitere Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md)
- [Referenz der konfigurierbaren Einstellungen](config-setting-ref.md) 
