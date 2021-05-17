---
title: Erste Schritte mit dem App-Steuerelement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430459"
---
# <a name="get-started-with-app-control"></a>Erste Schritte mit dem App-Steuerelement

Bevor Sie die App-Steuerung in Ihrer Umgebung aktivieren, sollten Sie überprüfen und verstehen, [wie](../service-description/app-control.md) Microsoft Managed Desktop und Ihre Rollen und Verantwortlichkeiten implementiert werden.

Microsoft Managed Desktop vereinfacht die App-Steuerung, indem die anspruchsvolleren Aspekte einer sicheren Basisrichtlinie berücksichtigt werden. Ihre IT-Administratoren müssen Ihre Apps weiterhin im Testring testen und die Protokolle auf Warnungen oder Fehler überprüfen. Wenn eine App eine Ausnahme benötigt, können Sie eine Anforderung oder eine Microsoft Managed Desktop Operation, je nachdem, wer sie zuerst erkennt.

## <a name="initial-deployment-of-apps"></a>Erstbereitstellung von Apps

Bei der ersten Bereitstellung von Apps müssen Microsoft Managed Desktop das aktuelle Verhalten bewerten. Die genauen Schritte zum Aktivieren der App-Steuerung hängen davon ab, ob geräte bereits in Ihrer Umgebung bereitgestellt wurden.

### <a name="devices-not-yet-in-use"></a>Noch nicht verwendete Geräte

Wenn Sie noch keine Geräte verwenden, öffnen Sie ein Dienstticket mit Microsoft Managed Desktop Vorgängen, die das Aktivieren der App-Steuerung anfordern. Im Anschluss an diesen Zeitplan werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt:

|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Tag 2       |
|Allgemein     | Enforced        |  Tag 3       |

Sie können während des Rollouts immer eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder ein Rollback zu erstellen.

### <a name="devices-already-in-use"></a>Geräte, die bereits verwendet werden

Wenn bereits mindestens ein Microsoft Managed Desktop verwendet wird, führen Sie die folgenden Schritte aus:

1. Öffnen Sie ein Dienstticket mit Microsoft Managed Desktop Vorgänge, die das Aktivieren der App-Steuerung anfordern. Vorgänge stellen eine [Überwachungsrichtlinie auf](../service-description/app-control.md#audit-policy) allen Geräten zur Verfügung.
2. [Testen Sie Ihre Anwendungen,](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) um zu sehen, ob eine blockiert werden würde. Wenn eine Anwendung blockiert würde, öffnen Sie eine [Signieranforderung](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Nachdem Sie die Tests abgeschlossen haben (unabhängig von den Ergebnissen), benachrichtigen Sie Operations, und notieren Sie sich alle ausstehenden Signieranforderungen. Im Anschluss an diesen Zeitplan werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt:

|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Angehalten, Rollout auf Anfrage       |
|Allgemein     | Enforced        |  Angehalten, Rollout auf Anfrage       |

Sie können während des Rollouts immer eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder ein Rollback zu erstellen.



