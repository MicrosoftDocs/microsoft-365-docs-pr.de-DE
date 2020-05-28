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
description: Hier erfahren Sie, wie Sie Filter zum Erstellen, bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht in Microsoft 365 verwenden können.
ms.openlocfilehash: faea21f0e5142d197cc2b90d6ade99490f9f88e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387213"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a>Erstellen, Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht in Office 365

[] Wenn Sie ein globaler Administrator oder als Administrator für die Benutzerverwaltung in Office 365 zuständig sind, können Sie benutzerdefinierte Benutzeransichten erstellen, um eine bestimmte Untermenge von Benutzern anzuzeigen. Diese Ansichten werden zusätzlich zu den Standardansichten angezeigt, die zum Bereitstellungsumfang von Office 365 gehören. Sie können benutzerdefinierte Benutzeransichten erstellen, bearbeiten oder löschen, und die von Ihnen erstellten benutzerdefinierten Ansichten stehen allen Administratoren zur Verfügung.

::: moniker range="o365-worldwide"

> [!NOTE]
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a>Benutzerdefinierte Benutzeransichten im Admin Center

::: moniker range="o365-worldwide"

Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der **Filter** Liste angezeigt, die alle Administratoren in Ihrem Unternehmen sehen, wenn Sie zur Seite **Benutzer** wechseln. Sie können bis zu 50 benutzerdefinierte Ansichten erstellen. 

::: moniker-end

::: moniker range="o365-germany"

Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der Liste **Ansichten** angezeigt, die alle Administratoren in Ihrem Unternehmen sehen, wenn Sie zur Seite **Benutzer** wechseln. Sie können bis zu 50 benutzerdefinierte Ansichten erstellen. 

::: moniker-end

::: moniker range="o365-21vianet"

Wenn Sie eine benutzerdefinierte Benutzeransicht erstellen, bearbeiten oder löschen, werden die Änderungen in der Liste **Ansichten** angezeigt, die alle Administratoren in Ihrem Unternehmen sehen, wenn Sie zur Seite **Benutzer** wechseln. Sie können bis zu 50 benutzerdefinierte Ansichten erstellen. 

::: moniker-end

> [!TIP]
>  Standard user views are displayed by default in the **Filters** drop-down list. Die Standardfilter umfassen **alle Benutzer**, **lizenzierte Benutzer**, **Gastbenutzer**, **Anmeldungs berechtigte**, **Anmeldungs blockiert**, nicht **lizenzierte Benutzer**, **Benutzer mit Fehlern**, **Abrechnungs Administratoren**, **globale Administratoren**, **Helpdesk**-Administratoren, **Dienstadministratoren**und **Benutzer Verwaltungs Administratoren**. Standardansichten können weder bearbeitet noch gelöscht werden. 

Zu Standardansichten müssen noch einige weitere Punkte angemerkt werden: 

- In einigen Standardansichten wird eine nicht sortierte Liste angezeigt, wenn die Liste mehr als 2.000 Benutzer enthält. Wenn Sie in dieser Liste nach bestimmten Benutzern suchen möchten, müssen Sie das Suchfeld verwenden. 
- Wenn Sie Microsoft 365 nicht von Microsoft erworben haben, werden die **Abrechnungs Administratoren** nicht in der Liste Standardansichten angezeigt. Weitere Informationen finden Sie unter [Zuweisen von Adminrollen](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Wählen der Filter für die benutzerdefinierte Benutzeransicht

Sie können Ihre benutzerdefinierten Ansichten im **benutzerdefinierten Filter** Bereich erstellen und bearbeiten. Wenn Sie mehrere Filteroptionen auswählen, erhalten Sie Ergebnisse mit Benutzern, die allen ausgewählten Filterkriterien entsprechen. Im folgende Beispiel wird gezeigt, wie Sie eine benutzerdefinierte Ansicht mit dem Namen "Kanadische Benutzer" erstellen, die alle Benutzer, die sich in Kanada befinden, in einer bestimmten Domäne enthält. 

  
 **A-Domäne** Wenn Sie mehrere Domänen für Ihre Organisation haben, können Sie aus einer Dropdownliste mit verfügbaren Domänen auswählen. 
  
 **B-Anmeldestatus** Wählen Sie Benutzer, die zugelassen oder blockiert sind. 
  
 **C-Standort** Wählen Sie einen Speicherort aus einer Dropdownliste mit Ländern aus. 
  
 **D-zugewiesene Produktlizenz** Wählen Sie aus einer Dropdownliste mit Lizenzen aus, die in Ihrer Organisation zur Verfügung stehen. Verwenden Sie diesen Filter, um Benutzer anzuzeigen, denen die ausgewählte Lizenz zugewiesen ist. Benutzer können auch über weitere Lizenzen verfügen. 
  
Sie können auch nach weiteren Benutzerprofildetails filtern, die in Ihrer Organisation verwendet werden, z. B. Abteilung, Ort, Bundesland oder Kanton, Land oder Region oder Position.
  
 **Weitere Bedingungen:**
  
- **Nur synchronisierte Benutzer:** Wählen Sie dieses Feld aus, um alle Benutzer anzuzeigen, die mit dem lokalen Active Directory-Dienst synchronisiert sind. Es spielt keine Rolle, ob die Benutzer aktiviert wurden. 
    
- **Benutzer mit Fehlern:** Wählen Sie dieses Feld aus, um Benutzer mit möglichen Bereitstellungsfehlern anzuzeigen. 
    
- **Benutzer ohne Lizenzen:** Wählen Sie dieses Feld aus, um nach allen Benutzern zu suchen, denen keine Lizenz zugewiesen ist. Die Ergebnisse für diese Ansicht können auch Benutzer umfassen, die ein Exchange-Postfach, aber keine Lizenz besitzen. Um speziell diese Benutzer nachzuverfolgen, verwenden Sie den Filter **Benutzer mit Exchange-Postfächern oder -Archiven und keinen Lizenzen**. Die Ergebnisse dieser Ansicht können auch Benutzer umfassen, die über ein Exchange-Archiv, jedoch nicht über eine Lizenz verfügen.
    
- Nicht **lizenzierte Benutzer mit Exchange-Postfächern oder-Archiven** Aktivieren Sie dieses Kontrollkästchen, um Benutzerkonten anzuzeigen, die in Exchange Online erstellt wurden und über ein Exchange-Postfach verfügen, dem aber keine Microsoft 365-Lizenz zugewiesen wurde. Die Ergebnisse dieses Filters enthalten Benutzer, die über ein Exchange-Archiv verfügen oder einem solchen zugewiesen wurden. 

> [!NOTE]
> Die nicht **lizenzierten Benutzer mit Exchange-Post** Fach Filter funktionieren in folgenden Fällen:
1. Das Postfach wurde kürzlich von **freigegebener** **Benutzer** konvertiert und verfügt über keine Lizenz.
2. Das Postfach wurde kürzlich zu Microsoft 365 migriert, aber es wurde keine Lizenz zugewiesen.
3. Das Postfach wurde mithilfe von PowerShell erstellt, und es wurde keine Lizenz zugewiesen.
4. Ein neues Postfach, das lokal mit einem New-Remote Mailbox-Cmdlet erstellt wurde, wird für den Benutzer bereitgestellt.
    
> [!TIP]
> Wenn Sie eine benutzerdefinierte Ansicht mit über 2.000 Benutzern erstellen, ist die daraus resultierende Benutzerliste nicht sortiert. Verwenden Sie in diesem Fall das Suchfeld, um nach Benutzern zu suchen oder Ihre benutzerdefinierte Ansicht zu bearbeiten, um die Suche zu verfeinern. 
  
## <a name="create-a-custom-user-view"></a>Erstellen einer benutzerdefinierten Benutzeransicht

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Klicken Sie auf der Seite **aktive Benutzer** auf **Filter** , und wählen Sie **Neuer Filter**aus.
  
3. Geben Sie auf der Seite **benutzerdefinierter Filter** den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen**aus. Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste mit den Filtern enthalten.
    
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten** aus, und wählen Sie **benutzerdefinierte Ansicht hinzufügen**aus.
  
3. Geben Sie auf der Seite **benutzerdefinierte Ansicht** den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen**aus. Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste mit den Filtern enthalten.

::: moniker-end


::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten** aus, und wählen Sie **benutzerdefinierte Ansicht hinzufügen**aus.
  
3. Geben Sie auf der Seite **benutzerdefinierte Ansicht** den Namen für den Filter ein, wählen Sie die Bedingungen für den benutzerdefinierten Filter aus, und wählen Sie dann **Hinzufügen**aus. Ihre benutzerdefinierte Ansicht ist jetzt in der Dropdownliste mit den Filtern enthalten.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Bearbeiten oder Löschen einer benutzerdefinierten Benutzeransicht

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
    
2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Filter**aus, wählen Sie den Filter aus, den Sie ändern möchten, und klicken Sie dann auf **Filter bearbeiten**. 
    
    > [!TIP]
    > Sie können nur benutzerdefinierte Ansichten bearbeiten. 
  
3. Bearbeiten Sie auf der Seite **benutzerdefinierter Filter** die Informationen nach Bedarf, und wählen Sie dann **Speichern**aus. Oder wählen Sie zum Löschen des Filters am unteren Rand der Seite die Option **Löschen**aus. 
    
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten**aus, wählen Sie den Filter aus, den Sie ändern möchten, und klicken Sie dann auf **diese Ansicht bearbeiten**. 
    
    > [!TIP]
    > Sie können nur benutzerdefinierte Ansichten bearbeiten. 
  
3. Bearbeiten Sie auf der Seite **benutzerdefinierte Ansicht** die Informationen nach Bedarf, und wählen Sie dann **Speichern**aus. Wenn Sie den Filter löschen möchten, wählen Sie unten auf der Seite die Option **benutzerdefinierte Ansicht löschen**aus. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>. 

2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Ansichten**aus, wählen Sie den Filter aus, den Sie ändern möchten, und klicken Sie dann auf **diese Ansicht bearbeiten**. 
    
    > [!TIP]
    > Sie können nur benutzerdefinierte Ansichten bearbeiten. 
  
3. Bearbeiten Sie auf der Seite **benutzerdefinierte Ansicht** die Informationen nach Bedarf, und wählen Sie dann **Speichern**aus. Wenn Sie den Filter löschen möchten, wählen Sie unten auf der Seite die Option **benutzerdefinierte Ansicht löschen**aus. 

::: moniker-end


     