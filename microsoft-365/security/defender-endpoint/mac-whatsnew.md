---
title: Neues in Microsoft Defender for Endpoint für Mac
description: Erfahren Sie mehr über die wichtigsten Änderungen in früheren Versionen von Microsoft Defender for Endpoint für Mac.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
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
ms.openlocfilehash: be906baca3a54183e22fa3b4ee424a9d8fc6957a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198693"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="1248e-104">Neues in Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="1248e-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1248e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1248e-105">**Applies to:**</span></span>
- [<span data-ttu-id="1248e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1248e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1248e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1248e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1248e-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1248e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1248e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1248e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="1248e-110">Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile.</span><span class="sxs-lookup"><span data-stu-id="1248e-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="1248e-111">Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die auf dieser [Seite aufgeführt sind.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1248e-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1248e-112">Die Unterstützung für macOS 10.13 (High Sierra) wird am 15. Februar 2021 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="1248e-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="1248e-113">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="1248e-113">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="1248e-114">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-114">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="1248e-115">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="1248e-115">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="1248e-116">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-116">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="1248e-117">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="1248e-117">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="1248e-118">Die alte Befehlszeilentoolsyntax ist mit dieser Version veraltet.</span><span class="sxs-lookup"><span data-stu-id="1248e-118">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="1248e-119">Informationen zur neuen Syntax finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="1248e-119">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="1248e-120">Es wurde ein neuer Befehlszeilenschalter hinzugefügt, um die Netzwerkerweiterung zu deaktivieren: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="1248e-120">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="1248e-121">Dieser Befehl kann hilfreich sein, um Netzwerkprobleme zu beheben, die mit Microsoft Defender for Endpoint für Mac in Zusammenhang stehen könnten.</span><span class="sxs-lookup"><span data-stu-id="1248e-121">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="1248e-122">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-122">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="1248e-123">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="1248e-123">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="1248e-124">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-124">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="1248e-125">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="1248e-125">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="1248e-126">Verbesserte Zuverlässigkeit des Agents bei der Ausführung unter macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="1248e-126">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="1248e-127">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="1248e-127">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="1248e-128">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-128">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="1248e-129">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="1248e-129">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="1248e-130">Bedingungen wurden entfernt, als Microsoft Defender for Endpoint einen macOS 11 (Big Sur)-Fehler auslöste, der sich in einer Kernelpanik manifestierte.</span><span class="sxs-lookup"><span data-stu-id="1248e-130">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="1248e-131">Behebung eines Speicherverlusts in der Endpunktsicherheitssystemerweiterung bei der Ausführung auf mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="1248e-131">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="1248e-132">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-132">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="1248e-133">101.10.72</span><span class="sxs-lookup"><span data-stu-id="1248e-133">101.10.72</span></span>

- <span data-ttu-id="1248e-134">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-134">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="1248e-135">101.09.61</span><span class="sxs-lookup"><span data-stu-id="1248e-135">101.09.61</span></span>

- <span data-ttu-id="1248e-136">Neue verwaltete Einstellung zum Deaktivieren der Option [zum Senden von Feedback hinzugefügt](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="1248e-136">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="1248e-137">Das Statusmenüsymbol zeigt jetzt einen fehlerfreien Status an, wenn die Produkteinstellungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1248e-137">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="1248e-138">Zuvor wurde im Statusmenüsymbol ein Warnungs- oder Fehlerstatus angezeigt, obwohl die Produkteinstellungen vom Administrator verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="1248e-138">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="1248e-139">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-139">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="1248e-140">101.09.50</span><span class="sxs-lookup"><span data-stu-id="1248e-140">101.09.50</span></span>

- <span data-ttu-id="1248e-141">Diese Produktversion wurde unter macOS Big Sur 11 Beta 9 überprüft.</span><span class="sxs-lookup"><span data-stu-id="1248e-141">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="1248e-142">Die neue Syntax für `mdatp` das Befehlszeilentool ist jetzt die Standardsyntax.</span><span class="sxs-lookup"><span data-stu-id="1248e-142">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="1248e-143">Weitere Informationen zur neuen Syntax finden Sie unter [Ressourcen für Microsoft Defender for Endpoint für Mac.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="1248e-143">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="1248e-144">Die alte Befehlszeilentoolsyntax wird am **1. Januar 2021** aus dem Produkt entfernt.</span><span class="sxs-lookup"><span data-stu-id="1248e-144">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="1248e-145">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="1248e-145">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="1248e-146">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-146">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="1248e-147">101.09.49</span><span class="sxs-lookup"><span data-stu-id="1248e-147">101.09.49</span></span>

- <span data-ttu-id="1248e-148">Verbesserungen der Benutzeroberfläche zur Unterscheidung von Vom IT-Administrator verwalteten Ausschlüssen und vom lokalen Benutzer definierten Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="1248e-148">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="1248e-149">Verbesserte CPU-Auslastung bei Bedarfsscans</span><span class="sxs-lookup"><span data-stu-id="1248e-149">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="1248e-150">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-150">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="1248e-151">101.07.23</span><span class="sxs-lookup"><span data-stu-id="1248e-151">101.07.23</span></span>

- <span data-ttu-id="1248e-152">Neue Felder zur Ausgabe von hinzugefügt, um den Status des passiven Modus und die `mdatp --health` EDR-Gruppen-ID zu überprüfen</span><span class="sxs-lookup"><span data-stu-id="1248e-152">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="1248e-153">`mdatp --health` wird in einem `mdatp health` zukünftigen Produktupdate ersetzt.</span><span class="sxs-lookup"><span data-stu-id="1248e-153">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="1248e-154">Fehler behoben, bei dem die automatische Beispielübermittlung auf der Benutzeroberfläche nicht als verwaltet gekennzeichnet wurde</span><span class="sxs-lookup"><span data-stu-id="1248e-154">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="1248e-155">Neue Einstellungen zum Steuern der Aufbewahrung von Elementen im Antivirusscanverlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1248e-155">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="1248e-156">Sie können jetzt [die Anzahl der](mac-preferences.md#antivirus-scan-history-retention-in-days) Tage angeben, die Elemente im Überprüfungsverlauf beibehalten werden sollen, und die maximale Anzahl von Elementen im [Scanverlauf angeben.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="1248e-156">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="1248e-157">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-157">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="1248e-158">101.06.63</span><span class="sxs-lookup"><span data-stu-id="1248e-158">101.06.63</span></span>

- <span data-ttu-id="1248e-159">Es wurde eine Leistungsregression behoben, die in Version eingeführt `101.05.17` wurde.</span><span class="sxs-lookup"><span data-stu-id="1248e-159">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="1248e-160">Die Regression wurde mit dem Fix eingeführt, um die Kernelpaniken zu beseitigen, die einige Kunden beim Zugriff auf SMB-Freigaben beobachtet haben.</span><span class="sxs-lookup"><span data-stu-id="1248e-160">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="1248e-161">Wir haben diese Codeänderung wiederhergestellt und untersuchen alternative Möglichkeiten, um die Kernelpaniken zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="1248e-161">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="1248e-162">101.05.17</span><span class="sxs-lookup"><span data-stu-id="1248e-162">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1248e-163">Wir arbeiten an einer neuen und erweiterten Syntax für das `mdatp` Befehlszeilentool.</span><span class="sxs-lookup"><span data-stu-id="1248e-163">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="1248e-164">Die neue Syntax ist derzeit die Standardeinstellung in den Kanälen Insider Fast und Insider Slow Update.</span><span class="sxs-lookup"><span data-stu-id="1248e-164">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="1248e-165">Wir empfehlen Ihnen, sich mit dieser neuen Syntax vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="1248e-165">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="1248e-166">Wir werden die alte Syntax parallel zur neuen Syntax weiterhin unterstützen und in den kommenden Monaten mehr Kommunikation rund um den Veralteten Plan für die alte Syntax bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1248e-166">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="1248e-167">Es wurde eine Kernelpanik behoben, die manchmal beim Zugriff auf SMB-Dateifreigaben aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="1248e-167">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="1248e-168">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-168">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="1248e-169">101.05.16</span><span class="sxs-lookup"><span data-stu-id="1248e-169">101.05.16</span></span>

- <span data-ttu-id="1248e-170">Verbesserungen bei der Schnellscanlogik, um die Anzahl der gescannten Dateien erheblich zu reduzieren</span><span class="sxs-lookup"><span data-stu-id="1248e-170">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="1248e-171">Unterstützung [für die automatische Vervollständigung](mac-resources.md#how-to-enable-autocompletion) für das Befehlszeilentool hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1248e-171">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="1248e-172">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-172">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="1248e-173">101.03.12</span><span class="sxs-lookup"><span data-stu-id="1248e-173">101.03.12</span></span>

- <span data-ttu-id="1248e-174">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-174">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="1248e-175">101.01.54</span><span class="sxs-lookup"><span data-stu-id="1248e-175">101.01.54</span></span>

- <span data-ttu-id="1248e-176">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="1248e-176">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="1248e-177">Verbesserungen bei der Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="1248e-177">Accessibility improvements</span></span>
- <span data-ttu-id="1248e-178">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-178">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="1248e-179">101.00.31</span><span class="sxs-lookup"><span data-stu-id="1248e-179">101.00.31</span></span>

- <span data-ttu-id="1248e-180">Verbesserte [Produkt-Onboarding-Erfahrung für Intune-Benutzer](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="1248e-180">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="1248e-181">[Antivirusausschlüsse unterstützen jetzt Platzhalter](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="1248e-181">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="1248e-182">Die Möglichkeit zum Auslösen von Antivirenscans aus dem kontextbezogenen MacOS-Menü wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1248e-182">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="1248e-183">Sie können nun mit der rechten Maustaste auf eine Datei oder einen Ordner im Finder klicken und **mit Microsoft Defender for Endpoint scannen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="1248e-183">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="1248e-184">In-Place-Produktabstufungen werden nun vom Installationsprogramm explizit nicht mehr zugelassen.</span><span class="sxs-lookup"><span data-stu-id="1248e-184">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="1248e-185">Wenn Sie ein Downgrade benötigen, deinstallieren Sie zuerst die vorhandene Version, und konfigurieren Sie Ihr Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="1248e-185">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="1248e-186">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-186">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="1248e-187">100.90.27</span><span class="sxs-lookup"><span data-stu-id="1248e-187">100.90.27</span></span>

- <span data-ttu-id="1248e-188">Sie können jetzt [einen Updatekanal](mac-updates.md#set-the-channel-name) für Microsoft Defender for Endpoint für Mac festlegen, der sich vom systemweiten Updatekanal ab unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="1248e-188">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="1248e-189">Symbol für neues Produkt</span><span class="sxs-lookup"><span data-stu-id="1248e-189">New product icon</span></span>
- <span data-ttu-id="1248e-190">Weitere Verbesserungen bei der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="1248e-190">Other user experience improvements</span></span>
- <span data-ttu-id="1248e-191">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-191">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="1248e-192">100.86.92</span><span class="sxs-lookup"><span data-stu-id="1248e-192">100.86.92</span></span>

- <span data-ttu-id="1248e-193">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="1248e-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="1248e-194">Es wurde ein Problem behoben, bei dem das Produkt während der Deinstallation manchmal nicht alle Dateien `/Library/Application Support/Microsoft/Defender` unter bereinigen konnte.</span><span class="sxs-lookup"><span data-stu-id="1248e-194">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="1248e-195">Reduzierte CPU-Auslastung des Produkts, wenn Microsoft-Produkte über Microsoft AutoUpdate aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="1248e-195">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="1248e-196">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-196">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="1248e-197">100.86.91</span><span class="sxs-lookup"><span data-stu-id="1248e-197">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="1248e-198">Um den vollständigsten Schutz für Ihre macOS-Geräte sicherzustellen und in Übereinstimmung mit Apple die Bereitstellung von systemeigenen MacOS-Sicherheitsupdates für Betriebssystemversionen zu beenden, die älter als [aktuell – 2] sind, werden MDATP für #A0 und -Updates unter macOS Sierra [10.12] nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1248e-198">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="1248e-199">MDATP für Mac-Updates und -Verbesserungen werden auf Geräten mit den Versionen Catalina [10.15], Mojave [10.14] und High Sierra [10.13] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1248e-199">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="1248e-200">Wenn Sie MDATP für Mac bereits auf Ihren Sierra [10.12]-Geräten bereitgestellt haben, aktualisieren Sie bitte auf die neueste macOS-Version, um risiken des Verlusts von Schutz zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="1248e-200">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="1248e-201">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-201">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="1248e-202">100.83.73</span><span class="sxs-lookup"><span data-stu-id="1248e-202">100.83.73</span></span>

- <span data-ttu-id="1248e-203">Weitere Steuerelemente für IT-Administratoren zur Verwaltung von Ausschlüssen, zur [Verwaltung](mac-preferences.md#threat-type-settings-merge-policy)von [Bedrohungstypeinstellungen](mac-preferences.md#exclusion-merge-policy)und nicht zulässigen [Bedrohungsaktionen hinzugefügt](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="1248e-203">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="1248e-204">Wenn der vollständige Festplattenzugriff auf dem Gerät nicht aktiviert ist, wird jetzt im Statusmenü eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1248e-204">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="1248e-205">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-205">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="1248e-206">100.82.60</span><span class="sxs-lookup"><span data-stu-id="1248e-206">100.82.60</span></span>

- <span data-ttu-id="1248e-207">Es wurde ein Problem behoben, bei dem das Produkt nach einem Definitionsupdate nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1248e-207">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="1248e-208">100.80.42</span><span class="sxs-lookup"><span data-stu-id="1248e-208">100.80.42</span></span>

- <span data-ttu-id="1248e-209">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-209">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="1248e-210">100.79.42</span><span class="sxs-lookup"><span data-stu-id="1248e-210">100.79.42</span></span>

- <span data-ttu-id="1248e-211">Es wurde ein Problem behoben, bei dem Microsoft Defender for Endpoint für Mac zeitautomatische Probleme verursachte.</span><span class="sxs-lookup"><span data-stu-id="1248e-211">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="1248e-212">Neue Option zum Befehlszeilenprogramm zum Testen der Konnektivität mit dem Back-End-Dienst hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1248e-212">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="1248e-213">Möglichkeit zum Anzeigen des vollständigen Bedrohungsverlaufs auf der Benutzeroberfläche hinzugefügt (kann über die Ansicht **Schutzverlauf zugegriffen** werden)</span><span class="sxs-lookup"><span data-stu-id="1248e-213">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="1248e-214">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-214">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="1248e-215">100.72.15</span><span class="sxs-lookup"><span data-stu-id="1248e-215">100.72.15</span></span>

- <span data-ttu-id="1248e-216">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-216">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="1248e-217">100.70.99</span><span class="sxs-lookup"><span data-stu-id="1248e-217">100.70.99</span></span>

- <span data-ttu-id="1248e-218">Es wurde ein Problem behoben, das sich auf die Fähigkeit einiger Benutzer aus wirkt, ein Upgrade auf macOS Catalina zu ermöglichen, wenn der Echtzeitschutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1248e-218">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="1248e-219">Dieses sporadische Problem wurde durch sperrende Dateien von Microsoft Defender for Endpoint innerhalb des Catalina-Upgradepakets verursacht, während sie auf Bedrohungen gescannt wurden, was zu Fehlern in der Upgradesequenz führte.</span><span class="sxs-lookup"><span data-stu-id="1248e-219">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="1248e-220">100.68.99</span><span class="sxs-lookup"><span data-stu-id="1248e-220">100.68.99</span></span>

- <span data-ttu-id="1248e-221">Die Möglichkeit zum Konfigurieren der Antivirenfunktionen für die Ausführung im [passiven Modus wurde hinzugefügt.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="1248e-221">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="1248e-222">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-222">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="1248e-223">100.65.28</span><span class="sxs-lookup"><span data-stu-id="1248e-223">100.65.28</span></span>

- <span data-ttu-id="1248e-224">Unterstützung für macOS Catalina hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="1248e-224">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="1248e-225">macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="1248e-225">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="1248e-226">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="1248e-226">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="1248e-227">In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.</span><span class="sxs-lookup"><span data-stu-id="1248e-227">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="1248e-228">Der Mechanismus für die Erteilung dieser Zustimmung hängt davon ab, wie Sie Microsoft Defender for Endpoint bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="1248e-228">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="1248e-229">Manuelle Bereitstellungen finden Sie in den aktualisierten Anweisungen im [Thema Manuelle](mac-install-manually.md#how-to-allow-full-disk-access) Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="1248e-229">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="1248e-230">Informationen zu verwalteten Bereitstellungen finden Sie in den aktualisierten Anweisungen in den [Themen JAMF-basierte](mac-install-with-jamf.md) Bereitstellung und [Microsoft Intune-basierte Bereitstellung.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="1248e-230">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="1248e-231">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="1248e-231">Performance improvements & bug fixes</span></span>
