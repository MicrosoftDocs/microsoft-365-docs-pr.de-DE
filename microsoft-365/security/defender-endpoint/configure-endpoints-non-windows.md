---
title: Integrieren von Nicht-Windows-Geräten in den Microsoft Defender für Endpunktdienst
description: Konfigurieren Sie nicht Windows Geräte, sodass sie Sensordaten an den Microsoft Defender für Endpunktdienst senden können.
keywords: Onboarding von Nicht-Windows-Geräten, Macos, Linux, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte
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
ms.openlocfilehash: 777f5f63c4739f277ec24f826bc8a61a226fb65f
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339670"
---
# <a name="onboard-non-windows-devices"></a>Onboarding von Nicht-Windows-Geräten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformen**
- macOS
- Linux

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender für Endpunkt bietet eine zentrale Sicherheitsumgebung für Windows und Plattformen, die nicht Windows sind. Sie können Warnungen von verschiedenen unterstützten Betriebssystemen in Microsoft 365 Defender sehen und das Netzwerk Ihrer Organisation besser schützen. 

Sie müssen die genauen Linux-Distributionen und macOS-Versionen kennen, die mit Defender für Endpunkt kompatibel sind, damit die Integration funktioniert. Weitere Informationen finden Sie unter:
- [Systemanforderungen für Microsoft Defender für Endpunkt unter Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Systemanforderungen für Microsoft Defender für Endpunkt unter macOS.](microsoft-defender-endpoint-mac.md#system-requirements)

## <a name="onboarding-non-windows-devices"></a>Onboarding von Nicht-Windows-Geräten
Sie müssen die folgenden Schritte ausführen, um Nicht-Windows-Geräte zu integrieren:
1. Wählen Sie Ihre bevorzugte Onboardingmethode aus:

   - Für macOS-Geräte können Sie sich für das Onboarding über Microsoft Defender für Endpunkt oder eine Drittanbieterlösung entscheiden. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt auf dem Mac.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - Wählen Sie für andere Nicht-Windows-Geräte die Option **"Onboarding nicht Windows Geräte durch Drittanbieterintegration"** aus.   
    1. Wählen Sie im Navigationsbereich **Interoperabilitätspartner**  >  aus. Stellen Sie sicher, dass die Drittanbieterlösung aufgeführt ist.
    2. Wählen Sie auf der Registerkarte **"Partneranwendungen"** den Partner aus, der Ihre nicht Windows Geräte unterstützt.
    3. Wählen Sie **"Partner öffnen" aus,** um die Seite des Partners zu öffnen. Folgen Sie den Anweisungen auf der Seite.
    4. Nachdem Sie ein Konto erstellt oder die Partnerlösung abonniert haben, sollten Sie zu einer Phase gelangen, in der ein globaler Mandantenadministrator in Ihrer Organisation aufgefordert wird, eine Berechtigungsanforderung von der Partneranwendung zu akzeptieren. Lesen Sie die Berechtigungsanforderung sorgfältig durch, um sicherzustellen, dass sie dem von Ihnen benötigten Dienst entspricht. 

        
2. Führen Sie einen Erkennungstest aus, indem Sie den Anweisungen der Drittanbieterlösung folgen.

## <a name="offboard-non-windows-devices"></a>Offboarding von Nicht-Windows-Geräten

1. Folgen Sie der Dokumentation des Drittanbieters, um die Verbindung zwischen der Drittanbieterlösung und Microsoft Defender für Endpunkt zu trennen.

2. Entfernen Sie Berechtigungen für die Drittanbieterlösung in Ihrem Azure AD-Mandanten.
   1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
   2. Wählen Sie **Azure Active Directory > Enterprise Anwendungen** aus.
   3. Wählen Sie die Anwendung aus, die Sie offboarden möchten.
   4. Wählen Sie die Schaltfläche **"Löschen"** aus.


## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Onboarding von Servern](configure-server-endpoints.md)
- [Konfigurieren der Einstellungen für Endpunktproxy und Internetkonnektivität für Ihren Azure ATP-Sensor](configure-proxy-internet.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
