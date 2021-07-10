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
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363979"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="a2b48-104">Gerätesteuerung für macOS</span><span class="sxs-lookup"><span data-stu-id="a2b48-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2b48-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a2b48-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2b48-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a2b48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a2b48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2b48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a2b48-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="a2b48-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a2b48-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="a2b48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a><span data-ttu-id="a2b48-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2b48-110">Requirements</span></span>

<span data-ttu-id="a2b48-111">Für die Gerätesteuerung für macOS sind die folgenden Voraussetzungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a2b48-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="a2b48-112">Microsoft Defender für Endpunkt-Berechtigung (kann Testversion sein)</span><span class="sxs-lookup"><span data-stu-id="a2b48-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="a2b48-113">Mindestversion des Betriebssystems: macOS 11 oder höher</span><span class="sxs-lookup"><span data-stu-id="a2b48-113">Minimum OS version: macOS 11 or higher</span></span>
> - <span data-ttu-id="a2b48-114">Mindestversion des Produkts: 101.34.20</span><span class="sxs-lookup"><span data-stu-id="a2b48-114">Minimum product version: 101.34.20</span></span>

## <a name="device-control-policy"></a><span data-ttu-id="a2b48-115">Gerätesteuerungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b48-115">Device control policy</span></span>

<span data-ttu-id="a2b48-116">Um die Gerätesteuerung für macOS zu konfigurieren, müssen Sie eine Richtlinie erstellen, die die Einschränkungen beschreibt, die Innerhalb Ihrer Organisation eingerichtet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a2b48-116">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="a2b48-117">Die Gerätesteuerungsrichtlinie ist im Konfigurationsprofil enthalten, das zum Konfigurieren aller anderen Produkteinstellungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2b48-117">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="a2b48-118">Weitere Informationen finden Sie unter [Konfigurationsprofilstruktur.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="a2b48-118">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="a2b48-119">Innerhalb des Konfigurationsprofils wird die Gerätesteuerungsrichtlinie im folgenden Abschnitt definiert:</span><span class="sxs-lookup"><span data-stu-id="a2b48-119">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="a2b48-120">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-120">Section</span></span>|<span data-ttu-id="a2b48-121">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-121">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-122">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-123">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-123">**Key**</span></span> | <span data-ttu-id="a2b48-124">deviceControl</span><span class="sxs-lookup"><span data-stu-id="a2b48-124">deviceControl</span></span> |
| <span data-ttu-id="a2b48-125">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-125">**Data type**</span></span> | <span data-ttu-id="a2b48-126">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="a2b48-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a2b48-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a2b48-127">**Comments**</span></span> | <span data-ttu-id="a2b48-128">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="a2b48-128">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="a2b48-129">Die Gerätesteuerungsrichtlinie kann für Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a2b48-129">The device control policy can be used to:</span></span>

- [<span data-ttu-id="a2b48-130">Anpassen des URL-Ziels für Benachrichtigungen, die vom Gerätesteuerelement ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="a2b48-130">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="a2b48-131">Zulassen oder Blockieren von Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="a2b48-131">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="a2b48-132">Anpassen des URL-Ziels für Benachrichtigungen, die vom Gerätesteuerelement ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="a2b48-132">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="a2b48-133">Wenn die von Ihnen eingerichtete Gerätesteuerungsrichtlinie auf einem Gerät erzwungen wird (z. B. ist der Zugriff auf ein Wechselmediengerät eingeschränkt), wird dem Benutzer eine Benachrichtigung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2b48-133">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Gerätesteuerungsbenachrichtigung](images/mac-device-control-notification.png)

<span data-ttu-id="a2b48-135">Wenn Endbenutzer auf diese Benachrichtigung klicken, wird eine Webseite im Standardbrowser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a2b48-135">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="a2b48-136">Sie können die URL konfigurieren, die geöffnet wird, wenn Endbenutzer auf die Benachrichtigung klicken.</span><span class="sxs-lookup"><span data-stu-id="a2b48-136">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="a2b48-137">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-137">Section</span></span>|<span data-ttu-id="a2b48-138">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-138">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-139">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-139">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-140">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-140">**Key**</span></span> | <span data-ttu-id="a2b48-141">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="a2b48-141">navigationTarget</span></span> |
| <span data-ttu-id="a2b48-142">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-142">**Data type**</span></span> | <span data-ttu-id="a2b48-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2b48-143">String</span></span> |
| <span data-ttu-id="a2b48-144">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a2b48-144">**Comments**</span></span> | <span data-ttu-id="a2b48-145">Wenn nicht definiert, verwendet das Produkt eine Standard-URL, die auf eine generische Seite verweist, auf der die vom Produkt ausgeführte Aktion erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="a2b48-145">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="a2b48-146">Zulassen oder Blockieren von Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="a2b48-146">Allow or block removable devices</span></span>

<span data-ttu-id="a2b48-147">Der Abschnitt "Wechselmedien" der Gerätesteuerungsrichtlinie wird verwendet, um den Zugriff auf Wechselmedien einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="a2b48-147">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="a2b48-148">Die folgenden Arten von Wechselmedien werden derzeit unterstützt und können in die Richtlinie einbezogen werden: USB-Speichergeräte.</span><span class="sxs-lookup"><span data-stu-id="a2b48-148">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="a2b48-149">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-149">Section</span></span>|<span data-ttu-id="a2b48-150">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-150">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-151">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-151">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-152">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-152">**Key**</span></span> | <span data-ttu-id="a2b48-153">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="a2b48-153">removableMediaPolicy</span></span> |
| <span data-ttu-id="a2b48-154">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-154">**Data type**</span></span> | <span data-ttu-id="a2b48-155">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="a2b48-155">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a2b48-156">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a2b48-156">**Comments**</span></span> | <span data-ttu-id="a2b48-157">Eine Beschreibung des Wörterbuchinhalts finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="a2b48-157">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="a2b48-158">Dieser Abschnitt der Richtlinie ist hierarchisch aufgebaut und ermöglicht maximale Flexibilität und deckt eine Vielzahl von Anwendungsfällen ab.</span><span class="sxs-lookup"><span data-stu-id="a2b48-158">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="a2b48-159">Auf der obersten Ebene befinden sich Anbieter, die durch eine Anbieter-ID identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-159">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="a2b48-160">Für jeden Anbieter gibt es Produkte, die durch eine Produkt-ID identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-160">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="a2b48-161">Schließlich gibt es für jedes Produkt Seriennummern, die bestimmte Geräte kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="a2b48-161">Finally, for each product there are serial numbers denoting specific devices.</span></span>

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

<span data-ttu-id="a2b48-162">Informationen dazu, wie Sie die Geräte-IDs finden, finden Sie unter Nachschlagen von [Geräte-IDs.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="a2b48-162">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="a2b48-163">Die Richtlinie wird vom spezifischsten Eintrag zum allgemeinen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a2b48-163">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="a2b48-164">Wenn ein Gerät angeschlossen ist, versucht das Produkt also, die spezifischste Übereinstimmung in der Richtlinie für jedes Wechselmediengerät zu finden und die Berechtigungen auf dieser Ebene anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-164">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="a2b48-165">Wenn keine Übereinstimmung vorhanden ist, wird die nächste beste Übereinstimmung angewendet, bis hin zu der auf der obersten Ebene angegebenen Berechtigung. Dies ist die Standardeinstellung, wenn ein Gerät keinem anderen Eintrag in der Richtlinie entspricht.</span><span class="sxs-lookup"><span data-stu-id="a2b48-165">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="a2b48-166">Richtlinienerzwingungsstufe</span><span class="sxs-lookup"><span data-stu-id="a2b48-166">Policy enforcement level</span></span>

<span data-ttu-id="a2b48-167">Im Abschnitt "Wechselmedien" gibt es eine Option zum Festlegen der Erzwingungsstufe, die einen der folgenden Werte annehmen kann:</span><span class="sxs-lookup"><span data-stu-id="a2b48-167">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="a2b48-168">`audit` – Wenn der Zugriff auf ein Gerät unter dieser Erzwingungsstufe eingeschränkt ist, wird dem Benutzer eine Benachrichtigung angezeigt, das Gerät kann jedoch weiterhin verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-168">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="a2b48-169">Diese Erzwingungsstufe kann nützlich sein, um die Effektivität einer Richtlinie zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="a2b48-169">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="a2b48-170">`block` – Unter dieser Erzwingungsstufe sind die Vorgänge, die der Benutzer auf dem Gerät ausführen kann, auf die in der Richtlinie definierten Vorgänge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a2b48-170">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="a2b48-171">Darüber hinaus wird eine Benachrichtigung für den Benutzer ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a2b48-171">Furthermore, a notification is raised to the user.</span></span> 

> [!NOTE] 
> <span data-ttu-id="a2b48-172">Standardmäßig ist die Erzwingungsstufe `audit` auf .</span><span class="sxs-lookup"><span data-stu-id="a2b48-172">By default, the enforcement level is set to `audit`.</span></span> 

|<span data-ttu-id="a2b48-173">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-173">Section</span></span>|<span data-ttu-id="a2b48-174">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-174">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-175">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-176">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-176">**Key**</span></span> | <span data-ttu-id="a2b48-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="a2b48-177">enforcementLevel</span></span> |
| <span data-ttu-id="a2b48-178">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-178">**Data type**</span></span> | <span data-ttu-id="a2b48-179">String</span><span class="sxs-lookup"><span data-stu-id="a2b48-179">String</span></span> |
| <span data-ttu-id="a2b48-180">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="a2b48-180">**Possible values**</span></span> | <span data-ttu-id="a2b48-181">Überwachung (Standard)</span><span class="sxs-lookup"><span data-stu-id="a2b48-181">audit (default)</span></span> <br/> <span data-ttu-id="a2b48-182">Block</span><span class="sxs-lookup"><span data-stu-id="a2b48-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="a2b48-183">Standardberechtigungsstufe</span><span class="sxs-lookup"><span data-stu-id="a2b48-183">Default permission level</span></span>

<span data-ttu-id="a2b48-184">Auf der obersten Ebene des Abschnitts "Wechselmedien" können Sie die Standardberechtigungsstufe für Geräte konfigurieren, die keiner anderen In der Richtlinie entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a2b48-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="a2b48-185">Diese Einstellung kann wie folgt festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="a2b48-185">This setting can be set to:</span></span>

- <span data-ttu-id="a2b48-186">`none` – Es können keine Vorgänge auf dem Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="a2b48-187">Eine Kombination der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="a2b48-187">A combination of the following values:</span></span>
    - <span data-ttu-id="a2b48-188">`read` – Lesevorgänge sind auf dem Gerät zulässig</span><span class="sxs-lookup"><span data-stu-id="a2b48-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="a2b48-189">`write` – Schreibvorgänge sind auf dem Gerät zulässig</span><span class="sxs-lookup"><span data-stu-id="a2b48-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="a2b48-190">`execute` - Ausführen von Vorgängen auf dem Gerät zulässig</span><span class="sxs-lookup"><span data-stu-id="a2b48-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="a2b48-191">Wenn `none` die Berechtigungsstufe vorhanden ist, werden alle anderen Berechtigungen ( `read` oder ) `write` `execute` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2b48-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="a2b48-192">Die `execute` Berechtigung bezieht sich nur auf die Ausführung von binären Binärdateien.</span><span class="sxs-lookup"><span data-stu-id="a2b48-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="a2b48-193">Es umfasst nicht die Ausführung von Skripts oder anderen Arten von Nutzlasten.</span><span class="sxs-lookup"><span data-stu-id="a2b48-193">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="a2b48-194">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-194">Section</span></span>|<span data-ttu-id="a2b48-195">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-196">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-197">**Key**</span></span> | <span data-ttu-id="a2b48-198">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2b48-198">permission</span></span> |
| <span data-ttu-id="a2b48-199">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-199">**Data type**</span></span> | <span data-ttu-id="a2b48-200">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a2b48-200">Array of strings</span></span> |
| <span data-ttu-id="a2b48-201">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="a2b48-201">**Possible values**</span></span> | <span data-ttu-id="a2b48-202">keine</span><span class="sxs-lookup"><span data-stu-id="a2b48-202">none</span></span> <br/> <span data-ttu-id="a2b48-203">Lesen</span><span class="sxs-lookup"><span data-stu-id="a2b48-203">read</span></span> <br/> <span data-ttu-id="a2b48-204">Schreiben</span><span class="sxs-lookup"><span data-stu-id="a2b48-204">write</span></span> <br/> <span data-ttu-id="a2b48-205">Ausführen</span><span class="sxs-lookup"><span data-stu-id="a2b48-205">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="a2b48-206">Einschränken von Wechselmedien nach Hersteller, Produkt und Seriennummer</span><span class="sxs-lookup"><span data-stu-id="a2b48-206">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="a2b48-207">Wie unter ["Zulassen oder Blockieren von Wechselmedien"](#allow-or-block-removable-devices)beschrieben, können Wechselmedien wie USB-Geräte anhand der Hersteller-ID, der Produkt-ID und der Seriennummer identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-207">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="a2b48-208">Auf der obersten Ebene der Richtlinie für Wechselmedien können Sie optional detailliertere Einschränkungen auf Herstellerebene definieren.</span><span class="sxs-lookup"><span data-stu-id="a2b48-208">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="a2b48-209">Das `vendors` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Anbieter-ID identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a2b48-209">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="a2b48-210">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-210">Section</span></span>|<span data-ttu-id="a2b48-211">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-211">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-212">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-212">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-213">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-213">**Key**</span></span> | <span data-ttu-id="a2b48-214">Anbieter</span><span class="sxs-lookup"><span data-stu-id="a2b48-214">vendors</span></span> |
| <span data-ttu-id="a2b48-215">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-215">**Data type**</span></span> | <span data-ttu-id="a2b48-216">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="a2b48-216">Dictionary (nested preference)</span></span> |

<span data-ttu-id="a2b48-217">Für jeden Anbieter können Sie die gewünschte Berechtigungsstufe für Geräte von diesem Anbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="a2b48-217">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="a2b48-218">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-218">Section</span></span>|<span data-ttu-id="a2b48-219">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-220">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-221">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-221">**Key**</span></span> | <span data-ttu-id="a2b48-222">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2b48-222">permission</span></span> |
| <span data-ttu-id="a2b48-223">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-223">**Data type**</span></span> | <span data-ttu-id="a2b48-224">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a2b48-224">Array of strings</span></span> |
| <span data-ttu-id="a2b48-225">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="a2b48-225">**Possible values**</span></span> | <span data-ttu-id="a2b48-226">Identisch mit [der Standardberechtigungsstufe](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="a2b48-226">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="a2b48-227">Darüber hinaus können Sie optional den Satz von Produkten angeben, die zu diesem Anbieter gehören, für den detailliertere Berechtigungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a2b48-227">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="a2b48-228">Das `products` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Produkt-ID identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a2b48-228">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="a2b48-229">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-229">Section</span></span>|<span data-ttu-id="a2b48-230">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-230">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-231">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-231">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-232">**Key**</span></span> | <span data-ttu-id="a2b48-233">Produkte</span><span class="sxs-lookup"><span data-stu-id="a2b48-233">products</span></span> |
| <span data-ttu-id="a2b48-234">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-234">**Data type**</span></span> | <span data-ttu-id="a2b48-235">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="a2b48-235">Dictionary (nested preference)</span></span> |

<span data-ttu-id="a2b48-236">Für jedes Produkt können Sie die gewünschte Berechtigungsstufe für dieses Produkt angeben.</span><span class="sxs-lookup"><span data-stu-id="a2b48-236">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="a2b48-237">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-237">Section</span></span>|<span data-ttu-id="a2b48-238">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-239">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-240">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-240">**Key**</span></span> | <span data-ttu-id="a2b48-241">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2b48-241">permission</span></span> |
| <span data-ttu-id="a2b48-242">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-242">**Data type**</span></span> | <span data-ttu-id="a2b48-243">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a2b48-243">Array of strings</span></span> |
| <span data-ttu-id="a2b48-244">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="a2b48-244">**Possible values**</span></span> | <span data-ttu-id="a2b48-245">Identisch mit [der Standardberechtigungsstufe](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="a2b48-245">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="a2b48-246">Darüber hinaus können Sie einen optionalen Satz von Seriennummern angeben, für die detailliertere Berechtigungen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a2b48-246">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="a2b48-247">Das `serialNumbers` Wörterbuch enthält einen oder mehrere Einträge, wobei jeder Eintrag durch die Seriennummer identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a2b48-247">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="a2b48-248">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-248">Section</span></span>|<span data-ttu-id="a2b48-249">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-249">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-250">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-250">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-251">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-251">**Key**</span></span> | <span data-ttu-id="a2b48-252">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="a2b48-252">serialNumbers</span></span> |
| <span data-ttu-id="a2b48-253">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-253">**Data type**</span></span> | <span data-ttu-id="a2b48-254">Wörterbuch (geschachtelte Präferenz)</span><span class="sxs-lookup"><span data-stu-id="a2b48-254">Dictionary (nested preference)</span></span> |

<span data-ttu-id="a2b48-255">Für jede Seriennummer können Sie die gewünschte Berechtigungsstufe angeben.</span><span class="sxs-lookup"><span data-stu-id="a2b48-255">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="a2b48-256">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2b48-256">Section</span></span>|<span data-ttu-id="a2b48-257">Wert</span><span class="sxs-lookup"><span data-stu-id="a2b48-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="a2b48-258">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="a2b48-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="a2b48-259">**Key**</span><span class="sxs-lookup"><span data-stu-id="a2b48-259">**Key**</span></span> | <span data-ttu-id="a2b48-260">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a2b48-260">permission</span></span> |
| <span data-ttu-id="a2b48-261">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a2b48-261">**Data type**</span></span> | <span data-ttu-id="a2b48-262">Array aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a2b48-262">Array of strings</span></span> |
| <span data-ttu-id="a2b48-263">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="a2b48-263">**Possible values**</span></span> | <span data-ttu-id="a2b48-264">Identisch mit [der Standardberechtigungsstufe](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="a2b48-264">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="a2b48-265">Beispiel für eine Gerätesteuerungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b48-265">Example device control policy</span></span>

<span data-ttu-id="a2b48-266">Das folgende Beispiel zeigt, wie alle oben genannten Konzepte in einer Gerätesteuerungsrichtlinie kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="a2b48-266">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="a2b48-267">Beachten Sie im folgenden Beispiel die hierarchische Natur der Richtlinie für Wechselmedien.</span><span class="sxs-lookup"><span data-stu-id="a2b48-267">In the following example, note the hierarchical nature of the removable media policy.</span></span>

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

<span data-ttu-id="a2b48-268">Wir haben weitere Beispiele für Gerätesteuerungsrichtlinien in die folgenden Dokumente aufgenommen:</span><span class="sxs-lookup"><span data-stu-id="a2b48-268">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="a2b48-269">Beispiele für Gerätesteuerungsrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="a2b48-269">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="a2b48-270">Beispiele für Gerätesteuerungsrichtlinien für JAMF</span><span class="sxs-lookup"><span data-stu-id="a2b48-270">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="a2b48-271">Nachschlagen von Gerätebezeichnern</span><span class="sxs-lookup"><span data-stu-id="a2b48-271">Look up device identifiers</span></span>

<span data-ttu-id="a2b48-272">So suchen Sie die Anbieter-ID, Produkt-ID und Seriennummer eines USB-Geräts:</span><span class="sxs-lookup"><span data-stu-id="a2b48-272">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="a2b48-273">Melden Sie sich bei einem Mac-Gerät an.</span><span class="sxs-lookup"><span data-stu-id="a2b48-273">Log into a Mac device.</span></span>
1. <span data-ttu-id="a2b48-274">Schließen Sie das USB-Gerät an, für das Sie die Bezeichner nachschlagen möchten.</span><span class="sxs-lookup"><span data-stu-id="a2b48-274">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="a2b48-275">Wählen Sie im Menü der obersten Ebene von macOS **"Info zu diesem Mac"** aus.</span><span class="sxs-lookup"><span data-stu-id="a2b48-275">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Informationen zu diesem Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="a2b48-277">Wählen Sie **"Systembericht" aus.**</span><span class="sxs-lookup"><span data-stu-id="a2b48-277">Select **System Report**.</span></span>

    ![Systembericht](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="a2b48-279">Wählen Sie in der linken Spalte **USB** aus.</span><span class="sxs-lookup"><span data-stu-id="a2b48-279">From the left column, select **USB**.</span></span>

    ![Ansicht aller USB-Geräte](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="a2b48-281">Navigieren Sie unter **der USB-Gerätestruktur** zu dem USB-Gerät, das Sie angeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a2b48-281">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Details zu einem USB-Gerät](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="a2b48-283">Die Anbieter-ID, Produkt-ID und Seriennummer werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2b48-283">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="a2b48-284">Wenn Sie die Anbieter-ID und die Produkt-ID zur Richtlinie für Wechselmedien hinzufügen, müssen Sie den Teil erst nach `0x` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a2b48-284">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="a2b48-285">In der folgenden Abbildung ist z. B. die Anbieter-ID `1000` und die Produkt-ID `090c` .</span><span class="sxs-lookup"><span data-stu-id="a2b48-285">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="a2b48-286">Ermitteln von USB-Geräten in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a2b48-286">Discover USB devices in your organization</span></span>

<span data-ttu-id="a2b48-287">Sie können Mount-, Unmount- und Volumeänderungsereignisse von USB-Geräten in der erweiterten Suche in Microsoft Defender für Endpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2b48-287">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="a2b48-288">Diese Ereignisse können hilfreich sein, um verdächtige Nutzungsaktivitäten zu identifizieren oder interne Untersuchungen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a2b48-288">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="a2b48-289">Bereitstellung von Gerätesteuerungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a2b48-289">Device control policy deployment</span></span>

<span data-ttu-id="a2b48-290">Die Gerätesteuerungsrichtlinie muss neben den anderen Produkteinstellungen enthalten sein, wie unter Festlegen der [Einstellungen für Microsoft Defender für Endpunkt unter macOS](mac-preferences.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2b48-290">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="a2b48-291">Dieses Profil kann mithilfe der Anweisungen bereitgestellt werden, die in der Bereitstellung des [Konfigurationsprofils](mac-preferences.md#configuration-profile-deployment)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="a2b48-291">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="a2b48-292">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a2b48-292">Troubleshooting tips</span></span>

<span data-ttu-id="a2b48-293">Nachdem Sie das Konfigurationsprofil über Intune oder JAMF übertragen haben, können Sie überprüfen, ob es vom Produkt erfolgreich aufgenommen wurde, indem Sie den folgenden Befehl aus dem Terminal ausführen:</span><span class="sxs-lookup"><span data-stu-id="a2b48-293">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="a2b48-294">Dieser Befehl druckt in der Standardausgabe der Gerätesteuerungsrichtlinie, die das Produkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2b48-294">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="a2b48-295">Falls dies gedruckt `Policy is empty` wird, stellen Sie sicher, dass (a) das Konfigurationsprofil tatsächlich von der Verwaltungskonsole an Ihr Gerät übertragen wurde und (b) es sich um eine gültige Gerätesteuerungsrichtlinie handelt, wie in diesem Dokument beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2b48-295">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="a2b48-296">Auf einem Gerät, auf dem die Richtlinie erfolgreich bereitgestellt wurde und ein oder mehrere Geräte angeschlossen sind, können Sie den folgenden Befehl ausführen, um alle Geräte und die effektiven Berechtigungen aufzuführen, die ihnen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="a2b48-296">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="a2b48-297">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="a2b48-297">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="a2b48-298">Im obigen Beispiel ist nur ein Wechselmediengerät angeschlossen und verfügt `read` über berechtigungen gemäß der `execute` Gerätesteuerungsrichtlinie, die an das Gerät übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="a2b48-298">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2b48-299">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a2b48-299">Related topics</span></span>

- [<span data-ttu-id="a2b48-300">Beispiele für Gerätesteuerungsrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="a2b48-300">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="a2b48-301">Beispiele für Gerätesteuerungsrichtlinien für JAMF</span><span class="sxs-lookup"><span data-stu-id="a2b48-301">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
