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
description: Verwenden Sie die integrierte Basismobilität und -sicherheit, um Informationen von registrierten Geräten zu entfernen.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876828"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="a5648-103">Wischen eines mobilen Geräts in Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="a5648-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="a5648-104">Sie können die integrierte Basismobilität und -sicherheit für Microsoft 365 verwenden, um nur Organisationsinformationen zu entfernen oder eine Zurücksetzung auf die Werkseinstellungen durchzuführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a5648-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a5648-105">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="a5648-105">Before you begin</span></span>

<span data-ttu-id="a5648-106">Mobile Geräte können vertrauliche Unternehmensinformationen speichern und Zugriff auf die Microsoft 365-Ressourcen Ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a5648-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="a5648-107">Um die Informationen Ihrer Organisation zu schützen, können Sie die Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen:</span><span class="sxs-lookup"><span data-stu-id="a5648-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="a5648-108">**Zurücksetzen auf** die Werkseinstellungen: Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="a5648-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="a5648-109">Nach Abschluss des Zurücksetzens wird das Gerät in den Werkseinstellungen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a5648-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="a5648-110">**Entfernen von Unternehmensdaten:** Entfernt nur Organisationsdaten und hinterlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a5648-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="a5648-111">**Wenn ein Gerät zurückgesetzt wird (Werkseinstellungen** zurücksetzen oder Unternehmensdaten entfernen), wird das Gerät aus der Liste der verwalteten Geräte entfernt.</span><span class="sxs-lookup"><span data-stu-id="a5648-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="a5648-112">**Automatisches** Zurücksetzen eines Geräts: Sie können eine Standardrichtlinie für Mobilität und Sicherheit einrichten, die ein Gerät automatisch zurückzusetzen versucht, nachdem der Benutzer mehrmals erfolglos versucht hat, das Gerätekennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="a5648-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="a5648-113">Führen Sie dazu die Schritte in "Erstellen von Gerätesicherheitsrichtlinien [für grundlegende Mobilität und Sicherheit" aus.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a5648-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="a5648-114">**Wenn Sie die Benutzeroberfläche** kennen möchten, wenn Sie ihr Gerät löschen, lesen Sie, was die Auswirkungen auf Benutzer   [und Geräte sind.](#whats-the-user-and-device-impact)</span><span class="sxs-lookup"><span data-stu-id="a5648-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="a5648-115">Wischen eines mobilen Geräts</span><span class="sxs-lookup"><span data-stu-id="a5648-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="a5648-116">Wechseln Sie zum [Microsoft 365 Admin Center.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="a5648-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="a5648-117">Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie in der Ergebnisliste die Option **"Mobile** Geräteverwaltung" aus.</span><span class="sxs-lookup"><span data-stu-id="a5648-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Option für die verwaltung mobiler Geräte für Mobilität und Secruity":::

3. <span data-ttu-id="a5648-119">Wählen **Sie Geräte verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="a5648-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="a5648-120">Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5648-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="a5648-121">Wählen Sie **"Verwalten"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5648-121">Select **Manage**.</span></span>

6. <span data-ttu-id="a5648-122">Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5648-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="a5648-123">Wenn Sie eine vollständige Zurücksetzung vornehmen und das Gerät auf die Werkseinstellungen zurücksetzen möchten, wählen Sie **"Zurücksetzen auf Werkseinstellungen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5648-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="a5648-124">Wählen Sie "Unternehmensdaten entfernen" aus, um eine selektive Zurücklöschung zu tun und nur Microsoft 365-Organisationsinformationen **zu löschen.**</span><span class="sxs-lookup"><span data-stu-id="a5648-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="a5648-125">Wählen Sie "Gerät entfernen" aus, um das Gerät **aus Ihrer Organisation zu entfernen.**</span><span class="sxs-lookup"><span data-stu-id="a5648-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="a5648-126">Wählen Sie zum Bestätigen **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="a5648-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="a5648-127">Wo finde ich, dass es funktioniert hat?</span><span class="sxs-lookup"><span data-stu-id="a5648-127">How do I know it worked?</span></span>

<span data-ttu-id="a5648-128">Das mobile Gerät wird nicht mehr in der Liste der verwalteten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5648-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="a5648-129">Warum sollten Sie ein Gerät wischen?</span><span class="sxs-lookup"><span data-stu-id="a5648-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="a5648-130">Löschen Sie ein Gerät aus folgenden Gründen:</span><span class="sxs-lookup"><span data-stu-id="a5648-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="a5648-131">Mobile Geräte wie Smartphones und Tablets werden immer häufiger mit vollem Funktionspensing ausgestattet.</span><span class="sxs-lookup"><span data-stu-id="a5648-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="a5648-132">Dies bedeutet, dass es für Ihre Benutzer einfacher ist, vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation zu speichern und unterwegs darauf zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a5648-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="a5648-133">Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Löschen des Geräts verhindern, dass die Informationen Ihrer Organisation in die falschen Hände geraten.</span><span class="sxs-lookup"><span data-stu-id="a5648-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="a5648-134">Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das für Basic Mobility and Security registriert ist, können Sie verhindern, dass Organisationsinformationen mit diesem Benutzer verwendet werden, indem Sie eine Zurücksetzung auf die Werkseinstellungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="a5648-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="a5648-135">Wenn Ihre Organisation Benutzern mobile Geräte zur Verfügung stellt, müssen Sie geräte möglicherweise von Zeit zu Zeit neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a5648-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="a5648-136">Durch das Zurücksetzen auf die Werkseinstellungen auf einem Gerät vor dem Zuweisen zu einem neuen Benutzer wird sichergestellt, dass alle vertraulichen Informationen des vorherigen Besitzers gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a5648-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="a5648-137">Welche Auswirkungen haben Benutzer und Geräte?</span><span class="sxs-lookup"><span data-stu-id="a5648-137">What's the user and device impact?</span></span>

<span data-ttu-id="a5648-138">Die Zurücklöschung wird sofort an das mobile Gerät gesendet, und das Gerät wird in Azure Active Directory als nicht kompatibel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a5648-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="a5648-139">Während alle Daten entfernt werden, wenn ein Gerät auf die Werkseinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für jeden Gerätetyp entfernt werden, wenn Sie Unternehmensdaten entfernen.</span><span class="sxs-lookup"><span data-stu-id="a5648-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="a5648-140">**Inhaltsfeind**</span><span class="sxs-lookup"><span data-stu-id="a5648-140">**Content impace**</span></span>|<span data-ttu-id="a5648-141">**iOS 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="a5648-141">**iOS 10 and later**</span></span>|<span data-ttu-id="a5648-142">**Android 5 und höher**</span><span class="sxs-lookup"><span data-stu-id="a5648-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5648-143">Microsoft 365-App-Daten werden gelöscht, wenn das Gerät durch Intune App Protection-Richtlinien geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="a5648-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="a5648-144">Die Apps werden nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="a5648-144">The apps aren't removed.</span></span> <span data-ttu-id="a5648-145">Bei Geräten, die nicht durch #A0 (Mobile Application Management) geschützt sind, werden zwischengespeicherte Daten von Outlook und OneDrive nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="a5648-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="a5648-146">**Hinweis** Zum Anwenden von Intune-App-Schutzrichtlinien benötigen Sie eine Intune-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="a5648-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="a5648-147">Ja</span><span class="sxs-lookup"><span data-stu-id="a5648-147">Yes</span></span>|<span data-ttu-id="a5648-148">Ja</span><span class="sxs-lookup"><span data-stu-id="a5648-148">Yes</span></span>|
|<span data-ttu-id="a5648-149">Richtlinieneinstellungen, die von Basic Mobility and Security auf Geräte angewendet werden, werden nicht mehr erzwungen. Benutzer können die Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="a5648-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="a5648-150">Ja</span><span class="sxs-lookup"><span data-stu-id="a5648-150">Yes</span></span>|<span data-ttu-id="a5648-151">Ja</span><span class="sxs-lookup"><span data-stu-id="a5648-151">Yes</span></span>|
|<span data-ttu-id="a5648-152">Von Basic Mobility and Security erstellte E-Mail-Profile werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a5648-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="a5648-153">Ja</span><span class="sxs-lookup"><span data-stu-id="a5648-153">Yes</span></span>|<span data-ttu-id="a5648-154">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a5648-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="a5648-155">Die Unternehmensportal-App ist im App Store für iOS und im Play Store für Android verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5648-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a5648-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a5648-156">Related topics</span></span>

[<span data-ttu-id="a5648-157">Einrichten von grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a5648-157">Set up Basic Mobility and Security</span></span>](set-up.md)