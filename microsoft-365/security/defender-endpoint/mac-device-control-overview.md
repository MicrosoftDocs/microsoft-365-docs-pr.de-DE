---
title: Gerätesteuerung für macOS
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt auf dem Mac konfigurieren, um Bedrohungen durch Wechselmedien wie USB-Geräte zu reduzieren.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Gerät, Steuerelement, USB, Wechseldatenträger, Medien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 682f59729e06c63818491ad7540528d574380c8b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877836"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="691a7-104">Gerätesteuerung für macOS</span><span class="sxs-lookup"><span data-stu-id="691a7-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="691a7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="691a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="691a7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="691a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="691a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="691a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="691a7-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="691a7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="691a7-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="691a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="691a7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="691a7-110">Requirements</span></span>

<span data-ttu-id="691a7-111">Für die Gerätesteuerung für macOS sind die folgenden Voraussetzungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="691a7-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="691a7-112">Microsoft Defender für Endpunkt-Berechtigung (kann Testversion sein)</span><span class="sxs-lookup"><span data-stu-id="691a7-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="691a7-113">Mindestversion des Betriebssystems: macOS 10.15.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="691a7-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="691a7-114">Mindestversion des Produkts: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="691a7-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="691a7-115">Ihr Gerät muss mit Systemerweiterungen ausgeführt werden (dies ist die Standardeinstellung unter macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="691a7-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="691a7-116">Sie können überprüfen, ob Ihr Gerät auf Systemerweiterungen ausgeführt wird, indem Sie den folgenden Befehl ausführen und überprüfen, ob es in der Konsole gedruckt `endpoint_security_extension` wird:</span><span class="sxs-lookup"><span data-stu-id="691a7-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="691a7-117">Ihr Gerät muss sich im `Beta` Microsoft AutoUpdate-Updatekanal (zuvor als `InsiderFast` "Microsoft AutoUpdate" bezeichnet) befindet.</span><span class="sxs-lookup"><span data-stu-id="691a7-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="691a7-118">Weitere Informationen finden Sie unter [Bereitstellen von Updates für Microsoft Defender für Endpunkt auf dem Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="691a7-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="691a7-119">Sie können den Updatekanal mit dem folgenden Befehl überprüfen:</span><span class="sxs-lookup"><span data-stu-id="691a7-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="691a7-120">Wenn der oben genannte Befehl weder gedruckt noch `Beta` , führen Sie den folgenden Befehl aus dem Terminal `InsiderFast` aus.</span><span class="sxs-lookup"><span data-stu-id="691a7-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="691a7-121">Das Kanalupdate wird beim nächsten Start des Produkts wirksam (wenn das nächste Produktupdate installiert oder das Gerät neu gestartet wird).</span><span class="sxs-lookup"><span data-stu-id="691a7-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="691a7-122">Wenn Sie sich in einer verwalteten Umgebung (JAMF oder Intune) befinden, können Sie den Updatekanal alternativ remote konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="691a7-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="691a7-123">Weitere Informationen finden Sie unter [Bereitstellen von Updates für Microsoft Defender für Endpunkt auf dem Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="691a7-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="691a7-124">Gerätesteuerungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="691a7-124">Device control policy</span></span>

<span data-ttu-id="691a7-125">Um die Gerätesteuerung für macOS zu konfigurieren, müssen Sie eine Richtlinie erstellen, die die Einschränkungen beschreibt, die Innerhalb Ihrer Organisation eingerichtet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="691a7-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="691a7-126">Die Gerätesteuerungsrichtlinie ist im Konfigurationsprofil enthalten, das zum Konfigurieren aller anderen Produkteinstellungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="691a7-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="691a7-127">Weitere Informationen finden Sie unter [Konfigurationsprofilstruktur.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="691a7-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="691a7-128">Innerhalb des Konfigurationsprofils wird die Gerätesteuerungsrichtlinie im folgenden Abschnitt definiert:</span><span class="sxs-lookup"><span data-stu-id="691a7-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="691a7-129">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-129">Section</span></span>|<span data-ttu-id="691a7-130">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-130">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-131">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-132">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-132">**Key**</span></span> | <span data-ttu-id="691a7-133">deviceControl</span><span class="sxs-lookup"><span data-stu-id="691a7-133">deviceControl</span></span> |
| <span data-ttu-id="691a7-134">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-134">**Data type**</span></span> | <span data-ttu-id="691a7-135">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="691a7-135">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="691a7-136">**Comments**</span><span class="sxs-lookup"><span data-stu-id="691a7-136">**Comments**</span></span> | <span data-ttu-id="691a7-137">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="691a7-137">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="691a7-138">Die Gerätesteuerungsrichtlinie kann für Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="691a7-138">The device control policy can be used to:</span></span>

- [<span data-ttu-id="691a7-139">Anpassen des URL-Ziels für Benachrichtigungen, die vom Gerätesteuerelement ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="691a7-139">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="691a7-140">Zulassen oder Blockieren von Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="691a7-140">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="691a7-141">Anpassen des URL-Ziels für Benachrichtigungen, die vom Gerätesteuerelement ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="691a7-141">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="691a7-142">Wenn die von Ihnen eingerichtete Gerätesteuerungsrichtlinie auf einem Gerät erzwungen wird (z. B. ist der Zugriff auf ein Wechselmediengerät eingeschränkt), wird dem Benutzer eine Benachrichtigung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="691a7-142">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Gerätesteuerungsbenachrichtigung](images/mac-device-control-notification.png)

<span data-ttu-id="691a7-144">Wenn Endbenutzer auf diese Benachrichtigung klicken, wird eine Webseite im Standardbrowser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="691a7-144">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="691a7-145">Sie können die URL konfigurieren, die geöffnet wird, wenn Endbenutzer auf die Benachrichtigung klicken.</span><span class="sxs-lookup"><span data-stu-id="691a7-145">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="691a7-146">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-146">Section</span></span>|<span data-ttu-id="691a7-147">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-147">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-148">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-148">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-149">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-149">**Key**</span></span> | <span data-ttu-id="691a7-150">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="691a7-150">navigationTarget</span></span> |
| <span data-ttu-id="691a7-151">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-151">**Data type**</span></span> | <span data-ttu-id="691a7-152">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="691a7-152">String</span></span> |
| <span data-ttu-id="691a7-153">**Comments**</span><span class="sxs-lookup"><span data-stu-id="691a7-153">**Comments**</span></span> | <span data-ttu-id="691a7-154">Wenn nicht definiert, verwendet das Produkt eine Standard-URL, die auf eine generische Seite verweist, auf der die vom Produkt ausgeführte Aktion erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="691a7-154">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="691a7-155">Zulassen oder Blockieren von Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="691a7-155">Allow or block removable devices</span></span>

<span data-ttu-id="691a7-156">Der Abschnitt "Wechselmedien" der Gerätesteuerungsrichtlinie wird verwendet, um den Zugriff auf Wechselmedien einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="691a7-156">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="691a7-157">Die folgenden Arten von Wechselmedien werden derzeit unterstützt und können in die Richtlinie einbezogen werden: USB-Speichergeräte.</span><span class="sxs-lookup"><span data-stu-id="691a7-157">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="691a7-158">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-158">Section</span></span>|<span data-ttu-id="691a7-159">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-159">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-160">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-160">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-161">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-161">**Key**</span></span> | <span data-ttu-id="691a7-162">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="691a7-162">removableMediaPolicy</span></span> |
| <span data-ttu-id="691a7-163">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-163">**Data type**</span></span> | <span data-ttu-id="691a7-164">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="691a7-164">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="691a7-165">**Comments**</span><span class="sxs-lookup"><span data-stu-id="691a7-165">**Comments**</span></span> | <span data-ttu-id="691a7-166">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="691a7-166">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="691a7-167">Dieser Abschnitt der Richtlinie ist hierarchisch aufgebaut und ermöglicht maximale Flexibilität und deckt eine Vielzahl von Anwendungsfällen ab.</span><span class="sxs-lookup"><span data-stu-id="691a7-167">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="691a7-168">Auf der obersten Ebene befinden sich Anbieter, die durch eine Anbieter-ID identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="691a7-168">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="691a7-169">Für jeden Anbieter gibt es Produkte, die durch eine Produkt-ID identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="691a7-169">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="691a7-170">Schließlich gibt es für jedes Produkt Seriennummern, die bestimmte Geräte kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="691a7-170">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="691a7-171">Informationen dazu, wie Sie die Geräte-IDs finden, finden Sie unter Nachschlagen von [Geräte-IDs.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="691a7-171">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="691a7-172">Die Richtlinie wird vom spezifischsten Eintrag zum allgemeinen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="691a7-172">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="691a7-173">Wenn ein Gerät angeschlossen ist, versucht das Produkt also, die spezifischste Übereinstimmung in der Richtlinie für jedes Wechselmediengerät zu finden und die Berechtigungen auf dieser Ebene anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="691a7-173">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="691a7-174">Wenn keine Übereinstimmung vorhanden ist, wird die nächste beste Übereinstimmung angewendet, bis hin zu der auf der obersten Ebene angegebenen Berechtigung. Dies ist die Standardeinstellung, wenn ein Gerät keinem anderen Eintrag in der Richtlinie entspricht.</span><span class="sxs-lookup"><span data-stu-id="691a7-174">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="691a7-175">Richtlinienerzwingungsstufe</span><span class="sxs-lookup"><span data-stu-id="691a7-175">Policy enforcement level</span></span>

<span data-ttu-id="691a7-176">Im Abschnitt "Wechselmedien" gibt es eine Option zum Festlegen der Erzwingungsstufe, die einen der folgenden Werte annehmen kann:</span><span class="sxs-lookup"><span data-stu-id="691a7-176">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="691a7-177">`audit` – Wenn der Zugriff auf ein Gerät unter dieser Erzwingungsstufe eingeschränkt ist, wird dem Benutzer eine Benachrichtigung angezeigt, das Gerät kann jedoch weiterhin verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="691a7-177">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="691a7-178">Diese Erzwingungsstufe kann nützlich sein, um die Effektivität einer Richtlinie zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="691a7-178">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="691a7-179">`block` – Unter dieser Erzwingungsstufe sind die Vorgänge, die der Benutzer auf dem Gerät ausführen kann, auf die in der Richtlinie definierten Vorgänge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="691a7-179">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="691a7-180">Darüber hinaus wird eine Benachrichtigung für den Benutzer ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="691a7-180">Furthermore, a notification is raised to the user.</span></span> 

|<span data-ttu-id="691a7-181">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-181">Section</span></span>|<span data-ttu-id="691a7-182">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-182">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-183">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-184">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-184">**Key**</span></span> | <span data-ttu-id="691a7-185">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="691a7-185">enforcementLevel</span></span> |
| <span data-ttu-id="691a7-186">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-186">**Data type**</span></span> | <span data-ttu-id="691a7-187">String</span><span class="sxs-lookup"><span data-stu-id="691a7-187">String</span></span> |
| <span data-ttu-id="691a7-188">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="691a7-188">**Possible values**</span></span> | <span data-ttu-id="691a7-189">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="691a7-189">audit (default)</span></span> <br/> <span data-ttu-id="691a7-190">Block</span><span class="sxs-lookup"><span data-stu-id="691a7-190">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="691a7-191">Standardberechtigungsstufe</span><span class="sxs-lookup"><span data-stu-id="691a7-191">Default permission level</span></span>

<span data-ttu-id="691a7-192">Auf der obersten Ebene des Abschnitts "Wechselmedien" können Sie die Standardberechtigungsstufe für Geräte konfigurieren, die keiner anderen In der Richtlinie entsprechen.</span><span class="sxs-lookup"><span data-stu-id="691a7-192">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="691a7-193">Diese Einstellung kann wie folgt festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="691a7-193">This setting can be set to:</span></span>

- <span data-ttu-id="691a7-194">`none` – Es können keine Vorgänge auf dem Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="691a7-194">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="691a7-195">Eine Kombination der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="691a7-195">A combination of the following values:</span></span>
    - <span data-ttu-id="691a7-196">`read` – Lesevorgänge sind auf dem Gerät zulässig</span><span class="sxs-lookup"><span data-stu-id="691a7-196">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="691a7-197">`write` – Schreibvorgänge sind auf dem Gerät zulässig</span><span class="sxs-lookup"><span data-stu-id="691a7-197">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="691a7-198">`execute` - Ausführen von Vorgängen auf dem Gerät zulässig</span><span class="sxs-lookup"><span data-stu-id="691a7-198">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="691a7-199">Wenn `none` die Berechtigungsstufe vorhanden ist, werden alle anderen Berechtigungen ( `read` oder ) `write` `execute` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="691a7-199">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="691a7-200">Die `execute` Berechtigung bezieht sich nur auf die Ausführung von binären Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="691a7-200">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="691a7-201">Es umfasst nicht die Ausführung von Skripts oder anderen Arten von Nutzlasten.</span><span class="sxs-lookup"><span data-stu-id="691a7-201">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="691a7-202">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-202">Section</span></span>|<span data-ttu-id="691a7-203">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-203">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-204">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-204">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-205">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-205">**Key**</span></span> | <span data-ttu-id="691a7-206">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="691a7-206">permission</span></span> |
| <span data-ttu-id="691a7-207">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-207">**Data type**</span></span> | <span data-ttu-id="691a7-208">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="691a7-208">Array of strings</span></span> |
| <span data-ttu-id="691a7-209">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="691a7-209">**Possible values**</span></span> | <span data-ttu-id="691a7-210">keine</span><span class="sxs-lookup"><span data-stu-id="691a7-210">none</span></span> <br/> <span data-ttu-id="691a7-211">Lesen</span><span class="sxs-lookup"><span data-stu-id="691a7-211">read</span></span> <br/> <span data-ttu-id="691a7-212">Schreiben</span><span class="sxs-lookup"><span data-stu-id="691a7-212">write</span></span> <br/> <span data-ttu-id="691a7-213">Ausführen</span><span class="sxs-lookup"><span data-stu-id="691a7-213">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="691a7-214">Einschränken von Wechselmedien nach Hersteller, Produkt und Seriennummer</span><span class="sxs-lookup"><span data-stu-id="691a7-214">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="691a7-215">Wie unter ["Zulassen oder Blockieren von Wechselmedien"](#allow-or-block-removable-devices)beschrieben, können Wechselmedien wie USB-Geräte anhand der Hersteller-ID, der Produkt-ID und der Seriennummer identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="691a7-215">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="691a7-216">Auf der obersten Ebene der Richtlinie für Wechselmedien können Sie optional detailliertere Einschränkungen auf Herstellerebene definieren.</span><span class="sxs-lookup"><span data-stu-id="691a7-216">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="691a7-217">Das `vendors` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Anbieter-ID identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="691a7-217">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="691a7-218">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-218">Section</span></span>|<span data-ttu-id="691a7-219">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-220">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-221">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-221">**Key**</span></span> | <span data-ttu-id="691a7-222">Anbieter</span><span class="sxs-lookup"><span data-stu-id="691a7-222">vendors</span></span> |
| <span data-ttu-id="691a7-223">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-223">**Data type**</span></span> | <span data-ttu-id="691a7-224">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="691a7-224">Dictionary (nested preference)</span></span> |

<span data-ttu-id="691a7-225">Für jeden Anbieter können Sie die gewünschte Berechtigungsstufe für Geräte von diesem Anbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="691a7-225">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="691a7-226">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-226">Section</span></span>|<span data-ttu-id="691a7-227">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-227">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-228">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-228">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-229">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-229">**Key**</span></span> | <span data-ttu-id="691a7-230">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="691a7-230">permission</span></span> |
| <span data-ttu-id="691a7-231">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-231">**Data type**</span></span> | <span data-ttu-id="691a7-232">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="691a7-232">Array of strings</span></span> |
| <span data-ttu-id="691a7-233">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="691a7-233">**Possible values**</span></span> | <span data-ttu-id="691a7-234">Identisch mit [der Standardberechtigungsstufe](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="691a7-234">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="691a7-235">Darüber hinaus können Sie optional den Satz von Produkten angeben, die zu diesem Anbieter gehören, für den detailliertere Berechtigungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="691a7-235">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="691a7-236">Das `products` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Produkt-ID identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="691a7-236">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="691a7-237">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-237">Section</span></span>|<span data-ttu-id="691a7-238">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-239">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-240">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-240">**Key**</span></span> | <span data-ttu-id="691a7-241">Produkte</span><span class="sxs-lookup"><span data-stu-id="691a7-241">products</span></span> |
| <span data-ttu-id="691a7-242">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-242">**Data type**</span></span> | <span data-ttu-id="691a7-243">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="691a7-243">Dictionary (nested preference)</span></span> |

<span data-ttu-id="691a7-244">Für jedes Produkt können Sie die gewünschte Berechtigungsstufe für dieses Produkt angeben.</span><span class="sxs-lookup"><span data-stu-id="691a7-244">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="691a7-245">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-245">Section</span></span>|<span data-ttu-id="691a7-246">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-246">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-247">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-247">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-248">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-248">**Key**</span></span> | <span data-ttu-id="691a7-249">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="691a7-249">permission</span></span> |
| <span data-ttu-id="691a7-250">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-250">**Data type**</span></span> | <span data-ttu-id="691a7-251">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="691a7-251">Array of strings</span></span> |
| <span data-ttu-id="691a7-252">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="691a7-252">**Possible values**</span></span> | <span data-ttu-id="691a7-253">Identisch mit [der Standardberechtigungsstufe](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="691a7-253">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="691a7-254">Darüber hinaus können Sie einen optionalen Satz von Seriennummern angeben, für die detailliertere Berechtigungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="691a7-254">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="691a7-255">Das `serialNumbers` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Seriennummer identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="691a7-255">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="691a7-256">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-256">Section</span></span>|<span data-ttu-id="691a7-257">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-258">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-259">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-259">**Key**</span></span> | <span data-ttu-id="691a7-260">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="691a7-260">serialNumbers</span></span> |
| <span data-ttu-id="691a7-261">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-261">**Data type**</span></span> | <span data-ttu-id="691a7-262">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="691a7-262">Dictionary (nested preference)</span></span> |

<span data-ttu-id="691a7-263">Für jede Seriennummer können Sie die gewünschte Berechtigungsstufe angeben.</span><span class="sxs-lookup"><span data-stu-id="691a7-263">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="691a7-264">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="691a7-264">Section</span></span>|<span data-ttu-id="691a7-265">Wert</span><span class="sxs-lookup"><span data-stu-id="691a7-265">Value</span></span>|
|:---|:---|
| <span data-ttu-id="691a7-266">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="691a7-266">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="691a7-267">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="691a7-267">**Key**</span></span> | <span data-ttu-id="691a7-268">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="691a7-268">permission</span></span> |
| <span data-ttu-id="691a7-269">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="691a7-269">**Data type**</span></span> | <span data-ttu-id="691a7-270">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="691a7-270">Array of strings</span></span> |
| <span data-ttu-id="691a7-271">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="691a7-271">**Possible values**</span></span> | <span data-ttu-id="691a7-272">Identisch mit [der Standardberechtigungsstufe](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="691a7-272">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="691a7-273">Beispiel für eine Gerätesteuerungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="691a7-273">Example device control policy</span></span>

<span data-ttu-id="691a7-274">Das folgende Beispiel zeigt, wie alle oben genannten Konzepte in einer Gerätesteuerungsrichtlinie kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="691a7-274">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="691a7-275">Beachten Sie im folgenden Beispiel die hierarchische Natur der Richtlinie für Wechselmedien.</span><span class="sxs-lookup"><span data-stu-id="691a7-275">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="691a7-276">Wir haben weitere Beispiele für Gerätesteuerungsrichtlinien in die folgenden Dokumente aufgenommen:</span><span class="sxs-lookup"><span data-stu-id="691a7-276">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="691a7-277">Beispiele für Gerätesteuerungsrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="691a7-277">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="691a7-278">Beispiele für Gerätesteuerungsrichtlinien für JAMF</span><span class="sxs-lookup"><span data-stu-id="691a7-278">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="691a7-279">Nachschlagen von Gerätebezeichnern</span><span class="sxs-lookup"><span data-stu-id="691a7-279">Look up device identifiers</span></span>

<span data-ttu-id="691a7-280">So suchen Sie die Anbieter-ID, Produkt-ID und Seriennummer eines USB-Geräts:</span><span class="sxs-lookup"><span data-stu-id="691a7-280">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="691a7-281">Melden Sie sich bei einem Mac-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="691a7-281">Log into a Mac device.</span></span>
1. <span data-ttu-id="691a7-282">Schließen Sie das USB-Gerät an, für das Sie die Bezeichner nachschlagen möchten.</span><span class="sxs-lookup"><span data-stu-id="691a7-282">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="691a7-283">Wählen Sie im Menü der obersten Ebene von macOS **"Info zu diesem Mac"** aus.</span><span class="sxs-lookup"><span data-stu-id="691a7-283">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Informationen zu diesem Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="691a7-285">Wählen Sie **"Systembericht" aus.**</span><span class="sxs-lookup"><span data-stu-id="691a7-285">Select **System Report**.</span></span>

    ![Systembericht](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="691a7-287">Wählen Sie in der linken Spalte **USB** aus.</span><span class="sxs-lookup"><span data-stu-id="691a7-287">From the left column, select **USB**.</span></span>

    ![Ansicht aller USB-Geräte](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="691a7-289">Navigieren Sie unter **der USB-Gerätestruktur** zu dem USB-Gerät, das Sie angeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="691a7-289">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Details zu einem USB-Gerät](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="691a7-291">Die Anbieter-ID, Produkt-ID und Seriennummer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="691a7-291">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="691a7-292">Wenn Sie die Anbieter-ID und die Produkt-ID zur Richtlinie für Wechselmedien hinzufügen, müssen Sie den Teil erst nach `0x` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="691a7-292">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="691a7-293">In der folgenden Abbildung ist z. B. die Anbieter-ID `1000` und die Produkt-ID `090c` .</span><span class="sxs-lookup"><span data-stu-id="691a7-293">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="691a7-294">Ermitteln von USB-Geräten in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="691a7-294">Discover USB devices in your organization</span></span>

<span data-ttu-id="691a7-295">Sie können Mount-, Unmount- und Volumeänderungsereignisse von USB-Geräten in der erweiterten Suche in Microsoft Defender für Endpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="691a7-295">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="691a7-296">Diese Ereignisse können hilfreich sein, um verdächtige Nutzungsaktivitäten zu identifizieren oder interne Untersuchungen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="691a7-296">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="691a7-297">Bereitstellung von Gerätesteuerungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="691a7-297">Device control policy deployment</span></span>

<span data-ttu-id="691a7-298">Die Gerätesteuerungsrichtlinie muss neben den anderen Produkteinstellungen enthalten sein, wie unter Festlegen der [Einstellungen für Microsoft Defender für Endpunkt unter macOS](mac-preferences.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="691a7-298">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="691a7-299">Dieses Profil kann mithilfe der Anweisungen bereitgestellt werden, die in der Bereitstellung des [Konfigurationsprofils](mac-preferences.md#configuration-profile-deployment)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="691a7-299">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="691a7-300">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="691a7-300">Troubleshooting tips</span></span>

<span data-ttu-id="691a7-301">Nachdem Sie das Konfigurationsprofil über Intune oder JAMF übertragen haben, können Sie überprüfen, ob es vom Produkt erfolgreich aufgenommen wurde, indem Sie den folgenden Befehl aus dem Terminal ausführen:</span><span class="sxs-lookup"><span data-stu-id="691a7-301">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="691a7-302">Dieser Befehl druckt in der Standardausgabe der Gerätesteuerungsrichtlinie, die das Produkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="691a7-302">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="691a7-303">Falls dies gedruckt `Policy is empty` wird, stellen Sie sicher, dass (a) das Konfigurationsprofil tatsächlich von der Verwaltungskonsole an Ihr Gerät übertragen wurde und (b) es sich um eine gültige Gerätesteuerungsrichtlinie handelt, wie in diesem Dokument beschrieben.</span><span class="sxs-lookup"><span data-stu-id="691a7-303">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="691a7-304">Auf einem Gerät, auf dem die Richtlinie erfolgreich bereitgestellt wurde und ein oder mehrere Geräte angeschlossen sind, können Sie den folgenden Befehl ausführen, um alle Geräte und die effektiven Berechtigungen aufzuführen, die ihnen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="691a7-304">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="691a7-305">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="691a7-305">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="691a7-306">Im obigen Beispiel ist nur ein Wechselmediengerät angeschlossen, und es verfügt `read` über berechtigungen gemäß der `execute` Gerätesteuerungsrichtlinie, die an das Gerät übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="691a7-306">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="691a7-307">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="691a7-307">Related topics</span></span>

- [<span data-ttu-id="691a7-308">Beispiele für Gerätesteuerungsrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="691a7-308">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="691a7-309">Beispiele für Gerätesteuerungsrichtlinien für JAMF</span><span class="sxs-lookup"><span data-stu-id="691a7-309">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
