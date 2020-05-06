---
title: Entwerfen einer isolierten SharePoint Online-Teamwebsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Entwerfen Sie isolierte SharePoint Online Teamwebsites, einschließlich bestimmen von Berechtigungsstufen, Zuweisen von Berechtigungen für Benutzer mit Zugriffsgruppen und geschachtelten Azure Ad Gruppen.
ms.openlocfilehash: 4663a0b9710fc05d0b063a3100d3b5ac223a2161
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034840"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Entwerfen einer isolierten SharePoint Online-Teamwebsite

 **Zusammenfassung:** Lernen Sie die Schritte zum Entwerfen von isolierten SharePoint Online-Teamwebsites kennen.
  
In diesem Artikel werden die wichtigsten Entwurfsentscheidungen erläutert, die Sie vor der Erstellung einer isolierten SharePoint Online-Teamwebsite treffen müssen.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Phase 1: Ermitteln der SharePoint-Gruppen und Berechtigungsstufen

Jede SharePoint Online-Teamwebsite wird standardmäßig mit den folgenden SharePoint-Gruppen erstellt:
  
- \<Websitename> Mitglieder
    
- \<Websitename> Besucher
    
- \<Websitename> Besitzer
    
Diese Gruppen sind von Microsoft 365-und Azure Active Directory (AD)-Gruppen getrennt und bilden die Grundlage für die Zuweisung von Berechtigungen für die Ressourcen der Website.
  
Der Satz von spezifischen Berechtigungen, der bestimmt, welche Aktionen ein Mitglied einer SharePoint-Gruppe auf einer Website ausführen kann, ist eine Berechtigungsstufe. Für eine SharePoint Online-Teamwebsite gibt es standardmäßig drei Berechtigungsstufen: Bearbeitungszugriff, Lesezugriff und Vollzugriff. In der folgenden Tabelle ist die standardmäßige Korrelation von SharePoint-Gruppen und zugewiesenen Berechtigungsstufen dargestellt:
  
|**SharePoint-Gruppe**|**Berechtigungsstufe**|
|:-----|:-----|
|\<Websitename> Mitglieder  <br/> |Bearbeiten  <br/> |
|\<Websitename> Besucher  <br/> |Read  <br/> |
|\<Websitename> Besitzer  <br/> |Vollzugriff  <br/> |
   
 **Bewährte Methode:** Sie können weitere SharePoint-Gruppen und Berechtigungsstufen erstellen. Allerdings wird empfohlen, die SharePoint-Standardgruppen und die Berechtigungsstufen für die isolierte SharePoint Online-Website zu verwenden.
  
Hier sind die standardmäßigen SharePoint-Gruppen und Berechtigungsstufen.
  
![Die SharePoint-Standardgruppen und-Berechtigungsstufen für eine SharePoint Online Website.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Phase 2: Zuweisen von Berechtigungen zu Benutzern mit Zugriffsgruppen

Sie können Benutzern Berechtigungen zuweisen, indem Sie Ihrem Benutzerkonto oder einer Microsoft 365-oder Azure Ad-Gruppe, der das Benutzerkonto angehört, die SharePoint-Gruppen hinzufügen. Einmal hinzugefügt, werden die Benutzerkonten, entweder direkt oder indirekt über die Mitgliedschaft in einer Microsoft 365-oder Azure Ad-Gruppe, der SharePoint-Gruppe zugeordneten Berechtigungsstufe zugeordnet.
  
Am Beispiel der SharePoint-Standardgruppen bedeutet dies:
  
- Mitglieder der SharePoint-Gruppe " ** \<Websitename> Mitglieder** ", die sowohl Benutzerkonten als auch Gruppen enthalten kann, werden der Berechtigungsstufe **Bearbeiten** zugewiesen.
    
- Mitglieder der SharePoint-Gruppe " ** \<Websitename> Besucher** ", die sowohl Benutzerkonten als auch Gruppen enthalten kann, werden mit der Berechtigungsstufe " **Lesen** " versehen.
    
- Mitglieder der SharePoint-Gruppe " ** \<Websitename> Besitzer** ", die sowohl Benutzerkonten als auch Gruppen enthalten kann, werden mit der Berechtigungsstufe " **Vollzugriff** " versehen.
    
 **Bewährte Methode:** Obwohl Sie Berechtigungen über einzelne Benutzerkonten verwalten können, empfehlen wir stattdessen die Verwendung einer einzelnen Azure AD-Gruppe, die als Zugriffsgruppe bezeichnet wird. Dadurch wird die Verwaltung von Berechtigungen über Mitgliedschaft in der Zugriffsgruppe anstelle der Verwaltung der Liste von Benutzerkonten für jede SharePoint-Gruppe erleichtert.
  
Azure Ad Gruppen für Microsoft 365 unterscheiden sich von Microsoft 365-Gruppen. Azure Ad Gruppen werden im Microsoft 365 Admin Center angezeigt, deren **Typ** auf **Sicherheit** festgelegt ist und keine e-Mail-Adresse hat. Azure AD-Gruppen können verwaltet werden in:
  
- Active Directory-Domänendienste (AD DS, Active Directory Domain Services)
    
    Dabei handelt es sich um Gruppen, die in Ihrer lokalen AD DS Infrastruktur erstellt und mit Ihrem Microsoft 365-Abonnement synchronisiert wurden. Im Microsoft 365 Admin Center haben diese Gruppen den **Status** **synchronisiert mit Active Directory**.
    
- Office 365
    
    Dabei handelt es sich um Gruppen, die entweder mit dem Microsoft 365 Admin Center, dem Azure-Portal oder mit Microsoft PowerShell erstellt wurden. Im Microsoft 365 Admin Center haben diese Gruppen den **Status** **Cloud**.
    
 **Bewährte Methode:** Wenn Sie AD DS lokal verwenden und mit Ihrem Microsoft 365-Abonnement synchronisieren, führen Sie die Benutzer-und Gruppenverwaltung mit AD DS aus.
  
Für isolierte SharePoint Online-Teamwebsites sieht die empfohlene Gruppenstruktur wie folgt aus:
  
|**SharePoint-Gruppe**|**Azure AD-basierte Zugriffsgruppe**|**Berechtigungsstufe**|
|:-----|:-----|:-----|
|\<Websitename> Mitglieder  <br/> |\<Websitename> Mitglieder  <br/> |Bearbeiten  <br/> |
|\<Websitename> Besucher  <br/> |\<Websitename> Viewer  <br/> |Read  <br/> |
|\<Websitename> Besitzer  <br/> |\<Websitename> Administratoren  <br/> |Vollzugriff  <br/> |
   
 **Bewährte Methode:** Sie können zwar entweder Microsoft 365-oder Azure Ad-Gruppen als Mitglieder von SharePoint-Gruppen verwenden, es wird jedoch empfohlen, Azure Ad Gruppen zu verwenden. Azure Ad Gruppen, die über AD DS oder Microsoft 365 verwaltet werden, bieten Ihnen mehr Flexibilität bei der Verwendung von geschachtelten Gruppen zum Zuweisen von Berechtigungen.
  
Im folgenden finden Sie die standardmäßigen SharePoint-Gruppen, die für die Verwendung von Azure AD basierten Zugriffsgruppen konfiguriert sind.
  
![Verwenden von Zugriffsgruppen als Mitglieder von Standard SharePoint Online Websitegruppen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
Beachten Sie beim Entwerfen der drei Zugriffsgruppen die folgenden Punkte:
  
- Es sollte nur einige wenige Mitglieder im ** \<Websitenamen> Administrators** -Zugriffsgruppe geben, die einer kleinen Anzahl von SharePoint Online Administratoren entsprechen, die die Teamwebsite verwalten.
    
- Die meisten ihrer Websitemitglieder befinden sich im ** \<Websitenamen> Mitglieder** oder ** \<Websitename> Viewer** -Zugriffsgruppen. Da Websitemitglieder im ** \<Websitenamen> Mitglieder** Zugriffsgruppe die Möglichkeit haben, Ressourcen auf der Website zu löschen oder zu ändern, sollten Sie die Mitgliedschaft sorgfältig prüfen. Wenn Sie Zweifel haben, fügen Sie das Website Mitglied dem ** \<Websitenamen> Viewer** -Zugriffsgruppe hinzu.
    
Im folgenden finden Sie ein Beispiel für die SharePoint-Gruppen und Zugriffsgruppen für eine isolierte Website mit dem Namen ProjectX.
  
![Ein Beispiel für die Verwendung von Zugriffsgruppen für eine SharePoint Online Website mit dem Namen ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Phase 3: Verwenden von geschachtelten Azure AD-Gruppen

Für ein Projekt, das auf eine kleine Anzahl von Personen beschränkt ist, ist es in den meisten Fällen ausreichend, den SharePoint-Gruppen der Website eine einzelne Ebene von Azure AD-basierten Zugriffsgruppen hinzuzufügen. Wenn jedoch eine große Anzahl von Personen vorhanden ist und diese Personen bereits Mitglied in bestehenden Azure AD-Gruppen sind, können Sie SharePoint-Berechtigungen einfacher mithilfe geschachtelter Gruppen zuweisen, d. h. Gruppen, die andere Gruppen als Mitglieder enthalten.
  
Beispiel: Sie möchten eine isolierte SharePoint Online-Teamwebsite für die Zusammenarbeit zwischen den Leitern der Abteilungen Vertrieb, Marketing, Technik, Recht und Support erstellen, und diese Abteilungen haben bereits eigene Gruppen mit Benutzerkonten der Führungskräfte als Mitgliedern. Anstatt eine neue Gruppe für die neuen Websitemitglieder zu erstellen und alle einzelnen Benutzerkonten der Führungskräfte hinzuzufügen, fügen Sie die vorhandenen Führungskräftegruppen für die einzelnen Abteilung zur neuen Gruppe hinzu.
  
 Wenn Sie ein Microsoft 365-Abonnement für mehrere Organisationen freigeben, kann eine einzelne Ebene der Gruppenmitgliedschaft für einen isolierten Standort für eine Organisation aufgrund der schieren Anzahl von Benutzerkonten schwierig zu verwalten sein. In diesem Fall können Sie zum Verwalten der Berechtigungen geschachtelte Azure AD-Gruppen für jede Organisation verwenden, die die Gruppen innerhalb der Organisationen enthalten.
  
So verwenden Sie geschachtelte Azure AD-Gruppen:
  
1. Identifizieren oder erstellen Sie die Azure AD-Gruppen, die Benutzerkonten enthalten sollen, und fügen Sie die entsprechenden Benutzerkonten als Mitglieder hinzu.
    
2. Erstellen Sie die Azure AD-basierte Containerzugriffsgruppe, die die anderen Azure AD-Gruppen enthalten soll, und fügen Sie die Gruppen als Mitglieder hinzu.
    
3.   Um die entsprechende Zugriffsebene für die Containerzugriffsgruppe festzulegen, identifizieren Sie die SharePoint-Gruppe und die entsprechende Berechtigungsstufe.
    
> [!NOTE]
> Sie können keine geschachtelten Microsoft 365-Gruppen verwenden. 
  
Im folgenden finden Sie ein Beispiel für geschachtelte Azure Ad Gruppen für die ProjectX-Mitglieder Zugriffsgruppe.
  
![Ein Beispiel für die Verwendung von geschachtelten Zugriffsgruppen für die Mitglieder Zugriffsgruppe für die ProjectX-Website.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Da alle Benutzerkonten in den Teams für Forschung, Entwicklung und Projektleitung als Websitemitglieder dienen sollen, ist es einfacher, ihre Azure Ad Gruppen zur Zugriffsgruppe ProjectX-Mitglieder hinzuzufügen.
  
## <a name="next-step"></a>Nächster Schritt

Wenn Sie eine isolierte Website in der Produktion erstellen und konfigurieren möchten, finden Sie entsprechende Informationen unter [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Siehe auch

[Isolierte SharePoint Online-Teamwebsites](isolated-sharepoint-online-team-sites.md)
  
[Verwalten einer isolierten SharePoint Online-Teamwebsite](manage-an-isolated-sharepoint-online-team-site.md)

[Bereitstellen einer isolierten SharePoint Online-Teamwebsite](deploy-an-isolated-sharepoint-online-team-site.md)



