---
title: Ein- und Ausblenden neuer Funktionen mit What's New Management
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Entscheiden Sie, welche Features und welche neuen Inhalte den Endbenutzern in der Office-Seite What es New Management for Office Desktop Apps angezeigt oder verborgen sind.
ms.openlocfilehash: 7399da493f8e6878a92dc13d92482d7ddece0ba3
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011699"
---
# <a name="show-or-hide-new-features-using-whats-new-management"></a>Ein- und Ausblenden neuer Funktionen mit What's New Management

Office What es New Management für Win 32 ermöglicht Ihrer Organisation zu entscheiden, welche Features in der Office-Desktop-App für Endbenutzer angezeigt oder ausgeblendet werden. Jede Version von Office enthält neue und verbesserte Features, und mit der Inhaltsvorschau können Sie neue Inhalte für jede Releaseversion und jeden Kanal anzeigen und auswählen, ob die neuen Inhalte für jedes Feature für Endbenutzer ausgeblendet oder angezeigt werden sollen. 

Die neuen Inhalte in den Office-Desktop-Apps heben eine kuratierte Liste der neuen Features hervor, die für diese Anwendung veröffentlicht werden, mit einer kurzen Beschreibung und oft mit einem Bild oder einem Video, das von dem Team erstellt wurde, das das Feature zur Verfügung stellt, damit Kunden erfahren, wie Sie das Feature verwenden können. 

Office What es New Management steht im Microsoft 365 Admin Center und über den [Client Konfigurationsdienst](https://config.office.com)zur Verfügung.

> [!NOTE]
> Administratorrollen für globale Administratoren und Office-Apps verwalten die neuen Inhalte, die Benutzern in Ihren Office-Apps angezeigt werden.

##  <a name="show-or-hide-new-features"></a>Anzeigen oder ausblenden neuer Features 

Administratoren können eine Vorschau der neuen Inhalte für einen Kanal anzeigen und die Veröffentlichung der Inhalte mithilfe von Office What es New Management verwalten.

1. Wählen Sie im Microsoft 365 Admin Center unter **Einstellungen**die Option **Einstellungen**aus.

2. Wählen Sie auf der Registerkarte **Dienste** die Option **Office What es New Management**aus.

3. Wählen Sie ein oder mehrere Features aus, um den Featurenamen, eine kurze Beschreibung, die Anwendung und die Veröffentlichungsversion für jedes Feature im Flyout-Fenster anzuzeigen.

4. Wählen Sie **aus Benutzer ausblenden** oder **Benutzern anzeigen**aus.  

    Der **standardmäßig angezeigte** Status gibt an, dass Featureinformationen standardmäßig für Benutzer angezeigt werden, bis der Administrator den Status für ein Feature auf " **ausgeblendet** " oder " **angezeigt**" festlegt.  

    > [!NOTE]
    > Wenn ein Feature in mehreren Office-Apps verfügbar ist, blendet das Feature auf ausgeblendet festlegen die Feature-Ansage in allen Office-Apps aus.

Neue Features werden in Office What es New Management basierend auf diesem Zeitplan angezeigt:

||||
|:-----|:-----|:-----|
|**Kanal** <br/> |**In der Verwaltungs Vorschau** <br/> |**Aktion ausführen** <br/> |
|**Monatlich** <br/> |15. des Monats  <br/> |1-3 Wochen vor der monatlichen Veröffentlichung <br/> |
|**Halbjährlich (gezielt)** <br/> |1. September und 1. März <br/> | 2 Wochen vor der Hauptversion, die neue Features bringt
|**Halbjährlich** <br/> |1. Januar und 1. Juli <br/> | 2 Wochen vor der Hauptversion, die neue Features bringt<br/> |

Weitere Informationen zu Kanal Aktualisierungs Plänen finden Sie unter [Update History for Microsoft 365 Apps (aufgelistet nach Datum)](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date).

## <a name="related-articles"></a>Verwandte Artikel

[Office What es New Management ist jetzt allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)