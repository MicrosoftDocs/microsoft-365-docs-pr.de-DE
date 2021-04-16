---
title: Erstellen und Verwalten von Gerätegruppen in Microsoft Defender for Endpoint
description: Erstellen von Gerätegruppen und Festlegen automatisierter Behebungsstufen für diese Gruppen, indem Sie die regeln, die für die Gruppe gelten, verwechseln
keywords: Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln,Ad-Gruppe, Rolle, Zuweisen, Rang
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acd24e5c87a74bbb32835ec170a121c5c0b6bb33
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860303"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="7f77c-104">Erstellen und Verwalten von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="7f77c-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7f77c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7f77c-105">**Applies to:**</span></span>
- <span data-ttu-id="7f77c-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7f77c-106">Azure Active Directory</span></span>
- <span data-ttu-id="7f77c-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="7f77c-107">Office 365</span></span>

> <span data-ttu-id="7f77c-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7f77c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7f77c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7f77c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7f77c-110">In einem Unternehmensszenario wird Sicherheitsbetriebsteams in der Regel eine Reihe von Geräten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="7f77c-111">Diese Geräte werden basierend auf einer Reihe von Attributen wie ihren Domänen, Computernamen oder festgelegten Tags gruppieren.</span><span class="sxs-lookup"><span data-stu-id="7f77c-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="7f77c-112">In Microsoft Defender for Endpoint können Sie Gerätegruppen erstellen und verwenden, um:</span><span class="sxs-lookup"><span data-stu-id="7f77c-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="7f77c-113">Einschränken des Zugriffs auf verwandte Warnungen und Daten auf bestimmte Azure AD-Benutzergruppen mit [zugewiesenen ROLLEN-ROLLEN](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="7f77c-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="7f77c-114">Konfigurieren verschiedener Einstellungen für die automatische Korrektur für verschiedene Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="7f77c-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="7f77c-115">Zuweisen bestimmter Korrekturstufen, die während automatisierter Untersuchungen angewendet werden</span><span class="sxs-lookup"><span data-stu-id="7f77c-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="7f77c-116">Filtern Sie in einer Untersuchung die **Liste Geräte** mithilfe des Gruppenfilters nach **bestimmten Gerätegruppen.**</span><span class="sxs-lookup"><span data-stu-id="7f77c-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="7f77c-117">Sie können Gerätegruppen im Kontext des rollenbasierten Zugriffs (Role-Based Access, RBAC) erstellen, um zu steuern, wer bestimmte Aktionen ergreifen kann, oder Informationen sehen, indem Sie die Gerätegruppen einer Benutzergruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="7f77c-118">Weitere Informationen finden Sie unter [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="7f77c-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="7f77c-119">Einen umfassenden Einblick in die RBAC-Anwendung finden Sie unter: [Wird Ihr SOC mit RBAC flach ausgeführt.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="7f77c-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="7f77c-120">Im Rahmen des Erstellens einer Gerätegruppe werden Sie:</span><span class="sxs-lookup"><span data-stu-id="7f77c-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="7f77c-121">Legen Sie die automatische Behebungsstufe für diese Gruppe fest.</span><span class="sxs-lookup"><span data-stu-id="7f77c-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="7f77c-122">Weitere Informationen zu Korrekturstufen finden Sie unter Verwenden der automatisierten Untersuchung zum Untersuchen und Behebung [von Bedrohungen](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="7f77c-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="7f77c-123">Geben Sie die Übereinstimmende Regel an, die bestimmt, welche Gerätegruppe zu der Gruppe gehört, basierend auf dem Gerätenamen, der Domäne, den Tags und der Betriebssystemplattform.</span><span class="sxs-lookup"><span data-stu-id="7f77c-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="7f77c-124">Wenn ein Gerät auch mit anderen Gruppen abgestimmt ist, wird es nur der am höchsten bewerteten Gerätegruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7f77c-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="7f77c-125">Wählen Sie die Azure AD-Benutzergruppe aus, die Zugriff auf die Gerätegruppe haben soll.</span><span class="sxs-lookup"><span data-stu-id="7f77c-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="7f77c-126">Rangieren Sie die Gerätegruppe relativ zu anderen Gruppen, nachdem sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7f77c-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="7f77c-127">Auf eine Gerätegruppe kann für alle Benutzer zugegriffen werden, wenn Sie ihr keine Azure AD-Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="7f77c-128">Erstellen einer Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="7f77c-128">Create a device group</span></span>

1. <span data-ttu-id="7f77c-129">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerätegruppen aus.**</span><span class="sxs-lookup"><span data-stu-id="7f77c-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="7f77c-130">Klicken **Sie auf Gerätegruppe hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="7f77c-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="7f77c-131">Geben Sie den Gruppennamen und die Automatisierungseinstellungen ein, und geben Sie die Übereinstimmungsregel an, die bestimmt, welche Geräte zur Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="7f77c-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="7f77c-132">Weitere [Informationen finden Sie unter Starten der automatisierten Untersuchung.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="7f77c-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="7f77c-133">Wenn Sie Geräte nach Organisationseinheit gruppieren möchten, können Sie den Registrierungsschlüssel für die Gruppenzugehörigkeit konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7f77c-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="7f77c-134">Weitere Informationen zum Taggen von Geräten finden Sie unter [Create and manage device tags](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7f77c-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="7f77c-135">Zeigen Sie eine Vorschau mehrerer Geräte an, die mit dieser Regel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="7f77c-136">Wenn Sie mit der Regel zufrieden sind, klicken Sie auf die **Registerkarte Benutzerzugriff.**</span><span class="sxs-lookup"><span data-stu-id="7f77c-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="7f77c-137">Weisen Sie die Benutzergruppen zu, die auf die von Ihnen erstellte Gerätegruppe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7f77c-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="7f77c-138">Sie können nur Zugriff auf Azure AD-Benutzergruppen gewähren, die ROLLENAC-Rollen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="7f77c-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="7f77c-139">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="7f77c-139">Click **Close**.</span></span> <span data-ttu-id="7f77c-140">Die Konfigurationsänderungen werden angewendet.</span><span class="sxs-lookup"><span data-stu-id="7f77c-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="7f77c-141">Verwalten von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="7f77c-141">Manage device groups</span></span>

<span data-ttu-id="7f77c-142">Sie können die Rangfolge einer Gerätegruppe höher oder tieferstufen, sodass sie beim Abgleich eine höhere oder niedrigere Priorität hat.</span><span class="sxs-lookup"><span data-stu-id="7f77c-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="7f77c-143">Wenn ein Gerät mit mehreren Gruppen abgestimmt ist, wird es nur der gruppe mit der höchsten Rangranggruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7f77c-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="7f77c-144">Sie können auch Gruppen bearbeiten und löschen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="7f77c-145">Das Löschen einer Gerätegruppe kann sich auf E-Mail-Benachrichtigungsregeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="7f77c-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="7f77c-146">Wenn eine Gerätegruppe unter einer E-Mail-Benachrichtigungsregel konfiguriert ist, wird sie aus dieser Regel entfernt.</span><span class="sxs-lookup"><span data-stu-id="7f77c-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="7f77c-147">Wenn die Gerätegruppe die einzige Gruppe ist, die für eine E-Mail-Benachrichtigung konfiguriert ist, wird diese E-Mail-Benachrichtigungsregel zusammen mit der Gerätegruppe gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7f77c-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="7f77c-148">Standardmäßig sind Gerätegruppen für alle Benutzer mit Portalzugriff zugänglich.</span><span class="sxs-lookup"><span data-stu-id="7f77c-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="7f77c-149">Sie können das Standardverhalten ändern, indem Sie der Gerätegruppe Azure AD-Benutzergruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="7f77c-150">Geräte, die nicht mit Gruppen übereinstimmen, werden der Gruppe Nicht gruppierende Geräte (Standard)-Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7f77c-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="7f77c-151">Sie können den Rang dieser Gruppe nicht ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="7f77c-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="7f77c-152">Sie können jedoch die Behebungsstufe dieser Gruppe ändern und die Azure AD-Benutzergruppen definieren, die auf diese Gruppe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7f77c-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="7f77c-153">Das Anwenden von Änderungen an der Gerätegruppenkonfiguration kann bis zu mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="7f77c-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f77c-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7f77c-154">Related topics</span></span>

- [<span data-ttu-id="7f77c-155">Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="7f77c-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="7f77c-156">Erstellen und Verwalten von Gerätekategorien</span><span class="sxs-lookup"><span data-stu-id="7f77c-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="7f77c-157">Abrufen einer Liste der Mandantengerätegruppen mithilfe der Graph-API</span><span class="sxs-lookup"><span data-stu-id="7f77c-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
