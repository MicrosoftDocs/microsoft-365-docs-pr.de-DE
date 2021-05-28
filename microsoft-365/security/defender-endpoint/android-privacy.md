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
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694341"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="042ae-104">Microsoft Defender für Endpunkt unter Android – Datenschutzinformationen</span><span class="sxs-lookup"><span data-stu-id="042ae-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="042ae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="042ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="042ae-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="042ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="042ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="042ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="042ae-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="042ae-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="042ae-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="042ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="042ae-110">Defender for Endpoint unter Android sammelt Informationen von Ihren konfigurierten Android-Geräten und speichert sie im selben Mandanten, in dem Sie Defender for Endpoint haben.</span><span class="sxs-lookup"><span data-stu-id="042ae-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="042ae-111">Die Informationen werden gesammelt, um Defender for Endpoint für Android sicher, auf dem neuesten Stand zu halten, wie erwartet zu gewährleisten und den Dienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="042ae-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="042ae-112">Weitere Informationen zur Datenspeicherung finden Sie unter [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="042ae-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="042ae-113">Es werden Informationen gesammelt, um Defender for Endpoint für Android sicher, auf dem neuesten Stand zu halten, wie erwartet zu gewährleisten und den Dienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="042ae-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

<span data-ttu-id="042ae-114">Weitere Informationen zu den häufigsten Datenschutzfragen zu Microsoft Defender for Endpoint auf mobilen Android- und iOS-Geräten finden Sie unter Microsoft Defender for Endpoint und Ihre Privatsphäre auf [mobilen Android- und iOS-Geräten.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)</span><span class="sxs-lookup"><span data-stu-id="042ae-114">For more information on most common privacy questions about Microsoft Defender for Endpoint on Android and iOS mobile devices, see [Microsoft Defender for Endpoint and your privacy on Android and iOS mobile devices](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).</span></span>

## <a name="required-data"></a><span data-ttu-id="042ae-115">Erforderliche Daten</span><span class="sxs-lookup"><span data-stu-id="042ae-115">Required Data</span></span> 

<span data-ttu-id="042ae-116">Erforderliche Daten bestehen aus Daten, die erforderlich sind, damit Defender for Endpoint für Android wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="042ae-116">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="042ae-117">Diese Daten sind für den Betrieb des Diensts unerlässlich und können Daten im Zusammenhang mit dem Endbenutzer, der Organisation, dem Gerät und den Apps enthalten.</span><span class="sxs-lookup"><span data-stu-id="042ae-117">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="042ae-118">Im Folgenden finden Sie eine Liste der Arten von Daten, die erfasst werden:</span><span class="sxs-lookup"><span data-stu-id="042ae-118">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="042ae-119">App-Informationen</span><span class="sxs-lookup"><span data-stu-id="042ae-119">App information</span></span>

<span data-ttu-id="042ae-120">Informationen zu **schädlichen** Android-Anwendungspaketen (APKs) auf dem Gerät, einschließlich</span><span class="sxs-lookup"><span data-stu-id="042ae-120">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="042ae-121">Installationsquelle</span><span class="sxs-lookup"><span data-stu-id="042ae-121">Install source</span></span>
-  <span data-ttu-id="042ae-122">Storage Speicherort (Dateipfad) der APK</span><span class="sxs-lookup"><span data-stu-id="042ae-122">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="042ae-123">Zeitpunkt der Installation, Größe der APK und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="042ae-123">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="042ae-124">Webseiten-/Netzwerkinformationen</span><span class="sxs-lookup"><span data-stu-id="042ae-124">Web page / Network information</span></span>

- <span data-ttu-id="042ae-125">Vollständige URL der Website nur, wenn eine schädliche Verbindung oder Webseite erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="042ae-125">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="042ae-126">Verbindungsinformationen</span><span class="sxs-lookup"><span data-stu-id="042ae-126">Connection information</span></span>
- <span data-ttu-id="042ae-127">Protokolltyp (z. B. HTTP, HTTPS usw.)</span><span class="sxs-lookup"><span data-stu-id="042ae-127">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="042ae-128">Geräte- und Kontoinformationen</span><span class="sxs-lookup"><span data-stu-id="042ae-128">Device and account information</span></span>

- <span data-ttu-id="042ae-129">Geräteinformationen wie Datum &, Android-Version, OEM-Modell, CPU-Informationen und Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="042ae-129">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="042ae-130">Die Geräte-ID ist eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="042ae-130">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="042ae-131">Wi-Fi-MAC-Adresse des Adapters</span><span class="sxs-lookup"><span data-stu-id="042ae-131">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="042ae-132">[Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (wie von Android beim ersten Start des Geräts generiert)</span><span class="sxs-lookup"><span data-stu-id="042ae-132">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="042ae-133">Nach dem Zufallsprinzip generierte GUID (Globally Unique Identifier)</span><span class="sxs-lookup"><span data-stu-id="042ae-133">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="042ae-134">Mandanten-, Geräte- und Benutzerinformationen</span><span class="sxs-lookup"><span data-stu-id="042ae-134">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="042ae-135">Azure Active Directory (AD) Geräte-ID und Azure-Benutzer-ID: Identifiziert das Gerät eindeutig, Benutzer bzw. Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="042ae-135">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="042ae-136">Azure-Mandanten-ID – GUID, die Ihre Organisation innerhalb Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="042ae-136">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="042ae-137">Microsoft Defender for Endpoint Org ID – Eindeutige ID, die dem Unternehmen zugeordnet ist, zu dem das Gerät gehört.</span><span class="sxs-lookup"><span data-stu-id="042ae-137">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="042ae-138">Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Unternehmen auswirken und wie viele Unternehmen betroffen sind</span><span class="sxs-lookup"><span data-stu-id="042ae-138">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="042ae-139">Benutzerprinzipalname – E-Mail-ID des Benutzers</span><span class="sxs-lookup"><span data-stu-id="042ae-139">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="042ae-140">Produkt- und Dienstnutzungsdaten</span><span class="sxs-lookup"><span data-stu-id="042ae-140">Product and service usage data</span></span>

<span data-ttu-id="042ae-141">Die folgenden Informationen werden nur für die auf dem Gerät installierte Microsoft Defender for Endpoint-App gesammelt.</span><span class="sxs-lookup"><span data-stu-id="042ae-141">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="042ae-142">Informationen zum App-Paket, einschließlich Name, Version und Status des App-Upgrades</span><span class="sxs-lookup"><span data-stu-id="042ae-142">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="042ae-143">In der App ausgeführte Aktionen</span><span class="sxs-lookup"><span data-stu-id="042ae-143">Actions performed in the app</span></span>

-   <span data-ttu-id="042ae-144">Informationen zur Bedrohungserkennung, z. B. Bedrohungsname, Kategorie usw.</span><span class="sxs-lookup"><span data-stu-id="042ae-144">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="042ae-145">Von Android generierte Absturzberichtsprotokolle</span><span class="sxs-lookup"><span data-stu-id="042ae-145">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="042ae-146">Optionale Daten</span><span class="sxs-lookup"><span data-stu-id="042ae-146">Optional Data</span></span>

<span data-ttu-id="042ae-147">Optionale Daten umfassen Diagnosedaten und Feedbackdaten.</span><span class="sxs-lookup"><span data-stu-id="042ae-147">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="042ae-148">Optionale Diagnosedaten sind zusätzliche Daten die uns helfen, Produktverbesserungen vorzunehmen, und erweiterte Informationen liefern, die uns helfen, Probleme zu erkennen, zu diagnostizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="042ae-148">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="042ae-149">Optionale Diagnosedaten umfassen:</span><span class="sxs-lookup"><span data-stu-id="042ae-149">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="042ae-150">App-, CPU- und Netzwerknutzung</span><span class="sxs-lookup"><span data-stu-id="042ae-150">App, CPU, and network usage</span></span>

-   <span data-ttu-id="042ae-151">Status des Geräts aus App-Sicht, einschließlich Scanstatus, Scanzeit, erteilten App-Berechtigungen und Upgradestatus</span><span class="sxs-lookup"><span data-stu-id="042ae-151">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="042ae-152">Vom Administrator konfigurierte Features</span><span class="sxs-lookup"><span data-stu-id="042ae-152">Features configured by the admin</span></span>

-   <span data-ttu-id="042ae-153">Grundlegende Informationen zu den Browsern auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="042ae-153">Basic information about the browsers on the device</span></span>

<span data-ttu-id="042ae-154">**Feedbackdaten** werden über in-App-Feedback gesammelt, das vom Benutzer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="042ae-154">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="042ae-155">Die E-Mail-Adresse des Benutzers, wenn er sie angeben will</span><span class="sxs-lookup"><span data-stu-id="042ae-155">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="042ae-156">Feedbacktyp (Schmunzeln, Stirnrunzeln, Idee) und alle vom Benutzer übermittelten Feedbackkommentare</span><span class="sxs-lookup"><span data-stu-id="042ae-156">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
