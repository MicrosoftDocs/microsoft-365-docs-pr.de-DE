---
title: Schützen nicht verwalteter Windows 10-PCs und Macs
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Schützen Sie sich gegen Phishing und andere Angriffe mit Microsoft 365 für Kampagnen.
ms.openlocfilehash: 0cd96cb73ad3d0b38ab1e5ff31c913d97528c2d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632791"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="bf785-103">Schützen nicht verwalteter Windows 10-PCs und Macs</span><span class="sxs-lookup"><span data-stu-id="bf785-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="bf785-104">Sie können Windows 10-PCs und Macs verwalten, indem Sie Sie in Microsoft InTune registrieren, sodass Sie vor dem Zugriff auf Daten in Ihrer Umgebung sicherstellen, dass Sie gesund und sicher sind.</span><span class="sxs-lookup"><span data-stu-id="bf785-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="bf785-105">Viele Kampagnen und kleine Unternehmen umfassen jedoch Mitarbeiter, die ihre eigenen Geräte mitbringen (BYOD), die nicht von der Organisation verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="bf785-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="bf785-106">Verwenden Sie diesen Artikel für diese nicht verwalteten PCs und Macs, um sicherzustellen, dass die minimalen Sicherheitsfunktionen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="bf785-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="bf785-107">Schützen eines Computers mit Windows 10 oder einem Mac</span><span class="sxs-lookup"><span data-stu-id="bf785-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="bf785-108">Wenn Ihr Windows 10-PC oder Mac nicht von Ihrer Organisation verwaltet wird, müssen Sie diese Sicherheitsfunktionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf785-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="bf785-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bf785-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="bf785-110">**Aktivieren der Geräteverschlüsselung**</span><span class="sxs-lookup"><span data-stu-id="bf785-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="bf785-111">Die Geräteverschlüsselung steht für eine Vielzahl von Windows-Geräten zur Verfügung und schützt Ihre Daten durch Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="bf785-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="bf785-112">Wenn Sie die Geräteverschlüsselung aktivieren, können nur autorisierte Personen auf Ihr Gerät und Ihre Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bf785-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="bf785-113">Anweisungen finden Sie unter [Aktivieren der Geräteverschlüsselung](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) .</span><span class="sxs-lookup"><span data-stu-id="bf785-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="bf785-114">Wenn die Geräteverschlüsselung auf Ihrem Gerät nicht verfügbar ist, können Sie stattdessen die standardmäßige [BitLocker-Verschlüsselung](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bf785-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="bf785-115">(BitLocker ist unter Windows 10 Home Edition nicht verfügbar.)</span><span class="sxs-lookup"><span data-stu-id="bf785-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="bf785-116">**Schützen Ihres Geräts mit Windows-Sicherheit**</span><span class="sxs-lookup"><span data-stu-id="bf785-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="bf785-117">Wenn Sie über Windows 10 verfügen, erhalten Sie den neuesten Virenschutz mit Windows-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="bf785-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="bf785-118">Wenn Sie Windows 10 zum ersten Mal starten, wird die Windows-Sicherheit aktiv und hilft Ihnen, Ihren PC zu schützen, indem Sie auf Schadsoftware (Schadsoftware), Viren und Sicherheitsbedrohungen überprüft.</span><span class="sxs-lookup"><span data-stu-id="bf785-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="bf785-119">Windows-Sicherheit verwendet den Echtzeitschutz zum Überprüfen aller Inhalte, die Sie auf Ihrem PC herunterladen oder ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf785-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="bf785-120">Windows Update lädt Updates für die Windows-Sicherheit automatisch herunter, um Ihren PC sicher zu halten und vor Bedrohungen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="bf785-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="bf785-121">Wenn Sie über eine frühere Version von Windows verfügen und Microsoft Security Essentials verwenden, empfiehlt es sich, zu Windows-Sicherheit zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="bf785-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="bf785-122">Weitere Informationen finden Sie unter [Help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span><span class="sxs-lookup"><span data-stu-id="bf785-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="bf785-123">**Aktivieren der Windows-Firewall**</span><span class="sxs-lookup"><span data-stu-id="bf785-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="bf785-124">Sie sollten die Windows-Firewall immer ausführen, auch wenn Sie eine andere Firewall aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="bf785-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="bf785-125">Durch das Deaktivieren der Windows-Firewall wird möglicherweise Ihr Gerät (und Ihr Netzwerk, falls vorhanden) anfälliger für nicht autorisierten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="bf785-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="bf785-126">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Windows-Firewall](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) für Anweisungen</span><span class="sxs-lookup"><span data-stu-id="bf785-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="bf785-127">Mac</span><span class="sxs-lookup"><span data-stu-id="bf785-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="bf785-128">**Verwenden von FileVault zum Verschlüsseln des Mac-Datenträgers**</span><span class="sxs-lookup"><span data-stu-id="bf785-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="bf785-129">Durch die Datenträgerverschlüsselung werden Daten geschützt, wenn Geräte verloren gehen oder gestohlen werden.</span><span class="sxs-lookup"><span data-stu-id="bf785-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="bf785-130">FileVault-Verschlüsselung mit vollständiger Festplatte verhindert nicht autorisierten Zugriff auf die Informationen auf dem Startdatenträger.</span><span class="sxs-lookup"><span data-stu-id="bf785-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="bf785-131">Anweisungen dazu finden Sie unter [Verwenden von FileVault zum Verschlüsseln des Startdatenträgers auf dem Mac](https://support.apple.com/HT204837) .</span><span class="sxs-lookup"><span data-stu-id="bf785-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="bf785-132">**Schützen des Mac vor Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="bf785-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="bf785-133">Microsoft empfiehlt die Installation und Verwendung zuverlässiger Antivirensoftware auf Ihrem Mac.</span><span class="sxs-lookup"><span data-stu-id="bf785-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="bf785-134">Im folgenden Artikel finden Sie eine Liste der Optionen: [Best Mac Antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="bf785-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="bf785-135">Sie können das Risiko von Schadsoftware auch reduzieren, indem Sie Software nur aus zuverlässigen Quellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf785-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="bf785-136">Mit den Einstellungen in Sicherheits & Datenschutzeinstellungen können Sie die auf Ihrem Mac installierten Softwarequellen angeben.</span><span class="sxs-lookup"><span data-stu-id="bf785-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="bf785-137">Weitere Informationen finden Sie unter [Protect Your Mac from Schadsoftware](https://support.apple.com/kb/PH25087).</span><span class="sxs-lookup"><span data-stu-id="bf785-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="bf785-138">**Aktivieren des Firewall-Schutzes**</span><span class="sxs-lookup"><span data-stu-id="bf785-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="bf785-139">Verwenden Sie Firewalleinstellungen, um Ihren Mac vor unerwünschten Kontakten zu schützen, die von anderen Computern initiiert wurden, wenn Sie mit dem Internet oder einem Netzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="bf785-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="bf785-140">Ohne diesen Schutz ist Ihr Mac möglicherweise anfälliger für unbefugten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="bf785-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="bf785-141">Anweisungen finden Sie unter [Informationen zur Anwendungs Firewall](https://support.apple.com/HT201642) .</span><span class="sxs-lookup"><span data-stu-id="bf785-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
