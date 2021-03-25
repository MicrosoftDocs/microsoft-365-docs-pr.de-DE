---
title: Bereitstellen von Updates für Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Beschreibt, wie Updates für Microsoft Defender ATP für Linux in Unternehmensumgebungen bereitgestellt werden.
keywords: microsoft, defender, atp, linux, updates, deploy
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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187721"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4c028-104">Bereitstellen von Updates für Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="4c028-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4c028-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4c028-105">**Applies to:**</span></span>
- [<span data-ttu-id="4c028-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4c028-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4c028-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c028-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4c028-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4c028-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4c028-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4c028-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4c028-110">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4c028-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="4c028-111">Jede Version von Defender for Endpoint für Linux hat ein Ablaufdatum, nach dem sie Ihr Gerät nicht mehr schützt.</span><span class="sxs-lookup"><span data-stu-id="4c028-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="4c028-112">Sie müssen das Produkt vor diesem Datum aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4c028-112">You must update the product prior to this date.</span></span> <span data-ttu-id="4c028-113">Führen Sie den folgenden Befehl aus, um das Ablaufdatum zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4c028-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="4c028-114">Führen Sie einen der folgenden Befehle aus, um Defender for Endpoint für Linux manuell zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="4c028-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="4c028-115">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="4c028-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="4c028-116">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="4c028-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="4c028-117">Ubuntu- und Debian-Systeme</span><span class="sxs-lookup"><span data-stu-id="4c028-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
