---
title: Problembehandlung bei grundlegender Mobilität und Sicherheit
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Führen Sie die folgenden Schritte aus, um grundlegende Mobilitäts-und Sicherheitsprobleme zu ermitteln.
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336898"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="868a2-103">Problembehandlung bei grundlegender Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="868a2-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="868a2-104">Wenn Sie beim Versuch, ein Gerät in grundlegender Mobilität und Sicherheit zu registrieren, Probleme haben, führen Sie die Schritte hier aus, um das Problem zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="868a2-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="868a2-105">Wenn das Problem durch die allgemeinen Schritte nicht behoben werden kann, lesen Sie einen der nachfolgenden Abschnitte mit bestimmten Schritten für Ihren Gerätetyp.</span><span class="sxs-lookup"><span data-stu-id="868a2-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="868a2-106">Schritte zum ersten Versuch</span><span class="sxs-lookup"><span data-stu-id="868a2-106">Steps to try first</span></span>

<span data-ttu-id="868a2-107">Überprüfen Sie zunächst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="868a2-107">To start, check the following:</span></span>

- <span data-ttu-id="868a2-108">Stellen Sie sicher, dass das Gerät nicht bereits mit einem anderen Anbieter für die Verwaltung mobiler Geräte wie InTune registriert ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="868a2-109">Stellen Sie sicher, dass das Gerät auf das richtige Datum und die korrekte Uhrzeit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="868a2-110">Wechseln Sie zu einem anderen WLAN-oder Mobilfunknetz auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="868a2-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="868a2-111">Für Android-oder IOS-Geräte deinstallieren Sie die Intune-Unternehmens Portal-App auf dem Gerät, und installieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="868a2-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="868a2-112">IOS-Telefon oder-Tablet</span><span class="sxs-lookup"><span data-stu-id="868a2-112">iOS phone or tablet</span></span>

- <span data-ttu-id="868a2-113">Stellen Sie sicher, dass Sie ein APNs-Zertifikat eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="868a2-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="868a2-114">Weitere Informationen finden Sie unter [Erstellen eines APNs-Zertifikats für IOS-Geräte](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="868a2-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="868a2-115"> *\*Settings**   >  *\*General**   > Stellen Sie sicher, dass in Einstellungen Allgemeines *\*Profil (oder Geräteverwaltung)** kein Verwaltungsprofil bereits installiert ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="868a2-116">Wenn dies der Fall ist, entfernen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="868a2-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="868a2-117">Wenn die Fehlermeldung "Gerät konnte nicht registriert werden" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der sich am Gerät angemeldet hat, eine Lizenz mit Exchange Online zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="868a2-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="868a2-118">Wenn die Fehlermeldung "Profil konnte nicht installiert werden" angezeigt wird, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="868a2-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="868a2-119">Stellen Sie sicher, dass Safari der Standardbrowser auf dem Gerät ist und dass Cookies nicht deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="868a2-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="868a2-120">Starten Sie das Gerät neu, und navigieren Sie dann zu Portal.Manage.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="868a2-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="868a2-121">Melden Sie sich mit Ihrer Microsoft 365-Benutzer-ID und Ihrem Kennwort an, und versuchen Sie, das Profil manuell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="868a2-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="868a2-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="868a2-122">Windows RT</span></span>

- <span data-ttu-id="868a2-123">Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von grundlegender Mobilität und Sicherheit eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="868a2-124">Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="868a2-124">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="868a2-125">Stellen Sie sicher, dass der Benutzer **die Option "Anmelden" wählt,**   anstatt " **beitreten**" auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="868a2-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="868a2-126">Windows 10-PC</span><span class="sxs-lookup"><span data-stu-id="868a2-126">Windows 10 PC</span></span>

- <span data-ttu-id="868a2-127">Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von grundlegender Mobilität und Sicherheit eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="868a2-128">Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="868a2-128">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="868a2-129">Wenn Sie nicht über Azure Active Directory Premium verfügen, müssen Sie sicherstellen, dass der Benutzer **nur in der Geräteverwaltung registrieren**auswählt,   anstatt **Connect**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="868a2-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="868a2-130">Android-Telefon oder-Tablet</span><span class="sxs-lookup"><span data-stu-id="868a2-130">Android phone or tablet</span></span>

- <span data-ttu-id="868a2-131">Stellen Sie sicher, dass auf dem Gerät Android 4,4 oder höher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="868a2-132">Stellen Sie sicher, dass Chrome auf dem neuesten Stand ist und als Standardbrowser festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="868a2-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="868a2-133">Wenn die Fehlermeldung "Wir konnten dieses Gerät nicht registrieren" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der sich am Gerät angemeldet hat, eine Lizenz zugewiesen wurde, die Exchange Online enthält.</span><span class="sxs-lookup"><span data-stu-id="868a2-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="868a2-134">Überprüfen Sie den Benachrichtigungsbereich auf dem Gerät, um festzustellen, ob alle erforderlichen Endbenutzeraktionen ausstehen, und führen Sie, falls dies der Fall ist, die Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="868a2-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>