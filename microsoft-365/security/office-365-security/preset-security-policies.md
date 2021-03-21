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
description: Administratoren erfahren, wie Sie Standard- und Strikte Richtlinieneinstellungen für die Schutzfunktionen von Exchange Online Protection (EOP) und Microsoft Defender für Office 365 anwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57c13517d9fd41bcafea5c9d672da0e6b581ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926760"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Vordefinierte Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Voreingestellte Sicherheitsrichtlinien bieten einen zentralen Speicherort für die gleichzeitige Anwendung aller empfohlenen Spam-, Schadsoftware- und Phishingrichtlinien auf Benutzer. Die Richtlinieneinstellungen sind nicht konfigurierbar. Stattdessen werden sie von uns festgelegt und basieren auf unseren Beobachtungen und Erfahrungen in den Rechenzentren, um ein Gleichgewicht zwischen dem Fernhalten schädlicher Inhalte von Benutzern zu schaffen, ohne dass die Arbeit unterbrochen wird.

Der Rest dieses Themas beschreibt vordefinierte Sicherheitsrichtlinien und deren Konfiguration.

## <a name="what-preset-security-policies-are-made-of"></a>Aus welchen vordefinierten Sicherheitsrichtlinien besteht

Voreingestellte Sicherheitsrichtlinien bestehen aus den folgenden Elementen:

- Profile
- Richtlinien
- Richtlinieneinstellungen

Darüber hinaus ist die Rangfolge wichtig, wenn mehrere vordefinierte Sicherheitsrichtlinien und andere Richtlinien für dieselbe Person gelten.

### <a name="profiles-in-preset-security-policies"></a>Profile in vordefinierten Sicherheitsrichtlinien

Ein Profil bestimmt die Schutzebene. Die folgenden Profile sind verfügbar:

- **Standardschutz:** Ein grundlegendes Schutzprofil, das für die meisten Benutzer geeignet ist.
- **Strenger Schutz:** Ein aggressiveres Schutzprofil für ausgewählte Benutzer (hochwertige Ziele oder Prioritätsbenutzer).

Sie verwenden Regeln mit Bedingungen und Ausnahmen, die bestimmen, auf wen die Profile angewendet werden oder nicht.

Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

Die verfügbaren Bedingungen und Ausnahmen sind:

- **Die Empfänger sind:** Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
- **Die Empfänger sind Mitglieder von**: Gruppen in Ihrer Organisation.
- **Die Empfängerdomänen sind:** Akzeptierte Domänen, die in Microsoft 365 konfiguriert sind.

### <a name="policies-in-preset-security-policies"></a>Richtlinien in vordefinierten Sicherheitsrichtlinien

Voreingestellte Sicherheitsrichtlinien verwenden die entsprechenden Richtlinien aus den verschiedenen Schutzfunktionen in EOP und Microsoft Defender für Office 365. Diese Richtlinien werden _erstellt, nachdem_ Sie den Benutzern die vordefinierten **Sicherheitsrichtlinien Standardschutz** oder **Strenger** Schutz zugewiesen haben. Sie können diese Richtlinien nicht ändern.

- **Exchange Online Protection (EOP)-Richtlinien:** Dazu gehören Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige EOP-Organisationen ohne Exchange Online-Postfächer:

  - [Antispamrichtlinien mit](configure-your-spam-filter-policies.md) dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy**.
  - [An malware policies named](configure-anti-malware-policies.md) **Standard Preset Security Policy** and Strict Preset **Security Policy**.
  - [EOP Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings) mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy** (Spoof-Einstellungen).

- **Microsoft Defender für Office 365-Richtlinien:** Dazu gehören Organisationen mit Microsoft 365 E5- oder Defender for Office 365-Add-On-Abonnements:

  - Antiphishingrichtlinien in Microsoft Defender für Office 365 mit dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy,** die Folgendes umfassen:

    - Dieselben [Spoofeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Antiphishingrichtlinien verfügbar sind.
    - [Identitätswechseleinstellungen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Erweiterte Phishingschwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) mit dem **Namen Standard Preset Security Policy** und Strict Preset **Security Policy**.

  - [Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) mit dem **Namen Standard Preset Security Policy** und Strict Preset **Security Policy**.

Beachten Sie, dass Sie EOP-Schutz auf andere Benutzer anwenden können als Microsoft Defender für Office 365-Schutz.

### <a name="policy-settings-in-preset-security-policies"></a>Richtlinieneinstellungen in vordefinierten Sicherheitsrichtlinien

Sie können die Richtlinieneinstellungen in den Schutzprofilen nicht ändern. Die **Richtlinieneinstellungswerte Standard** und **Strict** werden unter Empfohlene Einstellungen für EOP und Microsoft Defender für [Office 365-Sicherheit beschrieben.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Rangfolge für vordefinierte Sicherheitsrichtlinien und andere Richtlinien

Wenn mehrere Richtlinien auf einen Benutzer angewendet werden, wird die folgende Reihenfolge von der höchsten auf die niedrigste Priorität angewendet:

1. **Strikte** voreingestellte Sicherheitsrichtlinie für den Schutz
2. **Standardmäßige sicherheitsvoreingestellte** Sicherheitsrichtlinie für den Schutz
3. Benutzerdefinierte Sicherheitsrichtlinien
4. Standardsicherheitsrichtlinien

Anders ausgedrückt: Die Einstellungen  der Strikten Schutzrichtlinie überschreiben die Einstellungen der **Standardschutzrichtlinie,** die die Einstellungen aus einer benutzerdefinierten Richtlinie außer Kraft setzt, die die Einstellungen aus der Standardrichtlinie überschreibt.

## <a name="assign-preset-security-policies-to-users"></a>Zuweisen vordefinierter Sicherheitsrichtlinien zu Benutzern

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Voreingestellte Sicherheitsrichtlinien zu** wechseln, verwenden Sie <https://protection.office.com/presetSecurityPolicies> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:
  - Zum Konfigurieren vordefinierter Sicherheitsrichtlinien müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf vordefinierte Sicherheitsrichtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweis:** Durch hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im  Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen und Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Verwenden des Security & Compliance Center zum Zuweisen vordefinierter Sicherheitsrichtlinien für Benutzer

1. Wechseln Sie im Security & Compliance Center **zu** Richtlinienvoreingestellte Sicherheitsrichtlinien für die \>  \> **Bedrohungsverwaltung.**

2. Klicken **Sie unter Standardschutz** **oder Strenger Schutz** auf **Bearbeiten**.

3. Der **Assistent Standardschutz anwenden** oder Strikt anwenden **wird** gestartet. Identifizieren Sie **in den EOP-Schutzbestimmungen** für Schritt die internen Empfänger, für die die [EOP-Schutze](#policies-in-preset-security-policies) gelten:

   1. Klicken **Sie auf Bedingung hinzufügen**. Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:

      - **Die Empfänger sind**
      - **Die Empfänger sind Mitglieder von**
      - **Die Empfängerdomänen sind**

      Sie können eine Bedingung nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung angeben. Mehrere Werte derselben Bedingung verwenden OR-Logik (z. B. _\<recipient1\>_ oder _\<recipient2\>_ ).

   2. Die ausgewählte Bedingung wird in einem schattierten Abschnitt angezeigt. Klicken Sie in diesem Abschnitt in das Feld **Alle dieser** Kontrollkästchen. Wenn Sie einen Moment warten, wird eine Liste angezeigt, damit Sie einen Wert auswählen können. Sie können auch mit der Eingabe eines Werts beginnen, um die Liste zu filtern und einen Wert auszuwählen. Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie zum Entfernen eines einzelnen Werts **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert. Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.

   3. Klicken Sie auf Bedingung hinzufügen, und **wählen** Sie aus den verbleibenden Bedingungen aus, um eine weitere Bedingung hinzuzufügen. Unterschiedliche Bedingungen verwenden AND-Logik (z. B. _\<recipient1\>_ und _\<member of group 1\>_ ).

      Wiederholen Sie den vorherigen Schritt, um der Bedingung Werte hinzuzufügen, und wiederholen Sie diesen Schritt so oft wie erforderlich oder bis sie keine Bedingungen mehr haben.

   4. Klicken Sie auf Bedingung hinzufügen, um eine Ausnahme **hinzuzufügen.** Wählen Sie in der angezeigten Dropdownliste unter **Except when eine Bedingung aus.** Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Wenn Ihre Organisation Über Microsoft Defender für Office 365 verfügt, werden Sie zu den **ATP-Schutzbestimmungen** zur Identifizierung der internen Empfänger, für die die [Microsoft Defender for Office 365-Schutzmaßnahmen](#policies-in-preset-security-policies) gelten, verwendet.

   Die Einstellungen und das Verhalten sind genau wie die **EOP-Schutzeinstellungen für** Schritt.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **im Schritt** Bestätigen Ihre Auswahl, und klicken Sie dann auf **Bestätigen**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Verwenden des Security & Compliance Center zum Ändern der Zuweisungen vordefinierter Sicherheitsrichtlinien

Die Schritte zum Ändern der Zuweisung der **Standardschutz-** oder **Strikten** Schutzsicherheitsrichtlinie sind identisch mit dem, als Sie den Benutzern zunächst die vordefinierten [Sicherheitsrichtlinien zugewiesen haben.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

Um die **Standardschutz-** oder **Strikte** Schutzsicherheitsrichtlinien zu deaktivieren und dabei die vorhandenen Bedingungen und Ausnahmen zu erhalten, verschieben Sie den Umschalter auf **Deaktiviert**. Um die Richtlinien zu aktivieren, verschieben Sie den Umschalter auf **Aktiviert.**

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie eine Schutzeinstellung, bei der  der Standardwert von der Standardschutzeinstellung abhing, die  sich von der Einstellung Strikter Schutz abhing, um zu überprüfen, ob Sie einem Benutzer die Standardschutz- oder Strikte Schutzsicherheitsrichtlinie erfolgreich zugewiesen haben.  

Bei E-Mails, die als Spam erkannt werden (nicht als Spam mit hoher Vertrauenssicherheit), überprüfen Sie beispielsweise, ob die Nachricht an den Junk-E-Mail-Ordner für **Standardschutzbenutzer** zugestellt und für Benutzer des strengen Schutzes unter Quarantäne **gestellt** wird.

Oder stellen Sie bei Massen-E-Mails [sicher,](bulk-complaint-level-values.md)dass der BCL-Wert 6 oder höher die Nachricht an den Junk-E-Mail-Ordner für **Standardschutzbenutzer** übermittelt, und der BCL-Wert 4 oder höher isoliert die Nachricht für Strict **Protection-Benutzer.**