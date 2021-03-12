---
title: Vergleichen von Gruppen
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Hier erfahren Sie, welche Arten von Gruppen Sie verwenden können.
ms.openlocfilehash: dfb726fadbfbcf69a8ff57fa3d9025cd8811e617
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727247"
---
# <a name="compare-groups"></a><span data-ttu-id="76a5f-103">Vergleichen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="76a5f-103">Compare groups</span></span>

<span data-ttu-id="76a5f-104">Im Microsoft 365 Admin Center können Sie im Bereich **Gruppen** die folgenden Gruppentypen erstellen und verwalten:</span><span class="sxs-lookup"><span data-stu-id="76a5f-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="76a5f-105">**Microsoft 365-Gruppen** (vormals Office 365-Gruppen) werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet.</span><span class="sxs-lookup"><span data-stu-id="76a5f-105">**Microsoft 365 groups** (formerly Office 365 groups) are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="76a5f-106">**Verteilergruppen** werden verwendet, um Benachrichtigungen an eine Gruppe von Personen zu senden.</span><span class="sxs-lookup"><span data-stu-id="76a5f-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="76a5f-107">**Sicherheitsgruppen** werden verwendet, um Zugriff auf Ressourcen wie z. B. SharePoint-Sites zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="76a5f-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="76a5f-108">**E-Mail-aktivierte Sicherheitsgruppen** werden verwendet, um Zugriff auf Ressourcen wie z. B. Microsoft Office SharePoint Online zu gewähren und Benachrichtigungen per E-Mail an diese Benutzer zu senden.</span><span class="sxs-lookup"><span data-stu-id="76a5f-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="76a5f-109">**Freigegebene Postfächer** werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support.</span><span class="sxs-lookup"><span data-stu-id="76a5f-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="76a5f-110">Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="76a5f-110">Microsoft 365 groups</span></span>

<span data-ttu-id="76a5f-111">Microsoft 365-Gruppen werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet.</span><span class="sxs-lookup"><span data-stu-id="76a5f-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="76a5f-112">Bei jeder Microsoft 365-Gruppe erhalten Mitglieder eine Gruppen-E-Mail und einen freigegebenen Arbeitsbereich für Unterhaltungen, Dateien, Kalenderereignisse, Stream sowie einen Planner.</span><span class="sxs-lookup"><span data-stu-id="76a5f-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, Stream and a Planner.</span></span>

<span data-ttu-id="76a5f-113">Sie können einer Gruppe Personen von außerhalb Ihres Unternehmens hinzufügen, sofern dieses Feature [vom Administrator aktiviert wurde](manage-guest-access-in-groups.md).</span><span class="sxs-lookup"><span data-stu-id="76a5f-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="76a5f-114">Sie können externen Absendern das Senden von E-Mails an die Gruppen-E-Mail-Adresse gestatten.</span><span class="sxs-lookup"><span data-stu-id="76a5f-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="76a5f-115">Microsoft 365-Gruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder basierend auf Benutzerattributen wie Abteilung, Standort, Position usw. automatisch hinzugefügt oder entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="76a5f-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="76a5f-116">Auf Microsoft 365-Gruppen kann über Mobile Apps wie Outlook für iOS und Outlook für Android zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="76a5f-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="76a5f-117">Gruppenmitglieder können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Gruppen-E-Mail-Adresse senden, sofern dieses Feature [vom Administrator aktiviert wurde](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span><span class="sxs-lookup"><span data-stu-id="76a5f-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="76a5f-118">Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="76a5f-118">Distribution groups</span></span>

<span data-ttu-id="76a5f-119">[Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) werden verwendet, um Benachrichtigungen an eine Gruppe von Personen zu senden.</span><span class="sxs-lookup"><span data-stu-id="76a5f-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="76a5f-120">Verteilergruppen können externe E-Mails empfangen, sofern dieses Feature vom Administrator aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="76a5f-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="76a5f-121">Verteilergruppen eignen sich am besten für Situationen, in denen Sie Informationen an eine Gruppe von Personen übermitteln müssen, z. B. "Personen in Gebäude A" oder "Jeder bei Contoso".</span><span class="sxs-lookup"><span data-stu-id="76a5f-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

<span data-ttu-id="76a5f-122">Verteilergruppen können[auf Microsoft 365-Gruppen aktualisiert werden](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</span><span class="sxs-lookup"><span data-stu-id="76a5f-122">Distribution groups can be [upgraded to Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</span></span>

## <a name="security-groups"></a><span data-ttu-id="76a5f-123">Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="76a5f-123">Security groups</span></span>

<span data-ttu-id="76a5f-124">[Sicherheitsgruppen](../email/create-edit-or-delete-a-security-group.md) werden verwendet, um den Zugriff auf Microsoft 365-Ressourcen wie z. B. SharePoint zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="76a5f-124">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="76a5f-125">Sicherheitsgruppen können die Verwaltung vereinfachen, weil Sie nur die Gruppe verwalten müssen, anstatt Benutzer zu jeder Ressource einzeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76a5f-125">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="76a5f-126">Sicherheitsgruppen können Benutzer oder Geräte enthalten.</span><span class="sxs-lookup"><span data-stu-id="76a5f-126">Security groups can contain users or devices.</span></span> <span data-ttu-id="76a5f-127">Das Erstellen einer Sicherheitsgruppe für Geräte kann mit Verwaltungsdiensten für mobile Geräte (z. B. Intune) erfolgen.</span><span class="sxs-lookup"><span data-stu-id="76a5f-127">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="76a5f-128">Sicherheitsgruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder oder Geräte basierend auf Benutzerattributen wie Abteilung, Standort oder Position bzw. Geräteattributen wie Betriebssystemversion automatisch hinzugefügt oder entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="76a5f-128">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="76a5f-129">E-Mail-aktivierte Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="76a5f-129">Mail-enabled security groups</span></span>

<span data-ttu-id="76a5f-130">E-Mail-aktivierte Sicherheitsgruppen funktionieren wie normale Sicherheitsgruppen, mit dem Unterschied, dass sie nicht dynamisch über Azure Active Directory verwaltet werden können und keine Geräte enthalten können.</span><span class="sxs-lookup"><span data-stu-id="76a5f-130">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="76a5f-131">Sie bieten die Möglichkeit, E-Mails an alle Mitglieder der Gruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="76a5f-131">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="76a5f-132">Freigegebene Postfächer</span><span class="sxs-lookup"><span data-stu-id="76a5f-132">Shared mailboxes</span></span>

<span data-ttu-id="76a5f-133">[Freigegebene Postfächer](../email/create-a-shared-mailbox.md) werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="76a5f-133">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="76a5f-134">Freigegebene Postfächer können externe E-Mails empfangen, wenn der Administrator dieses Feature aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="76a5f-134">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="76a5f-135">Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat.</span><span class="sxs-lookup"><span data-stu-id="76a5f-135">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="76a5f-136">Dies ist besonders nützlich für Hilfe- und Support-Postfächer, da Benutzer E-Mails von "Contoso-Support" oder der "Rezeption von Gebäude A" senden können.</span><span class="sxs-lookup"><span data-stu-id="76a5f-136">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="76a5f-137">Aktuell ist es nicht möglich, ein freigegebenes Postfach zu einer Microsoft 365-Gruppe zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="76a5f-137">Currently it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="76a5f-138">Möchten Sie dies tun?</span><span class="sxs-lookup"><span data-stu-id="76a5f-138">Is this something you want?</span></span> <span data-ttu-id="76a5f-139">Erzählen Sie uns davon.</span><span class="sxs-lookup"><span data-stu-id="76a5f-139">Let us know.</span></span> <span data-ttu-id="76a5f-140">**[Stimmen Sie hier ab](https://go.microsoft.com/fwlink/?linkid=871518)**.</span><span class="sxs-lookup"><span data-stu-id="76a5f-140">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="76a5f-141">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="76a5f-141">Related articles</span></span>

[<span data-ttu-id="76a5f-142">Informationen zu Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="76a5f-142">Learn about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="76a5f-143">Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten</span><span class="sxs-lookup"><span data-stu-id="76a5f-143">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
