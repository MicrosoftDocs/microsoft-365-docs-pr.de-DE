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
ms.openlocfilehash: f57b388716eca02741ba48b3e6b47b7cf9f28884
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150081"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Voreingestellte Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Voreingestellte Sicherheitsrichtlinien bieten einen zentralen Ort zum gleichzeitigen Anwenden aller empfohlenen Spam-, Schadsoftware- und Phishingrichtlinien auf Benutzer. Die Richtlinieneinstellungen können nicht konfiguriert werden. Stattdessen werden sie von uns festgelegt und basieren auf unseren Beobachtungen und Erfahrungen in den Rechenzentren für ein Gleichgewicht zwischen dem Weghalten schädlicher Inhalte von Benutzern, ohne ihre Arbeit zu unterbrechen.

Im rest dieses Themas werden voreingestellte Sicherheitsrichtlinien und deren Konfiguration beschrieben.

## <a name="what-preset-security-policies-are-made-of"></a>Was voreingestellte Sicherheitsrichtlinien sind

Voreingestellte Sicherheitsrichtlinien bestehen aus den folgenden Elementen:

- Profile
- Richtlinien
- Richtlinieneinstellungen

Darüber hinaus ist die Rangfolge wichtig, wenn mehrere vordefinierte Sicherheitsrichtlinien und andere Richtlinien auf dieselbe Person angewendet werden.

### <a name="profiles-in-preset-security-policies"></a>Profile in voreingestellten Sicherheitsrichtlinien

Ein Profil bestimmt die Schutzebene. Die folgenden Profile sind verfügbar:

- **Standardschutz:** Ein grundlegendes Schutzprofil, das für die meisten Benutzer geeignet ist.
- **Strenger Schutz:** Ein aggressiveres Schutzprofil für ausgewählte Benutzer (hochwertige Ziele oder Benutzer mit Priorität).

Sie verwenden Regeln mit Bedingungen und Ausnahmen, die bestimmen, auf wen die Profile angewendet werden.

Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

Die verfügbaren Bedingungen und Ausnahmen sind:

- **Die Empfänger sind:** Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
- **Die Empfänger sind Mitglieder von**: Gruppen in Ihrer Organisation.
- **Die Empfängerdomänen sind:** Akzeptierte Domänen, die in Microsoft 365 konfiguriert sind.

### <a name="policies-in-preset-security-policies"></a>Richtlinien in vordefinierten Sicherheitsrichtlinien

Voreingestellte Sicherheitsrichtlinien verwenden die entsprechenden Richtlinien aus den verschiedenen Schutzfunktionen in EOP und Microsoft Defender für Office 365. Diese Richtlinien werden _erstellt, nachdem_  Sie den Benutzern die vordefinierten Sicherheitsrichtlinien **"Standardschutz"** oder "Strenger Schutz" zugewiesen haben. Sie können diese Richtlinien nicht ändern.

- **Exchange Online Protection (EOP)-Richtlinien:** Dazu gehören Microsoft 365-Organisationen mit Exchange Online-Postfächern und eigenständige EOP-Organisationen ohne Exchange Online-Postfächer:

  - [Antispamrichtlinien mit](configure-your-spam-filter-policies.md) dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy**.
  - [An malware policies named](configure-anti-malware-policies.md) **Standard Preset Security Policy** and Strict Preset **Security Policy**.
  - [EOP Antiphishingrichtlinien mit](set-up-anti-phishing-policies.md#spoof-settings) dem Namen **Standard Preset Security Policy** und Strict Preset Security **Policy** (Spoofing Settings).

- **Microsoft Defender für Office 365-Richtlinien:** Dazu gehören Organisationen mit Microsoft 365 E5- oder Defender für Office 365-Add-On-Abonnements:

  - Antiphishingrichtlinien in Microsoft Defender für Office 365 mit dem Namen **"Standard Preset Security Policy"** und **"Strict Preset Security Policy",** die Folgendes umfassen:

    - Dieselben [Spoofeinstellungen,](set-up-anti-phishing-policies.md#spoof-settings) die in den EOP-Antiphishingrichtlinien verfügbar sind.
    - [Identitätswechseleinstellungen](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Erweiterte Phishingschwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) mit dem Namen **Standard Preset Security Policy** und Strict Preset **Security Policy**.

  - [Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) mit dem Namen **Standard Preset Security Policy** und Strict Preset **Security Policy**.

Beachten Sie, dass Sie den Schutz von EOP auf andere Benutzer als Microsoft Defender für Office 365-Schutz anwenden können.

### <a name="policy-settings-in-preset-security-policies"></a>Richtlinieneinstellungen in voreingestellten Sicherheitsrichtlinien

Sie können die Richtlinieneinstellungen in den Schutzprofilen nicht ändern. Die Werte der **Richtlinieneinstellung** **"Standard"** und "Strict" werden in den empfohlenen Einstellungen für EOP und [Microsoft Defender für Office 365 Security beschrieben.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioritätsreihenfolge für voreingestellte Sicherheitsrichtlinien und andere Richtlinien

Wenn mehrere Richtlinien auf einen Benutzer angewendet werden, wird die folgende Reihenfolge von der höchsten bis zur niedrigsten Priorität angewendet:

1. **Voreingestellte Sicherheitsrichtlinie** für strengen Schutz
2. **Voreingestellte** Standardschutzsicherheitsrichtlinie
3. Benutzerdefinierte Sicherheitsrichtlinien
4. Standardsicherheitsrichtlinien

Anders ausgedrückt: Die Einstellungen  der Richtlinie "Strenger  Schutz" setzen die Einstellungen der Standardschutzrichtlinie außer Kraft, die die Einstellungen einer benutzerdefinierten Richtlinie außer Kraft setzt, wodurch die Einstellungen der Standardrichtlinie überschrieben werden.

## <a name="assign-preset-security-policies-to-users"></a>Zuweisen vordefinierter Sicherheitsrichtlinien zu Benutzern

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite vordefinierte **Sicherheitsrichtlinien zu** wechseln, verwenden Sie <https://protection.office.com/presetSecurityPolicies> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Konfigurieren voreingestellter Sicherheitsrichtlinien müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf voreingestellte Sicherheitsrichtlinien müssen Sie Mitglied der Rollengruppe "Globaler **Leser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweis:** Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance _Center_ sowie Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Verwenden des Security & Compliance Center zum Zuweisen vordefinierter Sicherheitsrichtlinien zu Benutzern

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinienvoreingestellte Sicherheitsrichtlinien für die \>  \> **Bedrohungsverwaltung".**

2. Klicken **Sie unter "Standardschutz"** **oder "Strenger Schutz"** auf **"Bearbeiten".**

3. Der **Assistent "Standardschutz anwenden"** oder **"Strikt anwenden" wird** gestartet. Identifizieren Sie in den auf Schritt angewendeten **EOP-Schutzmaßnahmen** die internen Empfänger, für die die [EOP-Schutzmaßnahmen](#policies-in-preset-security-policies) gelten:

   1. Klicken **Sie auf Bedingung hinzufügen**. Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet" aus, wenn:**

      - **Die Empfänger sind**
      - **Die Empfänger sind Mitglieder von**
      - **Die Empfängerdomänen sind**

      Sie können eine Bedingung nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung angeben. Mehrere Werte derselben Bedingung verwenden OR-Logik (z. B. _\<recipient1\>_ oder _\<recipient2\>_ ).

   2. Die von Ihnen ausgewählte Bedingung wird in einem schattierten Abschnitt angezeigt. Klicken Sie in diesem Abschnitt auf eines **dieser Kontrollkästchen.** Wenn Sie einen Moment warten, wird eine Liste angezeigt, sodass Sie einen Wert auswählen können. Sie können auch mit der Eingabe eines Werts beginnen, um die Liste zu filtern und einen Wert auszuwählen. Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie zum Entfernen eines einzelnen Werts **auf** das Symbol ![ ](../../media/scc-remove-icon.png) "Entfernen" für den Wert. Um die gesamte Bedingung zu entfernen, **klicken** Sie in der Bedingung ![ auf ](../../media/scc-remove-icon.png) "Entfernen".

   3. Um eine weitere Bedingung hinzuzufügen, klicken Sie auf **"Bedingung hinzufügen",** und wählen Sie eine der verbleibenden Bedingungen aus. Unterschiedliche Bedingungen verwenden AND-Logik (z. B. _\<recipient1\>_ und _\<member of group 1\>_ ).

      Wiederholen Sie den vorherigen Schritt, um der Bedingung Werte hinzuzufügen, und wiederholen Sie diesen Schritt so oft wie nötig oder bis die Bedingungen nicht mehr erfüllt sind.

   4. Klicken Sie auf "Bedingung hinzufügen", um **eine Ausnahme hinzuzufügen.** Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **Except when aus.** Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Wenn Ihre Organisation über Microsoft Defender für Office 365 verfügt, wenden Sie sich an die ATP-Schutzbestimmungen, um die internen Empfänger zu identifizieren, für die der [Microsoft Defender für Office 365-Schutz](#policies-in-preset-security-policies) gilt. 

   Die Einstellungen und das Verhalten sind genau wie die **EOP-Schutzeinstellungen, die für Denkschritte gelten.**

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **im Schritt** "Bestätigen" Ihre Auswahl, und klicken Sie dann auf **"Bestätigen".**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Verwenden des Security & Compliance Center zum Ändern der Zuweisungen vordefinierter Sicherheitsrichtlinien

Die Schritte zum Ändern der Zuweisung  der Sicherheitsrichtlinie **"Standardschutz"** oder "Strenger Schutz" sind identisch mit der Zuweisung der voreingestellten [Sicherheitsrichtlinien zu Benutzern.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

Um die **Standardschutz-** oder **Strikte** Schutzsicherheitsrichtlinien zu deaktivieren und dabei die vorhandenen Bedingungen und Ausnahmen zu erhalten, ziehen Sie den Umschalter in **"Deaktiviert".** Um die Richtlinien zu aktivieren, ziehen Sie den Umschalter in **"Aktiviert".**

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie eine Schutzeinstellung,  bei der  sich der Standardwert von der Standardschutzeinstellung abh?nst, die sich von  der Einstellung "Strenger Schutz" abh?nst, um zu überprüfen, ob Sie einem Benutzer den Standardschutz oder die Sicherheitsrichtlinie "Strenger Schutz" erfolgreich zugewiesen haben. 

Überprüfen Sie beispielsweise bei E-Mails, die als Spam erkannt wurden (keine Spam mit  hoher Confidence), dass die Nachricht an den Junk-E-Mail-Ordner für Standardschutzbenutzer zugestellt und für Benutzer des strengen Schutzes unter Quarantäne gestellt **wird.**

Oder stellen Sie bei Massen-E-Mails [sicher,](bulk-complaint-level-values.md)dass der BCL-Wert 6 oder höher die Nachricht an den Junk-E-Mail-Ordner für **Standardschutzbenutzer** übermittelt, und der BCL-Wert 4 oder höher isoliert die Nachricht für Strict-Schutz-Benutzer. 
