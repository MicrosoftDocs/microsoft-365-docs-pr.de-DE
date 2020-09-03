---
title: Wischen eines mobilen Geräts in grundlegender Mobilität und Sicherheit
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
description: Verwenden Sie die integrierte grundlegende Mobilität und Sicherheit, um Informationen von registrierten Geräten zu entfernen.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336891"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="30909-103">Wischen eines mobilen Geräts in grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="30909-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="30909-104">Mithilfe von integrierter grundlegender Mobilität und Sicherheit für Microsoft 365 können Sie nur organisatorische Informationen entfernen oder ein Factory-Reset durchführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="30909-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="30909-105">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="30909-105">Before you begin</span></span>

<span data-ttu-id="30909-106">Mobile Geräte können vertrauliche Organisationsinformationen speichern und den Zugriff auf die Microsoft 365-Ressourcen Ihrer Organisation ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="30909-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="30909-107">Um die Informationen Ihrer Organisation zu schützen, können Sie Firmendaten zurücksetzen oder entfernen:</span><span class="sxs-lookup"><span data-stu-id="30909-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="30909-108">**Factory Reset**: Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="30909-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="30909-109">Wenn die Zurücksetzung abgeschlossen ist, wird das Gerät in den Werkseinstellungen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="30909-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="30909-110">**Entfernen von Unternehmensdaten**: entfernt nur Organisationsdaten und hinterlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="30909-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="30909-111">**Wenn ein Gerät gelöscht wird (Factory zurücksetzen oder Entfernen von Unternehmensdaten)**, wird das Gerät aus der Liste der verwalteten Geräte entfernt.</span><span class="sxs-lookup"><span data-stu-id="30909-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="30909-112">**Automatisches Zurücksetzen eines Geräts**: Sie können eine grundlegende Mobilitäts-und Sicherheitsrichtlinie einrichten, mit der ein Gerät automatisch zurückgesetzt wird, nachdem der Benutzer erfolglos versucht hat, das Gerätekennwort eine bestimmte Anzahl von Malen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="30909-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="30909-113">Führen Sie dazu die Schritte unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md)aus.</span><span class="sxs-lookup"><span data-stu-id="30909-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="30909-114">**Wenn Sie die Benutzeroberfläche kennen möchten** , wenn Sie Ihr Gerät löschen, lesen Sie  [Was ist der Einfluss von Benutzern und Geräten?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="30909-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="30909-115">Wischen eines mobilen Geräts</span><span class="sxs-lookup"><span data-stu-id="30909-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="30909-116">Wechseln Sie zum [Microsoft 365 Admin Center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="30909-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="30909-117">Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie in der Ergebnisliste die **Verwaltung mobiler Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="30909-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Einfache Mobilitäts-und secruity-Option für die Mobile Geräteverwaltung":::

3. <span data-ttu-id="30909-119">Wählen Sie **Geräte verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="30909-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="30909-120">Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="30909-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="30909-121">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="30909-121">Select **Manage**.</span></span>

6. <span data-ttu-id="30909-122">Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="30909-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="30909-123">Um eine vollständige Zurücksetzung durchführen und das Gerät in den Werkseinstellungen wiederherstellen zu können, wählen Sie **Factory Reset**aus.</span><span class="sxs-lookup"><span data-stu-id="30909-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="30909-124">Um eine selektive Zurücksetzung durchführen und nur Informationen zu Microsoft 365-Organisationen zu löschen, wählen Sie **Unternehmensdaten entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="30909-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="30909-125">Wenn Sie das Gerät aus Ihrer Organisation entfernen möchten, wählen Sie **Gerät entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="30909-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="30909-126">Wählen Sie zum Bestätigen **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="30909-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="30909-127">Woher weiß ich, dass es funktioniert hat?</span><span class="sxs-lookup"><span data-stu-id="30909-127">How do I know it worked?</span></span>

<span data-ttu-id="30909-128">Das Mobile Gerät wird in der Liste der verwalteten Geräte nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30909-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="30909-129">Warum sollten Sie ein Gerät löschen?</span><span class="sxs-lookup"><span data-stu-id="30909-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="30909-130">Wischen Sie ein Gerät aus folgenden Gründen ab:</span><span class="sxs-lookup"><span data-stu-id="30909-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="30909-131">Mobile Geräte wie Smartphones und Tablets werden immer umfangreichere Features.</span><span class="sxs-lookup"><span data-stu-id="30909-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="30909-132">Dies bedeutet, dass es für Ihre Benutzer einfacher ist, vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation zu speichern und unterwegs darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="30909-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="30909-133">Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Abwischen des Geräts dazu beitragen, dass die Informationen Ihrer Organisation nicht in die falschen Hände geraten.</span><span class="sxs-lookup"><span data-stu-id="30909-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="30909-134">Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das in Basic Mobility and Security registriert ist, können Sie verhindern, dass organisatorische Informationen mit dem betreffenden Benutzer ausgeführt werden, indem Sie einen Factory-Reset durchführen.</span><span class="sxs-lookup"><span data-stu-id="30909-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="30909-135">Wenn Ihre Organisation Benutzern Mobile Geräte zur Verfügung stellt, müssen Sie möglicherweise von Zeit zu Zeit Geräte neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="30909-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="30909-136">Wenn Sie ein Factory-Reset auf einem Gerät durchführen, bevor Sie es einem neuen Benutzer zuweisen, wird sichergestellt, dass vertrauliche Informationen des vorherigen Besitzers gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="30909-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="30909-137">Was ist der Einfluss von Benutzern und Geräten?</span><span class="sxs-lookup"><span data-stu-id="30909-137">What's the user and device impact?</span></span>

<span data-ttu-id="30909-138">Die Löschung wird sofort an das Mobile Gerät gesendet, und das Gerät ist in Azure Active Directory als nicht kompatibel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="30909-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="30909-139">Während alle Daten entfernt werden, wenn ein Gerät auf die Werkseinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für die einzelnen Gerätetypen entfernt werden, wenn ein Gerät beim Entfernen von Unternehmensdaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30909-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="30909-140">**Inhalt unpaced**</span><span class="sxs-lookup"><span data-stu-id="30909-140">**Content impace**</span></span>|<span data-ttu-id="30909-141">**IOS 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="30909-141">**iOS 10 and later**</span></span>|<span data-ttu-id="30909-142">**Android 5 und höher**</span><span class="sxs-lookup"><span data-stu-id="30909-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30909-143">Microsoft 365 App-Daten werden gelöscht, wenn das Gerät durch InTune-App-Schutzrichtlinien geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="30909-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="30909-144">Die apps werden nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="30909-144">The apps aren't removed.</span></span> <span data-ttu-id="30909-145">Für Geräte, die nicht durch MAM-Richtlinien (Mobile Application Management) geschützt sind, entfernen Outlook und OneDrive zwischengespeicherte Daten nicht.</span><span class="sxs-lookup"><span data-stu-id="30909-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="30909-146">**Hinweis:** Zum Anwenden von InTune-App-Schutzrichtlinien benötigen Sie eine InTune-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="30909-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="30909-147">Ja</span><span class="sxs-lookup"><span data-stu-id="30909-147">Yes</span></span>|<span data-ttu-id="30909-148">Ja</span><span class="sxs-lookup"><span data-stu-id="30909-148">Yes</span></span>|
|<span data-ttu-id="30909-149">Richtlinieneinstellungen, die von grundlegender Mobilität und Sicherheit auf Geräte angewendet werden, werden nicht mehr erzwungen; Benutzer können die Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="30909-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="30909-150">Ja</span><span class="sxs-lookup"><span data-stu-id="30909-150">Yes</span></span>|<span data-ttu-id="30909-151">Ja</span><span class="sxs-lookup"><span data-stu-id="30909-151">Yes</span></span>|
|<span data-ttu-id="30909-152">Von Basic Mobility and Security erstellte e-Mail-Profile werden entfernt, und zwischengespeicherte e-Mails auf dem Gerät werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="30909-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="30909-153">Ja</span><span class="sxs-lookup"><span data-stu-id="30909-153">Yes</span></span>|<span data-ttu-id="30909-154">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="30909-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="30909-155">Die Unternehmens Portal-App steht im App Store für IOS und den Play Store für Android-Geräte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="30909-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="30909-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30909-156">Related topics</span></span>

[<span data-ttu-id="30909-157">Einrichten von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="30909-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)