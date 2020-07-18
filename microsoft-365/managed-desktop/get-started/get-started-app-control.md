---
title: Erste Schritte mit App-Steuerelement
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170709"
---
# <a name="get-started-with-app-control"></a>Erste Schritte mit App-Steuerelement

Bevor Sie die APP-Steuerung in Ihrer Umgebung aktivieren, sollten Sie sich vergewissern, [wie Sie von Microsoft Managed Desktop implementiert](../service-description/app-control.md) wird und welche Rollen und Zuständigkeiten Sie haben.

Microsoft Managed Desktop vereinfacht die APP-Steuerung, indem es die anspruchsvolleren Aspekte beim Erhalt einer sicheren Basisrichtlinie berücksichtigt. Ihre IT-Administratoren müssen Ihre apps weiterhin im testring testen und die Protokolle auf Warnungen oder Fehler überprüfen. Wenn eine APP eine Ausnahme benötigt, können Sie eine Anforderung oder eine von Microsoft verwaltete Desktop Operation möglicherweise in Abhängigkeit davon, wer Sie zuerst erkennt, einreichen.

## <a name="initial-deployment-of-apps"></a>Erstbereitstellung von apps

Wenn Sie Apps zum ersten Mal bereitstellen, muss Microsoft Managed Desktop das aktuelle Verhalten bewerten. Die genauen Schritte zum Aktivieren der APP-Steuerung hängen davon ab, ob in Ihrer Umgebung bereits Geräte bereitgestellt wurden.

### <a name="devices-already-in-use"></a>Bereits verwendete Geräte

Wenn bereits mindestens ein von Microsoft verwaltetes Desktop Gerät verwendet wird, führen Sie die folgenden Schritte aus:

1. Öffnen Sie ein Service Ticket bei Microsoft Managed Desktop Operations, in dem Sie aufgefordert werden, das App-Steuerelement einzuschalten. Der Vorgang stellt eine [Überwachungsrichtlinie](../service-description/app-control.md#audit-policy) für alle Geräte bereit.
2. [Testen Sie Ihre Anwendungen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) , um festzustellen, ob alle blockiert wären. Wenn eine Anwendung blockiert werden würde, öffnen Sie eine [Signaturer-Anforderung](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Nachdem Sie Ihre Tests (unabhängig von den Ergebnissen) abgeschlossen haben, Benachrichtigen Sie die Vorgänge und notieren Sie alle ausstehenden Signaturanforderungen. Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:

|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Tag 3       |
|Allgemein     | Enforced        |  Tag 7       |

Sie können jederzeit während des Rollouts eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder zurückzusetzen.

### <a name="devices-not-yet-in-use"></a>Noch nicht verwendete Geräte

Wenn Sie noch keine Geräte in Gebrauch haben, öffnen Sie ein Service Ticket bei Microsoft Managed Desktop Operations, in dem Sie aufgefordert werden, das App-Steuerelement einzuschalten. Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:

|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Tag 3       |
|Allgemein     | Enforced        |  Tag 7       |

Sie können jederzeit während des Rollouts eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder zurückzusetzen.

