---
title: Gerätebereitstellungsgruppen
description: Die Bereitstellungsgruppen, die zum Verwalten von Updates und anderen Änderungen verwendet werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985581"
---
# <a name="device-deployment-groups"></a>Gerätebereitstellungsgruppen

Microsoft Managed Desktop verwendet Bereitstellungsgruppen, um die Veröffentlichung von Updates und Konfigurationsänderungen an Geräten zu verwalten. Geräte werden Bereitstellungsgruppen ("Ringe" oder "Updategruppen") automatisch hinzugefügt, wenn sie bei Microsoft Managed Desktop registriert sind. Bereitstellungsgruppen ermöglichen es Geräten, Änderungen in einer phasenweisen Zeitachse zu empfangen.

Möglicherweise möchten Sie bestimmte Geräte nur zu Testzwecken zuweisen oder bestimmte Early Adopter dafür festlegen, dass sie die Änderungen zuerst erhalten. Wenn Sie über kritische Geräte verfügen, z. B. diejenigen, die von Führungskräften verwendet werden, oder die geschäftskritische Funktionen ausführen, sollten Sie sie in der Gruppe behalten, die Updates im langsamsten Rhythmus erhält. Microsoft Managed Desktop können Sie angeben, dass ein Gerät in einer der folgenden Gruppen verbleiben soll.

- **Test:** am besten für Geräte, die für Tests oder Benutzer verwendet werden, die häufige Änderungen und die Gefährdung durch neue Features tolerieren und auch frühzeitigEs Feedback geben können. Diese Gruppe empfängt häufig Änderungen, und die Erfahrungen in dieser Gruppe haben eine starke Auswirkung. Die Testgruppe ist von allen vereinbarungen zum Servicelevel und vom Benutzersupport ausgenommen. Es empfiehlt sich, zunächst nur einige Geräte zu verschieben und dann die Benutzererfahrung zu überprüfen. Microsoft Managed Desktop werden dieser Gruppe nicht automatisch Geräte zuweisen. Sie verfügt nur über Geräte, die Sie angeben.
- **Erstens:** ideal für Early Adopter, Freiwilligen oder designierte Validierer, IT-Spezialisten oder Vertreter von Geschäftsfunktionen, d. h. Für Personen, die Änderungen überprüfen und Ihnen Feedback zu dieser Erfahrung geben können.
- **Broad** empfängt zuletzt Änderungen. Der Großteil Ihrer Organisation befindet sich in der Regel in dieser Gruppe. Sie können auch Geräte angeben, die sich in dieser Gruppe befinden müssen und nur zuletzt Änderungen erhalten sollen, da sie geschäftskritische Funktionen ausführen oder Benutzern in kritischen Rollen angehören. 
- **Automatisch:** Wählen Sie diese Option aus, wenn Microsoft Managed Desktop einer der anderen Gruppen automatisch Geräte zuweisen möchten. (Wir weisen Test nicht automatisch Geräte zu.) Wenn Sie ein zuvor angegebenes Gerät freigeben möchten, damit es automatisch erneut zugewiesen werden kann, wählen Sie diese Option aus. 

Microsoft Managed Desktop verwendet einige zusätzliche Gruppen zum Steuern von Bereitstellungen, Sie können ihnen jedoch keine Geräte zuweisen. Sie können jedoch Geräte aus diesen Gruppen in eine der Gruppen in diesem Artikel verschieben. Weitere Informationen dazu, wie Windows Updates in Gruppen verwaltet werden, finden Sie unter [So werden Updates in Microsoft Managed Desktop behandelt.](updates.md)

Wenn sich ein Gerät in einer gruppe befindet, die Sie angegeben haben, sagt die **gruppe, die von** **"Admin"** zugewiesen wurde. Wenn Microsoft Managed Desktop die Gruppe zugewiesen hat, **wird** automatisch angezeigt. Während ein Gerät gerade zu einer Gruppe wechselt, heißt es **"Ausstehend".** Das **Gruppenfeld** zeigt immer die Gruppe an, in der sich das Gerät derzeit befindet, und wird nur aktualisiert, wenn eine Verschiebung abgeschlossen ist.

> [!IMPORTANT]
> Versuchen Sie nicht, die Mitgliedschaft dieser Gruppen direkt zu ändern. Führen Sie immer die unter ["Zuweisen von Geräten zu einer Bereitstellungsgruppe"](../working-with-managed-desktop/assign-deployment-group.md)beschriebenen Schritte aus.
