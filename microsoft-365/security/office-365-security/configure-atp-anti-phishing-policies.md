---
title: Konfigurieren der ATP Antiphishing-Richtlinien
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die erweiterten Anti-Phishing-Richtlinien erstellen, ändern und löschen, die in Organisationen mit Office 365 Advanced Threat Protection (ATP) verfügbar sind.
ms.openlocfilehash: b0316133c90837bedc657bde355f31d50ffe76ea
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537461"
---
# <a name="configure-atp-anti-phishing-policies-in-office-365"></a>Konfigurieren von Richtlinien für die ATP-Anti-Phishing in Office 365

ATP-Anti-Phishing-Richtlinien sind Teil [Office 365 Advanced Threat Protection](office-365-atp.md). Durch ATP-Richtlinien zum Schutz vor Phishing können Sie Ihre Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Arten von Phishing-Angriffen schützen. Weitere Informationen zu den Unterschieden zwischen Anti-Phishing-Richtlinien in Exchange Online Protection (EoP) und ATP Anti-Phishing Policies finden Sie unter [Anti-Phishing Protection in Office 365](anti-phishing-protection.md).

Administratoren können die standardmäßige ATP-Anti-Phishing-Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen). Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte ATP-Anti-Phishing-Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Sie können ATP-Anti-Phishing-Richtlinien im Office 365 Security & Compliance Center oder in Exchange Online PowerShell konfigurieren.

Informationen zum Konfigurieren der eingeschränkten integrierten Anti-Phishing-Richtlinie, die in Exchange Online Schutzorganisationen verfügbar ist (also Office 365 Organisationen ohne ATP), finden Sie unter [configure the default Anti-Phishing Policy in EoP](configure-anti-phishing-policies-eop.md).

## <a name="atp-anti-phishing-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell"></a>ATP-Richtlinien zum Schutz vor Phishing im Office 365 Security & Compliance Center vs Exchange Online PowerShell

Die grundlegenden Elemente einer ATP-Anti-Phishing-Richtlinie sind:

- **Die Anti-Phishing-Richtlinie**: gibt die zu aktivierenden oder zu deaktivierenden Phishing-Schutzmaßnahmen sowie die Aktionen zum Anwenden von Optionen an.

- **Die Anti-Phishing-Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Anti-Phishing-Richtlinie an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für die ATP-Anti-Phishing im Security & Compliance Center verwalten:

- Wenn Sie eine ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center erstellen, erstellen Sie tatsächlich eine Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide.

- Wenn Sie eine ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Anti-Phishing-Regel. Alle anderen Einstellungen ändern die zugehörige Anti-Phishing-Richtlinie.

- Wenn Sie eine ATP-Richtlinie zum Schutz vor Phishing aus dem Security & Compliance Center entfernen, werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie entfernt.

In Exchange Online PowerShell ist der Unterschied zwischen Anti-Phishing-Richtlinien und Anti-Phishing-Regeln offensichtlich. Sie können Anti-Phishing-Richtlinien mithilfe der ** \*-AntiPhishPolicy-** Cmdlets verwalten und Anti-Phishing-Regeln mithilfe der ** \*Cmdlets-AntiPhishRule** verwalten.

- In PowerShell erstellen Sie zuerst die Anti-Phishing-Richtlinie, dann erstellen Sie die Anti-Phishing-Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.

- In PowerShell ändern Sie die Einstellungen in der Anti-Phishing-Richtlinie und in der Anti-Phishing-Regel separat.

- Wenn Sie eine Anti-Phishing-Richtlinie aus PowerShell entfernen, wird die entsprechende Anti-Phishing-Regel nicht automatisch entfernt und umgekehrt.

### <a name="default-atp-anti-phishing-policy"></a>Standardmäßige ATP-Anti-Phishing-Richtlinie

Jede ATP-Organisation verfügt über eine integrierte ATP-Richtlinie zum Schutz vor Phishing mit dem Namen "Office365 AntiPhishing default", die die folgenden Eigenschaften aufweist:

- Die Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Anti-Phishing-Regel (Empfängerfilter) zugeordnet ist.

- Die Richtlinie mit dem Namen Office365 AntiPhishing default weist den benutzerdefinierten Prioritätswert auf **niedrigster** Bedeutung auf, den Sie nicht ändern können (die Richtlinie wird immer zuletzt angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität als die Richtlinie mit dem Namen Office365 AntiPhishing default.

- Die Richtlinie mit dem Namen Office365 AntiPhishing Default ist die Standardrichtlinie (die **IsDefault** - `True`Eigenschaft hat den Wert), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität des Anti-Phishing-Schutzes zu verbessern, können Sie benutzerdefinierte ATP-Anti-Phishing-Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite " **ATP-AntiPhishing** " zu wechseln, <https://protection.office.com/antiphishing>verwenden Sie.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Zum Hinzufügen, ändern und Löschen von Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Für den schreibgeschützten Zugriff auf Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppe **Sicherheits Leser** sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Unsere empfohlenen Einstellungen für ATP-AntiPhishing-Richtlinien finden Sie unter Einstellungen für Anti-Phishing-Richtlinien für [Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).

- Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection in Office 365](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für die ATP-Anti-Phishing

Durch das Erstellen einer benutzerdefinierten ATP-Richtlinie zum Schutz vor Phishing im Security & Compliance Center werden die Anti-Phishing-Regel und die zugehörige Anti-Phishing-Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.

Wenn Sie eine ATP-Anti-Phishing-Richtlinie erstellen, können Sie nur den Richtliniennamen, die Beschreibung und den Empfängerfilter angeben, der angibt, für wen die Richtlinie gilt. Nachdem Sie die Richtlinie erstellt haben, können Sie die Richtlinie ändern, um die Standardeinstellungen für AntiPhishing zu ändern oder zu überprüfen.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

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
   - **Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Office 365 an.

   Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.

   - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.
   - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.
   - Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.
   - Wenn Sie einzelne Einträge entfernen möchten **Remove** ![, klicken Sie](../../media/scc-remove-icon.png) auf entfernen-Symbol für den Wert entfernen.
   - Wenn Sie die gesamte Bedingung entfernen möchten **, klicken** ![Sie](../../media/scc-remove-icon.png) in der Bedingung auf entfernen-Symbol entfernen.

   Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei**aus.

   Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if**eine Ausnahme aus. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen. Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.

   Wenn Sie fertig sind, klicken Sie auf **Diese Richtlinie erstellen**.

6. Klicken Sie im Bestätigungsdialogfeld, das angezeigt wird, auf **OK** .

Nachdem Sie die ATP-Anti-Phishing-Richtlinie mit diesen allgemeinen Richtlinieneinstellungen erstellt haben, konfigurieren Sie die Schutzeinstellungen in der Richtlinie mithilfe der Anweisungen im nächsten Abschnitt.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Ändern von ATP-Anti-Phishing-Richtlinien

Verwenden Sie die folgenden Verfahren, um ATP-AntiPhishing-Richtlinien zu ändern: eine neue Richtlinie, die Sie erstellt haben, oder vorhandene Richtlinien, die Sie bereits angepasst haben.

1. Wenn Sie noch nicht vorhanden sind, öffnen Sie das Security & Compliance Center, und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Wählen Sie die benutzerdefinierte ATP-Anti-Phishing-Richtlinie aus, die Sie ändern möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

3. Das Flyout zum **Bearbeiten \<Ihres\> Richtlinien namens** wird angezeigt. Durch Klicken auf **Bearbeiten** in einem beliebigen Abschnitt erhalten Sie Zugriff auf die Einstellungen in diesem Abschnitt.

   - Die folgenden Schritte werden in der Reihenfolge angezeigt, in der die Abschnitte dargestellt werden, Sie sind jedoch nicht sequenziell (Sie können die Abschnitte in beliebiger Reihenfolge auswählen und ändern).

   - Nachdem Sie in einem Abschnitt auf **Bearbeiten** klicken, werden die verfügbaren Einstellungen in einem Assistenten Format angezeigt, Sie können jedoch in beliebiger Reihenfolge innerhalb der Seiten springen, und Sie können auf einer beliebigen Seite auf **Speichern** (oder](../../media/scc-remove-icon.png) **Abbrechen** **oder schließen** ![schließen) klicken, um zur Seite **Bearbeiten der Richtlinien \<Namen\> ** zurückzukehren (Sie müssen nicht die letzte Seite des Assistenten zum Speichern oder verlassen besuchen).

4. **Richtlinieneinstellung**: Klicken Sie auf **Bearbeiten** , um dieselben Einstellungen zu ändern, die beim [Erstellen der Richtlinie](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) im vorherigen Abschnitt verfügbar waren:

   - **Name**
   - **Beschreibung**
   - **Angewendet auf**
   - **Überprüfen der Einstellungen**

   Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

5. **Identitätswechsel**: Klicken Sie auf **Bearbeiten** , um die geschützten Absender und geschützten Domänen in der Richtlinie zu ändern. Diese Einstellungen sind eine Bedingung für die Richtlinie, die gefälschte Absender identifiziert, die in der von-Adresse eingehende Nachrichten (einzeln oder nach Domäne) suchen. Weitere Informationen finden Sie unter [Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).

   - **Hinzufügen von Benutzern zu Protect**: der Standardwert ist **Off**. Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**, und klicken Sie dann auf die Schaltfläche **Benutzer hinzufügen** , die angezeigt wird.

     Konfigurieren Sie im angezeigten **Benutzer Flyout hinzufügen** die folgenden Werte:

     - **E-Mail-Adresse**:

        - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der Benutzer aus, die Sie auswählen möchten.
        - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.
        - Wenn Sie einen Eintrag entfernen möchten **Remove** ![, klicken Sie](../../media/scc-remove-icon.png) auf entfernen-Symbol für den Benutzer entfernen.

     - **Name**: dieser Wert wird basierend auf der e-Mail-Adresse aufgefüllt, die Sie ausgewählt haben, aber Sie können ihn ändern.

     Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

    Um einen vorhandenen Eintrag zu bearbeiten, wählen Sie den geschützten Benutzer in der Liste aus.

   - **Hinzufügen von Domänen zu Protect**: Konfigurieren Sie eine oder beide der folgenden Einstellungen:

     - **Automatisches einschließen der Domänen, die ich besitze**: der Standardwert ist **Off**. Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.
     - **Benutzerdefinierte Domänen einschließen**: der Standardwert ist **Off**. Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**, und geben Sie im Feld **Domänen hinzufügen** den Domänennamen ein (beispielsweise contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.

   - **Aktionen**: Klicken Sie auf **Bearbeiten**

     - **Wenn e-Mail von einem imitierten Benutzer gesendet wird**: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen der gefälschte Absender einer der geschützten Benutzer ist, die Sie in **Add users to Protect**angegeben haben:

       - **Keine Aktion anwenden**
       - **Weiterleiten von Nachrichten an andere e-Mail-Adressen**
       - **Nachricht in Junk-E-Mail-Ordner verschieben**
       - **Nachricht isolieren**
       - **Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**
       - **Löschen der Nachricht vor der Zustellung**

     - **Wenn e-Mail von einer imitierten Domäne gesendet wird**: Konfigurieren Sie eine der folgenden Aktionen für Nachrichten, bei denen sich der gefälschte Absender in einer der geschützten Domänen befindet, die Sie in **Add Domains to Protect**angegeben haben:

     - **Keine Aktion anwenden**
     - **Weiterleiten von Nachrichten an andere e-Mail-Adressen**
     - **Nachricht in Junk-E-Mail-Ordner verschieben**
     - **Nachricht isolieren**
     - **Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**
     - **Löschen der Nachricht vor der Zustellung**

   - Klicken Sie auf **Identitätswechsel-Sicherheitstipps einschalten** , und konfigurieren Sie die folgenden Einstellungen:

     - **Tipp für imitierte Benutzer anzeigen**: der Standardwert ist **Off**. Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.
     - **Tipp für imitierte Domänen anzeigen**: der Standardwert ist **Off**. Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.
     - **Tipp für ungewöhnliche Zeichen anzeigen**: der Standardwert ist **Off**. Um Sie zu aktivieren, schieben Sie die Umschaltfläche auf **ein**.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Post Fach Intelligenz**:

     - **Mailbox Intelligence aktivieren?**: der Standardwert ist **on**. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.

     - **Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes?**: Diese Einstellung ist nur verfügbar, wenn **Mailbox Intelligence aktivieren** aktiviert **ist.**

       **Wenn e-Mails von einem imitierten Benutzer gesendet**werden, können Sie eine der folgenden Aktionen für Nachrichten, die nicht die Post Fach Intelligenz ausführen (dieselben Aktionen, die für geschützte Benutzer und geschützte Domänen zur Verfügung stehen) angeben:

       - **Keine Aktion anwenden**
       - **Weiterleiten von Nachrichten an andere e-Mail-Adressen**
       - **Nachricht in Junk-E-Mail-Ordner verschieben**
       - **Nachricht isolieren**
       - **Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile**
       - **Löschen der Nachricht vor der Zustellung**

   - **Hinzufügen von vertrauenswürdigen Absendern und Domänen**: Angeben von Ausnahmen für die Richtlinie:

     - **Vertrauenswürdige Absender**:

       - Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der Benutzer aus, die Sie auswählen möchten.
       - Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Benutzer auszuwählen.
       - Wenn Sie einen Eintrag entfernen möchten **Remove** ![, klicken Sie](../../media/scc-remove-icon.png) auf entfernen-Symbol für den Benutzer entfernen.

     - **Vertrauenswürdige Domänen**: Geben Sie den Domänennamen ein (beispielsweise contoso.com), drücken Sie die EINGABETASTE, und wiederholen Sie den Vorgang bei Bedarf.

   - **Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.

     - Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.
     - Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :

       - **Geschützte Benutzer**
       - **Geschützte Domänen** \> **umfassen Domänen, die ich besitze**
       - Geschützte Domänen **geschützte** Domänen (benutzerdefinierte Domänen) **Protected domains** \>
       - **Mailbox Intelligence**

   Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

6. **Spoof**: Klicken Sie auf **Bearbeiten** , um Spoof Intelligence ein-oder auszuschalten, die nicht authentifizierte Absender Identifikation in Outlook ein-oder auszuschalten und die Aktion so zu konfigurieren, dass Sie auf Nachrichten von blockierten gefälschten Absendern angewendet wird. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

   Beachten Sie, dass diese Einstellungen mit den Einstellungen identisch sind, die in der standardmäßigen Anti-Phishing-Richtlinie in EoP verfügbar sind.

   - **Spoofing-Filtereinstellungen**: der Standardwert ist " **on**", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**. Weitere Informationen finden Sie unter [configure Spoof Intelligence in Office 365](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Office 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - Nicht **authentifizierte Absender Funktion aktivieren**: der Standardwert ist **on**. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.

   - **Actions: geben**Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:

     **Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen**:

     - **Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern**
     - **Nachricht isolieren**

   - **Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.

     - Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.
     - Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :

       - **Aktivieren von Schutz vor Spoofing**
       - **Nicht authentifizierte Absender Funktion aktivieren**

   Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

7. **Erweiterte Einstellungen**: Klicken Sie auf **Bearbeiten** , um die erweiterten Phishing-Schwellenwerte zu konfigurieren. Weitere Informationen finden Sie unter [Advanced Phishing Thresholds in ATP Anti-Phishing Policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).

   - **Erweiterte Phishing-Schwellen**Werte: Wählen Sie einen der folgenden Werte aus:

   - **1-Standard** (Dies ist der Standardwert.)
   - **2-aggressiv**
   - **3-aggressiver**
   - **4-aggressiv**

   - **Überprüfen Sie Ihre Einstellungen**: Klicken Sie auf **Bearbeiten** , um zurück zur Seite **erweiterte Phishing-Schwellenwerte** zu wechseln.

   Wenn Sie fertig sind, klicken Sie auf einer der Seiten auf **Speichern** .

8. Überprüfen Sie die Einstellungen auf der Seite **Richtlinien \<\> Namen bearbeiten** , und klicken Sie dann auf **Schließen**.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Verwenden Sie das Security & Compliance Center, um die standardmäßige ATP-Anti-Phishing-Richtlinie zu ändern.

Die standardmäßige ATP-Anti-Phishing-Richtlinie heißt Office365 AntiPhishing default und wird nicht in der Liste der Richtlinien angezeigt. Führen Sie die folgenden Schritte aus, um die standardmäßige ATP-Anti-Phishing-Richtlinie zu ändern:

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie**.

3. Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt. Die folgenden Abschnitte sind verfügbar, die identische Einstellungen für beim [Ändern einer benutzerdefinierten Richtlinie](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)enthalten:

   - **Impersonation**
   - **Spoofing**
   - **Erweiterte Einstellungen**

   Die folgenden Einstellungen sind nicht verfügbar, wenn Sie die Standardrichtlinie ändern:

   - Sie können den Abschnitt mit den **Richtlinieneinstellungen** und die Werte anzeigen, es gibt jedoch keinen Link **Bearbeiten** , sodass Sie die Einstellungen nicht ändern können (Richtlinienname, Beschreibung und für wen die Richtlinie gilt (gilt für alle Empfänger)).
   - Die Standardrichtlinie kann nicht gelöscht werden.
   - Sie können die Priorität der Standardrichtlinie nicht ändern (Sie wird immer zuletzt angewendet).

4. Überprüfen Sie auf der **Standardseite Richtlinie Office365 bearbeiten** die Einstellungen, und klicken Sie dann auf **Schließen**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Aktivieren oder Deaktivieren von benutzerdefinierten ATP-Anti-Phishing-Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Beachten Sie den Wert in der Spalte **Status** :

   - Schieben Sie die Umschaltfläche auf **aus** , um die Richtlinie zu deaktivieren.

   - Schieben Sie die Umschaltfläche in **ein** , um die Richtlinie zu aktivieren.

Sie können die standardmäßige Anti-Phishing-Richtlinie nicht deaktivieren.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>Festlegen der Priorität von benutzerdefinierten ATP-Anti-Phishing-Richtlinien

Standardmäßig erhalten Richtlinien für ATP-AntiPhishing eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Zwei Richtlinien können nicht dieselbe Priorität haben.

Benutzerdefinierte ATP-Anti-Phishing-Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0). Die standardmäßige Anti-Phishing-Richtlinie mit dem Namen "Office365 AntiPhishing default" weist den benutzerdefinierten Prioritätswert als " **niedrigste**" auf und kann nicht geändert werden.

 **Hinweis**: im Security & Compliance Center können Sie die Priorität der ATP-Anti-Phishing-Richtlinie nur ändern, nachdem Sie Sie erstellt haben. In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Anti-Phishing-Regel erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften der Richtlinie auf **Priorität verbessern** oder **Priorität verringern** (die **Prioritäts** Nummer im Security & Compliance Center kann nicht direkt geändert werden). Das Ändern der Priorität einer Richtlinie ist nur dann sinnvoll, wenn Sie über mehrere Richtlinien verfügen.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Wählen Sie die Richtlinie aus, die Sie ändern möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

3. Das Flyout zum **Bearbeiten \<Ihres\> Richtlinien namens** wird angezeigt.

   - Die benutzerdefinierte ATP-Anti-Phishing-Richtlinie mit dem **Prioritäts** Wert **0** hat nur die Schaltfläche **Priorität verringern** verfügbar.

   - Die benutzerdefinierte ATP-Anti-Phishing-Richtlinie mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3**) hat nur die Schaltfläche " **Priorität verlängern** " zur Verfügung.

   - Wenn Sie über drei oder mehr benutzerdefinierte Anti-Phishing-Richtlinien verfügen, stehen für Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.

4. Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.

5. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für die ATP-Anti-Phishing

1. Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Führen Sie einen der folgenden Schritte aus:

   - Wählen Sie eine benutzerdefinierte ATP-Anti-Phishing-Richtlinie aus, die Sie anzeigen möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

   - Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.

3. Das Flyout zum **Bearbeiten \<Ihres\> Richtlinien namens** wird angezeigt, in dem Sie die Einstellungen und Werte anzeigen können.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von ATP-Anti-Phishing-Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Wählen Sie die Richtlinie aus, die Sie entfernen möchten. Wenn es bereits ausgewählt ist, deaktivieren Sie es, und wählen Sie es erneut aus.

3. Klicken Sie im angezeigten Dropdown-Dialogfeld ** \<Richtliniennamen\> bearbeiten** auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Konfigurieren von Richtlinien für die ATP-Anti-Phishing mithilfe Exchange Online PowerShell

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Verwenden von PowerShell zum Erstellen von Anti-Phishing-Richtlinien

Das Erstellen einer Anti-Phishing-Richtlinie in PowerShell ist ein zweistufiger Prozess:

1. Erstellen Sie die Anti-Phishing-Richtlinie.

2. Erstellen Sie die Anti-Phishing-Regel, die die Anti-Phishing-Richtlinie angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Anti-Phishing-Regel erstellen und ihr eine vorhandene, nicht zugeordnete Anti-Phishing-Richtlinie zuweisen. Eine Anti-Phishing-Regel kann nicht mehr als einer Anti-Phishing-Richtlinie zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Anti-Phishing-Richtlinien in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ `$false` im Cmdlet **New-AntiPhishRule** ).

  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Prioritäts_ _ \<Nummer\>_) für das Cmdlet **New-AntiPhishRule** fest.

- Eine neue Anti-Phishing-Richtlinie, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Anti-Phishing-Regel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Richtlinie

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu erstellen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird die Anti-Phishing-Richtlinie mit dem Namen "Research Quarantine" mit den folgenden Einstellungen erstellt:

- Die Richtlinie ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert `$true`ist).
- Die Beschreibung lautet: Abteilungs Richtlinie für Forschung.
- Aktiviert den Schutz von Organisationsdomänen für alle akzeptierten Domänen und den Schutz von Zieldomänen für fabrikam.com.
- Gibt Mai Fujito (mfujito@fabrikam.com) als Benutzer an, der vor Identitätswechsel geschützt werden soll.
- Aktiviert Post Fach Intelligenz.
- Aktiviert den Nachrichtenschutz für Postfächer und gibt die Quarantäneaktion an.
- Aktiviert Sicherheitstipps.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Default monitoring policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Verwenden von PowerShell zum Ändern von Anti-Phishing-Richtlinien

Anders als die folgenden Elemente sind die gleichen Einstellungen verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu AntiPhishing-Richt](#step-1-use-powershell-to-create-an-anti-phish-policy) Linien weiter oben in diesem Thema ändern.

- Der _MakeDefault_ -Schalter, der die angegebene Richtlinie in die Standardrichtlinie umwandelt (gilt für alle, immer **niedrigste** Priorität, und Sie können Sie nicht löschen) ist nur verfügbar, wenn Sie eine Anti-Phishing-Richtlinie in PowerShell ändern.

- Sie können keine Anti-Phishing-Richtlinie umbenennen (das Cmdlet " **AntiPhishPolicy** " hat keinen Parameter " _Name_ "). Wenn Sie eine Richtlinie zum Schutz vor Phishing im Security & Compliance Center umbenennen, benennen Sie die Anti-Phishing- _Regel_nur um.

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Richtlinie zu ändern:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Verwenden von PowerShell zum Ändern von Anti-Phishing-Regeln

Die einzige Einstellung, die beim Ändern einer Anti-Phishing-Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Anti-Phishing-Regeln finden Sie im nächsten Abschnitt.

Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine Anti-Phishing-Regel in PowerShell ändern. Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Anti-Phishing-Regel](#step-2-use-powershell-to-create-an-anti-phish-rule) weiter oben in diesem Thema beschrieben.

Verwenden Sie die folgende Syntax, um eine Anti-Phishing-Regel zu ändern:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) und [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die Richtlinien für ATP-Phishing erfolgreich konfiguriert haben:

- Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**. Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte. Um weitere Details anzuzeigen, führen Sie einen der folgenden Schritte aus:

  - Wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.
  - Klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.

- Ersetzen \<Sie in Exchange Online PowerShell Name\> durch den Namen der Richtlinie oder Regel, und führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
