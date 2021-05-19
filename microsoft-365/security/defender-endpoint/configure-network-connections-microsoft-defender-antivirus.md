---
title: Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen
description: Konfigurieren und testen Sie Ihre Verbindung mit Microsoft Defender Antivirus Cloud Protection Service.
keywords: Antivirus, Microsoft Defender Antivirus, Antischalware, Sicherheit, Verteidiger, Cloud, Aggressivität, Schutzstufe
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536022"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="9fe5b-104">Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="9fe5b-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9fe5b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-105">**Applies to:**</span></span>

- [<span data-ttu-id="9fe5b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9fe5b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9fe5b-107">Um sicherzustellen Microsoft Defender Antivirus der von der Cloud übermittelte Schutz ordnungsgemäß funktioniert, müssen Sie Ihr Netzwerk so konfigurieren, dass Verbindungen zwischen Ihren Endpunkten und bestimmten Microsoft-Servern zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="9fe5b-108">In diesem Artikel werden die Verbindungen aufgeführt, die zulässig sein müssen, z. B. mithilfe von Firewallregeln, und enthält Anweisungen zum Überprüfen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="9fe5b-109">Wenn Sie Ihren Schutz ordnungsgemäß konfigurieren, stellen Sie sicher, dass Sie den bestmöglichen Nutzen aus Ihren in der Cloud übermittelten Schutzdiensten erhalten.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="9fe5b-110">Weitere Informationen zur Netzwerkkonnektivität finden Sie im Blogbeitrag Wichtige Änderungen am [Microsoft Active Protection Services-Endpunkt.](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="9fe5b-111">Sie können auch die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren:</span><span class="sxs-lookup"><span data-stu-id="9fe5b-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="9fe5b-112">Aus der Cloud gelieferter Schutz</span><span class="sxs-lookup"><span data-stu-id="9fe5b-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="9fe5b-113">Schnelles Lernen (einschließlich Block auf den ersten Blick)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="9fe5b-114">Potenziell unerwünschte Anwendungsblockierung</span><span class="sxs-lookup"><span data-stu-id="9fe5b-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="9fe5b-115">Zulassen von Verbindungen mit Microsoft Defender Antivirus Clouddienst</span><span class="sxs-lookup"><span data-stu-id="9fe5b-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="9fe5b-116">Der Microsoft Defender Antivirus bietet schnellen, starken Schutz für Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="9fe5b-117">Das Aktivieren des in der Cloud übermittelten Schutzdiensts ist optional, wird jedoch dringend empfohlen, da er einen wichtigen Schutz vor Schadsoftware auf Ihren Endpunkten und im gesamten Netzwerk bietet.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

> [!NOTE]
> <span data-ttu-id="9fe5b-118">Der Microsoft Defender Antivirus cloud service ist ein Mechanismus für die Bereitstellung aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="9fe5b-119">Obwohl er als Clouddienst bezeichnet wird, ist er nicht nur Schutz für in der Cloud gespeicherte Dateien, sondern verwendet verteilte Ressourcen und maschinelles Lernen, um Ihren Endpunkten Schutz zu bieten, und zwar mit einer Geschwindigkeit, die wesentlich schneller ist als herkömmliche Security Intelligence-Updates.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="9fe5b-120">Weitere Informationen zum Aktivieren des Diensts mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets oder auf einzelnen Clients in der Windows-Sicherheit finden Sie unter [Enable cloud-delivered protection.](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="9fe5b-121">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="9fe5b-122">Da Es sich bei Ihrem Schutz um einen Clouddienst handelt, müssen Computer Zugriff auf das Internet haben und Microsoft Defender for Office 365 Machine Learning Services erreichen.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="9fe5b-123">Schließen Sie die URL nicht von `*.blob.core.windows.net` jeder Art von Netzwerkprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="9fe5b-124">In der folgenden Tabelle sind die Dienste und die zugehörigen URLs aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="9fe5b-125">Stellen Sie sicher, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den Zugriff auf diese URLs verweigern, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen (mit Ausnahme der URL `*.blob.core.windows.net` ).</span><span class="sxs-lookup"><span data-stu-id="9fe5b-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="9fe5b-126">Im Folgenden wird erwähnt, dass URLs Port 443 für die Kommunikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="9fe5b-127">**Dienst**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-127">**Service**</span></span>| <span data-ttu-id="9fe5b-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-128">**Description**</span></span> |<span data-ttu-id="9fe5b-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="9fe5b-130">Microsoft Defender Antivirus von der Cloud zugestellter Schutzdienst, auch als Microsoft Active Protection Service (MAPS) bezeichnet</span><span class="sxs-lookup"><span data-stu-id="9fe5b-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="9fe5b-131">Wird von Microsoft Defender Antivirus verwendet, um in der Cloud zugestellten Schutz zu bieten</span><span class="sxs-lookup"><span data-stu-id="9fe5b-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="9fe5b-132">Microsoft Update Service (MU)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="9fe5b-133">Windows Updatedienst (WU)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="9fe5b-134">Sicherheitsintelligenz und Produktupdates</span><span class="sxs-lookup"><span data-stu-id="9fe5b-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="9fe5b-135">Weitere Informationen finden Sie [unter Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="9fe5b-136">Sicherheitsintelligenzupdates Alternativer Downloadspeicherort (Alternate Download Location, ADL)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="9fe5b-137">Alternativer Speicherort für Microsoft Defender Antivirus Sicherheitsintelligenzupdates, wenn die installierte Sicherheitsintelligenz nicht mehr aktuell ist (7 oder mehr Tage zurück)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="9fe5b-138">Schadsoftware-Übermittlungsspeicher</span><span class="sxs-lookup"><span data-stu-id="9fe5b-138">Malware submission storage</span></span>|<span data-ttu-id="9fe5b-139">Hochladen Speicherort für Dateien, die über das Übermittlungsformular oder die automatische Beispielübermittlung an Microsoft übermittelt wurden</span><span class="sxs-lookup"><span data-stu-id="9fe5b-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="9fe5b-140">Zertifikatsperrliste (Certificate Revocation List, CRL)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="9fe5b-141">Wird von Windows beim Erstellen der SSL-Verbindung zu MAPS zum Aktualisieren der Zertifikatsperrliste verwendet</span><span class="sxs-lookup"><span data-stu-id="9fe5b-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="9fe5b-142">Symbol Store</span><span class="sxs-lookup"><span data-stu-id="9fe5b-142">Symbol Store</span></span>|<span data-ttu-id="9fe5b-143">Wird von Microsoft Defender Antivirus zum Wiederherstellen bestimmter kritischer Dateien während des Behebungsflusses verwendet</span><span class="sxs-lookup"><span data-stu-id="9fe5b-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="9fe5b-144">Universeller Telemetrieclient</span><span class="sxs-lookup"><span data-stu-id="9fe5b-144">Universal Telemetry Client</span></span>| <span data-ttu-id="9fe5b-145">Wird von Windows zum Senden von Clientdiagnosedaten verwendet. Microsoft Defender Antivirus verwendet Telemetrie für Die Produktqualitätsüberwachung</span><span class="sxs-lookup"><span data-stu-id="9fe5b-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="9fe5b-146">Das Update verwendet SSL (TCP Port 443), um Manifeste herunterzuladen und Diagnosedaten an Microsoft hochzuladen, die die folgenden DNS-Endpunkte verwenden:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="9fe5b-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="9fe5b-147">Überprüfen von Verbindungen zwischen Ihrem Netzwerk und der Cloud</span><span class="sxs-lookup"><span data-stu-id="9fe5b-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="9fe5b-148">Nachdem Sie die oben aufgeführten URLs zulassen, können Sie testen, ob Sie mit dem Microsoft Defender Antivirus-Clouddienst verbunden sind und ordnungsgemäß Berichterstellungs- und Empfangsinformationen erhalten, um sicherzustellen, dass Sie vollständig geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="9fe5b-149">**Verwenden Sie das Cmdline-Tool, um den von der Cloud übermittelten Schutz zu überprüfen:**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="9fe5b-150">Verwenden Sie das folgende Argument mit Microsoft Defender Antivirus Befehlszeilenprogramm ( ), um zu überprüfen, ob Ihr Netzwerk mit dem Microsoft Defender Antivirus `mpcmdrun.exe` kommunizieren kann:</span><span class="sxs-lookup"><span data-stu-id="9fe5b-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="9fe5b-151">Sie müssen eine Administratorversion der Eingabeaufforderung öffnen.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="9fe5b-152">Klicken Sie im Menü Start mit der rechten Maustaste auf das Element, klicken Sie auf Als Administrator **ausführen,** und klicken Sie an der Berechtigungsaufforderung **auf** Ja.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="9fe5b-153">Dieser Befehl funktioniert nur für Windows 10 Version 1703 oder höher.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="9fe5b-154">Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="9fe5b-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="9fe5b-155">**Versuchen Sie, eine gefälschte Schadsoftwaredatei von Microsoft herunterzuladen:**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="9fe5b-156">Sie können eine Beispieldatei herunterladen, die Microsoft Defender Antivirus erkennt und blockiert, wenn Sie ordnungsgemäß mit der Cloud verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="9fe5b-157">Laden Sie die Datei unter [https://aka.ms/ioavtest](https://aka.ms/ioavtest) herunter.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="9fe5b-158">Diese Datei ist keine tatsächliche Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="9fe5b-159">Es handelt sich um eine gefälschte Datei, die testen soll, ob Sie ordnungsgemäß mit der Cloud verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="9fe5b-160">Wenn Sie ordnungsgemäß verbunden sind, wird eine Warnung Microsoft Defender Antivirus angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="9fe5b-161">Wenn Sie eine Microsoft Edge verwenden, wird auch eine Benachrichtigung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9fe5b-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge benutzer darüber informieren, dass Schadsoftware gefunden wurde](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="9fe5b-163">Eine ähnliche Meldung tritt auf, wenn Sie Internet Explorer verwenden:</span><span class="sxs-lookup"><span data-stu-id="9fe5b-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender Antivirus Benachrichtigung des Benutzers, dass Schadsoftware gefunden wurde](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="9fe5b-165">Außerdem wird eine Erkennung  unter Quarantänebedrohungen im Abschnitt **Scanverlauf** in der Windows-Sicherheit angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9fe5b-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="9fe5b-166">Öffnen Sie Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Defender suchen.**</span><span class="sxs-lookup"><span data-stu-id="9fe5b-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="9fe5b-167">Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) und dann die Bezeichnung **Scanverlauf** aus:</span><span class="sxs-lookup"><span data-stu-id="9fe5b-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Screenshot der Bezeichnung "Scanverlauf" in der Windows-Sicherheit App](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="9fe5b-169">Wählen Sie **im Abschnitt Isolierte Bedrohungen** die Option **Vollständiger Verlauf,** um die erkannte gefälschte Schadsoftware zu sehen.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9fe5b-170">Versionen von Windows 10 vor Version 1703 haben eine andere Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="9fe5b-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="9fe5b-171">Weitere [Microsoft Defender Antivirus finden Sie in der Windows-Sicherheit App.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="9fe5b-172">Das Windows-Ereignisprotokoll zeigt auch Windows Defender [Clientereignis-ID 1116 an.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9fe5b-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="9fe5b-173">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9fe5b-173">Related articles</span></span>

- [<span data-ttu-id="9fe5b-174">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fe5b-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="9fe5b-175">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="9fe5b-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9fe5b-176">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="9fe5b-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9fe5b-177">Wichtige Änderungen am Microsoft Active Protection Services-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9fe5b-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
