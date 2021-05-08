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
ms.openlocfilehash: 9f36688972f00a27a274b6a974d958d1d590aa93
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243984"
---
# <a name="compare-groups"></a><span data-ttu-id="9b858-103">Vergleichen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="9b858-103">Compare groups</span></span>

<span data-ttu-id="9b858-104">Im Microsoft 365 Admin Center können Sie im Bereich **Gruppen** die folgenden Gruppentypen erstellen und verwalten:</span><span class="sxs-lookup"><span data-stu-id="9b858-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="9b858-105">**Microsoft 365-Gruppen** (vormals Office 365-Gruppen) werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b858-105">**Microsoft 365 groups** (formerly Office 365 groups) are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="9b858-106">**Verteilergruppen** werden verwendet, um E-Mail-Benachrichtigungen an eine Gruppe von Personen zu senden.</span><span class="sxs-lookup"><span data-stu-id="9b858-106">**Distribution groups** are used for sending email notifications to a group of people.</span></span>
- <span data-ttu-id="9b858-107">**Sicherheitsgruppen** werden verwendet, um Zugriff auf Ressourcen wie z. B. SharePoint-Sites zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="9b858-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="9b858-108">**E-Mail-aktivierte Sicherheitsgruppen** werden verwendet, um Zugriff auf Ressourcen wie z. B. Microsoft Office SharePoint Online zu gewähren und Benachrichtigungen per E-Mail an diese Benutzer zu senden.</span><span class="sxs-lookup"><span data-stu-id="9b858-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="9b858-109">**Freigegebene Postfächer** werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support.</span><span class="sxs-lookup"><span data-stu-id="9b858-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="9b858-110">Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="9b858-110">Microsoft 365 groups</span></span>

<span data-ttu-id="9b858-111">Microsoft 365-Gruppen werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b858-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="9b858-112">Bei jeder Microsoft 365-Gruppe erhalten Mitglieder eine Gruppen-E-Mail und einen freigegebenen Arbeitsbereich für Unterhaltungen, Dateien, Kalenderereignisse, Stream sowie einen Planner.</span><span class="sxs-lookup"><span data-stu-id="9b858-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, Stream and a Planner.</span></span>

<span data-ttu-id="9b858-113">Sie können einer Gruppe Personen von außerhalb Ihres Unternehmens hinzufügen, sofern dieses Feature [vom Administrator aktiviert wurde](manage-guest-access-in-groups.md).</span><span class="sxs-lookup"><span data-stu-id="9b858-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="9b858-114">Sie können externen Absendern das Senden von E-Mails an die Gruppen-E-Mail-Adresse gestatten.</span><span class="sxs-lookup"><span data-stu-id="9b858-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="9b858-115">Microsoft 365-Gruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder basierend auf Benutzerattributen wie Abteilung, Standort, Position usw. automatisch hinzugefügt oder entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="9b858-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="9b858-116">Auf Microsoft 365-Gruppen kann über Mobile Apps wie Outlook für iOS und Outlook für Android zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9b858-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="9b858-117">Gruppenmitglieder können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Gruppen-E-Mail-Adresse senden, sofern dieses Feature [vom Administrator aktiviert wurde](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).</span><span class="sxs-lookup"><span data-stu-id="9b858-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="9b858-118">Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="9b858-118">Distribution groups</span></span>

<span data-ttu-id="9b858-119">[Verteilergruppen](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) werden verwendet, um Benachrichtigungen an eine Gruppe von Personen zu senden.</span><span class="sxs-lookup"><span data-stu-id="9b858-119">[Distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="9b858-120">Verteilergruppen können externe E-Mails empfangen, sofern dieses Feature vom Administrator aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="9b858-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="9b858-121">Verteilergruppen eignen sich am besten für Situationen, in denen Sie Informationen an eine Gruppe von Personen übermitteln müssen, z. B. "Personen in Gebäude A" oder "Jeder bei Contoso".</span><span class="sxs-lookup"><span data-stu-id="9b858-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

<span data-ttu-id="9b858-122">Verteilergruppen können[auf Microsoft 365-Gruppen aktualisiert werden](../manage/upgrade-distribution-lists.md).</span><span class="sxs-lookup"><span data-stu-id="9b858-122">Distribution groups can be [upgraded to Microsoft 365 groups](../manage/upgrade-distribution-lists.md).</span></span>

<span data-ttu-id="9b858-123">Verteilergruppen können in Microsoft Teams zu einem Team hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9b858-123">Distribution groups can be added to a team in Microsoft Teams.</span></span>

## <a name="security-groups"></a><span data-ttu-id="9b858-124">Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="9b858-124">Security groups</span></span>

<span data-ttu-id="9b858-125">[Sicherheitsgruppen](../email/create-edit-or-delete-a-security-group.md) werden verwendet, um den Zugriff auf Microsoft 365-Ressourcen wie z. B. SharePoint zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="9b858-125">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="9b858-126">Sicherheitsgruppen können die Verwaltung vereinfachen, weil Sie nur die Gruppe verwalten müssen, anstatt Benutzer zu jeder Ressource einzeln hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b858-126">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="9b858-p105">Sicherheitsgruppen können Benutzer oder Geräte enthalten. Das Erstellen einer Sicherheitsgruppe für Geräte kann mit Verwaltungsdiensten für mobile Geräte (z. B. Intune) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b858-p105">Security groups can contain users or devices. Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="9b858-129">Sicherheitsgruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder oder Geräte basierend auf Benutzerattributen wie Abteilung, Standort oder Position bzw. Geräteattributen wie Betriebssystemversion automatisch hinzugefügt oder entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="9b858-129">Security groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

<span data-ttu-id="9b858-130">Sicherheitsgruppen können zu einem Team hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9b858-130">Security groups can be added to a team.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="9b858-131">E-Mail-aktivierte Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="9b858-131">Mail-enabled security groups</span></span>

<span data-ttu-id="9b858-132">E-Mail-aktivierte Sicherheitsgruppen funktionieren wie normale Sicherheitsgruppen, mit dem Unterschied, dass sie nicht dynamisch über Azure Active Directory verwaltet werden können und keine Geräte enthalten können.</span><span class="sxs-lookup"><span data-stu-id="9b858-132">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="9b858-133">Sie bieten die Möglichkeit, E-Mails an alle Mitglieder der Gruppe zu senden.</span><span class="sxs-lookup"><span data-stu-id="9b858-133">They include the ability to send mail to all the members of the group.</span></span>

<span data-ttu-id="9b858-134">E-Mail-aktivierte Sicherheitsgruppen können zu einem Team hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9b858-134">Mail-enabled security groups can be added to a team.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="9b858-135">Freigegebene Postfächer</span><span class="sxs-lookup"><span data-stu-id="9b858-135">Shared mailboxes</span></span>

<span data-ttu-id="9b858-136">[Freigegebene Postfächer](../email/create-a-shared-mailbox.md) werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9b858-136">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="9b858-137">Freigegebene Postfächer können externe E-Mails empfangen, wenn der Administrator dieses Feature aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="9b858-137">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="9b858-138">Freigegebene Postfächer beinhalten einen Kalender, der für die Zusammenarbeit verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9b858-138">Shared mailboxes include a calendar that can be used for collaboration.</span></span>

<span data-ttu-id="9b858-139">Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat.</span><span class="sxs-lookup"><span data-stu-id="9b858-139">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="9b858-140">Dies ist besonders nützlich für Hilfe- und Support-Postfächer, da Benutzer E-Mails von "Contoso-Support" oder der "Rezeption von Gebäude A" senden können.</span><span class="sxs-lookup"><span data-stu-id="9b858-140">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="9b858-141">Aktuell ist es nicht möglich, ein freigegebenes Postfach zu einer Microsoft 365-Gruppe zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="9b858-141">Currently it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="9b858-142">Möchten Sie dies tun?</span><span class="sxs-lookup"><span data-stu-id="9b858-142">Is this something you want?</span></span> <span data-ttu-id="9b858-143">Erzählen Sie uns davon.</span><span class="sxs-lookup"><span data-stu-id="9b858-143">Let us know.</span></span> <span data-ttu-id="9b858-144">**[Stimmen Sie hier ab](https://go.microsoft.com/fwlink/?linkid=871518)**.</span><span class="sxs-lookup"><span data-stu-id="9b858-144">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-content"></a><span data-ttu-id="9b858-145">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="9b858-145">Related content</span></span>

<span data-ttu-id="9b858-146">[Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9b858-146">[Learn about Microsoft 365 groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (article)</span></span>

<span data-ttu-id="9b858-147">[Warum Sie Ihre Verteilerlisten zu Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="9b858-147">[Why you should upgrade your distribution lists to groups in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (article)</span></span>
