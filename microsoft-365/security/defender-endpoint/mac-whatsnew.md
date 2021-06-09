---
title: Neuigkeiten in Microsoft Defender für Endpunkt auf dem Mac
description: Erfahren Sie mehr über die wichtigsten Änderungen für frühere Versionen von Microsoft Defender für Endpunkt auf dem Mac.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Installation, macos, whatsnew
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
ms.openlocfilehash: 6348d688103c51176fbed36c923a660c77a2258d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842782"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="2f539-104">Neuigkeiten in Microsoft Defender für Endpunkt auf dem Mac</span><span class="sxs-lookup"><span data-stu-id="2f539-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2f539-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2f539-105">**Applies to:**</span></span>
- [<span data-ttu-id="2f539-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2f539-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2f539-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f539-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2f539-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2f539-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2f539-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2f539-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="2f539-110">Unter macOS 11 (Big Sur) erfordert Microsoft Defender für Endpunkt zusätzliche Konfigurationsprofile.</span><span class="sxs-lookup"><span data-stu-id="2f539-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="2f539-111">Wenn Sie bereits ein Kundenupdate von früheren Versionen von macOS durchführen, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die auf [dieser Seite](mac-sysext-policies.md)aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2f539-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="2f539-112">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-112">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="2f539-113">Ab dieser Version werden Bedrohungen, die während von Bedarfs-Antivirusscans erkannt werden, die über den Befehlszeilenclient ausgelöst werden, automatisch behoben.</span><span class="sxs-lookup"><span data-stu-id="2f539-113">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="2f539-114">Bedrohungen, die während überprüfungen erkannt werden, die über die Benutzeroberfläche ausgelöst werden, erfordern weiterhin manuelle Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="2f539-114">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="2f539-115">`mdatp diagnostic real-time-protection-statistics` Unterstützt jetzt zwei zusätzliche Switches:</span><span class="sxs-lookup"><span data-stu-id="2f539-115">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="2f539-116">`--sort`: sortiert die Ausgabe absteigend nach der Gesamtzahl der gescannten Dateien.</span><span class="sxs-lookup"><span data-stu-id="2f539-116">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="2f539-117">`--top N`: zeigt die obersten N-Ergebnisse an (funktioniert nur, wenn `--sort` auch angegeben)</span><span class="sxs-lookup"><span data-stu-id="2f539-117">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="2f539-118">Leistungsverbesserungen (insbesondere bei Verwendung von YARN) & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-118">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="2f539-119">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-119">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="2f539-120">Behebung, um den Ablauf des Apple-Zertifikats für macOS- und frühere Versionen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="2f539-120">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="2f539-121">Dieser Fix stellt die Funktionen von Threat & Vulnerability Management (TVM) wieder her.</span><span class="sxs-lookup"><span data-stu-id="2f539-121">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="2f539-122">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-122">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="2f539-123">Microsoft Defender für Endpunkt unter macOS ist jetzt in der Vorschau für Us Government-Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f539-123">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="2f539-124">Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt für US Government-Kunden.](gov.md)</span><span class="sxs-lookup"><span data-stu-id="2f539-124">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="2f539-125">Leistungsverbesserungen (speziell für die Situation, in der die XCode Simulator-App verwendet wird) & Fehlerbehebungen.</span><span class="sxs-lookup"><span data-stu-id="2f539-125">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="2f539-126">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-126">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="2f539-127">Dem Befehlszeilentool wurde eine neue Option zum Anzeigen von Informationen zum letzten On-Demand-Scan hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2f539-127">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="2f539-128">Um Informationen zum letzten On-Demand-Scan anzuzeigen, führen Sie `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="2f539-128">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="2f539-129">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-129">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="2f539-130">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-130">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="2f539-131">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-131">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="2f539-132">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-132">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="2f539-133">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-133">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="2f539-134">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-134">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="2f539-135">Die syntax des alten Befehlszeilentools ist mit dieser Version veraltet.</span><span class="sxs-lookup"><span data-stu-id="2f539-135">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="2f539-136">Informationen zur neuen Syntax finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="2f539-136">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="2f539-137">Es wurde ein neuer Befehlszeilenschalter hinzugefügt, um die Netzwerkerweiterung zu deaktivieren: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="2f539-137">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="2f539-138">Dieser Befehl kann hilfreich sein, um Netzwerkprobleme zu beheben, die im Zusammenhang mit Microsoft Defender für Endpunkt auf dem Mac stehen könnten.</span><span class="sxs-lookup"><span data-stu-id="2f539-138">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="2f539-139">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-139">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="2f539-140">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-140">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="2f539-141">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-141">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="2f539-142">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-142">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="2f539-143">Verbesserte Zuverlässigkeit des Agents bei der Ausführung unter macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="2f539-143">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="2f539-144">Ein neuer Befehlszeilenschalter ( `--ignore-exclusions` ) wurde hinzugefügt, um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="2f539-144">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="2f539-145">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-145">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="2f539-146">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="2f539-146">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="2f539-147">Bedingungen entfernt, bei denen Microsoft Defender für Endpunkt einen MacOS 11(Big Sur)-Fehler auslöste, der sich in einer Kernel-Panze manifestiert</span><span class="sxs-lookup"><span data-stu-id="2f539-147">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="2f539-148">Es wurde ein Speicherverlust in der Endpoint Security-Systemerweiterung behoben, wenn sie auf Mac 11 (Big Sur) ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2f539-148">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="2f539-149">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-149">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="2f539-150">101.10.72</span><span class="sxs-lookup"><span data-stu-id="2f539-150">101.10.72</span></span>

- <span data-ttu-id="2f539-151">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-151">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="2f539-152">101.09.61</span><span class="sxs-lookup"><span data-stu-id="2f539-152">101.09.61</span></span>

- <span data-ttu-id="2f539-153">Neue verwaltete Einstellung zum [Deaktivieren der Option zum Senden](mac-preferences.md#show--hide-option-to-send-feedback) von Feedback hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="2f539-153">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="2f539-154">Das Statusmenüsymbol zeigt jetzt einen fehlerfreien Status an, wenn die Produkteinstellungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2f539-154">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="2f539-155">Zuvor wurde auf dem Statusmenüsymbol ein Warnungs- oder Fehlerstatus angezeigt, obwohl die Produkteinstellungen vom Administrator verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="2f539-155">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="2f539-156">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-156">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="2f539-157">101.09.50</span><span class="sxs-lookup"><span data-stu-id="2f539-157">101.09.50</span></span>

- <span data-ttu-id="2f539-158">Diese Produktversion wurde unter macOS Big Sur 11 Beta 9 überprüft.</span><span class="sxs-lookup"><span data-stu-id="2f539-158">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="2f539-159">Die neue Syntax für das `mdatp` Befehlszeilentool ist jetzt die Standardsyntax.</span><span class="sxs-lookup"><span data-stu-id="2f539-159">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="2f539-160">Weitere Informationen zur neuen Syntax finden Sie unter [Ressourcen für Microsoft Defender für Endpunkt unter macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="2f539-160">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="2f539-161">Die alte Befehlszeilentoolsyntax wird am **1. Januar 2021** aus dem Produkt entfernt.</span><span class="sxs-lookup"><span data-stu-id="2f539-161">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="2f539-162">Erweitert `mdatp diagnostic create` mit einem neuen Parameter ( ), der das Speichern der `--path [directory]` Diagnoseprotokolle in einem anderen Verzeichnis ermöglicht</span><span class="sxs-lookup"><span data-stu-id="2f539-162">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="2f539-163">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-163">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="2f539-164">101.09.49</span><span class="sxs-lookup"><span data-stu-id="2f539-164">101.09.49</span></span>

- <span data-ttu-id="2f539-165">Verbesserungen der Benutzeroberfläche zur Unterscheidung von Ausschlüssen, die vom IT-Administrator verwaltet werden, und Ausschlüssen, die vom lokalen Benutzer definiert sind</span><span class="sxs-lookup"><span data-stu-id="2f539-165">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="2f539-166">Verbesserte CPU-Auslastung bei Bedarfsscans</span><span class="sxs-lookup"><span data-stu-id="2f539-166">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="2f539-167">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-167">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="2f539-168">101.07.23</span><span class="sxs-lookup"><span data-stu-id="2f539-168">101.07.23</span></span>

- <span data-ttu-id="2f539-169">Neue Felder zur Ausgabe zur `mdatp --health` Überprüfung des Status des passiven Modus und der EDR Gruppen-ID hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="2f539-169">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="2f539-170">`mdatp --health` wird `mdatp health` in einem zukünftigen Produktupdate ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2f539-170">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="2f539-171">Ein Fehler wurde behoben, bei dem die automatische Beispielübermittlung auf der Benutzeroberfläche nicht als verwaltet gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="2f539-171">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="2f539-172">Neue Einstellungen zum Steuern der Aufbewahrung von Elementen im Antivirusscanverlauf hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2f539-172">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="2f539-173">Sie können jetzt [die Anzahl der Tage angeben, die Elemente im Scanverlauf aufbewahrt](mac-preferences.md#antivirus-scan-history-retention-in-days) werden sollen, und die maximale Anzahl von Elementen im [Scanverlauf angeben.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="2f539-173">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="2f539-174">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-174">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="2f539-175">101.06.63</span><span class="sxs-lookup"><span data-stu-id="2f539-175">101.06.63</span></span>

- <span data-ttu-id="2f539-176">Es wurde eine in Version eingeführte Leistungsregression `101.05.17` behoben.</span><span class="sxs-lookup"><span data-stu-id="2f539-176">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="2f539-177">Die Regression wurde mit dem Fix eingeführt, um die Kernel-Pannen zu beseitigen, die einige Kunden beim Zugriff auf SMB-Freigaben beobachtet haben.</span><span class="sxs-lookup"><span data-stu-id="2f539-177">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="2f539-178">Wir haben diese Codeänderung rückgängig gemacht und untersuchen alternative Möglichkeiten, die Kernel-Pannen zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="2f539-178">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="2f539-179">101.05.17</span><span class="sxs-lookup"><span data-stu-id="2f539-179">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f539-180">Wir arbeiten an einer neuen und erweiterten Syntax für das `mdatp` Befehlszeilentool.</span><span class="sxs-lookup"><span data-stu-id="2f539-180">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="2f539-181">Die neue Syntax ist derzeit die Standardeinstellung in den Updatekanälen "Insider Fast" und "Insider Slow".</span><span class="sxs-lookup"><span data-stu-id="2f539-181">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="2f539-182">Wir empfehlen Ihnen, sich mit dieser neuen Syntax zu verblassen.</span><span class="sxs-lookup"><span data-stu-id="2f539-182">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="2f539-183">Wir werden die alte Syntax weiterhin parallel zur neuen Syntax unterstützen und in den kommenden Monaten mehr Kommunikation über den Veraltetsplan für die alte Syntax bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2f539-183">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="2f539-184">Eine Kernel-Pannenreaktion wurde behoben, die manchmal beim Zugriff auf SMB-Dateifreigaben aufgetreten ist</span><span class="sxs-lookup"><span data-stu-id="2f539-184">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="2f539-185">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-185">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="2f539-186">101.05.16</span><span class="sxs-lookup"><span data-stu-id="2f539-186">101.05.16</span></span>

- <span data-ttu-id="2f539-187">Verbesserungen an der Schnellscanlogik, um die Anzahl der gescannten Dateien erheblich zu reduzieren</span><span class="sxs-lookup"><span data-stu-id="2f539-187">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="2f539-188">Unterstützung der [automatischen Kompletion](mac-resources.md#how-to-enable-autocompletion) für das Befehlszeilentool hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="2f539-188">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="2f539-189">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-189">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="2f539-190">101.03.12</span><span class="sxs-lookup"><span data-stu-id="2f539-190">101.03.12</span></span>

- <span data-ttu-id="2f539-191">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-191">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="2f539-192">101.01.54</span><span class="sxs-lookup"><span data-stu-id="2f539-192">101.01.54</span></span>

- <span data-ttu-id="2f539-193">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="2f539-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="2f539-194">Verbesserungen bei der Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="2f539-194">Accessibility improvements</span></span>
- <span data-ttu-id="2f539-195">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-195">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="2f539-196">101.00.31</span><span class="sxs-lookup"><span data-stu-id="2f539-196">101.00.31</span></span>

- <span data-ttu-id="2f539-197">Verbesserte [Produkt-Onboarding-Erfahrung für Intune-Benutzer](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="2f539-197">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="2f539-198">[Antivirusausschlüsse unterstützen jetzt Platzhalter](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="2f539-198">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="2f539-199">Es wurde die Möglichkeit hinzugefügt, Antivirenscans aus dem Kontextmenü von macOS auszulösen.</span><span class="sxs-lookup"><span data-stu-id="2f539-199">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="2f539-200">Sie können jetzt mit der rechten Maustaste auf eine Datei oder einen Ordner im Finder klicken und **"Mit Microsoft Defender für Endpunkt scannen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2f539-200">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="2f539-201">Direkte Produkt-Downgrades sind jetzt explizit vom Installationsprogramm nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2f539-201">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="2f539-202">Wenn Sie ein Downgrade ausführen müssen, deinstallieren Sie zuerst die vorhandene Version, und konfigurieren Sie Ihr Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="2f539-202">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="2f539-203">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-203">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="2f539-204">100.90.27</span><span class="sxs-lookup"><span data-stu-id="2f539-204">100.90.27</span></span>

- <span data-ttu-id="2f539-205">Sie können jetzt [einen Updatekanal](mac-updates.md#set-the-channel-name) für Microsoft Defender für Endpunkt unter macOS festlegen, der sich vom systemweiten Updatekanal unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2f539-205">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="2f539-206">Symbol "Neues Produkt"</span><span class="sxs-lookup"><span data-stu-id="2f539-206">New product icon</span></span>
- <span data-ttu-id="2f539-207">Weitere Verbesserungen der Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="2f539-207">Other user experience improvements</span></span>
- <span data-ttu-id="2f539-208">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-208">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="2f539-209">100.86.92</span><span class="sxs-lookup"><span data-stu-id="2f539-209">100.86.92</span></span>

- <span data-ttu-id="2f539-210">Verbesserungen bei der Kompatibilität mit dem Zeitcomputer</span><span class="sxs-lookup"><span data-stu-id="2f539-210">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="2f539-211">Es wurde ein Problem behoben, bei dem das Produkt manchmal nicht alle Dateien während der Deinstallation säuberte. `/Library/Application Support/Microsoft/Defender`</span><span class="sxs-lookup"><span data-stu-id="2f539-211">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="2f539-212">Verringerte die CPU-Auslastung des Produkts, wenn Microsoft-Produkte über Microsoft AutoUpdate aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="2f539-212">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="2f539-213">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-213">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="2f539-214">100.86.91</span><span class="sxs-lookup"><span data-stu-id="2f539-214">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="2f539-215">Um den umfassendsten Schutz für Ihre macOS-Geräte sicherzustellen und die Bereitstellung von nativen MacOS-Sicherheitsupdates an ältere Betriebssystemversionen als [aktuell – 2] durch Apple zu beenden, werden MDATP für die Mac-Bereitstellung und Updates unter macOS Sierra [10.12] nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2f539-215">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="2f539-216">MDATP für Mac-Updates und -Verbesserungen werden an Geräte bereitgestellt, auf denen die Versionen "Sierra" [10.15], "Mojave" [10.14] und "High Sierra" [10.13] ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f539-216">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="2f539-217">Wenn Sie bereits MDATP für Mac auf Ihren Sierra [10.12]-Geräten bereitgestellt haben, aktualisieren Sie bitte auf die neueste macOS-Version, um das Risiko zu vermeiden, dass der Schutz verloren geht.</span><span class="sxs-lookup"><span data-stu-id="2f539-217">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="2f539-218">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-218">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="2f539-219">100.83.73</span><span class="sxs-lookup"><span data-stu-id="2f539-219">100.83.73</span></span>

- <span data-ttu-id="2f539-220">Weitere Steuerelemente für IT-Administratoren im Zusammenhang mit [der Verwaltung von Ausschlüssen,](mac-preferences.md#exclusion-merge-policy)der Verwaltung von Einstellungen für [den Bedrohungstyp](mac-preferences.md#threat-type-settings-merge-policy)und [nicht zulässigen Bedrohungsaktionen](mac-preferences.md#disallowed-threat-actions) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="2f539-220">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="2f539-221">Wenn der vollständige Datenträgerzugriff auf dem Gerät nicht aktiviert ist, wird jetzt eine Warnung im Statusmenü angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f539-221">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="2f539-222">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-222">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="2f539-223">100.82.60</span><span class="sxs-lookup"><span data-stu-id="2f539-223">100.82.60</span></span>

- <span data-ttu-id="2f539-224">Es wurde ein Problem behoben, bei dem das Produkt nach einem Definitionsupdate nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f539-224">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="2f539-225">100.80.42</span><span class="sxs-lookup"><span data-stu-id="2f539-225">100.80.42</span></span>

- <span data-ttu-id="2f539-226">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-226">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="2f539-227">100.79.42</span><span class="sxs-lookup"><span data-stu-id="2f539-227">100.79.42</span></span>

- <span data-ttu-id="2f539-228">Es wurde ein Problem behoben, bei dem Microsoft Defender für Endpunkt auf dem Mac manchmal den Zeitcomputer beeinträchtigte.</span><span class="sxs-lookup"><span data-stu-id="2f539-228">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="2f539-229">Zum Testen der Konnektivität mit dem Back-End-Dienst wurde dem Befehlszeilenprogramm ein neuer Switch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2f539-229">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="2f539-230">Es wurde die Möglichkeit hinzugefügt, den vollständigen Bedrohungsverlauf auf der Benutzeroberfläche anzuzeigen (auf sie kann über die **Schutzverlaufsansicht** zugegriffen werden)</span><span class="sxs-lookup"><span data-stu-id="2f539-230">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="2f539-231">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-231">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="2f539-232">100.72.15</span><span class="sxs-lookup"><span data-stu-id="2f539-232">100.72.15</span></span>

- <span data-ttu-id="2f539-233">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-233">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="2f539-234">100.70.99</span><span class="sxs-lookup"><span data-stu-id="2f539-234">100.70.99</span></span>

- <span data-ttu-id="2f539-235">Es wurde ein Problem behoben, das sich auf die Möglichkeit einiger Benutzer auswirkte, auf macOS-Unterklasse zu aktualisieren, wenn der Echtzeitschutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2f539-235">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="2f539-236">Dieses sporadische Problem wurde dadurch verursacht, dass Microsoft Defender für Endpunkt Dateien innerhalb des Upgradepakets von Workstation sperrt, während sie auf Bedrohungen geprüft werden, was zu Fehlern in der Upgradesequenz geführt hat.</span><span class="sxs-lookup"><span data-stu-id="2f539-236">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="2f539-237">100.68.99</span><span class="sxs-lookup"><span data-stu-id="2f539-237">100.68.99</span></span>

- <span data-ttu-id="2f539-238">Die Möglichkeit zum Konfigurieren der Antivirusfunktionalität für die Ausführung im [passiven Modus](mac-preferences.md#enable--disable-passive-mode) wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2f539-238">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="2f539-239">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-239">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="2f539-240">100.65.28</span><span class="sxs-lookup"><span data-stu-id="2f539-240">100.65.28</span></span>

- <span data-ttu-id="2f539-241">Unterstützung für macOS Maze hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="2f539-241">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="2f539-242">macOS 10.15 (Mof) enthält neue Sicherheits- und Datenschutzverbesserungen.</span><span class="sxs-lookup"><span data-stu-id="2f539-242">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="2f539-243">Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.).</span><span class="sxs-lookup"><span data-stu-id="2f539-243">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="2f539-244">Wenn diese Zustimmung fehlt, ist Microsoft Defender für Endpunkt nicht in der Lage, Ihr Gerät vollständig zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2f539-244">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="2f539-245">Der Mechanismus für die Erteilung dieser Zustimmung hängt davon ab, wie Sie Microsoft Defender für Endpunkt bereitgestellt haben:</span><span class="sxs-lookup"><span data-stu-id="2f539-245">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="2f539-246">Informationen zu manuellen Bereitstellungen finden Sie in den aktualisierten Anweisungen im Thema ["Manuelle Bereitstellung".](mac-install-manually.md#how-to-allow-full-disk-access)</span><span class="sxs-lookup"><span data-stu-id="2f539-246">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="2f539-247">Informationen zu verwalteten Bereitstellungen finden Sie in den aktualisierten Anweisungen in den Themen zur [JAMF-basierten Bereitstellung](mac-install-with-jamf.md) und [Microsoft Intune-basierten Bereitstellung.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="2f539-247">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="2f539-248">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="2f539-248">Performance improvements & bug fixes</span></span>
