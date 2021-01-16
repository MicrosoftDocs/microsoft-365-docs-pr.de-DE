---
title: Problembehandlung für grundlegende Mobilität und Sicherheit
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
description: Führen Sie die folgenden Schritte aus, um Probleme mit der einfachen Mobilität und Sicherheit nachverfolgt zu werden.
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876852"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="777c6-103">Problembehandlung für grundlegende Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="777c6-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="777c6-104">Wenn beim Versuch, ein Gerät in Basic Mobility and Security zu registrieren, Probleme auftreten, führen Sie die hier gezeigten Schritte aus, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="777c6-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="777c6-105">Wenn das Problem mit den allgemeinen Schritten nicht behoben wird, finden Sie weitere Informationen in einem der späteren Abschnitte mit spezifischen Schritten für Ihren Gerätetyp.</span><span class="sxs-lookup"><span data-stu-id="777c6-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="777c6-106">Schritte zum ersten Versuch</span><span class="sxs-lookup"><span data-stu-id="777c6-106">Steps to try first</span></span>

<span data-ttu-id="777c6-107">Überprüfen Sie zunächst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="777c6-107">To start, check the following:</span></span>

- <span data-ttu-id="777c6-108">Stellen Sie sicher, dass das Gerät noch nicht bei einem anderen Anbieter für die Verwaltung mobiler Geräte registriert ist, z. B. Intune.</span><span class="sxs-lookup"><span data-stu-id="777c6-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="777c6-109">Stellen Sie sicher, dass das Gerät auf das richtige Datum und die richtige Uhrzeit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="777c6-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="777c6-110">Wechseln Sie auf dem Gerät zu einem anderen WLAN oder Mobilfunknetz.</span><span class="sxs-lookup"><span data-stu-id="777c6-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="777c6-111">Deinstallieren Sie für Android- oder iOS-Geräte die Intune-Unternehmensportal-App auf dem Gerät, und installieren Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="777c6-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="777c6-112">iOS-Smartphone oder -Tablet</span><span class="sxs-lookup"><span data-stu-id="777c6-112">iOS phone or tablet</span></span>

- <span data-ttu-id="777c6-113">Stellen Sie sicher, dass Sie ein APNs-Zertifikat eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="777c6-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="777c6-114">Weitere Informationen finden Sie unter [Erstellen eines APNs-Zertifikats für iOS-Geräte.](create-an-apns-certificate-for-ios-devices.md)</span><span class="sxs-lookup"><span data-stu-id="777c6-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="777c6-115">Stellen **Sie in**   >  **den** Einstellungen "Allgemeines   >  **Profil" (oder "Geräteverwaltung")** sicher, dass ein Verwaltungsprofil noch nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="777c6-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="777c6-116">Wenn dies der Benutzer ist, entfernen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="777c6-116">If it is, remove it.</span></span>

- <span data-ttu-id="777c6-117">Wenn die Fehlermeldung "Gerät konnte nicht registriert werden" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der am Gerät angemeldet ist, eine Lizenz zugewiesen wurde, die Exchange Online enthält.</span><span class="sxs-lookup"><span data-stu-id="777c6-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="777c6-118">Wenn die Fehlermeldung "Profil konnte nicht installiert werden" angezeigt wird, probieren Sie eine der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="777c6-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="777c6-119">Stellen Sie sicher, dass Safari der Standardbrowser auf dem Gerät ist und cookies nicht deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="777c6-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="777c6-120">Starten Sie das Gerät neu, und navigieren Sie dann zu portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="777c6-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="777c6-121">Melden Sie sich mit Ihrer Microsoft 365-Benutzer-ID und Ihrem Kennwort an, und versuchen Sie, das Profil manuell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="777c6-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="777c6-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="777c6-122">Windows RT</span></span>

- <span data-ttu-id="777c6-123">Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von Basic Mobility and Security eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="777c6-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="777c6-124">Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="777c6-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="777c6-125">Stellen Sie sicher, dass \*\*\*\* der Benutzer "Aktivieren" und   nicht "Beitreten" **aus.**</span><span class="sxs-lookup"><span data-stu-id="777c6-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="777c6-126">Windows 10-PC</span><span class="sxs-lookup"><span data-stu-id="777c6-126">Windows 10 PC</span></span>

- <span data-ttu-id="777c6-127">Stellen Sie sicher, dass Ihre Domäne in Microsoft 365 für die Verwendung von Basic Mobility and Security eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="777c6-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="777c6-128">Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="777c6-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="777c6-129">Wenn Sie nicht über Azure Active Directory Premium \*\*\*\* verfügen, stellen Sie sicher, dass der Benutzer nur die Geräteverwaltung registrieren und nicht    **"Verbinden" aus.**</span><span class="sxs-lookup"><span data-stu-id="777c6-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="777c6-130">Smartphone oder Tablet für Android</span><span class="sxs-lookup"><span data-stu-id="777c6-130">Android phone or tablet</span></span>

- <span data-ttu-id="777c6-131">Stellen Sie sicher, dass auf dem Gerät Android 4.4 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="777c6-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="777c6-132">Stellen Sie sicher, dass Chrome auf dem neuesten Stand ist und als Standardbrowser festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="777c6-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="777c6-133">Wenn die Fehlermeldung "Dieses Gerät konnte nicht registriert werden" angezeigt wird, melden Sie sich bei Microsoft 365 an, und stellen Sie sicher, dass dem Benutzer, der am Gerät angemeldet ist, eine Lizenz mit Exchange Online zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="777c6-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="777c6-134">Überprüfen Sie den Benachrichtigungsbereich auf dem Gerät, um zu sehen, ob erforderliche Endbenutzeraktionen ausstehen, und führen Sie, falls dies der Fall ist, die Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="777c6-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>