---
title: Aktivieren des eingeschränkten regelmäßigen Microsoft Defender Antivirus-Überprüfungsfeatures
description: Mit eingeschränkter regelmäßiger Überprüfung können Sie Microsoft Defender Antivirus zusätzlich zu Ihren anderen installierten AV-Anbietern verwenden.
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 64b65363ff53773f73cbbdc33b05a0a1beaf7f92
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690601"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Verwenden begrenzter regelmäßiger Überprüfungen in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Begrenzte regelmäßige Überprüfungen sind eine spezielle Art von Bedrohungserkennung und -behebung, die aktiviert werden können, wenn Sie ein anderes Antivirenprodukt auf einem Windows 10-Gerät installiert haben.

Sie kann nur in bestimmten Situationen aktiviert werden. Weitere Informationen zur begrenzten regelmäßigen Überprüfung und zur Funktionsweise von Microsoft Defender Antivirus mit anderen Antivirenprodukten finden Sie unter [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).

**Microsoft empfiehlt die Verwendung dieses Features in Unternehmensumgebungen nicht. Dies ist ein Feature, das in erster Linie für Verbraucher vorgesehen ist.** Dieses Feature verwendet nur eine begrenzte Teilmenge der Microsoft Defender Antivirus-Funktionen zum Erkennen von Schadsoftware und kann die meisten Schadsoftware und potenziell unerwünschte Software nicht erkennen. Darüber hinaus sind die Verwaltungs- und Berichtsfunktionen eingeschränkt. Microsoft empfiehlt Unternehmen, ihre primäre Antivirenlösung zu wählen und sie exklusiv zu verwenden.

## <a name="how-to-enable-limited-periodic-scanning"></a>Aktivieren begrenzter regelmäßiger Überprüfungen

Microsoft Defender Antivirus aktiviert sich standardmäßig auf einem Windows 10-Gerät, wenn kein anderes Antivirenprodukt installiert ist oder das andere Produkt veraltet ist, abgelaufen ist oder nicht ordnungsgemäß funktioniert.

Wenn Microsoft Defender Antivirus aktiviert ist, werden die üblichen Optionen angezeigt, um es auf diesem Gerät zu konfigurieren:

![Windows-Sicherheits-App mit Microsoft Defender AV-Optionen, einschließlich Scanoptionen, Einstellungen und Updateoptionen](images/vtp-wdav.png)

Wenn ein anderes Antivirenprodukt installiert ist und ordnungsgemäß funktioniert, deaktiviert Microsoft Defender Antivirus sich selbst. Die Windows Security-App ändert den Abschnitt **Virenschutz &,** um den Status des AV-Produkts anzuzeigen, und stellt einen Link zu den Konfigurationsoptionen des Produkts zur Verfügung.

Unterhalb von AV-Produkten von Drittanbietern wird ein neuer Link als **Microsoft Defender Antivirus-Optionen angezeigt.** Wenn Sie auf diesen Link klicken, wird der Umschalter, der eine eingeschränkte regelmäßige Überprüfung ermöglicht, erweitert. Beachten Sie, dass die eingeschränkte periodische Option eine Umschalte ist, um die regelmäßige Überprüfung zu aktivieren oder zu deaktivieren. 

Wenn Sie den Schalter auf **Ein** verschieben, werden die standardmäßigen Microsoft Defender AV-Optionen unterhalb des Drittanbieter-AV-Produkts angezeigt. Die eingeschränkte regelmäßige Überprüfungsoption wird am unteren Rand der Seite angezeigt.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)