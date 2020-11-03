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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie Standard mäßige und strenge Richtlinieneinstellungen über die Schutzfunktionen von Exchange Online Protection (EoP) und Office 365 Advanced Threat Protection (ATP) anwenden können.
ms.openlocfilehash: a624d48944965c217fb8547e4f09da0ec388e615
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830537"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a>Voreingestellte Sicherheitsrichtlinien in EoP und Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Vordefinierte Sicherheitsrichtlinien bieten einen zentralisierten Standort, um alle empfohlenen Spam-, Schadsoftware-und Phishing-Richtlinien gleichzeitig auf Benutzer anzuwenden. Die Richtlinieneinstellungen können nicht konfiguriert werden. Stattdessen werden Sie von uns festgelegt und basieren auf unseren Beobachtungen und Erfahrungen in den Rechenzentren für ein Gleichgewichtzwischen dem aufhalten schädlicher Inhalte von Benutzern, ohne Ihre Arbeit zu unterbrechen.

Der Rest dieses Themas beschreibt vordefinierte Sicherheitsrichtlinien und deren Konfiguration.

## <a name="what-preset-security-policies-are-made-of"></a>Welche vordefinierten Sicherheitsrichtlinien werden ausgeführt?

Vordefinierte Sicherheitsrichtlinien bestehen aus den folgenden Elementen:

- Profile
- Richtlinien
- Richtlinieneinstellungen

Darüber hinaus ist die Rangfolge wichtig, wenn mehrere vordefinierte Sicherheitsrichtlinien und andere Richtlinien auf dieselbe Person zutreffen.

### <a name="profiles-in-preset-security-policies"></a>Profile in vordefinierten Sicherheitsrichtlinien

Ein Profil bestimmt den Schutzgrad. Die folgenden Profile sind verfügbar:

- **Standard Schutz** : ein grundlegendes Schutzprofil, das für die meisten Benutzer geeignet ist.
- **Strenger Schutz** : ein aggressiveres Schutzprofil für ausgewählte Benutzer (hochwertige Ziele oder Prioritäts Benutzer).

Sie verwenden Regeln mit Bedingungen und Ausnahmen, die bestimmen, auf wen die Profile angewendet werden oder nicht.

Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_ ). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_ ).

Die verfügbaren Bedingungen und Ausnahmen sind:

- **Die Empfänger sind** : Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation.
- **Die Empfänger sind Mitglieder von** : Gruppen in Ihrer Organisation.
- **Die Empfängerdomänen sind** : akzeptierte Domänen, die in Microsoft 365 konfiguriert sind.

### <a name="policies-in-preset-security-policies"></a>Richtlinien in vordefinierten Sicherheitsrichtlinien

Vordefinierte Sicherheitsrichtlinien verwenden die entsprechenden Richtlinien aus den verschiedenen Schutzfeatures in EoP und Office 365 ATP. Diese Richtlinien werden erstellt, _nachdem_ Sie den Benutzern die vordefinierten Sicherheitsrichtlinien für **Standard Schutz** oder **strenge Schutz** zugewiesen haben. Diese Richtlinien können nicht geändert werden.

- **Exchange Online Protection (EoP)-Richtlinien** : Dies umfasst Microsoft 365-Organisationen mit Exchange Online Postfächern und eigenständigen EoP-Organisationen ohne Exchange Online Postfächern:
  
  - [Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md) mit dem Namen " **Standard-vordefinierte Sicherheitsrichtlinie** " und **strenge vordefinierte Sicherheitsrichtlinie**
  - [Antischadsoftware-Richtlinien](configure-anti-malware-policies.md) mit dem Namen " **Standard vordefinierte Sicherheitsrichtlinie** " und **strenge vordefinierte Sicherheitsrichtlinie**
  - [EoP-Anti-Phishing-Richtlinien](set-up-anti-phishing-policies.md#spoof-settings) mit dem Namen " **Standard mäßige Sicherheitsrichtlinie** " und " **strenge vordefinierte Sicherheitsrichtlinie** " (Spoof-Einstellungen).

- **Office 365 Advanced Threat Protection (ATP)-Richtlinien** : Dies umfasst Organisationen mit Microsoft 365 E5 oder Office 365 ATP-Add-on-Abonnements:

  - ATP-Anti-Phishing-Richtlinien mit dem Namen " **Standard Preset Security Policy** " und **strenge vordefinierte Sicherheitsrichtlinien** , einschließlich:

    - Dieselben [spoofeinstellungen](set-up-anti-phishing-policies.md#spoof-settings) , die in den EoP-Richtlinien zum Schutz vor Phishing verfügbar sind.
    - [Einstellungen für Identitätswechsel](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Erweiterte Phishing-Schwellenwerte](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) mit dem Namen " **Standard vordefinierte Sicherheitsrichtlinie** und **strenge vordefinierte Sicherheitsrichtlinie** ".

  - [Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) mit dem Namen " **Standard mäßige Sicherheitsrichtlinie** und **strenge vordefinierte Sicherheitsrichtlinie** ".

Beachten Sie, dass Sie EoP-Schutz für unterschiedliche Benutzer als ATP-Schutz anwenden können.

### <a name="policy-settings-in-preset-security-policies"></a>Richtlinieneinstellungen in vordefinierten Sicherheitsrichtlinien

Die Richtlinieneinstellungen in den Schutzprofilen können nicht geändert werden. Die **Standard mäßigen** und **strengen** Richtlinien Einstellungswerte werden in den [empfohlenen Einstellungen für EoP und Office 365 ATP-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)beschrieben.

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Prioritätsreihenfolge für vordefinierte Sicherheitsrichtlinien und andere Richtlinien

Wenn mehrere Richtlinien auf einen Benutzer angewendet werden, wird die folgende Reihenfolge von der höchsten Priorität bis zur niedrigsten Priorität angewendet:

1. **Strenge Schutz** voreingestellte Sicherheitsrichtlinie
2. **Standard Schutz** vordefinierte Sicherheitsrichtlinie
3. Benutzerdefinierte Sicherheitsrichtlinien
4. Standardsicherheitsrichtlinien

Mit anderen Worten: mit den Einstellungen der **strengen Schutz** Richtlinie werden die Einstellungen der **Standardschutz** Richtlinie außer Kraft gesetzt, die die Einstellungen aus einer benutzerdefinierten Richtlinie außer Kraft setzt, die die Einstellungen aus der Standardrichtlinie außer Kraft setzt.

## <a name="assign-preset-security-policies-to-users"></a>Zuweisen vordefinierter Sicherheitsrichtlinien zu Benutzern

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite mit den **vordefinierten Sicherheitsrichtlinien** wechseln möchten, verwenden Sie <https://protection.office.com/presetSecurityPolicies> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:

  - Um vordefinierte Sicherheitsrichtlinien zu konfigurieren, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Für den schreibgeschützten Zugriff auf vordefinierte Sicherheitsrichtlinien müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Globaler Leser** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Zuweisen von vordefinierten Sicherheitsrichtlinien zu Benutzern mithilfe des Security & Compliance Centers

1. Wechseln Sie im Security & Compliance Center zu den **Threat management** \> **Policy** \> **vordefinierten Sicherheitsrichtlinien** für Threat Management Policy.

2. Klicken Sie unter **Standard Schutz** oder **strenger Schutz** auf **Bearbeiten** .

3. Der Assistent zum **Anwenden von Standard Schutz** oder zum **Anwenden eines strengen Schutzes** wird gestartet. Identifizieren Sie im Abschnitt **EoP-Schutz** für Schritt die internen Empfänger, auf die die [EoP-Schutzmaßnahmen](#policies-in-preset-security-policies) zutreffen:

   1. Klicken Sie auf **Bedingung hinzufügen** . Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn** :

      - **Die Empfänger werden**
      - **Die Empfänger sind Mitglieder von**
      - **Die Empfängerdomänen werden**

      Sie können nur einmal eine Bedingung verwenden, aber Sie können mehrere Werte für die Bedingung angeben. Mehrere Werte der gleichen Bedingung verwenden oder Logik (beispielsweise _\<recipient1\>_ oder _\<recipient2\>_ ).

   2. Die von Ihnen ausgewählte Bedingung wird in einem schattierten Abschnitt angezeigt. Klicken Sie in diesem Abschnitt auf das **beliebige** Feld. Wenn Sie einen Moment warten, wird eine Liste angezeigt, in der Sie einen Wert auswählen können. Sie können auch mit der Eingabe eines Werts beginnen, um die Liste zu filtern und einen Wert auszuwählen. Wiederholen Sie diesen Schritt so oft wie nötig. Wenn Sie einen einzelnen Wert entfernen möchten **, klicken Sie** ![ ](../../media/scc-remove-icon.png) auf dem Wert auf entfernen-Symbol entfernen. Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .

   3. Klicken Sie zum Hinzufügen einer weiteren Bedingung auf **Bedingung hinzufügen** , und wählen Sie unter den restlichen Bedingungen aus. Unterschiedliche Bedingungen verwenden und Logik (beispielsweise _\<recipient1\>_ und _\<member of group 1\>_ ).

      Wiederholen Sie den vorherigen Schritt, um der Bedingung Werte hinzuzufügen, und wiederholen Sie diesen Schritt so oft wie nötig oder bis die Bedingungen abgelaufen sind.

   4. Klicken Sie zum Hinzufügen einer Ausnahme auf **Bedingung hinzufügen** . Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **außer when** aus. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter** .

4. Wenn Ihre Organisation Office 365 ATP hat, werden Sie zum Schritt " **ATP-Schutz gilt für** " geführt, um die internen Empfänger zu identifizieren, auf die der [Office 365 ATP-Schutz](#policies-in-preset-security-policies) angewendet wird.

   Die Einstellungen und das Verhalten sind genau wie die **EoP-Schutzmaßnahmen für** Step.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter** .

5. Überprüfen Sie im Schritt **bestätigen** Ihre Auswahl, und klicken Sie dann auf **bestätigen** .

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Verwenden des Security & Compliance Center zum Ändern der Zuweisungen von vordefinierten Sicherheitsrichtlinien

Die Schritte zum Ändern der Zuweisung der Sicherheitsrichtlinie " **Standard Schutz** " oder " **Strict Protection** " entsprechen denen, die Sie den [Benutzern anfänglich vordefinierten Sicherheitsrichtlinien zugewiesen](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)haben.

Um die **Standard mäßigen Schutz** **-oder Sicherheits** Richtlinien zu deaktivieren und gleichzeitig die vorhandenen Bedingungen und Ausnahmen zu erhalten, schieben Sie die Umschaltfläche auf **deaktiviert** . Um die Richtlinien zu aktivieren, schieben Sie die Umschaltfläche auf **aktiviert** .

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Um zu überprüfen, ob Sie den **Standardschutz** oder die Richtlinie zum Schutz des Sicherheits **Schutzes** erfolgreich einem Benutzer zugewiesen haben, verwenden Sie eine Schutzeinstellung, bei der sich der Standardwert von der **Standardschutz** Einstellung unterscheidet, was sich von der Einstellung für den **strengen Schutz** unterscheidet.

Beispiel: bei e-Mails, die als Spam erkannt werden (nicht als Spam mit hoher Vertrauenswürdigkeit), stellen Sie sicher, dass die Nachricht für **Standard Schutz** Benutzer an den Junk-e-Mail-Ordner übermittelt und für Benutzer mit **striktem Schutz** isoliert wurde.

Für [Massen-e-Mail](bulk-complaint-level-values.md)-Nachrichten stellen Sie sicher, dass der BCL-Wert 6 oder höher die Nachricht an den Junk-e-Mail-Ordner für **Standard Schutz** Benutzer übermittelt, und der BCL-Wert 4 oder höher isoliert die Nachricht für **strenge Schutz** Benutzer.
