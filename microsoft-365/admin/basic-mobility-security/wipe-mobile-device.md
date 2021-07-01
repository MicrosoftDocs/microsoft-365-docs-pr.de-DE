---
title: Zurücksetzen eines mobilen Geräts in Basic Mobility and Security
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
ms.openlocfilehash: c3cc547ce5e135ccdabf9a09b0d572f1b2530f47
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228147"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="4ce8a-103">Zurücksetzen eines mobilen Geräts in Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="4ce8a-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="4ce8a-104">Sie können die integrierte Grundlegende Mobilität und Sicherheit für Microsoft 365 verwenden, um nur Organisationsinformationen zu entfernen, oder um eine Zurücksetzung auf die Werkseinstellungen durchzuführen, um alle Informationen von einem mobilen Gerät zu löschen und in den Werkseinstellungen wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4ce8a-105">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="4ce8a-105">Before you begin</span></span>

<span data-ttu-id="4ce8a-106">Mobile Geräte können vertrauliche Unternehmensinformationen speichern und Zugriff auf die Microsoft 365 Ressourcen Ihrer Organisation gewähren.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="4ce8a-107">Um die Informationen Ihrer Organisation zu schützen, können Sie die Werkseinstellungen zurücksetzen oder Unternehmensdaten entfernen:</span><span class="sxs-lookup"><span data-stu-id="4ce8a-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="4ce8a-108">**Zurücksetzung auf die Werkseinstellungen:** Löscht alle Daten auf dem mobilen Gerät eines Benutzers, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="4ce8a-109">Nach Abschluss der Zurücksetzung wird das Gerät in den Werkseinstellungen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="4ce8a-110">**Unternehmensdaten entfernen:** Entfernt nur Organisationsdaten und verlässt installierte Anwendungen, Fotos und persönliche Informationen auf dem mobilen Gerät eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="4ce8a-111">**Wenn ein Gerät gelöscht wird (Zurücksetzung auf Werkseinstellungen oder Entfernen von Unternehmensdaten),** wird das Gerät aus der Liste der verwalteten Geräte entfernt.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="4ce8a-112">**Automatisches Zurücksetzen eines Geräts:** Sie können eine Grundlegende Mobilitäts- und Sicherheitsrichtlinie einrichten, die ein Gerät automatisch von der Werkseinstellungen zurücksetzt, nachdem der Benutzer eine bestimmte Anzahl von Malen erfolglos versucht, das Gerätekennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="4ce8a-113">Führen Sie dazu die Schritte unter [Erstellen von Gerätesicherheitsrichtlinien für grundlegende Mobilität und Sicherheit](create-device-security-policies.md)aus.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="4ce8a-114">**Wenn Sie die Benutzererfahrung beim** Zurücksetzen des Geräts kennen möchten, sehen Sie sich   [an, welche Auswirkungen der Benutzer und das Gerät haben?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="4ce8a-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="4ce8a-115">Zurücksetzen eines mobilen Geräts</span><span class="sxs-lookup"><span data-stu-id="4ce8a-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="4ce8a-116">Wechseln Sie zum [Microsoft 365 Admin Center](../../admin/admin-overview/about-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="4ce8a-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="4ce8a-117">Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie **"Mobile Geräteverwaltung"** aus der Liste der Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Grundlegende Option für die Verwaltung mobiler Geräte für Mobilität und Secruity":::

3. <span data-ttu-id="4ce8a-119">Wählen Sie **"Geräte verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ce8a-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="4ce8a-120">Wählen Sie das Gerät aus, das Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="4ce8a-121">Wählen Sie **"Verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ce8a-121">Select **Manage**.</span></span>

6. <span data-ttu-id="4ce8a-122">Wählen Sie die Art der Remotezurücksetzung aus, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="4ce8a-123">Um eine vollständige Zurücksetzung durchzuführen und das Gerät auf die Werkseinstellungen zurückzusetzen, wählen Sie **"Werkszurücksetzung"** aus.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="4ce8a-124">Wenn Sie nur Microsoft 365 Organisationsinformationen selektiv zurücksetzen und löschen möchten, wählen Sie **"Unternehmensdaten entfernen" aus.**</span><span class="sxs-lookup"><span data-stu-id="4ce8a-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="4ce8a-125">Um das Gerät aus Ihrer Organisation zu entfernen, wählen Sie **"Gerät entfernen"** aus.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="4ce8a-126">Wählen Sie zum Bestätigen **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="4ce8a-127">Wie kann ich feststellen, dass es funktioniert hat?</span><span class="sxs-lookup"><span data-stu-id="4ce8a-127">How do I know it worked?</span></span>

<span data-ttu-id="4ce8a-128">Das mobile Gerät wird nicht mehr in der Liste der verwalteten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="4ce8a-129">Warum sollten Sie ein Gerät zurücksetzen?</span><span class="sxs-lookup"><span data-stu-id="4ce8a-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="4ce8a-130">Zurücksetzen eines Geräts aus folgenden Gründen:</span><span class="sxs-lookup"><span data-stu-id="4ce8a-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="4ce8a-131">Mobile Geräte wie Smartphones und Tablets werden immer umfassender.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="4ce8a-132">Dies bedeutet, dass es für Ihre Benutzer einfacher ist, vertrauliche Unternehmensinformationen wie persönliche Identifikation oder vertrauliche Kommunikation zu speichern und unterwegs darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="4ce8a-133">Wenn eines dieser mobilen Geräte verloren geht oder gestohlen wird, kann das Zurücksetzen des Geräts dazu beitragen, dass die Informationen Ihrer Organisation nicht in die falschen Hände gelangen.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="4ce8a-134">Wenn ein Benutzer die Organisation mit einem persönlichen Gerät verlässt, das bei Basic Mobility and Security registriert ist, können Sie verhindern, dass Unternehmensinformationen mit diesem Benutzer übertragen werden, indem Sie eine Zurücksetzung auf die Werkseinstellungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="4ce8a-135">Wenn Ihre Organisation Mobilgeräte für Benutzer bereitstellt, müssen Sie geräte von Zeit zu Zeit neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="4ce8a-136">Wenn Sie auf einem Gerät eine Zurücksetzung auf die Werkseinstellungen durchführen, bevor sie einem neuen Benutzer zugewiesen wird, wird sichergestellt, dass alle vertraulichen Informationen des vorherigen Besitzers gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="4ce8a-137">Welche Auswirkungen haben Benutzer und Geräte?</span><span class="sxs-lookup"><span data-stu-id="4ce8a-137">What's the user and device impact?</span></span>

<span data-ttu-id="4ce8a-138">Die Zurücksetzung wird sofort an das mobile Gerät gesendet, und das Gerät wird im Azure Active Directory als nicht kompatibel gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="4ce8a-139">Während alle Daten entfernt werden, wenn ein Gerät auf die Werksstandardeinstellungen zurückgesetzt wird, wird in der folgenden Tabelle beschrieben, welche Inhalte für jeden Gerätetyp entfernt werden, wenn ein Gerät Unternehmensdaten entfernt.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="4ce8a-140">**Auswirkungen auf den Inhalt**</span><span class="sxs-lookup"><span data-stu-id="4ce8a-140">**Content impact**</span></span>|<span data-ttu-id="4ce8a-141">**iOS 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="4ce8a-141">**iOS 10 and later**</span></span>|<span data-ttu-id="4ce8a-142">**Android 5 und höher**</span><span class="sxs-lookup"><span data-stu-id="4ce8a-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ce8a-143">Microsoft 365 App-Daten werden gelöscht, wenn das Gerät durch Intune App Protection-Richtlinien geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="4ce8a-144">Die Apps werden nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-144">The apps aren't removed.</span></span> <span data-ttu-id="4ce8a-145">Für Geräte, die nicht durch MAM-Richtlinien (Mobile Application Management) geschützt sind, entfernen Outlook und OneDrive keine zwischengespeicherten Daten.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="4ce8a-146">**Hinweis** Zum Anwenden von Intune App-Schutzrichtlinien benötigen Sie eine Intune-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="4ce8a-147">Ja</span><span class="sxs-lookup"><span data-stu-id="4ce8a-147">Yes</span></span>|<span data-ttu-id="4ce8a-148">Ja</span><span class="sxs-lookup"><span data-stu-id="4ce8a-148">Yes</span></span>|
|<span data-ttu-id="4ce8a-149">Richtlinieneinstellungen, die von Basic Mobility and Security auf Geräte angewendet werden, werden nicht mehr erzwungen. Benutzer können die Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="4ce8a-150">Ja</span><span class="sxs-lookup"><span data-stu-id="4ce8a-150">Yes</span></span>|<span data-ttu-id="4ce8a-151">Ja</span><span class="sxs-lookup"><span data-stu-id="4ce8a-151">Yes</span></span>|
|<span data-ttu-id="4ce8a-152">E-Mail-Profile, die von Basic Mobility and Security erstellt wurden, werden entfernt, und zwischengespeicherte E-Mails auf dem Gerät werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="4ce8a-153">Ja</span><span class="sxs-lookup"><span data-stu-id="4ce8a-153">Yes</span></span>|<span data-ttu-id="4ce8a-154">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="4ce8a-154">N/A</span></span>|

> [!NOTE]
> <span data-ttu-id="4ce8a-155">Unternehmensportal App ist im App-Store für iOS und im Play-Store für Android-Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4ce8a-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>
