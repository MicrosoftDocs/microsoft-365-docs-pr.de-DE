---
title: Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender ATP für Linux
description: Bereitstellen und Überprüfen von Ausschlüssen für Microsoft Defender ATP für Linux. Ausschlüsse können für Dateien, Ordner und Prozesse festgelegt werden.
keywords: microsoft, defender, atp, linux, exclusions, scans, antivirus
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
ms.openlocfilehash: f5e9c237f53351df0249f0a12d08b8ba61572f7e
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587083"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="0d4c6-105">Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="0d4c6-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0d4c6-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0d4c6-106">**Applies to:**</span></span>
- [<span data-ttu-id="0d4c6-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0d4c6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0d4c6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d4c6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0d4c6-109">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0d4c6-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0d4c6-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0d4c6-111">Dieser Artikel enthält Informationen zum Definieren von Ausschlüssen, die für Scans bei Bedarf gelten, sowie Zum Schutz und Überwachung in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d4c6-112">Die in diesem Artikel beschriebenen Ausschlüsse gelten nicht für andere Defender for Endpoint for Linux-Funktionen, einschließlich Endpunkterkennung und -reaktion (EDR).</span><span class="sxs-lookup"><span data-stu-id="0d4c6-112">The exclusions described in this article don't apply to other Defender for Endpoint for Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="0d4c6-113">Dateien, die Sie mithilfe der in diesem Artikel beschriebenen Methoden ausschließen, können weiterhin EDR-Warnungen und andere Erkennungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="0d4c6-114">Sie können bestimmte Dateien, Ordner, Prozesse und prozessge öffnende Dateien aus Defender for Endpoint für Linux-Scans ausschließen.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Linux scans.</span></span>

<span data-ttu-id="0d4c6-115">Ausschlüsse können hilfreich sein, um fehlerhafte Erkennungen für Dateien oder Software zu vermeiden, die eindeutig oder an Ihre Organisation angepasst sind.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="0d4c6-116">Sie können auch hilfreich sein, um Leistungsprobleme zu mildern, die von Defender for Endpoint für Linux verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="0d4c6-117">Durch das Definieren von Ausschlüssen wird der von Defender for Endpoint für Linux gebotene Schutz gesenkt.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="0d4c6-118">Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="0d4c6-119">Unterstützte Ausschlusstypen</span><span class="sxs-lookup"><span data-stu-id="0d4c6-119">Supported exclusion types</span></span>

<span data-ttu-id="0d4c6-120">In der folgenden Tabelle sind die Ausschlusstypen aufgeführt, die von Defender for Endpoint für Linux unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-120">The follow table shows the exclusion types supported by Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="0d4c6-121">Ausschluss</span><span class="sxs-lookup"><span data-stu-id="0d4c6-121">Exclusion</span></span> | <span data-ttu-id="0d4c6-122">Definition</span><span class="sxs-lookup"><span data-stu-id="0d4c6-122">Definition</span></span> | <span data-ttu-id="0d4c6-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0d4c6-123">Examples</span></span>
---|---|---
<span data-ttu-id="0d4c6-124">Dateierweiterung</span><span class="sxs-lookup"><span data-stu-id="0d4c6-124">File extension</span></span> | <span data-ttu-id="0d4c6-125">Alle Dateien mit der Erweiterung, überall auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="0d4c6-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="0d4c6-126">Datei</span><span class="sxs-lookup"><span data-stu-id="0d4c6-126">File</span></span> | <span data-ttu-id="0d4c6-127">Eine bestimmte Datei, die durch den vollständigen Pfad identifiziert wird</span><span class="sxs-lookup"><span data-stu-id="0d4c6-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="0d4c6-128">Ordner</span><span class="sxs-lookup"><span data-stu-id="0d4c6-128">Folder</span></span> | <span data-ttu-id="0d4c6-129">Alle Dateien unter dem angegebenen Ordner (rekursiv)</span><span class="sxs-lookup"><span data-stu-id="0d4c6-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="0d4c6-130">Prozess</span><span class="sxs-lookup"><span data-stu-id="0d4c6-130">Process</span></span> | <span data-ttu-id="0d4c6-131">Ein bestimmter Prozess (entweder durch den vollständigen Pfad oder Dateinamen angegeben) und alle dateien, die von diesem geöffnet werden</span><span class="sxs-lookup"><span data-stu-id="0d4c6-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="0d4c6-132">Die oben genannten Pfade müssen harte Links und keine symbolischen Verknüpfungen sein, um erfolgreich ausgeschlossen zu werden.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="0d4c6-133">Sie können überprüfen, ob ein Pfad ein symbolischer Link ist, indem Sie `file <path-name>` ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="0d4c6-134">Datei-, Ordner- und Prozessausschlüsse unterstützen die folgenden Platzhalter:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="0d4c6-135">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="0d4c6-135">Wildcard</span></span> | <span data-ttu-id="0d4c6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d4c6-136">Description</span></span> | <span data-ttu-id="0d4c6-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d4c6-137">Example</span></span> | <span data-ttu-id="0d4c6-138">Übereinstimmungen</span><span class="sxs-lookup"><span data-stu-id="0d4c6-138">Matches</span></span> | <span data-ttu-id="0d4c6-139">Nicht übereinstimmend</span><span class="sxs-lookup"><span data-stu-id="0d4c6-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="0d4c6-140">Entspricht einer beliebigen Anzahl beliebiger Zeichen, einschließlich keines (beachten Sie, dass dieser Platzhalter nur einen Ordner ersetzt, wenn er innerhalb eines Pfads verwendet wird)</span><span class="sxs-lookup"><span data-stu-id="0d4c6-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="0d4c6-141">?</span><span class="sxs-lookup"><span data-stu-id="0d4c6-141">?</span></span> | <span data-ttu-id="0d4c6-142">Entspricht einem beliebigen einzelnen Zeichen</span><span class="sxs-lookup"><span data-stu-id="0d4c6-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="0d4c6-143">Konfigurieren der Liste der Ausschlüsse</span><span class="sxs-lookup"><span data-stu-id="0d4c6-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="0d4c6-144">Über die Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="0d4c6-144">From the management console</span></span>

<span data-ttu-id="0d4c6-145">Weitere Informationen zum Konfigurieren von Ausschlüssen von Puppet, Ansible oder einer anderen Verwaltungskonsole finden Sie unter [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="0d4c6-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="0d4c6-146">Über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="0d4c6-146">From the command line</span></span>

<span data-ttu-id="0d4c6-147">Führen Sie den folgenden Befehl aus, um die verfügbaren Switches zum Verwalten von Ausschlüssen zu sehen:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="0d4c6-148">Schließen Sie beim Konfigurieren von Ausschlüssen mit Platzhaltern den Parameter in doppelte Anführungszeichen ein, um das Kugeln zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="0d4c6-149">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-149">Examples:</span></span>

- <span data-ttu-id="0d4c6-150">Hinzufügen eines Ausschlusses für eine Dateierweiterung:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="0d4c6-151">Hinzufügen eines Ausschlusses für eine Datei:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="0d4c6-152">Hinzufügen eines Ausschlusses für einen Ordner:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="0d4c6-153">Fügen Sie einen Ausschluss für einen Ordner mit einem Platzhalter hinzu:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="0d4c6-154">Dadurch werden pfade nur eine Ebene unterhalb *von /var/* ausgeschlossen, aber keine Ordner, die tiefer geschachtelt sind. Beispiel: */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="0d4c6-155">Dadurch werden alle Pfade ausgeschlossen, deren *übergeordnetes Element /var/* ist. Beispiel: */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="0d4c6-156">Hinzufügen eines Ausschlusses für einen Prozess:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="0d4c6-157">Überprüfen von Ausschlusslisten mit der EICAR-Testdatei</span><span class="sxs-lookup"><span data-stu-id="0d4c6-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="0d4c6-158">Sie können überprüfen, ob Ihre Ausschlusslisten funktionieren, indem Sie `curl` eine Testdatei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="0d4c6-159">Ersetzen Sie im folgenden Bash-Codeausschnitt durch eine Datei, die `test.txt` Ihren Ausschlussregeln entspricht.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="0d4c6-160">Wenn Sie beispielsweise die Erweiterung ausgeschlossen `.testing` haben, ersetzen Sie `test.txt` durch `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="0d4c6-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="0d4c6-161">Wenn Sie einen Pfad testen, stellen Sie sicher, dass Sie den Befehl innerhalb dieses Pfads ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="0d4c6-162">Wenn Defender for Endpoint für Linux Schadsoftware meldet, funktioniert die Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-162">If Defender for Endpoint for Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="0d4c6-163">Wenn kein Bericht über Schadsoftware vorhanden ist und die heruntergeladene Datei vorhanden ist, funktioniert der Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="0d4c6-164">Sie können die Datei öffnen, um zu bestätigen, dass der Inhalt mit den auf der [EICAR-Testdateiwebsite beschriebenen Inhalten identisch ist.](http://2016.eicar.org/86-0-Intended-use.html)</span><span class="sxs-lookup"><span data-stu-id="0d4c6-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="0d4c6-165">Wenn Sie keinen Internetzugriff haben, können Sie eine eigene EICAR-Testdatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="0d4c6-166">Schreiben Sie die EICAR-Zeichenfolge mit dem folgenden Bash-Befehl in eine neue Textdatei:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="0d4c6-167">Sie können die Zeichenfolge auch in eine leere Textdatei kopieren und versuchen, sie mit dem Dateinamen oder in dem Ordner zu speichern, den Sie ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="0d4c6-168">Zulassen von Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="0d4c6-168">Allow threats</span></span>

<span data-ttu-id="0d4c6-169">Zusätzlich zum Ausschließen bestimmter Inhalte, die gescannt werden, können Sie das Produkt auch so konfigurieren, dass einige Klassen von Bedrohungen (identifiziert durch den Bedrohungsnamen) nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="0d4c6-170">Bei der Verwendung dieser Funktionalität sollten Sie Vorsichtigkeit walten lassen, da ihr Gerät nicht geschützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0d4c6-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="0d4c6-171">Führen Sie den folgenden Befehl aus, um der liste der zulässigen Bedrohungen einen Bedrohungsnamen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="0d4c6-172">Der Bedrohungsname, der einer Erkennung auf Ihrem Gerät zugeordnet ist, kann mithilfe des folgenden Befehls ermittelt werden:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="0d4c6-173">Führen Sie beispielsweise den folgenden Befehl aus, um der liste zulässigen Liste (der der `EICAR-Test-File (not a virus)` EICAR-Erkennung zugeordnete Bedrohungsname) hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0d4c6-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
