---
title: Erste Schritte mit der Kommunikationscompliance
description: Richten Sie Richtlinien für die Kommunikationscompliance ein, um die Benutzerkommunikation für die Überprüfung zu konfigurieren.
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
ms.openlocfilehash: f099d7bd180843530d23d0bbcee89dc8ae35cdbb
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256735"
---
# <a name="get-started-with-communication-compliance"></a>Erste Schritte mit der Kommunikationscompliance

Verwenden Sie Richtlinien zur Kommunikationscompliance, um die Benutzerkommunikation für die Prüfung durch interne oder externe Prüfer zu identifizieren. Weitere Informationen dazu, wie Richtlinien zur Kommunikationscompliance Ihnen bei der Überwachung der Kommunikation in Ihrer Organisation helfen können, finden Sie [in den Richtlinien zur Kommunikationscompliance in Microsoft 365.](communication-compliance.md) Wenn Sie überprüfen möchten, wie Contoso schnell eine Richtlinie zur Kommunikationscompliance konfiguriert hat, um in Microsoft Teams, Exchange Online und Yammer Kommunikationen auf anstößige Sprache zu überwachen, lesen Sie diese [Fallstudie.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzierung

Bevor Sie mit der Kommunikationscompliance beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Um auf die Kommunikationscompliance zuzugreifen und diese zu verwenden, muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 E3 Abonnement + das Microsoft 365 E5 Compliance-Add-On
- Microsoft 365 E3 Abonnement und das Add-On Microsoft 365 E5 Insider-Risikomanagement
- Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 A3 Abonnement und das Microsoft 365 A5 Compliance-Add-On
- Microsoft 365 A3 Abonnement und das Add-On Microsoft 365 A5 Insider-Risikomanagement
- Microsoft 365 G5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 G5-Abonnement + das Microsoft 365 G5 Compliance-Add-On
- Microsoft 365 G5-Abonnement + das add-on Microsoft 365 G5 Insider Risk Management
- Office 365 Enterprise E5-Abonnement (kostenpflichtige version oder Testversion)
- Office 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (für neue Abonnements nicht mehr verfügbar, siehe Hinweis)

Benutzern, die in Richtlinien zur Kommunikationscompliance enthalten sind, muss eine der oben genannten Lizenzen zugewiesen werden.

> [!IMPORTANT]
> Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden auf eines der oben genannten Abonnements umsteigen, die die gleichen oder zusätzlichen Compliancefeatures enthalten.

Wenn Sie keinen vorhandenen Office 365 Enterprise E5-Plan haben und die Kommunikationscompliance ausprobieren möchten, können Sie Ihrem vorhandenen Abonnement [Microsoft 365 hinzufügen](/office365/admin/try-or-buy-microsoft-365) oder sich für eine Testversion von Office 365 Enterprise E5 [registrieren.](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Schritt 1 (erforderlich): Aktivieren von Berechtigungen für die Kommunikationscompliance

> [!IMPORTANT]
> Standardmäßig haben globale Administratoren keinen Zugriff auf Kommunikationscompliancefeatures. Die in diesem Schritt zugewiesenen Rollen sind erforderlich, bevor auf Kommunikationscompliancefeatures zugegriffen werden kann. Nach dem Konfigurieren Ihrer Rollengruppen kann es bis zu 30 Minuten dauern, bis die Rollengruppenberechtigungen für zugewiesene Benutzer in Ihrer Organisation gelten.

Es gibt fünf Rollengruppen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikationscompliancefeatures verwendet werden. Um **die Kommunikationscompliance** als Menüoption in Microsoft 365 Compliance Center verfügbar zu machen und mit diesen Konfigurationsschritten fortzufahren, müssen Sie den Rollengruppen *"Kommunikationscompliance"* oder *"Kommunikationscompliance-Administrator"* zugewiesen werden. Um nach der anfänglichen Konfiguration auf Kommunikationscompliancefeatures zuzugreifen und diese zu verwalten, müssen Benutzer Mitglied mindestens einer Rollengruppe für die Kommunikationscompliance sein.

Je nachdem, wie Sie Kommunikationsrichtlinien und -warnungen verwalten möchten, müssen Sie Benutzern bestimmte Rollengruppen zuweisen. Sie haben die Möglichkeit, bestimmten Rollengruppen Benutzer mit unterschiedlichen Compliance-Verantwortlichkeiten zuzuweisen, um unterschiedliche Bereiche der Kommunikationscompliancefeatures zu verwalten. Sie können auch alle Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Betrachter der Rollengruppe *"Kommunikationscompliance"* zuweisen. Verwenden Sie eine einzelne Rollengruppe oder mehrere Rollengruppen, um Ihre Compliance-Verwaltungsanforderungen am besten zu erfüllen.

Wählen Sie bei der Konfiguration der Kommunikationscompliance aus den folgenden Rollengruppenoptionen aus:

| Rolle | Rollenberechtigungen |
|:-----|:-----|
| **Kommunikationscompliance** | Verwenden Sie diese Rollengruppe, um die Kommunikationscompliance für Ihre Organisation in einer einzigen Gruppe zu verwalten. Indem Sie alle Benutzerkonten für bestimmte Administratoren, Analysten, Ermittler und Betrachter hinzufügen, können Sie Kommunikationscomplianceberechtigungen in einer einzigen Gruppe konfigurieren. Diese Rollengruppe enthält alle Berechtigungsrollen für die Kommunikationscompliance. Diese Konfiguration ist die einfachste Möglichkeit, schnell mit der Kommunikationscompliance zu beginnen, und eignet sich gut für Organisationen, die keine separaten Berechtigungen benötigen, die für separate Benutzergruppen definiert sind. |
| **Kommunikationscompliance-Administrator** | Verwenden Sie diese Rollengruppe, um zunächst die Kommunikationscompliance zu konfigurieren und später die Administratoren der Kommunikationscompliance in eine definierte Gruppe zu unterteilen. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien zur Kommunikationscompliance, globale Einstellungen und Rollengruppenzuweisungen erstellen, lesen, aktualisieren und löschen. Benutzer, die dieser Rollengruppe zugewiesen sind, können keine Meldungswarnungen anzeigen. |
| **Kommunikationscompliance-Analyst** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Kommunikationscomplianceanalysten fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Richtlinien anzeigen, denen sie als Prüfer zugewiesen sind, Nachrichtenmetadaten anzeigen (nicht Nachrichteninhalte), an zusätzliche Prüfer eskalieren oder Benachrichtigungen an Benutzer senden. Analysten können ausstehende Warnungen nicht auflösen. |
| **Kommunikationscompliance-Ermittler** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die als Ermittler für die Kommunikationscompliance fungieren. Benutzer, die dieser Rollengruppe zugewiesen sind, können Nachrichtenmetadaten und Inhalte anzeigen, an zusätzliche Prüfer eskalieren, zu einem Advanced eDiscovery Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung auflösen. |
| **Kommunikationscompliance-Anzeigender** | Verwenden Sie diese Gruppe, um Benutzern Berechtigungen zuzuweisen, die Kommunikationsberichte verwalten. Benutzer, die dieser Rollengruppe zugewiesen sind, können auf der Startseite zur Kommunikationscompliance auf alle Berichterstellungs-Widgets zugreifen und alle Kommunikationscomplianceberichte anzeigen. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Option 1: Zuweisen aller Compliancebenutzer zur Rollengruppe "Kommunikationscompliance"

1. Melden Sie sich [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **"Berechtigungen".** Wählen Sie den Link aus, um Rollen in Office 365 anzuzeigen und zu verwalten.

3. Wählen Sie die Rollengruppe *"Kommunikationscompliance"* und dann die **Rollengruppe "Bearbeiten"** aus.

4. Wählen Sie Im linken Navigationsbereich **"Mitglieder auswählen"** und dann **"Bearbeiten"** aus.

5. Wählen Sie **"Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe *"Kommunikationscompliance"* hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen Sie **"Speichern"** aus, um die Benutzer der Rollengruppe hinzuzufügen. Wählen Sie **"Schließen"** aus, um die Schritte auszuführen

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Option 2: Zuweisen von Benutzern zu bestimmten Rollengruppen zur Kommunikationscompliance

Verwenden Sie diese Option, um Benutzern bestimmte Rollengruppen zuzuweisen, um den Zugriff auf die Kommunikationscompliance und die Zuständigkeiten zwischen den verschiedenen Benutzern in Ihrer Organisation zu segmentieren.

1. Melden Sie sich [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Security &amp; Compliance Center zu **"Berechtigungen".** Wählen Sie den Link aus, um Rollen in Office 365 anzuzeigen und zu verwalten.

3. Wählen Sie eine der Rollengruppen für die Kommunikationscompliance und dann die **Rollengruppe "Bearbeiten"** aus.

4. Wählen Sie Im linken Navigationsbereich **"Mitglieder auswählen"** und dann **"Bearbeiten"** aus.

5. Wählen Sie **"Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.

7. Wählen Sie **"Speichern"** aus, um die Benutzer der Rollengruppe hinzuzufügen.

8. Wählen Sie die nächste Rollengruppe für die Kommunikationscompliance aus, und wiederholen Sie dann die Schritte 4 bis 7 für jede erforderliche Rollengruppe.

9. Wählen Sie **"Schließen"** aus, um die Schritte auszuführen.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter ["Berechtigungen" im Compliance Center.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Schritt 2 (erforderlich): Aktivieren des Überwachungsprotokolls

Für die Kommunikationscompliance sind Überwachungsprotokolle erforderlich, um Warnungen anzuzeigen und die von den Prüfern ergriffenen Abhilfemaßnahmen zu verfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten im Zusammenhang mit einer definierten Organisationsrichtlinie oder immer dann, wenn sich eine Kommunikationscompliancerichtlinie ändert.

Schritt-für-Schritt-Anleitungen zum Aktivieren der Überwachung finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md) Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal ausführen. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Schritt 3 (optional): Einrichten von Gruppen für die Kommunikationscompliance

 Wenn Sie eine Richtlinie zur Kommunikationscompliance erstellen, definieren Sie, wer ihre Kommunikation überprüft und wer Rezensionen durchführt. In der Richtlinie verwenden Sie E-Mail-Adressen, um Einzelpersonen oder Personengruppen zu identifizieren. Um Ihre Einrichtung zu vereinfachen, können Sie Gruppen für Personen erstellen, die ihre Kommunikation überprüft haben, und Gruppen für Personen, die diese Kommunikation überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Verwenden Sie das folgende Diagramm, um Gruppen in Ihrer Organisation für Richtlinien zur Kommunikationscompliance zu konfigurieren:

| **Policy Member** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Überwachte Benutzer <br> Ausgeschlossene Benutzer | Verteilergruppen <br> Microsoft 365-Gruppen | Dynamische Verteilergruppen <br> Geschachtelte Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen <br> Microsoft 365 Von Gruppen mit dynamischer Mitgliedschaft |
| Prüfer | Keiner | Verteilergruppen <br> Dynamische Verteilergruppen <br> Geschachtelte Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen |

Wenn Sie eine Verteilergruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails und Teams Chats von jedem Benutzer in der Verteilergruppe. Wenn Sie eine Microsoft 365 Gruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle E-Mails und Teams An diese Gruppe gesendeten Chats, nicht die einzelnen E-Mails und Chats, die von jedem Gruppenmitglied empfangen werden.

Wenn Sie eine Organisation mit einer Exchange lokalen Bereitstellung oder einem externen E-Mail-Anbieter sind und Microsoft Teams Chats für Ihre Benutzer überwachen möchten, müssen Sie eine Verteilergruppe für die Benutzer mit lokalen oder externen Postfächern erstellen, die überwacht werden sollen. Später in diesen Schritten weisen Sie diese Verteilergruppe im Richtlinien-Assistenten als Auswahl **überwachter Benutzer und Gruppen** zu. Weitere Informationen zu den Anforderungen und Einschränkungen für die Aktivierung von cloudbasiertem Speicher und Teams Unterstützung für lokale Benutzer finden Sie unter [Suchen nach Teams Chatdaten für lokale Benutzer.](search-cloud-based-mailboxes-for-on-premises-users.md)

Um überwachte Benutzer in großen Unternehmen zu verwalten, müssen Sie möglicherweise alle Benutzer über große Gruppen hinweg überwachen. Sie können PowerShell verwenden, um eine Verteilergruppe für eine globale Kommunikationscompliancerichtlinie für die zugewiesene Gruppe zu konfigurieren. Auf diese Weise können Sie Tausende von Benutzern mit einer einzigen Richtlinie überwachen und die Richtlinie zur Kommunikationscompliance aktualisieren, wenn neue Mitarbeiter Ihrer Organisation beitreten.

1. Erstellen Sie eine dedizierte [Verteilergruppe](/powershell/module/exchange/new-distributiongroup) für Ihre globale Kommunikationscompliancerichtlinie mit den folgenden Eigenschaften: Stellen Sie sicher, dass diese Verteilergruppe nicht für andere Zwecke oder andere Office 365 Dienste verwendet wird.

    - **MemberDepartRestriction = Closed**. Stellt sicher, dass Benutzer sich selbst nicht aus der Verteilergruppe entfernen können.
    - **MemberJoinRestriction = Closed**. Stellt sicher, dass Benutzer sich nicht selbst zur Verteilergruppe hinzufügen können.
    - **ModerationEnabled = True**. Stellt sicher, dass alle an diese Gruppe gesendeten Nachrichten der Genehmigung unterliegen und dass die Gruppe nicht für die Kommunikation außerhalb der Kommunikationscompliancerichtlinienkonfiguration verwendet wird.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Wählen Sie ein nicht verwendetes [Exchange benutzerdefinierte Attribut](/Exchange/recipients/mailbox-custom-attributes) aus, um Benutzer nachzuverfolgen, die der Kommunikationscompliancerichtlinie in Ihrer Organisation hinzugefügt wurden.

3. Führen Sie das folgende PowerShell-Skript nach einem wiederkehrenden Zeitplan aus, um der Kommunikationscompliancerichtlinie Benutzer hinzuzufügen:

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

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Schritt 4 (optional): Überprüfen Sie, ob sich Ihr Yammer-Mandant im nativen Modus befindet

Im nativen Modus befinden sich alle Yammer Benutzer in Azure Active Directory (Azure AD), alle Gruppen sind Office 365 Gruppen, und alle Dateien werden in SharePoint Online gespeichert. Ihr Yammer Mandant muss sich im nativen Modus befinden, damit Richtlinien zur Kommunikationscompliance riskante Unterhaltungen in privaten Nachrichten und Community-Unterhaltungen in Yammer überprüfen und identifizieren können.

Weitere Informationen zum Konfigurieren von Yammer im nativen Modus finden Sie unter:

- [Übersicht über Yammer nativen Modus in Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Konfigurieren eines Yammer-Netzwerks für den nativen Modus für Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Schritt 5 (erforderlich): Erstellen einer Kommunikationscompliancerichtlinie

> [!IMPORTANT]
> Die Verwendung von PowerShell zum Erstellen und Verwalten von Richtlinien zur Kommunikationscompliance wird nicht unterstützt. Um diese Richtlinien zu erstellen und zu verwalten, müssen Sie die Richtlinienverwaltungssteuerelemente in der [Microsoft 365 Kommunikationscompliancelösung](https://compliance.microsoft.com/supervisoryreview)verwenden.

1. Melden Sie sich <https://compliance.microsoft.com> mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wählen Sie im Microsoft 365 Compliance Center die Option **"Kommunikationscompliance"** aus.

3. Wählen Sie die Registerkarte **Richtlinien** aus.

4. Wählen Sie **"Richtlinie erstellen"** aus, um eine neue Richtlinie aus einer Vorlage zu erstellen und zu konfigurieren, oder um eine benutzerdefinierte Richtlinie zu erstellen und zu konfigurieren.

    Wenn Sie eine Richtlinienvorlage zum Erstellen einer Richtlinie auswählen, führen Sie folgende Aktionen aus:

    - Bestätigen oder aktualisieren Sie den Richtliniennamen. Richtliniennamen können nicht geändert werden, nachdem die Richtlinie erstellt wurde.

    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl von Benutzern oder Gruppen, die Sie ausschließen möchten. Wenn Sie die Vorlage für Interessengruppen verwenden, wählen Sie zwei Gruppen oder zwei Benutzer aus, die für die interne Kommunikation überwacht werden sollen.

    - Wählen Sie die Prüfer für die Richtlinie aus. Prüfer sind einzelne Benutzer, und alle Prüfer müssen über Postfächer verfügen, die auf Exchange Online gehostet werden. Prüfer, die hier hinzugefügt wurden, sind die Prüfer, aus denen Sie wählen können, wenn Sie eine Warnung im Untersuchungs- und Korrekturworkflow eskalieren. Wenn Prüfer zu einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuweisung zur Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess bereitstellt.

    - Wählen Sie ein eingeschränktes Bedingungsfeld aus, in der Regel ein vertraulicher Informationstyp oder ein Schlüsselwortwörterbuch, das auf die Richtlinie angewendet werden soll.

    > [!NOTE]
    > Wenn Sie die [optische Zeichenerkennung (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) aktivieren möchten, um eingebettete oder angefügte Bilder in Nachrichten nach gedrucktem oder handschriftlichem Text zu scannen, der richtlinienbedingungen entspricht, wählen Sie **"Richtlinienbedingungen** und Prozentsatz anpassen"  >   aus, und aktivieren Sie **"Gedruckten oder handschriftlichen Text aus Bildern extrahieren" für die Auswertung.**

    Wenn Sie den Richtlinien-Assistenten zum Erstellen einer benutzerdefinierten Richtlinie verwenden möchten, führen Sie folgende Aktionen aus:

    - Geben Sie der Richtlinie einen Namen und eine Beschreibung. Richtliniennamen lassen sich nach dem Erstellen der Richtlinie nicht mehr ändern.

    - Wählen Sie die Benutzer oder Gruppen aus, die überwacht werden sollen, einschließlich aller Benutzer in Ihrer Organisation, bestimmter Benutzer und Gruppen oder anderer Benutzer und Gruppen, die Sie ausschließen möchten.

    - Wählen Sie die Prüfer für die Richtlinie aus. Prüfer sind einzelne Benutzer, und alle Prüfer müssen über Postfächer verfügen, die auf Exchange Online gehostet werden. Prüfer, die hier hinzugefügt wurden, sind die Prüfer, aus denen Sie wählen können, wenn Sie eine Warnung im Untersuchungs- und Korrekturworkflow eskalieren. Wenn Prüfer zu einer Richtlinie hinzugefügt werden, erhalten sie automatisch eine E-Mail-Nachricht, die sie über die Zuweisung zur Richtlinie benachrichtigt und Links zu Informationen zum Überprüfungsprozess bereitstellt.

    - Wählen Sie die zu scannenden Kommunikationskanäle aus, einschließlich Exchange, Microsoft Teams, Yammer oder Skype for Business. Wenn Sie in Microsoft 365 einen Connector konfiguriert haben, wählen Sie auch aus, dass Quellen von Drittanbietern überprüft werden sollen.

    - Wählen Sie die zu überwachende Kommunikationsrichtung, einschließlich eingehender, ausgehender oder interner Kommunikation.

    - Definieren Sie die [Kommunikationscompliancerichtlinienbedingungen.](communication-compliance-feature-reference.md#ConditionalSettings) Sie können zwischen Nachrichtenadresse, Schlüsselwort, Dateitypen und Übereinstimmungsbedingungen für die Größe auswählen.

    - Wählen Sie aus, ob Sie Typen vertraulicher Informationen einschließen möchten. In diesem Schritt können Sie standardmäßige und benutzerdefinierte Typen vertraulicher Informationen auswählen. Wählen Sie aus vorhandenen benutzerdefinierten Typen vertraulicher Informationen oder benutzerdefinierten Schlüsselwörterbüchern im Assistenten für Kommunikationscompliancerichtlinien aus. Sie können diese Elemente erstellen, bevor Sie den Assistenten bei Bedarf ausführen. Sie können auch neue Typen vertraulicher Informationen im Assistenten für Kommunikationscompliancerichtlinien erstellen.

    - Wählen Sie aus, ob Sie Klassifizierer aktivieren möchten. Klassifizierer können unangemessene Sprache und Bilder erkennen, die im Textkörper von E-Mail-Nachrichten oder anderen Texttypen gesendet oder empfangen werden. Sie können die folgenden integrierten Klassifizierer auswählen: *Bedrohung,* *Anstößigkeit,* *gezielte Belästigung,* Bilder für *Erwachsene,* *Racy-Bilder* und *Bilder von Hary*.

    - Aktivieren Sie [die optische Zeichenerkennung (OCR),](communication-compliance-feature-reference.md#optical-character-recognition-ocr) um eingebettete oder angefügte Bilder in Nachrichten auf gedruckten oder handschriftlichen Text zu überprüfen, der richtlinienbedingungen entspricht. Für benutzerdefinierte Richtlinien müssen eine oder mehrere bedingte Einstellungen, die Text, Schlüsselwörtern, Klassifizierungen oder Typen vertraulicher Informationen zugeordnet sind, in der Richtlinie konfiguriert werden, um die Auswahl der optischen Zeichenerkennungsüberprüfung zu ermöglichen.

    - Definieren Sie den Prozentsatz der zu überprüfenden Kommunikation.

    - Überprüfen Sie Ihre Richtlinienauswahl, und erstellen Sie die Richtlinie.

5. Wählen Sie **"Richtlinie erstellen"** aus, wenn Sie die Vorlagen verwenden, oder **"Übermitteln",** wenn Sie den benutzerdefinierten Richtlinien-Assistenten verwenden.

6. Die Seite **Ihre Richtlinie wurde erstellt** wird mit Richtlinien angezeigt, wann die Richtlinie aktiviert wird und welche Kommunikationen erfasst werden.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Schritt 6 (optional): Erstellen von Benachrichtigungsvorlagen und Konfigurieren der Benutzer-Anonymisierung

Wenn Sie die Möglichkeit haben möchten, auf eine Richtlinienwarnung zu reagieren, indem Sie eine Erinnerung an den zugeordneten Benutzer senden, müssen Sie mindestens eine Benachrichtigungsvorlage in Ihrer Organisation erstellen. Die Felder der Benachrichtigungsvorlage können bearbeitet werden, bevor sie als Teil des Warnungsbereinigungsprozesses gesendet werden, und es wird empfohlen, eine angepasste Benachrichtigungsvorlage für jede Kommunikationscompliancerichtlinie zu erstellen.

Sie können auch die Anonymisierung für angezeigte Benutzernamen aktivieren, wenn Sie Richtlinienüberstimmungen untersuchen und Maßnahmen für Nachrichten ergreifen.

1. Melden Sie sich [https://compliance.microsoft.com](https://compliance.microsoft.com) mithilfe von Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zur **Kommunikationscompliance.**

3. Um die Anonymisierung für Benutzernamen zu konfigurieren, wählen Sie die Registerkarte **"Datenschutz"** aus.

4. Um die Anonymisierung zu aktivieren, wählen Sie **anonymisierte Versionen von Benutzernamen anzeigen** aus.

5. Klicken Sie auf **Speichern**.

6. Navigieren Sie zur Registerkarte **"Benachrichtigungsvorlagen",** und wählen Sie dann **Benachrichtigungsvorlage** erstellen aus.

7. Füllen Sie auf der Seite **"Benachrichtigungsvorlage ändern"** die folgenden Felder aus:

    - Vorlagenname (erforderlich)
    - Senden von (erforderlich)
    - Cc und Bcc (optional)
    - Betreff (erforderlich)
    - Nachrichtentext (erforderlich)

8. Wählen Sie **"Speichern"** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Schritt 7 (optional): Testen Ihrer Kommunikationscompliancerichtlinie

Nachdem Sie eine Richtlinie zur Kommunikationscompliance erstellt haben, sollten Sie diese testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß durchgesetzt werden. Sie können auch [Ihre Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) testen,](create-test-tune-dlp-policy.md) wenn Ihre Richtlinien zur Kommunikationscompliance vertrauliche Informationstypen enthalten. Stellen Sie sicher, dass Sie Ihren Richtlinien Zeit für die Aktivierung geben, damit die Kommunikation erfasst wird, die Sie testen möchten.

Führen Sie die folgenden Schritte aus, um Ihre Kommunikationscompliancerichtlinie zu testen:

1. Öffnen Sie einen E-Mail-Client, Microsoft Teams oder Yammer, während Sie als überwachter Benutzer angemeldet sind, der in der Richtlinie definiert ist, die Sie testen möchten.

2. Senden Sie eine E-Mail, Microsoft Teams Chat oder Yammer Nachricht, die die kriterien erfüllt, die Sie in der Richtlinie zur Kommunikationscompliance definiert haben. Dieser Test kann ein Schlüsselwort, eine Anlagengröße, eine Domäne usw. sein. Stellen Sie sicher, dass Sie feststellen, ob die konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu lenient sind.

    > [!NOTE]
    > Es kann bis zu 24 Stunden dauern, bis E-Mail-Nachrichten in einer Richtlinie vollständig verarbeitet wurden. Es kann bis zu 48 Stunden dauern, bis die Kommunikation in Microsoft Teams- Yammer- und Drittanbieterplattformen vollständig in einer Richtlinie verarbeitet wird.

3. Melden Sie sich bei Microsoft 365 als Prüfer an, der in der Kommunikationscompliance-Richtlinie festgelegt ist. Navigieren Sie zu Benachrichtigungen zur **Kommunikationscompliance,**  >   um die Warnungen für Ihre Richtlinien anzuzeigen.

4. Korrigieren Sie die Warnung mithilfe der Korrektursteuerelemente, und stellen Sie sicher, dass die Warnung ordnungsgemäß aufgelöst wurde.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Kommunikationscompliancerichtlinie abgeschlossen haben, erhalten Sie nach 24 bis 48 Stunden Warnungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf mithilfe der Anleitung in Schritt 5 dieses Artikels.

Weitere Informationen zur Untersuchung von Kommunikationscompliancewarnungen finden Sie unter Untersuchen und Beheben von [Kommunikationscompliancewarnungen.](communication-compliance-investigate-remediate.md)
