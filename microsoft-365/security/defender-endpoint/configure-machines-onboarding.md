---
title: Get devices onboarded to Microsoft Defender for Endpoint
description: Verfolgen Sie das Onboarding von von Intune verwalteten Geräten zu Microsoft Defender for Endpoint, und erhöhen Sie die Onboardingrate.
keywords: Onboard, Intune-Verwaltung, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, Konfigurationsverwaltung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e0d5a13b0c33516209bd2d18361a1de6ab9245c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932941"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Get devices onboarded to Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Jedes integrierte Gerät fügt einen zusätzlichen EDR (EDR) hinzu und erhöht die Sichtbarkeit über Sicherheitsverletzungen in Ihrem Netzwerk. Das Onboarding stellt außerdem sicher, dass ein Gerät auf anfällige Komponenten sowie Sicherheitskonfigurationsprobleme überprüft werden kann und kritische Korrekturaktionen während von Angriffen erhalten kann.

Bevor Sie das Onboarding von Geräten nachverfolgen und verwalten können:
- [Registrieren Ihrer Geräte bei der Intune-Verwaltung](configure-machines.md#enroll-devices-to-intune-management)
- [Sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>Ermitteln und Nachverfolgen ungeschützter Geräte

Die **Onboardingkarte** bietet einen umfassenden Überblick über Ihre Onboardingrate, indem sie die Anzahl der Windows 10-Geräte, die tatsächlich in Defender for Endpoint integrierte sind, mit der Gesamtzahl der von Intune verwalteten Windows 10 vergleicht.

![Onboardingkarte für die Gerätekonfigurationsverwaltung](images/secconmgmt_onboarding_card.png)<br>
*Karte mit integrierten Geräten im Vergleich zur Gesamtzahl der von Intune verwalteten Windows 10 Gerät*

>[!NOTE]
>Wenn Sie Security Center Configuration Manager, das Onboardingskript oder andere Onboardingmethoden verwendet haben, die keine Intune-Profile verwenden, können Datenabweichungen auftreten. Um diese Abweichungen zu beheben, erstellen Sie ein entsprechendes Intune-Konfigurationsprofil für das Defender for Endpoint-Onboarding, und weisen Sie dieses Profil Ihren Geräten zu.

## <a name="onboard-more-devices-with-intune-profiles"></a>Onboarding von weiteren Geräten mit Intune-Profilen

Defender for Endpoint bietet verschiedene praktische Optionen für [das Onboarding Windows 10 Geräten.](onboard-configure.md) Für von Intune verwaltete Geräte können Sie jedoch Intune-Profile nutzen, um den Defender for Endpoint-Sensor bequem bereitzustellen, um Geräte auszuwählen und diese Geräte effektiv in den Dienst zu integrieren.

Wählen Sie **auf der Onboardingkarte** weitere Geräte **integrieren** aus, um ein Profil in Intune zu erstellen und zuzuordnen. Der Link führt Sie zur Seite "Gerätekonformität" auf Intune, die eine ähnliche Übersicht über Ihren Onboardingstatus bietet.

![Microsoft Defender for Endpoint Device Compliance-Seite zur Intune-Geräteverwaltung](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Microsoft Defender for Endpoint Device Compliance-Seite zur Intune-Geräteverwaltung*

>[!TIP]
>Alternativ können Sie im [Microsoft Azure-Portal](https://portal.azure.com/) über Alle Dienste > Intune > Device compliance > Microsoft Defender ATP zur Seite Defender for **Endpoint-Onboarding-Compliance navigieren.**

>[!NOTE]
> Wenn Sie die neuesten Gerätedaten anzeigen möchten, klicken Sie auf Liste der Geräte **ohne ATP-Sensor**.

Erstellen Sie auf der Seite Gerätekonformität ein Konfigurationsprofil speziell für die Bereitstellung des Defender for Endpoint-Sensors, und weisen Sie dieses Profil den Geräten zu, die Sie onboarden möchten. Dazu können Sie entweder:

- Wählen **Sie Erstellen eines Gerätekonfigurationsprofils aus, um den ATP-Sensor** so zu konfigurieren, dass er mit einem vordefinierten Gerätekonfigurationsprofil beginnt.
- Erstellen Sie das Gerätekonfigurationsprofil von Grund auf neu.

Weitere Informationen finden Sie [unter Verwenden von Intune-Gerätekonfigurationsprofilen zum Onboarding von Geräten in Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Verwandte Themen
- [Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind](configure-machines.md)
- [Erhöhen der Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint](configure-machines-security-baseline.md)
- [Optimieren der Bereitstellung und Erkennung von ASR-Regeln](configure-machines-asr.md)
