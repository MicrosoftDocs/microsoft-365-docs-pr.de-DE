---
title: Registrieren von Microsoft Defender for Endpoint auf macOS-Geräten bei Jamf Pro
description: Registrieren von Microsoft Defender for Endpoint auf macOS-Geräten bei Jamf Pro
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933097"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="fb1ad-104">Registrieren von Microsoft Defender for Endpoint auf macOS-Geräten bei Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="fb1ad-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fb1ad-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fb1ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="fb1ad-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fb1ad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fb1ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb1ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fb1ad-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="fb1ad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fb1ad-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="fb1ad-110">Registrieren von macOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="fb1ad-110">Enroll macOS devices</span></span>

<span data-ttu-id="fb1ad-111">Es gibt mehrere Methoden zum Registrieren bei JamF.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="fb1ad-112">Dieser Artikel führt Sie zu zwei Methoden:</span><span class="sxs-lookup"><span data-stu-id="fb1ad-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="fb1ad-113">Methode 1: Registrierungseinladungen</span><span class="sxs-lookup"><span data-stu-id="fb1ad-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="fb1ad-114">Methode 2: Vorabregistrierungen</span><span class="sxs-lookup"><span data-stu-id="fb1ad-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="fb1ad-115">Eine vollständige Liste finden Sie unter [Informationen zur Computerregistrierung](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span><span class="sxs-lookup"><span data-stu-id="fb1ad-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="fb1ad-116">Registrierungsmethode 1: Registrierungseinladungen</span><span class="sxs-lookup"><span data-stu-id="fb1ad-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="fb1ad-117">Navigieren Sie im Jamf Pro-Dashboard zu **Registrierungseinladungen**.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Abbildung der Konfigurationseinstellungen1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="fb1ad-119">Wählen Sie **+ Neu aus.**</span><span class="sxs-lookup"><span data-stu-id="fb1ad-119">Select **+ New**.</span></span>

    ![Eine Naht einer automatisch generierten Logobeschreibung](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="fb1ad-121">Geben **Sie unter Empfänger für die Einladung angeben >** unter **E-Mail-Adressen** die E-Mail-Adresse(n) der Empfänger ein.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Abbildung der Konfigurationseinstellungen2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Abbildung der Konfigurationseinstellungen3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="fb1ad-124">Beispiel: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fb1ad-124">For example: janedoe@contoso.com</span></span>

    ![Abbildung der Konfigurationseinstellungen4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="fb1ad-126">Konfigurieren Sie die Nachricht für die Einladung.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-126">Configure the message for the invitation.</span></span>

    ![Abbildung der Konfigurationseinstellungen5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Abbildung der Konfigurationseinstellungen6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Abbildung der Konfigurationseinstellungen7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Abbildung der Konfigurationseinstellungen8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="fb1ad-131">Registrierungsmethode 2: Vorabregistrierungen</span><span class="sxs-lookup"><span data-stu-id="fb1ad-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="fb1ad-132">Navigieren Sie im Jamf Pro-Dashboard zu **Prestage enrollments**.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Abbildung der Konfigurationseinstellungen9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="fb1ad-134">Befolgen Sie die Anweisungen unter [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span><span class="sxs-lookup"><span data-stu-id="fb1ad-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="fb1ad-135">Registrieren des macOS-Geräts</span><span class="sxs-lookup"><span data-stu-id="fb1ad-135">Enroll macOS device</span></span>

1. <span data-ttu-id="fb1ad-136">Wählen **Sie Weiter** aus, und installieren Sie das Zertifizierungsstellenzertifikat in einem **Systemeinstellungsfenster.**</span><span class="sxs-lookup"><span data-stu-id="fb1ad-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Abbildung der Jamf Pro-Registrierung1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="fb1ad-138">Kehren Sie nach der Installation des Zertifizierungsstellenzertifikats zum Browserfenster zurück, und wählen Sie **Weiter aus,** und installieren Sie das MDM-Profil.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Abbildung der Jamf Pro-Registrierung2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="fb1ad-140">Wählen **Sie Downloads** von JAMF zulassen aus.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Abbildung von Jamf Pro enrollment3](images/jamfpro-download.png)

4. <span data-ttu-id="fb1ad-142">Wählen **Sie Weiter** aus, um mit der INSTALLATION des MDM-Profils fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Abbildung von Jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="fb1ad-144">Wählen **Sie Weiter** aus, um das MDM-Profil zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Abbildung von Jamf Pro Enrollment5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="fb1ad-146">Wählen **Sie Weiter**  aus, um die Konfiguration zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="fb1ad-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Abbildung von Jamf Pro Enrollment6](images/jamfpro-mdm-profile.png)
