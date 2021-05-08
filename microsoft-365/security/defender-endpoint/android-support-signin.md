---
title: Behandeln von Problemen mit Microsoft Defender for Endpoint unter Android
description: Behandeln von Problemen für Microsoft Defender for Endpoint unter Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connectivity, communication
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246356"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Problembehandlung bei Microsoft Defender for Endpoint unter Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Beim Onboarding eines Geräts werden möglicherweise Anmeldeprobleme angezeigt, nachdem die App installiert wurde.

Während des Onboardings können Anmeldeprobleme auftreten, nachdem die App auf Ihrem Gerät installiert wurde.

Dieser Artikel enthält Lösungen zur Lösung der Anmeldeprobleme.  

## <a name="sign-in-failed---unexpected-error"></a>Anmeldung fehlgeschlagen – unerwarteter Fehler
**Anmeldefehler: Unerwarteter** *Fehler, versuchen Sie es später*

![Image of sign in failed error Unerwarteter Fehler](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Nachricht:**

Unerwarteter Fehler, versuchen Sie es später

**Ursache:**

Sie haben eine ältere Version von "Microsoft Authenticator"-App auf Ihrem Gerät installiert.

**Lösung:**

Installieren Sie die neueste Version [und Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) von Google Play Store und versuchen Sie es erneut.

## <a name="sign-in-failed---invalid-license"></a>Anmelden fehlgeschlagen – ungültige Lizenz

**Fehlgeschlagene Anmeldung:** *Ungültige Lizenz, wenden Sie sich an den Administrator*

![Image of sign in failed please contact administrator](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Nachricht:** *Ungültige Lizenz, wenden Sie sich an den Administrator.*

**Ursache:**

Ihnen ist keine Microsoft 365 zugewiesen, oder Ihre Organisation verfügt nicht über eine Lizenz für Microsoft 365 Enterprise Abonnement.

**Lösung:**

Weitere Informationen erhalten Sie von Ihrem Administrator.

## <a name="report-unsafe-site"></a>Unsichere Website melden

Phishingwebsites geben sich als vertrauenswürdige Websites aus, um Ihre persönlichen oder finanziellen Informationen zu erhalten. Besuchen Sie [die Seite Feedback zum Netzwerkschutz](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) bereitstellen, wenn Sie eine Website melden möchten, bei der es sich um eine Phishingwebsite handelt.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Phishingseiten werden auf einigen OEM-Geräten nicht blockiert

**Gilt für:** Nur bestimmte OEMs

-   **Xiaomi**

Phishing und schädliche Webbedrohungen, die von Defender for Endpoint für Android erkannt werden, werden auf einigen Xiaomi-Geräten nicht blockiert. Die folgenden Funktionen funktionieren auf diesen Geräten nicht.

![Abbildung der als unsicher gemeldeten Website](images/0c04975c74746a5cdb085e1d9386e713.png)


**Ursache:**

Die Geräte von Xiaomi enthalten ein neues Berechtigungsmodell. Dadurch wird verhindert, dass Defender for Endpoint für Android Popupfenster angezeigt wird, während es im Hintergrund ausgeführt wird.

Berechtigung für Die Geräte von Xiaomi: "Popupfenster anzeigen, während sie im Hintergrund ausgeführt werden."

![Abbildung der Popupeinstellung](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Lösung:**

Aktivieren Sie die erforderliche Berechtigung auf Xiaomi-Geräten.

- Anzeigen von Popupfenstern während der Ausführung im Hintergrund.
