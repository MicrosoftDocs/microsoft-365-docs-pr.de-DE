---
title: Microsoft Defender für Endpunkt unter Android – Datenschutzinformationen
description: Datenschutzsteuerelemente, Konfigurieren von Richtlinieneinstellungen, die sich auf den Datenschutz auswirken, sowie Informationen zu den diagnosedaten, die in Microsoft Defender for Endpoint auf Android gesammelt werden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostic
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1aaae2970cfb2f6da82507eefa87c8d0e2227661
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939624"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="cb298-104">Microsoft Defender für Endpunkt unter Android – Datenschutzinformationen</span><span class="sxs-lookup"><span data-stu-id="cb298-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="cb298-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cb298-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb298-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cb298-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb298-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb298-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cb298-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cb298-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb298-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cb298-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="cb298-110">Defender for Endpoint unter Android sammelt Informationen von Ihren konfigurierten Android-Geräten und speichert sie im selben Mandanten, in dem Sie Defender for Endpoint haben.</span><span class="sxs-lookup"><span data-stu-id="cb298-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="cb298-111">Die Informationen werden gesammelt, um Defender for Endpoint für Android sicher, auf dem neuesten Stand zu halten, wie erwartet zu gewährleisten und den Dienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cb298-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="cb298-112">Weitere Informationen zur Datenspeicherung finden Sie unter [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="cb298-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="cb298-113">Es werden Informationen gesammelt, um Defender for Endpoint für Android sicher, auf dem neuesten Stand zu halten, wie erwartet zu gewährleisten und den Dienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cb298-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="cb298-114">Erforderliche Daten</span><span class="sxs-lookup"><span data-stu-id="cb298-114">Required Data</span></span> 

<span data-ttu-id="cb298-115">Erforderliche Daten bestehen aus Daten, die erforderlich sind, damit Defender for Endpoint für Android wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cb298-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="cb298-116">Diese Daten sind für den Betrieb des Diensts unerlässlich und können Daten im Zusammenhang mit dem Endbenutzer, der Organisation, dem Gerät und den Apps enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb298-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="cb298-117">Im Folgenden finden Sie eine Liste der Arten von Daten, die erfasst werden:</span><span class="sxs-lookup"><span data-stu-id="cb298-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="cb298-118">App-Informationen</span><span class="sxs-lookup"><span data-stu-id="cb298-118">App information</span></span>

<span data-ttu-id="cb298-119">Informationen zu **schädlichen** Android-Anwendungspaketen (APKs) auf dem Gerät, einschließlich</span><span class="sxs-lookup"><span data-stu-id="cb298-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="cb298-120">Installationsquelle</span><span class="sxs-lookup"><span data-stu-id="cb298-120">Install source</span></span>
-  <span data-ttu-id="cb298-121">Speicherort (Dateipfad) der APK</span><span class="sxs-lookup"><span data-stu-id="cb298-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="cb298-122">Zeitpunkt der Installation, Größe der APK und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cb298-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="cb298-123">Webseiten-/Netzwerkinformationen</span><span class="sxs-lookup"><span data-stu-id="cb298-123">Web page / Network information</span></span>

- <span data-ttu-id="cb298-124">Vollständige URL der Website nur, wenn eine schädliche Verbindung oder Webseite erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="cb298-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="cb298-125">Verbindungsinformationen</span><span class="sxs-lookup"><span data-stu-id="cb298-125">Connection information</span></span>
- <span data-ttu-id="cb298-126">Protokolltyp (z. B. HTTP, HTTPS usw.)</span><span class="sxs-lookup"><span data-stu-id="cb298-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="cb298-127">Geräte- und Kontoinformationen</span><span class="sxs-lookup"><span data-stu-id="cb298-127">Device and account information</span></span>

- <span data-ttu-id="cb298-128">Geräteinformationen wie Datum &, Android-Version, OEM-Modell, CPU-Informationen und Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="cb298-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="cb298-129">Die Geräte-ID ist eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="cb298-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="cb298-130">Wi-Fi-MAC-Adresse des Adapters</span><span class="sxs-lookup"><span data-stu-id="cb298-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="cb298-131">[Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (wie von Android beim ersten Start des Geräts generiert)</span><span class="sxs-lookup"><span data-stu-id="cb298-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="cb298-132">Nach dem Zufallsprinzip generierte GUID (Globally Unique Identifier)</span><span class="sxs-lookup"><span data-stu-id="cb298-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="cb298-133">Mandanten-, Geräte- und Benutzerinformationen</span><span class="sxs-lookup"><span data-stu-id="cb298-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="cb298-134">Azure Active Directory (AD)-Geräte-ID und Azure-Benutzer-ID: Identifiziert das Gerät eindeutig, Benutzer bzw. Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb298-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="cb298-135">Azure-Mandanten-ID – GUID, die Ihre Organisation in Azure Active Directory identifiziert</span><span class="sxs-lookup"><span data-stu-id="cb298-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="cb298-136">Microsoft Defender for Endpoint Org ID – Eindeutige ID, die dem Unternehmen zugeordnet ist, zu dem das Gerät gehört.</span><span class="sxs-lookup"><span data-stu-id="cb298-136">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="cb298-137">Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Unternehmen auswirken und wie viele Unternehmen betroffen sind</span><span class="sxs-lookup"><span data-stu-id="cb298-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="cb298-138">Benutzerprinzipalname – E-Mail-ID des Benutzers</span><span class="sxs-lookup"><span data-stu-id="cb298-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="cb298-139">Produkt- und Dienstnutzungsdaten</span><span class="sxs-lookup"><span data-stu-id="cb298-139">Product and service usage data</span></span>

<span data-ttu-id="cb298-140">Die folgenden Informationen werden nur für die auf dem Gerät installierte Microsoft Defender for Endpoint-App gesammelt.</span><span class="sxs-lookup"><span data-stu-id="cb298-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="cb298-141">Informationen zum App-Paket, einschließlich Name, Version und Status des App-Upgrades</span><span class="sxs-lookup"><span data-stu-id="cb298-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="cb298-142">In der App ausgeführte Aktionen</span><span class="sxs-lookup"><span data-stu-id="cb298-142">Actions performed in the app</span></span>

-   <span data-ttu-id="cb298-143">Informationen zur Bedrohungserkennung, z. B. Bedrohungsname, Kategorie usw.</span><span class="sxs-lookup"><span data-stu-id="cb298-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="cb298-144">Von Android generierte Absturzberichtsprotokolle</span><span class="sxs-lookup"><span data-stu-id="cb298-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="cb298-145">Optionale Daten</span><span class="sxs-lookup"><span data-stu-id="cb298-145">Optional Data</span></span>

<span data-ttu-id="cb298-146">Optionale Daten umfassen Diagnosedaten und Feedbackdaten.</span><span class="sxs-lookup"><span data-stu-id="cb298-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="cb298-147">Optionale Diagnosedaten sind zusätzliche Daten die uns helfen, Produktverbesserungen vorzunehmen, und erweiterte Informationen liefern, die uns helfen, Probleme zu erkennen, zu diagnostizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cb298-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="cb298-148">Optionale Diagnosedaten umfassen:</span><span class="sxs-lookup"><span data-stu-id="cb298-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="cb298-149">App-, CPU- und Netzwerknutzung</span><span class="sxs-lookup"><span data-stu-id="cb298-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="cb298-150">Status des Geräts aus App-Sicht, einschließlich Scanstatus, Scanzeit, erteilten App-Berechtigungen und Upgradestatus</span><span class="sxs-lookup"><span data-stu-id="cb298-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="cb298-151">Vom Administrator konfigurierte Features</span><span class="sxs-lookup"><span data-stu-id="cb298-151">Features configured by the admin</span></span>

-   <span data-ttu-id="cb298-152">Grundlegende Informationen zu den Browsern auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="cb298-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="cb298-153">**Feedbackdaten** werden über in-App-Feedback gesammelt, das vom Benutzer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cb298-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="cb298-154">Die E-Mail-Adresse des Benutzers, wenn er sie angeben will</span><span class="sxs-lookup"><span data-stu-id="cb298-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="cb298-155">Feedbacktyp (Schmunzeln, Stirnrunzeln, Idee) und alle vom Benutzer übermittelten Feedbackkommentare</span><span class="sxs-lookup"><span data-stu-id="cb298-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
