---
title: Verwalten von Themen im Themencenter in Microsoft Viva Topics
description: Verwalten von Themen im Topic Center.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 4532f5685fdde7c89ca59e5c22e1ad8afdf2b112
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904034"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Verwalten von Themen im Themencenter in Microsoft Viva Topics

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


Im Themencenter "Viva Topics" kann  ein Wissensmanager die Seite Themen verwalten anzeigen, um Themen zu überprüfen, die in den Quellstandorten identifiziert wurden, wie von Ihrem Wissensadministrator angegeben.  

   ![Topic Center](../media/knowledge-management/topic-center.png) </br> 



Knowledge Manager unterstützen Sie dabei, ermittelte Themen durch die verschiedenen Phasen des Themenlebenszyklus zu führen:

- **Vorgeschlagen:** Ein Thema wurde von AI identifiziert und verfügt über genügend unterstützende Ressourcen, Verbindungen und Eigenschaften.
- **Bestätigt**: Ein Thema, das von AI vorgeschlagen wurde, wird überprüft. Die Überprüfung erfolgt durch Bestätigung durch einen Knowledge Manager. Darüber hinaus kann ein Thema bestätigt werden, wenn es eine netto positive 2 Stimmen von Endbenutzern gibt, die über die Feedbackmechanismen auf der Themenkarte empfangen werden.
- **Veröffentlicht**: Ein bestätigtes Thema, das kuratiert wurde: Manuelle Bearbeitungen wurden vorgenommen, um die Qualität zu verbessern.
- **Entfernt:** Ein Thema wird von einem Wissensmanager abgelehnt und ist für die Betrachter nicht mehr sichtbar. Das Thema kann sich in einem beliebigen Zustand befindet, wenn es entfernt wird (vorgeschlagen, bestätigt oder veröffentlicht). Wenn ein veröffentlichtes Thema entfernt wird, muss die Seite mit den kuratierten Details manuell über die Seitenbibliothek des Themencenters gelöscht werden.

   ![Topic-Lifecycle-Diagramm](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Auf der Seite Themen verwalten kann jeder Wissensmanager nur Themen anzeigen, in denen er Zugriff auf die zugrunde liegenden Dateien und Seiten hat, die mit dem Thema verbunden sind. Diese Berechtigungstrimmerung wird in der Liste der Themen angezeigt, die auf den Registerkarten **Vorgeschlagen,** **Bestätigt,** **Entfernt** und **Veröffentlicht** angezeigt werden. Die Anzahl der Themen zeigt jedoch unabhängig von berechtigungen die Gesamtzahlen in der Organisation an.

## <a name="requirements"></a>Anforderungen

Zum Verwalten von Themen im Themencenter müssen Sie:
- Verfügen Sie über eine Lizenz für "Viva Topics".

- Verfügen Sie über [**die Berechtigung Wer kann Themen**](./topic-experiences-user-permissions.md) verwalten. Knowledge admins can give users this permission in the Viva Topics topic permissions settings. 

Sie können die Seite Themen verwalten nicht im Themencenter anzeigen, es sei denn, Sie verfügen über die Berechtigung **Wer kann Themen verwalten.**

Im Themencenter kann ein Wissensmanager Themen überprüfen, die an den von Ihnen angegebenen Quellstandorten identifiziert wurden, und diese entweder bestätigen oder ablehnen. Ein Knowledge Manager kann auch neue Themenseiten erstellen und veröffentlichen, wenn sie nicht in der Themensuche gefunden wurden, oder vorhandene Bearbeiten, wenn sie aktualisiert werden müssen.


## <a name="review-suggested-topics"></a>Überprüfen der vorgeschlagenen Themen

Auf der Seite Themen verwalten des Themencenters werden Themen, die in Den angegebenen SharePoint-Quellstandorten gefunden wurden, auf der Registerkarte **Vorgeschlagen** aufgeführt. Bei Bedarf kann ein Wissensmanager unbestätigte Themen überprüfen und diese bestätigen oder ablehnen.

   ![Vorgeschlagene Themen](../media/knowledge-management/quality-score.png) </br> 

So überprüfen Sie ein vorgeschlagenes Thema:

1. Wählen Sie **auf der Seite** Themen verwalten die Registerkarte **Vorgeschlagen** aus, wählen Sie das Thema aus, um die Themenseite zu öffnen.</br>

2. Überprüfen Sie auf der Themenseite die Themenseite, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen. Wenn Sie alle Bearbeitungen veröffentlichen, wird dieses Thema auf die Registerkarte **Veröffentlicht** verschieben.

3. Nachdem Sie das Thema überprüft haben, wechseln Sie zurück zur Seite Themen verwalten. Für das ausgewählte Thema können Sie:

   - Aktivieren Sie das Häkchen, um das Thema zu bestätigen.
    
   - Wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.

    Bestätigte Themen werden aus der **Vorgeschlagenen** Liste entfernt und werden nun in der **Liste Bestätigt** angezeigt.

    Abgelehnte Themen werden aus der Liste Vorgeschlagen **entfernt** und werden nun auf der Registerkarte **Entfernt** angezeigt.

   </br> 

### <a name="quality-score"></a>Qualitätsergebnis

Jedem Thema, das auf der Seite Vorgeschlagene Themen angezeigt wird, wird eine Qualitätsnote zugewiesen. Die Qualitätskontrolle spiegelt die Informationsmenge wider, die dem durchschnittlichen Benutzer für die Informationen zu diesem Thema angezeigt wird, und dabei zu berücksichtigen, dass für jeden Benutzer aufgrund der Berechtigungen, die er möglicherweise für die Informationen in einem Thema hat, mehr oder weniger Informationen angezeigt werden. 

Die Qualitätsnote kann einen Einblick in die Themen mit den meisten Informationen bieten und hilfreich sein, um Themen zu finden, die möglicherweise manuell bearbeitet werden müssen. Beispielsweise kann ein Thema mit einer niedrigeren Qualitätsnote das Ergebnis davon sein, dass einige Benutzer nicht über SharePoint-Berechtigungen für relevante Dateien oder Websites verfügen, die AI in das Thema aufgenommen hat. Ein Mitwirkender könnte dann das Thema bearbeiten, um die Informationen (falls angemessen) zu enthalten, die dann für alle Benutzer angezeigt werden können, die das Thema anzeigen können.

### <a name="impressions"></a>Impressionen

In **der Spalte** Impressionen wird angezeigt, wie oft ein Thema endbenutzern angezeigt wurde. Dies umfasst Ansichten über Themenantwortkarten in der Suche und über Themenhighlights. Es spiegelt nicht das Klicken auf diese Themen wider, sondern das Thema wurde angezeigt. Die **Spalte Impressionen** wird für Themen auf den  Registerkarten **Vorgeschlagen,** **Bestätigt,** Veröffentlicht und Entfernt auf der Seite Themen verwalten angezeigt.

## <a name="confirmed-topics"></a>Bestätigte Themen

Auf der Seite Themen verwalten werden Themen, die in Ihren angegebenen SharePoint-Quellstandorten entdeckt wurden und von einem Knowledge Manager oder "crowdsourced" bestätigt wurden, der von einem Netto von zwei oder mehr Personen (Ausgleich negativer Benutzerstimmen mit positiven Benutzerstimmen) über den Kartenfeedbackmechanismus bestätigt wurde, auf der Registerkarte **Bestätigt** aufgeführt. Bei Bedarf kann ein Benutzer mit berechtigungen zum Verwalten von Themen bestätigte Themen überprüfen und ablehnen.

So überprüfen Sie ein bestätigtes Thema:

1. Wählen Sie **auf der** Registerkarte Bestätigt das Thema aus, um die Themenseite zu öffnen.</br>

2. Überprüfen Sie auf der Themenseite die Themenseite, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.

Beachten Sie, dass Sie ein bestätigtes Thema weiterhin ablehnen können. Wechseln Sie dazu auf der Registerkarte  Bestätigt zum ausgewählten Thema, und wählen Sie **das x** aus, wenn Sie das Thema ablehnen möchten.

## <a name="published-topics"></a>Veröffentlichte Themen
Veröffentlichte Themen wurden bearbeitet, sodass immer bestimmte Informationen angezeigt werden, die auf die Seite stoßen. Hier werden auch manuell erstellte Themen aufgelistet.

   ![Verwalten von Themen](../media/knowledge-management/manage-topics-new.png) </br>
