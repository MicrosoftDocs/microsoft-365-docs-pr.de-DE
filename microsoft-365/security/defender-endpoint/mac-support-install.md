---
title: Beheben von Installationsproblemen für Microsoft Defender ATP für Mac
description: Beheben von Installationsproblemen in Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, install
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
ms.openlocfilehash: 888bffdb85adeb7af58504439c1c31c7232cd73b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187625"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="29bcd-104">Beheben von Installationsproblemen für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="29bcd-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="29bcd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="29bcd-105">**Applies to:**</span></span>

- [<span data-ttu-id="29bcd-106">Microsoft Defender für Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="29bcd-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="29bcd-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="29bcd-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29bcd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29bcd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="29bcd-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="29bcd-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29bcd-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="29bcd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="29bcd-111">Installation fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="29bcd-111">Installation failed</span></span>

<span data-ttu-id="29bcd-112">Für die manuelle Installation heißt es auf der Seite Zusammenfassung des Installations-Assistenten: "Bei der Installation ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="29bcd-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="29bcd-113">Beim Installer ist ein Fehler aufgetreten, der zu einem Fehler bei der Installation führte.</span><span class="sxs-lookup"><span data-stu-id="29bcd-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="29bcd-114">Wenden Sie sich an den Softwarehersteller, um Unterstützung zu erhalten."</span><span class="sxs-lookup"><span data-stu-id="29bcd-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="29bcd-115">Bei MDM-Bereitstellungen wird auch ein allgemeiner Installationsfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29bcd-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="29bcd-116">Wir zeigen dem Endbenutzer zwar keinen genauen Fehler an, aber wir behalten eine Protokolldatei mit dem Installationsfortschritt in `/Library/Logs/Microsoft/mdatp/install.log` bei.</span><span class="sxs-lookup"><span data-stu-id="29bcd-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="29bcd-117">Jede Installationssitzung wird an diese Protokolldatei angefügt.</span><span class="sxs-lookup"><span data-stu-id="29bcd-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="29bcd-118">Sie können die `sed` letzte Installationssitzung nur verwenden:</span><span class="sxs-lookup"><span data-stu-id="29bcd-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="29bcd-119">In diesem Beispiel wird dem tatsächlichen Grund das Präfix `[ERROR]` vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="29bcd-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="29bcd-120">Die Installation ist fehlgeschlagen, da ein Downgrade zwischen diesen Versionen nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="29bcd-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="29bcd-121">MDATP-Installationsprotokoll fehlt oder wird nicht aktualisiert</span><span class="sxs-lookup"><span data-stu-id="29bcd-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="29bcd-122">In seltenen Fällen hinterlässt die Installation keine Ablaufverfolgung in der Datei /Library/Logs/Microsoft/mdatp/install.log von MDATP.</span><span class="sxs-lookup"><span data-stu-id="29bcd-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="29bcd-123">Sie können überprüfen, ob eine Installation ausgeführt wurde, und mögliche Fehler analysieren, indem Sie macOS-Protokolle abfragen (dies ist bei der MDM-Bereitstellung hilfreich, wenn keine Clientbenutzeroberfläche verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="29bcd-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="29bcd-124">Es wird empfohlen, ein schmales Zeitfenster zum Ausführen einer Abfrage zu verwenden und nach dem Namen des Protokollierungsprozesses zu filtern, da eine große Menge an Informationen zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="29bcd-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
