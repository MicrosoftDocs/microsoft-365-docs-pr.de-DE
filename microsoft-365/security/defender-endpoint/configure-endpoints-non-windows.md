---
title: Onboarding von Nicht-Windows-Geräten in den Microsoft Defender for Endpoint-Dienst
description: Konfigurieren Sie Nicht-Windows-Geräte so, dass sie Sensordaten an den Microsoft Defender ATP-Dienst senden können.
keywords: Onboarding von Nicht-Windows-Geräten, Macos, Linux, Geräteverwaltung, Konfigurieren von Windows ATP-Geräten, Konfigurieren von Microsoft Defender for Endpoint-Geräten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71f230f557792d75659dc4dbfc5911811514d5ea
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687877"
---
# <a name="onboard-non-windows-devices"></a>Onboarding von Nicht-Windows-Geräten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformen**
- macOS
- Linux

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender for Endpoint bietet eine zentrale Sicherheitsbetriebserfahrung für Windows- und Nicht-Windows-Plattformen. Sie können Warnungen von verschiedenen unterstützten Betriebssystemen im Microsoft Defender Security Center anzeigen und das Netzwerk Ihrer Organisation besser schützen. 

Sie müssen die genauen Linux-Distros- und macOS-Versionen kennen, die mit Defender for Endpoint kompatibel sind, damit die Integration funktioniert. Weitere Informationen finden Sie unter:
- [Systemanforderungen für Microsoft Defender for Endpoint unter Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Microsoft Defender for Endpoint für macOS-Systemanforderungen](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Onboarding von Nicht-Windows-Geräten
Sie müssen die folgenden Schritte zum Onboarding von Nicht-Windows-Geräten ausführen:
1. Wählen Sie Ihre bevorzugte Methode für das Onboarding aus:

   - Für macOS-Geräte können Sie das Onboarding über Microsoft Defender ATP oder über eine Drittanbieterlösung auswählen. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint für Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).

   - Für andere Nicht-Windows-Geräte wählen **Sie Onboard non-Windows devices through third-party integration aus.**   
    1. Wählen Sie im Navigationsbereich  >  **Interoperabilitätspartner aus.** Stellen Sie sicher, dass die Drittanbieterlösung aufgeführt ist.
    2. Wählen Sie **auf der Registerkarte** Partneranwendungen den Partner aus, der Ihre Nicht-Windows-Geräte unterstützt.
    3. Wählen **Sie Partnerseite öffnen aus,** um die Seite des Partners zu öffnen. Befolgen Sie die Anweisungen auf der Seite.
    4. Nach dem Erstellen eines Kontos oder dem Abonnieren der Partnerlösung sollten Sie zu einer Phase kommen, in der ein globaler Mandantenadministrator in Ihrer Organisation aufgefordert wird, eine Berechtigungsanforderung von der Partneranwendung zu akzeptieren. Lesen Sie die Berechtigungsanforderung sorgfältig durch, um sicherzustellen, dass sie mit dem von Ihnen benötigten Dienst abgestimmt ist. 

        
2. Führen Sie einen Erkennungstest aus, indem Sie die Anweisungen der Drittanbieterlösung befolgen.

## <a name="offboard-non-windows-devices"></a>Offboard-Nicht-Windows-Geräte

1. Befolgen Sie die Dokumentation des Drittanbieters, um die Drittanbieterlösung von Microsoft Defender for Endpoint zu trennen.

2. Entfernen Von Berechtigungen für die Drittanbieterlösung in Ihrem Azure AD-Mandanten.
   1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
   2. Wählen **Sie Azure Active Directory > Enterprise Applications aus.**
   3. Wählen Sie die Anwendung aus, die Sie offboarden möchten.
   4. Wählen Sie die **Schaltfläche Löschen** aus.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Onboarding von Servern](configure-server-endpoints.md)
- [Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor](configure-proxy-internet.md)
- [Beheben von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
