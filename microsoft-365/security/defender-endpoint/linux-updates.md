---
title: Bereitstellen von Updates für Microsoft Defender for Endpoint unter Linux
ms.reviewer: ''
description: Beschreibt, wie Updates für Microsoft Defender for Endpoint unter Linux in Unternehmensumgebungen bereitgestellt werden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, updates, deploy
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
ms.openlocfilehash: 9cb0c7375b538f502cf6165f13c68fd4b2fdcc64
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934753"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2ff08-104">Bereitstellen von Updates für Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="2ff08-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2ff08-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2ff08-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ff08-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2ff08-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ff08-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ff08-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2ff08-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2ff08-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ff08-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2ff08-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2ff08-110">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2ff08-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="2ff08-111">Jede Version von Defender for Endpoint unter Linux hat ein Ablaufdatum, nach dem sie Ihr Gerät nicht mehr schützt.</span><span class="sxs-lookup"><span data-stu-id="2ff08-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="2ff08-112">Sie müssen das Produkt vor diesem Datum aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2ff08-112">You must update the product prior to this date.</span></span> <span data-ttu-id="2ff08-113">Führen Sie den folgenden Befehl aus, um das Ablaufdatum zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="2ff08-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="2ff08-114">Führen Sie einen der folgenden Befehle aus, um Defender for Endpoint unter Linux manuell zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="2ff08-114">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="2ff08-115">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="2ff08-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="2ff08-116">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="2ff08-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="2ff08-117">Ubuntu- und Debian-Systeme</span><span class="sxs-lookup"><span data-stu-id="2ff08-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
