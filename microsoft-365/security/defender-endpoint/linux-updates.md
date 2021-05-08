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
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Bereitstellen von Updates für Microsoft Defender for Endpoint unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.

> [!WARNING]
> Jede Version von Defender for Endpoint unter Linux hat ein Ablaufdatum, nach dem sie Ihr Gerät nicht mehr schützt. Sie müssen das Produkt vor diesem Datum aktualisieren. Führen Sie den folgenden Befehl aus, um das Ablaufdatum zu überprüfen:
> ```bash
> mdatp health --field product_expiration
> ```


Allgemein verfügbare Microsoft Defender for Endpoint-Funktionen entsprechen unabhängig vom Updatekanal, der für eine Bereitstellung verwendet wird (Beta (Insider), Vorschau (Extern), Current (Production)).


Führen Sie einen der folgenden Befehle aus, um Defender for Endpoint unter Linux manuell zu aktualisieren:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL und Varianten (CentOS und Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES und Varianten

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu- und Debian-Systeme

```bash
sudo apt-get install --only-upgrade mdatp
```
