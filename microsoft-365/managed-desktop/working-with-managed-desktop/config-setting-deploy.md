---
title: Bereitstellen von konfigurierbaren Einstellungen in Microsoft Managed Desktop
description: Bereitstellen und Nachverfolgen von Änderungen an konfigurierbaren Einstellungen in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, Deploy, Staging-Bereitstellung, konfigurierbare Einstellungen
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414168"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen – Microsoft Managed Desktop

Nachdem Sie Änderungen an den Einstellungskategorien vorgenommen und eine Bereitstellung ausgeführt haben, können Sie den Bereitstellungsstatus für die Bereitstellung bereitstellen und nachverfolgen. Auf dieser Seite wird eine Zusammenfassung der einzelnen konfigurierbaren Einstellungen angezeigt. Öffnen Sie eine Einstellungskategorie, um die einzelnen Bereitstellungen und Ihre Details anzuzeigen, um die Änderungen bereitzustellen. 

## <a name="deployment-statuses"></a>Bereitstellungsstatus 

Dies sind die Statuen, die für jede Bereitstellung angezeigt werden.

Status  | Erklärung 
--- | --- 
Bereitstellen | Ihre Änderung wartet auf die Bereitstellung für diesen Ring.
In Arbeit | Die Änderung wird auf aktive Geräte in diesem Ring angewendet. 
Abschließen | Die Änderung, die für alle aktiven Geräte in diesem Ring abgeschlossen wurde. 
Failed | Die Änderung ist bei 10 Prozent der aktiven Geräte im Ring fehlgeschlagen, sodass die Bereitstellung angehalten wurde.<br><br> Eine Supportanforderung wird automatisch mit Microsoft Managed Desktop-Vorgängen geöffnet, um die Bereitstellung zu behandeln. 
Zurückgesetzt | Die Änderung wurde auf die letzte Änderung zurückgesetzt, die erfolgreich für alle Bereitstellungs Ringe bereitgestellt wurde.

## <a name="deploy-changes"></a>Bereitstellen von Änderungen

In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt. Nachdem Sie eine Bereitstellung inszeniert haben, stellen Sie Änderungen aus dem Bereitstellungsstatus bereit. 

**So stellen Sie Änderungen bereit**

1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie bereitstellen möchten, und wählen Sie dann die bereitgestellte Bereitstellung mit Staging aus.
4. Wählen Sie **Bereitstellen** aus, um die Änderung an einem der Bereitstellungs Ringe bereitzustellen.

![Bereitstellungsstatus für konfigurierbare Einstellungen (Übersicht)](images/deploy-cs-overview.png)

Microsoft Managed Desktop empfiehlt die Bereitstellung in Bereitstellungs Ringen in dieser Reihenfolge: Test, First, fast und dann Broad. 

Wenn in jedem Ring Änderungen vorgenommen werden, wird der Status in **abgeschlossen**geändert.

![Vollständige Bereitstellung von konfigurierbaren Einstellungen](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Wiederherstellen der Bereitstellung

In diesen Anweisungen wird das Hintergrundbild des Desktops angezeigt. 

Nachdem Sie eine Änderung bereitgestellt haben, können Sie den **Bereitstellungsstatus**wiederherstellen. Wenn Sie eine Änderung zurücksetzen, die gerade **ausgeführt** wird oder **abgeschlossen**ist, wird die aktuelle Bereitstellung angehalten. Die Einstellung wird auf die letzte Version zurückgesetzt, die für alle Ringe bereitgestellt wurde. 

**So stellen Sie eine Änderung wieder her**
1. Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)
2. Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.
3. Wählen Sie im **Bereitstellungsstatus** -Arbeitsbereich die Einstellung aus, die Sie wiederherstellen möchten, und wählen Sie dann die wiederherzustellende Staging-Bereitstellung aus.
4. Wenn Sie **diese Änderung rückgängig**machen möchten, wählen Sie **Bereitstellung zurück**setzen aus.

![Konfigurierbare Einstellungen werden wiederhergestellt](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Übersicht über konfigurierbare Einstellungen](config-setting-overview.md)
- [Referenz zu konfigurierbaren Einstellungen](config-setting-ref.md) 