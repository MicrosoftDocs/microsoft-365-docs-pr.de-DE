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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: Entwerfen Sie isolierte SharePoint Online-Teamwebsites, einschließlich der Bestimmung von Berechtigungsstufen, zuweisen von Berechtigungen zu Benutzern mit Zugriffsgruppen und geschachtelten Azure AD-Gruppen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0f92a925948dbf6c8c5c1beb6b9c709f508c4b3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165511"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Entwerfen einer isolierten SharePoint Online-Teamwebsite

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


 **Zusammenfassung:** Lernen Sie die Schritte zum Entwerfen von isolierten SharePoint Online-Teamwebsites kennen.

In diesem Artikel werden die wichtigsten Entwurfsentscheidungen erläutert, die Sie vor der Erstellung einer isolierten SharePoint Online-Teamwebsite treffen müssen.

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Phase 1: Ermitteln der SharePoint-Gruppen und Berechtigungsstufen

Jede SharePoint Online-Teamwebsite wird standardmäßig mit den folgenden SharePoint-Gruppen erstellt:

- \<site name> Member

- \<site name> Besucher

- \<site name> Besitzer

Diese Gruppen sind von Microsoft 365- und Azure Active Directory (AD)-Gruppen getrennt und stellen die Grundlage für die Zuweisung von Berechtigungen für die Ressourcen der Website bereit.

Der Satz von spezifischen Berechtigungen, der bestimmt, welche Aktionen ein Mitglied einer SharePoint-Gruppe auf einer Website ausführen kann, ist eine Berechtigungsstufe. Für eine SharePoint Online-Teamwebsite gibt es standardmäßig drei Berechtigungsstufen: Bearbeitungszugriff, Lesezugriff und Vollzugriff. In der folgenden Tabelle ist die standardmäßige Korrelation von SharePoint-Gruppen und zugewiesenen Berechtigungsstufen dargestellt:

****

|SharePoint-Gruppe|Berechtigungsstufe|
|---|---|
|\<site name> Member|Bearbeiten|
|\<site name> Besucher|Lesen|
|\<site name> Besitzer|Vollzugriff|
|

 **Bewährte Methode:** Sie können weitere SharePoint-Gruppen und Berechtigungsstufen erstellen. Allerdings wird empfohlen, die SharePoint-Standardgruppen und die Berechtigungsstufen für die isolierte SharePoint Online-Website zu verwenden.

Hier sind die standardmäßigen SharePoint-Gruppen und -Berechtigungsstufen.

![Die standardmäßigen SharePoint-Gruppen und -Berechtigungsstufen für eine SharePoint Online-Website.](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Phase 2: Zuweisen von Berechtigungen zu Benutzern mit Zugriffsgruppen

Sie können Benutzern Berechtigungen zuweisen, indem Sie ihr Benutzerkonto oder eine Microsoft 365- oder Azure AD-Gruppe, in der das Benutzerkonto Mitglied ist, den SharePoint-Gruppen hinzufügen. Nach dem Hinzufügen werden den Benutzerkonten, entweder direkt oder indirekt über die Mitgliedschaft in einer Microsoft 365- oder Azure AD-Gruppe, die der SharePoint-Gruppe zugeordnete Berechtigungsstufe zugewiesen.

Am Beispiel der SharePoint-Standardgruppen bedeutet dies:

- Mitgliedern der **\<site name> Mitglieder der** SharePoint-Gruppe, die Benutzerkonten und Gruppen umfassen kann, wird die Berechtigungsstufe "Bearbeiten"  zugewiesen.

- Mitgliedern der **\<site name> Besucher-SharePoint-Gruppe,** die Sowohl Benutzerkonten als auch Gruppen umfassen kann, wird die Berechtigungsstufe "Lesen"  zugewiesen.

- Mitgliedern der **\<site name> Besitzer-SharePoint-Gruppe,** die Sowohl Benutzerkonten als auch Gruppen umfassen kann, wird die Berechtigungsstufe **"Vollpunkt"** zugewiesen.

 **Bewährte Methode:** Obwohl Sie Berechtigungen über einzelne Benutzerkonten verwalten können, empfehlen wir stattdessen die Verwendung einer einzelnen Azure AD-Gruppe, die als Zugriffsgruppe bezeichnet wird. Dadurch wird die Verwaltung von Berechtigungen über Mitgliedschaft in der Zugriffsgruppe anstelle der Verwaltung der Liste von Benutzerkonten für jede SharePoint-Gruppe erleichtert.

Azure AD-Gruppen für Microsoft 365 sind unterschiedliche Microsoft 365-Gruppen. Azure AD-Gruppen werden im Microsoft 365 Admin Center angezeigt, deren **Typ** auf **"Sicherheit"** festgelegt ist und keine E-Mail-Adresse haben. Azure AD-Gruppen können verwaltet werden in:

- Active Directory-Domänendienste (AD DS)

    Dies sind Gruppen, die in Ihrer lokalen AD DS-Infrastruktur erstellt und mit Ihrem Microsoft 365-Abonnement synchronisiert wurden. Im Microsoft 365 Admin Center haben diese Gruppen den **Status** "Synchronisiert mit **Active Directory".**

- Office 365

    Dies sind Gruppen, die mit dem Microsoft 365 Admin Center, dem Azure-Portal oder Microsoft PowerShell erstellt wurden. Im Microsoft 365 Admin Center haben diese Gruppen den **Status** **"Cloud".**

 **Bewährte Methode:** Wenn Sie AD DS lokal verwenden und mit Ihrem Microsoft 365-Abonnement synchronisieren, führen Sie die Benutzer- und Gruppenverwaltung mit AD DS durch.

Für isolierte SharePoint Online-Teamwebsites sieht die empfohlene Gruppenstruktur wie folgt aus:

****

|SharePoint-Gruppe|Azure AD-basierte Zugriffsgruppe|Berechtigungsstufe|
|---|---|---|
|\<site name> Member|\<site name> Member|Bearbeiten|
|\<site name> Besucher|\<site name> Viewer|Lesen|
|\<site name> Besitzer|\<site name> Administratoren|Vollzugriff|
|

 **Bewährte Methode:** Obwohl Sie entweder Microsoft 365- oder Azure AD-Gruppen als Mitglieder von SharePoint-Gruppen verwenden können, empfehlen wir die Verwendung von Azure AD-Gruppen. Azure AD-Gruppen, die entweder über AD DS oder Microsoft 365 verwaltet werden, bieten Ihnen mehr Flexibilität bei der Verwendung geschachtelter Gruppen zum Zuweisen von Berechtigungen.

Hier sind die standardmäßigen SharePoint-Gruppen, die für die Verwendung von Azure AD-basierten Zugriffsgruppen konfiguriert sind.

![Verwenden von Zugriffsgruppen als Mitglieder standardmäßiger SharePoint Online-Websitegruppen.](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

Beachten Sie beim Entwerfen der drei Zugriffsgruppen die folgenden Punkte:

- In der Zugriffsgruppe "Administratoren" sollten nur wenige Mitglieder vorhanden sein, die einer kleinen Anzahl von SharePoint Online-Administratoren, die die Teamwebsite verwalten, entspricht. **\<site name>**

- Die meisten Ihrer Websitemitglieder befinden sich in den **\<site name> Zugriffsgruppen "Mitglieder"** oder **\<site name> "Viewer".** Da Websitemitglieder in **\<site name> der** Zugriffsgruppe "Mitglieder" die Möglichkeit haben, Ressourcen auf der Website zu löschen oder zu ändern, sollten Sie deren Mitgliedschaft sorgfältig abschätzen. Fügen Sie im Zweifelsfall das Websitemitglied der Zugriffsgruppe **\<site name> "Viewer"** hinzu.

Hier ist ein Beispiel für die SharePoint-Gruppen und Zugriffsgruppen für eine isolierte Website mit dem Namen ProjectX.

![Ein Beispiel für die Verwendung von Zugriffsgruppen für eine SharePoint Online-Website mit dem Namen ProjectX.](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a>Phase 3: Verwenden von geschachtelten Azure AD-Gruppen

Für ein Projekt, das auf eine kleine Anzahl von Personen beschränkt ist, ist es in den meisten Fällen ausreichend, den SharePoint-Gruppen der Website eine einzelne Ebene von Azure AD-basierten Zugriffsgruppen hinzuzufügen. Wenn jedoch eine große Anzahl von Personen vorhanden ist und diese Personen bereits Mitglied in bestehenden Azure AD-Gruppen sind, können Sie SharePoint-Berechtigungen einfacher mithilfe geschachtelter Gruppen zuweisen, d. h. Gruppen, die andere Gruppen als Mitglieder enthalten.

Beispiel: Sie möchten eine isolierte SharePoint Online-Teamwebsite für die Zusammenarbeit zwischen den Leitern der Abteilungen Vertrieb, Marketing, Technik, Recht und Support erstellen, und diese Abteilungen haben bereits eigene Gruppen mit Benutzerkonten der Führungskräfte als Mitgliedern. Anstatt eine neue Gruppe für die neuen Websitemitglieder zu erstellen und alle einzelnen Benutzerkonten der Führungskräfte hinzuzufügen, fügen Sie die vorhandenen Führungskräftegruppen für die einzelnen Abteilung zur neuen Gruppe hinzu.

 Wenn Sie ein Microsoft 365-Abonnement für mehrere Organisationen freigeben, kann eine einzelne Ebene der Gruppenmitgliedschaft für eine isolierte Website für eine Organisation aufgrund der einfachen Anzahl von Benutzerkonten schwierig zu verwalten sein. In diesem Fall können Sie zum Verwalten der Berechtigungen geschachtelte Azure AD-Gruppen für jede Organisation verwenden, die die Gruppen innerhalb der Organisationen enthalten.

So verwenden Sie geschachtelte Azure AD-Gruppen:

1. Identifizieren oder erstellen Sie die Azure AD-Gruppen, die Benutzerkonten enthalten sollen, und fügen Sie die entsprechenden Benutzerkonten als Mitglieder hinzu.

2. Erstellen Sie die Azure AD-basierte Containerzugriffsgruppe, die die anderen Azure AD-Gruppen enthalten soll, und fügen Sie die Gruppen als Mitglieder hinzu.

3.  Um die entsprechende Zugriffsebene für die Containerzugriffsgruppe festzulegen, identifizieren Sie die SharePoint-Gruppe und die entsprechende Berechtigungsstufe.

> [!NOTE]
> Sie können keine geschachtelten Microsoft 365-Gruppen verwenden.

Hier ist ein Beispiel für geschachtelte Azure AD-Gruppen für die ProjectX-Mitgliederzugriffsgruppe.

![Ein Beispiel für die Verwendung von geschachtelten Zugriffsgruppen für die Mitgliederzugriffsgruppe für die ProjectX-Website.](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

Da alle Benutzerkonten in den Teams "Forschung", "Technik" und "Project Leads" Websitemitglieder sein sollen, ist es einfacher, ihre Azure AD-Gruppen der Zugriffsgruppe "ProjectX-Mitglieder" hinzuzufügen.

## <a name="next-step"></a>Nächster Schritt

Wenn Sie eine isolierte Website in der Produktion erstellen und konfigurieren möchten, finden Sie entsprechende Informationen unter [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Siehe auch

[Isolierte SharePoint Online-Teamwebsites](isolated-sharepoint-online-team-sites.md)

[Verwalten einer isolierten SharePoint Online-Teamwebsite](manage-an-isolated-sharepoint-online-team-site.md)

[Bereitstellen einer isolierten SharePoint Online-Teamwebsite](deploy-an-isolated-sharepoint-online-team-site.md)
