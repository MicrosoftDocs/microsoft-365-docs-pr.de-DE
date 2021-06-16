---
title: Aktivieren der eingeschränkten regelmäßigen Microsoft Defender Antivirus-Überprüfungsfunktion
description: Mit der eingeschränkten regelmäßigen Überprüfung können Sie zusätzlich zu Ihren anderen installierten AV-Anbietern Microsoft Defender Antivirus verwenden.
keywords: lps, limited, periodic, scan, scan, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad49b08e687f4ba389616542bd607d4140e91132
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926691"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Verwendung von eingeschränkten periodischen Scans in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Die eingeschränkte regelmäßige Überprüfung ist eine spezielle Art der Bedrohungserkennung und -behebung, die aktiviert werden kann, wenn Sie ein anderes Antivirenprodukt auf einem Windows 10 Gerät installiert haben.

Sie kann nur in bestimmten Situationen aktiviert werden. Weitere Informationen zur eingeschränkten regelmäßigen Überprüfung und zur Funktionsweise Microsoft Defender Antivirus mit anderen Antivirenprodukten finden Sie unter [Microsoft Defender Antivirus Kompatibilität.](microsoft-defender-antivirus-compatibility.md)

**Microsoft empfiehlt nicht die Verwendung dieses Features in Unternehmensumgebungen. Dies ist ein Feature, das in erster Linie für Verbraucher vorgesehen ist.** Dieses Feature verwendet nur eine begrenzte Teilmenge der Microsoft Defender Antivirus Funktionen, um Schadsoftware zu erkennen, und kann nicht die meisten Schadsoftware und potenziell unerwünschte Software erkennen. Außerdem sind die Verwaltungs- und Berichtsfunktionen eingeschränkt. Microsoft empfiehlt Unternehmen, ihre primäre Antivirenlösung auszuwählen und ausschließlich zu verwenden.

## <a name="how-to-enable-limited-periodic-scanning"></a>Aktivieren der eingeschränkten regelmäßigen Überprüfung

Standardmäßig aktiviert sich Microsoft Defender Antivirus auf einem Windows 10 Gerät, wenn kein anderes Antivirenprodukt installiert ist oder wenn das andere Produkt veraltet, abgelaufen oder nicht ordnungsgemäß funktioniert.

Wenn Microsoft Defender Antivirus aktiviert ist, werden die üblichen Optionen angezeigt, um es auf diesem Gerät zu konfigurieren:

![Windows-Sicherheit-App mit Microsoft Defender AV-Optionen, einschließlich Scanoptionen, Einstellungen und Updateoptionen](images/vtp-wdav.png)

Wenn ein anderes Antivirenprodukt installiert ist und ordnungsgemäß funktioniert, deaktiviert Microsoft Defender Antivirus sich selbst. The Windows-Sicherheit app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.

Unter allen AV-Produkten von Drittanbietern wird ein neuer Link als **Microsoft Defender Antivirus Optionen** angezeigt. Durch Klicken auf diesen Link wird die Umschaltfläche angezeigt, die eine eingeschränkte regelmäßige Überprüfung ermöglicht. Beachten Sie, dass die eingeschränkte regelmäßige Option eine Umschaltfläche zum Aktivieren oder Deaktivieren der regelmäßigen Überprüfung ist. 

Wenn Sie den Schalter auf **"Ein"** setzen, werden die standardmäßigen Microsoft Defender AV-Optionen unter dem AV-Produkt des Drittanbieters angezeigt. Die eingeschränkte regelmäßige Überprüfungsoption wird am unteren Rand der Seite angezeigt.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)