---
title: Informationen zur Exchange Online-Administratorrolle
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
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
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Exchange-Onlineadministratoren verwalten die E-Mails und Postfächer Ihrer Organisation. Beispielsweise stellen sie gelöschte Elemente im Postfach eines Benutzers wiederher. '
ms.openlocfilehash: 4dc1f435571650ae4a805198782c3c24a92024fb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197649"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="91359-104">Informationen zur Exchange Online-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="91359-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="91359-105">Um Ihnen bei der Verwaltung von [](assign-admin-roles.md) Microsoft 365 zu helfen, können Sie Benutzern Berechtigungen zum Verwalten der E-Mails und Postfächer Ihrer Organisation über das [Exchange Admin Center zuweisen.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="91359-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="91359-106">Weisen Sie sie dazu der Exchange-Administratorrolle zu.</span><span class="sxs-lookup"><span data-stu-id="91359-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="91359-107">**Tipp:** Wenn Sie der Exchange-Administratorrolle eine Person zuweisen, weisen Sie sie auch der Dienstadministratorrolle zu.</span><span class="sxs-lookup"><span data-stu-id="91359-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="91359-108">Auf diese Weise können wichtige Informationen im Microsoft 365 Admin Center angezeigt werden, z. B. die Integrität des Exchange Online-Diensts und Änderungs- und Veröffentlichungsbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="91359-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="91359-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="91359-109">Before you begin</span></span>

<span data-ttu-id="91359-110">Hier folgen einige der wichtigsten Aufgaben, die Benutzer ausführen können, wenn ihnen die Exchange-Administratorrolle zugewiesen wurde:</span><span class="sxs-lookup"><span data-stu-id="91359-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="91359-111">Wiederherstellen gelöschter Elemente im Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="91359-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="91359-112">[Richten Sie eine Archiv- und Löschrichtlinie für Postfächer in Ihrer Organisation ein.](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="91359-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="91359-113">Einrichten von Postfachfeatures wie die Postfachfreigaberichtlinie: Wie Benutzer Kalender- und Kontaktinformationen für andere Personen außerhalb Ihrer Organisation freigeben können.</span><span class="sxs-lookup"><span data-stu-id="91359-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="91359-114">Richten Sie "[Senden als](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" und "[Senden im](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)Auftrag " Stellvertretung für das Postfach einer Person ein.</span><span class="sxs-lookup"><span data-stu-id="91359-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="91359-115">Eine Führungskraft möchte z. B., dass ihr Assistent über die Möglichkeit verfügt, E-Mails in ihrem Namen zu senden.</span><span class="sxs-lookup"><span data-stu-id="91359-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="91359-116">[Erstellen Sie ein freigegebenes Postfach,](../email/create-a-shared-mailbox.md) damit eine Gruppe von Personen E-Mails von einer gemeinsamen E-Mail-Adresse überwachen und senden kann.</span><span class="sxs-lookup"><span data-stu-id="91359-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="91359-117">[E-Mail-Antispamschutz-](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) und Schadsoftwarefilter für die Organisation.</span><span class="sxs-lookup"><span data-stu-id="91359-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="91359-118">Verwalten von Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="91359-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="91359-119">Exchange Online-Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="91359-119">Exchange Online role groups</span></span>

<span data-ttu-id="91359-p105">In einer großen Organisation kann der Exchange-Administrator Benutzer zu Exchange-Rollengruppen zuweisen. Wenn ein Administrator einen Benutzer einer Rollengruppe hinzugefügt wird, erhält der Benutzer Berechtigungen, um bestimmte Geschäftsfunktionen auszuführen, die nur Mitgliedern dieser Gruppe gestattet sind.</span><span class="sxs-lookup"><span data-stu-id="91359-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="91359-p106">Der Exchange-Administrator kann z. B. eine Person der Rollengruppe "Discoveryverwaltung" zuweisen, damit sie in Postfächern nach Daten suchen können, die bestimmte Kriterien erfüllen. Weitere Informationen hierzu finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen](/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="91359-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="91359-124">Weitere Informationen zu anderen Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="91359-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="91359-125">Informationen zu Microsoft 365-Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="91359-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="91359-126">Informationen zur SharePoint Online-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="91359-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="91359-127">Informationen zur Skype for Business-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="91359-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="91359-128">Verwenden der Microsoft Teams-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="91359-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)