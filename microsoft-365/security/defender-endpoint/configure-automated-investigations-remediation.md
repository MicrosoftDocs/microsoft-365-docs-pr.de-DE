---
title: Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen
description: Richten Sie Ihre automatisierten Untersuchungs- und Korrekturfunktionen in Microsoft Defender for Endpoint ein.
keywords: konfigurieren, einrichten, automatisieren, Untersuchung, Erkennung, Warnungen, Korrektur, Antwort
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 23d6c8c87a6cbcc7b8060440ba2c0cae6182767d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274544"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Wenn Ihre Organisation Microsoft Defender for Endpoint (Defender for [Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/) [verwendet,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) können automatisierte Untersuchungs- und Korrekturfunktionen Ihrem Sicherheitsteam Zeit und Aufwand sparen. Wie in [diesem Blogbeitrag beschrieben,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)sind diese Funktionen die idealen Schritte, die ein Sicherheitsanalyst zur Untersuchung und Behebung von Bedrohungen unternimmt. [Erfahren Sie mehr über automatisierte Untersuchung und Behebung](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations). 

Zum Konfigurieren der automatisierten Untersuchung und Behebung
1. [Aktivieren Sie die Features](#turn-on-automated-investigation-and-remediation); und 
2. [Einrichten von Gerätegruppen](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Aktivieren der automatisierten Untersuchung und Korrektur

1. Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zum Microsoft Defender Security Center ( ) und [https://securitycenter.windows.com](https://securitycenter.windows.com) melden Sie sich an.
2. Wählen Sie im Navigationsbereich Einstellungen **aus.**
3. Wählen Sie **im Abschnitt Allgemein** die Option Erweiterte Features **aus.**
4. Aktivieren Sie sowohl **die automatische Untersuchung als** auch die automatische Behebung von **Warnungen.**

## <a name="set-up-device-groups"></a>Gerätegruppen einrichten

1. Wählen Sie im Microsoft Defender Security Center ( ) auf der Seite [https://securitycenter.windows.com](https://securitycenter.windows.com) **Einstellungen** unter **Berechtigungen** **Gerätegruppen aus.**
2. Wählen **Sie + Gerätegruppe hinzufügen aus.**
3. Erstellen Sie mindestens eine Gerätegruppe wie folgt:
   - Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.
   - Wählen Sie **in der Liste** Automatisierungsebene eine Ebene aus, z. B. Vollständig – Bedrohungen automatisch **entfernen.** Die Automatisierungsebene bestimmt, ob Korrekturaktionen automatisch oder nur nach Genehmigung ausgeführt werden. Weitere Informationen finden Sie unter [Automatisierungsebenen in automatisierter Untersuchung und Korrektur](automation-levels.md).
   - Verwenden Sie **im Abschnitt** Mitglieder eine oder mehrere Bedingungen zum Identifizieren und Schließen von Geräten.
   - Wählen Sie **auf der Registerkarte** Benutzerzugriff die Azure Active [Directory-Gruppen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) aus, die Zugriff auf die zu erstellende Gerätegruppe haben sollen.
4. Wählen **Sie Fertig** aus, wenn Sie die Einrichtung Ihrer Gerätegruppe abgeschlossen haben.

## <a name="next-steps"></a>Nächste Schritte

- [Besuchen Sie das Aktionscenter, um ausstehende und abgeschlossene Korrekturaktionen zu sehen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Überprüfen und Genehmigen ausstehender Aktionen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Siehe auch

- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
