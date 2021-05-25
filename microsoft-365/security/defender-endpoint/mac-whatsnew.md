---
title: Neues in Microsoft Defender for Endpoint auf Mac
description: Erfahren Sie mehr über die wichtigsten Änderungen für frühere Versionen von Microsoft Defender for Endpoint auf Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, whatsnew
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
ms.openlocfilehash: d01e1d847a8932d95e645a89eff15cf0793491e5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651272"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="fab53-104">Neues in Microsoft Defender for Endpoint auf Mac</span><span class="sxs-lookup"><span data-stu-id="fab53-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fab53-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fab53-105">**Applies to:**</span></span>
- [<span data-ttu-id="fab53-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fab53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fab53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fab53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fab53-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="fab53-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fab53-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="fab53-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="fab53-110">Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile.</span><span class="sxs-lookup"><span data-stu-id="fab53-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="fab53-111">Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die auf dieser [Seite aufgeführt sind.](mac-sysext-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fab53-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="fab53-112">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-112">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="fab53-113">Ab dieser Version werden Bedrohungen, die während der überprüfungen bei Bedarf erkannt werden, die über den Befehlszeilenclient ausgelöst werden, automatisch behoben.</span><span class="sxs-lookup"><span data-stu-id="fab53-113">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="fab53-114">Bedrohungen, die bei Scans erkannt werden, die über die Benutzeroberfläche ausgelöst werden, erfordern weiterhin manuelle Aktionen.</span><span class="sxs-lookup"><span data-stu-id="fab53-114">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="fab53-115">`mdatp diagnostic real-time-protection-statistics` unterstützt jetzt zwei zusätzliche Switches:</span><span class="sxs-lookup"><span data-stu-id="fab53-115">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="fab53-116">`--sort`: sortiert die Ausgabe absteigend nach der Gesamtzahl der gescannten Dateien</span><span class="sxs-lookup"><span data-stu-id="fab53-116">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="fab53-117">`--top N`: zeigt die obersten N-Ergebnisse an (funktioniert nur, wenn `--sort` auch angegeben ist)</span><span class="sxs-lookup"><span data-stu-id="fab53-117">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="fab53-118">Leistungsverbesserungen (insbesondere für die Verwendung von YARN) & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-118">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="fab53-119">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-119">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="fab53-120">Fix, um den Ablauf des Apple-Zertifikats für macOS Catalina und früher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fab53-120">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="fab53-121">Mit diesem Fix wird die & (Vulnerability Management, TVM) von Bedrohungen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="fab53-121">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="fab53-122">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-122">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="fab53-123">Microsoft Defender for Endpoint auf macOS ist jetzt in der Vorschau für Us Government-Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fab53-123">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="fab53-124">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="fab53-124">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="fab53-125">Leistungsverbesserungen (insbesondere für die Situation, in der die & verwendet wird) & Fehlerbehebungen.</span><span class="sxs-lookup"><span data-stu-id="fab53-125">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="fab53-126">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-126">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="fab53-127">Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="fab53-127">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="fab53-128">Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="fab53-128">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="fab53-129">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-129">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="fab53-130">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-130">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="fab53-131">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-131">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="fab53-132">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-132">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="fab53-133">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-133">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="fab53-134">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-134">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="fab53-135">Die alte Befehlszeilentoolsyntax ist mit dieser Version veraltet.</span><span class="sxs-lookup"><span data-stu-id="fab53-135">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="fab53-136">Informationen zur neuen Syntax finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="fab53-136">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="fab53-137">Es wurde ein neuer Befehlszeilenschalter hinzugefügt, um die Netzwerkerweiterung zu deaktivieren: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="fab53-137">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="fab53-138">Dieser Befehl kann hilfreich sein, um Netzwerkprobleme zu beheben, die mit Microsoft Defender for Endpoint auf Dem Mac in Zusammenhang stehen könnten.</span><span class="sxs-lookup"><span data-stu-id="fab53-138">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="fab53-139">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-139">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="fab53-140">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-140">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="fab53-141">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-141">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="fab53-142">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-142">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="fab53-143">Verbesserte Zuverlässigkeit des Agents bei der Ausführung unter macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="fab53-143">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="fab53-144">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="fab53-144">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="fab53-145">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-145">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="fab53-146">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="fab53-146">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="fab53-147">Bedingungen wurden entfernt, als Microsoft Defender for Endpoint einen macOS 11 (Big Sur)-Fehler auslöste, der sich in einer Kernelpanik manifestierte.</span><span class="sxs-lookup"><span data-stu-id="fab53-147">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="fab53-148">Behebung eines Speicherverlusts in der Endpunktsicherheitssystemerweiterung bei der Ausführung auf mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="fab53-148">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="fab53-149">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-149">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="fab53-150">101.10.72</span><span class="sxs-lookup"><span data-stu-id="fab53-150">101.10.72</span></span>

- <span data-ttu-id="fab53-151">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-151">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="fab53-152">101.09.61</span><span class="sxs-lookup"><span data-stu-id="fab53-152">101.09.61</span></span>

- <span data-ttu-id="fab53-153">Neue verwaltete Einstellung zum Deaktivieren der Option [zum Senden von Feedback hinzugefügt](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="fab53-153">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="fab53-154">Das Statusmenüsymbol zeigt jetzt einen fehlerfreien Status an, wenn die Produkteinstellungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fab53-154">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="fab53-155">Zuvor wurde im Statusmenüsymbol ein Warnungs- oder Fehlerstatus angezeigt, obwohl die Produkteinstellungen vom Administrator verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="fab53-155">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="fab53-156">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-156">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="fab53-157">101.09.50</span><span class="sxs-lookup"><span data-stu-id="fab53-157">101.09.50</span></span>

- <span data-ttu-id="fab53-158">Diese Produktversion wurde unter macOS Big Sur 11 Beta 9 überprüft.</span><span class="sxs-lookup"><span data-stu-id="fab53-158">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="fab53-159">Die neue Syntax für `mdatp` das Befehlszeilentool ist jetzt die Standardsyntax.</span><span class="sxs-lookup"><span data-stu-id="fab53-159">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="fab53-160">Weitere Informationen zur neuen Syntax finden Sie unter [Ressourcen für Microsoft Defender for Endpoint auf macOS.](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="fab53-160">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="fab53-161">Die alte Befehlszeilentoolsyntax wird am **1. Januar 2021** aus dem Produkt entfernt.</span><span class="sxs-lookup"><span data-stu-id="fab53-161">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="fab53-162">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="fab53-162">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="fab53-163">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-163">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="fab53-164">101.09.49</span><span class="sxs-lookup"><span data-stu-id="fab53-164">101.09.49</span></span>

- <span data-ttu-id="fab53-165">Verbesserungen der Benutzeroberfläche zur Unterscheidung von Vom IT-Administrator verwalteten Ausschlüssen und vom lokalen Benutzer definierten Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="fab53-165">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="fab53-166">Verbesserte CPU-Auslastung bei Bedarfsscans</span><span class="sxs-lookup"><span data-stu-id="fab53-166">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="fab53-167">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-167">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="fab53-168">101.07.23</span><span class="sxs-lookup"><span data-stu-id="fab53-168">101.07.23</span></span>

- <span data-ttu-id="fab53-169">Neue Felder zur Ausgabe von hinzugefügt, um den Status des passiven Modus und die EDR `mdatp --health` zu überprüfen</span><span class="sxs-lookup"><span data-stu-id="fab53-169">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="fab53-170">`mdatp --health` wird in einem `mdatp health` zukünftigen Produktupdate ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fab53-170">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="fab53-171">Fehler behoben, bei dem die automatische Beispielübermittlung auf der Benutzeroberfläche nicht als verwaltet gekennzeichnet wurde</span><span class="sxs-lookup"><span data-stu-id="fab53-171">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="fab53-172">Neue Einstellungen zum Steuern der Aufbewahrung von Elementen im Antivirusscanverlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fab53-172">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="fab53-173">Sie können jetzt [die Anzahl der](mac-preferences.md#antivirus-scan-history-retention-in-days) Tage angeben, die Elemente im Überprüfungsverlauf beibehalten werden sollen, und die maximale Anzahl von Elementen im [Scanverlauf angeben.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="fab53-173">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="fab53-174">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-174">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="fab53-175">101.06.63</span><span class="sxs-lookup"><span data-stu-id="fab53-175">101.06.63</span></span>

- <span data-ttu-id="fab53-176">Es wurde eine Leistungsregression behoben, die in Version eingeführt `101.05.17` wurde.</span><span class="sxs-lookup"><span data-stu-id="fab53-176">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="fab53-177">Die Regression wurde mit dem Fix eingeführt, um die Kernelpaniken zu beseitigen, die einige Kunden beim Zugriff auf SMB-Freigaben beobachtet haben.</span><span class="sxs-lookup"><span data-stu-id="fab53-177">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="fab53-178">Wir haben diese Codeänderung wiederhergestellt und untersuchen alternative Möglichkeiten, um die Kernelpaniken zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="fab53-178">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="fab53-179">101.05.17</span><span class="sxs-lookup"><span data-stu-id="fab53-179">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fab53-180">Wir arbeiten an einer neuen und erweiterten Syntax für das `mdatp` Befehlszeilentool.</span><span class="sxs-lookup"><span data-stu-id="fab53-180">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="fab53-181">Die neue Syntax ist derzeit die Standardeinstellung in den Kanälen Insider Fast und Insider Slow Update.</span><span class="sxs-lookup"><span data-stu-id="fab53-181">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="fab53-182">Wir empfehlen Ihnen, sich mit dieser neuen Syntax vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="fab53-182">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="fab53-183">Wir werden die alte Syntax parallel zur neuen Syntax weiterhin unterstützen und in den kommenden Monaten mehr Kommunikation rund um den Veralteten Plan für die alte Syntax bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fab53-183">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="fab53-184">Es wurde eine Kernelpanik behoben, die manchmal beim Zugriff auf SMB-Dateifreigaben aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="fab53-184">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="fab53-185">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-185">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="fab53-186">101.05.16</span><span class="sxs-lookup"><span data-stu-id="fab53-186">101.05.16</span></span>

- <span data-ttu-id="fab53-187">Verbesserungen bei der Schnellscanlogik, um die Anzahl der gescannten Dateien erheblich zu reduzieren</span><span class="sxs-lookup"><span data-stu-id="fab53-187">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="fab53-188">Unterstützung [für die automatische Vervollständigung](mac-resources.md#how-to-enable-autocompletion) für das Befehlszeilentool hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="fab53-188">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="fab53-189">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-189">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="fab53-190">101.03.12</span><span class="sxs-lookup"><span data-stu-id="fab53-190">101.03.12</span></span>

- <span data-ttu-id="fab53-191">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-191">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="fab53-192">101.01.54</span><span class="sxs-lookup"><span data-stu-id="fab53-192">101.01.54</span></span>

- <span data-ttu-id="fab53-193">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="fab53-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="fab53-194">Verbesserungen bei der Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="fab53-194">Accessibility improvements</span></span>
- <span data-ttu-id="fab53-195">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-195">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="fab53-196">101.00.31</span><span class="sxs-lookup"><span data-stu-id="fab53-196">101.00.31</span></span>

- <span data-ttu-id="fab53-197">Verbesserte [Produkt-Onboarding-Erfahrung für Intune-Benutzer](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="fab53-197">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="fab53-198">[Antivirusausschlüsse unterstützen jetzt Platzhalter](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="fab53-198">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="fab53-199">Die Möglichkeit zum Auslösen von Antivirenscans aus dem kontextbezogenen MacOS-Menü wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fab53-199">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="fab53-200">Sie können nun mit der rechten Maustaste auf eine Datei oder einen Ordner im Finder klicken und **mit Microsoft Defender for Endpoint scannen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="fab53-200">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="fab53-201">In-Place-Produktabstufungen werden nun vom Installationsprogramm explizit nicht mehr zugelassen.</span><span class="sxs-lookup"><span data-stu-id="fab53-201">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="fab53-202">Wenn Sie ein Downgrade benötigen, deinstallieren Sie zuerst die vorhandene Version, und konfigurieren Sie Ihr Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="fab53-202">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="fab53-203">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-203">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="fab53-204">100.90.27</span><span class="sxs-lookup"><span data-stu-id="fab53-204">100.90.27</span></span>

- <span data-ttu-id="fab53-205">Sie können jetzt [einen Updatekanal](mac-updates.md#set-the-channel-name) für Microsoft Defender for Endpoint unter macOS festlegen, der sich vom systemweiten Updatekanal ab unterscheiden kann.</span><span class="sxs-lookup"><span data-stu-id="fab53-205">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="fab53-206">Symbol für neues Produkt</span><span class="sxs-lookup"><span data-stu-id="fab53-206">New product icon</span></span>
- <span data-ttu-id="fab53-207">Weitere Verbesserungen bei der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="fab53-207">Other user experience improvements</span></span>
- <span data-ttu-id="fab53-208">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-208">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="fab53-209">100.86.92</span><span class="sxs-lookup"><span data-stu-id="fab53-209">100.86.92</span></span>

- <span data-ttu-id="fab53-210">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="fab53-210">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="fab53-211">Es wurde ein Problem behoben, bei dem das Produkt während der Deinstallation manchmal nicht alle Dateien `/Library/Application Support/Microsoft/Defender` unter bereinigen konnte.</span><span class="sxs-lookup"><span data-stu-id="fab53-211">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="fab53-212">Reduzierte CPU-Auslastung des Produkts, wenn Microsoft-Produkte über Microsoft AutoUpdate aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="fab53-212">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="fab53-213">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-213">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="fab53-214">100.86.91</span><span class="sxs-lookup"><span data-stu-id="fab53-214">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="fab53-215">Um den vollständigsten Schutz für Ihre macOS-Geräte sicherzustellen und in Übereinstimmung mit Apple die Bereitstellung von systemeigenen macOS-Sicherheitsupdates für Betriebssystemversionen zu beenden, die älter als [aktuell – 2] sind, werden MDATP für #A0 und -Updates unter macOS Sierra [10.12] nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fab53-215">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="fab53-216">MDATP Für #A0 und -Verbesserungen werden Geräte mit den Versionen Catalina [10.15], Mojave [10.14] und High Sierra [10.13] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fab53-216">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="fab53-217">Wenn Sie bereits MDATP für Mac auf Ihren Sierra [10.12]-Geräten bereitgestellt haben, aktualisieren Sie bitte auf die neueste macOS-Version, um risiken des Verlusts von Schutz zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="fab53-217">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="fab53-218">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-218">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="fab53-219">100.83.73</span><span class="sxs-lookup"><span data-stu-id="fab53-219">100.83.73</span></span>

- <span data-ttu-id="fab53-220">Weitere Steuerelemente für IT-Administratoren zur Verwaltung von Ausschlüssen, zur [Verwaltung](mac-preferences.md#threat-type-settings-merge-policy)von [Bedrohungstypeinstellungen](mac-preferences.md#exclusion-merge-policy)und nicht zulässigen [Bedrohungsaktionen hinzugefügt](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="fab53-220">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="fab53-221">Wenn der vollständige Festplattenzugriff auf dem Gerät nicht aktiviert ist, wird jetzt im Statusmenü eine Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fab53-221">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="fab53-222">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-222">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="fab53-223">100.82.60</span><span class="sxs-lookup"><span data-stu-id="fab53-223">100.82.60</span></span>

- <span data-ttu-id="fab53-224">Es wurde ein Problem behoben, bei dem das Produkt nach einem Definitionsupdate nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fab53-224">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="fab53-225">100.80.42</span><span class="sxs-lookup"><span data-stu-id="fab53-225">100.80.42</span></span>

- <span data-ttu-id="fab53-226">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-226">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="fab53-227">100.79.42</span><span class="sxs-lookup"><span data-stu-id="fab53-227">100.79.42</span></span>

- <span data-ttu-id="fab53-228">Es wurde ein Problem behoben, bei dem Microsoft Defender for Endpoint auf Dem Mac manchmal mit dem Zeitcomputer ins Spiel kam.</span><span class="sxs-lookup"><span data-stu-id="fab53-228">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="fab53-229">Neue Option zum Befehlszeilenprogramm zum Testen der Konnektivität mit dem Back-End-Dienst hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="fab53-229">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="fab53-230">Möglichkeit zum Anzeigen des vollständigen Bedrohungsverlaufs auf der Benutzeroberfläche hinzugefügt (kann über die Ansicht **Schutzverlauf zugegriffen** werden)</span><span class="sxs-lookup"><span data-stu-id="fab53-230">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="fab53-231">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-231">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="fab53-232">100.72.15</span><span class="sxs-lookup"><span data-stu-id="fab53-232">100.72.15</span></span>

- <span data-ttu-id="fab53-233">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-233">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="fab53-234">100.70.99</span><span class="sxs-lookup"><span data-stu-id="fab53-234">100.70.99</span></span>

- <span data-ttu-id="fab53-235">Es wurde ein Problem behoben, das sich auf die Fähigkeit einiger Benutzer aus wirkt, ein Upgrade auf macOS Catalina zu ermöglichen, wenn der Echtzeitschutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fab53-235">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="fab53-236">Dieses sporadische Problem wurde durch sperrende Dateien von Microsoft Defender for Endpoint innerhalb des Catalina-Upgradepakets verursacht, während sie auf Bedrohungen gescannt wurden, was zu Fehlern in der Upgradesequenz führte.</span><span class="sxs-lookup"><span data-stu-id="fab53-236">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="fab53-237">100.68.99</span><span class="sxs-lookup"><span data-stu-id="fab53-237">100.68.99</span></span>

- <span data-ttu-id="fab53-238">Die Möglichkeit zum Konfigurieren der Antivirenfunktionen für die Ausführung im [passiven Modus wurde hinzugefügt.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="fab53-238">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="fab53-239">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-239">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="fab53-240">100.65.28</span><span class="sxs-lookup"><span data-stu-id="fab53-240">100.65.28</span></span>

- <span data-ttu-id="fab53-241">Unterstützung für macOS Catalina hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="fab53-241">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="fab53-242">macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="fab53-242">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="fab53-243">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="fab53-243">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="fab53-244">In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.</span><span class="sxs-lookup"><span data-stu-id="fab53-244">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="fab53-245">Der Mechanismus für die Erteilung dieser Zustimmung hängt davon ab, wie Sie Microsoft Defender for Endpoint bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="fab53-245">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="fab53-246">Manuelle Bereitstellungen finden Sie in den aktualisierten Anweisungen im [Thema Manuelle](mac-install-manually.md#how-to-allow-full-disk-access) Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="fab53-246">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="fab53-247">Informationen zu verwalteten Bereitstellungen finden Sie in den aktualisierten Anweisungen in den Themen [JAMF-basierte](mac-install-with-jamf.md) Bereitstellung [und Microsoft Intune Bereitstellung.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="fab53-247">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="fab53-248">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="fab53-248">Performance improvements & bug fixes</span></span>
