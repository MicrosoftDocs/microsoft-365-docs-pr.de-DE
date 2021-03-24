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
description: Administratoren erfahren, wie Sie die Konfigurationsanalyse verwenden, um Sicherheitsrichtlinien zu finden und zu beheben, die unterhalb der vordefinierten Sicherheitsrichtlinien standard protection und Strict protection liegen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065407"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Konfigurationsanalyse für Schutzrichtlinien in EOP und Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Die Konfigurationsanalyse im Security & Compliance Center bietet einen zentralen Ort zum Suchen und Beheben von Sicherheitsrichtlinien, an denen die Einstellungen unter den Einstellungen Standardschutz und Strenge Schutzprofileinstellungen in vordefinierten Sicherheitsrichtlinien [liegen.](preset-security-policies.md)

Die folgenden Richtlinientypen werden von der Konfigurationsanalyse analysiert:

- **Exchange Online Protection (EOP)-Richtlinien:** Dazu gehören Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige EOP-Organisationen ohne Exchange Online-Postfächer:

  - [Antispamrichtlinien](configure-your-spam-filter-policies.md).
  - [An malware-Richtlinien](configure-anti-malware-policies.md).
  - [EOP Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).

- **Microsoft Defender für Office 365-Richtlinien:** Dazu gehören Organisationen mit Microsoft 365 E5- oder Defender for Office 365-Add-On-Abonnements:

  - Antiphishingrichtlinien in Microsoft Defender für Office 365, die Folgendes umfassen:

    - Dieselben [Spoofeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Antiphishingrichtlinien verfügbar sind.
    - [Identitätswechseleinstellungen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Erweiterte Phishingschwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Richtlinien für sichere Links](set-up-safe-links-policies.md).

  - [Richtlinien für sichere Anlagen](set-up-safe-attachments-policies.md).

Die **Standard-** und Strict-Richtlinieneinstellungswerte, die als Basiswerte verwendet werden, werden unter Empfohlene Einstellungen für EOP und [Microsoft Defender für Office 365-Sicherheit beschrieben.](recommended-settings-for-eop-and-office365.md) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Konfigurationsanalyse zu** wechseln, verwenden Sie <https://protection.office.com/configurationAnalyzer> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Um die **Konfigurationsanalyse** zu verwenden und Sicherheitsrichtlinien zu aktualisieren, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf die Konfigurationsanalyse müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Security Reader"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >  
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Verwenden der Konfigurationsanalyse im Security & Compliance Center

Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Configuration analyzer**.

![Konfigurationsanalyse-Widget auf der Seite \> Bedrohungsverwaltungsrichtlinie](../../media/configuration-analyzer-widget.png)

Die Konfigurationsanalyse verfügt über zwei Hauptregisterkarten:

- **Einstellungen und Empfehlungen:** Sie wählen Standard oder Strict aus, und vergleichen Sie diese Einstellungen mit Ihren vorhandenen Sicherheitsrichtlinien. In den Ergebnissen können Sie die Werte Ihrer Einstellungen anpassen, um sie auf die gleiche Stufe wie Standard oder Strict zu bringen.

- **Konfigurationsdriftanalyse und -verlauf:** Mit dieser Ansicht können Sie Richtlinienänderungen im Laufe der Zeit nachverfolgen.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Registerkarte "Einstellungen und Empfehlungen" in der Konfigurationsanalyse

Standardmäßig wird die Registerkarte im Vergleich zum Standardschutzprofil geöffnet. Sie können zum Vergleich des Strikten Schutzprofils wechseln, indem Sie **auf Strenge Empfehlungen anzeigen klicken.** Wählen Sie Standardempfehlungen anzeigen aus, um **zurück zu wechseln.**

![Einstellungen und Empfehlungen in der Konfigurationsanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Standardmäßig enthält die Spalte **Richtliniengruppe/Einstellungsname** eine reduzierte Ansicht der verschiedenen Typen von Sicherheitsrichtlinien und der Anzahl der Einstellungen, die verbessert werden müssen (falls welche). Die Richtlinientypen sind:

- **Antispam**
- **Antiphishing**
- **An malware**
- **ATP Sichere Anlagen** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)
- **ATP Sichere Links** (wenn Ihr Abonnement Microsoft Defender für Office 365 enthält)

In der Standardansicht wird alles reduziert. Neben jeder Richtlinie finden Sie eine Zusammenfassung der Vergleichsergebnisse aus Ihren Richtlinien (die Sie ändern können) und den Einstellungen in den entsprechenden Richtlinien für die Standard- oder Strict-Schutzprofile (die Sie nicht ändern können). Es werden die folgenden Informationen für das Schutzprofil angezeigt, mit dem Sie vergleichen:

- **Grün**: Alle Einstellungen in allen vorhandenen Richtlinien sind mindestens so sicher wie das Schutzprofil.
- **Gelb**: Eine kleine Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil.
- **Rot**: Eine beträchtliche Anzahl von Einstellungen in den vorhandenen Richtlinien ist nicht so sicher wie das Schutzprofil. Dies können einige Einstellungen in vielen Richtlinien oder viele Einstellungen in einer Richtlinie sein.

Für vorteilhafte Vergleiche wird der Text angezeigt: **Alle Einstellungen folgen** \<**Standard** or **Strict**\> **Empfehlungen**. Andernfalls wird die Anzahl der empfohlenen Einstellungen angezeigt, die geändert werden müssen.

Wenn Sie **richtliniengruppen-/einstellungsnamen** erweitern, werden alle Richtlinien und die zugehörigen Einstellungen in jeder bestimmten Richtlinie angezeigt, die Aufmerksamkeit erfordern. Sie können auch einen bestimmten Richtlinientyp (z. B. **Antispam)** erweitern, um genau diese Einstellungen in den Richtlinientypen zu sehen, die Ihre Aufmerksamkeit erfordern.

Wenn der Vergleich keine Verbesserungsempfehlungen enthält (grün), zeigt die Erweiterung der Richtlinie nichts an. Wenn es eine Reihe von Verbesserungsempfehlungen gibt (gelb oder rot), werden die Einstellungen aufgedeckt, die Aufmerksamkeit erfordern, und entsprechende Informationen werden in den folgenden Spalten angezeigt:

- Der Name der Einstellung, die Ihre Aufmerksamkeit erfordert. Im vorherigen Screenshot ist dies beispielsweise der Schwellenwert für **Massen-E-Mails** in einer Antispamrichtlinie.

- **Richtlinie**: Der Name der betroffenen Richtlinie, die die Einstellung enthält.

- **Angewendet auf**: Die Anzahl der Benutzer, auf die die betroffenen Richtlinien angewendet werden.

- **Aktuelle Konfiguration:** Der aktuelle Wert der Einstellung.

- **Letzte Änderung:** Das Datum, an dem die Richtlinie zuletzt geändert wurde.

- **Empfehlungen**: Der Wert der Einstellung im Standard- oder Strict-Schutzprofil. Klicken Sie auf Übernehmen, um den Wert der Einstellung in Ihrer Richtlinie so zu ändern, dass sie mit dem empfohlenen Wert im Schutzprofil **übereinstimmen.** Wenn die Änderung erfolgreich war, wird die Meldung angezeigt: **Empfehlungen wurden erfolgreich angenommen.** Klicken **Sie auf Aktualisieren,** um die reduzierte Anzahl von Empfehlungen und das Entfernen der spezifischen Einstellung/Richtlinienzeile aus den Ergebnissen zu sehen.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Registerkarte Konfigurationsdriftanalyse und Verlauf in der Konfigurationsanalyse

Auf dieser Registerkarte können Sie die Änderungen nachverfolgen, die Sie an Ihren benutzerdefinierten Sicherheitsrichtlinien vorgenommen haben. Standardmäßig werden die folgenden Informationen angezeigt:

- **Zuletzt geändert**
- **Geändert von**
- **Einstellungsname**
- **Policy**
- **Type**

Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Im **angezeigten Flyout** Filter können Sie aus den folgenden Filtern auswählen:

- **Startzeit** und **Endzeit** (Datum)
- **Standardschutz oder** **strenger Schutz**

Klicken Sie auf Exportieren, um die Ergebnisse in eine **CSV-Datei zu exportieren.**

![Konfigurationsdriftanalyse und Verlaufsansicht in der Konfigurationsanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)