---
title: Bereitstellen konfigurierbarer Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen konfigurierbarer Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Bereitstellung, mehrstufige Bereitstellung, konfigurierbare Einstellungen
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
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Bereitstellen und Nachverfolgen konfigurierbarer Einstellungen – Microsoft Managed Desktop

Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung bereitgestellt haben, können Sie auf der Seite Bereitstellungsstatus mit der Bereitstellung Ihrer Einstellungen für Gruppen beginnen. Diese Seite enthält eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen. Durch Öffnen einer Einstellungskategorie können Sie Einstellungen für Gruppen bereitstellen und den Fortschritt dieser Bereitstellungen nachverfolgen.

## <a name="deployment-statuses"></a>Bereitstellungsstatus 

Dies sind die Status, die Für jede Bereitstellung angezeigt werden.

Status  | Erklärung 
--- | --- 
Bereitstellen | Ihre Änderung wartet darauf, für diese Gruppe bereitgestellt zu werden.
In Arbeit | Die Änderung wird auf aktive Geräte in dieser Gruppe angewendet. 
Abschließen | Die Änderung wurde auf allen aktiven Geräten in dieser Gruppe abgeschlossen. 
Fehlgeschlagen | Die Änderung ist auf 10 Prozent der aktiven Geräte in der Gruppe fehlgeschlagen, sodass die Bereitstellung beendet wurde.<br><br> Eine Supportanfrage wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu beheben. 
Reverted | Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungsgruppen bereitgestellt wurde.

## <a name="deploy-changes"></a>Bereitstellen von Änderungen

In diesen Anweisungen wird das Desktophintergrundbild angezeigt. Nachdem Sie eine Bereitstellung bereitgestellt haben, stellen Sie Änderungen auf der Seite Bereitstellungsstatus zur Bereitstellung zur Bereitstellungsstatusseite zur Bereitstellungsstatusseite. 

**So stellen Sie Änderungen zur Bereitstellung**

1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie im** Arbeitsbereich Bereitstellungsstatus die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitstellungsstufige Bereitstellung aus.
4. Wählen **Sie Bereitstellen** aus, um die Änderung in einer der Bereitstellungsgruppen bereitstellen.

> [!NOTE] 
> Das orangefarbene Warnsymbol zeigt an, dass eine vorherige Gruppe für die Bereitstellung verfügbar ist, da es empfohlen wird, den Rollup in der Reihenfolge zu erstellen. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Es wird empfohlen, bereitstellungsgruppen in der reihenfolge: Test, First, Fast, and then Broad. 

Wenn die Änderungen in jeder Gruppe abgeschlossen sind, wird der Status in **Abgeschlossen geändert.**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Bereitstellung wiederherstellen

Nachdem Sie eine Änderung bereitgestellt haben, können Sie den Bereitstellungsstatus **wiederherstellen.** Wenn Sie eine Änderung wiederherstellen, die **in Bearbeitung ist** oder abgeschlossen **ist,** wird die aktuelle Bereitstellung beendet. Die Einstellung kehrt zur letzten Version zurück, die für alle Gruppen bereitgestellt wurde. 

Wir zeigen die Schritte zum Wiederherstellen einer Änderung mithilfe des Desktophintergrundbilds als Beispiel. 

**So wiederherstellen Sie eine Änderung**
1. Melden Sie sich bei [Microsoft Endpoint Manager an,](https://endpoint.microsoft.com/) und navigieren Sie zum **Menü Geräte**
2. Suchen Sie nach dem Abschnitt Microsoft Managed Desktop, wählen Sie **Einstellungen aus.**
3. Wählen **Sie im** Arbeitsbereich Bereitstellungsstatus die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die mehrstufige Bereitstellung aus, die wiederhergestellt werden soll.
4. Wählen **Sie unter Diese Änderung wiederherstellen?** die Option Bereitstellung **wiederherstellen aus.**

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md)
- [Referenz der konfigurierbaren Einstellungen](config-setting-ref.md) 
