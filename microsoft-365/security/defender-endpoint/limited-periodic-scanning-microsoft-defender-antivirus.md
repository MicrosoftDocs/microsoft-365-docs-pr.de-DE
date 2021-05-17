---
title: Aktivieren der eingeschränkten Microsoft Defender Antivirus Überprüfungsfunktion
description: Mit eingeschränkter regelmäßiger Überprüfung können Sie Microsoft Defender Antivirus zusätzlich zu Ihren anderen installierten AV-Anbietern verwenden.
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274593"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Verwendung von eingeschränkten periodischen Scans in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Bei der begrenzten regelmäßigen Überprüfung handelt es sich um eine spezielle Art von Bedrohungserkennung und -behebung, die aktiviert werden kann, wenn Sie ein anderes Antivirenprodukt auf einem Windows 10 haben.

Sie kann nur in bestimmten Situationen aktiviert werden. Weitere Informationen zur eingeschränkten regelmäßigen Überprüfung und zur Microsoft Defender Antivirus verwendung mit anderen Antivirenprodukten finden Sie [unter Microsoft Defender Antivirus Kompatibilität](microsoft-defender-antivirus-compatibility.md).

**Microsoft empfiehlt die Verwendung dieses Features in Unternehmensumgebungen nicht. Dies ist ein Feature, das in erster Linie für Verbraucher vorgesehen ist.** Dieses Feature verwendet nur eine begrenzte Teilmenge der Microsoft Defender Antivirus, um Schadsoftware zu erkennen, und kann die meisten Schadsoftware und potenziell unerwünschte Software nicht erkennen. Darüber hinaus sind die Verwaltungs- und Berichtsfunktionen eingeschränkt. Microsoft empfiehlt Unternehmen, ihre primäre Antivirenlösung zu wählen und sie exklusiv zu verwenden.

## <a name="how-to-enable-limited-periodic-scanning"></a>Aktivieren begrenzter regelmäßiger Überprüfungen

Standardmäßig aktiviert Microsoft Defender Antivirus sich selbst auf einem Windows 10-Gerät, wenn kein anderes Antivirenprodukt installiert ist oder das andere Produkt veraltet, abgelaufen oder nicht ordnungsgemäß funktioniert.

Wenn Microsoft Defender Antivirus aktiviert ist, werden die üblichen Optionen angezeigt, um sie auf diesem Gerät zu konfigurieren:

![Windows-Sicherheit-App mit Microsoft Defender AV-Optionen, einschließlich Scanoptionen, Einstellungen und Updateoptionen](images/vtp-wdav.png)

Wenn ein anderes Antivirenprodukt installiert ist und ordnungsgemäß funktioniert, Microsoft Defender Antivirus selbst deaktiviert. Die Windows-Sicherheit-App ändert den Abschnitt **Virenschutz &,** um den Status des AV-Produkts anzuzeigen, und stellt einen Link zu den Konfigurationsoptionen des Produkts zur Verfügung.

Unterhalb von AV-Produkten von Drittanbietern wird ein neuer Link als Microsoft Defender Antivirus **angezeigt.** Wenn Sie auf diesen Link klicken, wird der Umschalter, der eine eingeschränkte regelmäßige Überprüfung ermöglicht, erweitert. Beachten Sie, dass die eingeschränkte periodische Option eine Umschalte ist, um die regelmäßige Überprüfung zu aktivieren oder zu deaktivieren. 

Wenn Sie den Schalter auf **Ein** verschieben, werden die standardmäßigen Microsoft Defender AV-Optionen unterhalb des Drittanbieter-AV-Produkts angezeigt. Die eingeschränkte regelmäßige Überprüfungsoption wird am unteren Rand der Seite angezeigt.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)