---
title: Office 365-IP-Adress- und -URL-Webdienst
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Erfahren Sie, wie Sie den Office 365-IP-Adress- und URL-Webdienst nutzen können, um den Netzwerkverkehr von Office 365 besser zu identifizieren und zu differenzieren.
ms.openlocfilehash: 1948491e1d3db724e7b7b6a5275234acab4be08a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918954"
---
# <a name="office-365-ip-address-and-url-web-service"></a><span data-ttu-id="7dbaa-103">Office 365-IP-Adress- und -URL-Webdienst</span><span class="sxs-lookup"><span data-stu-id="7dbaa-103">Office 365 IP Address and URL web service</span></span>

<span data-ttu-id="7dbaa-104">Der Office 365-IP-Adress- und URL-Dienst unterstützt Sie beim besseren Erkennen und Differenzieren des Netzwerkdatenverkehrs in Office 365, was es Ihnen erleichtert, Änderungen auszuwerten, zu konfigurieren und auf dem neuesten Stand zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-104">The Office 365 IP Address and URL web service helps you better identify and differentiate Office 365 network traffic, making it easier for you to evaluate, configure, and stay up to date with changes.</span></span> <span data-ttu-id="7dbaa-105">Dieser REST-basierte Webdienst ersetzt die vorherigen herunterladbaren XML-Dateien, die am 2. Oktober 2018 ausliefen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-105">This REST-based web service replaces the previous XML downloadable files, which were phased out on October 2, 2018.</span></span>

<span data-ttu-id="7dbaa-106">Als Kunde oder Hersteller von Netzwerkumkreisgeräten können Sie den Build für den Webdienst für die Office 365-IP-Adress- und -FQDN-Einträge erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-106">As a customer or a network perimeter device vendor, you can build against the web service for Office 365 IP address and FQDN entries.</span></span> <span data-ttu-id="7dbaa-107">Sie können direkt in einem Webbrowser auf die Daten zugreifen, indem Sie diese URLs verwenden:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-107">You can access the data directly in a web browser using these URLs:</span></span>

- <span data-ttu-id="7dbaa-108">Verwenden Sie für die neueste Version der Office 365-URLs und -IP-Adressbereiche [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-108">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="7dbaa-109">Verwenden Sie für die Daten auf der Seite für die Office 365-URLs und -IP-Adressbereiche für Firewalls und Proxyserver [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-109">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="7dbaa-110">Um die neuesten Änderungen seit Juli 2018 zu erhalten (Datum, zu dem der Webdienst erstmalig verfügbar war), verwenden Sie [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-110">To get all the latest changes since July 2018 when the web service was first available, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>

<span data-ttu-id="7dbaa-111">Als Kunde können Sie diesen Webdienst für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-111">As a customer, you can use this web service to:</span></span>

- <span data-ttu-id="7dbaa-112">Aktualisieren Sie Ihre PowerShell-Skripte zum Abrufen von Daten auf Office 365-Endpunkten und zum Ändern der Formatierung für Ihre Netzwerkgeräte.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-112">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
- <span data-ttu-id="7dbaa-113">Verwenden Sie diese Informationen, um auf Clientcomputern bereitgestellte PAC-Dateien zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-113">Use this information to update PAC files deployed to client computers.</span></span>

<span data-ttu-id="7dbaa-114">Als Anbieter von Netzwerkperimetergeräten können Sie diesen Webdienst für Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-114">As a network perimeter device vendor, you can use this web service to:</span></span>

- <span data-ttu-id="7dbaa-115">Erstellen und testen Sie Gerätesoftware für den Download der Liste für die automatische Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-115">Create and test device software to download the list for automated configuration.</span></span>
- <span data-ttu-id="7dbaa-116">Suchen Sie die aktuelle Version.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-116">Check for the current version.</span></span>
- <span data-ttu-id="7dbaa-117">Rufen Sie die aktuellen Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-117">Get the current changes.</span></span>

> [!NOTE]
> <span data-ttu-id="7dbaa-118">Wenn Sie Azure ExpressRoute für die Verbindung mit Office 365 verwenden, lesen Sie bitte [Azure ExpressRoute for Office 365](azure-expressroute.md), um sich mit den Office 365-Diensten vertraut zu machen, die von Azure ExpressRoute unterstützt werden. </span><span class="sxs-lookup"><span data-stu-id="7dbaa-118">If you are using Azure ExpressRoute to connect to Office 365, please review [Azure ExpressRoute for Office 365](azure-expressroute.md) to familiarize yourself with the Office 365 services supported over Azure ExpressRoute.</span></span> <span data-ttu-id="7dbaa-119">Bitte lesen Sie auch den Artikel [Office 365-URLs und -IP-Adressbereiche](urls-and-ip-address-ranges.md), um zu verstehen, welche Netzwerke für Office 365-Apps eine Internetverbindung benötigen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-119">Also review the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to understand which network requests for Office 365 applications require Internet connectivity.</span></span> <span data-ttu-id="7dbaa-120">Das wird Ihnen helfen, Ihre Umkreis-Sicherheitsgeräte besser zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-120">This will help to better configure your perimeter security devices.</span></span>

<span data-ttu-id="7dbaa-121">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-121">For more information, see:</span></span>

- [<span data-ttu-id="7dbaa-122">Ankündigungsblogbeitrag im Office 365 Tech-Community-Forum</span><span class="sxs-lookup"><span data-stu-id="7dbaa-122">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [<span data-ttu-id="7dbaa-123">Office 365-Tech-Community-Forum für Fragen zur Verwendung der Webdienste</span><span class="sxs-lookup"><span data-stu-id="7dbaa-123">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a><span data-ttu-id="7dbaa-124">Allgemeine Parameter</span><span class="sxs-lookup"><span data-stu-id="7dbaa-124">Common parameters</span></span>

<span data-ttu-id="7dbaa-125">Diese Parameter gelten für sämtliche Webdienstmethoden:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-125">These parameters are common across all the web service methods:</span></span>

- <span data-ttu-id="7dbaa-126">**format=<JSON | CSV>** – standardmäßig ist die zurückgegebene Datei als JSON formatiert.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-126">**format=<JSON | CSV>** — By default, the returned data format is JSON.</span></span> <span data-ttu-id="7dbaa-127">Verwenden Sie diesen optionalen Parameter, um die Daten in durch Trennzeichen getrennten Werten (CSV-Format) zurückzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-127">Use this optional parameter to return the data in comma-separated values (CSV) format.</span></span>
- <span data-ttu-id="7dbaa-128">**ClientRequestId=\<guid>** – eine erforderliche GUID, die Sie für die Clientzuordnung generieren.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-128">**ClientRequestId=\<guid>** — A required GUID that you generate for client association.</span></span> <span data-ttu-id="7dbaa-129">Generieren Sie eine eindeutige GUID für jeden Computer, von dem der Webdienst aufgerufen wird (die auf dieser Seite enthaltenen Skripts generieren eine GUID für Sie).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-129">Generate a unique GUID for each machine that calls the web service (the scripts included on this page generate a GUID for you).</span></span> <span data-ttu-id="7dbaa-130">Nutzen Sie nicht die in den folgenden Beispielen dargestellten GUIDs, da sie künftig durch den Webdienst blockiert werden könnten.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-130">Do not use the GUIDs shown in the following examples because they might be blocked by the web service in the future.</span></span> <span data-ttu-id="7dbaa-131">Das GUID-Format ist _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, wobei x eine hexadezimale Zahl darstellt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-131">GUID format is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, where x represents a hexadecimal number.</span></span>

  <span data-ttu-id="7dbaa-132">Wenn Sie eine GUID generieren möchten, können Sie den PowerShell-Befehl [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) verwenden oder einen Onlinedienst wie den [Online GUID Generator](https://www.guidgenerator.com/) nutzen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-132">To generate a GUID, you can use the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell command, or use an online service such as [Online GUID Generator](https://www.guidgenerator.com/).</span></span>

## <a name="version-web-method"></a><span data-ttu-id="7dbaa-133">Versionswebmethode</span><span class="sxs-lookup"><span data-stu-id="7dbaa-133">Version web method</span></span>

<span data-ttu-id="7dbaa-134">Microsoft aktualisiert die Office 365-IP-Adress- und -FQDN-Einträge am Ende jeden Monats.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-134">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month.</span></span> <span data-ttu-id="7dbaa-135">Out-of-Band-Updates werden manchmal aufgrund von Supportfällen, Sicherheitsupdates oder sonstigen betrieblichen Anforderungen veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-135">Out-of-band updates are sometimes published due to support incidents, security updates or other operational requirements.</span></span>

<span data-ttu-id="7dbaa-136">Den Daten für jede veröffentlichte Instanz wird eine Versionsnummer zugewiesen, und mit der Versionswebmethode können Sie nach der neuesten Version jeder Office 365-Dienstinstanz suchen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-136">The data for each published instance is assigned a version number, and the version web method enables you to check for the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="7dbaa-137">Wir empfehlen, die Version nicht mehr als einmal pro Stunde zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-137">We recommend that you check the version not more than once an hour.</span></span>

<span data-ttu-id="7dbaa-138">Parameter für die Versionswebmethode sind:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-138">Parameters for the version web method are:</span></span>

- <span data-ttu-id="7dbaa-139">**AllVersions=<true | false>** – standardmäßig ist die zurückgegebene Version die neueste.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-139">**AllVersions=<true | false>** — By default, the version returned is the latest.</span></span> <span data-ttu-id="7dbaa-140">Nehmen Sie diesen optionalen Parameter mit auf, um alle veröffentlichten Versionen seit dem ersten Release des Webdiensts anzufordern.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-140">Include this optional parameter to request all published versions since the web service was first released.</span></span>
- <span data-ttu-id="7dbaa-141">**Format=<JSON | CSV | RSS>** – zusätzlich zu den Formaten JSON und CSV unterstützt die Versionswebmethode auch RSS.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-141">**Format=<JSON | CSV | RSS>** — In addition to the JSON and CSV formats, the version web method also supports RSS.</span></span> <span data-ttu-id="7dbaa-142">Diesen optionalen Parameter können Sie zusammen mit dem Parameter _AllVersions=true_ verwenden, um einen RSS-Feed anzufordern, der mit Outlook oder anderen RSS-Readern genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-142">You can use this optional parameter along with the _AllVersions=true_ parameter to request an RSS feed that can be used with Outlook or other RSS readers.</span></span>
- <span data-ttu-id="7dbaa-143">**Instance=<Weltweit | China | Deutschland | USGovDoD | USGovGCCHigh>** – dieser optionale Parameter gibt die Instanz an, für die die Version zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This optional parameter specifies the instance to return the version for.</span></span> <span data-ttu-id="7dbaa-144">Wenn nicht angegeben, werden alle Instanzen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-144">If omitted, all instances are returned.</span></span> <span data-ttu-id="7dbaa-145">Gültige Instanzen sind: Weltweit, China, Deutschland, USGovDoD, USGovGCCHigh.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-145">Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span>

<span data-ttu-id="7dbaa-146">Die Rate der Versionswebmethode ist nicht beschränkt, und sie gibt nie 429-HTTP-Antwortcodes zurück.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-146">The version web method is not rate limited and does not ever return 429 HTTP Response Codes.</span></span> <span data-ttu-id="7dbaa-147">Die Antwort auf die Versionswebmethode enthält einen Cache-Control-Header, der empfiehlt, die Daten für eine Stunde zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-147">The response to the version web method does include a cache-control header recommending caching of the data for 1 hour.</span></span> <span data-ttu-id="7dbaa-148">Das Ergebnis der Versionswebmethode kann ein einzelner Datensatz oder ein Array aus Datensätzen sein.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-148">The result from the version web method can be a single record or an array of records.</span></span> <span data-ttu-id="7dbaa-149">Die Elemente jedes Datensatzes sind:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-149">The elements of each record are:</span></span>

- <span data-ttu-id="7dbaa-150">instance – die Kurzform der Office 365-Serviceinstanz.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-150">instance — The short name of the Office 365 service instance.</span></span>
- <span data-ttu-id="7dbaa-151">latest – die neueste Version für Endpunkte der angegebenen Instanz.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-151">latest — The latest version for endpoints of the specified instance.</span></span>
- <span data-ttu-id="7dbaa-152">versions – eine Liste aller vorherigen Versionen für die angegebene Instanz.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-152">versions — A list of all previous versions for the specified instance.</span></span> <span data-ttu-id="7dbaa-153">Dieses Element wird nur einbezogen, wenn der Parameter _AllVersions_ wahr ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-153">This element is only included if the _AllVersions_ parameter is true.</span></span>

### <a name="examples"></a><span data-ttu-id="7dbaa-154">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-154">Examples:</span></span>

<span data-ttu-id="7dbaa-155">Anfrage-URI – Beispiel 1: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-155">Example 1 request URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-p113">Dieser URI gibt die aktuelle Version jeder Instanz des Office 365-Diensts zurück. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p113">This URI returns the latest version of each Office 365 service instance. Example result:</span></span>

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> <span data-ttu-id="7dbaa-p114">Die GUID für den Parameter „ClientRequestID“ in diesen URIs dient nur als Beispiel. Um die Webdienst-URIs auszuprobieren, erstellen Sie Ihre eigene GUID. Die in den folgenden Beispielen gezeigten GUIDs werden möglicherweise in Zukunft vom Webdienst gesperrt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p114">The GUID for the ClientRequestID parameter in these URIs are only an example. To try the web service URIs out, generate your own GUID. The GUIDs shown in these examples may be blocked by the web service in the future.</span></span>

<span data-ttu-id="7dbaa-161">Anfrage-URI – Beispiel 2: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-161">Example 2 request URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-p115">Dieser URI gibt die aktuelle Version der angegebenen Instanz des Office 365-Diensts zurück. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p115">This URI returns the latest version of the specified Office 365 service instance. Example result:</span></span>

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="7dbaa-164">Anfrage-URI – Beispiel 3: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-164">Example 3 request URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-p116">Dieser URI zeigt die Ausgabe im CSV-Format an. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p116">This URI shows output in CSV format. Example result:</span></span>

```csv
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="7dbaa-167">Anfrage-URI – Beispiel 4: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-167">Example 4 request URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-p117">Dieser URI zeigt alle vorherigen Versionen an, die für die Dienstinstanz von Office 365 weltweit veröffentlicht wurden. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p117">This URI shows all prior versions that have been published for the Office 365 worldwide service instance. Example result:</span></span>

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

<span data-ttu-id="7dbaa-170">RSS-Feed-URI – Beispiel 5: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-170">Example 5 RSS Feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span></span>

<span data-ttu-id="7dbaa-p118">Dieser URI zeigt einen RSS-Feed der veröffentlichten Versionen, die Links zu der Liste der Änderungen für jede Version enthalten. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p118">This URI shows an RSS feed of the published versions that include links to the list of changes for each version. Example result:</span></span>

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a><span data-ttu-id="7dbaa-173">Endpunktwebmethode</span><span class="sxs-lookup"><span data-stu-id="7dbaa-173">Endpoints web method</span></span>

<span data-ttu-id="7dbaa-174">Die Endpunktwebmethode gibt alle Datensätze für IP-Adressbereiche und URLs zurück, die den Office 365-Dienst bilden.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-174">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service.</span></span> <span data-ttu-id="7dbaa-175">Die neuesten Daten aus der Endpunkt-Webmethode sollten immer für die Konfiguration von Netzwerkgeräten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-175">The latest data from the endpoints web method should always be used for network device configuration.</span></span> <span data-ttu-id="7dbaa-176">Microsoft kündigt neue Ergänzungen 30 Tage vor der Veröffentlichung an, um Ihnen Zeit zum Aktualisieren von Zugriffssteuerungs- und Proxyserver-Umgehungslisten zu lassen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-176">Microsoft provides advance notice 30 days prior to publishing new additions to give you time to update access control lists and proxy server bypass lists.</span></span> <span data-ttu-id="7dbaa-177">Wir empfehlen Ihnen, die Endpunktwebmethode erst wieder einzusetzen, wenn die Versionswebmethode besagt, dass eine neue Version der Daten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-177">We recommend that you only call the endpoints web method again when the version web method indicates that a new version of the data is available.</span></span>

<span data-ttu-id="7dbaa-178">Parameter für die Endpunktwebmethode sind:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-178">Parameters for the endpoints web method are:</span></span>

- <span data-ttu-id="7dbaa-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** – eine durch Trennzeichen getrennte Liste von Dienstbereichen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — A comma-separated list of service areas.</span></span> <span data-ttu-id="7dbaa-180">Gültige Elemente sind _Common_, _Exchange_, _SharePoint_ und _Skype_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-180">Valid items are _Common_, _Exchange_, _SharePoint_, and _Skype_.</span></span> <span data-ttu-id="7dbaa-181">Da _Common_-Dienstbereich-Elemente Voraussetzung für alle anderen Dienstbereiche sind, bezieht der Webdienst sie stets mit ein.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-181">Because _Common_ service area items are a prerequisite for all other service areas, the web service always includes them.</span></span> <span data-ttu-id="7dbaa-182">Wenn Sie diesen Parameter nicht miteinschließen, werden alle Dienstbereiche zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-182">If you do not include this parameter, all service areas are returned.</span></span>
- <span data-ttu-id="7dbaa-183">**TenantName=<tenant_name>** – Ihr Office 365-Mandantenname.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-183">**TenantName=<tenant_name>** — Your Office 365 tenant name.</span></span> <span data-ttu-id="7dbaa-184">Der Webdienst übernimmt Ihren angegebenen Namen und fügt ihn in URL-Teile ein, die den Mandantennamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-184">The web service takes your provided name and inserts it in parts of URLs that include the tenant name.</span></span> <span data-ttu-id="7dbaa-185">Wenn Sie keinen Mandantennamen angeben, haben diese URL-Teile das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-185">If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span>
- <span data-ttu-id="7dbaa-186">**NoIPv6=<true | false>** – legen Sie für diesen Wert _true_ fest, um IPv6-Adressen von der Ausgabe auszuschließen, wenn Sie IPv6 nicht in Ihrem Netzwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-186">**NoIPv6=<true | false>** — Set the value to _true_ to exclude IPv6 addresses from the output if you don't use IPv6 in your network.</span></span>
- <span data-ttu-id="7dbaa-187">**Instance=<Weltweit | China | Deutschland | USGovDoD | USGovGCCHigh>** – dieser erforderliche Parameter gibt die Instanz an, von der die Endpunkte zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This required parameter specifies the instance from which to return the endpoints.</span></span> <span data-ttu-id="7dbaa-188">Gültige Instanzen sind: _Weltweit_, _China_, _Deutschland_, _USGovDoD_ und _USGovGCCHigh_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-188">Valid instances are: _Worldwide_, _China_, _Germany_, _USGovDoD_, and _USGovGCCHigh_.</span></span>

<span data-ttu-id="7dbaa-189">Wenn Sie die Endpunktwebmethode zu häufig von derselben Client-IP-Adresse abrufen, erhalten Sie möglicherweise den HTTP-Antwortcode _429 (zu viele Anforderungen)_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-189">If you call the endpoints web method too many times from the same client IP address, you might receive HTTP response code _429 (Too Many Requests)_.</span></span> <span data-ttu-id="7dbaa-190">Wenn Sie diesen Antwortcode erhalten, warten Sie eine Stunde, bevor Sie Ihre Anforderung wiederholen, oder generieren Sie eine neue GUID für sie.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-190">If you get this response code, wait 1 hour before repeating your request, or generate a new GUID for the request.</span></span> <span data-ttu-id="7dbaa-191">Als allgemein bewährte Methode rufen Sie die Endpunktwebmethode nur auf, wenn die Versionswebmethode besagt, dass eine neue Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-191">As a general best practice, only call the endpoints web method when the version web method indicates that a new version is available.</span></span>

<span data-ttu-id="7dbaa-192">Das Ergebnis der Endpunktwebmethode ist ein Array aus Datensätzen, in dem jeder Datensatz einen bestimmten Endpunktsatz darstellt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-192">The result from the endpoints web method is an array of records in which each record represents a specific endpoint set.</span></span> <span data-ttu-id="7dbaa-193">Die Elemente für jeden Datensatz sind:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-193">The elements for each record are:</span></span>

- <span data-ttu-id="7dbaa-194">id – die unveränderliche ID-Nummer des Endpunktsatzes.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-194">id — The immutable id number of the endpoint set.</span></span>
- <span data-ttu-id="7dbaa-195">serviceArea – der Servicebereich, zu dem Folgendes gehört: _Common_, _Exchange_, _SharePoint_ oder _Skype_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-195">serviceArea — The service area that this is part of: _Common_, _Exchange_, _SharePoint_, or _Skype_.</span></span>
- <span data-ttu-id="7dbaa-196">urls – URLs für den Endpunktsatz.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-196">urls — URLs for the endpoint set.</span></span> <span data-ttu-id="7dbaa-197">ein JSON-Array von DNS-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-197">A JSON array of DNS records.</span></span> <span data-ttu-id="7dbaa-198">Weggelassen, falls leer.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-198">Omitted if blank.</span></span>
- <span data-ttu-id="7dbaa-199">tcpPorts – TCP-Ports für den Endpunktsatz.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-199">tcpPorts — TCP ports for the endpoint set.</span></span> <span data-ttu-id="7dbaa-200">Alle Ports-Elemente sind als eine durch Trennzeichen getrennte Liste von Ports oder Portbereichen formatiert, die durch einen Bindestrich (-) getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-200">All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-).</span></span> <span data-ttu-id="7dbaa-201">Ports werden auf alle IP-Adressen und alle URLs im Endpunktsatz für eine bestimmte Kategorie angewendet.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-201">Ports apply to all IP addresses and all URLs in the endpoint set for a given category.</span></span> <span data-ttu-id="7dbaa-202">Weggelassen, falls leer.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-202">Omitted if blank.</span></span>
- <span data-ttu-id="7dbaa-203">udpPorts – UDP-Ports für die IP-Adressbereiche in diesem Endpunktsatz.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-203">udpPorts — UDP ports for the IP address ranges in this endpoint set.</span></span> <span data-ttu-id="7dbaa-204">Weggelassen, falls leer.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-204">Omitted if blank.</span></span>
- <span data-ttu-id="7dbaa-205">ips – die zu diesem Endpunktsatz gehörigen IP-Adressbereiche (den aufgeführten TCP- oder UDP-Ports zugeordnet).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-205">ips — The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports.</span></span> <span data-ttu-id="7dbaa-206">ein JSON-Array von IP-Adressbereichen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-206">A JSON array of IP address ranges.</span></span> <span data-ttu-id="7dbaa-207">Weggelassen, falls leer.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-207">Omitted if blank.</span></span>
- <span data-ttu-id="7dbaa-208">category – die Kategorie „Konnektivität“ des Endpunktsatzes.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-208">category — The connectivity category for the endpoint set.</span></span> <span data-ttu-id="7dbaa-209">Gültige Werte sind _Optimize_, _Allow_ und _Default_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-209">Valid values are _Optimize_, _Allow_, and _Default_.</span></span> <span data-ttu-id="7dbaa-210">Wenn Sie die Ausgabe der Endpunktwebmethode für die Kategorie einer bestimmten IP-Adresse oder URL durchsuchen, kann die Abfrage mehrere Kategorien zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-210">If you search the endpoints web method output for the category of a specific IP address or URL, it is possible that your query will return multiple categories.</span></span> <span data-ttu-id="7dbaa-211">Folgen Sie in diesem Fall der Empfehlung für die Kategorie mit der höchsten Priorität.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-211">In such a case, follow the recommendation for the highest priority category.</span></span> <span data-ttu-id="7dbaa-212">Wenn der Endpunkt beispielsweise sowohl in _Optimize_ als auch _Allow_ angezeigt wird, sollten Sie den Anforderungen für _Optimize_ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-212">For example, if the endpoint appears in both _Optimize_ and _Allow_, you should follow the requirements for _Optimize_.</span></span> <span data-ttu-id="7dbaa-213">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-213">Required.</span></span>
- <span data-ttu-id="7dbaa-214">expressRoute – _True_, wenn dieser Endpunktsatz über ExpressRoute weitergeleitet wird; _False_, wenn nicht.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-214">expressRoute — _True_ if this endpoint set is routed over ExpressRoute, _False_ if not.</span></span>
- <span data-ttu-id="7dbaa-215">required – _True_, wenn für diesen Endpunktsatz Konnektivität erforderlich ist, damit Office 365 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-215">required — _True_ if this endpoint set is required to have connectivity for Office 365 to be supported.</span></span> <span data-ttu-id="7dbaa-216">_False_, wenn dieser Endpunktsatz optional ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-216">_False_ if this endpoint set is optional.</span></span>
- <span data-ttu-id="7dbaa-217">notes – für optionale Endpunkte beschreibt dieser Text die Office 365-Funktionalität, die nicht verfügbar wäre, wenn der Zugriff auf IP-Adressen oder URLs in diesem Endpunktsatz nicht auf Netzwerkebene möglich ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-217">notes — For optional endpoints, this text describes Office 365 functionality that would be unavailable if IP addresses or URLs in this endpoint set cannot be accessed at the network layer.</span></span> <span data-ttu-id="7dbaa-218">Weggelassen, falls leer.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-218">Omitted if blank.</span></span>

### <a name="examples"></a><span data-ttu-id="7dbaa-219">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-219">Examples:</span></span>

<span data-ttu-id="7dbaa-220">Anfrage-URI – Beispiel 1: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-220">Example 1 request URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-221">Dieser URI ruft alle Endpunkte für die Instanz von Office 365 weltweit für alle Workloads ab.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-221">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads.</span></span> <span data-ttu-id="7dbaa-222">Das Beispielergebnis zeigt einen Auszug der Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-222">Example result that shows an excerpt of the output:</span></span>

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

<span data-ttu-id="7dbaa-223">Beachten Sie, dass die vollständige Ausgabe der Anforderung in diesem Beispiel weitere Endpunktsätze enthalten würde.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-223">Note that the full output of the request in this example would contain other endpoint sets.</span></span>

<span data-ttu-id="7dbaa-224">Anfrage-URI – Beispiel 2: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-224">Example 2 request URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-225">In diesem Beispiel werden nur Endpunkte für die Instanz von Office 365 weltweit für Exchange Online und Abhängigkeiten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-225">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>

<span data-ttu-id="7dbaa-226">Die Ausgabe für Beispiel 2 ähnelt Beispiel 1 mit dem Unterschied, dass die Ergebnisse keine Endpunkte für SharePoint Online oder Skype for Business Online enthalten würden.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-226">The output for example 2 is similar to example 1 except that the results would not include endpoints for SharePoint Online or Skype for Business Online.</span></span>

## <a name="changes-web-method"></a><span data-ttu-id="7dbaa-227">Änderungswebmethode</span><span class="sxs-lookup"><span data-stu-id="7dbaa-227">Changes web method</span></span>

<span data-ttu-id="7dbaa-228">Die Änderungswebmethode gibt die neuesten Updates zurück, die veröffentlicht wurden, typischerweise die Änderungen des vorherigen Monats an IP-Adressbereichen und URLs.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-228">The changes web method returns the most recent updates that have been published, typically the previous month's changes to IP address ranges and URLs.</span></span>

<span data-ttu-id="7dbaa-229">Die wichtigsten Änderungen an Endpunktdaten sind neue URLs und IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-229">The most critical changes to endpoints data are new URLs and IP addresses.</span></span> <span data-ttu-id="7dbaa-230">Wenn eine IP-Adresse nicht zu einer Firewall-Zugriffssteuerungsliste oder eine URL nicht zu einer Proxyserver-Umgehungsliste hinzugefügt wird, kann dies zu einem Ausfall für Benutzer von Office 365 auf diesem Netzwerkgerät führen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-230">Failure to add an IP address to a firewall access control list or a URL to a proxy server bypass list can cause an outage for Office 365 users behind that network device.</span></span> <span data-ttu-id="7dbaa-231">Ungeachtet betrieblicher Anforderungen werden neue Endpunkte 30 Tage vor dem Datum, an dem die Endpunkte bereitgestellt werden, im Webdienst veröffentlicht, um Ihnen Zeit zum Aktualisieren von Zugriffssteuerungs- und Proxyserver-Umgehungslisten zu lassen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-231">Notwithstanding operational requirements, new endpoints are published to the web service 30 days in advance of the date the endpoints are provisioned for use to give you time to update access control lists and proxy server bypass lists.</span></span>

<span data-ttu-id="7dbaa-232">Die nötigen Parameter für die Änderungswebmethode sind:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-232">The required parameter for the changes web method is:</span></span>

- <span data-ttu-id="7dbaa-233">**Version=\<YYYYMMDDNN>** – Erforderlicher URL-Routenparameter.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-233">**Version=\<YYYYMMDDNN>** — Required URL route parameter.</span></span> <span data-ttu-id="7dbaa-234">Dieser Wert steht für die Version, die derzeit implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-234">This value is the version that you have currently implemented.</span></span> <span data-ttu-id="7dbaa-235">Der Webdienst wird die Änderungen seit dieser Version zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-235">The web service will return the changes since that version.</span></span> <span data-ttu-id="7dbaa-236">Das Format ist _JJJJMMTTNN_, wobei _NN_ eine natürliche Zahl ist, die erhöht wird, falls mehrere Versionen am gleichen Tag herausgegeben werden müssen. Dabei steht _00_ für das erste Update an einen bestimmten Tag.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-236">The format is _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day, with _00_ representing the first update for a given day.</span></span> <span data-ttu-id="7dbaa-237">Der Webdienst erfordert, dass der _Versions_-Parameter genau 10 Ziffern enthält.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-237">The web service requires the _version_ parameter to contain exactly 10 digits.</span></span>

<span data-ttu-id="7dbaa-238">Für die Änderungswebmethode sind die Gebühren auf dieselbe Art und Weise beschränkt wie bei der Endpunktwebmethode.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-238">The changes web method is rate limited in the same way as the endpoints web method.</span></span> <span data-ttu-id="7dbaa-239">Wenn Sie einen 429-HTTP-Antwortcode erhalten, warten Sie eine Stunde, bevor Sie Ihre Anforderung wiederholen, oder generieren Sie eine neue GUID für sie.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-239">If you receive a 429 HTTP response code, wait 1 hour before repeating your request or generate a new GUID for the request.</span></span>

<span data-ttu-id="7dbaa-240">Das Ergebnis der Änderungswebmethode ist ein Array aus Datensätzen, in dem jeder Datensatz eine Änderung in einer bestimmten Version der Endpunkte darstellt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-240">The result from the changes web method is an array of records in which each record represents a change in a specific version of the endpoints.</span></span> <span data-ttu-id="7dbaa-241">Die Elemente für jeden Datensatz sind:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-241">The elements for each record are:</span></span>

- <span data-ttu-id="7dbaa-242">id – die unveränderliche ID des Änderungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-242">id — The immutable id of the change record.</span></span>
- <span data-ttu-id="7dbaa-243">endpointSetId – die ID des Endpunktsatz-Datensatzes, der geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-243">endpointSetId — The ID of the endpoint set record that is changed.</span></span>
- <span data-ttu-id="7dbaa-244">disposition – beschreibt, was die Änderung am Endpunktsatz bewirkt hat.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-244">disposition — Describes what the change did to the endpoint set record.</span></span> <span data-ttu-id="7dbaa-245">Die Werte sind _change_, _add_ oder _remove_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-245">Values are _change_, _add_, or _remove_.</span></span>
- <span data-ttu-id="7dbaa-246">Auswirkung – nicht alle Änderungen sind für jede Umgebung gleichermaßen wichtig.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-246">impact — Not all changes will be equally important to every environment.</span></span> <span data-ttu-id="7dbaa-247">Dieses Element beschreibt die erwartete Wirkung auf die Umgebung eines Unternehmensnetzwerkumkreises infolge dieser Änderung.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-247">This element describes the expected impact to an enterprise network perimeter environment as a result of this change.</span></span> <span data-ttu-id="7dbaa-248">Dieses Element wird nur in Änderungsdatensätze der Version **2018112800** und höher einbezogen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-248">This element is included only in change records of version **2018112800** and later.</span></span> <span data-ttu-id="7dbaa-249">Die Optionen für die Wirkung sind: AddedIp – eine IP-Adresse wurde zu Office 365 hinzugefügt und ist in Kürze im Dienst online.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-249">Options for the impact are: — AddedIp – An IP address was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="7dbaa-250">Dies stellt eine Änderung dar, die Sie an einer Firewall oder einem anderem Netzwerkumkreisgerät der Schicht 3 vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-250">This represents a change you need to take on a firewall or other layer 3 network perimeter device.</span></span> <span data-ttu-id="7dbaa-251">Wenn Sie dies nicht hinzufügen, bevor wir starten, erleben Sie möglicherweise einen Ausfall.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-251">If you don’t add this before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="7dbaa-252">– AddedUrl – ein URL wurde Office 365 hinzugefügt und ist in Kürze im Dienst live.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-252">— AddedUrl – A URL was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="7dbaa-253">Dies stellt eine Änderung dar, die Sie auf einem Netzwerkumkreisgerät für die Proxyserver- oder URL-Analyse vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-253">This represents a change you need to take on a proxy server or URL parsing network perimeter device.</span></span> <span data-ttu-id="7dbaa-254">Wenn Sie diesen URL nicht hinzufügen, bevor wir starten, erleben Sie möglicherweise einen Ausfall.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-254">If you don’t add this URL before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="7dbaa-255">– AddedIpAndUrl: Sowohl eine IP-Adresse als auch ein URL wurden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-255">— AddedIpAndUrl — Both an IP address and a URL were added.</span></span> <span data-ttu-id="7dbaa-256">Dies stellt eine Änderung dar, die Sie entweder auf einem Firewall-Gerät der Schicht 3 oder einem Gerät zur Proxyserver- oder URL-Analyse vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-256">This represents a change you need to take on either a firewall layer 3 device or a proxy server or URL parsing device.</span></span> <span data-ttu-id="7dbaa-257">Wenn Sie diese IP bzw. URL nicht hinzufügen, bevor wir starten, erleben Sie möglicherweise einen Ausfall.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-257">If you don’t add this IP/URL pair before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="7dbaa-258">– RemovedIpOrUrl: Mindestens eine IP-Adresse oder URL wurde aus Office 365 entfernt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-258">— RemovedIpOrUrl – At least one IP address or URL was removed from Office 365.</span></span> <span data-ttu-id="7dbaa-259">Sie entfernen die Netzwerkendpunkte von ihren Umkreisgeräten, aber dafür gibt es keinen Stichtag.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-259">Remove the network endpoints from your perimeter devices, but there’s no deadline for you to do this.</span></span>
  <span data-ttu-id="7dbaa-260">– ChangedIsExpressRoute: Das Supportattribut „Express Route“ wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-260">— ChangedIsExpressRoute – The ExpressRoute support attribute was changed.</span></span> <span data-ttu-id="7dbaa-261">Wenn Sie ExpressRoute verwenden, müssen Sie möglicherweise je nach Konfiguration Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-261">If you use ExpressRoute, you might need to take action depending on your configuration.</span></span>
  <span data-ttu-id="7dbaa-262">– MovedIpOrUrl: Eine IP-Adresse oder URL wurde zwischen diesem Endpunktsatz und einem anderen verschoben.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-262">— MovedIpOrUrl – We moved an IP address or Url between this endpoint set and another one.</span></span> <span data-ttu-id="7dbaa-263">Im Allgemeinen ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-263">Generally no action is required.</span></span>
  <span data-ttu-id="7dbaa-264">– RemovedDuplicateIpOrUrl: Eine doppelte IP-Adresse oder URL wurde entfernt, diese ist aber immer noch für Office 365 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-264">— RemovedDuplicateIpOrUrl – We removed a duplicate IP address or Url but it’s still published for Office 365.</span></span> <span data-ttu-id="7dbaa-265">Im Allgemeinen ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-265">Generally no action is required.</span></span>
  <span data-ttu-id="7dbaa-266">– OtherNonPriorityChanges: Es wurde etwas weniger wichtiges als alle anderen Optionen geändert, z. B. die Inhalte eines Notizfelds.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-266">— OtherNonPriorityChanges – We changed something less critical than all of the other options, such as the contents of a note field.</span></span>
- <span data-ttu-id="7dbaa-267">version – die Version des veröffentlichten Endpunktsatzes, in dem die Änderung eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-267">version — The version of the published endpoint set in which the change was introduced.</span></span> <span data-ttu-id="7dbaa-268">Versionsnummern besitzen das Format _JJJJMMTTNN_, wobei _NN_ eine natürliche Zahl ist, die erhöht wird, falls mehrere Versionen am gleichen Tag herausgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-268">Version numbers are of the format _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
- <span data-ttu-id="7dbaa-269">previous – eine Unterstruktur, die vorherige Werte von Änderungselementen im Endpunktsatz angibt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-269">previous — A substructure detailing previous values of changed elements on the endpoint set.</span></span> <span data-ttu-id="7dbaa-270">Dies ist bei neu hinzugefügten Endpunktsätzen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-270">This will not be included for newly added endpoint sets.</span></span> <span data-ttu-id="7dbaa-271">Umfasst _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ und _notes_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-271">Includes  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="7dbaa-272">current – eine Unterstruktur, die aktualisierte Werte von Änderungselementen im Endpunktsatz angibt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-272">current — A substructure detailing updated values of changes elements on the endpoint set.</span></span> <span data-ttu-id="7dbaa-273">Umfasst _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ und _notes_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-273">Includes _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="7dbaa-274">add – eine Unterstruktur, die Elemente angibt, die zu Endpunktsatzsammlungen hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-274">add — A substructure detailing items to be added to endpoint set collections.</span></span> <span data-ttu-id="7dbaa-275">Wird weggelassen, wenn es keine Ergänzungen gibt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-275">Omitted if there are no additions.</span></span>
  <span data-ttu-id="7dbaa-276">– effectiveDate: definiert die Daten, wann die Ergänzungen live im Dienst sind.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-276">— effectiveDate — Defines the data when the additions will be live in the service.</span></span>
  <span data-ttu-id="7dbaa-277">– ips: Elemente, die dem Array _ips_ hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-277">— ips — Items to be added to the _ips_ array.</span></span>
  <span data-ttu-id="7dbaa-278">– urls: Elemente, die zum Array _urls_ hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-278">— urls- Items to be added to the _urls_ array.</span></span>
- <span data-ttu-id="7dbaa-279">remove – eine Unterstruktur, die aus dem Endpunktsatz zu entfernende Elemente angibt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-279">remove — A substructure detailing items to be removed from the endpoint set.</span></span> <span data-ttu-id="7dbaa-280">Wird weggelassen, wenn es keine Entfernungen gibt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-280">Omitted if there are no removals.</span></span>
  <span data-ttu-id="7dbaa-281">– ips: Elemente, die aus dem Array _ips_ entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-281">— ips — Items to be removed from the _ips_ array.</span></span>
  <span data-ttu-id="7dbaa-282">– urls: Elemente, die aus dem Array _urls_ entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-282">— urls- Items to be removed from the _urls_ array.</span></span>

### <a name="examples"></a><span data-ttu-id="7dbaa-283">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-283">Examples:</span></span>

<span data-ttu-id="7dbaa-284">Anfrage-URI – Beispiel 1: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-284">Example 1 request URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-p144">Dies fordert alle vorherigen Änderungen an der Dienstinstanz von Office 365 weltweit an. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p144">This requests all previous changes to the Office 365 worldwide service instance. Example result:</span></span>

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

<span data-ttu-id="7dbaa-287">Anfrage-URI – Beispiel 2: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="7dbaa-287">Example 2 request URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="7dbaa-p145">Dies fordert Änderungen seit der angegebenen Version der Instanz von Office 365 weltweite an. Die angegebene Version ist in diesem Fall die neueste. Beispielergebnis:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p145">This requests changes since the specified version to the Office 365 Worldwide instance. In this case, the version specified is the latest. Example result:</span></span>

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a><span data-ttu-id="7dbaa-291">PowerShell-Skript</span><span class="sxs-lookup"><span data-stu-id="7dbaa-291">Example PowerShell Script</span></span>

<span data-ttu-id="7dbaa-292">Sie können dieses PowerShell-Skript ausführen, um festzustellen, ob es Aktionen gibt, die Sie für aktualisierte Daten setzen müssen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-292">You can run this PowerShell script to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="7dbaa-293">Sie können dieses Skript als geplante Aufgabe ausführen, um nach einer Versionsaktualisierung zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-293">You can run this script as a scheduled task to check for a version update.</span></span> <span data-ttu-id="7dbaa-294">Um zu vermeiden, dass der Webdienst überlastet ist, versuchen Sie, das Skript nicht mehr als einmal pro Stunde auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-294">To avoid excessive load on the web service, try not to run the script more than once an hour.</span></span>

<span data-ttu-id="7dbaa-295">Dieses Skript führt folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-295">The script does the following:</span></span>

- <span data-ttu-id="7dbaa-296">Überprüfen der Versionsnummer der aktuellen Office 365 weltweit-Instanzendpunkte durch Aufrufen der Webdienst-REST-API.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-296">Checks the version number of the current Office 365 Worldwide instance endpoints by calling the web service REST API.</span></span>
- <span data-ttu-id="7dbaa-297">Suchen nach einer aktuellen Versionsdatei unter _$Env:TEMP\O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-297">Checks for a current version file at _$Env:TEMP\O365_endpoints_latestversion.txt_.</span></span> <span data-ttu-id="7dbaa-298">Der Pfad der globalen Variablen **$Env:TEMP** ist in der Regel _C:\Users\\<username\>\AppData\Local\Temp_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-298">The path of the global variable **$Env:TEMP** is usually _C:\Users\\<username\>\AppData\Local\Temp_.</span></span>
- <span data-ttu-id="7dbaa-299">Wenn dies das erste Mal ist, dass das Skript ausgeführt wurde, gibt es die aktuelle Version sowie alle aktuellen IP-Adressen und URLs zurück, schreibt die Endpunkt-Version in die Datei _$Env:TEMP\O365_endpoints_latestversion.txt_ und die Endpunkt-Datenausgabe in die Datei _$Env:TEMP\O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-299">If this is the first time the script has been run, the script returns the current version and all current IP addresses and URLs, writes the endpoints version to the file _$Env:TEMP\O365_endpoints_latestversion.txt_ and the endpoints data output to the file _$Env:TEMP\O365_endpoints_data.txt_.</span></span> <span data-ttu-id="7dbaa-300">Sie können den Pfad und/oder den Namen der Ausgabedatei ändern, indem Sie die folgenden Zeilen bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-300">You can modify the path and/or name of the output file by editing these lines:</span></span>

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- <span data-ttu-id="7dbaa-301">Wenn die neueste Webdienst-Version bei jeder nachfolgenden Ausführung des Skripts mit der Version in der Datei _O365_endpoints_latestversion.txt_ identisch ist, wird das Skript beendet, ohne Änderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-301">On each subsequent execution of the script, if the latest web service version is identical to the version in the _O365_endpoints_latestversion.txt_ file, the script exits without making any changes.</span></span>
- <span data-ttu-id="7dbaa-302">Wenn die neueste Webdienst-Version neuer als die Version in der Datei _O365_endpoints_latestversion.txt_ ist, gibt das Skript die Endpunkte und Filter für die Endpunkte der Kategorien **Allow** und **Optimize** zurück, aktualisiert die Version in der Datei _O365_endpoints_latestversion.txt_ und schreibt die aktualisierten Daten in die Datei _O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-302">When the latest web service version is newer than the version in the _O365_endpoints_latestversion.txt_ file, the script returns the endpoints and filters for the **Allow** and **Optimize** category endpoints, updates the version in the _O365_endpoints_latestversion.txt_ file, and writes the updated data to the _O365_endpoints_data.txt_ file.</span></span>

<span data-ttu-id="7dbaa-303">Das Skript generiert eine eindeutige _ClientRequestId_ für den Computer, auf dem es ausgeführt wird, und verwendet diese ID über mehrere Aufrufe hinweg.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-303">The script generates a unique _ClientRequestId_ for the computer it is executed on, and reuses this ID across multiple calls.</span></span> <span data-ttu-id="7dbaa-304">Diese ID wird in der Datei _O365_endpoints_latestversion.txt_ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-304">This ID is stored in the _O365_endpoints_latestversion.txt_ file.</span></span>

### <a name="to-run-the-powershell-script"></a><span data-ttu-id="7dbaa-305">Ausführen des PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="7dbaa-305">To run the PowerShell script</span></span>

1. <span data-ttu-id="7dbaa-306">Kopieren Sie das Skript, und speichern Sie es auf der Festplatte oder am Speicherort des Skripts als _Get-O365WebServiceUpdates.ps1_.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-306">Copy the script and save it to your local hard drive or script location as _Get-O365WebServiceUpdates.ps1_.</span></span>
1. <span data-ttu-id="7dbaa-307">Führen Sie das Skript in Ihrem bevorzugten Skript-Editor, z. B. PowerShell ISE oder VS Code, oder auf einer PowerShell-Konsole mithilfe des folgenden Befehls aus:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-307">Execute the script in your preferred script editor such as the PowerShell ISE or VS Code, or from a PowerShell console using the following command:</span></span>

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    <span data-ttu-id="7dbaa-308">Es gibt keine Parameter, die an das Skript weiterzugeben sind.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-308">There are no parameters to pass to the script.</span></span>

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a><span data-ttu-id="7dbaa-309">Python-Beispielskript</span><span class="sxs-lookup"><span data-stu-id="7dbaa-309">Example Python Script</span></span>

<span data-ttu-id="7dbaa-p150">Hier ist ein Python-Skript, das mit Python 3.6.3 unter Windows 10 getestet wurde. Sie können es ausführen, um festzustellen, ob es Aktionen gibt, die Sie für aktualisierte Daten ausführen müssen. Dieses Skript überprüft die Versionsnummer für Endpunkte mit der Instanz von Office 365 weltweit. Wenn eine Änderung vorhanden ist, lädt es die Endpunkte herunter und filtert nach den Endpunkten der Kategorie _Zulassen_ und _Optimieren_. Außerdem verwendet es eine eindeutige ClientRequestId über mehrere Anrufe hinweg und speichert die aktuelle Version in einer temporären Datei. Sie sollten dieses Skript einmal pro Stunde aufrufen, um zu überprüfen, ob ein Versionsupdate vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-p150">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data. This script checks the version number for the Office 365 Worldwide instance endpoints. When there is a change, it downloads the endpoints and filters for the _Allow_ and _Optimize_ category endpoints. It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file. You should call this script once an hour to check for a version update.</span></span>

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a><span data-ttu-id="7dbaa-315">Versionsverwaltung der Webdienstschnittstelle</span><span class="sxs-lookup"><span data-stu-id="7dbaa-315">Web Service interface versioning</span></span>

<span data-ttu-id="7dbaa-316">Möglicherweise sind Updates für die Parameter oder Ergebnisse für diese Webdienstmethoden zukünftig erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-316">Updates to the parameters or results for these web service methods may be required in the future.</span></span> <span data-ttu-id="7dbaa-317">Nach der Veröffentlichung der allgemein verfügbaren Version dieser Webdienste wird Microsoft angemessene Anstrengungen unternehmen, um die Aktualisierung des Webdiensts im Voraus anzukündigen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-317">After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service.</span></span> <span data-ttu-id="7dbaa-318">Wenn Microsoft der Auffassung ist, dass für ein Update Änderungen an Clients nötig sind, die den Webdienst verwenden, wird Microsoft die vorherige Version (um eine Version älter) des Webdienstes für mindestens 12 Monate nach der Veröffentlichung der neuen Version verfügbar halten.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-318">When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least 12 months after the release of the new version.</span></span> <span data-ttu-id="7dbaa-319">Kunden, die während dieses Zeitraums kein Upgrade durchführen, können möglicherweise nicht auf den Webdienst und seine Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-319">Customers who do not upgrade during that time may be unable to access the web service and its methods.</span></span> <span data-ttu-id="7dbaa-320">Kunden müssen sicherstellen, dass die Clients des Webdiensts fehlerfrei weiterarbeiten, wenn die folgenden Änderungen an der Signatur der Webdienstschnittstelle vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="7dbaa-320">Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>

- <span data-ttu-id="7dbaa-321">Hinzufügen eines neuen optionalen Parameters zu einer vorhandenen Webmethode, die nicht notwendigerweise von älteren Clients bereitgestellt werden muss und das Ergebnis nicht beeinträchtigt, das ein älterer Client erhält.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-321">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
- <span data-ttu-id="7dbaa-322">Hinzufügen eines neuen benannten Attributs zu einem der REST-Antwortelemente oder zusätzlicher Spalten zur Antwort-CSV.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-322">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
- <span data-ttu-id="7dbaa-323">Hinzufügen einer neuen Webmethode unter einem neuen Namen, die nicht von älteren Clients aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-323">Adding a new web method with a new name that is not called by the older clients.</span></span>

## <a name="update-notifications"></a><span data-ttu-id="7dbaa-324">Updatebenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="7dbaa-324">Update notifications</span></span>

<span data-ttu-id="7dbaa-325">Sie können einige unterschiedliche Methoden nutzen, um E-Mail-Benachrichtigungen zu erhalten, wenn Änderungen an den IP-Adressen und URLs im Webdienst veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-325">You can use a few different methods to get email notifications when changes to the IP addresses and URLs are published to the web service.</span></span>

- <span data-ttu-id="7dbaa-326">Wenn Sie eine Microsoft Flow-Lösung verwenden möchten, lesen Sie [Verwenden von Microsoft Flow, um eine E-Mail wegen Änderungen an Office 365-IP-Adressen und -URLs zu erhalten](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-326">To use a Microsoft Flow solution, see [Use Microsoft Flow to receive an email for changes to Office 365 IP Addresses and URLs](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span></span>
- <span data-ttu-id="7dbaa-327">Um eine Azure Logic App mithilfe einer ARM-Vorlage bereitzustellen, lesen Sie [Office 365-Updatebenachrichtigung (v1.1)](https://aka.ms/ipurlws-updates-template).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-327">To deploy an Azure Logic App using an ARM template, see [Office 365 Update Notification (v1.1)](https://aka.ms/ipurlws-updates-template).</span></span>
- <span data-ttu-id="7dbaa-328">Wenn Sie Ihr eigenes Benachrichtigungsskript mithilfe von PowerShell schreiben möchten, lesen Sie [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-328">To write your own notification script using PowerShell, see [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).</span></span>

## <a name="exporting-a-proxy-pac-file"></a><span data-ttu-id="7dbaa-329">Exportieren einer Proxy-PAC-Datei</span><span class="sxs-lookup"><span data-stu-id="7dbaa-329">Exporting a Proxy PAC file</span></span>

<span data-ttu-id="7dbaa-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) ist ein PowerShell-Skript, das die neuesten Netzwerkendpunkte aus dem IP-Adress- und URL-Webdienst von Office 365 liest und eine PAC-Beispieldatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is a PowerShell script that reads the latest network endpoints from the Office 365 IP Address and URL web service and creates a sample PAC file.</span></span> <span data-ttu-id="7dbaa-331">Informationen zur Verwendung von Get-PacFile finden Sie unter [Verwenden einer PAC-Datei für das direkte Routing von wichtigem Office 365-Datenverkehr](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="7dbaa-331">For information on using Get-PacFile, see [Use a PAC file for direct routing of vital Office 365 traffic](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7dbaa-332">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7dbaa-332">Related Topics</span></span>
  
[<span data-ttu-id="7dbaa-333">URLs und IP-Adressbereiche für Office 365</span><span class="sxs-lookup"><span data-stu-id="7dbaa-333">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="7dbaa-334">Verwalten von Office 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="7dbaa-334">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="7dbaa-335">Häufig gestellte Fragen zu Office 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="7dbaa-335">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[<span data-ttu-id="7dbaa-336">Prinzipien von Office 365-Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="7dbaa-336">Office 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="7dbaa-337">Office 365-Netzwerk- und Leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="7dbaa-337">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="7dbaa-338">Bewerten der Office 365-Netzwerkkonnektivität</span><span class="sxs-lookup"><span data-stu-id="7dbaa-338">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="7dbaa-339">Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7dbaa-339">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="7dbaa-340">Optimieren Ihres Netzwerks für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7dbaa-340">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[<span data-ttu-id="7dbaa-341">Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf</span><span class="sxs-lookup"><span data-stu-id="7dbaa-341">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="7dbaa-342">Plan zur Problembehandlung für Office 365</span><span class="sxs-lookup"><span data-stu-id="7dbaa-342">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)