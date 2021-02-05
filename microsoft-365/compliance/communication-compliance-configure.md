---
title: Erste Schritte mit der Kommunikationscompliance
description: Richten Sie Richtlinien zur Kommunikationskonformität ein, um die Benutzerkommunikation zur Überprüfung zu konfigurieren.
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
ms.openlocfilehash: 442f0dd13415c4ca435cdf69336d1fb07a9e045d
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109924"
---
# <a name="get-started-with-communication-compliance"></a>Erste Schritte mit der Kommunikationscompliance

Verwenden Sie Richtlinien zur Kommunikationskonformität, um die Benutzerkommunikation zur Untersuchung durch interne oder externe Prüfer zu identifizieren. Weitere Informationen dazu, wie Richtlinien zur Kommunikationskonformität Ihnen bei der Überwachung der Kommunikation in Ihrer Organisation helfen können, finden Sie unter Kommunikations-Compliance-Richtlinien [in Microsoft 365.](communication-compliance.md) Wenn Sie überprüfen möchten, wie Contoso schnell eine Kommunikationskonformitätsrichtlinie zur Überwachung auf anstößige Sprache in Microsoft Teams, Exchange Online und Yammer konfiguriert hat, sehen Sie sich diese [Fallstudie an.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzierung

Bevor Sie mit der Kommunikationskonformität beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Um auf die Kommunikationskonformität zugreifen und diese verwenden zu können, muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5 Insider Risk Management-Add-On
- Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3-Abonnement + das Microsoft 365 A5 Insider Risk Management-Add-On
- Microsoft 365 -G5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 -G5-Abonnement + das Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 -G5-Abonnement + das Microsoft 365 G5-Add-On "Insider Risk Management"
- Office 365 Enterprise E5-Abonnement (kostenpflichtig oder Testversion)
- Office 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (nicht mehr verfügbar für neue Abonnements, siehe Hinweis)

Benutzern, die in Richtlinien zur Kommunikationskonformität enthalten sind, muss eine der oben genannten Lizenzen zugewiesen werden.

>[!IMPORTANT]
>Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements überwechseln, das dieselben oder zusätzliche Compliancefeatures enthält.

Wenn Sie nicht über einen vorhandenen Office 365 Enterprise E5-Plan verfügen und die Kommunikationskonformität [](https://www.microsoft.com/microsoft-365/enterprise) testen möchten, können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder sich für eine Testversion von Office 365 Enterprise E5 registrieren.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Schritt 1 (erforderlich): Aktivieren von Berechtigungen für die Kommunikationskonformität

>[!Important]
>Standardmäßig haben globale Administratoren keinen Zugriff auf Kommunikationskonformitätsfeatures. Die in diesem Schritt zugewiesenen Rollen sind erforderlich, bevor auf Kommunikationskonformitätsfeatures zugegriffen werden kann. Nach dem Konfigurieren ihrer Rollengruppen kann es bis zu 30 Minuten dauern, bis die Rollengruppenberechtigungen auf zugewiesene Benutzer in Ihrer Organisation angewendet werden.

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationskonformitätsfeatures verwendet werden. Um  die Kommunikationskonformität als Menüoption im Microsoft 365 Compliance Center verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, müssen Sie den Rollengruppen *"Communication Compliance"* oder *"Communication Compliance Admin"* zugewiesen sein. Um nach der Erstkonfiguration auf Kommunikationskonformitätsfeatures zugreifen und diese verwalten zu können, müssen Benutzer Mitglied mindestens einer Rollengruppe für die Kommunikationskonformität sein.

Je nachdem, wie Sie Kommunikationsrichtlinien und Warnungen verwalten möchten, müssen Sie Benutzer bestimmten Rollengruppen zuweisen. Sie haben die Möglichkeit, Bestimmten Rollengruppen Benutzer mit unterschiedlichen Complianceaufgaben zuzuordnen, um verschiedene Bereiche der Kommunikationskonformitätsfeatures zu verwalten. Sie können auch alle Benutzerkonten für designierte Administratoren, Analysten, Ermittler  und Betrachter der Rollengruppe "Kommunikationskonformität" zuweisen. Verwenden Sie eine einzelne Rollengruppe oder mehrere Rollengruppen, um ihre Anforderungen für die Verwaltung der Richtlinienkonformität optimal zu erfüllen.

Wählen Sie beim Konfigurieren der Kommunikationskonformität aus den folgenden Rollengruppenoptionen aus:

| Rolle | Rollenberechtigungen |
|:-----|:-----|
| **Kommunikationskonformität** | Verwenden Sie diese Rollengruppe, um die Kommunikationskonformität für Ihre Organisation in einer einzigen Gruppe zu verwalten. Durch Hinzufügen aller Benutzerkonten für designierte Administratoren, Analysten, Ermittler und Betrachter können Sie Berechtigungen zur Kommunikationskonformität in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationskonformität. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationskonformität zu beginnen, und ist gut geeignet für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikationskonformitätsadministrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationskonformität zu konfigurieren und später Administratoren für die Kommunikationskonformität in eine definierte Gruppe zu untergtrennen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien zur Kommunikationskonformität, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Benachrichtigungen anzeigen. |
| **Communication Compliance Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Kommunikations-Compliance-Analysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, in denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten (keine Nachrichteninhalte) anzeigen, an zusätzliche Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht beheben. |
| **Kommunikations-Compliance-Ermittler** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die als Ermittler der Kommunikationskonformität fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und -inhalte anzeigen, an weitere Prüfer eskalieren, zu einem Advanced eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Communication Compliance Viewer** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zu erteilen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Startseite für die Kommunikationskonformität auf alle Berichts widgets zugreifen und alle Berichte zur Kommunikationskonformität anzeigen. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Option 1: Zuweisen aller Compliancebenutzer zur Rollengruppe "Kommunikationskonformität"

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **"Berechtigungen".** Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie die *Rollengruppe* "Kommunikationskonformität" und dann **"Rollengruppe bearbeiten" aus.**

4. Wählen **Sie im** linken Navigationsbereich "Mitglieder auswählen" und dann "Bearbeiten" **aus.**

5. Wählen **Sie "Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe "Kommunikationskonformität" hinzufügen möchten. 

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen **Sie "Speichern"** aus, um die Benutzer zur Rollengruppe hinzuzufügen. Wählen **Sie "Schließen"** aus, um die Schritte ausführen zu können.

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Option 2: Zuweisen von Benutzern zu bestimmten Rollengruppen für die Kommunikationskonformität

Verwenden Sie diese Option, um Benutzern bestimmte Rollengruppen zuzuordnen, um den Zugriff auf die Kommunikationskonformität und die Verantwortlichkeiten zwischen verschiedenen Benutzern in Ihrer Organisation zu segmentieren.

1. Melden Sie [https://protection.office.com/permissions](https://protection.office.com/permissions) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **"Berechtigungen".** Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie eine der Rollengruppen für die Kommunikationskonformität und dann **"Rollengruppe bearbeiten" aus.**

4. Wählen **Sie im** linken Navigationsbereich "Mitglieder auswählen" und dann "Bearbeiten" **aus.**

5. Wählen **Sie "Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen **Sie "Speichern"** aus, um die Benutzer zur Rollengruppe hinzuzufügen.

8. Wählen Sie die nächste Rollengruppe für die Kommunikationskonformität aus, und wiederholen Sie dann die Schritte 4 bis 7 für jede erforderliche Rollengruppe.

9. Wählen **Sie "Schließen"** aus, um die Schritte ausführen zu können.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter ["Berechtigungen" im Compliance Center.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Schritt 2 (erforderlich): Aktivieren des Überwachungsprotokolls

Für die Kommunikationscompliance sind Überwachungsprotokolle erforderlich, um Warnungen anzuzeigen und die von den Prüfern ergriffenen Abhilfemaßnahmen zu verfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die einer definierten Organisationsrichtlinie zugeordnet sind oder sich jederzeit ändern.

Schrittweise Anweisungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md) Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal tun. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Schritt 3 (optional): Einrichten von Gruppen für die Kommunikationskonformität

 Wenn Sie eine Richtlinie zur Kommunikationskonformität erstellen, definieren Sie, wer ihre Kommunikation überprüft hat und wer Überprüfungen durchführt. In der Richtlinie verwenden Sie E-Mail-Adressen, um Einzelpersonen oder Gruppen von Personen zu identifizieren. Zur Vereinfachung der Einrichtung können Sie Gruppen für Personen erstellen, deren Kommunikation überprüft wurde, und Gruppen für Personen erstellen, die diese Kommunikation überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie z. B. die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Mithilfe des folgenden Diagramms können Sie Gruppen in Ihrer Organisation für Richtlinien zur Kommunikationskonformität konfigurieren:

| **Richtlinienmitglied** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Überwachte Benutzer <br> Nicht überwachte Benutzer | Verteilergruppen <br> Microsoft 365-Gruppen | Dynamische Verteilergruppen <br> Geschachtelte Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen |
| Prüfer | Keine | Verteilergruppen <br> Dynamische Verteilergruppen <br> Geschachtelte Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen |
  
Wenn Sie eine Verteilergruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails und Teams-Chats von jedem Benutzer in der Verteilergruppe. Wenn Sie eine Microsoft 365-Gruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails und Teams-Chats, die an diese Gruppe gesendet werden, nicht die einzelnen E-Mails und Chats, die von jedem Gruppenmitglied empfangen werden.

Wenn Sie eine Organisation mit einer lokalen Bereitstellung von Exchange oder einem externen E-Mail-Anbieter sind und Microsoft Teams-Chats für Ihre Benutzer überwachen möchten, müssen Sie eine Verteilergruppe für die Benutzer mit lokalen oder externen Postfächern erstellen, die überwacht werden sollen. Später in diesen Schritten weisen Sie diese  Verteilergruppe im Richtlinienassistenten als Auswahl für überwachte Benutzer und Gruppen zu.

>[!IMPORTANT]
>Sie müssen eine Anforderung beim Microsoft-Support stellen, damit Ihre Organisation die grafische Benutzeroberfläche im Security & Compliance Center verwenden kann, um für lokale Benutzer nach Teams-Chatdaten zu suchen. Weitere Informationen finden Sie unter [Durchsuchen cloudbasierter Postfächer für lokale Benutzer.](search-cloud-based-mailboxes-for-on-premises-users.md)

Um überwachte Benutzer in großen Unternehmensorganisationen zu verwalten, müssen Sie möglicherweise alle Benutzer über große Gruppen hinweg überwachen. Sie können PowerShell verwenden, um eine Verteilergruppe für eine globale Richtlinie zur Kommunikationskonformität für die zugewiesene Gruppe zu konfigurieren. Auf diese Weise können Sie Tausende von Benutzern mit einer einzigen Richtlinie überwachen und die Richtlinie zur Kommunikationskonformität aktualisieren, sobald neue Mitarbeiter Ihrer Organisation beitreten.

1. Erstellen Sie [eine](/powershell/module/exchange/new-distributiongroup) dedizierte Verteilergruppe für Ihre globale Richtlinie zur Kommunikationskonformität mit den folgenden Eigenschaften: Stellen Sie sicher, dass diese Verteilergruppe nicht für andere Zwecke oder andere Office 365-Dienste verwendet wird.

    - **MemberDepartRestriction = Closed**. Stellt sicher, dass Benutzer sich selbst nicht aus der Verteilergruppe entfernen können.
    - **MemberJoinRestriction = Closed**. Stellt sicher, dass Benutzer sich selbst nicht zur Verteilergruppe hinzufügen können.
    - **ModerationEnabled = True**. Stellt sicher, dass alle an diese Gruppe gesendeten Nachrichten genehmigt werden und dass die Gruppe nicht für die Kommunikation außerhalb der Konfiguration der Kommunikationskonformitätsrichtlinie verwendet wird.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Wählen Sie ein nicht verwendetes [benutzerdefiniertes Exchange-Attribut aus,](/Exchange/recipients/mailbox-custom-attributes) um Benutzer nachverfolgt zu werden, die der Kommunikationskonformitätsrichtlinie in Ihrer Organisation hinzugefügt wurden.

3. Führen Sie das folgende PowerShell-Skript nach einem wiederkehrenden Zeitplan aus, um Der Kommunikationskonformitätsrichtlinie Benutzer hinzuzufügen:

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

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Schritt 4 (optional): Überprüfen, ob Yammer mandanten im nativen Modus ist

Im nativen Modus befinden sich Yammer Benutzer in Azure Active Directory (Azure AD), alle Gruppen sind Office 365-Gruppen, und alle Dateien werden in SharePoint Online gespeichert. Ihr Yammer muss sich im nativen Modus befinden, damit Kommunikationskonformitätsrichtlinien riskante Unterhaltungen in privaten Nachrichten und Communityunterhaltungen in Yammer.

Weitere Informationen zum Konfigurieren von Yammer im nativen Modus finden Sie unter:

- [Übersicht über Yammer nativen Modus in Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Konfigurieren eines Yammer-Netzwerks für den nativen Modus für Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Schritt 5 (erforderlich): Erstellen einer Kommunikationskonformitätsrichtlinie
  
>[!Important]
>Die Verwendung von PowerShell zum Erstellen und Verwalten von Richtlinien zur Kommunikationscompliance wird nicht unterstützt. Zum Erstellen und Verwalten dieser Richtlinien müssen Sie die Richtlinienverwaltungssteuerelemente in der [Microsoft 365-Kommunikationskonformitätslösung verwenden.](https://compliance.microsoft.com/supervisoryreview)

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wählen Sie im Microsoft 365 Compliance Center die **Kommunikationskonformität aus.**
  
3. Wählen Sie die **Registerkarte "Richtlinien"** aus.

4. Wählen **Sie "Richtlinie erstellen"** aus, um eine neue Richtlinie aus einer Vorlage zu erstellen und zu konfigurieren oder um eine benutzerdefinierte Richtlinie zu erstellen und zu konfigurieren.

    Wenn Sie eine Richtlinienvorlage zum Erstellen einer Richtlinie auswählen, haben Sie dies:

    - Bestätigen oder aktualisieren Sie den Richtliniennamen. Richtliniennamen können nicht mehr geändert werden, nachdem die Richtlinie erstellt wurde.
    
    - Wählen Sie die Zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl von Benutzern oder Gruppen, die Sie ausschließen möchten. Wenn Sie die Vorlage für Interessenkonflikte verwenden, wählen Sie zwei Gruppen oder zwei Benutzer aus, die auf die interne Kommunikation überwacht werden sollen.
    
    - Wählen Sie die Prüfer für die Richtlinie aus. Prüfer sind einzelne Benutzer, und alle Prüfer müssen über Postfächer verfügen, die auf Exchange Online gehostet werden. Die hier hinzugefügten Prüfer sind die Prüfer, aus denen Sie wählen können, wenn Sie eine Warnung im Untersuchungs- und Wartungsworkflow eskalieren. Wenn Prüfer einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuweisung an die Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess enthält.
    
    - Wählen Sie ein eingeschränktes Bedingungsfeld aus, in der Regel ein vertraulicher Informationstyp oder ein Schlüsselwortwörterbuch, das auf die Richtlinie angewendet werden soll.

    Wenn Sie den Richtlinienassistenten verwenden, um eine benutzerdefinierte Richtlinie zu erstellen, werden Sie dies wie gewohnt:

    - Geben Sie der Richtlinie einen Namen und eine Beschreibung. Richtliniennamen können nicht mehr geändert werden, nachdem die Richtlinie erstellt wurde.
    
    - Wählen Sie die zu überwachende Benutzer oder Gruppen aus, einschließlich aller Benutzer in Ihrer Organisation, bestimmter Benutzer und Gruppen oder anderer Benutzer und Gruppen, die Sie ausschließen möchten.
    
    - Wählen Sie die Prüfer für die Richtlinie aus. Prüfer sind einzelne Benutzer, und alle Prüfer müssen über Postfächer verfügen, die auf Exchange Online gehostet werden. Die hier hinzugefügten Prüfer sind die Prüfer, aus denen Sie wählen können, wenn Sie eine Warnung im Untersuchungs- und Wartungsworkflow eskalieren. Wenn Prüfer einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuweisung an die Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess enthält.
    
    - Wählen Sie die zu überprüfende Kommunikationskanäle aus, einschließlich Exchange, Microsoft Teams, Yammer oder Skype for Business. Sie können auch Drittanbieterquellen überprüfen, wenn Sie einen Connector in Microsoft 365 konfiguriert haben.
    
    - Wählen Sie die zu überwachende Kommunikationsrichtung aus, einschließlich eingehender, ausgehender oder interner Kommunikation.
    
    - Definieren Sie die Bedingungen der [Kommunikationskonformitätsrichtlinie.](communication-compliance-feature-reference.md#ConditionalSettings) Sie können zwischen Nachrichtenadresse, Schlüsselwort, Dateitypen und Größen-Übereinstimmungsbedingungen wählen.
    
    - Wählen Sie aus, ob Sie vertrauliche Informationstypen verwenden möchten. In diesem Schritt können Sie standardmäßige und benutzerdefinierte Typen vertraulicher Informationen auswählen. Wählen Sie aus vorhandenen benutzerdefinierten Typen vertraulicher Informationen oder benutzerdefinierten Schlüsselwortwörterbüchern im Assistenten für Kommunikationskonformitätsrichtlinien aus. Sie können diese Elemente bei Bedarf erstellen, bevor Sie den Assistenten ausführen. Sie können auch neue Typen vertraulicher Informationen im Assistenten für Kommunikationskonformitätsrichtlinien erstellen.
    
    - Wählen Sie aus, ob Sie Klassifizierungen aktivieren möchten. Klassifizierer können unangemessene Sprache und Bilder erkennen, die im Textkörper von E-Mail-Nachrichten oder anderen Texttypen gesendet oder empfangen wurden. Sie können die folgenden integrierten Klassifikatoren auswählen: *Bedrohung,* Ansheitshaltung, gezielte *Belästigung,* Bilder für Erwachsene, *Rassische* Bilder und *Gory-Bilder.* 

      > [!CAUTION]
      > Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse davon wegziehen. Es wird empfohlen, stattdessen die integrierten Klassifizierungen **"Bedrohung",** **"Anslästigkeit"** und "Gezielte Belästigung" zu verwenden. 

    - Definieren Sie den Prozentsatz der zu überprüfende Kommunikation.
    
    - Überprüfen Sie ihre Richtlinienauswahl, und erstellen Sie die Richtlinie.

5. Wählen **Sie "Richtlinie erstellen"** bei Verwendung der Vorlagen oder **"Absenden"** aus, wenn Sie den Assistenten für benutzerdefinierte Richtlinien verwenden.

6. Die **Seite "Ihre Richtlinie wurde erstellt"** wird mit Richtlinien angezeigt, wann die Richtlinie aktiviert wird und welche Kommunikation erfasst wird.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Schritt 6 (optional): Erstellen von Benachrichtigungsvorlagen und Konfigurieren der Benutzer anonymisierung

Wenn Sie die Möglichkeit haben möchten, auf eine Richtlinienwarnung zu reagieren, indem Sie eine Erinnerung an den zugeordneten Benutzer senden, müssen Sie mindestens eine Benachrichtigungsvorlage in Ihrer Organisation erstellen. Die Felder der Benachrichtigungsvorlage können bearbeitet werden, bevor sie im Rahmen des Warnungsbehebungsprozesses gesendet werden, und es wird empfohlen, eine angepasste Benachrichtigungsvorlage für jede Richtlinie zur Kommunikationskonformität zu erstellen.

Sie können auch die Anonymisierung für angezeigte Benutzernamen aktivieren, wenn Sie Richtlinien übereinstimmungen untersuchen und Aktionen für Nachrichten ergreifen.

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Kommunikationskonformität.**

3. Um die Anonymisierung für Benutzernamen zu konfigurieren, wählen Sie die Registerkarte **"Datenschutz"** aus.

4. Wählen Sie zum Aktivieren der Anonymisierung die Option **"Anonymisierte Versionen von Benutzernamen anzeigen" aus.**

5. Klicken Sie auf **Speichern**.

6. Navigieren Sie zur Registerkarte **"Benachrichtigungsvorlagen",** und wählen Sie dann **"Benachrichtigungsvorlage erstellen" aus.**

7. Füllen Sie **auf der Seite Zum Ändern einer Benachrichtigungsvorlage** die folgenden Felder aus:

    - Vorlagenname (erforderlich)
    - Senden von (erforderlich)
    - Cc und Bcc (optional)
    - Betreff (erforderlich)
    - Nachrichtentext (erforderlich)

8. Wählen **Sie "Speichern"** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Schritt 7 (optional): Testen der Kommunikationskonformitätsrichtlinie

Nachdem Sie eine Richtlinie zur Kommunikationskonformität erstellt haben, sollten Sie sie testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß erzwungen werden. Sie können auch Ihre Richtlinien zur Verhinderung von Datenverlust [(Data Loss Prevention, DLP)](create-test-tune-dlp-policy.md) testen, wenn Ihre Richtlinien zur Kommunikationskonformität vertrauliche Informationstypen enthalten. Stellen Sie sicher, dass Sie den Richtlinien Zeit zum Aktivieren geben, damit die kommunikation, die Sie testen möchten, erfasst wird.

Führen Sie die folgenden Schritte aus, um Ihre Kommunikationskonformitätsrichtlinie zu testen:

1. Öffnen Sie einen E-Mail-Client, Microsoft Teams Yammer, während Sie als überwachter Benutzer angemeldet sind, der in der Richtlinie definiert ist, die Sie testen möchten.

2. Senden Sie eine E-Mail, einen Microsoft Yammer oder eine Nachricht, die die Kriterien erfüllt, die Sie in der Kommunikationskonformitätsrichtlinie definiert haben. Dieser Test kann ein Schlüsselwort, eine Anlagengröße, eine Domäne usw. sein. Stellen Sie sicher, dass Sie feststellen, ob die konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu lensig sind.

    > [!NOTE]
    > Es kann bis zu 24 Stunden dauern, bis E-Mail-Nachrichten vollständig in einer Richtlinie zu verarbeiten sind. Die kommunikation in Microsoft Teams, Yammer und Drittanbieterplattformen kann bis zu 48 Stunden dauern, bis eine Richtlinie vollständig zu verarbeiten ist.

3. Melden Sie sich bei Microsoft 365 als Prüfer an, der in der Kommunikationskonformitätsrichtlinie festgelegt ist. Navigieren Sie **zu Warnungen zur**  >  **Kommunikationskonformität,** um die Warnungen für Ihre Richtlinien anzuzeigen.

4. Beheben Sie die Warnung mithilfe der Korrektursteuerelemente, und stellen Sie sicher, dass die Warnung ordnungsgemäß aufgelöst wurde.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Richtlinie zur Kommunikationskonformität abgeschlossen haben, erhalten Sie nach 24 bis 48 Stunden Benachrichtigungen von Aktivitätsindikatoren. Konfigurieren Sie nach Bedarf zusätzliche Richtlinien mithilfe der Anleitungen in Schritt 5 dieses Artikels.

Weitere Informationen zum Untersuchen von Warnungen zur Kommunikationskonformität finden Sie unter "Untersuchen und Behebung von Warnungen [zur Kommunikationskonformität".](communication-compliance-investigate-remediate.md)
