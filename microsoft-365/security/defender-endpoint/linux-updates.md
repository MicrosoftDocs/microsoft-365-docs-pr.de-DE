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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274724"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7163c-104">Bereitstellen von Updates für Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="7163c-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7163c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7163c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7163c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7163c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7163c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7163c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7163c-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7163c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7163c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7163c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="7163c-110">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7163c-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="7163c-111">Jede Version von Defender for Endpoint unter Linux hat ein Ablaufdatum, nach dem sie Ihr Gerät nicht mehr schützt.</span><span class="sxs-lookup"><span data-stu-id="7163c-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="7163c-112">Sie müssen das Produkt vor diesem Datum aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7163c-112">You must update the product prior to this date.</span></span> <span data-ttu-id="7163c-113">Führen Sie den folgenden Befehl aus, um das Ablaufdatum zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7163c-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="7163c-114">Allgemein verfügbare Microsoft Defender for Endpoint-Funktionen entsprechen unabhängig vom Updatekanal, der für eine Bereitstellung verwendet wird (Beta (Insider), Vorschau (Extern), Current (Production)).</span><span class="sxs-lookup"><span data-stu-id="7163c-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="7163c-115">Führen Sie einen der folgenden Befehle aus, um Defender for Endpoint unter Linux manuell zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="7163c-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="7163c-116">RHEL und Varianten (CentOS und Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="7163c-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="7163c-117">SLES und Varianten</span><span class="sxs-lookup"><span data-stu-id="7163c-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="7163c-118">Ubuntu- und Debian-Systeme</span><span class="sxs-lookup"><span data-stu-id="7163c-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
