---
title: Microsoft Defender für Endpunkt auf Nicht-Windows-Plattformen
description: Erfahren Sie mehr über die Microsoft Defender für Endpunkt-Funktionen für Nicht-Windows-Plattformen
keywords: Nicht-Fenster, Mac, Macos, Linux, Android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4793f3c84ddda0db7f4d67ac96cb31a6e2108c57
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326999"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>Microsoft Defender für Endpunkt auf Nicht-Windows-Plattformen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft ist auf dem Weg, seine branchenführenden Endpunktsicherheitsfunktionen über Windows und Windows Server hinaus auf macOS, Linux, Android und iOS zu erweitern.

Organisationen sind mit Bedrohungen auf einer Vielzahl von Plattformen und Geräten konfrontiert. Unsere Teams haben sich verpflichtet, Sicherheitslösungen nicht nur *für* Microsoft, sondern auch *von* Microsoft zu entwickeln, damit unsere Kunden ihre heterogenen Umgebungen schützen und schützen können. Wir hören auf Kundenfeedback und arbeiten eng mit unseren Kunden zusammen, um Lösungen zu erstellen, die ihren Anforderungen entsprechen.

Mit Microsoft Defender für Endpunkt profitieren Kunden von einer einheitlichen Ansicht aller Bedrohungen und Warnungen in der Microsoft Defender Security Center, über Windows und Nicht-Windows-Plattformen hinweg, sodass sie ein vollständiges Bild der Vorgänge in ihrer Umgebung erhalten können, sodass sie Bedrohungen schneller bewerten und darauf reagieren können.

## <a name="microsoft-defender-for-endpoint-on-macos"></a>Microsoft Defender für Endpunkt unter Mac OS 

Microsoft Defender für Endpunkt unter macOS bietet Funktionen für Antivirus, EDR (EDR) und Sicherheitsrisikomanagement für die drei neuesten versionen von macOS. Kunden können die Lösung über Microsoft Endpoint Manager und Jamf bereitstellen und verwalten. Genau wie bei Microsoft Office-Anwendungen unter macOS wird Microsoft Auto Update zum Verwalten von Microsoft Defender für Endpunkt auf Mac-Updates verwendet. Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)

Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-mac.md)zu Defender für Endpunkt unter macOS.

>[!NOTE]
>Die folgenden Funktionen werden derzeit auf macOS-Endpunkten nicht unterstützt:
>- Verhinderung von Datenverlust
>- Live-Antwort
>- SIEM


## <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender für Endpunkt unter Linux

Microsoft Defender für Endpunkt unter Linux bietet Funktionen zur Verhinderung (AV), EDR (EDR) und Sicherheitsrisikomanagement für Linux-Server. Dies umfasst eine vollständige Befehlszeilenerfahrung zum Konfigurieren und Verwalten des Agents, zum Initiieren von Scans und zum Verwalten von Bedrohungen. Wir unterstützen aktuelle Versionen der sechs gängigsten Linux Server-Distributionen: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS oder höher LTS, SLES 12+, Git 9+ und Oracle Linux 7.2. Microsoft Defender für Endpunkt unter Linux kann mithilfe von "Aufrechte", "Ansible" oder mit ihrem vorhandenen Linux-Konfigurationsverwaltungstool bereitgestellt und konfiguriert werden. Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)

Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-linux.md)zu Microsoft Defender für Endpunkt unter Linux.

>[!NOTE]
>Die folgenden Funktionen werden derzeit auf Linux-Endpunkten nicht unterstützt:
>- Verhinderung von Datenverlust
>- Live-Antwort
>- SIEM



## <a name="microsoft-defender-for-endpoint-on-android"></a>Microsoft Defender für Endpunkt unter Android

Microsoft Defender für Endpunkt unter Android ist unsere Mobile Threat Defense-Lösung für Geräte mit Android 6.0 und höher. Sowohl der Modus "Android Enterprise " (Arbeitsprofil) als auch "Geräteadministrator" werden unterstützt. Unter Android bieten wir Webschutz, einschließlich Antiphishing, Blockieren unsicherer Verbindungen und Festlegen von benutzerdefinierten Indikatoren. Die Lösung sucht nach Schadsoftware und potenziell unerwünschten Anwendungen (PUA) und bietet zusätzliche Funktionen zur Verhinderung von Sicherheitsverletzungen durch Die Integration in Microsoft Endpoint Manager und bedingten Zugriff. Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)

Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-android.md)zu Microsoft Defender für Endpunkt unter Android.

## <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender für Endpunkt für iOS

Microsoft Defender für Endpunkt unter iOS ist unsere Mobile Threat Defense-Lösung für Geräte mit iOS 11.0 und höher. Überwachte und nicht überwachte Geräte werden unterstützt. Unter iOS bieten wir Webschutz, der Antiphishing, das Blockieren unsicherer Verbindungen und das Festlegen benutzerdefinierter Indikatoren umfasst. Weitere Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS) 

Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-ios.md)zu Microsoft Defender für Endpunkt unter iOS.

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen 

Berechtigte lizenzierte Benutzer können Microsoft Defender für Endpunkt auf bis zu fünf gleichzeitigen Geräten verwenden. Microsoft Defender für Endpunkt steht auch zum Kauf über einen Cloud Solution Provider (CSP) zur Verfügung.

Kunden können Microsoft Defender für Endpunkt unter macOS über eine eigenständige Microsoft Defender für Endpunkt-Lizenz als Teil von Microsoft 365 A5/E5 oder Microsoft 365 Security erwerben.

Kürzlich angekündigte Funktionen von Microsoft Defender für Endpunkt unter Android und iOS sind in den oben genannten Angeboten als Teil der fünf qualifizierten Geräte für berechtigte lizenzierte Benutzer enthalten.

Defender für Endpunkt unter Linux ist über die Defender für Endpoint Server-SKU verfügbar, die sowohl für kommerzielle Kunden als auch für Kunden im Bildungsbereich verfügbar ist.

Bitte wenden Sie sich an Ihr Kontoteam oder CSP, um Preise und zusätzliche Berechtigungsanforderungen zu erhalten.
