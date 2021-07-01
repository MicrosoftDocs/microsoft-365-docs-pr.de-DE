---
title: Registrieren Ihres mobilen Geräts mit basic Mobility and Security
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
description: Bevor Sie Microsoft 365 Dienste mit Ihrem Gerät verwenden können, müssen Sie es möglicherweise zuerst bei Basic Mobility and Security for Microsoft 365 registrieren.
ms.openlocfilehash: 9da3424409a950670e3be45354a5c399fec52372
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228183"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="0f782-103">Registrieren Ihres mobilen Geräts mit basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="0f782-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="0f782-104">Die Verwendung Ihres Telefons, Tablets und anderer mobiler Geräte für die Arbeit ist eine großartige Möglichkeit, um auf dem Laufenden zu bleiben und an Geschäftsprojekten zu arbeiten, während Sie sich nicht im Büro befinden.</span><span class="sxs-lookup"><span data-stu-id="0f782-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="0f782-105">Bevor Sie Microsoft 365 Dienste mit Ihrem Gerät verwenden können, müssen Sie es möglicherweise zuerst bei Basic Mobility and Security für Microsoft 365 mit Microsoft Intune Unternehmensportal registrieren.</span><span class="sxs-lookup"><span data-stu-id="0f782-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="0f782-106">Organisationen wählen Basic Mobility and Security, damit Mitarbeiter mit ihren mobilen Geräten sicher auf geschäftliche E-Mails, Kalender und Dokumente zugreifen können, während das Unternehmen wichtige Daten sichert und ihre Complianceanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="0f782-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="0f782-107">Weitere Informationen finden Sie unter [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f782-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="0f782-108">Weitere Informationen finden Sie unter [Welche Informationen kann meine Organisation sehen, wenn ich mein Gerät registriert?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="0f782-108">For more info, see [What information can my organization see when I enroll my device?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f782-109">Wenn Sie Ihr Gerät bei Basic Mobility and Security für Microsoft 365 registrieren, müssen Sie möglicherweise ein Kennwort einrichten, zusammen mit der Möglichkeit, dass Ihre Arbeitsorganisation das Gerät zurücksetzen kann.</span><span class="sxs-lookup"><span data-stu-id="0f782-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="0f782-110">Eine Gerätezurücksetzung kann vom Microsoft 365 Admin Center durchgeführt werden, um beispielsweise alle Daten vom Gerät zu entfernen, wenn das Kennwort zu oft falsch eingegeben wurde oder nutzungsbegriffe fehlerhaft sind.</span><span class="sxs-lookup"><span data-stu-id="0f782-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="0f782-111">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="0f782-111">Supported devices</span></span>

<span data-ttu-id="0f782-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span><span class="sxs-lookup"><span data-stu-id="0f782-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="0f782-113">Die folgenden Optionen werden mit Basic Mobility and Security unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0f782-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="0f782-114">iOS 10.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="0f782-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="0f782-115">Android 4.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="0f782-115">Android 4.4 or later</span></span>

- <span data-ttu-id="0f782-116">Windows 8.1 und Windows 10 (Telefon und PC)</span><span class="sxs-lookup"><span data-stu-id="0f782-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="0f782-117">Wenn Ihr Gerät oben nicht aufgeführt ist und Sie es mit Basic Mobility and Security verwenden müssen, wenden Sie sich an Ihren Arbeits- oder Schuladministrator.</span><span class="sxs-lookup"><span data-stu-id="0f782-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

> [!TIP]
> <span data-ttu-id="0f782-118">Wenn Sie Probleme bei der Registrierung Ihres Geräts haben, finden Sie informationen unter [Problembehandlung für grundlegende Mobilität und Sicherheit.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="0f782-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="0f782-119">Einrichten Ihres mobilen Geräts mit Intune und Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="0f782-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="0f782-120">Die Intune-Unternehmensportal ermöglicht die Verwaltung eines Geräts durch Microsoft 365 und Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="0f782-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="0f782-121">iPhone oder iPad</span><span class="sxs-lookup"><span data-stu-id="0f782-121">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="0f782-122">Sie können E-Mails erst senden und empfangen, wenn Sie diesen Schritt abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0f782-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="0f782-123">Wechseln Sie zum Apple App-Store, und laden Sie Intune-Unternehmensportal herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="0f782-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="0f782-124">Informationen zum Verbinden und Konfigurieren Ihres iOS-Telefons oder Tablets mit dem Unternehmensportal für Office 365 finden Sie unter Einrichten des [iOS-Gerätezugriffs auf Ihre Unternehmensressourcen.](/mem/intune/user-help/enroll-your-device-in-intune-ios)</span><span class="sxs-lookup"><span data-stu-id="0f782-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](/mem/intune/user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="0f782-125">Android-Smartphone oder -Tablet</span><span class="sxs-lookup"><span data-stu-id="0f782-125">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="0f782-126">Sie können E-Mails erst senden und empfangen, wenn Sie diesen Schritt abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0f782-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="0f782-127">Wechseln Sie zum Google Play Store, und laden Sie Intune-Unternehmensportal herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="0f782-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="0f782-128">Informationen zum Verbinden und Konfigurieren Ihres Android-Telefons oder Tablets mit dem Unternehmensportal für Microsoft 365 finden Sie unter [Registrieren Ihres Geräts bei Unternehmensportal.](/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="0f782-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="0f782-129">Windows 8.1 und Windows 10</span><span class="sxs-lookup"><span data-stu-id="0f782-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="0f782-130">Wechseln Sie zum Microsoft Store, und laden Sie Intune-Unternehmensportal herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="0f782-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="0f782-131">Informationen zum Verbinden und Konfigurieren Ihres Windows Telefons oder PCs mit dem Unternehmensportal zum Microsoft 365 finden Sie unter [Windows Geräteregistrierung in Intune-Unternehmensportal.](/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="0f782-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f782-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0f782-132">Next steps</span></span>

<span data-ttu-id="0f782-133">Nachdem Ihr Gerät in Basic Mobility and Security registriert wurde, können Sie mit Office Apps auf Ihrem Gerät beginnen, um mit E-Mails, Kalendern, Kontakten und Dokumenten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f782-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>