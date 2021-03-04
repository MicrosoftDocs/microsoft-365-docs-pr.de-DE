---
title: Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security
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
description: Bevor Sie Microsoft 365-Dienste mit Ihrem Gerät verwenden können, müssen Sie sie möglicherweise zuerst in Basic Mobility and Security für Microsoft 365 registrieren.
ms.openlocfilehash: 2a9c0bd9faf670d7dca340d3bc4e9f6586bd6b66
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423201"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="833b4-103">Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="833b4-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="833b4-104">Die Verwendung Ihres Telefons, Tablets und anderer mobiler Geräte für die Arbeit ist eine hervorragende Möglichkeit, um auf dem Laufenden zu bleiben und an Geschäftsprojekten zu arbeiten, während Sie nicht im Büro sind.</span><span class="sxs-lookup"><span data-stu-id="833b4-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="833b4-105">Bevor Sie Microsoft 365-Dienste mit Ihrem Gerät verwenden können, müssen Sie sie möglicherweise zuerst in Basic Mobility and Security für Microsoft 365 mithilfe des Microsoft Intune-Unternehmensportals registrieren.</span><span class="sxs-lookup"><span data-stu-id="833b4-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="833b4-106">Organisationen wählen Grundlegende Mobilität und Sicherheit aus, damit Mitarbeiter ihre mobilen Geräte verwenden können, um sicher auf geschäftliche E-Mails, Kalender und Dokumente zu zugreifen, während das Unternehmen wichtige Daten sichert und seine Complianceanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="833b4-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="833b4-107">Weitere Informationen finden Sie unter [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="833b4-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="833b4-108">Weitere Informationen finden Sie unter [Welche Informationen kann meine Organisation sehen, wenn ich mein Gerät registriert?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="833b4-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="833b4-109">Wenn Sie Ihr Gerät in Basic Mobility and Security für Microsoft 365 registrieren, müssen Sie möglicherweise ein Kennwort einrichten und der Arbeitsorganisation das Zurücksetzen des Geräts ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="833b4-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="833b4-110">Eine Gerätelöschung kann aus dem Microsoft 365 Admin Center ausgeführt werden, um beispielsweise alle Daten vom Gerät zu entfernen, wenn das Kennwort zu oft falsch eingegeben wurde oder wenn Nutzungsbedingungen beschädigt sind.</span><span class="sxs-lookup"><span data-stu-id="833b4-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="833b4-111">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="833b4-111">Supported devices</span></span>

<span data-ttu-id="833b4-112">Die grundlegende Mobilität und Sicherheit für Microsoft 365, die vom Intune-Dienst gehostet werden, funktioniert mit den meisten, aber nicht allen mobilen Geräten.</span><span class="sxs-lookup"><span data-stu-id="833b4-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="833b4-113">Die folgenden Funktionen werden von Basic Mobility and Security unterstützt:</span><span class="sxs-lookup"><span data-stu-id="833b4-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="833b4-114">iOS 10.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="833b4-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="833b4-115">Android 4.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="833b4-115">Android 4.4 or later</span></span>

- <span data-ttu-id="833b4-116">Windows 8.1 und Windows 10 (Telefon und PC)</span><span class="sxs-lookup"><span data-stu-id="833b4-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="833b4-117">Wenn Ihr Gerät nicht oben aufgeführt ist und Sie es mit Basic Mobility and Security verwenden müssen, wenden Sie sich an Ihren Arbeits- oder Schuladministrator.</span><span class="sxs-lookup"><span data-stu-id="833b4-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="833b4-118">Wenn Sie Probleme beim Registrieren Ihres Geräts haben, finden Sie weitere Informationen unter [Problembehandlung für grundlegende Mobilität und Sicherheit](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="833b4-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="833b4-119">Einrichten Ihres mobilen Geräts mit Intune und Grundlegende Mobilität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="833b4-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="833b4-120">Das Intune-Unternehmensportal ermöglicht die Verwaltung eines Geräts durch Microsoft 365 und Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="833b4-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="833b4-121">iPhone oder iPad</span><span class="sxs-lookup"><span data-stu-id="833b4-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="833b4-122">Sie können E-Mails erst senden und empfangen, wenn Sie diesen Schritt abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="833b4-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="833b4-123">Wechseln Sie zum Apple App Store, und laden Sie das Intune-Unternehmensportal herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="833b4-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="833b4-124">Informationen zum Verbinden und Konfigurieren Ihres iOS-Telefons oder Tablets mit dem Unternehmensportal zu Office 365 finden Sie unter Einrichten des iOS-Gerätezugriffs [auf Ihre Unternehmensressourcen.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="833b4-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="833b4-125">Android-Smartphone oder -Tablet</span><span class="sxs-lookup"><span data-stu-id="833b4-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="833b4-126">Sie können E-Mails erst senden und empfangen, wenn Sie diesen Schritt abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="833b4-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="833b4-127">Wechseln Sie zum Google Play Store, und laden Sie das Intune-Unternehmensportal herunter und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="833b4-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="833b4-128">Informationen zum Verbinden und Konfigurieren Ihres Android-Smartphones oder Tablets mit dem Unternehmensportal zu Microsoft 365 finden Sie unter Registrieren Ihres Geräts [beim Unternehmensportal](https://go.microsoft.com/fwlink/?linkid=875317).</span><span class="sxs-lookup"><span data-stu-id="833b4-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="833b4-129">Windows 8.1 und Windows 10</span><span class="sxs-lookup"><span data-stu-id="833b4-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="833b4-130">Wechseln Sie zum Microsoft Store, und laden Sie das Intune-Unternehmensportal herunter und installieren Sie es</span><span class="sxs-lookup"><span data-stu-id="833b4-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="833b4-131">Informationen zum Verbinden und Konfigurieren Ihres Windows-Telefons oder -PCs mit dem Unternehmensportal zu Microsoft 365 finden Sie unter Registrierung von [Windows-Geräten im Intune-Unternehmensportal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="833b4-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="833b4-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="833b4-132">What's next?</span></span>

<span data-ttu-id="833b4-133">Nachdem Ihr Gerät in Basic Mobility and Security registriert wurde, können Sie mit der Verwendung von Office-Apps auf Ihrem Gerät beginnen, um mit E-Mails, Kalendern, Kontakten und Dokumenten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="833b4-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
