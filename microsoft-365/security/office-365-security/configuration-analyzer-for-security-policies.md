---
title: Konfigurationsanalyse für Sicherheitsrichtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Konfigurationsanalyse verwenden, um Sicherheitsrichtlinien zu finden und zu beheben, die sich unter den voreingestellten Sicherheitsrichtlinien "Standardschutz" und "Strenger Schutz" befinden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01a9b3a2b01a3cfc95a3911f75907cbe0ef9d58f
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108427"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Konfigurationsanalyse für Schutzrichtlinien in EOP und Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Configuration Analyzer im Microsoft 365 Defender-Portal bietet einen zentralen Ort zum Suchen und Beheben von Sicherheitsrichtlinien, in denen sich die Einstellungen unter den Standardschutz- und Strict Protection-Profileinstellungen in [vordefinierten Sicherheitsrichtlinien befinden.](preset-security-policies.md)

Die folgenden Richtlinientypen werden vom Konfigurationsanalyseprogramm analysiert:

- **Exchange Online Protection (EOP)-Richtlinien:** Dazu gehören Microsoft 365 Organisationen mit Exchange Online Postfächern und eigenständige EOP-Organisationen ohne Exchange Online Postfächer:

  - [Antispamrichtlinien](configure-your-spam-filter-policies.md).
  - [Antischadsoftwarerichtlinien](configure-anti-malware-policies.md).
  - [EOP-Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).

- **Microsoft Defender für Office 365-Richtlinien:** Dies umfasst Organisationen mit Microsoft 365 E5 oder Defender für Office 365-Add-On-Abonnements:

  - Antiphishingrichtlinien in Microsoft Defender für Office 365, die Folgendes umfassen:
    - Die gleichen [Spoofingeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Antiphishingrichtlinien verfügbar sind.
    - [Identitätswechseleinstellungen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Erweiterte Phishing-Schwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Tresor Verknüpfungsrichtlinien](set-up-safe-links-policies.md).
  - [Tresor Anlagenrichtlinien.](set-up-safe-attachments-policies.md)

Die Standard- und **Strict-Richtlinieneinstellungswerte,** die als Basislinien verwendet werden, werden in [den empfohlenen Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365.md)beschrieben. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Microsoft 365 Defender Portal Berechtigungen zugewiesen werden:
  - Um die Konfigurationsanalyse zu verwenden **und** Aktualisierungen an Sicherheitsrichtlinien vorzunehmen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >  
  > - Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a>Verwenden der Konfigurationsanalyse im Microsoft 365 Defender-Portal

Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail-&** \> **Zusammenarbeitsrichtlinien &** Seite "Richtlinien \> **für Bedrohungsregeln"** im Abschnitt \> "Konfigurationsanalyse" mit **Vorlagenrichtlinien.** \> 

Die **Seite "Konfigurationsanalyse"** verfügt über zwei Hauptregisterkarten:

- **Einstellungen und Empfehlungen:** Wählen Sie **"Standard"** oder **"Streng"** aus, und vergleichen Sie diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien. In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um sie auf die gleiche Ebene wie Standard oder Strict zu bringen.
- Analyse und Verlauf der **Konfigurationsabweichung:** Mit dieser Ansicht können Sie Richtlinienänderungen im Laufe der Zeit nachverfolgen.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Registerkarte "Einstellungen und Empfehlungen" in der Konfigurationsanalyse

Standardmäßig wird die Registerkarte für den Vergleich mit dem Standardschutzprofil geöffnet. Sie können zum Vergleich des Streng-Schutzprofils wechseln, indem Sie die **Empfehlungen "Streng anzeigen"** auswählen. Um zurück zu wechseln, wählen Sie **"Standardempfehlungen anzeigen" aus.**

![Einstellungen- und Empfehlungenansicht im Configuration Analyzer](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Standardmäßig enthält die Spalte **"Richtliniengruppe/Einstellungsname"** eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und der Anzahl der Einstellungen, die verbessert werden müssen (sofern vorhanden). Die Arten von Richtlinien sind:

- **Antispam**
- **Antiphishing**
- **Antischadsoftware**
- **Tresor Anlagen** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)
- **Tresor Links** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)

In der Standardansicht ist alles reduziert. Neben jeder Richtlinie gibt es eine Zusammenfassung der Vergleichsergebnisse aus Ihren Richtlinien (die Sie ändern können) und den Einstellungen in den entsprechenden Richtlinien für die Standard- oder Strict-Schutzprofile (die Sie nicht ändern können). Sie sehen die folgenden Informationen für das Schutzprofil, mit dem Sie vergleichen:

- **Grün:** Alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil.
- **Gelb:** Eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.
- **Rot:** Eine erhebliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil. Dies können einige Einstellungen in vielen Richtlinien oder viele Einstellungen in einer Richtlinie sein.

Für vergleiche werden Sie den Text sehen: **Alle Einstellungen folgen** \<**Standard** or **Strict**\> **Empfehlungen.** Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die Sie ändern müssen.

Wenn Sie den **Richtliniengruppen-/Einstellungsnamen** erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder bestimmten Richtlinie, die Aufmerksamkeit erfordern, offengelegt. Sie können auch einen bestimmten Richtlinientyp (z. B. **Antispam)** erweitern, um nur die Einstellungen in den Richtlinientypen anzuzeigen, die Ihre Aufmerksamkeit erfordern.

Wenn der Vergleich keine Verbesserungsempfehlungen enthält (grün), wird beim Erweitern der Richtlinie nichts angezeigt. Wenn es eine Reihe von Verbesserungsempfehlungen gibt (gelb oder rot), werden die Einstellungen, die Aufmerksamkeit erfordern, angezeigt, und entsprechende Informationen werden in den folgenden Spalten angezeigt:

- **Richtliniengruppe/Einstellungsname:** Der Name der Einstellung, der Ihre Aufmerksamkeit erfordert. Im vorherigen Screenshot sind dies beispielsweise die Einstellungen in der Standardmäßigen Antispamrichtlinie.
- **Richtlinie:** Der Name der betroffenen Richtlinie, die die Einstellung enthält.
- **Angewendet auf**: Die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet werden.
- **Aktuelle Konfiguration:** Der aktuelle Wert der Einstellung. Für die Standardrichtlinie dieses Typs, die für alle Empfänger gilt, ist dieser Wert leer.
- **Zuletzt geändert:** Das Datum, an dem die Richtlinie zuletzt geändert wurde.
- **Empfehlungen:** Der Wert der Einstellung im Standard- oder Strict-Schutzprofil. Klicken Sie auf **"Übernehmen",** um den Wert der Einstellung in Ihrer Richtlinie so zu ändern, dass er dem empfohlenen Wert im Schutzprofil entspricht. Wenn die Änderung erfolgreich ist, wird die Meldung angezeigt: **Empfehlungen erfolgreich übernommen.** Klicken Sie auf **"Aktualisieren",** um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellungs-/Richtlinienzeile aus den Ergebnissen anzuzeigen.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Registerkarte "Analyse und Verlauf der Konfiguration" in der Konfigurationsanalyse

Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben. Standardmäßig werden die folgenden Informationen angezeigt:

- **Zuletzt geändert**
- **Geändert von**
- **Einstellungsname**
- **Richtlinie**
- **Typ**
- **Konfigurationsänderung**
- **Konfigurationsabweichung:** Der Wert **"Erhöhen"** oder **"Verkleinern".**

Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Im  angezeigten Filter-Flyout können Sie aus den folgenden Filtern auswählen:

- **Startzeit** und **Endzeit** (Datum)
- **Standardschutz** oder **strenger Schutz**

Klicken Sie auf **"Exportieren",** um die Ergebnisse in eine .csv Datei zu exportieren.

![Konfigurations-Abweichungsanalyse und Verlaufsansicht im Configuration Analyzer](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
