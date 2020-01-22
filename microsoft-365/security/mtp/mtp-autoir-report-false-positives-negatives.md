---
title: Vorgehensweise Melden von falsch positiven oder falschen negativen Daten in Air in Microsoft Threat Protection
description: Wurde in Microsoft Threat Protection etwas übersehen oder fälschlicherweise von Air erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslöser, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260193"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Vorgehensweise Melden von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Haben [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) im Microsoft Threat Protection-Vorgang fehl am oder falsch erkannt? Sie können diesen Bericht an Microsoft melden oder Ihre Benachrichtigungen anpassen (falls erforderlich). Verwenden Sie die folgende Tabelle als Leitfaden: 


|Element  |Erkannt von  |Vorgehensweise melden  |
|---------|---------|---------|
|E-Mail <br/>E-Mail-Anlage <br/>URL in einer e-Mail-Nachricht oder Office-Datei      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft für Office 365-Scans](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Datei oder App auf einem Gerät    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[Übermitteln einer Datei an Microsoft zur Analyse von Schadsoftware](https://www.microsoft.com/wdsi/filesubmission)         |
|Warnung durch legitime Verwendung ausgelöst <br/>Falsche Warnung    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> oder <br/>[Erkennung erweiterter Azure-Bedrohungen](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Verwalten von Benachrichtigungen im Cloud-App-Sicherheitsportal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a>Nächste Schritte

- [Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion](mtp-autoir-actions.md)
- [Erfahren Sie mehr über das Info-Center](mtp-action-center.md)
- [Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection](advanced-hunting-overview.md)
