---
title: Erstellen, Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Erfahren Sie, wie Sie mithilfe von Filtern benutzerdefinierte Benutzeransichten in Microsoft 365 erstellen, bearbeiten oder löschen können.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759930"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Erstellen, Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht

Wenn Sie ein globaler Administrator oder Benutzerverwaltungsadministrator eines Microsoft 365 Business-Abonnements sind, können Sie benutzerdefinierte Benutzeransichten erstellen, um eine bestimmte Teilmenge von Benutzern anzeigen zu können. Diese Ansichten sind zusätzlich zum Standardsatz von Ansichten. Sie können benutzerdefinierte Benutzeransichten erstellen, bearbeiten oder löschen, und die von Ihnen erstellten benutzerdefinierten Ansichten stehen allen Administratoren zur Verfügung.
  
## <a name="custom-user-views-in-the-admin-center"></a>Benutzerdefinierte Benutzeransichten im Admin Center

Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der Filterliste angezeigt, die allen Administratoren in Ihrem Unternehmen angezeigt wird, wenn sie zur Seite Benutzer **wechseln.**  Sie können bis zu 50 benutzerdefinierte Ansichten erstellen. 

> [!TIP]
>  Standard user views are displayed by default in the **Filters** drop-down list. Zu den Standardfiltern gehören **Alle** Benutzer **,** Lizenzierte Benutzer **,** Gastbenutzer **,** Anmeldung zulässig **,** Anmeldung blockiert , Nicht lizenzierte Benutzer **,** Benutzer mit Fehlern , **Abrechnungsadministratoren**, **globale** Administratoren , **Helpdeskadministratoren**, **Dienstadministratoren** und **Benutzerverwaltungsadministratoren**.  Standardansichten können weder bearbeitet noch gelöscht werden. 

Zu Standardansichten müssen noch einige weitere Punkte angemerkt werden: 

- In einigen Standardansichten wird eine nicht sortierte Liste angezeigt, wenn die Liste mehr als 2.000 Benutzer enthält. Wenn Sie in dieser Liste nach bestimmten Benutzern suchen möchten, müssen Sie das Suchfeld verwenden. 
- Wenn Sie Microsoft 365 nicht von Microsoft kaufen, werden **Abrechnungsadministratoren** nicht in der Standardansichtsliste angezeigt. Weitere Informationen finden Sie unter [Zuweisen von Adminrollen](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Wählen der Filter für die benutzerdefinierte Benutzeransicht

Sie können ihre benutzerdefinierten Ansichten im Benutzerdefinierten **Filterbereich erstellen und** bearbeiten. Wenn Sie mehrere Filteroptionen auswählen, erhalten Sie Ergebnisse mit Benutzern, die allen ausgewählten Filterkriterien entsprechen. Im folgende Beispiel wird gezeigt, wie Sie eine benutzerdefinierte Ansicht mit dem Namen "Kanadische Benutzer" erstellen, die alle Benutzer, die sich in Kanada befinden, in einer bestimmten Domäne enthält. 

  
 **A – Domäne** Wenn Sie über mehrere Domänen für Ihre Organisation verfügen, können Sie aus einer Dropdownliste der verfügbaren Domänen auswählen. 
  
 **B – Anmeldestatus** Wählen Sie Benutzer aus, die zugelassen oder blockiert sind. 
  
 **C – Speicherort** Wählen Sie einen Speicherort aus einer Dropdownliste mit Ländern aus. 
  
 **D – Zugewiesene Produktlizenz** Wählen Sie aus einer Dropdownliste der Lizenzen aus, die in Ihrer Organisation verfügbar sind. Verwenden Sie diesen Filter, um Benutzer anzuzeigen, denen die ausgewählte Lizenz zugewiesen ist. Benutzer können auch über weitere Lizenzen verfügen. 
  
Sie können auch nach weiteren Benutzerprofildetails filtern, die in Ihrer Organisation verwendet werden, z. B. Abteilung, Ort, Bundesland oder Kanton, Land oder Region oder Position.
  
 **Weitere Bedingungen:**
  
- **Nur synchronisierte Benutzer:** Wählen Sie dieses Feld aus, um alle Benutzer anzuzeigen, die mit dem lokalen Active Directory-Dienst synchronisiert sind. Es spielt keine Rolle, ob die Benutzer aktiviert wurden. 
    
- **Benutzer mit Fehlern:** Wählen Sie dieses Feld aus, um Benutzer mit möglichen Bereitstellungsfehlern anzuzeigen. 
    
- **Benutzer ohne Lizenzen:** Wählen Sie dieses Feld aus, um nach allen Benutzern zu suchen, denen keine Lizenz zugewiesen ist. Die Ergebnisse für diese Ansicht können auch Benutzer umfassen, die ein Exchange-Postfach, aber keine Lizenz besitzen. Um speziell diese Benutzer nachzuverfolgen, verwenden Sie den Filter **Benutzer mit Exchange-Postfächern oder -Archiven und keinen Lizenzen**. Die Ergebnisse dieser Ansicht können auch Benutzer umfassen, die über ein Exchange-Archiv, jedoch nicht über eine Lizenz verfügen.
    
- **Nicht lizenzierte Benutzer mit Exchange-Postfächern oder -Archiven** Aktivieren Sie dieses Feld, um Benutzerkonten zu zeigen, die in Exchange Online erstellt wurden und über ein Exchange-Postfach verfügen, aber keine Microsoft 365-Lizenz zugewiesen wurden. Die Ergebnisse dieses Filters enthalten Benutzer, die über ein Exchange-Archiv verfügen oder einem solchen zugewiesen wurden. 

> [!NOTE]
> Der **Filter Nicht lizenzierte Benutzer mit Exchange-Postfächern** funktioniert, wenn:
1. Das Postfach wurde kürzlich von freigegeben für **benutzer** **konvertiert** und verfügt über keine Lizenz.
2. Das Postfach wurde kürzlich zu Microsoft 365 migriert, es wurde jedoch keine Lizenz zugewiesen.
3. Das Postfach wurde mithilfe von PowerShell erstellt, und es wurde keine Lizenz zugewiesen.
4. Ein neues Postfach, das lokal mit einem New-RemoteMailbox erstellt wurde, wird für den Benutzer bereitgestellt.
    
> [!TIP]
> Wenn Sie eine benutzerdefinierte Ansicht mit über 2.000 Benutzern erstellen, ist die daraus resultierende Benutzerliste nicht sortiert. Verwenden Sie in diesem Fall das Suchfeld, um Benutzer zu finden oder Ihre benutzerdefinierte Ansicht zu bearbeiten, um die Suche zu verfeinern. 
  
## <a name="create-a-custom-user-view"></a>Erstellen einer benutzerdefinierten Benutzeransicht

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Wählen Sie **auf der Seite** Aktive Benutzer Die Option **Filter** aus, und wählen Sie Neuer **Filter aus.**
  
3. Geben Sie **auf der** Seite Benutzerdefinierter Filter den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen aus.** Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste der Filter enthalten.
    
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie **auf der Seite** Aktive Benutzer die Option Ansichten **aus,** und wählen **Sie Benutzerdefinierte Ansicht hinzufügen aus.**
  
3. Geben Sie **auf der** Seite Benutzerdefinierte Ansicht den Namen für Den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen aus.** Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste der Filter enthalten.

::: moniker-end


::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie **auf der Seite** Aktive Benutzer die Option Ansichten **aus,** und wählen **Sie Benutzerdefinierte Ansicht hinzufügen aus.**
  
3. Geben Sie **auf der** Seite Benutzerdefinierte Ansicht den Namen für Den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen aus.** Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste der Filter enthalten.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Wählen Sie **auf der** Seite Aktive Benutzer die Option **Filter** aus, wählen Sie den Filter aus, den Sie ändern möchten, und wählen Sie dann Filter **bearbeiten aus.** 
    
    > [!TIP]
    > Sie können nur benutzerdefinierte Ansichten bearbeiten. 
  
3. Bearbeiten Sie **auf der** Seite Benutzerdefinierter Filter die Informationen nach Bedarf, und wählen Sie dann **Speichern aus.** Wenn Sie den Filter löschen möchten, wählen Sie am unteren Rand der Seite Löschen **aus.** 
    
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie **auf der** Seite Aktive Benutzer **Ansichten** aus, wählen Sie den Filter aus, den Sie ändern möchten, und wählen Sie dann Diese Ansicht **bearbeiten aus.** 
    
    > [!TIP]
    > Sie können nur benutzerdefinierte Ansichten bearbeiten. 
  
3. Bearbeiten Sie **auf der** Seite Benutzerdefinierte Ansicht die Informationen nach Bedarf, und wählen Sie dann **Speichern aus.** Wenn Sie den Filter löschen möchten, wählen Sie am unteren Rand der Seite benutzerdefinierte **Ansicht löschen aus.** 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie **auf der** Seite Aktive Benutzer **Ansichten** aus, wählen Sie den Filter aus, den Sie ändern möchten, und wählen Sie dann Diese Ansicht **bearbeiten aus.** 
    
    > [!TIP]
    > Sie können nur benutzerdefinierte Ansichten bearbeiten. 
  
3. Bearbeiten Sie **auf der** Seite Benutzerdefinierte Ansicht die Informationen nach Bedarf, und wählen Sie dann **Speichern aus.** Wenn Sie den Filter löschen möchten, wählen Sie am unteren Rand der Seite benutzerdefinierte **Ansicht löschen aus.** 

::: moniker-end


     