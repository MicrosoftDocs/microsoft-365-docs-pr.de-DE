---
title: Erstellen und Verwalten von Gerätetags
description: Verwenden von Gerätetags zum Gruppieren von Geräten zum Erfassen des Kontexts und Aktivieren der erstellung dynamischer Listen im Rahmen eines Vorfalls
keywords: Tags, Gerätetags, Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln,Ad-Gruppe, Rolle, Zuweisen, Rang
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
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187589"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="bad8f-104">Erstellen und Verwalten von Gerätetags</span><span class="sxs-lookup"><span data-stu-id="bad8f-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bad8f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bad8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="bad8f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bad8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bad8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bad8f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bad8f-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bad8f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bad8f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bad8f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bad8f-110">Fügen Sie Tags auf Geräten hinzu, um eine logische Gruppenmitgliedschaft zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="bad8f-111">Gerätetags unterstützen die ordnungsgemäße Zuordnung des Netzwerks, sodass Sie verschiedene Tags anfügen können, um Kontext zu erfassen und dynamische Listenerstellung als Teil eines Vorfalls zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="bad8f-112">Tags können als Filter **in** der Gerätelistenansicht oder zum Gruppieren von Geräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bad8f-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="bad8f-113">Weitere Informationen zur Gerätegruppe finden Sie unter [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="bad8f-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="bad8f-114">Sie können Tags auf Geräten mithilfe der folgenden Methoden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="bad8f-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="bad8f-115">Verwenden des Portals</span><span class="sxs-lookup"><span data-stu-id="bad8f-115">Using the portal</span></span>
- <span data-ttu-id="bad8f-116">Festlegen eines Registrierungsschlüsselwerts</span><span class="sxs-lookup"><span data-stu-id="bad8f-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="bad8f-117">Zwischen dem Hinzufügen eines Tags zu einem Gerät und seiner Verfügbarkeit in der Geräteliste und Geräteseite kann eine gewisse Latenz auftreten.</span><span class="sxs-lookup"><span data-stu-id="bad8f-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="bad8f-118">Informationen zum Hinzufügen von Gerätetags mithilfe der API finden Sie unter [Add or remove device tags API](add-or-remove-machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="bad8f-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="bad8f-119">Hinzufügen und Verwalten von Gerätetags mithilfe des Portals</span><span class="sxs-lookup"><span data-stu-id="bad8f-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="bad8f-120">Wählen Sie das Gerät aus, auf dem Sie Tags verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="bad8f-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="bad8f-121">Sie können ein Gerät aus einer der folgenden Ansichten auswählen oder suchen:</span><span class="sxs-lookup"><span data-stu-id="bad8f-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="bad8f-122">**Dashboard für Sicherheitsvorgänge:** Wählen Sie den Gerätenamen im Abschnitt Top devices with active alerts aus.</span><span class="sxs-lookup"><span data-stu-id="bad8f-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="bad8f-123">**Warnungswarteschlange** : Wählen Sie den Gerätenamen neben dem Gerätesymbol aus der Benachrichtigungswarteschlange aus.</span><span class="sxs-lookup"><span data-stu-id="bad8f-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="bad8f-124">**Geräteliste** – Wählen Sie den Gerätenamen aus der Liste der Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="bad8f-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="bad8f-125">**Suchfeld** : Wählen Sie im Dropdownmenü Gerät aus, und geben Sie den Gerätenamen ein.</span><span class="sxs-lookup"><span data-stu-id="bad8f-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="bad8f-126">Sie können auch über die Datei- und IP-Ansichten zur Warnungsseite gelangen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="bad8f-127">Wählen **Sie In der** Zeile Reaktionsaktionen die Option Tags verwalten aus.</span><span class="sxs-lookup"><span data-stu-id="bad8f-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Abbildung der Schaltfläche "Tags verwalten"](images/manage-tags.png)

3. <span data-ttu-id="bad8f-129">Geben Sie ein, um Tags zu suchen oder zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-129">Type to find or create tags</span></span>

    ![Abbildung des Hinzufügens von Tags auf einem Gerät1](images/new-tags.png)

<span data-ttu-id="bad8f-131">Tags werden der Geräteansicht hinzugefügt und werden  auch in der Gerätelistenansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad8f-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="bad8f-132">Anschließend können Sie den **Filter Tags verwenden,** um die relevante Liste der Geräte zu sehen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="bad8f-133">Die Filterung funktioniert möglicherweise nicht für Tagnamen, die Klammer enthalten.</span><span class="sxs-lookup"><span data-stu-id="bad8f-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="bad8f-134">Wenn Sie ein neues Tag erstellen, wird eine Liste vorhandener Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad8f-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="bad8f-135">In der Liste werden nur Tags angezeigt, die über das Portal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="bad8f-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="bad8f-136">Vorhandene Tags, die auf Clientgeräten erstellt wurden, werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bad8f-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="bad8f-137">Sie können auch Tags aus dieser Ansicht löschen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-137">You can also delete tags from this view.</span></span>

![Abbildung des Hinzufügens von Tags auf einem Gerät2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="bad8f-139">Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts</span><span class="sxs-lookup"><span data-stu-id="bad8f-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="bad8f-140">Gilt nur auf den folgenden Geräten:</span><span class="sxs-lookup"><span data-stu-id="bad8f-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="bad8f-141">Windows 10, Version 1709 oder höher</span><span class="sxs-lookup"><span data-stu-id="bad8f-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="bad8f-142">Windows Server, Version 1803 oder höher</span><span class="sxs-lookup"><span data-stu-id="bad8f-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="bad8f-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bad8f-143">Windows Server 2016</span></span>
>- <span data-ttu-id="bad8f-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bad8f-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="bad8f-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="bad8f-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="bad8f-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bad8f-146">Windows 8.1</span></span>
>- <span data-ttu-id="bad8f-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="bad8f-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="bad8f-148">Die maximale Anzahl von Zeichen, die in einem Tag festgelegt werden können, ist 200.</span><span class="sxs-lookup"><span data-stu-id="bad8f-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="bad8f-149">Geräte mit ähnlichen Tags können nützlich sein, wenn Sie kontextbezogene Aktionen auf eine bestimmte Liste von Geräten anwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="bad8f-150">Verwenden Sie den folgenden Registrierungsschlüsseleintrag, um ein Tag auf einem Gerät hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="bad8f-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="bad8f-151">Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="bad8f-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="bad8f-152">Registrierungsschlüsselwert (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="bad8f-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="bad8f-153">Registrierungsschlüsseldaten: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="bad8f-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="bad8f-154">Das Gerätetag ist Teil des Geräteinformationsberichts, der einmal am Tag generiert wird.</span><span class="sxs-lookup"><span data-stu-id="bad8f-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="bad8f-155">Alternativ können Sie den Endpunkt neu starten, der einen neuen Geräteinformationsbericht übertragen würde.</span><span class="sxs-lookup"><span data-stu-id="bad8f-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="bad8f-156">Wenn Sie ein Tag entfernen müssen, das mit dem obigen Registrierungsschlüssel hinzugefügt wurde, löschen Sie den Inhalt der Registrierungsschlüsseldaten, anstatt den Schlüssel "Gruppe" zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bad8f-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
