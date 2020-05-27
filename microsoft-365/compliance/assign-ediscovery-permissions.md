---
title: Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center
f1.keywords:
- NOCSH
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
description: Zuweisen der erforderlichen Berechtigungen zum Ausführen von eDiscovery-bezogenen Aufgaben mithilfe des Security & Compliance Centers.
ms.openlocfilehash: 4c39dc3cd0d3c5d13d33330eca930e07227c38d3
ms.sourcegitcommit: 17a45261926dde1a7cd24e0ac516cfc49e453806
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374404"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center

Wenn Sie möchten, dass Benutzer eines der [eDiscovery-bezogenen Tools](ediscovery.md) im Security & Compliance Center in Office 365 oder im Microsoft 365 Compliance Center verwenden, müssen Sie Ihnen die entsprechenden Berechtigungen zuweisen. Die einfachste Möglichkeit besteht darin, der Person die entsprechende Rollengruppe auf der Seite **Berechtigungen** im Security & Compliance Center hinzuzufügen. In diesem Thema werden die Berechtigungen beschrieben, die zum Ausführen von eDiscovery-und Inhalts suchbezogenen Aufgaben mithilfe des Security & Compliance Centers erforderlich sind.
  
Die primäre eDiscovery-bezogene Rollengruppe in Security & Compliance Center wird als **eDiscovery-Manager**bezeichnet. In dieser Rollengruppe gibt es zwei Untergruppen. 
  
- **eDiscovery** -Manager: ein eDiscovery-Manager kann das Inhalts Such Tool im Security & Compliance Center zum Durchsuchen von Inhaltsspeicherorten in der Organisation und zum Ausführen verschiedener Such bezogener Aktionen wie Vorschau-und Export Suchergebnisse verwenden. Mitglieder können auch Kern-eDiscovery-Fälle und erweiterte eDiscovery-Fälle erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, die Case-aufbewahrungsinformationen erstellen, Suchvorgänge mit einem Fall durchführen und Zugriffs Fall Daten ausführen. eDiscovery-Manager können nur auf die von Ihnen erstellten Fälle zugreifen und diese verwalten. Sie können nicht auf Fälle zugreifen oder diese verwalten, die von anderen eDiscovery-Managern erstellt wurden.
  
- **eDiscovery-Administratoren** : ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager" und kann dieselben Aufgaben im Zusammenhang mit der Inhaltssuche und der Fallverwaltung ausführen, die ein eDiscovery-Manager ausführen kann. Darüber hinaus können eDiscovery-Administratoren folgende Aktionen durchführen:
  
  - Greifen Sie auf alle Fälle zu, die auf der **eDiscovery-und der** **Advanced eDiscovery** -Seite im Security & Compliance Center aufgeführt sind.

  - Zugriffs Fall Daten in Advanced eDiscovery für jeden Fall in der Organisation.
  
  - Verwalten Sie alle eDiscovery-Fälle, nachdem Sie sich selbst als Mitglied der Anfrage hinzugefügt haben.
  
  Im Abschnitt [Weitere Informationen](#more-information) finden Sie Gründe, warum Sie eDiscovery-Administratoren in Ihrer Organisation benötigen.

> [!NOTE]
> Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-oder Microsoft E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer E1-oder E3-Lizenz eine E5-Add-on-Lizenz zugewiesen werden. Administratoren, Compliance Officer oder juristische Personen, die den Fällen als Mitglieder zugewiesen sind, und Verwenden von Advanced eDiscovery zum erfassen, anzeigen und Analysieren von Daten benötigen keine E5-Lizenz. Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://aka.ms/complianceSD).
  
## <a name="before-you-begin"></a>Vorabinformationen

- Sie müssen Mitglied der Rollengruppe "Organisationsverwaltung" sein oder der Rolle "Rollenverwaltung" zugewiesen sein, um eDiscovery-Berechtigungen im Security & Compliance Center zuzuweisen.
    
- Sie können das [Add-RoleGroupMember-](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember) Cmdlet in Security & Compliance Center PowerShell verwenden, um eine e-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe eDiscovery Managers in der Rollengruppe "eDiscovery-Manager" hinzuzufügen. Sie können jedoch keine e-Mail-aktivierte Sicherheitsgruppe zur Untergruppe der eDiscovery-Administratoren hinzufügen. Ausführliche Informationen finden Sie im Abschnitt [More Information](#more-information) . 
    
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Wählen Sie im linken Bereich des Security and Compliance Centers **Berechtigungen**aus, und aktivieren Sie dann das Kontrollkästchen neben **eDiscovery-Manager**.
    
4. Führen Sie auf der Flyout-Seite des **eDiscovery-Managers** einen der folgenden Schritte basierend auf den eDiscovery-Berechtigungen aus, die Sie zuweisen möchten. 
  
    **So machen Sie einen Benutzer zu einem eDiscovery-Manager:** Wählen Sie neben **eDiscovery-Manager**die Option **Bearbeiten**aus. Wählen Sie im Abschnitt **eDiscovery-Manager** auswählen den Hyperlink **eDiscovery-Manager auswählen** aus, und wählen Sie dann ![ Add Icon Add aus ](../media/ITPro-EAC-AddIcon.gif) **Add**. Wählen Sie die Benutzer (oder Benutzer) aus, die Sie als eDiscovery-Manager hinzufügen möchten, und wählen Sie dann **Hinzufügen**aus. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Fertig**aus. Wählen Sie dann auf der Flyout-Seite für **eDiscovery-Manager bearbeiten** die Option **Speichern** aus, um die Änderungen an der eDiscovery-Manager-Mitgliedschaft zu speichern.
  
    **So machen Sie einen Benutzer zu einem eDiscovery-Administrator:** Wählen Sie neben **eDiscovery-Manager**die Option **Bearbeiten**aus. Wählen Sie im Abschnitt **eDiscovery-Administrator auswählen** unter **eDiscovery-Administratoren**die Option **eDiscovery-Administrator**auswählen, **Bearbeiten**aus, und klicken Sie dann auf ![ Symbol ](../media/ITPro-EAC-AddIcon.gif) **hinzu**fügen. Wählen Sie die Benutzer (oder Benutzer) aus, die Sie als **eDiscovery-Administrator**hinzufügen möchten, und fügen Sie dann **hinzu**. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Fertig**aus. Wählen Sie dann auf der Flyout-Seite für **eDiscovery-Administrator bearbeiten** die Option **Speichern** aus, um die Änderungen an der eDiscovery-Administrator Mitgliedschaft zu speichern.
      
> [!NOTE]
> Sie können auch das **Add-eDiscoveryCaseAdmin-** Cmdlet verwenden, um einen Benutzer zu einem eDiscovery-Administrator zu machen. Dem Benutzer muss jedoch die Fall Verwaltungsrolle zugewiesen sein, bevor Sie dieses Cmdlet verwenden können, um Sie zu einem eDiscovery-Administrator zu machen. Weitere Informationen finden Sie unter [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217). 
  
Auf der Seite **Berechtigungen** im Security & Compliance Center können Sie Benutzern auch eDiscovery-bezogene Berechtigungen zuweisen, indem Sie Sie den Rollengruppen "Compliance-Administrator", "Organisationsverwaltung" und "Prüfer" hinzufügen. Eine Beschreibung der eDiscovery-bezogenen RBAC-Rollen, die den einzelnen Rollengruppen zugewiesen sind, finden Sie im Abschnitt [über RBAC-Rollen im Zusammenhang mit eDiscovery](#rbac-roles-related-to-ediscovery) . 

## <a name="rbac-roles-related-to-ediscovery"></a>RBAC-Rollen im Zusammenhang mit eDiscovery

In der folgenden Tabelle sind die eDiscovery-Rollen im Sicherheits & Compliance Center aufgeführt und die integrierten Rollengruppen angegeben, denen jede Rolle standardmäßig zugewiesen ist. 
    
|**Rolle**|**Complianceadministrator**|**eDiscovery-Manager-& Administrator**|**Organisationsverwaltung**|**Reviewer**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|Fallverwaltung <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Kommunikation <br/> | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Compliance-Suche <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Custodian <br/> | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Exportieren <br/> | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|Vorschau <br/>  | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|Überprüfung <br/>  | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|RMS-Entschlüsselung <br/>  ||![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|Suchen und löschen <br/> | <br/> | <br/> |![Häkchen](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
In den folgenden Abschnitten werden die einzelnen eDiscovery-Rollen, die in der vorherigen Tabelle aufgeführt sind, beschrieben.

### <a name="case-management"></a>Fallverwaltung

Mit dieser Rolle können Benutzer den Zugriff auf zentrale eDiscovery-und erweiterte eDiscovery-Fälle im Security & Compliance Center erstellen, bearbeiten, löschen und steuern. Wie bereits erläutert, muss einem Benutzer die Fall Verwaltungsrolle zugewiesen werden, bevor Sie das Cmdlet **Add-eDiscoveryCaseAdmin** verwenden können, um Sie zu einem eDiscovery-Administrator zu machen.

Weitere Informationen finden Sie unter:

- [Erste Schritte mit Core eDiscovery](get-started-core-ediscovery.md)

- [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Kommunikation

Mit dieser Rolle können Benutzer die gesamte Kommunikation mit den in einem erweiterten eDiscovery-Fall identifizierten Depotbanken verwalten. Dies umfasst das Erstellen von Aufbewahrungs Benachrichtigungen, Speichern von Erinnerungen und Eskalationen an die Verwaltung. Der Benutzer kann auch die depotbestätigung für "Aufbewahrungs Benachrichtigungen" verfolgen und den Zugriff auf das Depot verwalten, das von jeder Depotbank verwendet wird, um die Kommunikation für die Fälle nachzuverfolgen, in denen Sie als depotverwalter identifiziert wurden.

Weitere Informationen finden Sie unter [Arbeiten mit Kommunikationen in Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Compliance-Suche

Mit dieser Rolle können Benutzer das Tool für die Inhaltssuche im Security & Compliance Center ausführen, um Postfächer und öffentliche Ordner, SharePoint Online Websites, OneDrive für Unternehmen Websites, Skype for Business Unterhaltungen, Microsoft 365-Gruppen und Microsoft Teams sowie Jammer Gruppen zu durchsuchen. Diese Rolle ermöglicht es einem Benutzer, eine Schätzung der Suchergebnisse zu erhalten und Export Berichte zu erstellen, aber zusätzliche Rollen sind erforderlich, um Inhalts Suchaktionen wie das Anzeigen einer Vorschau, exportieren oder Löschen von Suchergebnissen zu initiieren.

Benutzer, denen die Rolle "Konformitäts Suche" zugewiesen ist, jedoch nicht über die Rolle "Vorschau" verfügen, können eine Vorschau der Ergebnisse einer Suche anzeigen, in der die Vorschau Aktion von einem Benutzer initiiert wurde, dem die Rolle "Vorschau" zugewiesen wurde. Der Benutzer ohne die Vorschau-Rolle kann bis zu zwei Wochen nach dem Erstellen der ersten Vorschau-Aktion eine Vorschau der Ergebnisse anzeigen.

Auf ähnliche Weise können Benutzer, denen die Rolle "Konformitäts Suche" zugewiesen ist, aber nicht über die Rolle "Exportieren" verfügen, die Ergebnisse einer Suche herunterladen, in der die Exportaktion von einem Benutzer initiiert wurde, dem die Rolle "Export" zugewiesen wurde. Der Benutzer ohne die Rolle "Export" kann die Ergebnisse einer Suche bis zu zwei Wochen nach dem Erstellen der ursprünglichen Exportaktion herunterladen. Anschließend können Sie die Ergebnisse nicht herunterladen, es sei denn, jemand mit der Export Rolle startet den Export neu.

Weitere Informationen finden Sie unter [Inhaltssuche in Office 365](content-search.md).

### <a name="custodian"></a>Custodian

Diese Rolle ermöglicht es Benutzern, Verwalter für erweiterte eDiscovery-Fälle zu identifizieren und zu verwalten und die Informationen aus Azure Active Directory und anderen Quellen zu verwenden, um Datenquellen zu finden, die Depotbanken zugeordnet sind. Der Benutzer kann in einem Fall andere Datenquellen wie Postfächer, SharePoint-Websites und Teams mit Depotbanken verknüpfen. Der Benutzer kann auch eine rechtliche Aufbewahrungspflicht für die mit den Depotbanken verknüpften Datenquellen festlegen, um Inhalte im Kontext eines Falles beizubehalten.

Weitere Informationen finden Sie unter [Arbeiten mit Verwaltern in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Exportieren

Die Rolle ermöglicht Benutzern das Exportieren der Ergebnisse einer Inhaltssuche auf einen lokalen Computer. Außerdem können Sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. 

Weitere Informationen zum Exportieren von Suchergebnissen finden Sie unter [Exportieren von Suchergebnissen aus Security & Compliance Center](export-search-results.md).

### <a name="hold"></a>Hold

Diese Rolle ermöglicht es Benutzern, Inhalte in Postfächern, öffentlichen Ordnern, Websites, Skype for Business Unterhaltungen und Microsoft 365-Gruppen aufzubewahren. Wenn Inhalte gespeichert sind, können Inhaltsbesitzer den ursprünglichen Inhalt weiterhin ändern oder löschen, der Inhalt bleibt jedoch erhalten, bis die Aufbewahrungsdauer aufgehoben oder die Aufbewahrungsdauer abgelaufen ist. 

Weitere Informationen zu Holds finden Sie unter:

- [Erstellen eines Haltestatus in der zentralen eDiscovery](create-ediscovery-holds.md) 

- [Erstellen eines Haltestatus in Advanced eDiscovery](add-custodians-to-case.md#step-4-place-custodians-on-hold)

### <a name="preview"></a>Vorschau

Diese Rolle ermöglicht Benutzern das Anzeigen einer Liste von Elementen, die von einer Inhaltssuche zurückgegeben wurden. Sie können auch jedes Element aus der Liste öffnen und anzeigen, um den Inhalt anzuzeigen.

### <a name="review"></a>Überprüfung

Diese Rolle ermöglicht Benutzern den Zugriff auf Falldaten in [Advanced eDiscovery (klassisch)](office-365-advanced-ediscovery.md) (auch bekannt als *Advanced eDiscovery v1*). Der primäre Zweck dieser Rolle besteht darin, Benutzern den Zugriff auf Advanced eDiscovery (Classic) zu ermöglichen. Benutzer, denen diese Rolle zugewiesen ist, können die Liste der Fälle auf der Seite " **eDiscovery** " im Security & Compliance Center anzeigen und öffnen, von der Sie Mitglieder sind. Nachdem der Benutzer im Security & Compliance Center auf einen Fall zugegriffen hat, kann er auf " **Advanced eDiscovery" wechseln** , um auf die Falldaten in Advanced eDiscovery (klassisch) zuzugreifen und diese zu analysieren. Diese Rolle ermöglicht es dem Benutzer nicht, die Ergebnisse einer Inhaltssuche in der Vorschau anzuzeigen, die mit dem Fall verbunden ist, oder andere Aufgaben zur Inhaltssuche oder Fallverwaltung ausführen.

> [!NOTE]
> Zu diesem Zeitpunkt können Benutzer, denen die Überprüfungs Rolle zugewiesen ist (oder ein Mitglied der Rollengruppe Prüfer ist) nicht auf Daten in [Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery v2*) zugreifen. Wenn Sie einem Fall in Advanced eDiscovery v2 Mitglieder hinzufügen möchten, damit Sie die Falldaten überprüfen können, muss ein Benutzer Mitglied der Rollengruppe "eDiscovery-Manager" sein.

### <a name="rms-decrypt"></a>RMS-Entschlüsselung

Mit dieser Rolle können Benutzer durch Rechte geschützte e-Mail-Nachrichten beim Exportieren von Suchergebnissen oder beim Vorbereiten von Suchergebnissen für die Analyse in Advanced eDiscovery entschlüsseln. Weitere Informationen zum Entschlüsseln von Suchergebnissen während des Exports finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).

### <a name="search-and-purge"></a>Suchen und löschen

Diese Rolle ermöglicht es Benutzern, das Massen Entfernen von Daten durchzuführen, die den Kriterien einer Inhaltssuche entsprechen. Weitere Informationen finden Sie unter [Suchen nach und Löschen von e-Mail-Nachrichten in Ihrer Organisation](search-for-and-delete-messages-in-your-organization.md). 

## <a name="more-information"></a>Weitere Informationen

- **Gründe für das Festlegen eines eDiscovery-Administrators** Wie bereits erwähnt, ist ein eDiscovery-Administrator Mitglied der Rollengruppe „eDiscovery-Manager“, die alle eDiscovery-Fälle in Ihrer Organisation anzeigen und auf diese zugreifen kann. Dieser Zugriff auf alle eDiscovery-Fälle dient zwei wichtigen Zwecken: 

  - Wenn eine Person, die das einzige Mitglied eines eDiscovery-Falls ist, die Organisation verlässt, kann niemand (einschließlich Mitglieder der Rollengruppe „Organisationsverwaltung“ oder andere Mitglieder der Rollengruppe „eDiscovery-Manager“) auf diesen eDiscovery-Fall zugreifen, da diese Personen keine Fallmitglieder sind. In diesem Fall gäbe es keine Möglichkeit, auf die Daten in dem Fall zuzugreifen. Da ein eDiscovery-Administrator jedoch auf alle eDiscovery-Fälle in der Organisation zugreifen kann, kann er den Fall anzeigen und sich selbst oder einen anderen eDiscovery-Manager als Mitglied des Falles hinzufügen.

  - Da ein eDiscovery-Administrator alle zentralen eDiscovery-und Advanced-eDiscovery-Fälle anzeigen und darauf zugreifen kann, kann er alle Fälle und zugehörige Compliance-Suchvorgänge überwachen und überwachen. So kann der Missbrauch von Compliancesuchen oder anderen eDiscovery-Fällen verhindert werden. Da eDiscovery-Administratoren Zugriff auf potenziell vertrauliche Informationen in den Ergebnissen einer Compliancesuche haben, sollten Sie die Anzahl von eDiscovery-Administratoren gering halten.

- **Kann ich eine Gruppe als Mitglied der eDiscovery-Manager-Rollengruppe hinzufügen?** Wie bereits erläutert, können Sie eine e-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe eDiscovery Managers in der Rollengruppe eDiscovery-Manager mithilfe des **Add-RoleGroupMember-** Cmdlets in Security & Compliance Center PowerShell hinzufügen. Sie können beispielsweise den folgenden Befehl ausführen, um eine e-Mail-aktivierte Sicherheitsgruppe zur eDiscovery-Manager-Rollengruppe hinzuzufügen. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange-Verteilergruppen und Microsoft 365-Gruppen werden nicht unterstützt. Sie müssen eine e-Mail-aktivierte Sicherheitsgruppe verwenden, die Sie in Exchange Online PowerShell mithilfe des `New-DistributionGroup -Type Security` Befehls erstellen können. Sie können auch eine e-Mail-aktivierte Sicherheitsgruppe (und Mitglieder hinzufügen) im Exchange Admin Center oder im Microsoft 365 Admin Center erstellen. Es kann bis zu 60 Minuten dauern, nachdem Sie es erstellt haben, damit eine neue e-Mail-aktivierte Sicherheit zur Rollengruppe "eDiscovery-Manager" hinzugefügt werden kann. 

    Wie bereits erwähnt, können Sie eine e-Mail-aktivierte Sicherheitsgruppe nicht mithilfe des Cmdlets **Add-eDiscoveryCaseAdmin** in Security & Compliance Center PowerShell als eDiscovery-Administrator festlegen. Sie können nur einzelne Benutzer als eDiscovery-Administratoren hinzufügen.

    Sie können auch keine e-Mail-aktivierte Sicherheitsgruppe als Mitglied einer Anfrage hinzufügen.
