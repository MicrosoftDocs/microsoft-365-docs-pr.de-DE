---
title: Konfigurieren von Aufsichtsrichtlinien für Ihre Organisation
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: Einrichten von Aufsichts Überprüfungsrichtlinien zum Erfassen der Mitarbeiterkommunikation zur Überprüfung.
ms.openlocfilehash: dae8969598f5a71814c1b61db83341f30c0cb9d7
ms.sourcegitcommit: 8e5b799efd3ddd0eae9dd2835c3783103817fb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "37317617"
---
# <a name="configure-supervision-policies-for-your-organization"></a>Konfigurieren von Aufsichtsrichtlinien für Ihre Organisation

Verwenden Sie Aufsichtsrichtlinien zum Erfassen von Mitarbeiter Kommunikationen zur Untersuchung durch interne oder externe Bearbeiter. Weitere Informationen zum Überwachen der Kommunikation in Ihrer Organisation mithilfe von Aufsichtsrichtlinien finden Sie unter [Aufsichtsrichtlinien in Office 365](supervision-policies.md).

> [!NOTE]
> Benutzer, die von Aufsichtsrichtlinien überwacht werden, müssen über eine Microsoft 365 E5-Konformitäts Lizenz, eine Office 365 Enterprise E3-Lizenz mit dem Add-on für die erweiterte Kompatibilität verfügen oder in einem Office 365 Enterprise E5-Abonnement enthalten sein.
> Wenn Sie über keinen vorhandenen Enterprise E5-Plan verfügen und die Überwachung testen möchten, können Sie [sich für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Führen Sie die folgenden Schritte aus, um die Überwachung in Ihrer Office 365 Organisation einzurichten und zu verwenden:
  
- **Schritt 1 (optional)**: Einrichten [von Gruppen für die Überwachung](#step-1-set-up-groups-for-supervision-optional) 

    Bevor Sie mit der Überwachung beginnen, müssen Sie ermitteln, wer die Kommunikation überprüft und wer Prüfungen durchführt. Wenn Sie mit nur wenigen Benutzern beginnen möchten, um zu sehen, wie die Überwachung funktioniert, können Sie das Einrichten von Gruppen jetzt überspringen.

- **Schritt 2 (erforderlich)**: [Beaufsichtigung in Ihrer Organisation verfügbar machen](#step-2-make-supervision-available-in-your-organization-required)

    Fügen Sie sich selbst der Rollengruppe aufsichtsüberprüfung hinzu, damit Sie Richtlinien einrichten können. Jeder, dem diese Rolle zugewiesen ist, kann im Compliance Center auf die Seite " **Beaufsichtigung** " zugreifen. Wenn beschreibbar-e-Mail auf Exchange Online gehostet wird, muss jeder Prüfer über [Remote-PowerShell-Zugriff auf Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)verfügen.

- **Schritt 3 (optional)**: [Erstellen benutzerdefinierter vertraulicher Informationstypen und benutzerdefinierter Schlüsselwörter Wörterbücher](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    Wenn Sie einen benutzerdefinierten vertraulichen Infotyp oder ein benutzerdefiniertes Stichwort Wörterbuch für Ihre Aufsichtsrichtlinie benötigen, müssen Sie es vor dem Starten des Aufsichts Assistenten erstellen.

- **Schritt 4 (erforderlich)**: Einrichten [einer Aufsichtsrichtlinie](#step-4-set-up-a-supervision-policy-required)

    Sie erstellen Aufsichtsrichtlinien im Compliance Center. Diese Richtlinien definieren, welche Kommunikation in Ihrer Organisation überprüft werden muss, und gibt an, wer Prüfungen durchführt. Kommunikationen umfassen e-Mail-und Microsoft Teams-Kommunikation und Platt Form Kommunikation von Drittanbietern (wie Facebook, Twitter usw.).

- **Schritt 5 (optional)**: [Testen Ihrer Aufsichtsrichtlinie](#step-5-test-your-supervision-policy-optional)

    Testen Sie Ihre Aufsichtsrichtlinie, um sicherzustellen, dass Sie wie gewünscht funktioniert. Es ist wichtig sicherzustellen, dass Ihre Konformitäts Strategie ihre Standards erfüllt.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Schritt 1: Einrichten von Gruppen für die Beaufsichtigung (optional)

 Wenn Sie eine Aufsichtsrichtlinie erstellen, definieren Sie, wer Ihre Kommunikation überprüft hat und wer Prüfungen durchführt. In der Richtlinie verwenden Sie e-Mail-Adressen, um Personen oder Gruppen von Personen zu identifizieren. Um das Setup zu vereinfachen, können Sie Gruppen für Personen erstellen, die Ihre Kommunikation überprüft haben, sowie Gruppen für Personen, die diese Kommunikationen überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Sie möchten beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen, oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Anhand des folgenden Diagramms können Sie Gruppen in Ihrer Organisation für Aufsichtsrichtlinien konfigurieren:

| **Richtlinien Mitglied** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Beaufsichtigte Benutzer <br> Nicht überwachte Benutzer | Verteilergruppen <br> Office 365-Gruppen | Dynamische Verteilergruppen |
| Prüfer | E-Mail-aktivierte Sicherheitsgruppen  | Verteilergruppen <br> Dynamische Verteilergruppen |
  
Wenn Sie eine Office 365 Gruppe für beaufsichtigte Benutzer auswählen, überwacht die Richtlinie den Inhalt des freigegebenen Office 365 Postfachs und der Microsoft Teams-Kanäle, die der Gruppe zugeordnet sind. Wenn Sie eine Verteilerliste auswählen, überwacht die Richtlinie einzelne Benutzerpostfächer.

Um beaufsichtigte Benutzer in großen Unternehmensorganisationen zu verwalten, müssen Sie möglicherweise alle Benutzer über große Gruppen hinweg überwachen. Sie können PowerShell verwenden, um eine Verteilergruppe für eine globale Aufsichtsrichtlinie für die zugewiesene Gruppe zu konfigurieren. Auf diese Weise können Sie Tausende von Benutzern mit einer einzigen Richtlinie überwachen und die Aufsichtsrichtlinie so aktualisieren, dass neue Mitarbeiter Ihrer Organisation beitreten.

1. Erstellen Sie eine dedizierte [Verteilergruppe](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) für Ihre globale Aufsichtsrichtlinie mit den folgenden Eigenschaften: Stellen Sie sicher, dass diese Verteilergruppe nicht für andere Zwecke oder andere Office 365 Dienste verwendet wird.

    - **MemberDepartRestriction = geschlossen**. Stellt sicher, dass sich Benutzer nicht aus der Verteilergruppe entfernen können.
    - **MemberJoinRestriction = geschlossen**. Stellt sicher, dass Benutzer sich nicht der Verteilergruppe hinzufügen können.
    - **ModerationEnabled = true**. Stellt sicher, dass alle an diese Gruppe gesendeten Nachrichten genehmigungspflichtig sind und dass die Gruppe nicht zur Kommunikation außerhalb der Aufsichtsrichtlinien Konfiguration verwendet wird.

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. Wählen Sie ein nicht verwendetes [Exchange-benutzerdefiniertes Attribut](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) aus, um Benutzer nachzuverfolgen, die der Aufsichtsrichtlinie in Ihrer Organisation hinzugefügt wurden.

3. Führen Sie das folgende PowerShell-Skript nach einem regelmäßigen Zeitplan aus, um Benutzer zur Aufsichtsrichtlinie hinzuzufügen:

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Weitere Informationen zum Einrichten von Gruppen finden Sie unter:

- [Erstellen und Verwalten von Verteilergruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Übersicht über Office 365 Gruppen](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Schritt 2: Bereitstellen der Überwachung in Ihrer Organisation (erforderlich)

Um die **Überwachung** als Menüoption im Compliance Center zur Verfügung zu stellen, muss Ihnen die Rolle "Aufsichts Überprüfungs Administrator" zugewiesen sein.
  
Dazu können Sie sich selbst als Mitglied der Rollengruppe aufsichtsüberprüfung hinzufügen, oder Sie können eine Rollengruppe erstellen.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Hinzufügen von Mitgliedern zur Rollengruppe "aufsichtsüberprüfung"

1. Melden Sie [https://protection.office.com](https://protection.office.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an.

2. Wechseln Sie im Compliance Center zu **Berechtigungen**.

3. Wählen Sie die Rollengruppe **aufsichtsüberprüfung** aus, und klicken Sie dann auf das Symbol bearbeiten.

4. Fügen Sie im Abschnitt **Mitglieder** die Personen hinzu, die die Überwachung für Ihre Organisation verwalten sollen.

### <a name="create-a-new-role-group"></a>Erstellen einer neuen Rollengruppe

1. Melden Sie [https://protection.office.com](https://protection.office.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an.

2. Wechseln Sie im Compliance Center zu **Berechtigungen** , und klicken Sie dann auf**+** hinzufügen ().

3. Klicken Sie im Abschnitt **Rollen** auf Hinzufügen**+**(), und führen Sie einen Bildlauf nach unten zum **Aufsichts Überprüfungs Administrator**durch. Fügen Sie diese Rolle der Rollengruppe hinzu.

4. Fügen Sie im Abschnitt **Mitglieder** die Personen hinzu, die die Überwachung für Ihre Organisation verwalten sollen.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter [Berechtigungen im Compliance Center](../security/office-365-security/protect-against-threats.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Aktivieren des Remote-PowerShell-Zugriffs für Bearbeiter (wenn e-Mail auf Exchange Online gehostet wird)

1. Befolgten Sie die Anweisungen unter [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Schritt 3: Erstellen benutzerdefinierter vertraulicher Informationstypen und benutzerdefinierter Schlüsselwörter Wörterbücher (optional)

Um aus vorhandenen benutzerdefinierten vertraulichen Informationstypen oder benutzerdefinierten Schlüssel Wörterbüchern im Assistenten für Aufsichtsrichtlinien auswählen zu können, müssen Sie diese Elemente bei Bedarf zunächst erstellen.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Erstellen eines benutzerdefinierten Schlüsselwort Wörterbuchs/Lexikons (optional)

Verwenden Sie einen Text-Editor (wie Notepad), um eine Datei zu erstellen, die die Stichwort Begriffe enthält, die Sie in einer Aufsichtsrichtlinie überwachen möchten. Stellen Sie sicher, dass sich jeder Ausdruck in einer separaten Textreihe befindet, und speichern Sie die Datei im Format **Unicode/UTF-16 (Little Endian)** .

### <a name="create-custom-sensitive-information-types"></a>Erstellen benutzerdefinierter vertraulicher Informationstypen

1. Erstellen Sie einen neuen Typ für vertrauliche Informationen, und fügen Sie Ihr Benutzerwörterbuch im Office 365 Security #a0 Compliance Center hinzu. Navigieren Sie zu **Klassifikationen** \> **vertrauliche Informationstypen** , und führen Sie die Schritte im **Assistenten für neue vertrauliche Informationen**aus. Hier finden Sie:

    - Definieren eines Namens und einer Beschreibung für den Typ vertraulicher Informationen
    - Definieren der Nähe, Konfidenz Stufe und primärer Musterelemente
    - Importieren des Benutzerwörterbuchs als Anforderung für das entsprechende Element
    - Überprüfen der Auswahl und Erstellen des Typs für vertrauliche Informationen

    Ausführlichere Informationen finden Sie unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md) und [Erstellen eines Stichwort Wörterbuchs](create-a-keyword-dictionary.md) .

    Nachdem das Benutzerwörterbuch/das Lexikon erstellt wurde, können Sie die konfigurierten Schlüsselwörter mit dem Cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) oder hinzufügen und entfernen mithilfe des Cmdlets "Cmdlet" [festlegen-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) anzeigen.

## <a name="step-4-set-up-a-supervision-policy-required"></a>Schritt 4: Einrichten einer Aufsichtsrichtlinie (erforderlich)
  
1. Melden Sie [https://protection.office.com](https://protection.office.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an.

2. Wählen Sie im Compliance Center die Option **Beaufsichtigung**aus.
  
3. Wählen Sie **Create** aus, und führen Sie den Assistenten aus, um die Richtlinienkonfiguration einzurichten. Mithilfe des Assistenten können Sie Folgendes tun:

    - Geben Sie der Richtlinie einen Namen und eine Beschreibung.
    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl von Benutzern oder Gruppen, die Sie ausschließen möchten.
    - Definieren Sie die [Bedingungen](supervision-policies.md#ConditionalSettings)für die Aufsichtsrichtlinie. Sie können zwischen Nachrichtenadresse, Stichwort, Dateitypen und Größen Übereinstimmungsbedingungen wählen.
    - Wählen Sie aus, ob Sie vertrauliche Informationstypen einbeziehen möchten. Hier können Sie Standard-und benutzerdefinierte vertrauliche Informationstypen auswählen.
    - Wählen Sie aus, ob Sie das anstößige Sprachmodell aktivieren möchten. Dadurch wird eine ungeeignete Sprache erkannt, die im Textkörper von e-Mail-Nachrichten gesendet oder empfangen wird.
    - Definieren Sie den Prozentsatz der zu überprüfenden Kommunikation.
    - Wählen Sie die Bearbeiter für die Richtlinie aus. Bearbeiter können einzelne Benutzer oder [e-Mail-aktivierte Sicherheitsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)sein. Alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden.
    - Überprüfen Sie Ihre Richtlinienauswahl und erstellen Sie die Richtlinie.

## <a name="step-5-test-your-supervision-policy-optional"></a>Schritt 5: Testen Ihrer Aufsichtsrichtlinie (optional)

Nachdem Sie eine Aufsichtsrichtlinie erstellt haben, sollten Sie testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß erzwungen werden. Möglicherweise möchten Sie auch [die DLP-Richtlinien (Data Loss Prevention) testen](create-test-tune-dlp-policy.md) , wenn Ihre Überwachungsrichtlinien vertrauliche Informationstypen enthalten. Führen Sie die folgenden Schritte aus, um Ihre Aufsichtsrichtlinie zu testen:

1. Öffnen Sie einen e-Mail-Client oder Microsoft Teams, der als überwachten Benutzer angemeldet ist, der in der Richtlinie definiert ist, die Sie testen möchten.
2. Senden Sie eine e-Mail oder einen Microsoft Teams-Chat, die die Kriterien erfüllen, die Sie in der Aufsichtsrichtlinie definiert haben. Hierbei kann es sich um ein Stichwort, eine Anlagegröße, eine Domäne usw. handeln. Stellen Sie sicher, dass Sie feststellen, ob die konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu nachsichtig sind.

    > [!NOTE]
    > E-Mails, die bestimmten Richtlinien unterliegen, werden nahezu in Echtzeit verarbeitet und können unmittelbar nach der Konfiguration der Richtlinie getestet werden. Chats in Microsoft Teams können bis zu 24 Stunden in Anspruch nehmen, um eine Richtlinie vollständig zu verarbeiten. 

3. Melden Sie sich bei Ihrem Office 365-Mandanten als Prüfer an, der in der Aufsichtsrichtlinie angegeben ist. Navigieren Sie zu **Beaufsichtigung** > *Ihre benutzerdefinierte Richtlinie* > **geöffnet** , um den Bericht für die Richtlinie anzuzeigen.

## <a name="powershell-reference"></a>PowerShell-Referenz

Bei Bedarf können Sie Aufsichtsrichtlinien mit den folgenden PowerShell-Cmdlets erstellen und verwalten:

- [New-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [Gruppe-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [Remove-SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [New-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [Gruppe-SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get-SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get-SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
