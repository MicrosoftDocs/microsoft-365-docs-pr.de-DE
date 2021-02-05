---
title: Verwalten von Themen im Themencenter in Microsoft Topics
description: Verwalten von Themen im Themencenter.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107186"
---
# <a name="manage-topics-in-the-topic-center"></a>Verwalten von Themen im Themencenter 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


Im Themencenter "Aktuelle Themen" kann  ein Knowledge Manager die Seite "Themen verwalten" anzeigen, um Themen zu überprüfen, die in den Von Ihrem Wissensadministrator angegebenen Speicherorten für die SharePoint-Quelle identifiziert wurden.  

   ![Themencenter](../media/knowledge-management/topic-center.png) </br> 



Knowledge Manager unterstützen Sie dabei, ermittelte Themen durch den Themenlebenszyklus zu führen, in dem folgende Themen enthalten sind:

- Vorgeschlagen: Ein Thema wurde von AI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften.
- Bestätigt: Ein Thema, das von AI vorgeschlagen wurde, wird überprüft. Die Überprüfung erfolgt durch Bestätigung durch einen Knowledge Manager. Darüber hinaus kann ein Thema bestätigt werden, wenn mindestens zwei Benutzer über die Feedbackfrage auf der Themenkarte positives Feedback geben.
- Veröffentlicht: Ein bestätigtes Thema, das behandelt wurde: Es wurden manuelle Änderungen vorgenommen, um die Qualität zu verbessern.
- Entfernt: Ein Thema wird von einem Knowledge Manager abgelehnt und ist für Die Besucher nicht mehr sichtbar. Das Thema kann in einem beliebigen Status sein, wenn es entfernt wird (vorgeschlagen, bestätigt oder veröffentlicht). Wenn ein veröffentlichtes Thema entfernt wird, muss die Seite mit den behandelten Details manuell über die Seitenbibliothek des Themencenters gelöscht werden.

   ![Diagramm "Themenlebenszyklus"](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Auf der Seite "Themen verwalten" kann jeder Knowledge Manager nur Themen anzeigen, in denen er Zugriff auf die Dateien und Seiten des Themas hat. Dies wird in den Themen wider, die unter den Registerkarten "Vorgeschlagen", "Bestätigt", "Entfernt" und "Veröffentlicht" aufgeführt sind. Die Themenanzahl zeigt jedoch die Gesamtanzahl in der Organisation an.

## <a name="requirements"></a>Anforderungen

Um Themen im Themencenter zu verwalten, müssen Sie:
- Sie verfügen über eine Lizenz für "Topics".

- Die Berechtigung [**"Wer kann Themen verwalten"**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) haben. Wissensadministratoren können Benutzern diese Berechtigung in den Themen "Themen" erteilen. 

Die Seite "Themen verwalten" kann nur dann im Themencenter angezeigt werden, wenn Sie über die Berechtigung "Wer kann Themen **verwalten"** verfügt.

Im Themencenter kann ein Knowledge Manager Themen überprüfen, die an den von Ihnen angegebenen SharePoint-Quellstandorten identifiziert wurden, und diese entweder bestätigen oder ablehnen. Ein Wissensmanager kann auch neue Themenseiten erstellen und veröffentlichen, wenn diese bei der Themenermittlung nicht gefunden wurden, oder vorhandene bearbeiten, wenn sie aktualisiert werden müssen.


## <a name="review-suggested-topics"></a>Überprüfen der vorgeschlagenen Themen

Auf der Seite "Themen im Themencenter verwalten" werden Themen, die in den angegebenen Speicherorten für die SharePoint-Quelle gefunden wurden, auf der Registerkarte **"Vorgeschlagen"** aufgeführt. Bei Bedarf kann ein Knowledge Manager nicht bestätigte Themen überprüfen und diese bestätigen oder ablehnen.

   ![Vorgeschlagene Themen](../media/knowledge-management/quality-score.png) </br> 

So überprüfen Sie ein vorgeschlagenes Thema:

1. Wählen Sie auf der Seite "Themen **verwalten"** die Registerkarte **"Vorgeschlagen"** aus, und wählen Sie das Thema aus, um die Themenseite zu öffnen.</br>

2. Überprüfen Sie auf der Themenseite die  Themenseite, und wählen Sie "Bearbeiten" aus, wenn Sie Änderungen an der Seite vornehmen müssen. Wenn Sie alle Bearbeitungen veröffentlichen, wird dieses Thema auf die Registerkarte **"Veröffentlicht"** verschieben.

3. Wechseln Sie nach der Überprüfung des Themas zurück zur Seite "Themen verwalten". Für das ausgewählte Thema können Sie:

   - Aktivieren Sie das Kontrollkästchen, um das Thema zu bestätigen.
    
   - Wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.

    Bestätigte Themen werden aus der **Vorgeschlagenen** Liste entfernt und nun in der Liste **"Bestätigt"** angezeigt.

    Abgelehnte Themen werden aus der Liste **"Vorgeschlagen"** entfernt und nun auf der Registerkarte **"Entfernt"** angezeigt.

   </br> 

### <a name="quality-score"></a>Qualitätsergebnis

Jedem Thema, das auf der Seite "Vorgeschlagene Themen" angezeigt wird, ist eine <b>Qualitätsergebnis</b> zugewiesen. Die Qualitätsergebnis ist eine Spiegelung der Informationsmenge, die dem durchschnittlichen Benutzer für die Informationen zu diesem Thema angezeigt wird, und dabei berücksichtigen, dass jedem Benutzer aufgrund der Berechtigungen, die er für die Informationen in einem Thema hat, möglicherweise mehr oder weniger Informationen angezeigt werden. 

Die Qualitätsergebnis kann helfen, Einblicke in die Themen mit den meisten Informationen zu erhalten, und kann hilfreich sein, um Themen zu finden, die möglicherweise manuell bearbeitet werden müssen.  Beispielsweise kann ein Thema mit einer niedrigeren Qualitätssentwertung das Ergebnis sein, dass einige Benutzer keine SharePoint-Berechtigungen für relevante Dateien oder Websites haben, die ai in das Thema eingeschlossen hat. Ein Mitwirkender könnte dann das Thema bearbeiten, um die Informationen (falls angemessen) zu enthalten, die dann für alle Benutzer angezeigt werden können, die das Thema anzeigen können.

Die Qualität kann zwischen 1 und 100 liegen. Ein neu gefundenes Thema hat eine Qualitätsnote von 0, bis zwei oder mehr Benutzer es angezeigt haben. Die Qualität der einzelnen Benutzer wird durch eine Reihe von Faktoren bestimmt, z. B. durch die Menge der Inhalte, die für den bestimmten Benutzer angezeigt werden. Dies wird durch die Berechtigungen des Benutzers gesteuert, da auf jeder Themenseite Sicherheitstrimmer für von AI generierte Inhalte festgelegt sind. Die auf der Registerkarte "Vorgeschlagene Themen" angezeigte Qualitätsergebnis ist ein Durchschnittswert der einzelnen Benutzer.

### <a name="impressions"></a>Impressionen

In <b>der</b> Spalte "Anzeigen" wird angezeigt, wie oft ein Thema endbenutzern angezeigt wurde. Dazu gehören Ansichten über Themenkarten in der Suche, über Themenhighlights und über Themencenteransichten. Das Click-Through-Thema in diesen Themen wird nicht dargestellt, aber das Thema wurde angezeigt. Die Spalte "Impressionen" wird für Themen auf den Registerkarten "Vorgeschlagen", "Bestätigt", "Veröffentlicht" und "Entfernt" auf der Seite "Themen verwalten" angezeigt.


## <a name="confirmed-topics"></a>Bestätigte Themen

Auf der Seite "Themen verwalten" werden Themen, die an den angegebenen Speicherorten für die SharePoint-Quelle gefunden wurden und von einem  Knowledge Manager bestätigt wurden oder von zwei oder mehr Personen über den Kartenfeedbackmechanismus bestätigt wurden, auf der Registerkarte "Bestätigt" aufgeführt. Bei Bedarf kann ein Benutzer mit Berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und ablehnen.

So überprüfen Sie ein bestätigtes Thema:

1. Wählen Sie **auf der** Registerkarte "Bestätigt" das Thema aus, um die Themenseite zu öffnen.</br>

2. Überprüfen Sie auf der Themenseite die  Themenseite, und wählen Sie "Bearbeiten" aus, wenn Sie Änderungen an der Seite vornehmen müssen.

Beachten Sie, dass Sie ein bestätigtes Thema weiterhin ablehnen können.  Wechseln Sie dazu zum ausgewählten Thema in der Liste "Bestätigt", und wählen Sie das **x** aus, wenn Sie das Thema ablehnen möchten.

## <a name="published-topics"></a>Veröffentlichte Themen
Veröffentlichte Themen wurden bearbeitet, sodass immer bestimmte Informationen angezeigt werden, die auf die Seite stoßen. Hier werden auch manuell erstellte Themen aufgelistet.

   ![Verwalten von Themen](../media/knowledge-management/manage-topics-new.png) </br> 




