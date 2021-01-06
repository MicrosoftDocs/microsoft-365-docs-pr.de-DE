---
title: Konfigurieren von Anti-Phishing-Richtlinien in EOP
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
description: Administratoren können erfahren, wie Sie die AntiPhishing-Richtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EoP)-Organisationen mit oder ohne Exchange Online Postfächern verfügbar sind.
ms.openlocfilehash: 03c1ce8e940491607fe04988d41c927f92479d96
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760332"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Konfigurieren von Anti-Phishing-Richtlinien in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer gibt es eine standardmäßige Anti-Phishing-Richtlinie, die eine beschränkte Anzahl von Antispoofing-Funktionen enthält, die standardmäßig aktiviert sind. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

Administratoren können die standardmäßige Anti-Phishing-Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen). Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte Anti-Phishing-Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Organisationen mit Exchange Online Postfächern können Anti-Phishing-Richtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren. Eigenständige EoP-Organisationen können nur das Security & Compliance Center verwenden.

Informationen zum Erstellen und Ändern der erweiterten Anti-Phishing-Richtlinien in Microsoft Defender für Office 365, die in Defender für Office 365 verfügbar sind, finden Sie unter [configure Anti-Phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

Die grundlegenden Elemente einer Anti-Phishing-Richtlinie sind:

- **Die Anti-Phishing-Richtlinie**: gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.
- **Die Anti-Phishing-Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Anti-Phishing-Richtlinien im Security & Compliance Center verwalten:

- Wenn Sie eine Anti-Phishing-Richtlinie erstellen, erstellen Sie tatsächlich eine Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide.
- Wenn Sie eine Anti-Phishing-Richtlinie ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Anti-Phishing-Regel. Alle anderen Einstellungen ändern die zugehörige Anti-Phishing-Richtlinie.
- Wenn Sie eine Anti-Phishing-Richtlinie entfernen, werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie entfernt.

In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat. Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell zum Konfigurieren von Richtlinien für die antiphishingbehandlung](#use-exchange-online-powershell-to-configure-anti-phishing-policies) weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default", die die folgenden Eigenschaften aufweist:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität des Anti-Phishing-Schutzes zu verbessern, können Sie benutzerdefinierte Anti-Phishing-Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Anti-Phishing** wechseln möchten, verwenden Sie <https://protection.office.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Sie können keine Anti-Phishing-Richtlinien in eigenständigen EoP PowerShell verwalten.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Hinzufügen, ändern und Löschen von Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.
  - Für den schreibgeschützten Zugriff auf Anti-Phishing-Richtlinien müssen Sie ein Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein <sup>\*</sup> .

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe " **Organisationsverwaltung** " in der Ansicht "nur Leserechten" in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) bietet außerdem schreibgeschützten Zugriff auf das Feature <sup>\*</sup> .
  - <sup>\*</sup> Im Security & Compliance Center können Benutzer mit dem schreibgeschützten Zugriff die Einstellungen von benutzerdefinierten Richtlinien zum Schutz vor Phishing anzeigen. Schreibgeschützte Benutzer können die Einstellungen in der standardmäßigen Anti-Phishing-Richtlinie nicht sehen.

- Zum Erstellen und Ändern von Anti-Phishing-Richtlinien in eigenständigen EoP müssen Sie etwas tun, das für Ihren Mandanten _Hydratation_ erfordert. Im Exchange Admin Center (EAC) können Sie beispielsweise zur Registerkarte **Berechtigungen** wechseln, eine vorhandene Rollengruppe auswählen, auf Bearbeitungssymbol **Bearbeiten** klicken ![ ](../../media/ITPro-EAC-EditIcon.png) und eine Rolle entfernen (die Sie letztendlich wieder hinzufügen werden). Wenn Ihr Mandant noch nie hydratisiert wurde, erhalten Sie ein Dialogfeld mit dem Namen **Update Organization Settings** with a Progress Bar, die erfolgreich abgeschlossen werden soll. Weitere Informationen zur Hydratation finden Sie unter dem Cmdlet [enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (das nicht in eigenständigen EoP PowerShell oder im Security & Compliance Center verfügbar ist).

- Unsere empfohlenen Einstellungen für Anti-Phishing-Richtlinien finden Sie unter [EoP default Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Lassen Sie bis zu 30 Minuten für die Anwendung der aktualisierten Richtlinie zu.

- Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Anti-Phishing-Richtlinien

Durch das Erstellen einer benutzerdefinierten Anti-Phishing-Richtlinie im Security & Compliance Center werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.

Wenn Sie eine Anti-Phishing-Richtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der angibt, für wen die Richtlinie gilt. Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardeinstellungen für AntiPhishing zu ändern oder zu überprüfen.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Klicken Sie auf der Seite **Anti-Phishing** auf **Erstellen**.

3. Der Assistent zum **Erstellen eines neuen Anti-Phishing-Richtlinien** wird geöffnet. Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken Sie auf **Bedingung hinzufügen**. Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:

   - **Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.

   - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.
   - Wenn Sie einzelne Einträge entfernen möchten  , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.
   - Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei** aus.

   Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if** eine Ausnahme aus. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen. Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.

   Wenn Sie fertig sind, klicken Sie auf **Diese Richtlinie erstellen**.

6. Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **OK** .

Nachdem Sie die Anti-Phishing-Richtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, können Sie anhand der Anweisungen im nächsten Abschnitt die Schutzeinstellungen in der Richtlinie konfigurieren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Anti-Phishing-Richtlinien

Verwenden Sie die folgenden Verfahren, um Richtlinien zum Schutz vor Phishing zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.

1. Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Wählen Sie die benutzerdefinierte Richtlinie zum Schutz vor Phishing aus, die Sie ändern möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

3. Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt. Durch Klicken auf **Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.

   - Die folgenden Schritte werden in der Reihenfolge angezeigt, in der die Abschnitte dargestellt werden, Sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).

   - Nachdem Sie in einem Abschnitt auf **Bearbeiten** klicken, werden die verfügbaren Einstellungen in einem Assistenten Format angezeigt, aber Sie können in beliebiger Reihenfolge auf die Seiten springen, und Sie können auf einer beliebigen Seite auf **Speichern** **(oder** **Abbrechen** oder Schließen schließen) klicken, um ![ ](../../media/scc-remove-icon.png) zur Seite **Richtlinie \<name\> Bearbeiten** zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder verlassen besuchen).

4. **Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten** , um dieselben Einstellungen zu ändern, die beim [Erstellen der Richtlinie](#use-the-security--compliance-center-to-create-anti-phishing-policies) im vorherigen Abschnitt verfügbar waren:

   - **Name**
   - **Beschreibung**
   - **Angewendet auf**
   - **Überprüfen der Einstellungen**

   Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

5. **Spoof**: Klicken Sie auf **Bearbeiten** , um Spoof Intelligence ein-oder auszuschalten, die nicht authentifizierte Absender Identifikation in Outlook ein-oder auszuschalten und die Aktion so zu konfigurieren, dass Sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

   Beachten Sie, dass diese Einstellungen auch in Anti-Phishing-Richtlinien in Defender für Office 365 zur Verfügung stehen.

   - **Spoofing-Filtereinstellungen**: der Standardwert ist " **on**", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**. Weitere Informationen finden Sie unter [configure Spoof Intelligence in EoP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Microsoft 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - Nicht **authentifizierte Absender Funktion aktivieren**: der Standardwert ist **on**. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.

   - **Actions: geben** Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:

     **Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen**:

     - **Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern**
     - **Nachricht isolieren**

   - **Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.

     - Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.
     - Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :

       - **Aktivieren von Schutz vor Spoofing**
       - **Nicht authentifizierte Absender Funktion aktivieren**

   Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

6. Überprüfen Sie die Einstellungen auf der Seite **Richtlinie \<Name\> Bearbeiten** , und klicken Sie dann auf **Schließen**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Verwenden des Security & Compliance Center zum Ändern der standardmäßigen Anti-Phishing-Richtlinie

Die standardmäßige Anti-Phishing-Richtlinie heißt Office365 AntiPhishing Default, und Sie wird nicht in der Liste der Richtlinien angezeigt. Führen Sie die folgenden Schritte aus, um die standardmäßige Anti-Phishing-Richtlinie zu ändern:

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie**.

3. Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt. Die folgenden Abschnitte sind verfügbar, die identische Einstellungen enthalten, wenn Sie [eine benutzerdefinierte Richtlinie ändern](#use-the-security--compliance-center-to-modify-anti-phishing-policies).

   - **Impersonation**
   - **Spoofing**
   - **Erweiterte Einstellungen**

   Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:

   - Sie können den Abschnitt mit den **Richtlinieneinstellungen** und die Werte anzeigen, es gibt jedoch keinen Link **Bearbeiten** , sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).
   - Die Standardrichtlinie kann nicht gelöscht werden.
   - Sie können die Priorität der Standardrichtlinie nicht ändern (Sie wird immer zuletzt angewendet).

4. Überprüfen Sie auf der **Standardseite Richtlinie Office365 bearbeiten** die Einstellungen, und klicken Sie dann auf **Schließen**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivieren oder deaktivieren benutzerdefinierter Anti-Phishing-Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Beachten Sie den Wert in der Spalte **Status** :

   - Schieben Sie die Umschaltfläche auf **aus** , um die Richtlinie zu deaktivieren.

   - Schieben Sie die Umschaltfläche in **ein** , um die Richtlinie zu aktivieren.

Sie können die standardmäßige Anti-Phishing-Richtlinie nicht deaktivieren.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Festlegen der Priorität von benutzerdefinierten Richtlinien zum Schutz vor Phishing

Standardmäßig erhalten Anti-Phishing-Richtlinien eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Benutzerdefinierte Anti-Phishing-Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0). Die standardmäßige Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" weist den benutzerdefinierten Prioritätswert als " **niedrigste**" auf und kann nicht geändert werden.

 **Hinweis**: im Security & Compliance Center können Sie die Priorität der Anti-Phishing-Richtlinie nur ändern, nachdem Sie Sie erstellt haben. In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Anti-Phishing-Regel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften der Richtlinie auf **Priorität verbessern** oder **Priorität verringern** (die **Prioritäts** Nummer im Security & Compliance Center kann nicht direkt geändert werden). Das Ändern der Priorität einer Richtlinie ist nur dann sinnvoll, wenn Sie über mehrere Richtlinien verfügen.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Wählen Sie die Richtlinie aus, die Sie ändern möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

3. Das Flyout **Richtlinie \<name\> Bearbeiten** wird angezeigt.

   - Für die benutzerdefinierte Richtlinie zum Schutz vor Phishing mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.

   - Für die benutzerdefinierte Richtlinie zum Schutz vor Phishing mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3**) ist nur die Schaltfläche **Priorität verlängern** verfügbar.

   - Wenn Sie über drei oder mehr benutzerdefinierte Anti-Phishing-Richtlinien verfügen, stehen für Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.

4. Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Anti-Phishing-Richtlinien

1. Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Führen Sie einen der folgenden Schritte aus:

   - Wählen Sie eine benutzerdefinierte Richtlinie zum Schutz vor Phishing aus, die Sie anzeigen möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

   - Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.

3. Das Flyout zum **Bearbeiten \<name\> Ihrer Richtlinie** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von Anti-Phishing-Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Wählen Sie die Richtlinie aus, die Sie entfernen möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

3. Klicken Sie im daraufhin angezeigten Dialogfeld **Richtlinie \<name\> Bearbeiten** auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Konfigurieren von Anti-Phishing-Richtlinien mithilfe Exchange Online PowerShell

Wie bereits beschrieben, besteht eine Anti-Phishing-Richtlinie aus einer Anti-Phishing-Richtlinie und einer Anti-Phishing-Regel.

In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phishing-Richtlinien und Anti-Phishing-Regeln offensichtlich. Sie können Anti-Phishing-Richtlinien mithilfe der **\* -AntiPhishPolicy-** Cmdlets verwalten und Anti-Phishing-Regeln mithilfe der Cmdlets **\* -AntiPhishRule** verwalten.

- In PowerShell erstellen Sie zuerst die Anti-Phishing-Richtlinie, dann erstellen Sie die Anti-Phishing-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Anti-Phishing-Richtlinie und in der Anti-Phishing-Regel separat.
- Wenn Sie eine Anti-Phishing-Richtlinie aus PowerShell entfernen, wird die entsprechende Anti-Phishing-Regel nicht automatisch entfernt und umgekehrt.

> [!NOTE]
> Die folgenden PowerShell-Verfahren sind in eigenständigen EoP-Organisationen nicht verfügbar, die Exchange Online Protection PowerShell verwenden.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Verwenden von PowerShell zum Erstellen von Anti-Phishing-Richtlinien

Das Erstellen einer Anti-Phishing-Richtlinie in PowerShell ist ein zweistufiger Prozess:

1. Erstellen Sie die Anti-Phishing-Richtlinie.
2. Erstellen Sie die Anti-Phishing-Regel, die die Anti-Phishing-Richtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Anti-Phishing-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti-Phishing-Richtlinie zuweisen. Eine Anti-Phishing-Regel kann nicht mehr als einer Anti-Phishing-Richtlinie zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Anti-Phishing-Richtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-AntiPhishRule** ).
  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule** fest).

- Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu erstellen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In diesem Beispiel wird eine Anti-Phishing-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:

- Die Beschreibung lautet: Abteilungs Richtlinie für Forschung.
- Ändert die Standardaktion für Spoofing in Quarantäne.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu erstellen:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine Anti-Phishing-Regel namens "Research Department" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Anti-Phishing-Richtlinie "Research Quarantine" zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe „Research Department“.
- Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Richtlinien

Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Richtlinien anzuzeigen:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Richtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Richtlinie "Executives" zurückgegeben.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Regeln

Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Regeln anzuzeigen:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Anti-Phishing-Regeln zusammen mit den angegebenen Eigenschaften zurückgegeben.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

In diesem Beispiel werden alle Eigenschaftswerte für die Anti-Phishing-Regel namens "Contoso Executives" zurückgegeben.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien

Anders als die folgenden Elemente sind die gleichen Einstellungen verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern, als wenn Sie eine Richtlinie erstellen, wie in [Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie](#step-1-use-powershell-to-create-an-anti-phish-policy) weiter oben in diesem Artikel beschrieben.

- Der _MakeDefault_ -Schalter, der die angegebene Richtlinie in die Standardrichtlinie umwandelt (gilt für alle, immer **niedrigste** Priorität, und Sie können Sie nicht löschen) ist nur verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern.

- Sie können keine Anti-Phishing-Richtlinie umbenennen (das Cmdlet " **AntiPhishPolicy** " hat keinen Parameter " _Name_ "). Wenn Sie eine Richtlinie zum Schutz vor Phishing im Security & Compliance Center umbenennen, benennen Sie die Anti-Phishing- _Regel_ nur um.

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu ändern:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Verwenden von PowerShell zum Ändern von Anti-Phishing-Regeln

Die einzige Einstellung, die beim Ändern einer Anti-Phishing-Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Anti-Phishing-Regeln finden Sie im nächsten Abschnitt.

Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen eines Anti-Phishing-Regel](#step-2-use-powershell-to-create-an-anti-phish-rule) Abschnitts weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu ändern:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Anti-Phishing-Regeln

Durch das Aktivieren oder Deaktivieren einer Anti-Phishing-Regel in PowerShell wird die gesamte Richtlinie zum Schutz vor Phishing aktiviert oder deaktiviert (die Anti-Phishing-Regel und die zugewiesene Anti-Phishing-Richtlinie). Sie können die standardmäßige Anti-Phishing-Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" deaktiviert.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Anti-Phishing-Regeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Anti-Phishing-Regel in PowerShell festzulegen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Hinweise**:

- Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-AntiPhishRule** .

- Die standardmäßige Anti-Phishing-Richtlinie verfügt nicht über eine entsprechende Anti-Phishing-Regel, und Sie hat immer den Wert unveränderbare Priorität **niedrigste**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Verwenden von PowerShell zum Entfernen von Anti-Phishing-Richtlinien

Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Richtlinie verwenden, wird die entsprechende Anti-Phishing-Regel nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Anti-Phishing-Richtlinie namens "Marketing Department" entfernt.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Verwenden von PowerShell zum Entfernen von Anti-Phishing-Regeln

Wenn Sie PowerShell zum Entfernen einer Anti-Phishing-Regel verwenden, wird die entsprechende Anti-Phishing-Richtlinie nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Anti-Phishing-Regel namens "Marketing Department" entfernt.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um die erfolgreiche Konfiguration von Anti-Phishing-Richtlinien in Microsoft Defender für Office 365 zu überprüfen:

- Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**. Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte. Um weitere Details anzuzeigen, führen Sie einen der folgenden Schritte aus:

  - Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.
  - Klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
