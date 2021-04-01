---
title: Erste Schritte mit der Kommunikationscompliance
description: Richten Sie Richtlinien für die Kommunikationskonformität ein, um die Benutzerkommunikation zur Überprüfung zu konfigurieren.
f1.keywords:
- NOCSH
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: e4dcbeeda50c6229935bae8003d8db129d852451
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488202"
---
# <a name="get-started-with-communication-compliance"></a>Erste Schritte mit der Kommunikationscompliance

Verwenden Sie Kommunikationskonformitätsrichtlinien, um die Benutzerkommunikation für die Prüfung durch interne oder externe Prüfer zu identifizieren. Weitere Informationen dazu, wie Kommunikationskonformitätsrichtlinien Ihnen bei der Überwachung der Kommunikation in Ihrer Organisation helfen können, finden Sie unter Kommunikationskonformitätsrichtlinien [in Microsoft 365](communication-compliance.md). Wenn Sie überprüfen möchten, wie Contoso schnell eine Kommunikationskonformitätsrichtlinie für die Überwachung auf anstößige Sprache in Microsoft Teams, Exchange Online und Yammer konfiguriert hat, lesen Sie diese [Fallstudie](communication-compliance-case-study.md).

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzierung

Bevor Sie mit der Kommunikationskonformität beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Für den Zugriff auf und die Verwendung der Kommunikationskonformität muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 E3-Abonnement + Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3-Abonnement + Das Microsoft 365 E5 Insider Risk Management-Add-On
- Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 A3-Abonnement + Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Insider Risk Management-Add-On
- Microsoft 365 G5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 G5-Abonnement + Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 G5-Abonnement + Das Microsoft 365 G5 Insider Risk Management-Add-On
- Office 365 Enterprise E5-Abonnement (kostenpflichtig oder Testversion)
- Office 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (nicht mehr verfügbar für neue Abonnements, siehe Hinweis)

Benutzern, die in Kommunikationskonformitätsrichtlinien enthalten sind, muss eine der oben genannten Lizenzen zugewiesen werden.

>[!IMPORTANT]
>Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements überwechseln, die die gleichen oder zusätzlichen Compliancefeatures enthalten.

Wenn Sie nicht über einen vorhandenen Office 365 Enterprise E5-Plan verfügen und die Kommunikationskonformität [](https://www.microsoft.com/microsoft-365/enterprise) testen möchten, können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Office 365 Enterprise E5 registrieren.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Schritt 1 (erforderlich): Aktivieren von Berechtigungen für die Kommunikationskonformität

>[!Important]
>Standardmäßig haben globale Administratoren keinen Zugriff auf Kommunikationskonformitätsfeatures. Die in diesem Schritt zugewiesenen Rollen sind erforderlich, bevor auf Kommunikationskonformitätsfeatures zugegriffen werden kann. Nach dem Konfigurieren Ihrer Rollengruppen kann es bis zu 30 Minuten dauern, bis die Rollengruppenberechtigungen auf zugewiesene Benutzer in Ihrer Organisation angewendet werden.

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationskonformitätsfeatures verwendet werden. Um die **Kommunikationskonformität** als Menüoption im Microsoft 365 Compliance Center verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, müssen Sie den Rollengruppen *Kommunikationskonformität* oder Kommunikationskonformität *administrator* zugewiesen werden. Um nach der Erstkonfiguration auf Kommunikationskonformitätsfeatures zu zugreifen und diese zu verwalten, müssen Benutzer Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.

Je nachdem, wie Sie Kommunikationsrichtlinien und Warnungen verwalten möchten, müssen Sie Benutzer bestimmten Rollengruppen zuweisen. Sie haben die Möglichkeit, Bestimmten Rollengruppen Benutzer mit unterschiedlichen Compliance-Verantwortlichkeiten zuzuordnen, um verschiedene Bereiche von Kommunikations-Compliance-Features zu verwalten. Sie können auch alle Benutzerkonten für designierte Administratoren, Analysten, Ermittler  und Betrachter der Rollengruppe Kommunikationskonformität zuweisen. Verwenden Sie eine einzelne Rollengruppe oder mehrere Rollengruppen, um Ihre Anforderungen an die Complianceverwaltung optimal zu erfüllen.

Wählen Sie beim Konfigurieren der Kommunikationskonformität aus den folgenden Rollengruppenoptionen aus:

| Rolle | Rollenberechtigungen |
|:-----|:-----|
| **Kommunikationskonformität** | Verwenden Sie diese Rollengruppe, um die Kommunikationskonformität für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Viewer können Sie Berechtigungen für die Kommunikationskonformität in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationskonformität. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationskonformität zu beginnen und ist für Organisationen geeignet, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikations-Compliance-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationskonformität zu konfigurieren und später Administratoren der Kommunikationskonformität in eine definierte Gruppe zu trennen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Kommunikationskonformitätsrichtlinien, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Benachrichtigungen anzeigen. |
| **Communication Compliance Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Kommunikations-Compliance-Analysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, an denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten (nicht Nachrichteninhalte) anzeigen, an zusätzliche Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht auflösen. |
| **Kommunikations-Compliance-Prüfer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Ermittler für die Kommunikationskonformität fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und -inhalte anzeigen, an zusätzliche Prüfer eskalieren, zu einem Erweiterten eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Communication Compliance Viewer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Homepage der Kommunikationskonformität auf alle Berichts-Widgets zugreifen und alle Berichte zur Kommunikationskonformität anzeigen. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Option 1: Zuweisen aller Compliancebenutzer zur Rollengruppe "Kommunikationskonformität"

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie die *Rollengruppe* Kommunikationskonformität aus, und wählen Sie **dann Rollengruppe bearbeiten aus.**

4. Wählen **Sie im** linken Navigationsbereich Mitglieder auswählen aus, und wählen Sie dann Bearbeiten **aus.**

5. Wählen **Sie Hinzufügen** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe Kommunikationskonformität hinzufügen möchten. 

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen **Sie Speichern** aus, um die Benutzer zur Rollengruppe hinzuzufügen. Wählen **Sie Schließen** aus, um die Schritte zu ausführen.

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Option 2: Zuweisen von Benutzern zu bestimmten Rollengruppen für die Kommunikationskonformität

Verwenden Sie diese Option, um Benutzer bestimmten Rollengruppen zuzuordnen, um den Zugriff auf die Kommunikationskonformität und die Verantwortlichkeiten zwischen verschiedenen Benutzern in Ihrer Organisation zu segmentieren.

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie eine der Rollengruppen für die Kommunikationskonformität aus, und wählen Sie **dann Rollengruppe bearbeiten aus.**

4. Wählen **Sie im** linken Navigationsbereich Mitglieder auswählen aus, und wählen Sie dann Bearbeiten **aus.**

5. Wählen **Sie Hinzufügen** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen **Sie Speichern** aus, um die Benutzer zur Rollengruppe hinzuzufügen.

8. Wählen Sie die nächste Rollengruppe für die Kommunikationskonformität aus, und wiederholen Sie dann die Schritte 4 bis 7 für jede erforderliche Rollengruppe.

9. Wählen **Sie Schließen** aus, um die Schritte zu ausführen.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter [Permissions im Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Schritt 2 (erforderlich): Aktivieren des Überwachungsprotokolls

Für die Kommunikationscompliance sind Überwachungsprotokolle erforderlich, um Warnungen anzuzeigen und die von den Prüfern ergriffenen Abhilfemaßnahmen zu verfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die mit einer definierten Organisationsrichtlinie verknüpft sind, oder zu jeder Zeit, in der sich eine Kommunikationskonformitätsrichtlinie ändert.

Schrittweise Anweisungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md) Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal tun. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Schritt 3 (optional): Einrichten von Gruppen für die Kommunikationskonformität

 Wenn Sie eine Kommunikationskonformitätsrichtlinie erstellen, definieren Sie, wer ihre Kommunikation überprüft hat und wer Rezensionen durchführt. In der Richtlinie verwenden Sie E-Mail-Adressen, um Einzelpersonen oder Gruppen von Personen zu identifizieren. Zur Vereinfachung ihres Setups können Sie Gruppen für Personen erstellen, deren Kommunikation überprüft wurde, und Gruppen für Personen, die diese Kommunikation überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht werden soll.

Verwenden Sie das folgende Diagramm, um Gruppen in Ihrer Organisation für Kommunikationskonformitätsrichtlinien zu konfigurieren:

| **Mitglied der Richtlinie** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Überwachte Benutzer <br> Nicht überwachte Benutzer | Verteilergruppen <br> Microsoft 365-Gruppen | Dynamische Verteilergruppen <br> Geschachtelte Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen <br> Microsoft 365-Gruppen mit dynamischer Mitgliedschaft |
| Prüfer | Keine | Verteilergruppen <br> Dynamische Verteilergruppen <br> Geschachtelte Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen |
  
Wenn Sie eine Verteilergruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails und Teams-Chats von jedem Benutzer in der Verteilergruppe. Wenn Sie eine Microsoft 365-Gruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails und Teams-Chats, die an diese Gruppe gesendet werden, nicht die einzelnen E-Mails und Chats, die von jedem Gruppenmitglied empfangen werden.

Wenn Sie eine Organisation mit einer lokalen Exchange-Bereitstellung oder einem externen E-Mail-Anbieter sind und Microsoft Teams-Chats für Ihre Benutzer überwachen möchten, müssen Sie eine Verteilergruppe für die Benutzer mit lokalen oder externen Postfächern erstellen, die überwacht werden sollen. Später in diesen Schritten weisen Sie diese  Verteilergruppe als Auswahl für überwachte Benutzer und Gruppen im Richtlinien-Assistenten zu.

Um überwachte Benutzer in großen Unternehmensorganisationen zu verwalten, müssen Sie möglicherweise alle Benutzer über große Gruppen hinweg überwachen. Sie können PowerShell verwenden, um eine Verteilergruppe für eine globale Kommunikationskonformitätsrichtlinie für die zugewiesene Gruppe zu konfigurieren. Auf diese Weise können Sie Tausende von Benutzern mit einer einzigen Richtlinie überwachen und die Richtlinie zur Kommunikationskonformität aktualisieren, sobald neue Mitarbeiter Ihrer Organisation beitreten.

1. Erstellen Sie [eine](/powershell/module/exchange/new-distributiongroup) dedizierte Verteilergruppe für Ihre globale Kommunikationskonformitätsrichtlinie mit den folgenden Eigenschaften: Stellen Sie sicher, dass diese Verteilergruppe nicht für andere Zwecke oder andere Office 365-Dienste verwendet wird.

    - **MemberDepartRestriction = Closed**. Stellt sicher, dass Benutzer sich nicht aus der Verteilergruppe entfernen können.
    - **MemberJoinRestriction = Closed**. Stellt sicher, dass Benutzer sich nicht der Verteilergruppe hinzufügen können.
    - **ModerationEnabled = True**. Stellt sicher, dass alle an diese Gruppe gesendeten Nachrichten der Genehmigung unterliegen und dass die Gruppe nicht für die Kommunikation außerhalb der Konfiguration der Kommunikationskonformitätsrichtlinie verwendet wird.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Wählen Sie ein nicht verwendetes [benutzerdefiniertes Exchange-Attribut aus,](/Exchange/recipients/mailbox-custom-attributes) um Benutzer nachverfolgt zu werden, die der Kommunikationskonformitätsrichtlinie in Ihrer Organisation hinzugefügt wurden.

3. Führen Sie das folgende PowerShell-Skript in einem wiederkehrenden Zeitplan aus, um der Kommunikationskonformitätsrichtlinie Benutzer hinzuzufügen:

    ```PowerShell
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

- [Erstellen und Verwalten von Verteilergruppen](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Übersicht über Microsoft 365-Gruppen](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Schritt 4 (optional): Überprüfen, ob sich Yammer Mandanten im nativen Modus befindet

Im nativen Modus befinden sich Yammer Benutzer in Azure Active Directory (Azure AD), alle Gruppen sind Office 365-Gruppen, und alle Dateien werden in SharePoint Online gespeichert. Ihr Yammer muss sich im nativen Modus befinden, damit Kommunikationskonformitätsrichtlinien riskante Unterhaltungen in privaten Nachrichten und Communityunterhaltungen in der Yammer.

Weitere Informationen zum Konfigurieren von Yammer im systemeigenen Modus finden Sie unter:

- [Übersicht über Yammer systemeigenen Modus in Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Konfigurieren eines Yammer-Netzwerks für den nativen Modus für Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Schritt 5 (erforderlich): Erstellen einer Kommunikationskonformitätsrichtlinie
  
>[!Important]
>Die Verwendung von PowerShell zum Erstellen und Verwalten von Richtlinien zur Kommunikationscompliance wird nicht unterstützt. Zum Erstellen und Verwalten dieser Richtlinien müssen Sie die Richtlinienverwaltungssteuerelemente in der [Microsoft 365 Communication Compliance-Lösung verwenden.](https://compliance.microsoft.com/supervisoryreview)

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wählen Sie im Microsoft 365 Compliance Center die Option **Kommunikationskonformität aus.**
  
3. Wählen Sie die **Registerkarte Richtlinien** aus.

4. Wählen **Sie Richtlinie erstellen** aus, um eine neue Richtlinie aus einer Vorlage zu erstellen und zu konfigurieren oder um eine benutzerdefinierte Richtlinie zu erstellen und zu konfigurieren.

    Wenn Sie eine Richtlinienvorlage zum Erstellen einer Richtlinie auswählen, werden Sie:

    - Bestätigen oder aktualisieren Sie den Richtliniennamen. Richtliniennamen können nach dem Erstellen der Richtlinie nicht mehr geändert werden.

    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl von Benutzern oder Gruppen, die Sie ausschließen möchten. Wenn Sie die Vorlage für Interessenkonflikte verwenden, wählen Sie zwei Gruppen oder zwei Benutzer aus, die für die interne Kommunikation überwacht werden sollen.

    - Wählen Sie die Prüfer für die Richtlinie aus. Prüfer sind einzelne Benutzer, und für alle Prüfer müssen Postfächer in Exchange Online gehostet sein. Hier hinzugefügte Prüfer sind die Prüfer, aus denen Sie wählen können, wenn Sie eine Warnung im Untersuchungs- und Behebungsworkflow eskalieren. Wenn Prüfer einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuordnung zur Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess enthält.

    - Wählen Sie ein eingeschränktes Bedingungsfeld aus, in der Regel ein vertraulicher Informationstyp oder ein Schlüsselwortwörterbuch, das auf die Richtlinie angewendet werden soll.

    >[!NOTE]
    >Wenn Sie die optische Zeichenerkennung [(Optical Character Recognition, OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) aktivieren möchten, um eingebettete oder angefügte Bilder in Nachrichten auf gedruckten oder handschriftlichen Text zu überprüfen, der richtlinienbedingungen entspricht, wählen Sie Richtlinienbedingungen anpassen und Prozentsatz anpassen aus, und aktivieren Sie zur Auswertung gedruckten oder handschriftlichen Text aus Bildern  >   extrahieren. 

    Wenn Sie den Richtlinien-Assistenten zum Erstellen einer benutzerdefinierten Richtlinie verwenden möchten, werden Sie:

    - Geben Sie der Richtlinie einen Namen und eine Beschreibung. Richtliniennamen können nach dem Erstellen der Richtlinie nicht mehr geändert werden.

    - Wählen Sie die zu überwachende Benutzer oder Gruppen aus, einschließlich aller Benutzer in Ihrer Organisation, bestimmter Benutzer und Gruppen oder anderer Benutzer und Gruppen, die Sie ausschließen möchten.

    - Wählen Sie die Prüfer für die Richtlinie aus. Prüfer sind einzelne Benutzer, und für alle Prüfer müssen Postfächer in Exchange Online gehostet sein. Hier hinzugefügte Prüfer sind die Prüfer, aus denen Sie wählen können, wenn Sie eine Warnung im Untersuchungs- und Behebungsworkflow eskalieren. Wenn Prüfer einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuordnung zur Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess enthält.

    - Wählen Sie die zu scannende Kommunikationskanäle aus, einschließlich Exchange, Microsoft Teams, Yammer oder Skype for Business. Sie können auch Drittanbieterquellen überprüfen, wenn Sie einen Connector in Microsoft 365 konfiguriert haben.

    - Wählen Sie die zu überwachende Kommunikationsrichtung aus, einschließlich eingehender, ausgehender oder interner Kommunikation.

    - Definieren Sie die Richtlinienbedingungen für die [Kommunikationskonformität.](communication-compliance-feature-reference.md#ConditionalSettings) Sie können zwischen Nachrichtenadresse, Schlüsselwort, Dateitypen und Größenverhältnissen auswählen.

    - Wählen Sie aus, ob Vertrauliche Informationstypen enthalten sein möchten. In diesem Schritt können Sie standard- und benutzerdefinierte Typen vertraulicher Informationen auswählen. Wählen Sie aus vorhandenen benutzerdefinierten Typen vertraulicher Informationen oder benutzerdefinierten Schlüsselwortwörterbüchern im Assistenten für Kommunikationskonformitätsrichtlinien aus. Sie können diese Elemente erstellen, bevor Sie den Assistenten bei Bedarf ausführen. Sie können auch neue Typen vertraulicher Informationen im Assistenten für Kommunikationskonformitätsrichtlinien erstellen.

    - Wählen Sie aus, ob Sie Klassifikatoren aktivieren möchten. Klassifikatoren können unangemessene Sprache und Bilder erkennen, die im Textkörper von E-Mail-Nachrichten oder anderen Texttypen gesendet oder empfangen wurden. Sie können die folgenden integrierten Klassifizierungen auswählen: *Bedrohung,* *Profanität,* gezielte *Belästigung,* Bilder für *Erwachsene,* *Rassische* Bilder und *Gory-Bilder.*

      > [!CAUTION]
      > Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse davon abziehen. Es wird empfohlen, stattdessen die **integrierten** Klassifikatoren Threat, **Profanity** und **Targeted** zu verwenden.

    - Aktivieren [Sie die optische Zeichenerkennung (OCR),](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) um eingebettete oder angefügte Bilder in Nachrichten auf gedruckten oder handschriftlichen Text zu überprüfen, der Richtlinienbedingungen entspricht. Für benutzerdefinierte Richtlinien müssen eine oder mehrere bedingte Einstellungen, die Text, Schlüsselwörter, Klassifizierungen oder typen vertraulicher Informationen zugeordnet sind, in der Richtlinie konfiguriert werden, um die Auswahl der Überprüfung der optischen Zeichenerkennung zu aktivieren.

    - Definieren Sie den Prozentsatz der zu überprüfende Kommunikation.

    - Überprüfen Sie die Richtlinienauswahl, und erstellen Sie die Richtlinie.

5. Wählen **Sie Richtlinie erstellen** bei Verwendung der Vorlagen oder **Übermitteln** aus, wenn Sie den benutzerdefinierten Richtlinien-Assistenten verwenden.

6. Die **Seite Ihre Richtlinie wurde erstellt** wird mit Richtlinien angezeigt, wann die Richtlinie aktiviert wird und welche Kommunikation erfasst wird.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Schritt 6 (optional): Erstellen von Benachrichtigungsvorlagen und Konfigurieren der Benutzer anonymisierung

Wenn Sie die Möglichkeit haben möchten, auf eine Richtlinienwarnung zu reagieren, indem Sie eine Erinnerungsbenachrichtigung an den zugeordneten Benutzer senden, müssen Sie mindestens eine Benachrichtigungsvorlage in Ihrer Organisation erstellen. Die Felder der Benachrichtigungsvorlage können bearbeitet werden, bevor sie im Rahmen des Warnungsbehebungsprozesses gesendet werden, und es wird empfohlen, eine angepasste Benachrichtigungsvorlage für jede Kommunikationskonformitätsrichtlinie zu erstellen.

Sie können auch die Anonymisierung für angezeigte Benutzernamen aktivieren, wenn Sie Richtlinien übereinstimmungen untersuchen und Aktionen für Nachrichten ergreifen.

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Kommunikationskonformität**.

3. Um die Anonymisierung für Benutzernamen zu konfigurieren, wählen **Sie** die Registerkarte Datenschutz aus.

4. Wählen Sie anonymisierte Versionen **von Benutzernamen anzeigen aus, um die Anonymisierung zu aktivieren.**

5. Klicken Sie auf **Speichern**.

6. Navigieren Sie zur **Registerkarte Benachrichtigungsvorlagen,** und wählen Sie **dann Benachrichtigungsvorlage erstellen aus.**

7. Füllen Sie **auf der Seite Eine Benachrichtigungsvorlage ändern** die folgenden Felder aus:

    - Vorlagenname (erforderlich)
    - Senden von (erforderlich)
    - Cc und Bcc (optional)
    - Betreff (erforderlich)
    - Nachrichtentext (erforderlich)

8. Wählen **Sie Speichern** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Schritt 7 (optional): Testen Ihrer Kommunikationskonformitätsrichtlinie

Nachdem Sie eine Kommunikationskonformitätsrichtlinie erstellt haben, sollten Sie sie testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß erzwungen werden. Sie können auch Ihre Richtlinien zur Verhinderung von Datenverlust [(Data Loss Prevention, DLP)](create-test-tune-dlp-policy.md) testen, wenn Ihre Richtlinien für die Kommunikationskonformität vertrauliche Informationstypen enthalten. Stellen Sie sicher, dass Sie Ihren Richtlinien Zeit für die Aktivierung geben, damit die kommunikation, die Sie testen möchten, erfasst wird.

Führen Sie die folgenden Schritte aus, um Ihre Kommunikationskonformitätsrichtlinie zu testen:

1. Öffnen Sie einen E-Mail-Client, Microsoft Teams oder Yammer, während Sie als überwachter Benutzer angemeldet sind, der in der Richtlinie definiert ist, die Sie testen möchten.

2. Senden Sie eine E-Mail, einen Microsoft Teams-Chat oder Yammer, die die Kriterien erfüllt, die Sie in der Kommunikationskonformitätsrichtlinie definiert haben. Dieser Test kann ein Schlüsselwort, eine Anlagengröße, eine Domäne usw. sein. Stellen Sie sicher, dass Sie feststellen, ob die konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu nachsichtig sind.

    > [!NOTE]
    > E-Mail-Nachrichten können bis zu 24 Stunden in einer Richtlinie vollständig verarbeiten. Die Kommunikation in Microsoft Teams, Yammer und Drittanbieterplattformen kann bis zu 48 Stunden in einer Richtlinie dauern.

3. Melden Sie sich bei Microsoft 365 als in der Kommunikationskonformitätsrichtlinie festgelegter Prüfer an. Navigieren Sie zu **Kommunikationskonformitätswarnungen,**  >   um die Warnungen für Ihre Richtlinien anzuzeigen.

4. Beheben Sie die Warnung mithilfe der Korrektursteuerelemente, und stellen Sie sicher, dass die Warnung ordnungsgemäß aufgelöst wurde.

## <a name="next-steps"></a>Weitere Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Kommunikationskonformitätsrichtlinie abgeschlossen haben, erhalten Sie nach 24-48 Stunden Benachrichtigungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf mithilfe der Anleitung in Schritt 5 dieses Artikels.

Weitere Informationen zum Untersuchen von Kommunikationskonformitätswarnungen finden Sie unter [Investigate and remediate communication compliance alerts](communication-compliance-investigate-remediate.md).
