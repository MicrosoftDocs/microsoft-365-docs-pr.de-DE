---
title: Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Weisen Sie die erforderlichen Berechtigungen zum Ausführen von eDiscovery-bezogenen Aufgaben mithilfe des Security & Compliance Center zu.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98a731a726798ef463fd6b11f9be84c9f8cc95c0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919943"
---
# <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center

Wenn Sie möchten, dass Benutzer eines der [eDiscovery-bezogenen](ediscovery.md) Tools im Security & Compliance Center in Office 365 oder im Microsoft 365 Compliance Center verwenden, müssen Sie ihnen die entsprechenden Berechtigungen zuweisen. Die einfachste Möglichkeit hierzu besteht darin, die Benutzer der entsprechenden Rollengruppe auf der Seite **Berechtigungen** im Security & Compliance Center hinzuzufügen. In diesem Thema werden die Berechtigungen beschrieben, die zum Ausführen von eDiscovery- und Inhaltssucheaufgaben mithilfe des Security & Compliance Center erforderlich sind.
  
Die primäre eDiscovery-bezogene Rollengruppe im Security & Compliance Center heißt **eDiscovery Manager**. Es gibt zwei Untergruppen innerhalb dieser Rollengruppe.
  
- **eDiscovery-Manager** : Ein eDiscovery-Manager kann das Tool für die Inhaltssuche im Security & Compliance Center verwenden, um Inhaltsstandorte in der Organisation zu durchsuchen und verschiedene suchbezogene Aktionen wie vorschau- und exportbezogene Suchergebnisse durchzuführen. Mitglieder können auch Fälle in Core eDiscovery und Advanced eDiscovery erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, Fallspeicher erstellen, suchten, die einem Fall zugeordnet sind, und auf Falldaten zugreifen. eDiscovery-Manager können nur auf die Fälle, die sie selbst erstellt haben, zugreifen und sie verwalten. Sie können nicht auf Fälle, die von anderen eDiscovery-Managern erstellt wurden, zugreifen oder diese verwalten.
  
- **eDiscovery Administratoren** – Ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager" und kann die gleichen Aufgaben im Zusammenhang mit Inhaltssuche und Fallverwaltung ausführen wie ein eDiscovery-Manager. Außerdem kann ein eDiscovery-Administrator Folgendes:
  
  - Greifen Sie auf alle Fälle zu, die auf den **Seiten eDiscovery** und **Advanced eDiscovery** im Security & Compliance Center aufgeführt sind.

  - Zugriff auf Falldaten in Advanced eDiscovery für jeden beliebigen Fall in der Organisation.
  
  - Verwalten von eDiscovery-Fällen, nachdem sie sich selbst als Fallmitglied hinzugefügt haben.
  
  Gründe, warum Sie eDiscovery-Administratoren in Ihrer Organisation wünschen, finden Sie unter [Weitere Informationen](#more-information).

> [!NOTE]
> Zum Analysieren der Daten eines Benutzers mithilfe von Advanced eDiscovery muss dem Benutzer (dem Verwahrer der Daten) eine Office 365 E5- oder Microsoft 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1- oder Office 365- oder Microsoft 365 E3-Lizenz eine Microsoft 365 E5 Compliance- oder Microsoft 365 eDiscovery- und Audit-Add-On-Lizenz zugewiesen werden. Administratoren, Compliance officers oder Rechtsmitarbeiter, die Fällen als Mitglieder zugewiesen sind und Advanced eDiscovery zum Sammeln, Anzeigen und Analysieren von Daten verwenden, benötigen keine E5-Lizenz. Weitere Informationen zur Advanced eDiscovery-Lizenzierung finden Sie unter [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md).
  
## <a name="confirm-your-roles"></a>Bestätigen Ihrer Rollen

- Sie müssen Mitglied der Rollengruppe Organisationsverwaltung sein oder der Rollenverwaltungsrolle zugewiesen werden, um eDiscovery-Berechtigungen im Security & Compliance Center zu erteilen.

- Sie können das [Cmdlet Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) in Security & Compliance Center PowerShell verwenden, um eine E-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe eDiscovery Managers in der Rollengruppe eDiscovery-Manager hinzuzufügen. Sie können jedoch keine E-Mail-aktivierte Sicherheitsgruppe zur Untergruppe eDiscovery Administrators hinzufügen. Weitere Informationen finden Sie [unter Weitere Informationen](#more-information). 
  
## <a name="assign-ediscovery-permissions-in-the-security--compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Security & Compliance Center

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
  
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.
  
3. Wählen Sie im linken Bereich des Sicherheits- und Compliancecenters Berechtigungen **aus,** und aktivieren Sie dann das Kontrollkästchen neben **eDiscovery Manager**.
  
4. Gehen Sie auf der Flyoutseite des **eDiscovery-Managers** basierend auf den eDiscovery-Berechtigungen, die Sie zuweisen möchten, wie folgt vor.
  
    **So machen Sie einen Benutzer zum eDiscovery-Manager:** Wählen Sie **neben eDiscovery Manager** die Option **Bearbeiten aus.** Wählen Sie **im Abschnitt eDiscovery-Manager** auswählen den Link **eDiscovery-Manager** auswählen aus, und wählen Sie dann Hinzufügen von ![ Symbol hinzufügen ](../media/ITPro-EAC-AddIcon.gif) **aus.** Wählen Sie den Benutzer (oder die Benutzer) aus, den Sie als eDiscovery-Manager hinzufügen möchten, und wählen Sie dann **Hinzufügen aus.** Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Fertig aus.** Wählen Sie dann auf der Seite **Bearbeiten eDiscovery-Manager** auswählen die Option **Speichern** aus, um die Änderungen an der eDiscovery-Manager-Mitgliedschaft zu speichern.
  
    **So machen Sie einen Benutzer zum eDiscovery-Administrator:** Wählen Sie **neben eDiscovery Manager** die Option **Bearbeiten aus.** Wählen Sie im Abschnitt **eDiscovery-Administrator** auswählen unter **eDiscovery-Administratoren** die Option **eDiscovery-Administrator** auswählen aus, wählen Sie Bearbeiten **aus,** und wählen Sie dann Hinzufügen von ![ Symbol hinzufügen ](../media/ITPro-EAC-AddIcon.gif) **aus.** Wählen Sie den Benutzer (oder Benutzer) aus, den Sie als **eDiscovery-Administrator** hinzufügen möchten, und fügen Sie dann **hinzu.** Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Fertig aus.** Wählen Sie dann auf der Seite **Bearbeiten eDiscovery-Administrator** auswählen die Option **Speichern** aus, um die Änderungen an der eDiscovery-Administratormitgliedschaft zu speichern.
  
> [!NOTE]
> Sie können auch das **Cmdlet Add-eDiscoveryCaseAdmin** verwenden, um einen Benutzer zum eDiscovery-Administrator zu machen. Dem Benutzer muss jedoch die Rolle Fallverwaltung zugewiesen werden, bevor Sie dieses Cmdlet zum eDiscovery-Administrator machen können. Weitere Informationen finden Sie unter [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin). 
  
Auf  der Seite Berechtigungen im Security & Compliance Center können Sie Benutzern auch eDiscovery-bezogene Berechtigungen zuweisen, indem Sie sie den Rollengruppen Complianceadministrator, Organisationsverwaltung und Prüfer hinzufügen. Eine Beschreibung der eDiscovery-bezogenen ROLLENGRUPPEN, die jeder dieser Rollengruppen zugewiesen sind, finden Sie unter [RBAC roles related to eDiscovery](#rbac-roles-related-to-ediscovery).

## <a name="rbac-roles-related-to-ediscovery"></a>RbAC-Rollen im Zusammenhang mit eDiscovery

In der folgenden Tabelle sind die eDiscovery-bezogenen Rollen des Security & Compliance Center aufgeführt und die integrierten Rollengruppen aufgeführt, denen jede Rolle standardmäßig zugewiesen ist.
  
| Rolle | Complianceadministrator | eDiscovery Manager & Administrator | Organisationsverwaltung | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Fallverwaltung <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |
|Kommunikation <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Compliance-Suche <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |
|Verwahrer <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exportieren <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |
|Preview <br/>  | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Review <br/>  | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> |
|RMS-Entschlüsselung <br/>  ||![Häkchen](../media/checkmark.png) <br/> |||
|Suchen und Löschen <br/> | <br/> | <br/> |![Häkchen](../media/checkmark.png)           <br/> | <br/> |
||||
  
In den folgenden Abschnitten werden die einzelnen eDiscovery-bezogenen ROLLENAC-Rollen beschrieben, die in der vorherigen Tabelle aufgeführt sind.

### <a name="case-management"></a>Fallverwaltung

Diese Rolle ermöglicht Benutzern das Erstellen, Bearbeiten, Löschen und Steuern des Zugriffs auf Core eDiscovery- und Advanced eDiscovery-Fälle im Security & Compliance Center. Wie bereits erläutert, muss einem Benutzer die Rolle Fallverwaltung zugewiesen werden, bevor Sie das **Cmdlet Add-eDiscoveryCaseAdmin** verwenden können, um sie zu einem eDiscovery-Administrator zu machen.

Weitere Informationen finden Sie unter:

- [Erste Schritte mit Core eDiscovery](get-started-core-ediscovery.md)

- [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Kommunikation

Mit dieser Rolle können Benutzer die gesamte Kommunikation mit den in einem Advanced eDiscovery-Fall identifizierten Verwahrern verwalten. Dazu gehören das Erstellen von Haltebenachrichtigungen, Das Halten von Erinnerungen und Eskalationen für die Verwaltung. Der Benutzer kann auch die Bestätigung von Haltebenachrichtigungen nachverfolgen und den Zugriff auf das Verwahrportal verwalten, das von jedem Custodian zum Nachverfolgen der Kommunikation für fälle verwendet wird, in denen er als Custodian identifiziert wurde.

Weitere Informationen finden Sie unter [Arbeiten mit Kommunikationen in Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Compliance-Suche

Mit dieser Rolle können Benutzer das Tool für die Inhaltssuche im Security & Compliance Center ausführen, um Postfächer und öffentliche Ordner, SharePoint Online-Websites, OneDrive for &, Skype for Business-Unterhaltungen, Microsoft 365-Gruppen und Microsoft Teams sowie Yammer-Gruppen zu durchsuchen. Mit dieser Rolle kann ein Benutzer eine Schätzung der Suchergebnisse erhalten und Exportberichte erstellen. Es sind jedoch zusätzliche Rollen erforderlich, um Inhaltssuchaktionen wie das Anzeigen, Exportieren oder Löschen von Suchergebnissen zu initiieren.

Benutzer, denen die Rolle "Compliancesuche" zugewiesen ist, aber nicht über die Vorschaurolle verfügen, können eine Vorschau der Ergebnisse einer Suche anzeigen, bei der die Vorschauaktion von einem Benutzer initiiert wurde, dem die Vorschaurolle zugewiesen ist. Der Benutzer ohne die Vorschaurolle kann eine Vorschau der Ergebnisse für bis zu zwei Wochen anzeigen, nachdem die erste Vorschauaktion erstellt wurde.

Ebenso können Benutzer, denen die Rolle Compliancesuche zugewiesen ist, aber nicht über die Rolle Export verfügen, die Ergebnisse einer Suche herunterladen, in der die Exportaktion von einem Benutzer initiiert wurde, dem die Rolle Export zugewiesen ist. Der Benutzer ohne die Exportrolle kann die Ergebnisse einer Suche bis zu zwei Wochen nach dem Erstellen der ersten Exportaktion herunterladen. Danach können sie die Ergebnisse nur herunterladen, wenn ein Benutzer mit der Rolle Export den Export neu startet.

Weitere Informationen finden Sie unter [Inhaltssuche in Office 365](content-search.md).

### <a name="custodian"></a>Verwahrer

Mit dieser Rolle können Benutzer Custodians für Advanced eDiscovery-Fälle identifizieren und verwalten und die Informationen aus Azure Active Directory und anderen Quellen verwenden, um Datenquellen zu finden, die Custodians zugeordnet sind. Der Benutzer kann in einem Fall anderen Datenquellen wie Postfächern, SharePoint-Websites und Teams Custodians zuordnen. Der Benutzer kann auch für die Datenquellen, die Custodians zugeordnet sind, einen rechtlichen Halteraum einhalten, um Inhalte im Kontext eines Falls zu erhalten.

Weitere Informationen finden Sie unter [Arbeiten mit Verwahrern in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Exportieren

Mit der Rolle können Benutzer die Ergebnisse einer Inhaltssuche auf einen lokalen Computer exportieren. Außerdem können sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten.

Weitere Informationen zum Exportieren von Suchergebnissen finden Sie unter Exportieren von Suchergebnissen [aus security & Compliance Center](export-search-results.md).

### <a name="hold"></a>Hold

Mit dieser Rolle können Benutzer Inhalte in Postfächern, öffentlichen Ordnern, Websites, Skype for Business-Unterhaltungen und Microsoft 365-Gruppen speichern. Wenn Inhalte aufbewahrt werden, können Inhaltsbesitzer die ursprünglichen Inhalte weiterhin ändern oder löschen, sie werden aber aufbewahrt, bis die Aufbewahrung deaktiviert wird oder die Aufbewahrungsdauer abgelaufen ist.

Weitere Informationen zu Halteinformationen finden Sie unter:

- [Erstellen eines Haltebereichs in Core eDiscovery](create-ediscovery-holds.md) 

- [Erstellen eines Halteraums in Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Preview

Mit dieser Rolle können Benutzer eine Liste der Elemente anzeigen, die von einer Inhaltssuche zurückgegeben wurden. Außerdem können sie die einzelnen Elemente der Liste öffnen und deren Inhalte anzeigen.

### <a name="review"></a>Review

Mit dieser Rolle können Benutzer auf Überprüfungssätze in [Advanced eDiscovery zugreifen.](overview-ediscovery-20.md) Benutzer, denen diese Rolle zugewiesen ist, können die Liste der Fälle auf der **Seite eDiscovery > Advanced** im Microsoft 365 Compliance Center, in dem sie Mitglied sind, anzeigen und öffnen. Nachdem der Benutzer auf einen Advanced eDiscovery-Fall zugegriffen hat, kann er **Sätze überprüfen** auswählen, um auf Falldaten zu zugreifen. Diese Rolle ermöglicht es dem Benutzer nicht, eine Vorschau der Ergebnisse einer Sammlungssuche anzuzeigen, die dem Fall zugeordnet ist, oder andere Such- oder Fallverwaltungsaufgaben auszuführen. Benutzer mit dieser Rolle können nur auf die Daten in einem Überprüfungssatz zugreifen.

### <a name="rms-decrypt"></a>RMS-Entschlüsselung

Mit dieser Rolle können Benutzer durch Rechte geschützte E-Mail-Nachrichten anzeigen, wenn sie eine Vorschau der Suchergebnisse anzeigen und entschlüsselte E-Mail-Nachrichten mit geschützten Rechten exportieren. Mit dieser Rolle können Benutzer auch eine Datei anzeigen [](encryption.md) (und exportieren), die mit einer Microsoft-Verschlüsselungstechnologie verschlüsselt ist, wenn die verschlüsselte Datei an eine E-Mail-Nachricht angefügt wird, die in den Ergebnissen einer eDiscovery-Suche enthalten ist. Darüber hinaus können Benutzer mit dieser Rolle verschlüsselte E-Mail-Anlagen überprüfen und abfragen, die einem Überprüfungssatz in Advanced eDiscovery hinzugefügt werden. Weitere Informationen zur Entschlüsselung in eDiscovery finden Sie unter [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Suchen und Löschen

Mit dieser Rolle können Benutzer Massenentfernungen von Daten durchführen, die den Kriterien einer Inhaltssuche entsprechen. Weitere Informationen finden Sie unter [Suchen und Löschen von E-Mail-Nachrichten in Ihrer Organisation.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Weitere Informationen

- **Gründe für das Festlegen eines eDiscovery-Administrators** Wie bereits erwähnt, ist ein eDiscovery-Administrator Mitglied der Rollengruppe „eDiscovery-Manager“, die alle eDiscovery-Fälle in Ihrer Organisation anzeigen und auf diese zugreifen kann. Dieser Zugriff auf alle eDiscovery-Fälle dient zwei wichtigen Zwecken:

  - Wenn eine Person, die das einzige Mitglied eines eDiscovery-Falls ist, die Organisation verlässt, kann niemand (einschließlich Mitglieder der Rollengruppe „Organisationsverwaltung“ oder andere Mitglieder der Rollengruppe „eDiscovery-Manager“) auf diesen eDiscovery-Fall zugreifen, da diese Personen keine Fallmitglieder sind. In diesem Fall gäbe es keine Möglichkeit, auf die Daten in dem Fall zuzugreifen. Da ein eDiscovery-Administrator jedoch auf alle eDiscovery-Fälle in der Organisation zugreifen kann, kann er den Fall anzeigen und sich selbst oder einen anderen eDiscovery-Manager als Mitglied des Falls hinzufügen.

  - Da ein eDiscovery-Administrator alle Core eDiscovery- und Advanced eDiscovery-Fälle anzeigen und darauf zugreifen kann, kann er alle Fälle und zugehörigen Compliancesuchen überwachen und überwachen. So kann der Missbrauch von Compliancesuchen oder anderen eDiscovery-Fällen verhindert werden. Da eDiscovery-Administratoren Zugriff auf potenziell vertrauliche Informationen in den Ergebnissen einer Compliancesuche haben, sollten Sie die Anzahl von eDiscovery-Administratoren gering halten.

- **Kann ich eine Gruppe als Mitglied der Rollengruppe eDiscovery-Manager hinzufügen?** Wie bereits erläutert, können Sie eine E-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe eDiscovery Managers in der Rollengruppe eDiscovery-Manager hinzufügen, indem Sie das **Cmdlet Add-RoleGroupMember** in Security & Compliance Center PowerShell verwenden. Sie können beispielsweise den folgenden Befehl ausführen, um der Rollengruppe eDiscovery Manager eine E-Mail-aktivierte Sicherheitsgruppe hinzuzufügen. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange-Verteilergruppen und Microsoft 365-Gruppen werden nicht unterstützt. Sie müssen eine E-Mail-aktivierte Sicherheitsgruppe verwenden, die Sie in Exchange Online PowerShell erstellen können, indem Sie `New-DistributionGroup -Type Security` ausführen. Sie können auch eine E-Mail-aktivierte Sicherheitsgruppe (und Mitglieder hinzufügen) im Exchange Admin Center oder im Microsoft 365 Admin Center erstellen. Es kann bis zu 60 Minuten dauern, bis eine neue E-Mail-aktivierte Sicherheit zur Rollengruppe eDiscovery Managers hinzugefügt werden kann. 

    Wie bereits erwähnt, können Sie eine E-Mail-aktivierte Sicherheitsgruppe nicht zu einem eDiscovery-Administrator machen, indem Sie das **Cmdlet Add-eDiscoveryCaseAdmin** in Security & Compliance Center PowerShell verwenden. Sie können nur einzelne Benutzer als eDiscovery-Administratoren hinzufügen.

    Sie können auch keine E-Mail-aktivierte Sicherheitsgruppe als Mitglied eines Falls hinzufügen.