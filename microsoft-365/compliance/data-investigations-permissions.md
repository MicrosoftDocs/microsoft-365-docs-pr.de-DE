---
title: Zuweisen von Berechtigungen für Daten Untersuchungen (Vorschau)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel wird beschrieben, wie Sie die erforderlichen Berechtigungen für die Verwendung des Tools zur Datenermittlung in Microsoft 365 einrichten.
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285441"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="bc8d9-103">Zuweisen von Berechtigungen für Daten Untersuchungen (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="bc8d9-103">Assign permissions for Data Investigations (preview)</span></span>

<span data-ttu-id="bc8d9-104">Für den Zugriff auf eine Daten Untersuchung im Office 365 oder Microsoft 365 Compliance Center müssen Sie Mitglied der Rollengruppe "Data Investigator" sein.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="bc8d9-105">Zum Hinzufügen von Mitgliedern zu einer Rollengruppe müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" sein oder der Rolle "Rollenverwaltung" im Security & Compliance Center zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="bc8d9-106">Nachdem ein Benutzer ein Mitglied der Rollengruppe "Data Investigator" geworden ist, kann er Untersuchungen erstellen, auf Sie zugreifen und diese durchführen, bei denen Sie Mitglied sind.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="bc8d9-107">So weisen Sie Berechtigungen für die Datenermittlung zu:</span><span class="sxs-lookup"><span data-stu-id="bc8d9-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="bc8d9-108">Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="bc8d9-109">Klicken Sie im Security & Compliance Center auf **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="bc8d9-110">Klicken Sie auf die Rollengruppe **Daten Ermittler** , und klicken Sie dann neben **Mitglieder** auf der Flyout-Seite auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="bc8d9-111">Klicken Sie auf **Mitglieder auswählen** , und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="bc8d9-112">Wählen Sie die Benutzer aus, die Sie als Daten Ermittler hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="bc8d9-113">Nachdem Sie alle Benutzer hinzugefügt haben, klicken Sie auf **Fertig** und dann auf **Speichern** , um die Änderungen an der Rollengruppe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="bc8d9-114">Die Verwaltungsrolle "Data Investigation", die der Rollengruppe "Data Investigator" zugewiesen ist, stellt die erforderlichen Berechtigungen für den Zugriff auf das Tool für die Datenermittlung im Office 365 oder im Microsoft 365 Compliance Center bereit.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="bc8d9-115">Standardmäßig ist diese Rolle nicht der Rollengruppe "Organisationsverwaltung" zugewiesen, was bedeutet, dass globale Administratoren in Ihrer Organisation möglicherweise nicht standardmäßig auf das Tool für Daten Ermittlungen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="bc8d9-116">Um dies zu beheben, können Sie der Rollengruppe "Data Investigator" globale Administratoren hinzufügen oder der Rollengruppe "Organisationsverwaltung" die Verwaltungsrolle "Daten Ermittlungsverwaltung" hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="bc8d9-117">Eine dritte Option besteht darin, eine benutzerdefinierte Rollengruppe zu erstellen und die Verwaltungsrolle "Data Investigation" (und andere Rollen) zuzuweisen und dann entsprechende Mitglieder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc8d9-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="bc8d9-118">Weitere Informationen zu Rollengruppen und Rollen finden Sie unter [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="bc8d9-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
