---
title: Voreingestellte Sicherheitsrichtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Standard- und Strict-Richtlinieneinstellungen für die Schutzfunktionen von Exchange Online Protection (EOP) und Microsoft Defender für Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 61166c78f31a86882ef0e2dc2a79683aea794040
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383462"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Voreingestellte Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Voreingestellte Sicherheitsrichtlinien bieten einen zentralen Ort zum gleichzeitigen Anwenden aller empfohlenen Spam-, Schadsoftware- und Phishingrichtlinien auf Benutzer. Die Richtlinieneinstellungen können nicht konfiguriert werden. Stattdessen werden sie von uns festgelegt und basieren auf unseren Beobachtungen und Erfahrungen in den Rechenzentren, um ein Gleichgewicht zwischen der Entfernung schädlicher Inhalte von Benutzern und der Vermeidung unnötiger Unterbrechungen zu finden.

Der Rest dieses Artikels beschreibt voreingestellte Sicherheitsrichtlinien und deren Konfiguration.

## <a name="what-preset-security-policies-are-made-of"></a>Voreingestellte Sicherheitsrichtlinien

Voreingestellte Sicherheitsrichtlinien bestehen aus den folgenden Elementen:

- Profile
- Richtlinien
- Richtlinieneinstellungen

Darüber hinaus ist die Rangfolge wichtig, wenn mehrere vordefinierte Sicherheitsrichtlinien und andere Richtlinien für dieselbe Person gelten.

### <a name="profiles-in-preset-security-policies"></a>Profile in vordefinierten Sicherheitsrichtlinien

Ein Profil bestimmt die Schutzebene. Die folgenden Profile sind verfügbar:

- **Standardschutz:** Ein grundlegendes Schutzprofil, das für die meisten Benutzer geeignet ist.
- **Strenger Schutz:** Ein aggressiveres Schutzprofil für ausgewählte Benutzer (hochwertige Ziele oder Benutzer mit hoher Priorität).

Sie verwenden Regeln mit Bedingungen und Ausnahmen, die bestimmen, auf wen die Profile angewendet werden.

Die verfügbaren Bedingungen und Ausnahmen sind:

- **Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
- **Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.
- **Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.

Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

### <a name="policies-in-preset-security-policies"></a>Richtlinien in vordefinierten Sicherheitsrichtlinien

Voreingestellte Sicherheitsrichtlinien verwenden die entsprechenden Richtlinien aus den verschiedenen Schutzfunktionen in EOP und Microsoft Defender für Office 365. Diese Richtlinien werden erstellt, _nachdem_ Sie den Benutzern die voreingestellten Sicherheitsrichtlinien **"Standardschutz"** oder **"Strenger Schutz"** zugewiesen haben. Sie können diese Richtlinien nicht ändern.

- **Exchange Online Protection (EOP)-Richtlinien:** Dazu gehören Microsoft 365 Organisationen mit Exchange Online Postfächern und eigenständige EOP-Organisationen ohne Exchange Online Postfächer:

  - [Antispamrichtlinien](configure-your-spam-filter-policies.md) mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy.**
  - [Antischadsoftwarerichtlinien](configure-anti-malware-policies.md) mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy.**
  - [EOP-Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings) mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy** (Spoofing-Einstellungen).

- **Microsoft Defender für Office 365-Richtlinien:** Dies umfasst Organisationen mit Microsoft 365 E5 oder Defender für Office 365-Add-On-Abonnements:

  - Antiphishingrichtlinien in Microsoft Defender für Office 365 mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy,** die Folgendes umfassen:

    - Die gleichen [Spoofingeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Antiphishingrichtlinien verfügbar sind.
    - [Identitätswechseleinstellungen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Erweiterte Phishing-Schwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Tresor links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and Strict Preset Security **Policy**.

  - [Tresor Anlagenrichtlinien](set-up-safe-attachments-policies.md) mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy.**

Beachten Sie, dass Sie EOP-Schutzmaßnahmen für Office 365 Schutz auf andere Benutzer als Microsoft Defender anwenden können.

### <a name="policy-settings-in-preset-security-policies"></a>Richtlinieneinstellungen in vordefinierten Sicherheitsrichtlinien

Sie können die Richtlinieneinstellungen in den Schutzprofilen nicht ändern. Die **Standard-** und Strict-Richtlinieneinstellungswerte werden in [den empfohlenen Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365.md)beschrieben. 

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Rangfolge für voreingestellte Sicherheitsrichtlinien und andere Richtlinien

Wenn mehrere Richtlinien auf einen Benutzer angewendet werden, wird die folgende Reihenfolge von der höchsten Priorität zur niedrigsten Priorität angewendet:

1. **Voreingestellte** Sicherheitsrichtlinie für strengen Schutz
2. **Voreingestellte Standardsicherheitsrichtlinie**
3. Benutzerdefinierte Sicherheitsrichtlinien
4. Standardsicherheitsrichtlinien

Mit anderen Worten, die Einstellungen der **Strict-Schutzrichtlinie** setzen die Einstellungen der **Standardschutzrichtlinie** außer Kraft, die die Einstellungen einer benutzerdefinierten Richtlinie überschreibt, die die Einstellungen aus der Standardrichtlinie überschreibt. 

Wenn beispielsweise eine Sicherheitseinstellung im **Standardschutz** vorhanden ist und ein Administrator den **Standardschutz** für einen Benutzer aktiviert hat, wird die **Standardschutzeinstellung** anstelle der Einstellung angewendet, die für diese Einstellung in einer benutzerdefinierten Richtlinie oder in der Standardrichtlinie (für denselben Benutzer) konfiguriert ist. Beachten Sie, dass Sie möglicherweise einen Teil Ihrer Organisation haben, auf den Sie nur die **Standard-** oder **Strict-Schutzrichtlinie** anwenden möchten, während Sie eine benutzerdefinierte Richtlinie auf andere Benutzer in Ihrer Organisation anwenden, um bestimmte Anforderungen zu erfüllen.

## <a name="assign-preset-security-policies-to-users"></a>Zuweisen voreingestellter Sicherheitsrichtlinien zu Benutzern

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:
  - Um voreingestellte Sicherheitsrichtlinien zu konfigurieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf voreingestellte Sicherheitsrichtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>Verwenden des Microsoft 365 Defender Portals, um Benutzern voreingestellte Sicherheitsrichtlinien zuzuweisen

1. Wechseln Sie im Portal Microsoft 365 Defender zur Seite "Richtlinien für **die E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln"** im Abschnitt "Richtlinien mit Vorlagen für \>  \> **voreingestellte Sicherheitsrichtlinien".**

2. Klicken Sie unter **"Standardschutz"** oder **"Strenger Schutz"** auf **"Bearbeiten".**

3. Der Assistent **"Standardschutz anwenden"** oder **"Strengen Schutz anwenden"** wird gestartet. Identifizieren Sie auf der Seite für den **EOP-Schutz** die internen Empfänger, für die der [EOP-Schutz](#policies-in-preset-security-policies) gilt (Empfängerbedingungen):
   - **Benutzer**
   - **Gruppen**
   - **Domänen**

   Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus. Wiederholen Sie diesen Vorgang so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt. Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.

   - **Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. In Microsoft Defender für Office 365 Organisationen werden Sie zum Defender für **Office 365 Schutzmaßnahmen gelten für** die Seite, um die internen Empfänger zu identifizieren, für die Microsoft Defender für Office 365 [Schutz](#policies-in-preset-security-policies) gilt (Empfängerbedingungen).

   Die Einstellungen und das Verhalten entsprechen genau den **EOP-Schutzmaßnahmen,** die auf die Seite angewendet werden.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Überprüfen Sie auf der Seite **"Überprüfen und bestätigen Sie Ihre Änderungen",** überprüfen Sie Ihre Auswahl, und klicken Sie dann auf **"Bestätigen".**

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Ändern der Zuweisungen voreingestellter Sicherheitsrichtlinien

Die Schritte zum Ändern der Zuweisung der **Standardschutz-** oder **Strict Protection-Sicherheitsrichtlinie** sind die gleichen wie bei der anfänglichen Zuweisung der [voreingestellten Sicherheitsrichtlinien zu Benutzern.](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)

Um den **Standardschutz** oder **strenge Schutzsicherheitsrichtlinien** zu deaktivieren und gleichzeitig die vorhandenen Bedingungen und Ausnahmen zu erhalten, ziehen Sie die Umschaltfläche auf **"Deaktiviert"** ![ ](../../media/scc-toggle-off.png) um. Um die Richtlinien zu aktivieren, schieben Sie die Umschaltfläche auf **"Aktiviert"** ![ ](../../media/scc-toggle-on.png) ein.

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie eine Schutzeinstellung, bei der der Standardwert von der **Standardschutzeinstellung** abweicht, um zu überprüfen, ob Sie einem Benutzer erfolgreich den **Standardschutz** **oder** die Strict-Schutzrichtlinie zugewiesen haben. Dies unterscheidet sich von der Einstellung **"Strenger Schutz".**

Überprüfen Sie beispielsweise bei E-Mails, die als Spam erkannt werden (kein Spam mit hoher Spamwahrscheinlichkeit), ob die Nachricht an den Junk-E-Mail-Ordner für **Standardschutzbenutzer** übermittelt und für **Strenger Schutz** unter Quarantäne gestellt wird.

Oder stellen Sie für [Massen-E-Mails](bulk-complaint-level-values.md)sicher, dass der BCL-Wert 6 oder höher die Nachricht an den Junk-E-Mail-Ordner für **Standardschutzbenutzer** übermittelt, und der BCL-Wert 4 oder höher unter Quarantäne stellt die Nachricht für **Strict Protection-Benutzer.**
