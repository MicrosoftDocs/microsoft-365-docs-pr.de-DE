---
title: Erste Schritte mit der Kommunikationscompliance
description: Einrichten von Richtlinien für die Kommunikations Konformität zum Konfigurieren der Benutzerkommunikation für die Überprüfung.
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
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: c61529b612079c93e3c175a67fccd32a7c561400
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597576"
---
# <a name="get-started-with-communication-compliance"></a>Erste Schritte mit der Kommunikationscompliance

Verwenden Sie Richtlinien für die Kommunikations Konformität, um die Benutzerkommunikation für die Prüfung durch interne oder externe Bearbeiter zu identifizieren. Weitere Informationen zur Überwachung der Kommunikation in Ihrer Organisation mithilfe von Kommunikationsrichtlinien finden Sie unter [Communication Compliance Policies in Microsoft 365](communication-compliance.md). Wenn Sie überprüfen möchten, wie Contoso eine Kommunikations Konformitätsrichtlinie für die Überwachung anstößiger Sprachen in Microsoft Teams, Exchange Online und jammern von Kommunikation schnell konfiguriert hat, lesen Sie diese [Fallstudie](communication-compliance-case-study.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie mit der Kommunikation Compliance beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-ons bestätigen. Für den Zugriff auf und die Verwendung der Kommunikations Konformität muss Ihre Organisation über eines der folgenden Abonnements oder Add-ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 E3-Abonnement + das Microsoft 365 E5-Compliance-Add-on
- Microsoft 365 E3-Abonnement + Microsoft 365 E5 Insider Risk Management-Add-on
- Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 a3-Abonnement + das Microsoft 365 A5-Konformitäts-Add-on
- Microsoft 365 a3-Abonnement + Microsoft 365 A5 Insider Risk Management-Add-on
- Microsoft 365 G5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 G5-Abonnement + das Microsoft 365 G5-Compliance-Add-on
- Microsoft 365 G5-Abonnement + das Microsoft 365 G5-Insider Risiko Management-Add-on
- Office 365 Enterprise E5-Abonnement (kostenpflichtige oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-on (nicht mehr für neue Abonnements verfügbar, siehe Hinweis)

Benutzern, die in Kommunikationsrichtlinien Richtlinien enthalten sind, muss eine der oben genannten Lizenzen zugewiesen sein.

>[!IMPORTANT]
>Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn die aktuellen Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements übergehen, die die gleichen oder zusätzliche Compliance-Features enthalten.

Wenn Sie keinen Office 365 Enterprise E5-Plan haben und das Insider Risk Management ausprobieren möchten, können Sie [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Abonnement hinzufügen oder [sich für eine Testversion](https://www.microsoft.com/microsoft-365/enterprise) von Office 365 Enterprise E5 anmelden.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Schritt 1 (erforderlich): Aktivieren von Berechtigungen für die Kommunikations Kompatibilität

>[!Important]
>Standardmäßig haben globale Administratoren keinen Zugriff auf Features für die Kommunikations Kompatibilität. Die in diesem Schritt zugewiesenen Rollen sind erforderlich, bevor auf Kommunikations Kompatibilitätsfeatures zugegriffen werden kann.

Es gibt fünf Rollen, die zum Konfigurieren von Berechtigungen zum Verwalten von Kommunikations Kompatibilitätsfeatures verwendet werden. Um die **Kommunikation Compliance** als Menüoption im Microsoft 365 Compliance Center zur Verfügung zu stellen und diese Konfigurationsschritte fortzusetzen, müssen Sie der *Administratorrolle "Communications Compliance"* zugewiesen sein.

Je nachdem, wie Sie Kommunikationsrichtlinien und Warnungen verwalten möchten, müssen Sie eine oder mehrere neue Rollengruppen für Administratoren, Prüfer und Ermittler erstellen. Sie haben die Möglichkeit, Benutzer bestimmten Rollengruppen zuzuweisen, um verschiedene Bereiche der Kommunikations Kompatibilitätsfeatures zu verwalten. Sie können auch eine Rollengruppe erstellen und der Gruppe alle Kommunikations Konformitäts Rollen zuweisen. Erstellen Sie eine einzelne Rollengruppe oder mehrere Rollengruppen, die Ihren Anforderungen an die Compliance-Verwaltung am besten entsprechen.

Wählen Sie unter diesen Rollenoptionen beim Konfigurieren der Rollengruppen für die Kommunikations Konformität aus:

|**Rolle**|**Rollenberechtigungen**|
|:-----|:-----|
| **Communication Compliance-Administrator** | Benutzer, denen diese Rolle zugewiesen ist, können Kommunikationsrichtlinien, globale Einstellungen und Rollengruppen Zuordnungen erstellen, lesen, aktualisieren und löschen. Benutzern, denen diese Rolle zugewiesen ist, können keine Nachrichten Benachrichtigungen angezeigt werden. |
| **Kompatibilitätsanalyse für Kommunikation** | Benutzer, denen diese Rolle zugewiesen ist, können Richtlinien anzeigen, in denen Sie als Bearbeiter zugewiesen werden, Nachrichten Metadaten anzeigen (keine Nachrichteninhalte), an zusätzliche Bearbeiter eskalieren oder Benachrichtigungen an Benutzer senden. Ausstehende Warnungen können von Analysten nicht aufgelöst werden. |
| **Untersuchung der Kommunikations Konformität** | Benutzer, denen diese Rolle zugewiesen ist, können Nachrichten Metadaten und-Inhalte anzeigen, an zusätzliche Bearbeiter eskalieren, zu einem erweiterten eDiscovery-Fall eskalieren, Benachrichtigungen an Benutzer senden und die Warnung lösen. |
| **Communication Compliance Viewer** | Benutzer, denen diese Rolle zugewiesen ist, können auf der Homepage der Communication Compliance auf alle Berichts-Widgets zugreifen und alle Kommunikations Konformitätsberichte anzeigen. |
| **Kommunikation Compliance Case Management** | Benutzer, denen diese Rolle zugewiesen ist, können Fälle verwalten und Benachrichtigungen bearbeiten. Diese Rolle ist für das Erstellen benutzerdefinierter Rollengruppen für Administratoren, Analysten und Ermittler erforderlich. Benutzerdefinierte Gruppen für Viewer benötigen diese Rolle nicht zugewiesen. |

### <a name="option-1-create-a-new-role-group-with-all-communication-compliance-roles"></a>Option 1: Erstellen einer neuen Rollengruppe mit allen Kommunikations Konformitäts Rollen

1. Melden [https://protection.office.com/permissions](https://protection.office.com/permissions) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. &amp;Wechseln Sie im Security Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie **Erstellen** aus.

4. Geben Sie der neuen Rollengruppe im Feld **Name** einen Anzeigenamen. Wählen Sie **Weiter** aus.

5. Wählen Sie **Rollen auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie die Kontrollkästchen für die folgenden Rollen:

    - Communication Compliance-Administrator
    - Kompatibilitätsanalyse für Kommunikation
    - Untersuchung der Kommunikations Konformität
    - Communication Compliance Viewer
    - Kommunikation Compliance Case Management

    ![Kommunikation Compliance Roles](../media/communication-compliance-case-roles.png)

6. Wählen Sie **Hinzufügen** und **Fertig**aus, und wählen Sie dann **weiter** aus, um fortzufahren.

7. Wählen Sie **Mitglieder auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für alle Benutzer und Gruppen, für die Sie Richtlinien erstellen und Nachrichten mit Richtlinien Übereinstimmungen verwalten möchten, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

8. Wählen Sie **Rollengruppe erstellen** aus, um abzuschließen.

### <a name="option-2-create-new-role-groups-with-different-communication-compliance-roles"></a>Option 2: Erstellen neuer Rollengruppen mit unterschiedlichen Kommunikations Konformitäts Rollen

Erstellen Sie mehrere Rollengruppen, um den Zugriff auf Kommunikation und die Zuständigkeiten zwischen verschiedenen Benutzern in Ihrer Organisation zu segmentieren. Für jede neue Rollengruppe weisen Sie unterschiedliche Kommunikations Konformitäts Rollen zu.

1. Melden [https://protection.office.com/permissions](https://protection.office.com/permissions) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. &amp;Wechseln Sie im Security Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie **Erstellen** aus.

4. Geben Sie der neuen Rollengruppe im Feld **Name** einen Anzeigenamen. Wählen Sie **Weiter** aus.

5. Wählen Sie **Rollen auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für die Kommunikations Konformitäts Rollen, die Sie dieser Gruppe zuweisen möchten. Wenn sich diese Rollengruppe beispielsweise für Compliance-Analysten in Ihrer Organisation eignet, wählen Sie die Rolle Compliance *Analysis* and *Communication Compliance Case Management* aus. Wenn diese Rollengruppe für Compliance-Ermittler gilt, wählen Sie die Rollen für die *Kommunikation Compliance Investigation* and *Communications Compliance Case Management* aus.

    ![Kommunikation Compliance Roles](../media/communication-compliance-analysts-role-group.png)

6. Wählen Sie **Hinzufügen** und **Fertig**aus, und wählen Sie dann **weiter** aus, um fortzufahren.

7. Wählen Sie **Mitglieder auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für alle Benutzer und Gruppen, für die Sie Richtlinien erstellen und Nachrichten mit Richtlinien Übereinstimmungen verwalten möchten, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

8. Wählen Sie **Rollengruppe erstellen** aus, um abzuschließen.

9. Erstellen Sie nach Bedarf zusätzliche Rollengruppen für die Kommunikations Konformität.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter [Berechtigungen im Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Schritt 2 (erforderlich): Aktivieren des Überwachungsprotokolls

Für die Kommunikationscompliance sind Überwachungsprotokolle erforderlich, um Warnungen anzuzeigen und die von den Prüfern ergriffenen Abhilfemaßnahmen zu verfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die einer definierten Organisationsrichtlinie zugeordnet sind, oder wenn sich eine Kommunikations Konformitätsrichtlinie ändert.

Eine Schritt-für-Schritt-Anleitung zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](turn-audit-log-search-on-or-off.md). Daraufhin teilt Ihnen eine Meldung mit, dass das Überwachungsprotokoll vorbereitet wird und Sie in ein paar Stunden nach Abschluss der Vorbereitung eine Suche durchführen können. Sie müssen diese Aktion nur einmal ausführen. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Schritt 3 (optional): Einrichten von Gruppen für die Kommunikations Kompatibilität

 Wenn Sie eine Konformitätsrichtlinie für die Kommunikation erstellen, definieren Sie, wer Ihre Kommunikation überprüft hat und wer Prüfungen durchführt. In der Richtlinie verwenden Sie e-Mail-Adressen, um Personen oder Gruppen von Personen zu identifizieren. Um das Setup zu vereinfachen, können Sie Gruppen für Personen erstellen, die Ihre Kommunikation überprüft haben, sowie Gruppen für Personen, die diese Kommunikationen überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Verwenden Sie das folgende Diagramm, um Sie bei der Konfiguration von Gruppen in Ihrer Organisation für Kommunikationsrichtlinien zu unterstützen:

| **Richtlinien Mitglied** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Beaufsichtigte Benutzer <br> Nicht überwachte Benutzer | Verteilergruppen <br> Microsoft 365-Gruppen | Dynamische Verteilergruppen |
| Prüfer | Keine | Verteilergruppen <br> Dynamische Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen |
  
Wenn Sie eine Verteilergruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle e-Mails von jedem Benutzer in der Verteilergruppe. Wenn Sie eine Microsoft 365-Gruppe in der Richtlinie zuweisen, überwacht die Richtlinie alle e-Mails, die an diese Gruppe gesendet werden, und nicht die einzelnen e-Mails, die von den einzelnen Gruppenmitgliedern empfangen werden.

Wenn Sie eine Organisation mit einer lokalen Exchange-Bereitstellung oder einem externen e-Mail-Anbieter sind und Microsoft Teams-Chats für Ihre Benutzer überwachen möchten, müssen Sie eine Verteilergruppe für die Benutzer mit lokalen oder externen Postfächern erstellen, die überwacht werden sollen. Später in diesen Schritten weisen Sie diese Verteilergruppe im Richtlinien-Assistenten als über **wachte Benutzer und Gruppen** Auswahl zu.

>[!IMPORTANT]
>Sie müssen eine Anforderung mit dem Microsoft-Support einreichen, damit Ihre Organisation die grafische Benutzeroberfläche im Security & Compliance Center verwenden kann, um nach teamchatdaten für lokale Benutzer zu suchen. Weitere Informationen finden Sie unter [searching Cloud-based Mailboxes for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).

Weitere Informationen zum Einrichten von Gruppen finden Sie unter:

- [Erstellen und Verwalten von Verteilergruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Übersicht über Microsoft 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Schritt 4 (optional): überprüfen, ob sich der Jammer-Mandant im einheitlichen Modus befindet

Im nativen Modus befinden sich alle Yammer-Benutzer in Azure Active Directory (AAD), alle Gruppen sind Office 365-Gruppen, und alle Dateien werden in SharePoint Online gespeichert. Ihr jammern-Mandant muss sich im einheitlichen Modus befinden, damit Kommunikationsrichtlinien Konformitätsrichtlinien gefährliche Unterhaltungen in privaten Nachrichten und Community-Unterhaltungen in jammern überprüfen und identifizieren können.

Weitere Informationen zum Konfigurieren von jammern im einheitlichen Modus finden Sie unter:

- [Übersicht über den einheitlichen Modus "jammern" in Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [Konfigurieren eines Yammer-Netzwerks für den nativen Modus für Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Schritt 5 (erforderlich): Erstellen einer Kommunikations Konformitätsrichtlinie
  
>[!Important]
>Die Verwendung von PowerShell zum Erstellen und Verwalten von Richtlinien zur Kommunikationscompliance wird nicht unterstützt. Zum Erstellen und Verwalten dieser Richtlinien müssen Sie die Steuerelemente für die Richtlinienverwaltung in der [Microsoft 365 Communication Compliance-Lösung](https://compliance.microsoft.com/supervisoryreview)verwenden.

1. Melden [https://compliance.microsoft.com](https://compliance.microsoft.com) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wählen Sie im Microsoft 365 Compliance Center die Option **Communication Compliance**aus.
  
3. Wählen Sie die Registerkarte **Richtlinien** aus.

4. Wählen Sie **Richtlinie erstellen** aus, um eine neue Richtlinie aus einer Vorlage zu erstellen und zu konfigurieren oder um eine benutzerdefinierte Richtlinie zu erstellen und zu konfigurieren.

    Wenn Sie eine Richtlinienvorlage zum Erstellen einer Richtlinie auswählen, können Sie Folgendes tun:

    - Bestätigen oder aktualisieren Sie den Richtliniennamen. Richtliniennamen können nach der Erstellung der Richtlinie nicht mehr geändert werden.
    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl von Benutzern oder Gruppen, die Sie ausschließen möchten.
    - Wählen Sie die Bearbeiter für die Richtlinie aus. Bearbeiter sind einzelne Benutzer, und alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden. Hier hinzugefügte Bearbeiter sind die Bearbeiter, aus denen Sie auswählen können, wenn Sie eine Warnung im Workflow "Untersuchung" und "Korrektur" eskalieren. Wenn Bearbeiter einer Richtlinie hinzugefügt werden, erhalten Sie automatisch eine e-Mail-Nachricht, die Sie über die Zuweisung zur Richtlinie benachrichtigt und Links zu Informationen über den Überprüfungsprozess enthält.
    - Wählen Sie ein eingeschränktes Bedingungsfeld, normalerweise einen vertraulichen Infotyp oder ein Stichwort Wörterbuch, das auf die Richtlinie angewendet werden soll.

    Wenn Sie den Richtlinien-Assistenten verwenden, um eine benutzerdefinierte Richtlinie zu erstellen, müssen Sie Folgendes tun:

    - Geben Sie der Richtlinie einen Namen und eine Beschreibung. Richtliniennamen können nach der Erstellung der Richtlinie nicht mehr geändert werden.
    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich aller Benutzer in Ihrer Organisation, bestimmter Benutzer und Gruppen oder anderer Benutzer und Gruppen, die Sie ausschließen möchten.
    - Wählen Sie die Bearbeiter für die Richtlinie aus. Bearbeiter sind einzelne Benutzer, und alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden. Hier hinzugefügte Bearbeiter sind die Bearbeiter, aus denen Sie auswählen können, wenn Sie eine Warnung im Workflow "Untersuchung" und "Korrektur" eskalieren. Wenn Bearbeiter einer Richtlinie hinzugefügt werden, erhalten Sie automatisch eine e-Mail-Nachricht, die Sie über die Zuweisung zur Richtlinie benachrichtigt und Links zu Informationen über den Überprüfungsprozess enthält.
    - Wählen Sie die zu scannenden Kommunikationskanäle aus, einschließlich Exchange, Microsoft Teams, jammern oder Skype for Business. Sie können auch Drittanbieterquellen überprüfen, wenn Sie einen Connector in Microsoft 365 konfiguriert haben.
    - Wählen Sie die zu überwachende Kommunikationsrichtung, einschließlich eingehende, ausgehende oder interne Kommunikation.
    - Definieren Sie die [Bedingungen](communication-compliance-feature-reference.md#ConditionalSettings)für die Kommunikation-Konformitätsrichtlinie. Sie können zwischen Nachrichtenadresse, Stichwort, Dateitypen und Größen Übereinstimmungsbedingungen wählen.
    - Wählen Sie aus, ob Sie vertrauliche Informationstypen einbeziehen möchten. In diesem Schritt können Sie Standard-und benutzerdefinierte vertrauliche Informationstypen auswählen. Wählen Sie unter vorhandene benutzerdefinierte vertrauliche Informationstypen oder benutzerdefinierte Schlüsselwörter Wörterbücher im Assistenten für die Kommunikation mit Kompatibilitätsrichtlinien aus. Sie können diese Elemente erstellen, bevor Sie den Assistenten ausführen, falls erforderlich. Sie können auch neue vertrauliche Informationstypen aus dem Assistenten für Kommunikations Konformitätsrichtlinien erstellen.
    - Wählen Sie aus, ob Sie Klassifizierungen aktivieren möchten. Klassifizierer können ungeeignete Sprache und Bilder erkennen, die im Textkörper von e-Mail-Nachrichten oder anderen Texttypen gesendet oder empfangen wurden. Sie können die folgenden integrierten Klassifizierungen auswählen: *Bedrohung*, *Profanität*, *gezielte Belästigung*, *Erwachsene Bilder*, *rassige Bilder*und *blutige Bilder*.

    >[!CAUTION]
    >Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse aus dieser entfernen. Es wird empfohlen, stattdessen die integrierten Klassifizierungen " **Bedrohung**", " **Profanität**" und " **gezielte Belästigung** " zu verwenden.

    - Definieren Sie den Prozentsatz der zu überprüfenden Kommunikation.
    - Überprüfen Sie Ihre Richtlinienauswahl und erstellen Sie die Richtlinie.

5. Wählen Sie **Richtlinie erstellen** aus, wenn Sie die Vorlagen verwenden oder über **Mitteln** , wenn Sie den Assistenten für benutzerdefinierte Richtlinien verwenden.

6. Die Seite **Ihre Richtlinie wurde erstellt** wird mit Richtlinien angezeigt, wenn die Richtlinie aktiviert wird und welche Kommunikation aufgezeichnet wird.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Schritt 6 (optional): Erstellen von Benachrichtigungsvorlagen und Konfigurieren der Benutzer Anonymisierung

Wenn Sie die Möglichkeit haben möchten, auf eine Richtlinien Warnung zu reagieren, indem Sie eine Erinnerungs Benachrichtigung an den zugeordneten Benutzer senden, müssen Sie mindestens eine Notice-Vorlage in Ihrer Organisation erstellen. Die Notiz Vorlagenfelder können bearbeitet werden, bevor Sie als Teil des Warnungs Korrekturprozesses gesendet werden, und es wird empfohlen, eine benutzerdefinierte Benachrichtigungsvorlage für jede Kommunikations Konformitätsrichtlinie zu erstellen.

Sie können auch festlegen, dass für angezeigte Benutzernamen Anonymisierung aktiviert wird, wenn Sie Richtlinien Übereinstimmungen untersuchen und Aktionen für Nachrichten ausführen.

1. Melden [https://compliance.microsoft.com](https://compliance.microsoft.com) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Communication Compliance**.

3. Um die Anonymisierung für Benutzernamen zu konfigurieren, wählen Sie die Registerkarte **Datenschutz** aus.

4. Um die Anonymisierung zu aktivieren, wählen Sie **Anonyme Versionen von Benutzernamen anzeigen**aus.

5. Wählen Sie **Speichern** aus.

6. Navigieren Sie zur Registerkarte **Notiz Vorlagen** , und wählen Sie dann **Notizvorlage erstellen**aus.

7. Füllen Sie auf der Seite **Notizvorlage ändern** die folgenden Felder aus:

    - Vorlagenname (erforderlich)
    - Senden von (erforderlich)
    - CC und BCC (optional)
    - Betreff (erforderlich)
    - Nachrichtentext (erforderlich)

8. Wählen Sie **Speichern** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Schritt 7 (optional): Testen der Konformitätsrichtlinie für die Kommunikation

Nachdem Sie eine Kommunikations Konformitätsrichtlinie erstellt haben, empfiehlt es sich, diese zu testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß erzwungen werden. Möglicherweise möchten Sie auch [Ihre Datenverlust Verhinderung (DLP)-Richtlinien testen](create-test-tune-dlp-policy.md) , wenn ihre Kommunikations Konformitätsrichtlinien vertrauliche Informationstypen enthalten. Stellen Sie sicher, dass Ihre Richtlinien Zeit zur Aktivierung geben, damit die zu testende Kommunikation erfasst wird.

Führen Sie die folgenden Schritte aus, um die Konformitätsrichtlinie für Kommunikation zu testen:

1. Öffnen Sie einen e-Mail-Client, Microsoft Teams oder jammern, während Sie sich als überwachten Benutzer angemeldet haben, der in der Richtlinie definiert ist, die Sie testen möchten.
2. Senden Sie eine e-Mail, Microsoft Teams Chat oder Jammer Meldung, die die Kriterien erfüllt, die Sie in der Kommunikations Konformitätsrichtlinie definiert haben. Bei diesem Test kann es sich um ein Stichwort, eine Anlagegröße, eine Domäne usw. handeln. Stellen Sie sicher, dass Sie feststellen, ob ihre konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu nachsichtig sind.

    > [!NOTE]
    > Die Kommunikation in allen Quellkanälen kann bis zu 24 Stunden in Anspruch nehmen, um eine Richtlinie vollständig zu verarbeiten.

3. Melden Sie sich bei Microsoft 365 als Prüfer an, der in der Kommunikations Konformitätsrichtlinie festgelegt ist. Navigieren Sie zu **Kommunikation Compliance**  >  **Alerts** , um die Warnungen für Ihre Richtlinien anzuzeigen.

4. Beheben Sie die Warnung mithilfe der Korrektur Steuerelemente, und stellen Sie sicher, dass die Warnung ordnungsgemäß aufgelöst wurde.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie diese Schritte zum Erstellen Ihrer ersten Kommunikations Konformitätsrichtlinie abgeschlossen haben, erhalten Sie nach etwa 24 Stunden Warnungen von Aktivitätsindikatoren. Konfigurieren Sie zusätzliche Richtlinien nach Bedarf mithilfe der Anleitungen in Schritt 5 dieses Artikels.

Weitere Informationen zum Untersuchen von Benachrichtigungen über die Kommunikations Konformität finden Sie unter über [prüfen und Beheben von Benachrichtigungen zur Kommunikations Konformität](communication-compliance-investigate-remediate.md).
