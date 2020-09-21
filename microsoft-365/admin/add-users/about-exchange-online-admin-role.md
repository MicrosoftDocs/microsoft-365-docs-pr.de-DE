---
title: Informationen zur Exchange Online-Administratorrolle
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 'Exchange Online-Administratoren verwalten die e-Mails und Postfächer Ihrer Organisation. Beispielsweise werden gelöschte Elemente im Postfach eines Benutzers wiederhergestellt. '
ms.openlocfilehash: be4c8a4f1c75402d690cc705dd408c9070e40c9b
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131770"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="d2d10-104">Informationen zur Exchange Online-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="d2d10-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="d2d10-105">Zur Unterstützung der Verwaltung von Microsoft 365 können Sie Benutzern Berechtigungen zum Verwalten der e-Mails und Postfächer Ihrer Organisation über das [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?LinkID=271807) [zuweisen](assign-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="d2d10-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="d2d10-106">Weisen Sie sie dazu der Exchange-Administratorrolle zu.</span><span class="sxs-lookup"><span data-stu-id="d2d10-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="d2d10-107">**Tipp**: Wenn Sie eine Person der Exchange-Administratorrolle zuweisen, weisen Sie Sie auch der Dienstadministrator Rolle zu.</span><span class="sxs-lookup"><span data-stu-id="d2d10-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="d2d10-108">Auf diese Weise werden wichtige Informationen im Microsoft 365 Admin Center angezeigt, beispielsweise die Integrität des Exchange Online Diensts sowie Änderungs-und Freigabe Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="d2d10-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d2d10-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="d2d10-109">Before you begin</span></span>

<span data-ttu-id="d2d10-110">Hier folgen einige der wichtigsten Aufgaben, die Benutzer ausführen können, wenn ihnen die Exchange-Administratorrolle zugewiesen wurde:</span><span class="sxs-lookup"><span data-stu-id="d2d10-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="d2d10-111">Wiederherstellen gelöschter Elemente im Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="d2d10-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="d2d10-112">[Richten Sie eine Archivierungs-und Löschrichtlinie für Postfächer in Ihrer Organisation ein](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="d2d10-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="d2d10-113">Einrichten von Postfachfeatures wie die Postfachfreigaberichtlinie: Wie Benutzer Kalender- und Kontaktinformationen für andere Personen außerhalb Ihrer Organisation freigeben können.</span><span class="sxs-lookup"><span data-stu-id="d2d10-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="d2d10-114">Einrichten der Delegaten "[Senden als](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" und "[Senden bei abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" für das Postfach eines anderen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d2d10-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="d2d10-115">Eine Führungskraft möchte z. B., dass ihr Assistent über die Möglichkeit verfügt, E-Mails in ihrem Namen zu senden.</span><span class="sxs-lookup"><span data-stu-id="d2d10-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="d2d10-116">[Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md) , damit eine Gruppe von Personen e-Mails über eine gemeinsame e-Mail-Adresse überwachen und senden kann.</span><span class="sxs-lookup"><span data-stu-id="d2d10-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="d2d10-117">[E-Mail-Anti-Spam-Schutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) und Malware Filter für die Organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d10-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="d2d10-118">Verwalten von Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d2d10-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="d2d10-119">Exchange Online-Rollengruppen</span><span class="sxs-lookup"><span data-stu-id="d2d10-119">Exchange Online role groups</span></span>

<span data-ttu-id="d2d10-p105">In einer großen Organisation kann der Exchange-Administrator Benutzer zu Exchange-Rollengruppen zuweisen. Wenn ein Administrator einen Benutzer einer Rollengruppe hinzugefügt wird, erhält der Benutzer Berechtigungen, um bestimmte Geschäftsfunktionen auszuführen, die nur Mitgliedern dieser Gruppe gestattet sind.</span><span class="sxs-lookup"><span data-stu-id="d2d10-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="d2d10-p106">Der Exchange-Administrator kann z. B. eine Person der Rollengruppe "Discoveryverwaltung" zuweisen, damit sie in Postfächern nach Daten suchen können, die bestimmte Kriterien erfüllen. Weitere Informationen hierzu finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="d2d10-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-role"></a><span data-ttu-id="d2d10-124">Informationen zur anderen Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="d2d10-124">Learn about other admin role</span></span>

- [<span data-ttu-id="d2d10-125">Informationen zu Microsoft 365-Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="d2d10-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="d2d10-126">Informationen zur SharePoint Online-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="d2d10-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="d2d10-127">Informationen zur Skype for Business-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="d2d10-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="d2d10-128">Verwenden der Microsoft Teams-Administratorrolle</span><span class="sxs-lookup"><span data-stu-id="d2d10-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 