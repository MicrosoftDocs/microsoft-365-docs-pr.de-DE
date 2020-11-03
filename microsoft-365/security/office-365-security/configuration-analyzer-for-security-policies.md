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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie mithilfe der Konfigurationsanalyse Sicherheitsrichtlinien finden und beheben können, die unter den vordefinierten Sicherheitsrichtlinien für Standard Schutz und strenge Schutzbedingungen liegen.
ms.openlocfilehash: 1429bddc5ae5f8409ad4f3593f7ea236b13f854c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846472"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Konfigurationsanalyse für Schutzrichtlinien in EoP und Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, sind nicht in allen Organisationen verfügbar und können geändert werden. Weitere Informationen zum Veröffentlichungszeitplan finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).

Configuration Analyzer im Security & Compliance Center bietet einen zentralen Standort, um Sicherheitsrichtlinien zu finden und zu beheben, bei denen die Einstellungen unter den Standard mäßigen Schutz-und strengen Schutzprofil Einstellungen in [vordefinierten Sicherheitsrichtlinien](preset-security-policies.md)liegen.

Die folgenden Richtlinientypen werden vom Configuration Analyzer analysiert:

- **Exchange Online Protection (EoP)-Richtlinien** : Dies umfasst Microsoft 365-Organisationen mit Exchange Online Postfächern und eigenständigen EoP-Organisationen ohne Exchange Online Postfächern:
  
  - [Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).
  - [Anti-Malware-Richtlinien](configure-anti-malware-policies.md).
  - [EoP-Anti-Phishing-Richtlinien](set-up-anti-phishing-policies.md#spoof-settings).

- **Microsoft Defender für Office 365-Richtlinien** : Dies umfasst Organisationen mit Microsoft 365 E5 oder Defender für Office 365 Add-on-Abonnements:

  - Anti-Phishing-Richtlinien in Microsoft Defender für Office 365, die Folgendes umfassen:

    - Dieselben [spoofeinstellungen](set-up-anti-phishing-policies.md#spoof-settings) , die in den EoP-Richtlinien zum Schutz vor Phishing verfügbar sind.
    - [Einstellungen für Identitätswechsel](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Erweiterte Phishing-Schwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md).

  - [Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md).

Die **Standard mäßigen** und **strengen** Richtlinien Einstellungswerte, die als Baselines verwendet werden, werden in den [empfohlenen Einstellungen für EoP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365-atp.md)beschrieben.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Configuration Analyzer** wechseln möchten, verwenden Sie <https://protection.office.com/configurationAnalyzer> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Artikel ausführen können:

  - Sie müssen Mitglied einer der folgenden Rollengruppen sein, um die Konfigurationsanalyse verwenden **und** Updates für Sicherheitsrichtlinien vornehmen zu können:

    - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Verwenden des Configuration Analyzer im Security & Compliance Center

Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Configuration Analyzer**.

![Configuration Analyzer-Widget auf der Seite "Threat Management- \> Richtlinie"](../../media/configuration-analyzer-widget.png)

Die Konfigurationsanalyse verfügt über zwei Hauptregisterkarten:

- **Einstellungen und Empfehlungen** : Sie wählen Standard oder Strict aus und vergleichen diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien. In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um Sie auf die gleiche Stufe wie Standard oder Strict zu bringen.

- **Analyse und Verlauf der Konfigurations Drift** : in dieser Ansicht können Sie Richtlinienänderungen im Laufe der Zeit verfolgen.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Registerkarte Einstellungen und Empfehlungen in der Konfigurationsanalyse

Standardmäßig wird die Registerkarte im Vergleich zum Standard Schutzprofil geöffnet. Sie können zum Vergleich des strengen Schutz Profils wechseln, indem Sie auf **strenge Empfehlungen anzeigen** klicken. Um zurück zu wechseln, wählen Sie **Standard Empfehlungen anzeigen** aus.

![Ansicht "Einstellungen und Empfehlungen" in der Konfigurationsanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Standardmäßig enthält die Spalte **Richtliniengruppen/Einstellungsname** eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und der Anzahl von Einstellungen, die verbessert werden müssen (sofern vorhanden). Die Typen von Richtlinien lauten wie folgt:

- **Anti-Spam**
- **Anti-Phishing**
- **Anti-Malware**
- **ATP-sichere Anlagen** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)
- **ATP-sichere Links** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)

In der Standardansicht wird alles reduziert. Neben den einzelnen Richtlinien gibt es eine Zusammenfassung der Vergleichsergebnisse aus ihren Richtlinien (die Sie ändern können) und die Einstellungen in den entsprechenden Richtlinien für die Standard mäßigen oder strengen Schutzprofile (die Sie nicht ändern können). Die folgenden Informationen für das Schutzprofil, mit dem Sie verglichen werden, werden angezeigt:

- **Grün** : alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil.
- **Amber** : eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.
- **Rot** : eine beträchtliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil. Dabei kann es sich um einige Einstellungen in vielen Richtlinien oder um viele Einstellungen in einer Richtlinie handeln.

Für günstige Vergleiche wird der Text angezeigt: **alle Einstellungen folgen** den \<**Standard** or **Strict**\> **Empfehlungen**. Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die geändert werden sollten.

Wenn Sie den **Namen der Richtliniengruppe/Einstellung** erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder spezifischen Richtlinie, die Aufmerksamkeit erfordern, aufgedeckt. Sie können auch einen bestimmten Richtlinientyp erweitern (beispielsweise **Anti-Spam** ), um nur die Einstellungen in diesen Richtlinientypen anzuzeigen, die Ihre Aufmerksamkeit erfordern.

Wenn der Vergleich keine Empfehlungen für Verbesserungen (grün) hat, zeigt das Erweitern der Richtlinie nichts. Wenn es eine Reihe von Verbesserungsempfehlungen gibt (Amber oder rot), werden die Einstellungen, die Aufmerksamkeit erfordern, aufgedeckt, und entsprechende Informationen werden in den folgenden Spalten angezeigt:

- Der Name der Einstellung, die Ihre Aufmerksamkeit erfordert. Im vorherigen Screenshot ist dies beispielsweise der **Schwellenwert für Massen-e-Mails** in einer Anti-Spam-Richtlinie.

- **Richtlinie** : der Name der betroffenen Richtlinie, die die Einstellung enthält.

- **Angewendet auf** : die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet wurden.

- **Aktuelle Konfiguration** : der aktuelle Wert der Einstellung.

- **Zuletzt geändert** : das Datum, an dem die Richtlinie zuletzt geändert wurde.

- **Empfehlungen** : der Wert der Einstellung im Standard mäßigen oder strengen Schutzprofil. Klicken Sie auf über **nehmen** , um den Wert der Einstellung in Ihrer Richtlinie so zu ändern, dass er dem empfohlenen Wert im Schutzprofil entspricht. Wenn die Änderung erfolgreich war, wird die Meldung angezeigt: **Empfehlungen wurden erfolgreich angenommen**. Klicken Sie auf **Aktualisieren** , um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellung/Richtlinienzeile aus den Ergebnissen anzuzeigen.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Konfigurations Drift Analyse und Registerkarte Verlauf in der Konfigurationsanalyse

Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben. Standardmäßig werden die folgenden Informationen angezeigt:

- **Zuletzt geändert**
- **Geändert von**
- **Einstellungs Name**
- **Richtlinie**
- **Type**

Klicken Sie auf **Filter** , um die Ergebnisse zu filtern. Im eingeblendeten **Filter** -Flyout können Sie aus den folgenden Filtern auswählen:

- **Startzeit** und **Endzeit** (Datum)
- **Standard Schutz** oder **strenger Schutz**

Klicken Sie auf **exportieren** , um die Ergebnisse in eine CSV-Datei zu exportieren.

![Konfigurations Drift Analyse und Verlaufsansicht in der Konfigurationsanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
