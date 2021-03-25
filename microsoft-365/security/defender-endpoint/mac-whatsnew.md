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
ms.openlocfilehash: f1cd2221ab07caeab341447ebd19824d7476fb52
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187373"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="5058b-104">Neues in Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="5058b-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5058b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5058b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5058b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5058b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5058b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5058b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5058b-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="5058b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5058b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="5058b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="5058b-110">Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile.</span><span class="sxs-lookup"><span data-stu-id="5058b-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="5058b-111">Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die auf dieser [Seite aufgeführt sind.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5058b-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5058b-112">Die Unterstützung für macOS 10.13 (High Sierra) wird am 15. Februar 2021 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="5058b-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="5058b-113">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="5058b-113">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="5058b-114">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-114">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="5058b-115">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="5058b-115">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="5058b-116">Die alte Befehlszeilentoolsyntax ist mit dieser Version veraltet.</span><span class="sxs-lookup"><span data-stu-id="5058b-116">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="5058b-117">Informationen zur neuen Syntax finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5058b-117">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="5058b-118">Es wurde ein neuer Befehlszeilenschalter hinzugefügt, um die Netzwerkerweiterung zu deaktivieren: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="5058b-118">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="5058b-119">Dieser Befehl kann hilfreich sein, um Netzwerkprobleme zu beheben, die mit Microsoft Defender for Endpoint für Mac in Zusammenhang stehen könnten.</span><span class="sxs-lookup"><span data-stu-id="5058b-119">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="5058b-120">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-120">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="5058b-121">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="5058b-121">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="5058b-122">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-122">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="5058b-123">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="5058b-123">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="5058b-124">Verbesserte Zuverlässigkeit des Agents bei der Ausführung unter macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="5058b-124">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="5058b-125">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="5058b-125">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="5058b-126">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-126">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="5058b-127">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="5058b-127">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="5058b-128">Bedingungen wurden entfernt, als Microsoft Defender for Endpoint einen macOS 11 (Big Sur)-Fehler auslöste, der sich in einer Kernelpanik manifestierte.</span><span class="sxs-lookup"><span data-stu-id="5058b-128">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="5058b-129">Behebung eines Speicherverlusts in der Endpunktsicherheitssystemerweiterung bei der Ausführung auf mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="5058b-129">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="5058b-130">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-130">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="5058b-131">101.10.72</span><span class="sxs-lookup"><span data-stu-id="5058b-131">101.10.72</span></span>

- <span data-ttu-id="5058b-132">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-132">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="5058b-133">101.09.61</span><span class="sxs-lookup"><span data-stu-id="5058b-133">101.09.61</span></span>

- <span data-ttu-id="5058b-134">Neue verwaltete Einstellung zum Deaktivieren der Option [zum Senden von Feedback hinzugefügt](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="5058b-134">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="5058b-135">Das Statusmenüsymbol zeigt jetzt einen fehlerfreien Status an, wenn die Produkteinstellungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5058b-135">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="5058b-136">Zuvor wurde im Statusmenüsymbol ein Warnungs- oder Fehlerstatus angezeigt, obwohl die Produkteinstellungen vom Administrator verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="5058b-136">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="5058b-137">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-137">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="5058b-138">101.09.50</span><span class="sxs-lookup"><span data-stu-id="5058b-138">101.09.50</span></span>

- <span data-ttu-id="5058b-139">Diese Produktversion wurde unter macOS Big Sur 11 Beta 9 überprüft.</span><span class="sxs-lookup"><span data-stu-id="5058b-139">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="5058b-140">Die neue Syntax für `mdatp` das Befehlszeilentool ist jetzt die Standardsyntax.</span><span class="sxs-lookup"><span data-stu-id="5058b-140">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="5058b-141">Weitere Informationen zur neuen Syntax finden Sie unter [Ressourcen für Microsoft Defender for Endpoint für Mac.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="5058b-141">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="5058b-142">Die alte Befehlszeilentoolsyntax wird am **1. Januar 2021** aus dem Produkt entfernt.</span><span class="sxs-lookup"><span data-stu-id="5058b-142">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="5058b-143">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="5058b-143">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="5058b-144">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-144">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="5058b-145">101.09.49</span><span class="sxs-lookup"><span data-stu-id="5058b-145">101.09.49</span></span>

- <span data-ttu-id="5058b-146">Verbesserungen der Benutzeroberfläche zur Unterscheidung von Vom IT-Administrator verwalteten Ausschlüssen und vom lokalen Benutzer definierten Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="5058b-146">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="5058b-147">Verbesserte CPU-Auslastung bei Bedarfsscans</span><span class="sxs-lookup"><span data-stu-id="5058b-147">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="5058b-148">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-148">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="5058b-149">101.07.23</span><span class="sxs-lookup"><span data-stu-id="5058b-149">101.07.23</span></span>

- <span data-ttu-id="5058b-150">Neue Felder zur Ausgabe von hinzugefügt, um den Status des passiven Modus und die `mdatp --health` EDR-Gruppen-ID zu überprüfen</span><span class="sxs-lookup"><span data-stu-id="5058b-150">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="5058b-151">`mdatp --health` wird in einem `mdatp health` zukünftigen Produktupdate ersetzt.</span><span class="sxs-lookup"><span data-stu-id="5058b-151">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="5058b-152">Fehler behoben, bei dem die automatische Beispielübermittlung auf der Benutzeroberfläche nicht als verwaltet gekennzeichnet wurde</span><span class="sxs-lookup"><span data-stu-id="5058b-152">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="5058b-153">Neue Einstellungen zum Steuern der Aufbewahrung von Elementen im Antivirusscanverlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5058b-153">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="5058b-154">Sie können jetzt [die Anzahl der](mac-preferences.md#antivirus-scan-history-retention-in-days) Tage angeben, die Elemente im Überprüfungsverlauf beibehalten werden sollen, und die maximale Anzahl von Elementen im [Scanverlauf angeben.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="5058b-154">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="5058b-155">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-155">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="5058b-156">101.06.63</span><span class="sxs-lookup"><span data-stu-id="5058b-156">101.06.63</span></span>

- <span data-ttu-id="5058b-157">Es wurde eine Leistungsregression behoben, die in Version eingeführt `101.05.17` wurde.</span><span class="sxs-lookup"><span data-stu-id="5058b-157">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="5058b-158">Die Regression wurde mit dem Fix eingeführt, um die Kernelpaniken zu beseitigen, die einige Kunden beim Zugriff auf SMB-Freigaben beobachtet haben.</span><span class="sxs-lookup"><span data-stu-id="5058b-158">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="5058b-159">Wir haben diese Codeänderung wiederhergestellt und untersuchen alternative Möglichkeiten, um die Kernelpaniken zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="5058b-159">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="5058b-160">101.05.17</span><span class="sxs-lookup"><span data-stu-id="5058b-160">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5058b-161">Wir arbeiten an einer neuen und erweiterten Syntax für das `mdatp` Befehlszeilentool.</span><span class="sxs-lookup"><span data-stu-id="5058b-161">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="5058b-162">Die neue Syntax ist derzeit die Standardeinstellung in den Kanälen Insider Fast und Insider Slow Update.</span><span class="sxs-lookup"><span data-stu-id="5058b-162">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="5058b-163">Wir empfehlen Ihnen, sich mit dieser neuen Syntax vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="5058b-163">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="5058b-164">Wir werden die alte Syntax parallel zur neuen Syntax weiterhin unterstützen und in den kommenden Monaten mehr Kommunikation rund um den Veralteten Plan für die alte Syntax bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5058b-164">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="5058b-165">Es wurde eine Kernelpanik behoben, die manchmal beim Zugriff auf SMB-Dateifreigaben aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="5058b-165">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="5058b-166">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-166">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="5058b-167">101.05.16</span><span class="sxs-lookup"><span data-stu-id="5058b-167">101.05.16</span></span>

- <span data-ttu-id="5058b-168">Verbesserungen bei der Schnellscanlogik, um die Anzahl der gescannten Dateien erheblich zu reduzieren</span><span class="sxs-lookup"><span data-stu-id="5058b-168">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="5058b-169">Unterstützung [für die automatische Vervollständigung](mac-resources.md#how-to-enable-autocompletion) für das Befehlszeilentool hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="5058b-169">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="5058b-170">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-170">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="5058b-171">101.03.12</span><span class="sxs-lookup"><span data-stu-id="5058b-171">101.03.12</span></span>

- <span data-ttu-id="5058b-172">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-172">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="5058b-173">101.01.54</span><span class="sxs-lookup"><span data-stu-id="5058b-173">101.01.54</span></span>

- <span data-ttu-id="5058b-174">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="5058b-174">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="5058b-175">Verbesserungen bei der Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="5058b-175">Accessibility improvements</span></span>
- <span data-ttu-id="5058b-176">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-176">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="5058b-177">101.00.31</span><span class="sxs-lookup"><span data-stu-id="5058b-177">101.00.31</span></span>

- <span data-ttu-id="5058b-178">Verbesserte [Produkt-Onboarding-Erfahrung für Intune-Benutzer](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="5058b-178">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="5058b-179">[Antivirusausschlüsse unterstützen jetzt Platzhalter](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="5058b-179">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="5058b-180">Die Möglichkeit zum Auslösen von Antivirenscans aus dem kontextbezogenen MacOS-Menü wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5058b-180">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="5058b-181">Sie können nun mit der rechten Maustaste auf eine Datei oder einen Ordner im Finder klicken und **mit Microsoft Defender for Endpoint scannen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="5058b-181">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="5058b-182">In-Place-Produktabstufungen werden nun vom Installationsprogramm explizit nicht mehr zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5058b-182">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="5058b-183">Wenn Sie ein Downgrade benötigen, deinstallieren Sie zuerst die vorhandene Version, und konfigurieren Sie Ihr Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="5058b-183">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="5058b-184">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-184">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="5058b-185">100.90.27</span><span class="sxs-lookup"><span data-stu-id="5058b-185">100.90.27</span></span>

- <span data-ttu-id="5058b-186">Sie können jetzt [einen Updatekanal](mac-updates.md#set-the-channel-name) für Microsoft Defender for Endpoint für Mac festlegen, der sich vom systemweiten Updatekanal ab unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="5058b-186">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="5058b-187">Symbol für neues Produkt</span><span class="sxs-lookup"><span data-stu-id="5058b-187">New product icon</span></span>
- <span data-ttu-id="5058b-188">Weitere Verbesserungen bei der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="5058b-188">Other user experience improvements</span></span>
- <span data-ttu-id="5058b-189">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-189">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="5058b-190">100.86.92</span><span class="sxs-lookup"><span data-stu-id="5058b-190">100.86.92</span></span>

- <span data-ttu-id="5058b-191">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="5058b-191">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="5058b-192">Es wurde ein Problem behoben, bei dem das Produkt während der Deinstallation manchmal nicht alle Dateien `/Library/Application Support/Microsoft/Defender` unter bereinigen konnte.</span><span class="sxs-lookup"><span data-stu-id="5058b-192">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="5058b-193">Reduzierte CPU-Auslastung des Produkts, wenn Microsoft-Produkte über Microsoft AutoUpdate aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="5058b-193">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="5058b-194">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-194">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="5058b-195">100.86.91</span><span class="sxs-lookup"><span data-stu-id="5058b-195">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="5058b-196">Um den vollständigsten Schutz für Ihre macOS-Geräte sicherzustellen und in Übereinstimmung mit Apple die Bereitstellung von systemeigenen MacOS-Sicherheitsupdates für Betriebssystemversionen zu beenden, die älter als [aktuell – 2] sind, werden MDATP für #A0 und -Updates unter macOS Sierra [10.12] nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5058b-196">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="5058b-197">MDATP für Mac-Updates und -Verbesserungen werden auf Geräten mit den Versionen Catalina [10.15], Mojave [10.14] und High Sierra [10.13] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5058b-197">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="5058b-198">Wenn Sie MDATP für Mac bereits auf Ihren Sierra [10.12]-Geräten bereitgestellt haben, aktualisieren Sie bitte auf die neueste macOS-Version, um risiken des Verlusts von Schutz zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5058b-198">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="5058b-199">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-199">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="5058b-200">100.83.73</span><span class="sxs-lookup"><span data-stu-id="5058b-200">100.83.73</span></span>

- <span data-ttu-id="5058b-201">Weitere Steuerelemente für IT-Administratoren zur Verwaltung von Ausschlüssen, zur [Verwaltung](mac-preferences.md#threat-type-settings-merge-policy)von [Bedrohungstypeinstellungen](mac-preferences.md#exclusion-merge-policy)und nicht zulässigen [Bedrohungsaktionen hinzugefügt](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="5058b-201">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="5058b-202">Wenn der vollständige Festplattenzugriff auf dem Gerät nicht aktiviert ist, wird jetzt im Statusmenü eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5058b-202">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="5058b-203">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-203">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="5058b-204">100.82.60</span><span class="sxs-lookup"><span data-stu-id="5058b-204">100.82.60</span></span>

- <span data-ttu-id="5058b-205">Es wurde ein Problem behoben, bei dem das Produkt nach einem Definitionsupdate nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5058b-205">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="5058b-206">100.80.42</span><span class="sxs-lookup"><span data-stu-id="5058b-206">100.80.42</span></span>

- <span data-ttu-id="5058b-207">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-207">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="5058b-208">100.79.42</span><span class="sxs-lookup"><span data-stu-id="5058b-208">100.79.42</span></span>

- <span data-ttu-id="5058b-209">Es wurde ein Problem behoben, bei dem Microsoft Defender for Endpoint für Mac zeitautomatische Probleme verursachte.</span><span class="sxs-lookup"><span data-stu-id="5058b-209">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="5058b-210">Neue Option zum Befehlszeilenprogramm zum Testen der Konnektivität mit dem Back-End-Dienst hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="5058b-210">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="5058b-211">Möglichkeit zum Anzeigen des vollständigen Bedrohungsverlaufs auf der Benutzeroberfläche hinzugefügt (kann über die Ansicht **Schutzverlauf zugegriffen** werden)</span><span class="sxs-lookup"><span data-stu-id="5058b-211">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="5058b-212">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-212">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="5058b-213">100.72.15</span><span class="sxs-lookup"><span data-stu-id="5058b-213">100.72.15</span></span>

- <span data-ttu-id="5058b-214">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-214">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="5058b-215">100.70.99</span><span class="sxs-lookup"><span data-stu-id="5058b-215">100.70.99</span></span>

- <span data-ttu-id="5058b-216">Es wurde ein Problem behoben, das sich auf die Fähigkeit einiger Benutzer aus wirkt, ein Upgrade auf macOS Catalina zu ermöglichen, wenn der Echtzeitschutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5058b-216">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="5058b-217">Dieses sporadische Problem wurde durch sperrende Dateien von Microsoft Defender for Endpoint innerhalb des Catalina-Upgradepakets verursacht, während sie auf Bedrohungen gescannt wurden, was zu Fehlern in der Upgradesequenz führte.</span><span class="sxs-lookup"><span data-stu-id="5058b-217">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="5058b-218">100.68.99</span><span class="sxs-lookup"><span data-stu-id="5058b-218">100.68.99</span></span>

- <span data-ttu-id="5058b-219">Die Möglichkeit zum Konfigurieren der Antivirenfunktionen für die Ausführung im [passiven Modus wurde hinzugefügt.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="5058b-219">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="5058b-220">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-220">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="5058b-221">100.65.28</span><span class="sxs-lookup"><span data-stu-id="5058b-221">100.65.28</span></span>

- <span data-ttu-id="5058b-222">Unterstützung für macOS Catalina hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="5058b-222">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="5058b-223">macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="5058b-223">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="5058b-224">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="5058b-224">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="5058b-225">In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.</span><span class="sxs-lookup"><span data-stu-id="5058b-225">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="5058b-226">Der Mechanismus für die Erteilung dieser Zustimmung hängt davon ab, wie Sie Microsoft Defender for Endpoint bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="5058b-226">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="5058b-227">Manuelle Bereitstellungen finden Sie in den aktualisierten Anweisungen im [Thema Manuelle](mac-install-manually.md#how-to-allow-full-disk-access) Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5058b-227">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="5058b-228">Informationen zu verwalteten Bereitstellungen finden Sie in den aktualisierten Anweisungen in den [Themen JAMF-basierte](mac-install-with-jamf.md) Bereitstellung und [Microsoft Intune-basierte Bereitstellung.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="5058b-228">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="5058b-229">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5058b-229">Performance improvements & bug fixes</span></span>
