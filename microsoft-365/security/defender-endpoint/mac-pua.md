---
title: Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender ATP für Mac
description: Erkennen und Blockieren von potenziell unerwünschten Anwendungen (PUA) mithilfe von Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187421"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="09303-104">Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="09303-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09303-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="09303-105">**Applies to:**</span></span>
- [<span data-ttu-id="09303-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="09303-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09303-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="09303-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="09303-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09303-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="09303-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="09303-110">Das Feature zum Schutz potenziell unerwünschter Anwendungen (PUA) in Microsoft Defender for Endpoint für Mac kann PUA-Dateien auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="09303-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="09303-111">Diese Anwendungen gelten nicht als Viren, Schadsoftware oder andere Arten von Bedrohungen, sie können jedoch Aktionen für Endpunkte ausführen, die sich negativ auf ihre Leistung oder Verwendung auswirken.</span><span class="sxs-lookup"><span data-stu-id="09303-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="09303-112">PUA kann sich auch auf Anwendungen beziehen, die als schlecht angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="09303-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="09303-113">Diese Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk mit Schadsoftware infiziert wird, Schadsoftwareinfektionen schwieriger zu identifizieren sind und IT-Ressourcen beim Bereinigen der Anwendungen verschwenden.</span><span class="sxs-lookup"><span data-stu-id="09303-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="09303-114">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="09303-114">How it works</span></span>

<span data-ttu-id="09303-115">Microsoft Defender for Endpoint für Mac kann PUA-Dateien erkennen und melden.</span><span class="sxs-lookup"><span data-stu-id="09303-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="09303-116">Wenn sie im Sperrmodus konfiguriert sind, werden PUA-Dateien in die Quarantäne verschoben.</span><span class="sxs-lookup"><span data-stu-id="09303-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="09303-117">Wenn ein PUA auf einem Endpunkt erkannt wird, stellt Microsoft Defender for Endpoint für Mac dem Benutzer eine Benachrichtigung vor, es sei denn, Benachrichtigungen wurden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="09303-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="09303-118">Der Bedrohungsname enthält das Wort "Application".</span><span class="sxs-lookup"><span data-stu-id="09303-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="09303-119">Konfigurieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="09303-119">Configure PUA protection</span></span>

<span data-ttu-id="09303-120">Der PUA-Schutz in Microsoft Defender for Endpoint für Mac kann auf eine der folgenden Arten konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="09303-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="09303-121">**Off**: Der PUA-Schutz ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="09303-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="09303-122">**Überwachung:** PUA-Dateien werden in den Produktprotokollen, jedoch nicht im Microsoft Defender Security Center gemeldet.</span><span class="sxs-lookup"><span data-stu-id="09303-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="09303-123">Dem Benutzer wird keine Benachrichtigung angezeigt, und es werden keine Aktionen vom Produkt ergriffen.</span><span class="sxs-lookup"><span data-stu-id="09303-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="09303-124">**Block**: PUA-Dateien werden in den Produktprotokollen und im Microsoft Defender Security Center gemeldet.</span><span class="sxs-lookup"><span data-stu-id="09303-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="09303-125">Dem Benutzer wird eine Benachrichtigung angezeigt, und das Produkt wird aktiv.</span><span class="sxs-lookup"><span data-stu-id="09303-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="09303-126">Standardmäßig ist der PUA-Schutz im **Überwachungsmodus** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="09303-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="09303-127">Sie können konfigurieren, wie PUA-Dateien über die Befehlszeile oder über die Verwaltungskonsole behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="09303-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="09303-128">Verwenden Sie das Befehlszeilentool, um den PUA-Schutz zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="09303-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="09303-129">Führen Sie im Terminal den folgenden Befehl aus, um den PUA-Schutz zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="09303-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="09303-130">Konfigurieren des PUA-Schutzes mithilfe der Verwaltungskonsole:</span><span class="sxs-lookup"><span data-stu-id="09303-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="09303-131">In Ihrem Unternehmen können Sie den PUA-Schutz über eine Verwaltungskonsole wie JAMF oder Intune konfigurieren, ähnlich wie andere Produkteinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="09303-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="09303-132">Weitere Informationen finden Sie im Abschnitt [Bedrohungstypeinstellungen](mac-preferences.md#threat-type-settings) im Thema Festlegen von Einstellungen für [Microsoft Defender for Endpoint für Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="09303-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09303-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="09303-133">Related topics</span></span>

- [<span data-ttu-id="09303-134">Festlegen von Einstellungen für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="09303-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)
