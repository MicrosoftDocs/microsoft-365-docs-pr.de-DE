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
description: Administratoren können erfahren, wie Sie die Antiphishingrichtlinien erstellen, ändern und löschen, die in Exchange Online Protection (EOP)-Organisationen mit oder ohne Exchange Online-Postfächer verfügbar sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 052e19d811f56fe633ff0fbde79f51860a04a669
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165847"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Konfigurieren von Anti-Phishing-Richtlinien in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer gibt es eine standardmäßige Antiphishingrichtlinie, die eine begrenzte Anzahl von Standardmäßig aktivierten Antis spoofing-Funktionen enthält. Weitere Informationen finden Sie unter ["Spoofing"-Einstellungen in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#spoof-settings)

Administratoren können die standardmäßige Antiphishingrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Für eine höhere Granularität können Sie auch benutzerdefinierte Antiphishingrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Organisationen mit Exchange Online-Postfächern können Antiphishingrichtlinien im Security & Compliance Center oder in Exchange Online PowerShell konfigurieren. Eigenständige EOP-Organisationen können nur das Security & Compliance Center verwenden.

Informationen zum Erstellen und Ändern der erweiterten Antiphishingrichtlinien in Microsoft Defender für Office 365, die in Defender für Office 365 verfügbar sind, finden Sie unter Konfigurieren von [Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-atp-anti-phishing-policies.md)

Die grundlegenden Elemente einer Antiphishingrichtlinie sind:

- **Die Antiphishingrichtlinie:** Gibt die zu aktivierenden oder zu deaktivierenden Phishingschutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.
- **Die Antiphishregel:** Gibt die Prioritäts- und Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Antiphishingrichtlinien im Security & Compliance Center verwalten:

- Wenn Sie eine Antiphishingrichtlinie erstellen, erstellen Sie tatsächlich eine Antiphishingregel und die zugeordnete Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Antiphishingrichtlinie ändern, ändern Einstellungen im Zusammenhang mit Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Antiphishingregel. Alle anderen Einstellungen ändern die zugeordnete Anti-Phishing-Richtlinie.
- Wenn Sie eine Antiphishingrichtlinie entfernen, werden die Antiphishingregel und die zugehörige Antiphishingrichtlinie entfernt.

In Exchange Online PowerShell verwalten Sie die Richtlinie und die Regel separat. Weitere Informationen finden Sie im Abschnitt "Verwenden von [Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien"](#use-exchange-online-powershell-to-configure-anti-phishing-policies) weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte Antiphishingrichtlinie namens Office365 AntiPhish Default, die über die folgenden Eigenschaften verfügt:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität des Antiphishingschutzes zu erhöhen, können Sie benutzerdefinierte Antiphishingrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur **Antiphishingseite zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Antiphishingrichtlinien können in der eigenständigen EOP PowerShell nicht verwaltet werden.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Hinzufügen, Ändern und Löschen von Antiphishingrichtlinien müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf Antiphishingrichtlinien müssen  Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** <sup>\*</sup> sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die **Rollengruppe "Organisationsverwaltung nur** anzeigen" in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das <sup>\*</sup> Feature.
  - <sup>\*</sup> Im Security & Compliance Center können Benutzer mit schreibgeschützten Zugriff die Einstellungen benutzerdefinierter Antiphishingrichtlinien anzeigen. Schreibgeschützte Benutzer können die Einstellungen in der standardmäßigen Antiphishingrichtlinie nicht sehen.

- Um Antiphishingrichtlinien in EOP als eigenständige Lösung zu erstellen und zu ändern, müssen Sie etwas tun, das eine _Hydratation_ für Ihren Mandanten erfordert. In der Exchange Admin Center (EAC) können  Sie beispielsweise zur Registerkarte "Berechtigungen" wechseln, eine vorhandene Rollengruppe auswählen, auf das Symbol "Bearbeiten" klicken und eine Rolle entfernen (die Sie letztendlich wieder  ![ ](../../media/ITPro-EAC-EditIcon.png) hinzufügen). Wenn Ihr Mandant noch nie aktivieren wurde, erhalten Sie ein Dialogfeld namens "Organisationseinstellungen aktualisieren" mit einer Statusleiste, die erfolgreich abgeschlossen werden sollte.  Weitere Informationen zur Hydratation finden Sie im [Cmdlet "Enable-OrganizationCustomization"](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (das in der eigenständigen EOP PowerShell oder im Security & Compliance Center nicht verfügbar ist).

- Die empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP-Standardeinstellungen für Antiphishingrichtlinien.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

- Es kann bis zu 30 Minuten dauern, bis die aktualisierte Richtlinie angewendet wird.

- Informationen dazu, wo Antiphishingrichtlinien in der Filterpipeline angewendet werden, finden Sie unter "Reihenfolge und [Rangfolge des E-Mail-Schutzes".](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Antiphishingrichtlinien

Beim Erstellen einer benutzerdefinierten Antiphishingrichtlinie im Security & Compliance Center werden die Antiphishingregel und die zugeordnete Antiphishingrichtlinie gleichzeitig mit demselben Namen für beide erstellt.

Wenn Sie eine Antiphishingrichtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der identifiziert, auf wen die Richtlinie angewendet wird. Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die standardmäßigen Antiphishingeinstellungen zu ändern oder zu überprüfen.

1. Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**

2. Klicken Sie **auf der Seite "Antiphishing"** auf **"Erstellen".**

3. Der **Assistent zum Erstellen einer neuen Antiphishingrichtlinie wird** geöffnet. Konfigurieren Sie **auf der Seite "Ihre Richtlinie benennen"** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Identifizieren Sie **auf der angezeigten** Seite "Angewendet auf" die internen Empfänger, auf die die Richtlinie angewendet wird.

   Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).

   Klicken **Sie auf Bedingung hinzufügen**. Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet" aus, wenn:**

   - **Der Empfänger ist:** Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.
   - **Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.

   - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der auszuwählende Werte durch.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Wenn Sie weitere Werte hinzufügen möchten, klicken Sie in einen leeren Bereich des Felds.
   - Klicken Sie zum Entfernen einzelner Einträge **auf** das Symbol ![ ](../../media/scc-remove-icon.png) "Entfernen" für den Wert.
   - Um die gesamte Bedingung zu entfernen, **klicken** Sie in der Bedingung ![ auf ](../../media/scc-remove-icon.png) "Entfernen".

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf "Bedingung **hinzufügen",** und wählen Sie unter "Angewendet" einen verbleibenden Wert **aus, wenn**.

   Klicken Sie zum Hinzufügen von Ausnahmen auf **"Bedingung hinzufügen",** und wählen Sie unter "Außer wenn" **eine Ausnahme aus.** Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie **ihre Einstellungen auf** der angezeigten Seite "Einstellungen überprüfen". Sie können **in** jeder Einstellung auf "Bearbeiten" klicken, um sie zu ändern.

   Klicken Sie nach Abschluss des Abschlusses auf **"Diese Richtlinie erstellen".**

6. Klicken Sie im angezeigten Bestätigungsdialogfeld auf **"OK".**

Nachdem Sie die Antiphishingrichtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, konfigurieren Sie mithilfe der Anweisungen im nächsten Abschnitt die Schutzeinstellungen in der Richtlinie.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Antiphishingrichtlinien

Verwenden Sie die folgenden Verfahren, um Antiphishingrichtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.

1. Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu Threat **Management** \> **Policy** \> **Anti-Phishing**.

2. Wählen Sie die benutzerdefinierte Antiphishingrichtlinie aus, die Sie ändern möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

3. Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt. Wenn **Sie** in einem beliebigen Abschnitt auf "Bearbeiten" klicken, können Sie auf die Einstellungen in diesem Abschnitt zugreifen.

   - Die folgenden Schritte werden in der Reihenfolge dargestellt, in der die Abschnitte angezeigt werden, sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).

   - Nachdem Sie **in** einem Abschnitt auf "Bearbeiten" geklickt haben, werden die verfügbaren Einstellungen in  einem Assistentenformat angezeigt.  Sie können jedoch in beliebiger Reihenfolge innerhalb der Seiten wechseln, und Sie können auf einer beliebigen Seite auf "Speichern" klicken (oder  ![ ](../../media/scc-remove-icon.png) **\<name\>** auf das Symbol "Abbrechen" oder "Schließen" klicken, um zur Seite "Richtlinie bearbeiten" zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder Verlassen besuchen).

4. **Richtlinieneinstellung:** Klicken Sie auf "Bearbeiten", um dieselben Einstellungen zu ändern, die beim Erstellen der Richtlinie [im](#use-the-security--compliance-center-to-create-anti-phishing-policies) vorherigen Abschnitt verfügbar waren: 

   - **Name**
   - **Beschreibung**
   - **Angewendet auf**
   - **Überprüfen Ihrer Einstellungen**

   Wenn Sie fertig sind, klicken Sie auf einer **beliebigen** Seite auf "Speichern".

5. **Spoofing:** Klicken Sie auf "Bearbeiten", um die Spoofintelligenz zu aktivieren oder zu deaktivieren, die Identifizierung nicht authentifizierter Absender in Outlook ein- oder auszuschalten und die Aktion so zu konfigurieren, dass sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird.  Weitere Informationen finden Sie unter ["Spoofing"-Einstellungen in Antiphishingrichtlinien.](set-up-anti-phishing-policies.md#spoof-settings)

   Beachten Sie, dass dieselben Einstellungen auch in Antiphishingrichtlinien in Defender für Office 365 verfügbar sind.

   - **Spoofingfiltereinstellungen:** Der Standardwert ist **"Ein",** und es wird empfohlen, ihn zu be lassen. Um sie zu deaktivieren, ziehen Sie den Umschalter auf **"Aus".** Weitere Informationen finden Sie unter [Konfigurieren der Spoofintelligenz in EOP.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > Sie müssen den Antis spoofingschutz nicht deaktivieren, wenn Ihr #A0 nicht auf Microsoft 365 verweisen kann. stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter ["Erweiterte Filterung für Connectors in Exchange Online".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Feature "Nicht authentifizierter Absender aktivieren":** Der Standardwert ist **"On".** Um sie zu deaktivieren, ziehen Sie den Umschalter auf **"Aus".**

   - **Aktionen:** Geben Sie die Aktion an, die für Nachrichten mit Spoofingintelligenz ausführen soll:

     Wenn eine E-Mail von einer Person gesendet wird, die nicht zum **Spoofing Ihrer Domäne zugelassen ist:**

     - **Nachricht in die Junk-E-Mail-Ordner der Empfänger verschieben**
     - **Isolieren der Nachricht**

   - **Überprüfen Sie Ihre Einstellungen:** Anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.

     - Sie können in jedem Abschnitt **auf** "Bearbeiten" klicken, um zur entsprechenden Seite zurück zu wechseln.
     - Sie können die folgenden  Einstellungen  direkt auf dieser Seite ein- oder ausschalten:

       - **Aktivieren des Antispoofingschutzes**
       - **Feature "Nicht authentifizierter Absender aktivieren"**

   Wenn Sie fertig sind, klicken Sie auf einer **beliebigen** Seite auf "Speichern".

6. Überprüfen Sie auf der Seite "Richtlinie **bearbeiten" \<Name\>** Ihre Einstellungen, und klicken Sie dann auf **"Schließen".**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Ändern der standardmäßigen Antiphishingrichtlinie mithilfe des Security & Compliance Center

Die standardmäßige Antiphishingrichtlinie heißt Office365 AntiPhish Default und wird nicht in der Liste der Richtlinien angezeigt. Gehen Sie wie folgt vor, um die standardmäßige Antiphishingrichtlinie zu ändern:

1. Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**

2. Klicken Sie **auf der Seite "Antiphishing"** auf **"Standardrichtlinie".**

3. Die **Seite "Office365-Antiphish-Standard** bearbeiten" wird angezeigt. Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für das Ändern [einer benutzerdefinierten Richtlinie enthalten.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Impersonation**
   - **Spoofing**
   - **Erweiterte Einstellungen**

   Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:

   - Sie können  den Abschnitt und die Werte der  Richtlinieneinstellung anzeigen, es gibt jedoch keinen Link "Bearbeiten", sodass Sie die Einstellungen (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger) nicht ändern können.
   - Die Standardrichtlinie kann nicht gelöscht werden.
   - Sie können die Priorität der Standardrichtlinie nicht ändern (sie wird immer zuletzt angewendet).

4. Überprüfen Sie **auf der Seite "Office365-Antiphish-Standardrichtlinie** bearbeiten" Ihre Einstellungen, und klicken Sie dann auf **"Schließen".**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivieren oder Deaktivieren von benutzerdefinierten Antiphishingrichtlinien

1. Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**

2. Beachten Sie den  Wert in der Statusspalte:

   - Ziehen Sie den Umschalter auf **"Aus",** um die Richtlinie zu deaktivieren.

   - Ziehen Sie den Umschalter auf **"Ein",** um die Richtlinie zu aktivieren.

Sie können die standardmäßige Antiphishingrichtlinie nicht deaktivieren.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Festlegen der Priorität von benutzerdefinierten Antiphishingrichtlinien

Standardmäßig erhalten Antiphishingrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

Benutzerdefinierte Antiphishingrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0). Die standardmäßige Antiphishingrichtlinie namens Office365 AntiPhish Default hat den benutzerdefinierten Prioritätswert **"Niedrigste",** und Sie können ihn nicht ändern.

 **Hinweis:** Im Security & Compliance Center können Sie die Priorität der Anti-Phishing-Richtlinie erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Antiphishregel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).

Um die Priorität einer Richtlinie  zu ändern, klicken Sie **in** den Eigenschaften der Richtlinie  auf "Priorität erhöhen" oder "Priorität verringern" (Sie können die Prioritätsnummer im Security & Compliance Center nicht direkt ändern). Das Ändern der Priorität einer Richtlinie ist nur sinnvoll, wenn Sie über mehrere Richtlinien verfügen.

1. Wechseln Sie im Security & Compliance  Center zur \>  \> **Atp-Antiphishing-Richtlinie zur Bedrohungsverwaltung.**

2. Wählen Sie die Richtlinie aus, die Sie ändern möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

3. Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt.

   - Für die benutzerdefinierte Antiphishingrichtlinie mit dem **Prioritätswert** **0** ist nur die Schaltfläche "Priorität **verringern"** verfügbar.

   - Für die benutzerdefinierte Antiphishingrichtlinie mit dem niedrigsten Prioritätswert (z. B. **3)** ist nur die Schaltfläche "Priorität  **erhöhen"** verfügbar.

   - Wenn Sie über drei oder mehr benutzerdefinierte Antiphishingrichtlinien verfügen, verfügen Richtlinien  zwischen dem höchsten und dem niedrigsten Prioritätswert über die Schaltflächen "Priorität erhöhen" und **"Priorität** verringern".

4. Klicken **Sie auf "Priorität erhöhen"** oder **"Priorität verringern",** um den **Prioritätswert zu** ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Antiphishingrichtlinien

1. Wechseln Sie im Security & Compliance Center zu "Threat **management** \> **Policy** \> **Anti-phishing".**

2. Führen Sie einen der folgenden Schritte aus:

   - Wählen Sie eine benutzerdefinierte Antiphishingrichtlinie aus, die Sie anzeigen möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

   - Klicken **Sie auf "Standardrichtlinie",** um die standardmäßige Antiphishingrichtlinie anzeigen.

3. Das **Flyout \<name\> "Richtlinie bearbeiten"** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Verwenden des Security & Compliance Centers zum Entfernen von Antiphishingrichtlinien

1. Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".**

2. Wählen Sie die Richtlinie aus, die Sie entfernen möchten. Wenn sie bereits ausgewählt ist, deaktivieren Sie sie, und wählen Sie sie erneut aus.

3. Klicken Sie **im \<name\> angezeigten** Flyout "Richtlinie bearbeiten" auf "Richtlinie löschen", und klicken Sie dann **im** angezeigten Warndialogfeld auf "Ja".

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Verwenden von Exchange Online PowerShell zum Konfigurieren von Antiphishingrichtlinien

Wie zuvor beschrieben, besteht eine Antiphishingrichtlinie aus einer Antiphishingrichtlinie und einer Antiphishingregel.

In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phish-Richtlinien und Anti-Phishing-Regeln offensichtlich. Sie verwalten Antiphiishrichtlinien mithilfe der **\* -AntiPhishPolicy-Cmdlets,** und Sie verwalten Antiphiishregeln mithilfe der **\* -AntiPhishRule-Cmdlets.**

- In PowerShell erstellen Sie zuerst die Anti-Phishing-Richtlinie, dann erstellen Sie die Anti-Phish-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Anti-Phish-Richtlinie und der Anti-Phish-Regel separat.
- Wenn Sie eine Anti-Phish-Richtlinie aus PowerShell entfernen, wird die entsprechende Antiphishregel nicht automatisch entfernt und umgekehrt.

> [!NOTE]
> Die folgenden PowerShell-Verfahren sind in eigenständigen EOP-Organisationen, die Exchange Online Protection PowerShell verwenden, nicht verfügbar.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Verwenden von PowerShell zum Erstellen von Antiphishingrichtlinien

Das Erstellen einer Antiphishingrichtlinie in PowerShell besteht aus zwei Schritte:

1. Erstellen Sie die Anti-Phish-Richtlinie.
2. Erstellen Sie die Anti phish-Regel, die die Anti-Phish-Richtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Anti-Phish-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti phish-Richtlinie zuweisen. Eine Anti-Phish-Regel kann nicht mehreren Anti-Phishing-Richtlinien zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Anti-Phish-Richtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im **Cmdlet "New-AntiPhishRule").**
  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ ) für das _\<Number\>_ **Cmdlet New-AntiPhishRule)** festgelegt.

- Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie

Verwenden Sie folgende Syntax, um eine Anti-Phish-Richtlinie zu erstellen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In diesem Beispiel wird eine Anti-Phish-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:

- Die Beschreibung ist: Richtlinie der Forschungsabteilung.
- Ändert die Standardaktion für Spoofing in "Quarantäne".

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Antiphishregel

Verwenden Sie die folgende Syntax, um eine Anti phish-Regel zu erstellen:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine Antiphishregel namens "Research Department" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Anti-Phishing-Richtlinie "Research Quarantine" zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe „Research Department“.
- Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Richtlinien

Verwenden Sie die folgende Syntax, um vorhandene Anti-Phishing-Richtlinien anzeigen zu können:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Übersichtsliste aller Anti-Phishing-Richtlinien zusammen mit den angegebenen Eigenschaften zurückgegeben.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In diesem Beispiel werden alle Eigenschaftswerte für die Phishingrichtlinie "Executives" zurückgegeben.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Verwenden von PowerShell zum Anzeigen von Anti-Phishing-Regeln

Verwenden Sie die folgende Syntax, um vorhandene Antiphishregeln anzeigen zu können:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Übersichtsliste aller Antiphishregeln zusammen mit den angegebenen Eigenschaften zurückgegeben.

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

In diesem Beispiel werden alle Eigenschaftswerte für die Phishingregel "Contoso Executives" zurückgegeben.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien

Neben den folgenden Elementen stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Anti-Phish-Richtlinie in PowerShell ändern, wie beim Erstellen einer Richtlinie, wie in Schritt 1 beschrieben: Verwenden von PowerShell zum Erstellen einer [Anti-Phishing-Richtlinie](#step-1-use-powershell-to-create-an-anti-phish-policy) weiter oben in diesem Artikel.

- Die _Option MakeDefault,_ die die angegebene Richtlinie in die  Standardrichtlinie umschaltt (gilt für alle Benutzer, hat immer die niedrigste Priorität, und Sie können sie nicht löschen) ist nur verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern.

- Sie können eine Antiphiishrichtlinie nicht umbenennen (das **Cmdlet "Set-AntiPhishPolicy"** hat keinen _Parameter "Name")._ Wenn Sie eine Antiphishingrichtlinie im Security & Compliance Center umbenennen, benennen Sie nur die Antiphishingregel _um._

Verwenden Sie folgende Syntax, um eine Anti-Phish-Richtlinie zu ändern:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Verwenden von PowerShell zum Ändern von Anti-Phish-Regeln

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Anti-Phish-Regel in PowerShell ändern, ist der Parameter _"Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Antiphishregeln finden Sie im nächsten Abschnitt.

Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie in Schritt [2 beschrieben:](#step-2-use-powershell-to-create-an-anti-phish-rule) Verwenden von PowerShell zum Erstellen eines Abschnitts zur Antiphishregel weiter oben in diesem Artikel.

Verwenden Sie die folgende Syntax, um eine Anti phish-Regel zu ändern:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Anti-Phish-Regeln

Durch Aktivieren oder Deaktivieren einer Antiphishingregel in PowerShell wird die gesamte Antiphishingrichtlinie (die Antiphishingregel und die zugewiesene Antiphishingrichtlinie) aktiviert oder deaktiviert. Sie können die standardmäßige Antiphishingrichtlinie nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine #A0 in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Phishingregel "Marketing Department" deaktiviert.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-AntiPhishRule"](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) und ["Disable-AntiPhishRule".](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Anti-Phish-Regeln

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

- Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den Parameter _"Priority"_ im Cmdlet **"New-AntiPhishRule".**

- Die Standardmäßige Anti phish-Richtlinie verfügt nicht über eine entsprechende Anti-Phishing-Regel, und sie hat immer den nicht veränderbaren Prioritätswert **Niedrigste**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Verwenden von PowerShell zum Entfernen von Anti-Phishing-Richtlinien

Wenn Sie PowerShell verwenden, um eine Anti-Phish-Richtlinie zu entfernen, wird die entsprechende Anti phish-Regel nicht entfernt.

Verwenden Sie folgende Syntax, um eine #A0 in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Phishingrichtlinie "Marketing Department" entfernt.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Verwenden von PowerShell zum Entfernen von Anti-Phishing-Regeln

Wenn Sie PowerShell verwenden, um eine Anti-Phish-Regel zu entfernen, wird die entsprechende Anti-Phishing-Richtlinie nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Antiphishregel in PowerShell zu entfernen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Phishingregel "Marketing Department" entfernt.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um die erfolgreiche Konfiguration von Antiphishingrichtlinien in Microsoft Defender für Office 365 zu überprüfen:

- Wechseln Sie im Security & Compliance Center zu **"Bedrohungsverwaltungsrichtlinie** \>  \> **Antiphishing".** Überprüfen Sie die Liste der Richtlinien, deren **Statuswerte** und ihre **Prioritätswerte.** Gehen Sie wie folgt vor, um weitere Details anzuzeigen:

  - Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.
  - Klicken Sie **auf "Standardrichtlinie",** und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
