---
title: Erstellen und Verwalten von Gerätegruppen in Microsoft Defender für Endpunkt
description: Erstellen Sie Gerätegruppen, und legen Sie automatisierte Korrekturstufen für sie fest, indem Sie die für die Gruppe geltenden Regeln bestätigen.
keywords: Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln, AAD-Gruppe, Rolle, zuweisen, Rangfolge
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
ms.openlocfilehash: 49bd90d8a082f55622e54976cc8fc78229d8c646
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453537"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="674a4-104">Erstellen und Verwalten von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="674a4-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="674a4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="674a4-105">**Applies to:**</span></span>
- <span data-ttu-id="674a4-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="674a4-106">Azure Active Directory</span></span>
- <span data-ttu-id="674a4-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="674a4-107">Office 365</span></span>

> <span data-ttu-id="674a4-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="674a4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="674a4-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="674a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="674a4-110">In einem Unternehmensszenario werden Sicherheitsteams in der Regel eine Gruppe von Geräten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="674a4-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="674a4-111">Diese Geräte werden basierend auf einer Reihe von Attributen wie Domänen, Computernamen oder bestimmten Tags gruppiert.</span><span class="sxs-lookup"><span data-stu-id="674a4-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="674a4-112">In Microsoft Defender für Endpunkt können Sie Gerätegruppen erstellen und für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="674a4-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="674a4-113">Beschränken des Zugriffs auf verwandte Warnungen und Daten auf bestimmte Azure AD-Benutzergruppen mit [zugewiesenen RBAC-Rollen](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="674a4-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="674a4-114">Konfigurieren unterschiedlicher Einstellungen für die automatische Problembehebung für unterschiedliche Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="674a4-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="674a4-115">Zuweisen bestimmter Korrekturstufen, die während automatisierter Untersuchungen angewendet werden sollen</span><span class="sxs-lookup"><span data-stu-id="674a4-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="674a4-116">Filtern Sie in einer Untersuchung die **Geräteliste** mithilfe des **Gruppenfilters** nach bestimmten Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="674a4-116">In an investigation, filter the **Devices list** to specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="674a4-117">Sie können Gerätegruppen im Kontext des rollenbasierten Zugriffs (Role-Based Access, RBAC) erstellen, um zu steuern, wer bestimmte Aktionen ausführen oder Informationen anzeigen kann, indem Sie einer Benutzergruppe die Gerätegruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="674a4-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="674a4-118">Weitere Informationen finden Sie unter [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung.](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="674a4-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="674a4-119">Einen umfassenden Einblick in die RBAC-Anwendung finden Sie unter: [Wird Ihr SOC flach mit RBAC ausgeführt.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="674a4-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="674a4-120">Im Rahmen des Erstellungsprozesses einer Gerätegruppe gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="674a4-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="674a4-121">Legen Sie die automatische Korrekturstufe für diese Gruppe fest.</span><span class="sxs-lookup"><span data-stu-id="674a4-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="674a4-122">Weitere Informationen zu Korrekturstufen finden Sie unter [Verwenden der automatisierten Untersuchung, um Bedrohungen zu untersuchen und zu beheben.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="674a4-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="674a4-123">Geben Sie die Übereinstimmungsregel an, die basierend auf dem Gerätenamen, der Domäne, den Tags und der Betriebssystemplattform bestimmt, welche Gerätegruppe zur Gruppe gehört.</span><span class="sxs-lookup"><span data-stu-id="674a4-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="674a4-124">Wenn ein Gerät auch anderen Gruppen zugeordnet ist, wird es nur der Gerätegruppe mit dem höchsten Rang hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="674a4-124">If a device is also matched to other groups, it's added only to the highest ranked device group.</span></span>
- <span data-ttu-id="674a4-125">Wählen Sie die Azure AD-Benutzergruppe aus, die Zugriff auf die Gerätegruppe haben soll.</span><span class="sxs-lookup"><span data-stu-id="674a4-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="674a4-126">Rangfolge der Gerätegruppe relativ zu anderen Gruppen nach der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="674a4-126">Rank the device group relative to other groups after it's created.</span></span>

>[!NOTE]
><span data-ttu-id="674a4-127">Eine Gerätegruppe ist für alle Benutzer zugänglich, wenn Sie ihr keine Azure AD-Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="674a4-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="674a4-128">Erstellen einer Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="674a4-128">Create a device group</span></span>

1. <span data-ttu-id="674a4-129">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpunktberechtigungsgerätegruppen**  >    >  aus.</span><span class="sxs-lookup"><span data-stu-id="674a4-129">In the navigation pane, select **Settings** > **Endpoints** > **Permissions** > **Device groups**.</span></span>

2. <span data-ttu-id="674a4-130">Klicken Sie auf **"Gerätegruppe hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="674a4-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="674a4-131">Geben Sie den Gruppennamen und die Automatisierungseinstellungen ein, und geben Sie die entsprechende Regel an, die bestimmt, welche Geräte zur Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="674a4-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="674a4-132">Erfahren [Sie, wie die automatisierte Untersuchung beginnt.](automated-investigations.md#how-the-automated-investigation-starts)</span><span class="sxs-lookup"><span data-stu-id="674a4-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="674a4-133">Wenn Sie Geräte nach Organisationseinheit gruppieren möchten, können Sie den Registrierungsschlüssel für die Gruppenmitgliedschaft konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="674a4-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="674a4-134">Weitere Informationen zum Gerätetagging finden Sie unter [Erstellen und Verwalten von Gerätetags.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="674a4-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="674a4-135">Anzeigen einer Vorschau mehrerer Geräte, die mit dieser Regel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="674a4-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="674a4-136">Wenn Sie mit der Regel zufrieden sind, klicken Sie auf die Registerkarte **"Benutzerzugriff".**</span><span class="sxs-lookup"><span data-stu-id="674a4-136">If you're satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="674a4-137">Weisen Sie die Benutzergruppen zu, die auf die von Ihnen erstellte Gerätegruppe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="674a4-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="674a4-138">Sie können nur Azure AD-Benutzergruppen Zugriff gewähren, die RBAC-Rollen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="674a4-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="674a4-139">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="674a4-139">Click **Close**.</span></span> <span data-ttu-id="674a4-140">Die Konfigurationsänderungen werden angewendet.</span><span class="sxs-lookup"><span data-stu-id="674a4-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="674a4-141">Verwalten von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="674a4-141">Manage device groups</span></span>

<span data-ttu-id="674a4-142">Sie können den Rang einer Gerätegruppe höher oder tiefer stufen, sodass sie während des Abgleichs eine höhere oder niedrigere Priorität erhält.</span><span class="sxs-lookup"><span data-stu-id="674a4-142">You can promote or demote the rank of a device group so that it's given higher or lower priority during matching.</span></span> <span data-ttu-id="674a4-143">Wenn ein Gerät mit mehr als einer Gruppe abgeglichen wird, wird es nur der Gruppe mit dem höchsten Rang hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="674a4-143">When a device is matched to more than one group, it's added only to the highest ranked group.</span></span> <span data-ttu-id="674a4-144">Sie können auch Gruppen bearbeiten und löschen.</span><span class="sxs-lookup"><span data-stu-id="674a4-144">You can also edit and delete groups.</span></span>



>[!WARNING]
><span data-ttu-id="674a4-145">Das Löschen einer Gerätegruppe kann sich auf E-Mail-Benachrichtigungsregeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="674a4-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="674a4-146">Wenn eine Gerätegruppe unter einer E-Mail-Benachrichtigungsregel konfiguriert ist, wird sie aus dieser Regel entfernt.</span><span class="sxs-lookup"><span data-stu-id="674a4-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="674a4-147">Wenn die Gerätegruppe die einzige Gruppe ist, die für eine E-Mail-Benachrichtigung konfiguriert ist, wird diese E-Mail-Benachrichtigungsregel zusammen mit der Gerätegruppe gelöscht.</span><span class="sxs-lookup"><span data-stu-id="674a4-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="674a4-148">Standardmäßig sind Gerätegruppen für alle Benutzer mit Portalzugriff zugänglich.</span><span class="sxs-lookup"><span data-stu-id="674a4-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="674a4-149">Sie können das Standardverhalten ändern, indem Sie der Gerätegruppe Azure AD-Benutzergruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="674a4-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="674a4-150">Geräte, die keiner Gruppe zugeordnet sind, werden der Gruppe "Nicht gruppierte Geräte" (Standardgruppe) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="674a4-150">Devices that aren't matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="674a4-151">Sie können den Rang dieser Gruppe nicht ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="674a4-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="674a4-152">Sie können jedoch die Korrekturstufe dieser Gruppe ändern und die Azure AD-Benutzergruppen definieren, die auf diese Gruppe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="674a4-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="674a4-153">Das Anwenden von Änderungen an der Gerätegruppenkonfiguration kann bis zu mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="674a4-153">Applying changes to device group configuration may take up to several minutes.</span></span>


### <a name="add-device-group-definitions"></a><span data-ttu-id="674a4-154">Hinzufügen von Gerätegruppendefinitionen</span><span class="sxs-lookup"><span data-stu-id="674a4-154">Add device group definitions</span></span>
<span data-ttu-id="674a4-155">Gerätegruppendefinitionen können auch mehrere Werte für jede Bedingung enthalten.</span><span class="sxs-lookup"><span data-stu-id="674a4-155">Device group definitions can also include multiple values for each condition.</span></span> <span data-ttu-id="674a4-156">Sie können mehrere Tags, Gerätenamen und Domänen auf die Definition einer einzelnen Gerätegruppe festlegen.</span><span class="sxs-lookup"><span data-stu-id="674a4-156">You can set multiple tags, device names, and domains to the definition of a single device group.</span></span>

1. <span data-ttu-id="674a4-157">Erstellen Sie eine neue Gerätegruppe, und wählen Sie dann die Registerkarte **"Geräte"** aus.</span><span class="sxs-lookup"><span data-stu-id="674a4-157">Create a new device group, then select **Devices** tab.</span></span>
2. <span data-ttu-id="674a4-158">Fügen Sie den ersten Wert für eine der Bedingungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="674a4-158">Add the first value for one of the conditions.</span></span>
3. <span data-ttu-id="674a4-159">Wählen Sie `+` diese Option aus, um weitere Zeilen desselben Eigenschaftstyps hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="674a4-159">Select `+` to add more rows of the same property type.</span></span>

>[!TIP]
> <span data-ttu-id="674a4-160">Verwenden Sie den Operator "OR" zwischen Zeilen desselben Bedingungstyps, der mehrere Werte pro Eigenschaft zulässt.</span><span class="sxs-lookup"><span data-stu-id="674a4-160">Use the 'OR' operator between rows of the same condition type, which allows multiple values per property.</span></span>
> <span data-ttu-id="674a4-161">Sie können bis zu 10 Zeilen (Werte) für jeden Eigenschaftstyp hinzufügen – Tag, Gerätename, Domäne.</span><span class="sxs-lookup"><span data-stu-id="674a4-161">You can add up to 10 rows (values) for each property type - tag, device name, domain.</span></span>

<span data-ttu-id="674a4-162">Weitere Informationen zum Verknüpfen mit Gerätegruppendefinitionen finden Sie unter ["Gerätegruppen – Microsoft 365 Sicherheit".](https://sip.security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="674a4-162">For more information on linking to device groups definitions, see [Device groups - Microsoft 365 security](https://sip.security.microsoft.com/homepage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="674a4-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="674a4-163">Related topics</span></span>

- [<span data-ttu-id="674a4-164">Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="674a4-164">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="674a4-165">Erstellen und Verwalten von Gerätekategorien</span><span class="sxs-lookup"><span data-stu-id="674a4-165">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="674a4-166">Abrufen einer Liste von Mandantengerätegruppen mithilfe Graph API</span><span class="sxs-lookup"><span data-stu-id="674a4-166">Get list of tenant device groups using Graph API</span></span>](/graph/api/device-list-memberof)
