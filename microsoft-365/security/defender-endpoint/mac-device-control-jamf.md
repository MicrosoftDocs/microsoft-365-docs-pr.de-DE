---
title: Beispiele für Gerätesteuerungsrichtlinien für JAMF
description: Erfahren Sie, wie Sie Gerätesteuerungsrichtlinien mithilfe von Beispielen verwenden, die mit JAMF verwendet werden können.
keywords: microsoft, defender, endpoint, Microsoft Defender for Endpoint, mac, device, control, usb, removable, media, jamf
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
ms.openlocfilehash: b9ce161a472366d11b267824c9bd08ceccf285aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933457"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="530ce-104">Beispiele für Gerätesteuerungsrichtlinien für JAMF</span><span class="sxs-lookup"><span data-stu-id="530ce-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="530ce-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="530ce-105">**Applies to:**</span></span>
- [<span data-ttu-id="530ce-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="530ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="530ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="530ce-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="530ce-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="530ce-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="530ce-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="530ce-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="530ce-110">Dieses Dokument enthält Beispiele für Gerätesteuerungsrichtlinien, die Sie für Ihre eigene Organisation anpassen können.</span><span class="sxs-lookup"><span data-stu-id="530ce-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="530ce-111">Diese Beispiele sind anwendbar, wenn Sie JAMF zum Verwalten von Geräten in Ihrem Unternehmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="530ce-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="530ce-112">Einschränken des Zugriffs auf alle Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="530ce-112">Restrict access to all removable media</span></span>

<span data-ttu-id="530ce-113">Im folgenden Beispiel wird der Zugriff auf alle Wechselmedien eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="530ce-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="530ce-114">Beachten Sie die Berechtigung, die auf oberster Ebene der Richtlinie angewendet wird, was bedeutet, dass `none` alle Dateivorgänge verboten sind.</span><span class="sxs-lookup"><span data-stu-id="530ce-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="530ce-115">Festlegen, dass alle Wechselmedien schreibgeschützt sind</span><span class="sxs-lookup"><span data-stu-id="530ce-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="530ce-116">Im folgenden Beispiel wird konfiguriert, dass alle Wechselmedien schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="530ce-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="530ce-117">Beachten Sie die Berechtigung, die auf der obersten Ebene der Richtlinie angewendet wird, was bedeutet, dass alle Schreib- und Ausführungsvorgänge nicht zulässig `read` sind.</span><span class="sxs-lookup"><span data-stu-id="530ce-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="530ce-118">Programmausführung von Wechselmedien nicht ermöglichen</span><span class="sxs-lookup"><span data-stu-id="530ce-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="530ce-119">Das folgende Beispiel zeigt, wie die Programmausführung von Wechselmedien nicht zulässig sein kann.</span><span class="sxs-lookup"><span data-stu-id="530ce-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="530ce-120">Beachten Sie `read` die `write` Berechtigungen, die auf der obersten Ebene der Richtlinie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="530ce-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="530ce-121">Einschränken aller Geräte von bestimmten Anbietern</span><span class="sxs-lookup"><span data-stu-id="530ce-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="530ce-122">Im folgenden Beispiel werden alle Geräte von bestimmten Anbietern (in diesem Fall durch und `fff0` identifiziert) `4525` eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="530ce-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="530ce-123">Alle anderen Geräte sind uneingeschränkt, da die auf oberster Ebene der Richtlinie definierte Berechtigung alle möglichen Berechtigungen (Lese-, Schreib- und Ausführungsberechtigungen) auflistet.</span><span class="sxs-lookup"><span data-stu-id="530ce-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="530ce-124">Einschränken bestimmter Geräte, die durch Hersteller-ID, Produkt-ID und Seriennummer identifiziert werden</span><span class="sxs-lookup"><span data-stu-id="530ce-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="530ce-125">Das folgende Beispiel schränkt zwei bestimmte Geräte ein, die durch hersteller-ID, `fff0` Produkt-ID `1000` und Seriennummern und identifiziert `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` werden.</span><span class="sxs-lookup"><span data-stu-id="530ce-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="530ce-126">Auf allen anderen Ebenen der Richtlinie enthalten die Berechtigungen alle möglichen Werte (Lesen, Schreiben und Ausführen), was bedeutet, dass alle anderen Geräte uneingeschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="530ce-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="530ce-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="530ce-127">Related topics</span></span>

- [<span data-ttu-id="530ce-128">Übersicht über die Gerätesteuerung für macOS</span><span class="sxs-lookup"><span data-stu-id="530ce-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
