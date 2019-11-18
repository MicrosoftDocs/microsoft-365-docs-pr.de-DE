---
title: 'Zuweisen von eDiscovery-Berechtigungen im Security #a0 Compliance Center'
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 'Zuweisen der erforderlichen Berechtigungen zum Ausführen von eDiscovery-bezogenen Aufgaben mithilfe des Security #a0 Compliance Centers.'
ms.openlocfilehash: 61b55c221c11a577a64d0d2358c89253b1e90714
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686223"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Security #a0 Compliance Center

Wenn Sie möchten, dass Benutzer eines der eDiscovery-bezogenen Tools im Security #a0 Compliance Center in Office 365 verwenden, müssen Sie Ihnen die entsprechenden Berechtigungen zuweisen. Die einfachste Möglichkeit besteht darin, der Person die entsprechende Rollengruppe auf der Seite **Berechtigungen** im Security #a0 Compliance Center hinzuzufügen. In diesem Thema werden die Berechtigungen beschrieben, die zum Ausführen von eDiscovery-und Inhalts suchbezogenen Aufgaben mithilfe des Security #a0 Compliance Centers erforderlich sind. 
  
Die primäre eDiscovery-bezogene Rollengruppe in Security #a0 Compliance Center wird als **eDiscovery-Manager**bezeichnet. In dieser Rollengruppe gibt es zwei Untergruppen. 
  
- **eDiscovery** -Manager: ein eDiscovery-Manager kann das Inhalts Such Tool im Security #a0 Compliance Center zum Durchsuchen von Inhaltsspeicherorten in der Organisation und zum Ausführen verschiedener Such bezogener Aktionen wie Vorschau-und Export Suchergebnisse verwenden. Mitglieder können auch eDiscovery-Fälle erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, die Fall Behältern erstellen und mit einem Fall verknüpfte Inhalts Suchvorgänge ausführen und Zugriffs Fall Daten in Office 365 Advanced eDiscovery bearbeiten.  EDiscovery-Manager können nur auf die von Ihnen erstellten Fälle zugreifen und diese verwalten. Sie können nicht auf Fälle zugreifen oder diese verwalten, die von anderen eDiscovery-Managern erstellt wurden. 
    
- **eDiscovery-Administratoren** : ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager" und kann dieselben Aufgaben im Zusammenhang mit der Inhaltssuche und der Fallverwaltung ausführen, die ein eDiscovery-Manager ausführen kann. Darüber hinaus können eDiscovery-Administratoren folgende Aktionen durchführen: 
    
  - Greifen Sie auf alle Fälle zu, die auf der Seite **eDiscovery-Fälle** im Security #a0 Compliance Center aufgeführt sind. 

  - Zugriffs Fall Daten in Advanced eDiscovery für jeden Fall in der Organisation.
    
  - eDiscovery-Fälle verwalten, nachdem sie sich selbst als Fallmitglied hinzugefügt haben.
  
  Im Abschnitt [Weitere Informationen](#more-information) finden Sie Gründe, warum Sie eDiscovery-Administratoren in Ihrer Organisation benötigen. 

> [!NOTE]
> Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden. Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz.  
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Sie müssen Mitglied der Rollengruppe "Organisationsverwaltung" sein (oder der Rolle "Rollenverwaltung" zugewiesen sein), um eDiscovery-Berechtigungen im Security #a0 Compliance Center zuzuweisen.
    
- Sie können das [Add-RoleGroupMember-](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember) Cmdlet in Security #a0 Compliance Center PowerShell verwenden, um eine e-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe eDiscovery Managers in der Rollengruppe "eDiscovery-Manager" hinzuzufügen. Sie können jedoch keine e-Mail-aktivierte Sicherheitsgruppe zur Untergruppe der eDiscovery-Administratoren hinzufügen. Weitere Informationen finden Sie im Abschnitt [Weitere Informationen](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Security #a0 Compliance Center

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im linken Bereich des Security and Compliance Centers auf **Berechtigungen**, und klicken Sie dann auf das Kontrollkästchen neben **eDiscovery-Manager**.
    
4. Führen Sie auf der Flyout-Seite des **eDiscovery-Managers** einen der folgenden Schritte basierend auf den eDiscovery-Berechtigungen aus, die Sie zuweisen möchten. 
  
    **So machen Sie einen Benutzer zu einem eDiscovery-Manager:** Klicken Sie neben **eDiscovery-Manager**auf **Bearbeiten**. Klicken Sie im Abschnitt **eDiscovery-Manager auswählen** auf den Hyperlink **eDiscovery-Manager auswählen** , ![und klicken](media/ITPro-EAC-AddIcon.gif) Sie dann auf Symbol **hinzu**fügen. Wählen Sie die Benutzer (oder Benutzer) aus, die Sie als eDiscovery-Manager hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Fertig**. Klicken Sie dann auf der Seite zum **Bearbeiten von eDiscovery-Manager** -Flyouts auswählen auf **Speichern** , um die Änderungen an der eDiscovery-Manager-Mitgliedschaft zu speichern.
  
    **So machen Sie einen Benutzer zu einem eDiscovery-Administrator:** Klicken Sie neben **eDiscovery-Manager**auf **Bearbeiten**. Klicken Sie im Abschnitt **eDiscovery-Administrator auswählen** unter **eDiscovery-Administratoren**auf **eDiscovery-Administrator auswählen** , klicken Sie auf ![ **Bearbeiten**, und klicken Sie dann auf Symbol](media/ITPro-EAC-AddIcon.gif) **hinzu**fügen. Wählen Sie die Benutzer (oder Benutzer) aus, die Sie als **eDiscovery-Administrator**hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Fertig**. Klicken Sie dann auf der Flyout-Seite **"eDiscovery-Administrator bearbeiten"** auf **Speichern** , um die Änderungen an der eDiscovery-Administrator Mitgliedschaft zu speichern.
      
> [!NOTE]
> Sie können auch das **Add-eDiscoveryCaseAdmin-** Cmdlet verwenden, um einen Benutzer zu einem eDiscovery-Administrator zu machen. Dem Benutzer muss jedoch die Fall Verwaltungsrolle zugewiesen sein, bevor Sie dieses Cmdlet verwenden können, um Sie zu einem eDiscovery-Administrator zu machen. Weitere Informationen finden Sie unter [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Auf der Seite **Berechtigungen** im Security #a0 Compliance Center können Sie auch Benutzern eDiscovery-bezogene Berechtigungen zuweisen, indem Sie Sie den Rollengruppen "Compliance-Administrator", "Organisationsverwaltung" und "Prüfer" hinzufügen. Eine Beschreibung der eDiscovery-bezogenen RBAC-Rollen, die den einzelnen Rollengruppen zugewiesen sind, finden Sie im Abschnitt [über RBAC-Rollen im Zusammenhang mit eDiscovery](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>RBAC-Rollen im Zusammenhang mit eDiscovery

In der folgenden Tabelle sind die eDiscovery-Rollen im Sicherheits #a0 Compliance Center aufgeführt und die integrierten Rollengruppen angegeben, denen jede Rolle standardmäßig zugewiesen ist. 
    
|**Rolle**|**Complianceadministrator**|**eDiscovery-Manager-#a0 Administrator**|**Organisationsverwaltung**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Fallverwaltung <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Compliance-Suche <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Exportieren <br/> | <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Vorschau <br/>  | <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Review <br/>  | <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|RMS-Entschlüsselung <br/>  ||![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Suchen und löschen <br/> | <br/> | <br/> |![Häkchen](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
In den folgenden Abschnitten werden die einzelnen eDiscovery-Rollen, die in der vorherigen Tabelle aufgeführt sind, beschrieben.

### <a name="case-management"></a>Fallverwaltung

Diese Rolle ermöglicht Benutzern das Erstellen, bearbeiten, löschen und Steuern des Zugriffs auf eDiscovery-Fälle im Security #a0 Compliance Center. Weitere Informationen finden Sie unter [Verwalten von eDiscovery-Fällen im Security #a0 Compliance Center](manage-ediscovery-cases.md). Wie bereits erläutert, muss einem Benutzer die Fall Verwaltungsrolle zugewiesen werden, bevor Sie das Cmdlet **Add-eDiscoveryCaseAdmin** verwenden können, um Sie zu einem eDiscovery-Administrator zu machen. 

### <a name="compliance-search"></a>Compliance-Suche

Mit dieser Rolle können Benutzer das Tool für die Inhaltssuche im Security #a0 Compliance Center ausführen, um Postfächer und öffentliche Ordner, SharePoint Online Websites, OneDrive für Unternehmen Websites, Skype for Business Unterhaltungen, Office 365 Gruppen und Microsoft Teams zu durchsuchen. Diese Rolle ermöglicht es einem Benutzer, eine Schätzung der Suchergebnisse zu erhalten und Export Berichte zu erstellen, aber zusätzliche Rollen sind erforderlich, um Inhalts Suchaktionen wie das Anzeigen einer Vorschau, exportieren oder Löschen von Suchergebnissen zu initiieren.

Beachten Sie, dass Benutzern, denen die Rolle "Konformitäts Suche" zugewiesen ist, jedoch keine Vorschau Rolle besitzt, die Ergebnisse einer Suche in der Vorschau angezeigt werden, in der die Vorschau Aktion von einem Benutzer initiiert wurde, dem die Rolle "Vorschau" zugewiesen ist. Der Benutzer ohne die Vorschau-Rolle kann bis zu zwei Wochen nach dem Erstellen der ersten Vorschau-Aktion eine Vorschau der Ergebnisse anzeigen.

Ebenso können Benutzer, denen die Rolle "Konformitäts Suche" zugewiesen ist, aber nicht über die Rolle "Exportieren" verfügen, die Ergebnisse einer Suche herunterladen, in der die Exportaktion von einem Benutzer initiiert wurde, dem die Rolle "Export" zugewiesen wurde. Der Benutzer ohne die Rolle "Exportieren" kann die Ergebnisse einer Suche bis zu 2 Wochen nach dem Erstellen der ursprünglichen Exportaktion herunterladen. Anschließend können Sie die Ergebnisse nicht herunterladen, es sei denn, jemand mit der Export Rolle startet den Export neu.

Weitere Informationen finden Sie unter [Inhaltssuche in Office 365](content-search.md). 

### <a name="export"></a>Exportieren

Die Rolle ermöglicht Benutzern das Exportieren der Ergebnisse einer Inhaltssuche auf einen lokalen Computer. Außerdem können Sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. 

Weitere Informationen zum Exportieren von Suchergebnissen finden Sie unter [Exportieren von Suchergebnissen aus Security #a0 Compliance Center](export-search-results.md).

### <a name="hold"></a>Hold

Diese Rolle ermöglicht Benutzern das Platzieren von Inhalten in Postfächern, öffentlichen Ordnern, Websites, Skype for Business Unterhaltungen und Office 365 Gruppen in der Warteschleife. Wenn Inhalte gespeichert sind, können Inhaltsbesitzer weiterhin den ursprünglichen Inhalt ändern oder löschen, der Inhalt bleibt jedoch erhalten, bis die Aufbewahrungszeit aufgehoben wird oder die Aufbewahrungsdauer abläuft. 

Weitere Informationen zu Holds finden Sie unter:

- [eDiscovery-Fälle](ediscovery-cases.md) 
- [Übersicht über Aufbewahrungsrichtlinien](retention-policies.md)

### <a name="preview"></a>Vorschau

Diese Rolle ermöglicht Benutzern das Anzeigen einer Liste von Elementen, die von einer Inhaltssuche zurückgegeben wurden. Sie können auch jedes Element aus der Liste öffnen und anzeigen, um den Inhalt anzuzeigen.

### <a name="review"></a>Review

Diese Rolle ermöglicht Benutzern den Zugriff auf die Falldaten in Office 365 Advanced eDiscovery. Der primäre Zweck dieser Rolle besteht darin, Benutzern den Zugriff auf Erweiterte eDiscovery zu ermöglichen. Benutzer, denen diese Rolle zugewiesen ist, können die Liste der Fälle auf der Seite "eDiscovery" im Security #a0 Compliance Center anzeigen und öffnen, von der Sie Mitglieder sind. Nachdem der Benutzer im Security #a0 Compliance Center auf einen Fall zugegriffen hat, kann er auf " **Advanced eDiscovery" wechseln** , um auf die Falldaten in Advanced eDiscovery zuzugreifen und diese zu analysieren. Diese Rolle ermöglicht es dem Benutzer nicht, die Ergebnisse einer Inhaltssuche in einer Vorschau anzuzeigen, die mit dem Fall verbunden ist, oder andere Inhaltssuche oder Fall Verwaltungsaufgaben auszuführen.

### <a name="rms-decrypt"></a>RMS-Entschlüsselung

Mit dieser Rolle können Benutzer RMS-verschlüsselte e-Mail-Nachrichten beim Exportieren von Suchergebnissen oder beim Vorbereiten von Suchergebnissen für die Analyse in Advanced eDiscovery entschlüsseln. Weitere Informationen zum Entschlüsseln von Suchergebnissen während des Exports finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).

### <a name="search-and-purge"></a>Suchen und löschen

Diese Rolle ermöglicht es Benutzern, das Massen Entfernen von Daten durchzuführen, die den Kriterien einer Inhaltssuche entsprechen. Weitere Informationen finden Sie unter [Suchen nach und Löschen von e-Mail-Nachrichten in Ihrer Office 365 Organisation](search-for-and-delete-messages-in-your-organization.md). 


## <a name="more-information"></a>Weitere Informationen

- **Gründe für das Festlegen eines eDiscovery-Administrators** Wie bereits erwähnt, ist ein eDiscovery-Administrator Mitglied der Rollengruppe „eDiscovery-Manager“, die alle eDiscovery-Fälle in Ihrer Organisation anzeigen und auf diese zugreifen kann. Dieser Zugriff auf alle eDiscovery-Fälle dient zwei wichtigen Zwecken: 
    
  - Wenn eine Person, die das einzige Mitglied eines eDiscovery-Falls ist, die Organisation verlässt, kann niemand (einschließlich Mitglieder der Rollengruppe „Organisationsverwaltung“ oder andere Mitglieder der Rollengruppe „eDiscovery-Manager“) auf diesen eDiscovery-Fall zugreifen, da diese Personen keine Fallmitglieder sind. In diesem Fall gäbe es keine Möglichkeit, auf die Daten in dem Fall zuzugreifen. Da ein eDiscovery-Administrator jedoch auf alle eDiscovery-Fälle in der Organisation zugreifen kann, kann er den Fall anzeigen und sich selbst oder einen anderen eDiscovery-Manager als Mitglied des Falles hinzufügen.
    
  - Da ein eDiscovery-Administrator alle eDiscovery-Fälle anzeigen und darauf zugreifen kann, kann er alle Fälle und zugehörige Compliance-Suchvorgänge überwachen und überwachen. So kann der Missbrauch von Compliancesuchen oder anderen eDiscovery-Fällen verhindert werden. Da eDiscovery-Administratoren Zugriff auf potenziell vertrauliche Informationen in den Ergebnissen einer Compliancesuche haben, sollten Sie die Anzahl von eDiscovery-Administratoren gering halten.
    
    Außerdem werden eDiscovery-Administratoren automatisch als Administratoren in Advanced eDiscovery hinzugefügt. Das bedeutet, dass eine Person ein eDiscovery-Administrator sein muss, um administrative Aufgaben in Advanced eDiscovery durchzuführen, beispielsweise das Einrichten von Benutzern, das Erstellen von Fällen und das Importieren von Daten in einen Fall.
    
- **Kann ich eine Gruppe als Mitglied der eDiscovery-Manager-Rollengruppe hinzufügen?** Wie bereits erläutert, können Sie eine e-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe eDiscovery Managers in der Rollengruppe eDiscovery-Manager mithilfe des **Add-RoleGroupMember-** Cmdlets in Security #a0 Compliance Center PowerShell hinzufügen. Sie können beispielsweise den folgenden Befehl ausführen, um eine e-Mail-aktivierte Sicherheitsgruppe zur eDiscovery-Manager-Rollengruppe hinzuzufügen. 
    
  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Beachten Sie, dass eine Exchange-Verteilergruppe oder eine Office 365 Gruppe nicht unterstützt wird. Sie müssen eine e-Mail-aktivierte Sicherheitsgruppe verwenden, die Sie in Exchange Online PowerShell mithilfe des ` New-DistributionGroup -Type Security ` Befehls erstellen können. Sie können auch eine e-Mail-aktivierte Sicherheitsgruppe (und Mitglieder hinzufügen) im Exchange Admin Center oder im Microsoft 365 Admin Center erstellen. Beachten Sie, dass es bis zu 60 Minuten dauern kann, nachdem Sie es erstellt haben, damit eine neue e-Mail-aktivierte Sicherheit zur Rollengruppe "eDiscovery-Manager" hinzugefügt werden kann. 
    
    Wie bereits erwähnt, können Sie eine e-Mail-aktivierte Sicherheitsgruppe nicht mithilfe des Cmdlets **Add-eDiscoveryCaseAdmin** in Security #a0 Compliance Center PowerShell als eDiscovery-Administrator festlegen. Sie können nur einzelne Benutzer als eDiscovery-Administratoren hinzufügen. 
    
    Beachten Sie, dass Sie auch keine e-Mail-aktivierte Sicherheitsgruppe als Mitglied einer Anfrage hinzufügen können.
