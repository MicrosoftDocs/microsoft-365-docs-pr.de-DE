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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie die Antiphishingrichtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EOP)-Organisationen mit oder ohne Exchange Online-Postfächer verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c277558bad32e1926030483d202b70ae3c910315
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065392"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Konfigurieren von Anti-Phishing-Richtlinien in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer gibt es eine Standardmäßige Antiphishingrichtlinie, die eine begrenzte Anzahl von Antis spoofing-Features enthält, die standardmäßig aktiviert sind. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).

Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Organisationen mit Exchange Online-Postfächern können Antiphishingrichtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren. Eigenständige EOP-Organisationen können nur das Security & Compliance Center verwenden.

Informationen zum Erstellen und Ändern der erweiterten Antiphishingrichtlinien in Microsoft Defender für Office 365, die in Defender for Office 365 verfügbar sind, finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

Die grundlegenden Elemente einer Antiphishingrichtlinie sind:

- **Die Antiphishrichtlinie**: Gibt die zu aktivierenden oder deaktivierenden Phishingschutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.
- **Die Antiphishregel**: Gibt die Priorität und empfängerfilter (auf wen die Richtlinie angewendet wird) für eine Antiphishrichtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Security & Compliance Center verwalten:

- Wenn Sie eine Antiphishingrichtlinie erstellen, erstellen Sie tatsächlich eine Antiphishregel und die zugehörige Antiphishrichtlinie gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Antiphishingrichtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled oder disabled und Empfängerfiltern die Antiphishregel. Alle anderen Einstellungen ändern die zugeordnete Antiphishrichtlinie.
- Wenn Sie eine Antiphishingrichtlinie entfernen, werden die Antiphishregel und die zugehörige Antiphishingrichtlinie entfernt.

In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat. Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies) zum Konfigurieren von Antiphishingrichtlinien weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default mit den folgenden Eigenschaften:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, auch wenn der Richtlinie keine Antiphishregel (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität des Antiphishingschutzes zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

  Antiphishingrichtlinien können nicht in eigenständigen EOP PowerShell verwaltet werden.

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Zum Hinzufügen, Ändern und Löschen von Antiphishingrichtlinien müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** <sup>\*</sup> sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die **Rollengruppe "Nur-Ansichtsorganisationsverwaltung"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) gewährt auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.
  - <sup>\*</sup> Im Security & Compliance Center können Benutzer mit schreibgeschützten Zugriff die Einstellungen benutzerdefinierter Antiphishingrichtlinien anzeigen. Schreibgeschützte Benutzer können die Einstellungen in der Standardmäßigen Antiphishingrichtlinie nicht sehen.

- Zum Erstellen und Ändern von Antiphishingrichtlinien in eigenständigem EOP müssen Sie etwas tun, das eine _Hydratation_ für Ihren Mandanten erfordert. Beispielsweise können Sie im Exchange Admin Center (EAC) zur Registerkarte Berechtigungen wechseln,  eine vorhandene Rollengruppe auswählen, auf Bearbeiten (Symbol bearbeiten) klicken und eine Rolle entfernen (die Sie schließlich wieder  ![ ](../../media/ITPro-EAC-EditIcon.png) hinzufügen). Wenn Ihr Mandant noch nie hydratisiert wurde, erhalten Sie ein Dialogfeld namens **"Organisationseinstellungen** aktualisieren" mit einer Statusleiste, die erfolgreich abgeschlossen werden sollte. Weitere Informationen zur Hydratation finden Sie im [Cmdlet Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (das nicht in der eigenständigen EOP PowerShell oder im Security & Compliance Center verfügbar ist).

- Unsere empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).

- Es ist bis zu 30 Minuten zulässig, bis die aktualisierte Richtlinie angewendet wird.

- Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Erstellen von Antiphishingrichtlinien mithilfe & Security & Compliance Center

Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Security & Compliance Center werden die Antiphishregel und die zugehörige Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.

Wenn Sie eine Antiphishingrichtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der identifiziert, auf wen die Richtlinie angewendet wird. Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardmäßigen Antiphishingeinstellungen zu ändern oder zu überprüfen.

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.

2. Klicken Sie **auf der Seite Antiphishing** auf **Erstellen**.

3. Der **Assistent zum Erstellen einer neuen Antiphishingrichtlinie** wird geöffnet. Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Identifizieren Sie **auf der angezeigten** Seite Angewendet auf die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken **Sie auf Bedingung hinzufügen**. Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:

   - **Der Empfänger ist**: Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird ein entsprechendes Dropdownfeld mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.

   - Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Werte.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.
   - Klicken Sie zum Entfernen einzelner Einträge **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert.
   - Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen,** und wählen Sie einen verbleibenden Wert unter **Angewendet wenn aus.**

   Klicken Sie zum Hinzufügen von Ausnahmen auf **Bedingung hinzufügen,** und wählen Sie unter **Except if eine Ausnahme aus.** Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **auf der angezeigten** Seite Einstellungen überprüfen Ihre Einstellungen. Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.

   Klicken Sie nach Abschluss des Abschlusses auf **Diese Richtlinie erstellen.**

6. Klicken Sie im angezeigten Bestätigungsdialogfeld auf **OK.**

Nachdem Sie die Antiphishingrichtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, verwenden Sie die Anweisungen im nächsten Abschnitt, um die Schutzeinstellungen in der Richtlinie zu konfigurieren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Antiphishingrichtlinien

Verwenden Sie die folgenden Verfahren, um Antiphishingrichtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.

1. Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie **zu** Richtlinie zur \>  \> **Bedrohungsverwaltung Antiphishing**.

2. Wählen Sie die benutzerdefinierte Antiphishingrichtlinie aus, die Sie ändern möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

3. Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt. Durch Klicken **auf Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.

   - Die folgenden Schritte werden in der Reihenfolge dargestellt, in der die Abschnitte angezeigt werden, sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).

   - Nachdem Sie **in** einem Abschnitt auf Bearbeiten geklickt haben, werden die verfügbaren Einstellungen in einem  Assistentenformat angezeigt, Sie  können jedoch in beliebiger Reihenfolge innerhalb der Seiten springen, und Sie können auf einer beliebigen Seite auf Speichern klicken (oder  ![ ](../../media/scc-remove-icon.png) **\<name\>** Abbrechen oder Schließen schließen, um zur Seite Richtlinie bearbeiten zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder Verlassen des Assistenten besuchen).

4. **Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten,** um dieselben Einstellungen zu ändern, die beim Erstellen der Richtlinie [im](#use-the-security--compliance-center-to-create-anti-phishing-policies) vorherigen Abschnitt verfügbar waren:

   - **Name**
   - **Beschreibung**
   - **Angewendet auf**
   - **Überprüfen Der Einstellungen**

   Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.

5. **Spoof**:  Klicken Sie auf Bearbeiten, um die Spoofintelligenz ein- oder auszuschalten, die Identifikation nicht authentifizierter Absender in Outlook ein- oder auszuschalten und die Aktion so zu konfigurieren, dass sie auf Nachrichten von blockierten spoofierten Absendern angewendet wird. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).

   Beachten Sie, dass diese Einstellungen auch in Antiphishingrichtlinien in Defender for Office 365 verfügbar sind.

   - **Spoofing-Filtereinstellungen:** Der Standardwert ist **Ein**, und es wird empfohlen, ihn zu be lassen. Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**. Weitere Informationen finden Sie unter [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365 verweisen soll. Stattdessen aktivieren Sie erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Feature Nicht authentifizierter Absender aktivieren:** Der Standardwert ist **Ein**. Um es zu deaktivieren, verschieben Sie den Umschalter auf **Aus**.

   - **Aktionen**: Geben Sie die Aktion für Nachrichten an, bei der spoof intelligence fehlschlagen:

     **Wenn E-Mails von einer Person** gesendet werden, die Ihre Domäne nicht spoofen darf:

     - **Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger**
     - **Isolieren der Nachricht**

   - **Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.

     - Sie können in jedem **Abschnitt** auf Bearbeiten klicken, um zur relevanten Seite zurück zu springen.
     - Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:

       - **Aktivieren des Antispoofingschutzes**
       - **Aktivieren des Features "Nicht authentifizierter Absender"**

   Wenn Sie fertig sind, klicken Sie auf **einer beliebigen** Seite auf Speichern.

6. Überprüfen Sie auf **der Seite \<Name\>** Richtlinie bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Ändern der standardmäßigen Antiphishingrichtlinie mithilfe des Security & Compliance Center

Die Standardmäßige Antiphishingrichtlinie heißt Office365 AntiPhish Default und wird nicht in der Liste der Richtlinien angezeigt. Gehen Sie wie folgt vor, um die Standardmäßige Antiphishingrichtlinie zu ändern:

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.

2. Klicken Sie **auf der Seite Antiphishing** auf **Standardrichtlinie**.

3. Die **Seite Office365 AntiPhish Default** bearbeiten wird angezeigt. Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für das Ändern [einer benutzerdefinierten Richtlinie enthalten.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Impersonation**
   - **Spoof**
   - **Erweiterte Einstellungen**

   Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:

   - Sie können  den Abschnitt Richtlinieneinstellung und -werte  anzeigen, es gibt jedoch keinen Link Bearbeiten, sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).
   - Die Standardrichtlinie kann nicht gelöscht werden.
   - Sie können die Priorität der Standardrichtlinie nicht ändern (sie wird immer zuletzt angewendet).

4. Überprüfen Sie **auf der Seite Office365-Standardrichtlinie** bearbeiten Ihre Einstellungen, und klicken Sie dann auf **Schließen**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivieren oder Deaktivieren benutzerdefinierter Antiphishingrichtlinien

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.

2. Beachten Sie den Wert in der **Spalte Status:**

   - Verschieben Sie den Umschalter auf **Aus,** um die Richtlinie zu deaktivieren.

   - Verschieben Sie den Umschalter auf **Ein,** um die Richtlinie zu aktivieren.

Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien

Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Benutzerdefinierte Antiphishingrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0). Die Standardmäßige Antiphishingrichtlinie mit dem Namen Office365 AntiPhish Default hat den benutzerdefinierten Prioritätswert **Lowest**, und Sie können sie nicht ändern.

 **Hinweis:** Im Security & Compliance Center können Sie die Priorität der Antiphishingrichtlinie nur ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishregel erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).

Um die Priorität einer Richtlinie  zu ändern, klicken Sie **in** den Eigenschaften der Richtlinie  auf Priorität erhöhen oder Priorität verringern (Sie können die Prioritätsnummer im Security & Compliance Center nicht direkt ändern). Das Ändern der Priorität einer Richtlinie ist nur sinnvoll, wenn Sie über mehrere Richtlinien verfügen.

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing.**

2. Wählen Sie die Richtlinie aus, die Sie ändern möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

3. Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.

   - Die benutzerdefinierte Antiphishingrichtlinie mit dem **Prioritätswert** **0** verfügt nur über die **Schaltfläche Priorität** verringern.

   - Die benutzerdefinierte Antiphishingrichtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**

   - Wenn Sie über drei oder mehr benutzerdefinierte Antiphishingrichtlinien verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität** verringern zur Verfügung.

4. Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Anzeigen von Antiphishingrichtlinien mithilfe & Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing**.

2. Führen Sie einen der folgenden Schritte aus:

   - Wählen Sie eine benutzerdefinierte Antiphishingrichtlinie aus, die Sie anzeigen möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

   - Klicken **Sie auf Standardrichtlinie,** um die Standardmäßige Antiphishingrichtlinie anzeigen zu können.

3. Das **Flyout \<name\> "Richtlinie** bearbeiten" wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Entfernen von Antiphishingrichtlinien mithilfe des Security & Compliance Centers

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.

2. Wählen Sie die Richtlinie aus, die Sie entfernen möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

3. Klicken Sie **im \<name\> angezeigten** Flyout Richtlinie bearbeiten auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Konfigurieren von Antiphishingrichtlinien mithilfe von Exchange Online PowerShell

Wie bereits beschrieben, besteht eine Antiphishingrichtlinie aus einer Antiphishrichtlinie und einer Antiphishregel.

In Exchange Online PowerShell ist der Unterschied zwischen Antiphishrichtlinien und Antiphishregeln offensichtlich. Sie verwalten Antiphishrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphishregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**

- In PowerShell erstellen Sie zuerst die Antiphishrichtlinie, dann erstellen Sie die Antiphishregel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Antiphishrichtlinie und der Antiphishregel separat.
- Wenn Sie eine Antiphishrichtlinie aus PowerShell entfernen, wird die entsprechende Antiphishregel nicht automatisch entfernt und umgekehrt.

> [!NOTE]
> Die folgenden PowerShell-Verfahren sind in eigenständigen EOP-Organisationen, die Exchange Online Protection PowerShell verwenden, nicht verfügbar.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Erstellen von Antiphishingrichtlinien mithilfe von PowerShell

Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Stufen:

1. Erstellen Sie die Antiphishrichtlinie.
2. Erstellen Sie die Antiphishregel, die die Antiphishrichtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Antiphishregel erstellen und ihr eine vorhandene, nicht zugeordnete Antiphishrichtlinie zuweisen. Eine Antiphishregel kann nicht mehr als einer Antiphishrichtlinie zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Antiphishrichtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-AntiPhishRule).**
  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-AntiPhishRule.**

- Eine neue Antiphishrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Antiphishregel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Schritt 1: Erstellen einer Antiphishrichtlinie mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu erstellen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In diesem Beispiel wird eine Phishingrichtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:

- Die Beschreibung ist: Research department policy.
- Ändert die Standardaktion für Spoofing in Quarantäne.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Schritt 2: Erstellen einer Antiphishregel mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Antiphishregel zu erstellen:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine Antiphishregel namens "Research Department" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Antiphishrichtlinie "Research Quarantine" zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe „Research Department“.
- Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Anzeigen von Antiphishrichtlinien mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Antiphishrichtlinien anzeigen zu können:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishrichtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishrichtlinie "Executives" zurückgegeben.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Anzeigen von Antiphishregeln mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Antiphishregeln anzeigen zu können:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Antiphishregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.

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

In diesem Beispiel werden alle Eigenschaftswerte für die Antiphishregel namens Contoso Executives zurückgegeben.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Verwenden von PowerShell zum Ändern von Antiphishrichtlinien

Neben den folgenden Elementen sind dieselben Einstellungen verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern, als wenn Sie eine Richtlinie wie in [Schritt 1:](#step-1-use-powershell-to-create-an-anti-phish-policy) Verwenden von PowerShell beschrieben erstellen, um eine Antiphishrichtlinie weiter oben in diesem Artikel zu erstellen.

- Die _MakeDefault-Option,_ die die angegebene Richtlinie in die  Standardrichtlinie umstellt (auf alle Benutzer angewendet, immer niedrigste Priorität, und Sie können sie nicht löschen) ist nur verfügbar, wenn Sie eine Antiphishrichtlinie in PowerShell ändern.

- Sie können eine Antiphishrichtlinie nicht umbenennen (das **Cmdlet Set-AntiPhishPolicy** hat keinen _Name-Parameter)._ Wenn Sie eine Antiphishingrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Antiphishingregel _um._

Verwenden Sie die folgende Syntax, um eine Antiphishrichtlinie zu ändern:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Verwenden von PowerShell zum Ändern von Antiphishregeln

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Antiphishregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishregeln finden Sie im nächsten Abschnitt.

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt Schritt 2: Verwenden von PowerShell beschrieben, um eine [Antiphishregel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Artikel zu erstellen.

Verwenden Sie die folgende Syntax, um eine Antiphishregel zu ändern:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Antiphishregeln

Durch Aktivieren oder Deaktivieren einer Antiphishregel in PowerShell wird die gesamte Antiphishingrichtlinie (die Antiphishregel und die zugewiesene Antiphishingrichtlinie) aktiviert oder deaktiviert. Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Antiphishregel "Marketing Department" deaktiviert.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) und [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Festlegen der Priorität von Antiphishregeln mithilfe von PowerShell

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer #A0 in PowerShell zu setzen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Hinweise**:

- Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-AntiPhishRule.**

- Die Standardmäßige Antiphishrichtlinie verfügt nicht über eine entsprechende Antiphishregel und hat immer den nicht veränderbaren Prioritätswert **Lowest**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Entfernen von Antiphishrichtlinien mithilfe von PowerShell

Wenn Sie PowerShell verwenden, um eine Antiphishrichtlinie zu entfernen, wird die entsprechende Antiphishregel nicht entfernt.

Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Antiphishrichtlinie "Marketing Department" entfernt.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Entfernen von Antiphishregeln mithilfe von PowerShell

Wenn Sie PowerShell verwenden, um eine Antiphishregel zu entfernen, wird die entsprechende Antiphishrichtlinie nicht entfernt.

Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Antiphishregel "Marketing Department" entfernt.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie Antiphishingrichtlinien in Microsoft Defender für Office 365 erfolgreich konfiguriert haben:

- Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**. Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.** Gehen Sie wie folgt vor, um weitere Details anzuzeigen:

  - Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.
  - Klicken **Sie auf Standardrichtlinie,** und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```