---
title: Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender ATP für Mac
description: Bereitstellen und Überprüfen von Ausschlüssen für Microsoft Defender ATP für Mac. Ausschlüsse können für Dateien, Ordner und Prozesse festgelegt werden.
keywords: microsoft, defender, atp, mac, exclusions, scans, antivirus
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
ms.openlocfilehash: 0ce77d55ece955fbf97b5c9f32859514b55acb5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187649"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="7200f-105">Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="7200f-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7200f-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7200f-106">**Applies to:**</span></span>
- [<span data-ttu-id="7200f-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7200f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7200f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7200f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7200f-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7200f-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7200f-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7200f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="7200f-111">Dieser Artikel enthält Informationen zum Definieren von Ausschlüssen, die für Scans bei Bedarf gelten, sowie Zum Schutz und Überwachung in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="7200f-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7200f-112">Die in diesem Artikel beschriebenen Ausschlüsse gelten nicht für andere Defender for Endpoint für Mac-Funktionen, einschließlich Endpunkterkennung und -reaktion (EDR).</span><span class="sxs-lookup"><span data-stu-id="7200f-112">The exclusions described in this article don't apply to other Defender for Endpoint for Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="7200f-113">Dateien, die Sie mithilfe der in diesem Artikel beschriebenen Methoden ausschließen, können weiterhin EDR-Warnungen und andere Erkennungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="7200f-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="7200f-114">Sie können bestimmte Dateien, Ordner, Prozesse und prozessgeladene Dateien aus Defender for Endpoint für Mac-Scans ausschließen.</span><span class="sxs-lookup"><span data-stu-id="7200f-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Mac scans.</span></span>

<span data-ttu-id="7200f-115">Ausschlüsse können hilfreich sein, um fehlerhafte Erkennungen für Dateien oder Software zu vermeiden, die eindeutig oder an Ihre Organisation angepasst sind.</span><span class="sxs-lookup"><span data-stu-id="7200f-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="7200f-116">Sie können auch hilfreich sein, um Leistungsprobleme zu mildern, die von Defender for Endpoint für Mac verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="7200f-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Mac.</span></span>

>[!WARNING]
><span data-ttu-id="7200f-117">Durch das Definieren von Ausschlüssen wird der von Defender for Endpoint für Mac angebotene Schutz gesenkt.</span><span class="sxs-lookup"><span data-stu-id="7200f-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="7200f-118">Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="7200f-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="7200f-119">Unterstützte Ausschlusstypen</span><span class="sxs-lookup"><span data-stu-id="7200f-119">Supported exclusion types</span></span>

<span data-ttu-id="7200f-120">In der folgenden Tabelle sind die Ausschlusstypen aufgeführt, die von Defender for Endpoint für Mac unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7200f-120">The follow table shows the exclusion types supported by Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="7200f-121">Ausschluss</span><span class="sxs-lookup"><span data-stu-id="7200f-121">Exclusion</span></span> | <span data-ttu-id="7200f-122">Definition</span><span class="sxs-lookup"><span data-stu-id="7200f-122">Definition</span></span> | <span data-ttu-id="7200f-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7200f-123">Examples</span></span>
---|---|---
<span data-ttu-id="7200f-124">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="7200f-124">File extension</span></span> | <span data-ttu-id="7200f-125">Alle Dateien mit der Erweiterung, überall auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="7200f-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="7200f-126">File</span><span class="sxs-lookup"><span data-stu-id="7200f-126">File</span></span> | <span data-ttu-id="7200f-127">Eine bestimmte Datei, die durch den vollständigen Pfad identifiziert wird</span><span class="sxs-lookup"><span data-stu-id="7200f-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="7200f-128">Ordner</span><span class="sxs-lookup"><span data-stu-id="7200f-128">Folder</span></span> | <span data-ttu-id="7200f-129">Alle Dateien unter dem angegebenen Ordner (rekursiv)</span><span class="sxs-lookup"><span data-stu-id="7200f-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="7200f-130">Prozess</span><span class="sxs-lookup"><span data-stu-id="7200f-130">Process</span></span> | <span data-ttu-id="7200f-131">Ein bestimmter Prozess (entweder durch den vollständigen Pfad oder Dateinamen angegeben) und alle dateien, die von diesem geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="7200f-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="7200f-132">Datei-, Ordner- und Prozessausschlüsse unterstützen die folgenden Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="7200f-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="7200f-133">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="7200f-133">Wildcard</span></span> | <span data-ttu-id="7200f-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7200f-134">Description</span></span> | <span data-ttu-id="7200f-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7200f-135">Example</span></span> | <span data-ttu-id="7200f-136">Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="7200f-136">Matches</span></span> | <span data-ttu-id="7200f-137">Nicht übereinstimmend</span><span class="sxs-lookup"><span data-stu-id="7200f-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="7200f-138">Entspricht einer beliebigen Anzahl beliebiger Zeichen, einschließlich keines (beachten Sie, dass dieser Platzhalter nur einen Ordner ersetzt, wenn er innerhalb eines Pfads verwendet wird)</span><span class="sxs-lookup"><span data-stu-id="7200f-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="7200f-139">?</span><span class="sxs-lookup"><span data-stu-id="7200f-139">?</span></span> | <span data-ttu-id="7200f-140">Entspricht einem beliebigen einzelnen Zeichen</span><span class="sxs-lookup"><span data-stu-id="7200f-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="7200f-141">Das Produkt versucht, firmlinks beim Auswerten von Ausschlüssen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7200f-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="7200f-142">Die Auflösung von Firmlink funktioniert nicht, wenn der Ausschluss Platzhalter enthält oder die Zieldatei (auf dem `Data` Volume) nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7200f-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="7200f-143">Konfigurieren der Liste der Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="7200f-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="7200f-144">Über die Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="7200f-144">From the management console</span></span>

<span data-ttu-id="7200f-145">Weitere Informationen zum Konfigurieren von Ausschlüssen aus JAMF, Intune oder einer anderen Verwaltungskonsole finden Sie unter [Set preferences for Defender for Endpoint for Mac](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="7200f-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint for Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="7200f-146">Über die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="7200f-146">From the user interface</span></span>

<span data-ttu-id="7200f-147">Öffnen Sie die Defender for Endpoint-Anwendung, und navigieren Sie zu Einstellungen **verwalten** Hinzufügen oder Entfernen von  >  **Ausschluss...**, wie im folgenden Screenshot gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7200f-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![Screenshot "Verwalten von Ausschlüssen"](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-37-exclusions)

<span data-ttu-id="7200f-149">Wählen Sie den Typ des Ausschlusses aus, den Sie hinzufügen möchten, und folgen Sie den Eingabeaufforderungen.</span><span class="sxs-lookup"><span data-stu-id="7200f-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="7200f-150">Überprüfen von Ausschlusslisten mit der EICAR-Testdatei</span><span class="sxs-lookup"><span data-stu-id="7200f-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="7200f-151">Sie können überprüfen, ob Ihre Ausschlusslisten funktionieren, indem Sie `curl` eine Testdatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="7200f-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="7200f-152">Ersetzen Sie im folgenden Bash-Codeausschnitt durch eine Datei, die `test.txt` Ihren Ausschlussregeln entspricht.</span><span class="sxs-lookup"><span data-stu-id="7200f-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="7200f-153">Wenn Sie beispielsweise die Erweiterung ausgeschlossen `.testing` haben, ersetzen Sie `test.txt` durch `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="7200f-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="7200f-154">Wenn Sie einen Pfad testen, stellen Sie sicher, dass Sie den Befehl innerhalb dieses Pfads ausführen.</span><span class="sxs-lookup"><span data-stu-id="7200f-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="7200f-155">Wenn Defender for Endpoint für Mac Schadsoftware meldet, funktioniert die Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="7200f-155">If Defender for Endpoint for Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="7200f-156">Wenn kein Bericht über Schadsoftware vorhanden ist und die heruntergeladene Datei vorhanden ist, funktioniert der Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="7200f-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="7200f-157">Sie können die Datei öffnen, um zu bestätigen, dass der Inhalt mit den auf der [EICAR-Testdateiwebsite beschriebenen Inhalten identisch ist.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="7200f-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="7200f-158">Wenn Sie keinen Internetzugriff haben, können Sie eine eigene EICAR-Testdatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="7200f-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="7200f-159">Schreiben Sie die EICAR-Zeichenfolge mit dem folgenden Bash-Befehl in eine neue Textdatei:</span><span class="sxs-lookup"><span data-stu-id="7200f-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="7200f-160">Sie können die Zeichenfolge auch in eine leere Textdatei kopieren und versuchen, sie mit dem Dateinamen oder in dem Ordner zu speichern, den Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="7200f-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="7200f-161">Zulassen von Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="7200f-161">Allow threats</span></span>

<span data-ttu-id="7200f-162">Zusätzlich zum Ausschließen bestimmter Inhalte, die gescannt werden, können Sie das Produkt auch so konfigurieren, dass einige Klassen von Bedrohungen (identifiziert durch den Bedrohungsnamen) nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="7200f-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="7200f-163">Bei der Verwendung dieser Funktionalität sollten Sie Vorsichtigkeit walten lassen, da ihr Gerät nicht geschützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7200f-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="7200f-164">Führen Sie den folgenden Befehl aus, um der liste der zulässigen Bedrohungen einen Bedrohungsnamen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="7200f-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="7200f-165">Der Bedrohungsname, der einer Erkennung auf Ihrem Gerät zugeordnet ist, kann mithilfe des folgenden Befehls ermittelt werden:</span><span class="sxs-lookup"><span data-stu-id="7200f-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="7200f-166">Führen Sie beispielsweise den folgenden Befehl aus, um der liste zulässigen Liste (der der `EICAR-Test-File (not a virus)` EICAR-Erkennung zugeordnete Bedrohungsname) hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="7200f-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
