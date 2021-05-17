---
title: Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender for Endpoint unter Linux
description: Erkennen und Blockieren von potenziell unerwünschten Anwendungen (PUA) mithilfe von Microsoft Defender for Endpoint unter Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, pua, pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7ec3399129cc65d75b464f5d5f56bb11250ccaf2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933157"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="1a5dc-104">Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="1a5dc-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1a5dc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1a5dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a5dc-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1a5dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1a5dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a5dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1a5dc-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1a5dc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a5dc-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1a5dc-110">Das Feature zum Schutz potenziell unerwünschter Anwendungen (PUA) in Defender for Endpoint unter Linux kann PUA-Dateien auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint on Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="1a5dc-111">Diese Anwendungen gelten nicht als Viren, Schadsoftware oder andere Arten von Bedrohungen, sie können jedoch Aktionen für Endpunkte ausführen, die sich negativ auf ihre Leistung oder Verwendung auswirken.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="1a5dc-112">PUA kann sich auch auf Anwendungen beziehen, die als schlecht angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="1a5dc-113">Diese Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk mit Schadsoftware infiziert wird, Schadsoftwareinfektionen schwieriger zu identifizieren sind und IT-Ressourcen beim Bereinigen der Anwendungen verschwenden.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="1a5dc-114">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="1a5dc-114">How it works</span></span>

<span data-ttu-id="1a5dc-115">Defender for Endpoint unter Linux kann PUA-Dateien erkennen und melden.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-115">Defender for Endpoint on Linux can detect and report PUA files.</span></span> <span data-ttu-id="1a5dc-116">Wenn sie im Sperrmodus konfiguriert sind, werden PUA-Dateien in die Quarantäne verschoben.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="1a5dc-117">Wenn ein PUA auf einem Endpunkt erkannt wird, speichert Defender for Endpoint unter Linux eine Aufzeichnung der Infektion im Bedrohungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-117">When a PUA is detected on an endpoint, Defender for Endpoint on Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="1a5dc-118">Der Verlauf kann über das Microsoft Defender Security Center oder über das `mdatp` Befehlszeilentool visualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="1a5dc-119">Der Bedrohungsname enthält das Wort "Application".</span><span class="sxs-lookup"><span data-stu-id="1a5dc-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="1a5dc-120">Konfigurieren des PUA-Schutzes</span><span class="sxs-lookup"><span data-stu-id="1a5dc-120">Configure PUA protection</span></span>

<span data-ttu-id="1a5dc-121">Der PUA-Schutz in Defender for Endpoint unter Linux kann auf eine der folgenden Arten konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="1a5dc-121">PUA protection in Defender for Endpoint on Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="1a5dc-122">**Off**: Der PUA-Schutz ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="1a5dc-123">**Überwachung**: PUA-Dateien werden in den Produktprotokollen gemeldet, jedoch nicht in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="1a5dc-124">Es werden keine Aufzeichnungen der Infektion im Bedrohungsverlauf gespeichert, und das Produkt hat keine Maßnahmen ergriffen.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="1a5dc-125">**Block**: PUA-Dateien werden in den Produktprotokollen und in den Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="1a5dc-126">Ein Datensatz der Infektion wird im Bedrohungsverlauf gespeichert, und das Produkt hat Maßnahmen ergriffen.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="1a5dc-127">Standardmäßig ist der PUA-Schutz im **Überwachungsmodus** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="1a5dc-128">Sie können konfigurieren, wie PUA-Dateien über die Befehlszeile oder über die Verwaltungskonsole behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="1a5dc-129">Verwenden Sie das Befehlszeilentool, um den PUA-Schutz zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1a5dc-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="1a5dc-130">Führen Sie im Terminal den folgenden Befehl aus, um den PUA-Schutz zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1a5dc-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="1a5dc-131">Konfigurieren des PUA-Schutzes mithilfe der Verwaltungskonsole:</span><span class="sxs-lookup"><span data-stu-id="1a5dc-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="1a5dc-132">In Ihrem Unternehmen können Sie den PUA-Schutz über eine Verwaltungskonsole wie "Puppet" oder "Ansible" konfigurieren, ähnlich wie andere Produkteinstellungen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="1a5dc-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="1a5dc-133">Weitere Informationen finden Sie im Abschnitt [Bedrohungstypeinstellungen](linux-preferences.md#threat-type-settings) im Artikel Festlegen von Einstellungen [für Defender for Endpoint unter Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="1a5dc-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint on Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1a5dc-134">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1a5dc-134">Related articles</span></span>

- [<span data-ttu-id="1a5dc-135">Festlegen von Einstellungen für Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="1a5dc-135">Set preferences for Defender for Endpoint on Linux</span></span>](linux-preferences.md)
