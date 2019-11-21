---
title: Konfigurieren der Kommunikations Kompatibilität für Microsoft 365 (Vorschau)
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
description: Einrichten von Richtlinien für die Kommunikations Konformität zum Konfigurieren der Mitarbeiterkommunikation für die Überprüfung.
ms.openlocfilehash: 0a830914a22968119d836e2190a6f133d91fd305
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755603"
---
# <a name="configure-communication-compliance-for-microsoft-365-preview"></a>Konfigurieren der Kommunikations Kompatibilität für Microsoft 365 (Vorschau)

> [!IMPORTANT]
> Dieses Thema bezieht sich auf die Konfiguration der Kommunikations Kompatibilität in einem Microsoft 365-Abonnement. Wenn Sie Aufsichtsrichtlinien für ein Office 365-Abonnement konfigurieren möchten, finden Sie weitere Informationen unter [configure Supervision for Office 365](supervision-policies.md).

Verwenden Sie Kommunikationsrichtlinien zur Erfassung von Mitarbeiter Kommunikationen zur Untersuchung durch interne oder externe Bearbeiter. Weitere Informationen zur Überwachung der Kommunikation in Ihrer Organisation mithilfe von Kommunikationsrichtlinien finden Sie unter [Communication Compliance Policies in Microsoft 365](communication-compliance.md).

> [!NOTE]
> Benutzer, die über Kommunikations Konformitätsrichtlinien überwacht werden, müssen über eine Microsoft 365 E5-Konformitäts Lizenz, eine Office 365 Enterprise E3-Lizenz mit dem Add-on für die erweiterte Kompatibilität verfügen oder in einem Office 365 Enterprise E5-Abonnement enthalten sein.
> Wenn Sie über keinen vorhandenen Enterprise E5-Plan verfügen und die Kommunikations Kompatibilität testen möchten, können Sie [sich für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Führen Sie die folgenden Schritte aus, um die Kommunikations Konformität in Ihrer Microsoft 365-Organisation einzurichten und zu verwenden:
  
- **Schritt 1 (optional)**: Einrichten [von Gruppen für die Kommunikations Kompatibilität](#step-1-set-up-groups-for-communication-compliance-optional) 

    Bevor Sie mit der Verwendung der Kommunikations Konformität beginnen, müssen Sie ermitteln, wer die Kommunikation überprüft und wer Prüfungen durchführt. Wenn Sie mit nur wenigen Benutzern beginnen möchten, um zu sehen, wie die Kommunikations Kompatibilität funktioniert, können Sie das Einrichten von Gruppen jetzt überspringen.

- **Schritt 2 (erforderlich)**: [Stellen Sie die Kommunikations Konformität in Ihrer Organisation zur Verfügung](#step-2-make-communication-compliance-available-in-your-organization-required) .

    Fügen Sie sich selbst der **Aufsichts Überprüfungs Administrator** Rolle hinzu, damit Sie Richtlinien einrichten können. Sie müssen außerdem eine Gruppe mit dem **Aufsichts Überprüfungs Administrator**, der **Fallverwaltung** und den **Überprüfungs** Rollen für Personen oder Gruppen erstellen, die Ermittlungs-und Korrekturaktionen für Nachrichten mit Richtlinien Übereinstimmungen durchführen sollen. Jeder, dem diese Rollen zugewiesen sind, kann im Microsoft 365 Compliance Center auf die Seite " **Kommunikations Kompatibilität** " zugreifen. Wenn beschreibbar-e-Mail auf Exchange Online gehostet wird, muss jeder Prüfer über [Remote-PowerShell-Zugriff auf Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)verfügen.

- **Schritt 3 (erforderlich)**: [Einrichten einer Kommunikations Konformitätsrichtlinie](#step-3-create-a-communication-compliance-policy-required)

    Sie erstellen Richtlinien für die Kommunikations Konformität im Microsoft 365 Compliance Center. Diese Richtlinien definieren, welche Kommunikation in Ihrer Organisation überprüft werden muss, und gibt an, wer Prüfungen durchführt. Zu den Kommunikationen Gehören e-Mail, Microsoft Teams, Skype for Business und Platt Form Kommunikation von Drittanbietern (wie Facebook, Twitter usw.).

- **Schritt 4 (optional)**: [Erstellen von Notiz Vorlagen für Mitarbeiter](#step-4-create-employee-notice-templates-optional)

    Erstellen benutzerdefinierter Benachrichtigungsvorlagen zum Senden von e-Mail-Benachrichtigungen an Mitarbeiter als Korrekturoption für Richtlinien Übereinstimmungen.

- **Schritt 5 (optional)**: [Testen der Konformitätsrichtlinie für die Kommunikation](#step-5-test-your-communication-compliance-policy-optional)

    Testen Sie Ihre Kommunikations Konformitätsrichtlinie, um sicherzustellen, dass Sie wie gewünscht funktioniert. Es ist wichtig sicherzustellen, dass Ihre Konformitäts Strategie ihre Standards erfüllt.

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a>Schritt 1: Einrichten von Gruppen für die Kommunikations Kompatibilität (optional)

 Wenn Sie eine Konformitätsrichtlinie für die Kommunikation erstellen, definieren Sie, wer Ihre Kommunikation überprüft hat und wer Prüfungen durchführt. In der Richtlinie verwenden Sie e-Mail-Adressen, um Personen oder Gruppen von Personen zu identifizieren. Um das Setup zu vereinfachen, können Sie Gruppen für Personen erstellen, die Ihre Kommunikation überprüft haben, sowie Gruppen für Personen, die diese Kommunikationen überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Sie möchten beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen, oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Verwenden Sie das folgende Diagramm, um Sie bei der Konfiguration von Gruppen in Ihrer Organisation für Kommunikationsrichtlinien zu unterstützen:

| **Richtlinien Mitglied** | **Unterstützte Gruppen** | **Nicht unterstützte Gruppen** |
|:-----|:-----|:-----|
|Beaufsichtigte Benutzer <br> Nicht überwachte Benutzer | Verteilergruppen <br> Office 365-Gruppen | Dynamische Verteilergruppen |
| Prüfer | E-Mail-aktivierte Sicherheitsgruppen  | Verteilergruppen <br> Dynamische Verteilergruppen |
  
Wenn Sie eine Office 365 Gruppe für beaufsichtigte Benutzer auswählen, überwacht die Richtlinie den Inhalt des freigegebenen Office 365 Postfachs und der Microsoft Teams-Kanäle, die der Gruppe zugeordnet sind. Wenn Sie eine Verteilerliste auswählen, überwacht die Richtlinie einzelne Benutzerpostfächer.

Weitere Informationen zum Einrichten von Gruppen finden Sie unter:

- [Erstellen und Verwalten von Verteilergruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Verwalten von E-Mail-aktivierten Sicherheitsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Übersicht über Office 365 Gruppen](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a>Schritt 2: Bereitstellen der Kommunikations Kompatibilität in Ihrer Organisation (erforderlich)

Um die **Kommunikation Compliance** als Menüoption im Microsoft 365 Compliance Center zur Verfügung zu stellen, muss Ihnen die Rolle " **Aufsichts Überprüfungs Administrator** " zugewiesen sein. Um Nachrichten mit Richtlinien Übereinstimmungen zu untersuchen und zu beheben, müssen Sie darüber hinaus eine Gruppe für Bearbeiter mit dem **Aufsichts Überprüfungs Administrator**, der **Fallverwaltung** und den **Überprüfungs** Rollen erstellen.

### <a name="create-a-new-role-group"></a>Erstellen einer neuen Rollengruppe

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Berechtigungen**. Wählen Sie den Link zum Anzeigen und Verwalten von Rollen in Office 365 aus.

3. Wählen Sie **Erstellen** aus.

4. Geben Sie der neuen Rollengruppe im Feld **Name** einen Anzeigenamen. Wählen Sie **Weiter** aus.

5. Wählen Sie **Rollen auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für **Aufsichts Überprüfungs Administrator**, **Fallverwaltung**und **Überprüfung**, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

6. Wählen Sie **Mitglieder auswählen** aus, und klicken Sie dann auf **Hinzufügen**. Aktivieren Sie das Kontrollkästchen für alle Benutzer und Gruppen, für die Sie Richtlinien erstellen und Nachrichten mit Richtlinien Übereinstimmungen verwalten möchten, und wählen Sie dann **Hinzufügen** und **Fertig**aus. Wählen Sie **Weiter** aus.

7. Wählen Sie **Rollengruppe erstellen** aus, um abzuschließen.

Weitere Informationen zu Rollengruppen und Berechtigungen finden Sie unter [Berechtigungen im Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-3-create-a-communication-compliance-policy-required"></a>Schritt 3: Erstellen einer Konformitätsrichtlinie für die Kommunikation (erforderlich)
  
1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wählen Sie im Microsoft 365 Compliance Center die Option **Communication Compliance**aus.
  
3. Wählen Sie die Registerkarte **Richtlinien** aus.

4. Wählen Sie **Richtlinie erstellen** aus, um eine neue Richtlinie aus einer Vorlage zu erstellen und zu konfigurieren oder um eine benutzerdefinierte Richtlinie zu erstellen und zu konfigurieren.

    Wenn Sie eine Richtlinienvorlage zum Erstellen einer Richtlinie auswählen, können Sie Folgendes tun:

    - Bestätigen oder aktualisieren Sie den Richtliniennamen. Richtliniennamen können nach der Erstellung der Richtlinie nicht mehr geändert werden.
    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl von Benutzern oder Gruppen, die Sie ausschließen möchten.
    - Wählen Sie die Bearbeiter für die Richtlinie aus. Bearbeiter können einzelne Benutzer oder [e-Mail-aktivierte Sicherheitsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)sein. Alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden.
    - Wählen Sie ein eingeschränktes Bedingungsfeld, normalerweise einen vertraulichen Infotyp oder ein Stichwort Wörterbuch, das auf die Richtlinie angewendet werden soll.

    Wenn Sie den Richtlinien-Assistenten verwenden, um eine benutzerdefinierte Richtlinie zu erstellen, müssen Sie Folgendes tun:

    - Geben Sie der Richtlinie einen Namen und eine Beschreibung. Richtliniennamen können nach der Erstellung der Richtlinie nicht mehr geändert werden.
    - Wählen Sie die zu überwachenden Benutzer oder Gruppen aus, einschließlich der Auswahl aller Benutzer in Ihrer Organisation, bestimmter Benutzer und Gruppen oder anderer Benutzer und Gruppen, die Sie ausschließen möchten. -
    - Wählen Sie die Bearbeiter für die Richtlinie aus. Bearbeiter können einzelne Benutzer oder [e-Mail-aktivierte Sicherheitsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)sein. Alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden.
    - Wählen Sie die zu scannenden Kommunikationskanäle aus, einschließlich Exchange, Microsoft Teams oder Skype for Business. Sie können auch Drittanbieterquellen überprüfen, wenn Sie einen Connector in Microsoft 365 konfiguriert haben.
    - Wählen Sie die zu überwachende Kommunikationsrichtung, einschließlich eingehende, ausgehende oder interne Kommunikation.
    - Definieren Sie die [Bedingungen](communication-compliance-feature-reference.md#ConditionalSettings)für die Kommunikation-Konformitätsrichtlinie. Sie können zwischen Nachrichtenadresse, Stichwort, Dateitypen und Größen Übereinstimmungsbedingungen wählen.
    - Wählen Sie aus, ob Sie vertrauliche Informationstypen einbeziehen möchten. Hier können Sie Standard-und benutzerdefinierte vertrauliche Informationstypen auswählen. Auswählen von vorhandenen benutzerdefinierten vertraulichen Informationstypen oder benutzerdefinierten Schlüsselwörter Wörterbüchern im Assistenten für Kommunikations Konformitätsrichtlinien können Sie diese Elemente erstellen, bevor Sie den Assistenten bei Bedarf ausführen. Bei Bedarf können Sie auch neue vertrauliche Informationstypen aus dem Assistenten für die Kommunikation mit Kompatibilitätsrichtlinien erstellen.
    - Wählen Sie aus, ob Sie das anstößige Sprachmodell aktivieren möchten. Dadurch wird eine ungeeignete Sprache erkannt, die im Textkörper von e-Mail-Nachrichten gesendet oder empfangen wird.
    - Definieren Sie den Prozentsatz der zu überprüfenden Kommunikation.
    - Überprüfen Sie Ihre Richtlinienauswahl und erstellen Sie die Richtlinie.

5. Wählen Sie **Richtlinie erstellen** aus, wenn Sie die Vorlagen verwenden oder über **Mitteln** , wenn Sie den Assistenten für benutzerdefinierte Richtlinien verwenden.

6. Die Seite **Ihre Richtlinie wurde erstellt** wird mit Richtlinien angezeigt, wenn die Richtlinie aktiviert wird und die Kommunikation aufgezeichnet wird.

## <a name="step-4-create-employee-notice-templates-optional"></a>Schritt 4: Erstellen von Employee Notice-Vorlagen (optional)

Wenn Sie die Möglichkeit haben möchten, auf eine Richtlinien Warnung zu reagieren, indem Sie eine Erinnerungs Benachrichtigung an den zugeordneten Mitarbeiter senden, müssen Sie in Ihrer Organisation mindestens eine Notice-Vorlage erstellen. Die Notiz Vorlagenfelder können vor dem Senden als Teil des Warnungs Korrekturprozesses bearbeitet werden, und es wird empfohlen, eine benutzerdefinierte Benachrichtigungsvorlage für jede Kommunikations Konformitätsrichtlinie zu erstellen.

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Communication Compliance**.

3. Wählen Sie die Registerkarte **Notiz Vorlagen** und dann **Notizvorlage erstellen**aus.

4. Füllen Sie auf der Seite **Notizvorlage ändern** die folgenden Felder aus:

    - Hinweis Vorlagenname (erforderlich)
    - Senden von (erforderlich)
    - CC und BCC (optional)
    - Betreff (erforderlich)
    - Nachrichtentext (erforderlich)

5. Wählen Sie **Speichern** aus, um die Benachrichtigungsvorlage zu erstellen und zu speichern.

## <a name="step-5-test-your-communication-compliance-policy-optional"></a>Schritt 5: Testen der Konformitätsrichtlinie für Kommunikation (optional)

Nachdem Sie eine Kommunikations Konformitätsrichtlinie erstellt haben, sollten Sie testen, um sicherzustellen, dass die von Ihnen definierten Bedingungen von der Richtlinie ordnungsgemäß erzwungen werden. Möglicherweise möchten Sie auch [Ihre Datenverlust Verhinderung (DLP)-Richtlinien testen](create-test-tune-dlp-policy.md) , wenn ihre Kommunikations Konformitätsrichtlinien vertrauliche Informationstypen enthalten. Stellen Sie sicher, dass Ihre Richtlinien Zeit zur Aktivierung geben, damit die zu testende Kommunikation erfasst wird.

Führen Sie die folgenden Schritte aus, um die Konformitätsrichtlinie für Kommunikation zu testen:

1. Öffnen Sie einen e-Mail-Client oder Microsoft Teams, der als überwachten Benutzer angemeldet ist, der in der Richtlinie definiert ist, die Sie testen möchten.
2. Senden Sie eine e-Mail oder einen Microsoft Teams-Chat, die die Kriterien erfüllen, die Sie in der Kommunikations Konformitätsrichtlinie definiert haben. Hierbei kann es sich um ein Stichwort, eine Anlagegröße, eine Domäne usw. handeln. Stellen Sie sicher, dass Sie feststellen, ob die konfigurierten bedingten Einstellungen in der Richtlinie zu restriktiv oder zu nachsichtig sind.

    > [!NOTE]
    > Die Kommunikation in allen Quellkanälen kann bis zu 24 Stunden in Anspruch nehmen, um eine Richtlinie vollständig zu verarbeiten.

3. Melden Sie sich bei Microsoft 365 als Prüfer an, der in der Kommunikations Konformitätsrichtlinie festgelegt ist. Navigieren Sie zu **Kommunikation Compliance** > **Alerts** , um die Warnungen für Ihre Richtlinien anzuzeigen.

4. Beheben Sie die Warnung mithilfe der Korrektur Steuerelemente, und stellen Sie sicher, dass die Warnung ordnungsgemäß aufgelöst wurde.
