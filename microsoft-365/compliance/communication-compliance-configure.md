---
title: Erste Schritte mit der Kommunikationscompliance
description: Einrichten von Richtlinien für die Kommunikations Konformität zum Konfigurieren der Mitarbeiterkommunikation für die Überprüfung.
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
ms.openlocfilehash: b1ce2de627e7068124a1dfd15b84d40a2063d3a2
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210561"
---
# <a name="get-started-with-communication-compliance"></a>Erste Schritte mit der Kommunikationscompliance

Verwenden Sie Kommunikationsrichtlinien zur Erfassung von Mitarbeiter Kommunikationen zur Untersuchung durch interne oder externe Bearbeiter. Weitere Informationen zur Überwachung der Kommunikation in Ihrer Organisation mithilfe von Kommunikationsrichtlinien finden Sie unter [Communication Compliance Policies in Microsoft 365](communication-compliance.md). Wenn Sie überprüfen möchten, wie Contoso eine Kommunikations Konformitätsrichtlinie für die Überwachung anstößiger Sprachen in Microsoft Teams, Exchange Online und jammern von Kommunikation schnell konfiguriert hat, lesen Sie diese [Fallstudie](communication-compliance-case-study.md).

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

Um die **Kommunikation Compliance** als Menüoption im Microsoft 365 Compliance Center zur Verfügung zu stellen, muss Ihnen die Rolle " **Aufsichts Überprüfungs Administrator** " zugewiesen sein. Sie müssen eine neue Rollengruppe für Bearbeiter mit dem **Aufsichts Überprüfungs Administrator**, **der Fallverwaltung**, dem **Kompatibilitäts Administrator**und den **Überprüfungs** Rollen erstellen, um Nachrichten mit Richtlinien Übereinstimmungen zu untersuchen und zu beheben.

### <a name="create-a-new-role-group"></a>Erstellen einer neuen Rollengruppe

1. Melden [https://protection.office.com/permissions](https://protection.office.com/permissions) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. &amp;Wechseln Sie im Security Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie **Erstellen** aus.

4. Geben Sie der neuen Rollengruppe im Feld **Name** einen Anzeigenamen. Wählen Sie **Weiter** aus.

5. Wählen Sie **Rollen auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für **Aufsichts Überprüfungs Administrator**, **Fallverwaltung**, **Kompatibilitäts Administrator**und **Überprüfung**, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

    ![Kommunikation Compliance erforderlich Rollengruppen](../media/communication-compliance-role-groups-1.png)

6. Wählen Sie **Mitglieder auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für alle Benutzer und Gruppen, für die Sie Richtlinien erstellen und Nachrichten mit Richtlinien Übereinstimmungen verwalten möchten, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

7. Wählen Sie **Rollengruppe erstellen** aus, um abzuschließen.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter [Berechtigungen im Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Schritt 2 (erforderlich): Aktivieren des Überwachungsprotokolls

Für die Kommunikations Kompatibilität müssen Überwachungsprotokolle Warnungen anzeigen und von den Prüfern vorgenommene Korrekturaktionen nachverfolgen. Die Überwachungsprotokolle sind eine Zusammenfassung aller Aktivitäten, die einer definierten Organisationsrichtlinie zugeordnet sind, oder wenn sich eine Kommunikations Konformitätsrichtlinie ändert.

Eine Schritt-für-Schritt-Anleitung zum Aktivieren der Überwachung finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](turn-audit-log-search-on-or-off.md). Nachdem Sie die Überwachung aktiviert haben, wird eine Meldung angezeigt, die besagt, dass das Überwachungsprotokoll vorbereitet wird und dass Sie eine Suche in einigen Stunden nach Abschluss der Vorbereitung ausführen können. Sie müssen diese Aktion nur einmal ausführen. Weitere Informationen zur Verwendung des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Schritt 3 (optional): Einrichten von Gruppen für die Kommunikations Kompatibilität

 Wenn Sie eine Konformitätsrichtlinie für die Kommunikation erstellen, definieren Sie, wer Ihre Kommunikation überprüft hat und wer Prüfungen durchführt. In der Richtlinie verwenden Sie e-Mail-Adressen, um Personen oder Gruppen von Personen zu identifizieren. Um das Setup zu vereinfachen, können Sie Gruppen für Personen erstellen, die Ihre Kommunikation überprüft haben, sowie Gruppen für Personen, die diese Kommunikationen überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Verwenden Sie das folgende Diagramm, um Sie bei der Konfiguration von Gruppen in Ihrer Organisation für Kommunikationsrichtlinien zu unterstützen:

| **Richtlinien Mitglied** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Beaufsichtigte Benutzer <br> Nicht überwachte Benutzer | Verteilergruppen <br> Microsoft 365-Gruppen | Dynamische Verteilergruppen |
| Prüfer | Keine | Verteilergruppen <br> Dynamische Verteilergruppen <br> E-Mail-aktivierte Sicherheitsgruppen |
  
Wenn Sie eine Microsoft 365-Gruppe für beaufsichtigte Benutzer auswählen, überwacht die Richtlinie den Inhalt des freigegebenen Postfachs und der Microsoft Teams-Kanäle, die der Gruppe zugeordnet sind. Wenn Sie eine Verteilerliste auswählen, überwacht die Richtlinie einzelne Benutzerpostfächer.

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
>Die Verwendung von PowerShell zum Erstellen und Verwalten von Kommunikations Konformitätsrichtlinien wird nicht unterstützt. Zum Erstellen und Verwalten dieser Richtlinien müssen Sie die Steuerelemente für die Richtlinienverwaltung in der [Microsoft 365 Communication Compliance-Lösung](https://compliance.microsoft.com/supervisoryreview)verwenden.

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
    - Wählen Sie aus, ob Sie Klassifizierungen aktivieren möchten. Klassifizierer können eine ungeeignete Sprache erkennen, die im Textkörper von e-Mail-Nachrichten oder anderen Texttypen gesendet oder empfangen wurde.

    >[!CAUTION]
    >Wir veraltern die integrierte Klassifizierung der **offensiven Sprache** , da Sie eine hohe Anzahl falsch positiver Ergebnisse erzeugt. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse aus dieser entfernen. Es wird empfohlen, stattdessen die integrierten Klassifizierungen " **Bedrohung**", " **Profanität**" und " **Belästigung** " zu verwenden.

    - Definieren Sie den Prozentsatz der zu überprüfenden Kommunikation.
    - Überprüfen Sie Ihre Richtlinienauswahl und erstellen Sie die Richtlinie.

5. Wählen Sie **Richtlinie erstellen** aus, wenn Sie die Vorlagen verwenden oder über **Mitteln** , wenn Sie den Assistenten für benutzerdefinierte Richtlinien verwenden.

6. Die Seite **Ihre Richtlinie wurde erstellt** wird mit Richtlinien angezeigt, wenn die Richtlinie aktiviert wird und welche Kommunikation aufgezeichnet wird.

## <a name="step-6-optional-create-employee-notice-templates"></a>Schritt 6 (optional): Erstellen von Notiz Vorlagen für Mitarbeiter

Wenn Sie die Möglichkeit haben möchten, auf eine Richtlinien Warnung zu reagieren, indem Sie eine Erinnerungs Benachrichtigung an den zugeordneten Mitarbeiter senden, müssen Sie in Ihrer Organisation mindestens eine Notice-Vorlage erstellen. Die Notiz Vorlagenfelder können bearbeitet werden, bevor Sie als Teil des Warnungs Korrekturprozesses gesendet werden, und es wird empfohlen, eine benutzerdefinierte Benachrichtigungsvorlage für jede Kommunikations Konformitätsrichtlinie zu erstellen.

1. Melden [https://compliance.microsoft.com](https://compliance.microsoft.com) Sie sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Communication Compliance**.

3. Wählen Sie die Registerkarte **Notiz Vorlagen** und dann **Notizvorlage erstellen**aus.

4. Füllen Sie auf der Seite **Notizvorlage ändern** die folgenden Felder aus:

    - Hinweis Vorlagenname (erforderlich)
    - Senden von (erforderlich)
    - CC und BCC (optional)
    - Betreff (erforderlich)
    - Nachrichtentext (erforderlich)

5. Wählen Sie **Speichern** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Schritt 7 (optional): Testen der Konformitätsrichtlinie für die Kommunikation

Nachdem Sie eine Kommunikations Konformitätsrichtlinie erstellt haben, empfiehlt es sich, diese zu testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß erzwungen werden. Möglicherweise möchten Sie auch [Ihre Datenverlust Verhinderung (DLP)-Richtlinien testen](create-test-tune-dlp-policy.md) , wenn ihre Kommunikations Konformitätsrichtlinien vertrauliche Informationstypen enthalten. Stellen Sie sicher, dass Ihre Richtlinien Zeit zur Aktivierung geben, damit die zu testende Kommunikation erfasst wird.

Führen Sie die folgenden Schritte aus, um die Konformitätsrichtlinie für Kommunikation zu testen:

1. Öffnen Sie einen e-Mail-Client, Microsoft Teams oder jammern, während Sie sich als überwachten Benutzer angemeldet haben, der in der Richtlinie definiert ist, die Sie testen möchten.
2. Senden Sie eine e-Mail, Microsoft Teams Chat oder Jammer Meldung, die die Kriterien erfüllt, die Sie in der Kommunikations Konformitätsrichtlinie definiert haben. Bei diesem Test kann es sich um ein Stichwort, eine Anlagegröße, eine Domäne usw. handeln. Stellen Sie sicher, dass Sie feststellen, ob ihre konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu nachsichtig sind.

    > [!NOTE]
    > Die Kommunikation in allen Quellkanälen kann bis zu 24 Stunden in Anspruch nehmen, um eine Richtlinie vollständig zu verarbeiten.

3. Melden Sie sich bei Microsoft 365 als Prüfer an, der in der Kommunikations Konformitätsrichtlinie festgelegt ist. Navigieren Sie zu **Kommunikation Compliance**  >  **Alerts** , um die Warnungen für Ihre Richtlinien anzuzeigen.

4. Beheben Sie die Warnung mithilfe der Korrektur Steuerelemente, und stellen Sie sicher, dass die Warnung ordnungsgemäß aufgelöst wurde.
