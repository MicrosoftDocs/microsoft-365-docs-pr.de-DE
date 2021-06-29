---
title: Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 Compliance Center
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
description: Weisen Sie die erforderlichen Berechtigungen zum Ausführen von eDiscovery-bezogenen Aufgaben mithilfe der Microsoft 365 Compliance Center zu.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e75a18c338d2634ae3be93514ee518d9e91860
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194673"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>Zuweisen von eDiscovery-Berechtigungen im Microsoft 365 Compliance Center

Wenn Sie möchten, dass Benutzer eines der [eDiscovery-bezogenen Tools](ediscovery.md) im Microsoft 365 Compliance Center verwenden, müssen Sie ihnen die entsprechenden Berechtigungen zuweisen. Die einfachste Möglichkeit besteht darin, der Person die entsprechende Rollengruppe auf der Seite **"Berechtigungen"** im Compliance Center hinzuzufügen. In diesem Thema werden die berechtigungen beschrieben, die zum Ausführen von eDiscovery-Aufgaben erforderlich sind.
  
Die primäre eDiscovery-bezogene Rollengruppe in Microsoft 365 Compliance Center heißt **eDiscovery-Manager.** Es gibt zwei Untergruppen innerhalb dieser Rollengruppe.
  
- **eDiscovery-Manager** – Ein eDiscovery-Manager kann eDiscovery-Suchtools verwenden, um Inhaltsspeicherorte in der Organisation zu durchsuchen und verschiedene suchbezogene Aktionen wie Vorschau und Export von Suchergebnissen auszuführen. Mitglieder können auch Fälle in Core eDiscovery und Advanced eDiscovery erstellen und verwalten, Mitglieder zu einem Fall hinzufügen und entfernen, Fallarchive erstellen, Suchvorgänge ausführen, die einem Fall zugeordnet sind, und auf Falldaten zugreifen. eDiscovery-Manager können nur auf die Fälle, die sie selbst erstellt haben, zugreifen und sie verwalten. Sie können nicht auf Fälle, die von anderen eDiscovery-Managern erstellt wurden, zugreifen oder diese verwalten.
  
- **eDiscovery Administratoren** – Ein eDiscovery-Administrator ist Mitglied der Rollengruppe "eDiscovery-Manager" und kann die gleichen Aufgaben im Zusammenhang mit Inhaltssuche und Fallverwaltung ausführen wie ein eDiscovery-Manager. Außerdem kann ein eDiscovery-Administrator Folgendes:
  
  - Greifen Sie auf alle Fälle zu, die auf den **Core eDiscovery-** und **Advanced eDiscovery-Seiten** im Microsoft 365 Compliance Center aufgeführt sind.

  - Zugriff auf Falldaten in Advanced eDiscovery für jeden beliebigen Fall in der Organisation.
  
  - Verwalten von eDiscovery-Fällen, nachdem sie sich selbst als Fallmitglied hinzugefügt haben.
  
  Weitere [Informationen](#more-information)finden Sie unter "Gründe für eDiscovery-Administratoren in Ihrer Organisation".

> [!NOTE]
> Um die Daten eines Benutzers mithilfe Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwahrer der Daten) eine Office 365 E5 oder Microsoft 365 E5 Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1 oder einer Office 365 oder Microsoft 365 E3-Lizenz eine Microsoft 365 E5 Compliance- oder Microsoft 365 eDiscovery- und Überwachungs-Add-On-Lizenz zugewiesen werden. Administratoren, Compliance-Beauftragte oder Rechtsmitarbeiter, die Fällen als Mitglieder zugewiesen sind und Advanced eDiscovery verwenden, um Daten zu sammeln, anzuzeigen und zu analysieren, benötigen keine E5-Lizenz. Weitere Informationen zu Advanced eDiscovery Lizenzierung finden Sie unter [Abonnements und Lizenzierung in Advanced eDiscovery.](overview-ediscovery-20.md#subscriptions-and-licensing)
  
## <a name="before-you-assign-permissions"></a>Vor dem Zuweisen von Berechtigungen

- Sie müssen Mitglied der Rollengruppe "Organisationsverwaltung" sein oder der Rollenverwaltungsrolle zugewiesen werden, um eDiscovery-Berechtigungen im Microsoft 365 Compliance Center zuzuweisen.

- Sie können das Cmdlet ["Add-RoleGroupMember"](/powershell/module/exchange/Add-RoleGroupMember) in Security & Compliance Center PowerShell verwenden, um eine E-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe "eDiscovery-Manager" in der Rollengruppe "eDiscovery-Manager" hinzuzufügen. Sie können jedoch keine E-Mail-aktivierte Sicherheitsgruppe zur Untergruppe "eDiscovery-Administratoren" hinzufügen. Ausführliche Informationen finden Sie unter ["Weitere Informationen".](#more-information) 
  
## <a name="assign-ediscovery-permissions"></a>Zuweisen von eDiscovery-Berechtigungen

1. Wechseln Sie zu <https://compliance.microsoft.com> einem Konto, das Berechtigungen zuweisen kann, und melden Sie sich an.
  
2. Wählen Sie im linken Bereich des Microsoft 365 Compliance Center **Berechtigungen** aus.

3. Klicken Sie auf der Seite **"Berechtigungen & Rollen"** im **Compliance Center** auf **"Rollen".**

4. Wählen Sie auf der Rollenseite des **Compliance Centers** **eDiscovery-Manager** aus.
  
5. Führen Sie auf der Flyoutseite des **eDiscovery-Managers** eine der folgenden Aktionen basierend auf den eDiscovery-Berechtigungen aus, die Sie zuweisen möchten.
  
    **So machen Sie einen Benutzer zum eDiscovery-Manager:** Wählen Sie neben **dem eDiscovery-Manager** **"Bearbeiten"** aus. Klicken Sie auf der Assistentenseite **"eDiscovery-Manager auswählen"** auf ![ "Symbol ](../media/ITPro-EAC-AddIcon.gif) **hinzufügen"**. Wählen Sie den Benutzer aus, den Sie als eDiscovery-Manager hinzufügen möchten, und wählen Sie dann **"Hinzufügen"** aus. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Fertig"** aus. Wählen Sie dann auf der Seite **"eDiscovery-Manager-Assistenten bearbeiten"** die Option **"Speichern"** aus, um die Änderungen an der eDiscovery-Manager-Mitgliedschaft zu speichern.
  
    **So machen Sie einen Benutzer zum eDiscovery-Administrator:** Wählen Sie neben **eDiscovery-Administrator** **"Bearbeiten"** aus. Klicken Sie auf der Seite **"eDiscovery-Administrator auswählen"** auf ![ "Symbol ](../media/ITPro-EAC-AddIcon.gif) **hinzufügen"**. Wählen Sie den Benutzer aus, den Sie als **eDiscovery-Administrator** hinzufügen möchten, und  **fügen Sie** dann hinzu. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **"Fertig"** aus. Wählen Sie dann auf der Seite **"eDiscovery-Administrator** auswählen bearbeiten" die Option **"Speichern"** aus, um die Änderungen an der eDiscovery-Administratormitgliedschaft zu speichern.
  
> [!NOTE]
> Sie können auch das Cmdlet **"Add-eDiscoveryCaseAdmin"** verwenden, um einen Benutzer zu einem eDiscovery-Administrator zu machen. Dem Benutzer muss jedoch die Rolle "Fallverwaltung" zugewiesen werden, bevor Sie dieses Cmdlet zum eDiscovery-Administrator machen können. Weitere Informationen finden Sie unter [Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin). 
  
Auf der Seite **"Berechtigungen"** im Microsoft 365 Compliance Center können Sie Benutzern auch eDiscovery-bezogene Berechtigungen zuweisen, indem Sie sie den Rollengruppen "Complianceadministrator", "Organisationsverwaltung" und "Prüfer" hinzufügen. Eine Beschreibung der eDiscovery-bezogenen RBAC-Rollen, die jeder dieser Rollengruppen zugewiesen sind, finden Sie unter [RBAC-Rollen im Zusammenhang mit eDiscovery.](#rbac-roles-related-to-ediscovery)

## <a name="rbac-roles-related-to-ediscovery"></a>RBAC-Rollen im Zusammenhang mit eDiscovery

Die folgende Tabelle enthält die eDiscovery-bezogenen RBAC-Rollen im Microsoft 365 Compliance Center und gibt die integrierten Rollengruppen an, denen jede Rolle standardmäßig zugewiesen ist.
  
| Rolle | Complianceadministrator | eDiscovery-Manager & Administrator | Organisationsverwaltung | Reviewer |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Fallverwaltung <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |
|Kommunikation <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Compliance-Suche <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |
|Verwahrer <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exportieren <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Hold <br/>  |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |
|Vorschau <br/>  | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> | <br/> |
|Überprüfung <br/>  | <br/> |![Häkchen](../media/checkmark.png) <br/> | <br/> |![Häkchen](../media/checkmark.png) <br/> |
|RMS Decrypt <br/>  ||![Häkchen](../media/checkmark.png) <br/> |||
|Suchen und Löschen <br/> | <br/> | <br/> |![Häkchen](../media/checkmark.png)           <br/> | <br/> |
||||
  
In den folgenden Abschnitten werden die einzelnen eDiscovery-bezogenen RBAC-Rollen beschrieben, die in der vorherigen Tabelle aufgeführt sind.

### <a name="case-management"></a>Fallverwaltung

Mit dieser Rolle können Benutzer den Zugriff auf Core eDiscovery und Advanced eDiscovery Fälle im Microsoft 365 Compliance Center erstellen, bearbeiten, löschen und steuern. Wie zuvor erläutert, muss einem Benutzer die Rolle "Fallverwaltung" zugewiesen werden, bevor Sie das Cmdlet **"Add-eDiscoveryCaseAdmin"** verwenden können, um sie zu einem eDiscovery-Administrator zu machen.

Weitere Informationen finden Sie unter:

- [Erste Schritte mit Core eDiscovery](get-started-core-ediscovery.md)

- [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Kommunikation

Mit dieser Rolle können Benutzer die gesamte Kommunikation mit den in einem Advanced eDiscovery Fall identifizierten Verwahrern verwalten. Dies umfasst das Erstellen von Aufbewahrungsbenachrichtigungen, Aufbewahrungserinnerungen und Eskalationen für die Verwaltung. Der Benutzer kann auch die Bestätigung von Aufbewahrungsbenachrichtigungen für Verwahrer nachverfolgen und den Zugriff auf das Verwahrerportal verwalten, das von jedem Verwahrer verwendet wird, um die Kommunikation für die Fälle nachzuverfolgen, in denen er als Verwahrer identifiziert wurde.

Weitere Informationen finden Sie unter [Arbeiten mit Kommunikationen in Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Compliance-Suche

Mit dieser Rolle können Benutzer das Tool für die Inhaltssuche im Microsoft 365 Compliance Center ausführen, um Postfächer und öffentliche Ordner, SharePoint Onlinewebsites, OneDrive for Business Websites, Skype for Business Unterhaltungen, Microsoft 365 Gruppen und Microsoft Teams und Yammer Gruppen zu durchsuchen. Diese Rolle ermöglicht es einem Benutzer, eine Schätzung der Suchergebnisse abzurufen und Exportberichte zu erstellen. Andere Rollen sind jedoch erforderlich, um Inhaltssuchaktionen zu initiieren, z. B. anzeigen, exportieren oder Löschen von Suchergebnissen.

In der Inhaltssuche und Core eDiscovery können Benutzer, denen die Rolle "Compliancesuche" zugewiesen ist, jedoch nicht über die Rolle "Vorschau" verfügt, eine Vorschau der Ergebnisse einer Suche anzeigen, in der die Vorschauaktion von einem Benutzer initiiert wurde, dem die Rolle "Vorschau" zugewiesen ist. Der Benutzer ohne die Vorschaurolle kann bis zu zwei Wochen nach erstellung der ersten Vorschauaktion eine Vorschau der Ergebnisse anzeigen.

Ebenso können Benutzer in der Inhaltssuche und Core eDiscovery, denen die Rolle "Compliancesuche" zugewiesen ist, aber nicht über die Exportrolle verfügt, die Ergebnisse einer Suche herunterladen, in der die Exportaktion von einem Benutzer initiiert wurde, dem die Exportrolle zugewiesen ist. Der Benutzer ohne die Exportrolle kann die Ergebnisse einer Suche bis zu zwei Wochen nach erstellung der anfänglichen Exportaktion herunterladen. Danach können sie die Ergebnisse nur herunterladen, wenn eine Person mit der Exportrolle den Export neu startet.

Die zweiwöchige Karenzzeit für die Vorschau und den Export von Suchergebnissen (ohne die entsprechenden Such- und Exportrollen) gilt nicht für Advanced eDiscovery. Benutzern müssen die Rollen "Vorschau" und "Export" zugewiesen werden, um Inhalte in Advanced eDiscovery anzeigen und exportieren zu können.

### <a name="custodian"></a>Verwahrer

Mit dieser Rolle können Benutzer Verwahrer für Advanced eDiscovery Fälle identifizieren und verwalten und die Informationen aus Azure Active Directory und anderen Quellen verwenden, um Datenquellen zu finden, die mit Verwahrern verknüpft sind. Der Benutzer kann in einem Fall andere Datenquellen wie Postfächer, SharePoint Websites und Teams mit Verwahrern verknüpfen. Der Benutzer kann auch die Datenquellen, die Mitverwahrern zugeordnet sind, gesetzlich sperren, um Inhalte im Kontext eines Falls beizubehalten.

Weitere Informationen finden Sie unter [Arbeiten mit Verwahrern in Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Exportieren

Mit der Rolle können Benutzer die Ergebnisse einer Inhaltssuche auf einen lokalen Computer exportieren. Außerdem können sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten.

Weitere Informationen zum Exportieren von Suchergebnissen finden Sie unter [Exportieren von Suchergebnissen aus Microsoft 365 Compliance Center](export-search-results.md).

### <a name="hold"></a>Hold

Mit dieser Rolle können Benutzer Inhalte in Postfächern, öffentlichen Ordnern, Websites, Skype for Business Unterhaltungen und Microsoft 365 Gruppen aufbewahren. Wenn Inhalte aufbewahrt werden, können Inhaltsbesitzer die ursprünglichen Inhalte weiterhin ändern oder löschen, sie werden aber aufbewahrt, bis die Aufbewahrung deaktiviert wird oder die Aufbewahrungsdauer abgelaufen ist.

Weitere Informationen zu Haltebereichen finden Sie unter:

- [Erstellen eines Haltebereichs in Core eDiscovery](create-ediscovery-holds.md) 

- [Erstellen eines Haltebereichs in Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Vorschau

Mit dieser Rolle können Benutzer eine Liste von Elementen anzeigen, die von einer Inhaltssuche zurückgegeben wurden. Außerdem können sie die einzelnen Elemente der Liste öffnen und deren Inhalte anzeigen.

### <a name="review"></a>Überprüfung

Mit dieser Rolle können Benutzer auf Prüfdateisätze in [Advanced eDiscovery](overview-ediscovery-20.md)zugreifen. Benutzer, denen diese Rolle zugewiesen ist, können die Liste der Fälle auf der Seite **"eDiscovery > Erweitert"** im Microsoft 365 Compliance Center sehen und öffnen, in dem sie Mitglieder sind. Nachdem der Benutzer auf einen Advanced eDiscovery Fall zugegriffen hat, kann er **Prüfdateisätze** auswählen, um auf Falldaten zuzugreifen. Mit dieser Rolle kann der Benutzer keine Vorschau der Ergebnisse einer Sammlungssuche anzeigen, die dem Fall zugeordnet ist, oder andere Such- oder Fallverwaltungsaufgaben ausführen. Benutzer mit dieser Rolle können nur auf die Daten in einem Prüfdateisatz zugreifen.

### <a name="rms-decrypt"></a>RMS Decrypt

Mit dieser Rolle können Benutzer E-Mail-Nachrichten anzeigen, die rechtegeschützt sind, wenn sie Suchergebnisse in der Vorschau anzeigen und entschlüsselte E-Mail-Nachrichten mit geschützten Rechten exportieren. Mit dieser Rolle können Benutzer auch eine Datei anzeigen (und exportieren), die mit einer [Microsoft-Verschlüsselungstechnologie](encryption.md) verschlüsselt ist, wenn die verschlüsselte Datei an eine E-Mail-Nachricht angefügt ist, die in den Ergebnissen einer eDiscovery-Suche enthalten ist. Darüber hinaus können Benutzer mit dieser Rolle verschlüsselte E-Mail-Anlagen überprüfen und abfragen, die einem Prüfdateisatz in Advanced eDiscovery hinzugefügt werden. Weitere Informationen zur Entschlüsselung in eDiscovery finden Sie unter [Entschlüsselung in Microsoft 365 eDiscovery-Tools.](ediscovery-decryption.md)

### <a name="search-and-purge"></a>Suchen und Löschen

Mit dieser Rolle können Benutzer Daten, die den Kriterien einer Inhaltssuche entsprechen, massenweise entfernen. Weitere Informationen finden Sie unter Suchen nach und Löschen von [E-Mail-Nachrichten in Ihrer Organisation.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Weitere Informationen

- **Gründe für das Festlegen eines eDiscovery-Administrators** Wie bereits erwähnt, ist ein eDiscovery-Administrator Mitglied der Rollengruppe „eDiscovery-Manager“, die alle eDiscovery-Fälle in Ihrer Organisation anzeigen und auf diese zugreifen kann. Dieser Zugriff auf alle eDiscovery-Fälle dient zwei wichtigen Zwecken:

  - Wenn eine Person, die das einzige Mitglied eines eDiscovery-Falls ist, die Organisation verlässt, kann niemand (einschließlich Mitglieder der Rollengruppe „Organisationsverwaltung“ oder andere Mitglieder der Rollengruppe „eDiscovery-Manager“) auf diesen eDiscovery-Fall zugreifen, da diese Personen keine Fallmitglieder sind. In diesem Fall gäbe es keine Möglichkeit, auf die Daten in dem Fall zuzugreifen. Da ein eDiscovery-Administrator jedoch auf alle eDiscovery-Fälle in der Organisation zugreifen kann, kann er den Fall anzeigen und sich selbst oder einen anderen eDiscovery-Manager als Mitglied des Falls hinzufügen.

  - Da ein eDiscovery-Administrator alle Core eDiscovery- und Advanced eDiscovery-Fälle anzeigen und darauf zugreifen kann, kann er alle Fälle und zugehörige Compliancesuchen überwachen und überwachen. So kann der Missbrauch von Compliancesuchen oder anderen eDiscovery-Fällen verhindert werden. Da eDiscovery-Administratoren Zugriff auf potenziell vertrauliche Informationen in den Ergebnissen einer Compliancesuche haben, sollten Sie die Anzahl von eDiscovery-Administratoren gering halten.

- **Kann ich eine Gruppe als Mitglied der Rollengruppe "eDiscovery-Manager" hinzufügen?** Wie zuvor erläutert, können Sie eine E-Mail-aktivierte Sicherheitsgruppe als Mitglied der Untergruppe "eDiscovery-Manager" in der Rollengruppe "eDiscovery-Manager" hinzufügen, indem Sie das Cmdlet **"Add-RoleGroupMember"** in Security & Compliance Center PowerShell verwenden. Sie können beispielsweise den folgenden Befehl ausführen, um der Rollengruppe "eDiscovery-Manager" eine E-Mail-aktivierte Sicherheitsgruppe hinzuzufügen. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange Verteilergruppen und Microsoft 365 Gruppen werden nicht unterstützt. Sie müssen eine E-Mail-aktivierte Sicherheitsgruppe verwenden, die Sie in Exchange Online PowerShell erstellen können, indem Sie `New-DistributionGroup -Type Security` . Sie können auch eine E-Mail-aktivierte Sicherheitsgruppe im Exchange Admin Center oder im Microsoft 365 Admin Center erstellen (und Mitglieder hinzufügen). Es kann bis zu 60 Minuten dauern, nachdem Sie es erstellt haben, damit eine neue E-Mail-aktivierte Sicherheit zur Rollengruppe "eDiscovery-Manager" hinzugefügt werden kann. 

    Wie bereits erwähnt, können Sie eine E-Mail-aktivierte Sicherheitsgruppe nicht als eDiscovery-Administrator festlegen, indem Sie das Cmdlet **"Add-eDiscoveryCaseAdmin"** in Security & Compliance Center PowerShell verwenden. Sie können nur einzelne Benutzer als eDiscovery-Administratoren hinzufügen.

    Sie können auch keine E-Mail-aktivierte Sicherheitsgruppe als Mitglied eines Falls hinzufügen.