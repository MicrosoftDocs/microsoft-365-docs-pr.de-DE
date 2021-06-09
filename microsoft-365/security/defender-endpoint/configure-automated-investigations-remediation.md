---
title: Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen
description: Richten Sie Ihre Funktionen für automatisierte Untersuchungen und Korrekturen in Microsoft Defender für Endpunkt ein.
keywords: konfigurieren, einrichten, automatisiert, Untersuchung, Erkennung, Warnungen, Wartung, Reaktion
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
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841331"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Wenn Ihre Organisation [Microsoft Defender für Endpunkt](/windows/security/threat-protection/) (Defender für Endpunkt) verwendet, können automatisierte [Untersuchungs- und Korrekturfunktionen](/microsoft-365/security/defender-endpoint/automated-investigations) Ihrem Sicherheitsteam Zeit und Mühe sparen. Wie in [diesem Blogbeitrag](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)beschrieben, imitieren diese Funktionen die idealen Schritte, die ein Sicherheitsanalyst unternimmt, um Bedrohungen zu untersuchen und zu beheben. [Erfahren Sie mehr über die automatisierte Untersuchung und Behebung.](/microsoft-365/security/defender-endpoint/automated-investigations) 

So konfigurieren Sie automatisierte Untersuchungen und Korrekturen
1. [Aktivieren Sie die Features;](#turn-on-automated-investigation-and-remediation) Und 
2. [Richten Sie Gerätegruppen ein.](#set-up-device-groups)

## <a name="turn-on-automated-investigation-and-remediation"></a>Aktivieren der automatischen Untersuchung und Behebung

1. Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) und melden Sie sich an.
2. Wählen Sie im Navigationsbereich **Einstellungen** aus.
3. Wählen Sie im Abschnitt **"Allgemein"** die Option **"Erweiterte Features" aus.**
4. Aktivieren Sie sowohl **die automatische Untersuchung** als auch die automatische Auflösung von **Warnungen.**

## <a name="set-up-device-groups"></a>Gerätegruppen einrichten

1. Wählen Sie im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) auf der Seite **Einstellungen** unter **Berechtigungen** **Gerätegruppen** aus.
2. Wählen Sie **+ Gerätegruppe hinzufügen** aus.
3. Erstellen Sie mindestens eine Gerätegruppe wie folgt:
   - Geben Sie einen Namen und eine Beschreibung für die Gerätegruppe an.
   - Wählen Sie in der **Liste der Automatisierungsebenen** eine Ebene aus, z. B. **"Vollständig" – Bedrohungen automatisch beheben.** Die Automatisierungsstufe bestimmt, ob Korrekturmaßnahmen automatisch oder nur nach Genehmigung durchgeführt werden. Weitere Informationen finden Sie in den [Automatisierungsstufen der automatisierten Untersuchung und Behebung.](automation-levels.md)
   - Verwenden Sie im Abschnitt **"Mitglieder"** eine oder mehrere Bedingungen, um Geräte zu identifizieren und einzuschließen.
   - Wählen Sie auf der Registerkarte **"Benutzerzugriff"** die [Azure Active Directory Gruppen](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) aus, die Zugriff auf die Gerätegruppe haben sollen, die Sie erstellen.
4. Wählen Sie **"Fertig"** aus, wenn Sie die Einrichtung Ihrer Gerätegruppe abgeschlossen haben.

## <a name="next-steps"></a>Nächste Schritte

- [Besuchen Sie das Info-Center, um ausstehende und abgeschlossene Korrekturaktionen anzuzeigen.](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Überprüfen und Genehmigen ausstehender Aktionen](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Siehe auch

- [Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt](defender-endpoint-false-positives-negatives.md)
