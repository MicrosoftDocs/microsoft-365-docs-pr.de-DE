---
title: Wischen eines mobilen Geräts in Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Verwenden Sie integrierte Grundlegende Mobilität und Sicherheit, um Informationen von registrierten Geräten zu entfernen.
ms.openlocfilehash: 8c873923505fe527f5a44df0e8b15d290e92023b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706142"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="86c72-103">Wischen eines mobilen Geräts in Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="86c72-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="86c72-104">Sie können integrierte Grundlegende Mobilität und Sicherheit für Microsoft 365 verwenden, um nur Organisationsinformationen zu entfernen oder eine Werkszurücksetzung durchzuführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="86c72-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="86c72-105">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="86c72-105">Before you begin</span></span>

<span data-ttu-id="86c72-106">Mobile Geräte können vertrauliche Organisationsinformationen speichern und Zugriff auf die Ressourcen Microsoft 365 Organisation bieten.</span><span class="sxs-lookup"><span data-stu-id="86c72-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="86c72-107">Um die Informationen Ihrer Organisation zu schützen, können Sie die Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen:</span><span class="sxs-lookup"><span data-stu-id="86c72-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="86c72-108">**Werkseinstellung:** Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und personenbezogener Informationen.</span><span class="sxs-lookup"><span data-stu-id="86c72-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="86c72-109">Nach Abschluss des Zurücksetzens wird das Gerät in den Werkseinstellungen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="86c72-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="86c72-110">**Entfernen von Unternehmensdaten**: Entfernt nur Organisationsdaten und hinterlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="86c72-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="86c72-111">**Wenn ein Gerät zurückgesetzt wird (Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen)** wird das Gerät aus der Liste der verwalteten Geräte entfernt.</span><span class="sxs-lookup"><span data-stu-id="86c72-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="86c72-112">**Automatisches** Zurücksetzen eines Geräts: Sie können eine Grundlegende Mobilitäts- und Sicherheitsrichtlinie einrichten, die ein Gerät automatisch in der Fabrik zurück setzt, nachdem der Benutzer erfolglos versucht hat, das Gerätekennwort mehrmals einzugeben.</span><span class="sxs-lookup"><span data-stu-id="86c72-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="86c72-113">Führen Sie dazu die Schritte unter Erstellen von [Gerätesicherheitsrichtlinien in grundlegenden Mobilitäts- und Sicherheitsrichtlinien aus.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="86c72-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="86c72-114">**Wenn Sie die Benutzeroberfläche beim** Wischen des Geräts kennen möchten, lesen Sie Was sind die Auswirkungen auf Benutzer   [und Geräte?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="86c72-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="86c72-115">Wischen eines mobilen Geräts</span><span class="sxs-lookup"><span data-stu-id="86c72-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="86c72-116">Wechseln Sie zum [Microsoft 365 Admin Center](../../admin/admin-overview/about-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="86c72-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="86c72-117">Geben Sie mobile Geräteverwaltung in das Suchfeld ein, und wählen Sie **mobile Geräteverwaltung** in der Liste der Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="86c72-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Grundlegende Option zur Verwaltung mobiler Geräte für Mobilität und Secruity":::

3. <span data-ttu-id="86c72-119">Wählen **Sie Geräte verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="86c72-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="86c72-120">Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="86c72-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="86c72-121">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="86c72-121">Select **Manage**.</span></span>

6. <span data-ttu-id="86c72-122">Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="86c72-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="86c72-123">Wählen Sie Factory reset aus, um ein vollständiges Zurücksetzen zu durchführen und das Gerät in den Werkseinstellungen **wiederherzustellen.**</span><span class="sxs-lookup"><span data-stu-id="86c72-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="86c72-124">Wählen Sie Zum selektiven Löschen und Löschen Microsoft 365 Unternehmensinformationen entfernen **aus.**</span><span class="sxs-lookup"><span data-stu-id="86c72-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="86c72-125">Um das Gerät aus Ihrer Organisation zu entfernen, wählen Sie **Gerät entfernen aus.**</span><span class="sxs-lookup"><span data-stu-id="86c72-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="86c72-126">Wählen Sie zum Bestätigen **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="86c72-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="86c72-127">Wo kann ich wissen, dass es funktioniert hat?</span><span class="sxs-lookup"><span data-stu-id="86c72-127">How do I know it worked?</span></span>

<span data-ttu-id="86c72-128">Das mobile Gerät wird nicht mehr in der Liste der verwalteten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86c72-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="86c72-129">Warum möchten Sie ein Gerät wischen?</span><span class="sxs-lookup"><span data-stu-id="86c72-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="86c72-130">Wischen Sie ein Gerät aus folgenden Gründen:</span><span class="sxs-lookup"><span data-stu-id="86c72-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="86c72-131">Mobile Geräte wie Smartphones und Tablets werden immer mehr voll funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="86c72-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="86c72-132">Dies bedeutet, dass Ihre Benutzer vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation leichter speichern und unterwegs darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="86c72-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="86c72-133">Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Wischen des Geräts dazu beitragen, zu verhindern, dass die Informationen Ihrer Organisation in die falschen Hände geraten.</span><span class="sxs-lookup"><span data-stu-id="86c72-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="86c72-134">Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das in Basic Mobility and Security registriert ist, können Sie verhindern, dass Organisationsinformationen mit diesem Benutzer verwendet werden, indem Sie eine Werkszurücksetzung durchführen.</span><span class="sxs-lookup"><span data-stu-id="86c72-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="86c72-135">Wenn Ihre Organisation benutzern mobile Geräte zur Verfügung stellt, müssen Sie Geräte möglicherweise von Zeit zu Zeit neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86c72-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="86c72-136">Wenn Sie ein Factory Reset auf einem Gerät durchführen, bevor sie einem neuen Benutzer zugewiesen werden, wird sichergestellt, dass alle vertraulichen Informationen des vorherigen Besitzers gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="86c72-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="86c72-137">Welche Auswirkungen haben Benutzer und Geräte?</span><span class="sxs-lookup"><span data-stu-id="86c72-137">What's the user and device impact?</span></span>

<span data-ttu-id="86c72-138">Die Löschung wird sofort an das mobile Gerät gesendet, und das Gerät ist in Azure Active Directory als nicht kompatibel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="86c72-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="86c72-139">Während alle Daten entfernt werden, wenn ein Gerät auf die Werkseinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für jeden Gerätetyp entfernt werden, wenn ein Gerät beim Entfernen von Unternehmensdaten entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="86c72-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="86c72-140">**Auswirkungen auf Inhalte**</span><span class="sxs-lookup"><span data-stu-id="86c72-140">**Content impact**</span></span>|<span data-ttu-id="86c72-141">**iOS 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="86c72-141">**iOS 10 and later**</span></span>|<span data-ttu-id="86c72-142">**Android 5 und höher**</span><span class="sxs-lookup"><span data-stu-id="86c72-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="86c72-143">Microsoft 365 App-Daten werden gelöscht, wenn das Gerät durch Intune App Protection-Richtlinien geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="86c72-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="86c72-144">Die Apps werden nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="86c72-144">The apps aren't removed.</span></span> <span data-ttu-id="86c72-145">Bei Geräten, die nicht durch Mam -Richtlinien (Mobile Application Management) geschützt sind, Outlook und OneDrive zwischengespeicherte Daten nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="86c72-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="86c72-146">**Hinweis** Zum Anwenden von Intune-App-Schutzrichtlinien benötigen Sie eine Intune-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="86c72-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="86c72-147">Ja</span><span class="sxs-lookup"><span data-stu-id="86c72-147">Yes</span></span>|<span data-ttu-id="86c72-148">Ja</span><span class="sxs-lookup"><span data-stu-id="86c72-148">Yes</span></span>|
|<span data-ttu-id="86c72-149">Richtlinieneinstellungen, die von Basic Mobility and Security auf Geräte angewendet werden, werden nicht mehr erzwungen. Benutzer können die Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="86c72-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="86c72-150">Ja</span><span class="sxs-lookup"><span data-stu-id="86c72-150">Yes</span></span>|<span data-ttu-id="86c72-151">Ja</span><span class="sxs-lookup"><span data-stu-id="86c72-151">Yes</span></span>|
|<span data-ttu-id="86c72-152">Von Basic Mobility and Security erstellte E-Mail-Profile werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht.</span><span class="sxs-lookup"><span data-stu-id="86c72-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="86c72-153">Ja</span><span class="sxs-lookup"><span data-stu-id="86c72-153">Yes</span></span>|<span data-ttu-id="86c72-154">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="86c72-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="86c72-155">Unternehmensportal App ist im App-Store für iOS und im Play-Store für Android-Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86c72-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>
