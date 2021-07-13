---
title: Konfigurieren und Validieren von Ausschlüssen für Microsoft Defender für Endpunkt unter Linux
description: Bereitstellen und Überprüfen von Ausschlüssen für Microsoft Defender für Endpunkt unter Linux. Ausschlüsse können für Dateien, Ordner und Prozesse festgelegt werden.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Ausschlüsse, Scans, Antivirus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b55572509e9837f2858f96b01a13fbf259b2b770
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393787"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="62b20-105">Konfigurieren und Validieren von Ausschlüssen für Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="62b20-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62b20-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="62b20-106">**Applies to:**</span></span>

- [<span data-ttu-id="62b20-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="62b20-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62b20-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62b20-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="62b20-109">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="62b20-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="62b20-110">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="62b20-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="62b20-111">Dieser Artikel enthält Informationen zum Definieren von Ausschlüssen, die für Scans bei Bedarf gelten, sowie zum Echtzeitschutz und zur Überwachung.</span><span class="sxs-lookup"><span data-stu-id="62b20-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62b20-112">Die in diesem Artikel beschriebenen Ausschlüsse gelten nicht für andere Defender für Endpunkt unter Linux-Funktionen, einschließlich EDR (EDR).</span><span class="sxs-lookup"><span data-stu-id="62b20-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="62b20-113">Dateien, die Sie mithilfe der in diesem Artikel beschriebenen Methoden ausschließen, können weiterhin EDR Warnungen und andere Erkennungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="62b20-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="62b20-114">Sie können bestimmte Dateien, Ordner, Prozesse und vom Prozess geöffnete Dateien von Defender für Endpunkt bei Linux-Scans ausschließen.</span><span class="sxs-lookup"><span data-stu-id="62b20-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="62b20-115">Ausschlüsse können nützlich sein, um falsche Erkennungen von Dateien oder Software zu vermeiden, die für Ihre Organisation eindeutig oder angepasst sind.</span><span class="sxs-lookup"><span data-stu-id="62b20-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="62b20-116">Sie können auch nützlich sein, um Leistungsprobleme zu beheben, die von Defender für Endpunkt unter Linux verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="62b20-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="62b20-117">Durch das Definieren von Ausschlüssen wird der von Defender für Endpunkt unter Linux angebotene Schutz verringert.</span><span class="sxs-lookup"><span data-stu-id="62b20-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="62b20-118">Sie sollten immer die Risiken auswerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von denen Sie sicher sind, dass sie nicht bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="62b20-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="62b20-119">Unterstützte Ausschlusstypen</span><span class="sxs-lookup"><span data-stu-id="62b20-119">Supported exclusion types</span></span>

<span data-ttu-id="62b20-120">In der folgenden Tabelle sind die ausschlusstypen aufgeführt, die von Defender für Endpunkt unter Linux unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="62b20-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="62b20-121">Ausschluss</span><span class="sxs-lookup"><span data-stu-id="62b20-121">Exclusion</span></span> | <span data-ttu-id="62b20-122">Definition</span><span class="sxs-lookup"><span data-stu-id="62b20-122">Definition</span></span> | <span data-ttu-id="62b20-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="62b20-123">Examples</span></span>
---|---|---
<span data-ttu-id="62b20-124">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="62b20-124">File extension</span></span> | <span data-ttu-id="62b20-125">Alle Dateien mit der Erweiterung an beliebiger Stelle auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="62b20-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="62b20-126">Datei</span><span class="sxs-lookup"><span data-stu-id="62b20-126">File</span></span> | <span data-ttu-id="62b20-127">Eine bestimmte Datei, die durch den vollständigen Pfad identifiziert wird</span><span class="sxs-lookup"><span data-stu-id="62b20-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="62b20-128">Ordner</span><span class="sxs-lookup"><span data-stu-id="62b20-128">Folder</span></span> | <span data-ttu-id="62b20-129">Alle Dateien unter dem angegebenen Ordner (rekursiv)</span><span class="sxs-lookup"><span data-stu-id="62b20-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="62b20-130">Prozess</span><span class="sxs-lookup"><span data-stu-id="62b20-130">Process</span></span> | <span data-ttu-id="62b20-131">Ein bestimmter Prozess (angegeben durch den vollständigen Pfad oder Dateinamen) und alle geöffneten Dateien</span><span class="sxs-lookup"><span data-stu-id="62b20-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="62b20-132">Die oben genannten Pfade müssen feste Verknüpfungen und keine symbolischen Verknüpfungen sein, damit sie erfolgreich ausgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="62b20-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="62b20-133">Sie können überprüfen, ob ein Pfad eine symbolische Verknüpfung ist, indem Sie `file <path-name>` ausführen.</span><span class="sxs-lookup"><span data-stu-id="62b20-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="62b20-134">Datei-, Ordner- und Prozessausschlüsse unterstützen die folgenden Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="62b20-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="62b20-135">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="62b20-135">Wildcard</span></span> | <span data-ttu-id="62b20-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62b20-136">Description</span></span> | <span data-ttu-id="62b20-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62b20-137">Example</span></span> | <span data-ttu-id="62b20-138">Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="62b20-138">Matches</span></span> | <span data-ttu-id="62b20-139">Stimmt nicht überein</span><span class="sxs-lookup"><span data-stu-id="62b20-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="62b20-140">Gleicht eine beliebige Anzahl von Zeichen ab, einschließlich keines (beachten Sie, dass bei Verwendung dieses Platzhalters innerhalb eines Pfads nur ein Ordner ersetzt wird).</span><span class="sxs-lookup"><span data-stu-id="62b20-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="62b20-141">?</span><span class="sxs-lookup"><span data-stu-id="62b20-141">?</span></span> | <span data-ttu-id="62b20-142">Gleicht ein beliebiges einzelnes Zeichen ab</span><span class="sxs-lookup"><span data-stu-id="62b20-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="62b20-143">So konfigurieren Sie die Liste der Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="62b20-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="62b20-144">Aus der Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="62b20-144">From the management console</span></span>

<span data-ttu-id="62b20-145">Weitere Informationen zum Konfigurieren von Ausschlüssen aus Deringen, Ansible oder einer anderen Verwaltungskonsole finden Sie unter [Festlegen von Einstellungen für Defender für Endpunkt unter Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="62b20-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="62b20-146">Über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="62b20-146">From the command line</span></span>

<span data-ttu-id="62b20-147">Führen Sie den folgenden Befehl aus, um die verfügbaren Optionen zum Verwalten von Ausschlüssen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="62b20-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="62b20-148">Wenn Sie Ausschlüsse mit Platzhaltern konfigurieren, schließen Sie den Parameter in doppelte Anführungszeichen ein, um Globbing zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="62b20-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="62b20-149">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="62b20-149">Examples:</span></span>

- <span data-ttu-id="62b20-150">Fügen Sie einen Ausschluss für eine Dateierweiterung hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="62b20-151">Fügen Sie einen Ausschluss für eine Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="62b20-152">Fügen Sie einen Ausschluss für einen Ordner hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- <span data-ttu-id="62b20-153">Fügen Sie einen Ausschluss für einen zweiten Ordner hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-153">Add an exclusion for a second folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- <span data-ttu-id="62b20-154">Fügen Sie einen Ausschluss für einen Ordner mit einem Platzhalter hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-154">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="62b20-155">Dadurch werden nur Pfade eine Ebene unter */var/* ausgeschlossen, aber keine Ordner, die tiefer verschachtelt sind; Beispiel: */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="62b20-155">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="62b20-156">Dadurch werden alle Pfade ausgeschlossen, deren übergeordnetes Element */var/* ist; Beispiel: */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="62b20-156">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="62b20-157">Fügen Sie einen Ausschluss für einen Prozess hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-157">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```


- <span data-ttu-id="62b20-158">Fügen Sie einen Ausschluss für einen zweiten Prozess hinzu:</span><span class="sxs-lookup"><span data-stu-id="62b20-158">Add an exclusion for a second process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="62b20-159">Überprüfen von Ausschlusslisten mit der EICAR-Testdatei</span><span class="sxs-lookup"><span data-stu-id="62b20-159">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="62b20-160">Sie können überprüfen, ob Ihre Ausschlusslisten funktionieren, indem `curl` Sie eine Testdatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="62b20-160">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="62b20-161">Ersetzen Sie im folgenden Bash-Codeausschnitt `test.txt` durch eine Datei, die Ihren Ausschlussregeln entspricht.</span><span class="sxs-lookup"><span data-stu-id="62b20-161">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="62b20-162">Wenn Sie die Erweiterung beispielsweise ausgeschlossen `.testing` haben, ersetzen Sie `test.txt` sie durch `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="62b20-162">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="62b20-163">Wenn Sie einen Pfad testen, stellen Sie sicher, dass Sie den Befehl innerhalb dieses Pfads ausführen.</span><span class="sxs-lookup"><span data-stu-id="62b20-163">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="62b20-164">Wenn Defender für Endpunkt unter Linux Schadsoftware meldet, funktioniert die Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="62b20-164">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="62b20-165">Wenn kein Bericht über Schadsoftware vorhanden ist und die heruntergeladene Datei vorhanden ist, funktioniert der Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="62b20-165">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="62b20-166">Sie können die Datei öffnen, um zu bestätigen, dass der Inhalt mit dem identisch ist, was auf der [EICAR-Testdateiwebsite](http://2016.eicar.org/86-0-Intended-use.html)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="62b20-166">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="62b20-167">Wenn Sie keinen Internetzugriff haben, können Sie Eine eigene EICAR-Testdatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="62b20-167">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="62b20-168">Schreiben Sie die EICAR-Zeichenfolge in eine neue Textdatei mit dem folgenden Bash-Befehl:</span><span class="sxs-lookup"><span data-stu-id="62b20-168">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="62b20-169">Sie können die Zeichenfolge auch in eine leere Textdatei kopieren und versuchen, sie mit dem Dateinamen oder in dem Ordner zu speichern, den Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="62b20-169">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="62b20-170">Zulassen von Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="62b20-170">Allow threats</span></span>

<span data-ttu-id="62b20-171">Neben dem Ausschließen bestimmter Inhalte von der Überprüfung können Sie das Produkt auch so konfigurieren, dass einige Klassen von Bedrohungen (durch den Bedrohungsnamen identifiziert) nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="62b20-171">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="62b20-172">Seien Sie vorsichtig, wenn Sie diese Funktionalität verwenden, da ihr Gerät dadurch ungeschützter ist.</span><span class="sxs-lookup"><span data-stu-id="62b20-172">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="62b20-173">Führen Sie den folgenden Befehl aus, um der Liste zugelassener Bedrohungen einen Bedrohungsnamen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="62b20-173">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="62b20-174">Der bedrohungsname, der einer Erkennung auf Ihrem Gerät zugeordnet ist, kann mit dem folgenden Befehl abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="62b20-174">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="62b20-175">Führen Sie z. B. den folgenden Befehl aus, um der Liste zugelassener Elemente (der der `EICAR-Test-File (not a virus)` EICAR-Erkennung zugeordnete Bedrohungsname) hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="62b20-175">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
