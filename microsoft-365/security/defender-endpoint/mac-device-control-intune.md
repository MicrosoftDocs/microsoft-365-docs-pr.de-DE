---
title: Beispiele für Gerätesteuerungsrichtlinien für Intune
description: Erfahren Sie, wie Sie Gerätesteuerungsrichtlinien anhand von Beispielen verwenden, die mit Intune verwendet werden können.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Gerät, Steuerung, USB, Wechseldatenträger, Medien, Intune
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
ms.openlocfilehash: f52d1e9ea0d3e4c2da2ec413085a0f14efc453c7
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363803"
---
# <a name="examples-of-device-control-policies-for-intune"></a><span data-ttu-id="37494-104">Beispiele für Gerätesteuerungsrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="37494-104">Examples of device control policies for Intune</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="37494-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="37494-105">**Applies to:**</span></span>
- [<span data-ttu-id="37494-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="37494-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37494-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37494-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="37494-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="37494-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="37494-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="37494-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="37494-110">Dieses Dokument enthält Beispiele für Gerätesteuerungsrichtlinien, die Sie für Ihre eigene Organisation anpassen können.</span><span class="sxs-lookup"><span data-stu-id="37494-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="37494-111">Diese Beispiele sind anwendbar, wenn Sie Intune zum Verwalten von Geräten in Ihrem Unternehmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="37494-111">These examples are applicable if you are using Intune to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="37494-112">Einschränken des Zugriffs auf alle Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="37494-112">Restrict access to all removable media</span></span>

<span data-ttu-id="37494-113">Im folgenden Beispiel wird der Zugriff auf alle Wechselmedien eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="37494-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="37494-114">Beachten Sie die `none` Berechtigung, die auf der obersten Ebene der Richtlinie angewendet wird, was bedeutet, dass alle Dateivorgänge nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="37494-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
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
        </array> 
    </dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="37494-115">Festlegen, dass alle Wechselmedien schreibgeschützt sind</span><span class="sxs-lookup"><span data-stu-id="37494-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="37494-116">Im folgenden Beispiel werden alle Wechselmedien als schreibgeschützt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="37494-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="37494-117">Beachten Sie die `read` Berechtigung, die auf der obersten Ebene der Richtlinie angewendet wird, was bedeutet, dass alle Schreib- und Ausführungsvorgänge nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="37494-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
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
        </array> 
    </dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="37494-118">Verbieten der Programmausführung von Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="37494-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="37494-119">Das folgende Beispiel zeigt, wie die Programmausführung von Wechselmedien unzulässig sein kann.</span><span class="sxs-lookup"><span data-stu-id="37494-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="37494-120">Beachten Sie die `read` und `write` die Berechtigungen, die auf der obersten Ebene der Richtlinie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="37494-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
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
        </array> 
    </dict> 
</plist> 
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="37494-121">Einschränken aller Geräte von bestimmten Anbietern</span><span class="sxs-lookup"><span data-stu-id="37494-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="37494-122">Das folgende Beispiel schränkt alle Geräte von bestimmten Anbietern ein (in diesem Fall identifiziert von `fff0` und `4525` ).</span><span class="sxs-lookup"><span data-stu-id="37494-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="37494-123">Alle anderen Geräte sind uneingeschränkt, da die auf der obersten Ebene der Richtlinie definierte Berechtigung alle möglichen Berechtigungen (Lesen, Schreiben und Ausführen) auflistet.</span><span class="sxs-lookup"><span data-stu-id="37494-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
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
        </array> 
    </dict> 
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="37494-124">Einschränken bestimmter Geräte, die nach Hersteller-ID, Produkt-ID und Seriennummer identifiziert werden</span><span class="sxs-lookup"><span data-stu-id="37494-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="37494-125">Im folgenden Beispiel werden zwei bestimmte Geräte eingeschränkt, die durch die Hersteller-ID, `fff0` produkt-ID `1000` und Seriennummern `04ZSSMHI2O7WBVOA` und identifiziert `04ZSSMHI2O7WBVOB` werden.</span><span class="sxs-lookup"><span data-stu-id="37494-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="37494-126">Auf allen anderen Ebenen der Richtlinie enthalten die Berechtigungen alle möglichen Werte (Lesen, Schreiben und Ausführen), was bedeutet, dass alle anderen Geräte uneingeschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="37494-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
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
        </array> 
    </dict> 
</plist>
```

## <a name="related-topics"></a><span data-ttu-id="37494-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="37494-127">Related topics</span></span>

- [<span data-ttu-id="37494-128">Übersicht über die Gerätesteuerung für macOS</span><span class="sxs-lookup"><span data-stu-id="37494-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
