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
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Registrieren von Microsoft Defender for Endpoint auf macOS-Geräten bei Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Registrieren von macOS-Geräten

Es gibt mehrere Methoden zum Registrieren bei JamF.

Dieser Artikel führt Sie zu zwei Methoden:

- [Methode 1: Registrierungseinladungen](#enrollment-method-1-enrollment-invitations)
- [Methode 2: Vorabregistrierungen](#enrollment-method-2-prestage-enrollments)

Eine vollständige Liste finden Sie unter [Informationen zur Computerregistrierung](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).


## <a name="enrollment-method-1-enrollment-invitations"></a>Registrierungsmethode 1: Registrierungseinladungen

1. Navigieren Sie im Jamf Pro-Dashboard zu **Registrierungseinladungen**.

    ![Abbildung der Konfigurationseinstellungen1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Wählen Sie **+ Neu aus.**

    ![Eine Naht einer automatisch generierten Logobeschreibung](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. Geben **Sie unter Empfänger für die Einladung angeben >** unter **E-Mail-Adressen** die E-Mail-Adresse(n) der Empfänger ein.

    ![Abbildung der Konfigurationseinstellungen2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Abbildung der Konfigurationseinstellungen3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Beispiel: janedoe@contoso.com

    ![Abbildung der Konfigurationseinstellungen4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Konfigurieren Sie die Nachricht für die Einladung.

    ![Abbildung der Konfigurationseinstellungen5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Abbildung der Konfigurationseinstellungen6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Abbildung der Konfigurationseinstellungen7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Abbildung der Konfigurationseinstellungen8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Registrierungsmethode 2: Vorabregistrierungen

1. Navigieren Sie im Jamf Pro-Dashboard zu **Prestage enrollments**.

    ![Abbildung der Konfigurationseinstellungen9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Befolgen Sie die Anweisungen unter [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).

## <a name="enroll-macos-device"></a>Registrieren des macOS-Geräts

1. Wählen **Sie Weiter** aus, und installieren Sie das Zertifizierungsstellenzertifikat in einem **Systemeinstellungsfenster.**

    ![Abbildung der Jamf Pro-Registrierung1](images/jamfpro-ca-certificate.png)

2. Kehren Sie nach der Installation des Zertifizierungsstellenzertifikats zum Browserfenster zurück, und wählen Sie **Weiter aus,** und installieren Sie das MDM-Profil. 

    ![Abbildung der Jamf Pro-Registrierung2](images/jamfpro-install-mdm-profile.png)

3. Wählen **Sie Downloads** von JAMF zulassen aus.

    ![Abbildung von Jamf Pro enrollment3](images/jamfpro-download.png)

4. Wählen **Sie Weiter** aus, um mit der INSTALLATION des MDM-Profils fortzufahren. 

    ![Abbildung von Jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. Wählen **Sie Weiter** aus, um das MDM-Profil zu installieren.

    ![Abbildung von Jamf Pro Enrollment5](images/jamfpro-mdm-unverified.png)

6. Wählen **Sie Weiter**  aus, um die Konfiguration zu vervollständigen. 

    ![Abbildung von Jamf Pro Enrollment6](images/jamfpro-mdm-profile.png)
