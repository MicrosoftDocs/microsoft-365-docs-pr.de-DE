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

Bevor Sie die APP-Steuerung in Ihrer Umgebung aktivieren, sollten Sie sich vergewissern, [wie Sie von Microsoft Managed Desktop implementiert](../service-description/app-control.md) wird und welche Rollen und Zuständigkeiten Sie haben.

Microsoft Managed Desktop vereinfacht die APP-Steuerung, indem es die anspruchsvolleren Aspekte beim Erhalt einer sicheren Basisrichtlinie berücksichtigt. Ihre IT-Administratoren müssen Ihre apps weiterhin im testring testen und die Protokolle auf Warnungen oder Fehler überprüfen. Wenn eine APP eine Ausnahme benötigt, können Sie eine Anforderung oder eine von Microsoft verwaltete Desktop Operation möglicherweise in Abhängigkeit davon, wer Sie zuerst erkennt, einreichen.

## <a name="initial-deployment-of-apps"></a>Erstbereitstellung von apps

Wenn Sie Apps zum ersten Mal bereitstellen, muss Microsoft Managed Desktop das aktuelle Verhalten bewerten. Die genauen Schritte zum Aktivieren der APP-Steuerung hängen davon ab, ob in Ihrer Umgebung bereits Geräte bereitgestellt wurden.

### <a name="devices-not-yet-in-use"></a>Noch nicht verwendete Geräte

Wenn Sie noch keine Geräte in Gebrauch haben, öffnen Sie ein Service Ticket bei Microsoft Managed Desktop Operations, in dem Sie aufgefordert werden, das App-Steuerelement einzuschalten. Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:

|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Tag 2       |
|Allgemein     | Enforced        |  Tag 3       |

Sie können jederzeit während des Rollouts eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder zurückzusetzen.

### <a name="devices-already-in-use"></a>Bereits verwendete Geräte

Wenn bereits mindestens ein von Microsoft verwaltetes Desktop Gerät verwendet wird, führen Sie die folgenden Schritte aus:

1. Öffnen Sie ein Service Ticket bei Microsoft Managed Desktop Operations, in dem Sie aufgefordert werden, das App-Steuerelement einzuschalten. Der Vorgang stellt eine [Überwachungsrichtlinie](../service-description/app-control.md#audit-policy) für alle Geräte bereit.
2. [Testen Sie Ihre Anwendungen](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) , um festzustellen, ob alle blockiert wären. Wenn eine Anwendung blockiert werden würde, öffnen Sie eine [Signaturer-Anforderung](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Nachdem Sie Ihre Tests (unabhängig von den Ergebnissen) abgeschlossen haben, Benachrichtigen Sie die Vorgänge und notieren Sie alle ausstehenden Signaturanforderungen. Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:

|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Angehalten, Rollout auf Anforderung       |
|Allgemein     | Enforced        |  Angehalten, Rollout auf Anforderung       |

Sie können jederzeit während des Rollouts eine andere Dienstanforderung öffnen, um einen Teil dieser Bereitstellung anzuhalten oder zurückzusetzen.



