---
title: Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail Nachrichten
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zum Erstellen von Nachrichtenfluss Regeln (Transportregeln) zum Verschlüsseln und Entschlüsseln von Nachrichten mit Office 365 Nachrichtenverschlüsselung erlernen.
ms.openlocfilehash: f9e9440c40b68f36d0dcca069dcd0797412af184
ms.sourcegitcommit: f70f75b9dd163c00a3c6bc4b9f9b055e90c50367
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "43790704"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail Nachrichten

Als globaler Administrator können Sie e-Mail-Flussregeln erstellen (auch als Transportregeln bezeichnet), um e-Mail-Nachrichten zu schützen, die Sie senden und empfangen. Sie können Regeln einrichten, um ausgehende e-Mail-Nachrichten zu verschlüsseln und Verschlüsselung von verschlüsselten Nachrichten aus Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten zu entfernen, die von Ihrer Organisation gesendet werden. Sie können die Exchange-Verwaltungskonsole (EAC) oder Exchange Online PowerShell verwenden, um diese Regeln zu erstellen. Zusätzlich zu den allgemeinen Verschlüsselungsregeln können Sie auch die Aktivierung oder Deaktivierung einzelner Nachrichtenverschlüsselungsoptionen für Endbenutzer auswählen.

Sie können keine eingehenden e-Mails von Absendern außerhalb Ihrer Organisation verschlüsseln.

Wenn Sie kürzlich von AD RMS zu Azure Information Protection migriert haben, müssen Sie Ihre vorhandenen Nachrichtenfluss Regeln überprüfen, um sicherzustellen, dass Sie in ihrer neuen Umgebung weiterhin funktionieren. Darüber hinaus müssen Sie die vorhandenen Nachrichtenfluss Regeln aktualisieren, wenn Sie die neuen Funktionen zur Office 365 Nachrichtenverschlüsselung (OM) über Azure Information Protection nutzen möchten. Andernfalls erhalten die Benutzer weiterhin verschlüsselte e-Mails, die das vorherige HTML-Anlagenformat anstelle der neuen nahtlosen OM-Umgebung verwenden. Wenn Sie noch kein OM eingerichtet haben, finden Sie weitere Informationen unter [Einrichten der neuen Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md) .

Informationen zu den Komponenten, die Nachrichtenfluss Regeln bilden und wie Nachrichtenfluss Regeln funktionieren, finden Sie unter [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Weitere Informationen zur Funktionsweise von Nachrichtenfluss Regeln mit Azure Information Protection finden Sie unter [Configuring Exchange Online Mail Flow Rules for Azure Information Protection Labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Bei Exchange-Hybrid Umgebungen können lokale Benutzer verschlüsselte e-Mails nur mit OM senden, wenn e-Mails über Exchange Online weitergeleitet werden. Um om in einer Exchange-Hybridumgebung zu konfigurieren, müssen Sie zunächst [die Hybrid Konfiguration mit dem Assistenten für die Hybrid Konfiguration konfigurieren](https://docs.microsoft.com/Exchange/exchange-hybrid) und dann [Mail so konfigurieren, dass Sie vom e-Mail-Server zu Office 365 fließt](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Nachdem Sie die e-Mail-Nachricht für den Ablauf Office 365 konfiguriert haben, können Sie mithilfe dieser Anleitung Nachrichtenfluss Regeln für OM konfigurieren.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Erstellen von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten mit den neuen OM-Funktionen

Sie können e-Mail-Flussregeln für die Auslösung der Nachrichtenverschlüsselung mit den neuen OM-Funktionen mithilfe der Exchange-Verwaltungskonsole definieren.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Erstellen einer Regel zum Verschlüsseln von e-Mail-Nachrichten mit den neuen OM-Funktionen mithilfe der Exchange-Verwaltungskonsole

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** \> Center **Exchange**aus.

4. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> wählen Sie **Neues** ![neues Symbol neue **Regel erstellen**aus. Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Geben Sie unter **Name**einen Namen für die Regel ein, beispielsweise Verschlüsseln von e-Mails für DrToniRamos@hotmail.com.

6. Wählen Sie unter **Diese Regel anwenden, wenn** eine Bedingung aus, und geben Sie ggf. einen Wert ein. Geben Sie beispielsweise Folgendes ein, um Nachrichten an "DrToniRamos@hotmail.com" zu verschlüsseln:

   1. Wählen Sie unter **Diese Regel anwenden, wenn****the recipient is** (Der Empfänger ist) aus.

   2. Wählen Sie in der Kontaktliste einen vorhandenen Namen aus, oder geben Sie im Feld **Namen prüfen** eine neue E-Mail-Adresse ein.

      - Um einen vorhandenen Namen auszuwählen, wählen Sie ihn in der Liste aus, und klicken Sie dann auf **OK**.

      - Geben Sie zum Eingeben eines neuen Namens eine e-Mail-Adresse in das Feld **Namen überprüfen** ein, und wählen Sie \> dann **Namen überprüfen** **OK**aus.

7. Wenn Sie weitere Bedingungen hinzufügen möchten, wählen Sie **Weitere Optionen** aus, und wählen Sie dann **Bedingung hinzufügen** aus und wählen Sie aus der Liste aus.

   Wenn Sie beispielsweise die Regel nur dann anwenden möchten, wenn sich der Empfänger außerhalb Ihrer Organisation befindet, wählen Sie **Bedingung hinzufügen** aus, und wählen Sie dann **den Empfänger ist extern/intern** \> **außerhalb der Organisation** \> **OK**aus.

8. Um die Verschlüsselung mithilfe der neuen OM-Funktionen zu aktivieren, wählen Sie die Option **Nachrichtensicherheit ändern** **aus,** und wählen Sie dann **Office 365 Nachrichtenverschlüsselung und Rechte Schutz anwenden**aus. Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern**aus, und klicken Sie dann auf **OK**.
  
  Die Liste der Vorlagen enthält alle Standardvorlagen und-Optionen sowie benutzerdefinierte Vorlagen, die Sie zur Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365 Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)beschrieben. Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Informationen zur Option " **nicht weiterleiten** " finden Sie unter [do not Forward Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option **nur verschlüsseln** finden Sie unter [verschlüsseln nur Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Sie können die Option **Aktion hinzufügen** auswählen, wenn Sie eine andere Aktion angeben möchten.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Aktualisieren einer vorhandenen Nachrichtenfluss Regel für die Verwendung der neuen OM-Funktionen mithilfe der Exchange-Verwaltungskonsole

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** \> Center **Exchange**aus.

4. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

5. Wählen Sie in der Liste der Nachrichtenfluss Regeln die Regel aus, die Sie ändern möchten, um die neuen OM-Funktionen **Edit** ![zu verwenden,](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)und klicken Sie dann auf Bearbeitungssymbol bearbeiten.

6. Um die Verschlüsselung mithilfe der neuen OM-Funktionen zu aktivieren, wählen Sie die Option **Nachrichtensicherheit ändern** **aus,** und wählen Sie dann **Office 365 Nachrichtenverschlüsselung und Rechte Schutz anwenden**aus. Wählen Sie in der Liste eine RMS-Vorlage aus, klicken Sie auf **Speichern** , und wählen Sie dann **OK**aus.

   Die Liste der Vorlagen enthält alle Standardvorlagen und-Optionen sowie benutzerdefinierte Vorlagen, die Sie zur Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365 Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen beschrieben, die auf dem Azure Information Protection-Bereich basieren](set-up-new-message-encryption-capabilities.md). Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Informationen zur Option " **nicht weiterleiten** " finden Sie unter [do not Forward Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option **nur verschlüsseln** finden Sie unter [verschlüsseln nur Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Sie können die Option **Aktion hinzufügen** auswählen, wenn Sie eine andere Aktion angeben möchten.

7. Entfernen Sie in der Liste **ausführen die folgenden** Aktionen, die zum **Ändern der Nachrichtensicherheit** \> zugewiesen sind, **die frühere Version von OM anwenden**.

8. Wählen Sie **Speichern** aus.

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>Erstellen von Nachrichtenfluss Regeln zum Entfernen der Verschlüsselung für ausgehende e-Mail-Nachrichten mit den neuen OM-Funktionen

Mithilfe der Exchange-Verwaltungskonsole können Sie e-Mail-Flussregeln zum Auslösen der Nachrichtenverschlüsselung mit den neuen OM-Funktionen definieren.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Erstellen einer Regel zum Entfernen der Verschlüsselung aus e-Mail-Nachrichten mit den neuen OM-Funktionen mithilfe der Exchange-Verwaltungskonsole

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** \> Center **Exchange**aus.

4. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> wählen Sie **Neues** ![neues Symbol neue **Regel erstellen**aus. Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Geben Sie unter **Name**einen Namen für die Regel ein, beispielsweise die Verschlüsselung aus ausgehenden e-Mails entfernen.

6. Fügen Sie unter **diese Regel anwenden, wenn** die Bedingungen, an denen die Verschlüsselung aus Nachrichten entfernt werden soll, **den Absender** \> hinzu, der sich **innerhalb der Organisation**befindet. Fügen Sie nun zusätzliche Bedingungen hinzu, um bestimmte Empfänger zu adressieren, beispielsweise **der Empfänger** \> befindet sich **außerhalb der Organisation**.

7. Wählen Sie unter **Folgendes ausführen die**Option **Nachrichtensicherheit** \> **Entfernen Office 365 Nachrichtenverschlüsselung und Rechte Schutz**aus.

8. Klicken Sie auf **Speichern**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Erstellen von Nachrichtenfluss Regeln für Office 365 Nachrichtenverschlüsselung ohne die neuen Funktionen

Wenn Sie Ihre Organisation noch nicht in die neuen OM-Funktionen verschoben haben, verwenden Sie diese Aufgaben zum Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von Nachrichten für Ihre Organisation. Microsoft empfiehlt, einen Plan für die Umstellung auf die neuen OM-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie unter [Einrichten von neuen Office 365 Nachrichten Verschlüsselungsfunktionen, die auf Azure Information Protection basieren](set-up-new-message-encryption-capabilities.md).

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Erstellen einer Nachrichtenfluss Regel zum Verschlüsseln von e-Mail-Nachrichten ohne die neuen OM-Funktionen mithilfe der Exchange-Verwaltungskonsole

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** \> Center **Exchange**aus.

4. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> wählen Sie **Neues** ![neues Symbol neue **Regel erstellen**aus. Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Geben Sie unter **Name**einen Namen für die Regel ein, beispielsweise Verschlüsseln von e-Mails für DrToniRamos@hotmail.com.

6. Wählen Sie unter **Diese Regel anwenden, wenn** eine Bedingung aus, und geben Sie ggf. einen Wert ein. Geben Sie beispielsweise Folgendes ein, um Nachrichten an "DrToniRamos@hotmail.com" zu verschlüsseln:

   1. Wählen Sie unter **Diese Regel anwenden, wenn****the recipient is** (Der Empfänger ist) aus.

   2. Wählen Sie in der Kontaktliste einen vorhandenen Namen aus, oder geben Sie im Feld **Namen prüfen** eine neue E-Mail-Adresse ein.

      - Um einen vorhandenen Namen auszuwählen, wählen Sie ihn in der Liste aus, und klicken Sie dann auf **OK**.

      - Geben Sie zum Eingeben eines neuen Namens eine e-Mail-Adresse in das Feld **Namen überprüfen** ein, und wählen Sie \> dann **Namen überprüfen** **OK**aus.

7. Um weitere Bedingungen hinzuzufügen, wählen Sie **Weitere Optionen** aus, und wählen Sie dann **Bedingung hinzufügen** aus, und wählen Sie aus der Liste aus.

   Wenn Sie beispielsweise die Regel nur dann anwenden möchten, wenn sich der Empfänger außerhalb Ihrer Organisation befindet, wählen Sie **Bedingung hinzufügen** aus, und wählen Sie dann **den Empfänger ist extern/intern** \> **außerhalb der Organisation** \> **OK**aus.

8. Um die Verschlüsselung ohne Verwendung der neuen OM-Funktionen zu aktivieren, wählen Sie unter **Folgendes ausführen die**Option **Nachrichtensicherheit** \> **Anwenden der vorherigen Version von OM**ändern aus, und wählen Sie dann **Speichern**aus.

  Wenn Sie eine Fehlermeldung erhalten, dass IRM-Lizenzierung nicht aktiviert ist, haben Sie noch kein OM für Ihre Organisation eingerichtet. Wenn Sie OM jetzt einrichten möchten, müssen Sie es für die Verwendung der neuen OM-Funktionen einrichten. Weitere Informationen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen, die auf dem Azure Information Protection-Bereich basieren](set-up-new-message-encryption-capabilities.md). Microsoft unterstützt das Einrichten neuer Bereitstellungen von "OM" nicht mehr ohne die neuen Funktionen.

  Sie können die Option **Aktion hinzufügen** auswählen, wenn Sie eine andere Aktion angeben möchten.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Verwenden Exchange Online PowerShell zum Erstellen einer e-Mail-Fluss Regel zum Verschlüsseln von e-Mail-Nachrichten ohne die neuen OM-Funktionen

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Erstellen Sie mithilfe des Cmdlets **New-TransportRule** eine Regel, _ApplyOME_ und legen Sie `$true`den Parameter ApplyOME auf fest.

   In diesem Beispiel müssen alle e-Mail-Nachrichten, die an DrToniRamos@hotmail.com gesendet werden, verschlüsselt werden.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **Hinweise**:

   - Der eindeutige Name der neuen Regel lautet "verschlüsseln Sie Regel für Dr. Toni Ramos".

   - Der Parameter _SentTo_ gibt die Nachrichtenempfänger an (gekennzeichnet durch den Namen, die e-Mail-Adresse, den Distinguished Name usw.). In diesem Beispiel wird der Empfänger durch die e-Mail-Adresse "DrToniRamos@hotmail.com" identifiziert.

   - Der Parameter _SentToScope_ gibt den Speicherort der Nachrichtenempfänger an. In diesem Beispiel befindet sich das Postfach des Empfängers in Hotmail und ist nicht Teil der Organisation, daher wird der `NotInOrganization` Wert verwendet.

   Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Entfernen der Verschlüsselung aus e-Mail-Antworten ohne die neuen OM-Funktionen verschlüsselt

Wenn Ihre E-Mail-Benutzer verschlüsselte Nachrichten senden, können Empfänger dieser Nachrichten verschlüsselte Antworten senden. Sie können e-Mail-Flussregeln erstellen, um die Verschlüsselung automatisch von Antworten zu entfernen, sodass sich e-Mail-Benutzer in Ihrer Organisation nicht beim Verschlüsselungs Portal anmelden müssen, um Sie anzuzeigen. Sie können die Exchange-Verwaltungskonsole oder Windows PowerShell-Cmdlets verwenden, um diese Regeln zu definieren. Wenn Sie noch nicht die neuen OM-Funktionen verwenden, können Sie nur Nachrichten entschlüsseln, die entweder innerhalb Ihrer Organisation gesendet werden, oder Nachrichten, die Antworten auf Nachrichten sind, die von innerhalb Ihrer Organisation gesendet werden. Verschlüsselte Nachrichten, die von außerhalb Ihrer Organisation stammen, können nicht entschlüsselt werden.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen einer Regel zum Entfernen der Verschlüsselung aus e-Mail-Antworten, die ohne die neuen OM-Funktionen verschlüsselt wurden

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die Kachel **Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin** \> Center **Exchange**aus.

4. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> wählen Sie **Neues** ![neues Symbol neue **Regel erstellen**aus. Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Geben Sie unter **Name**einen Namen für die Regel ein, beispielsweise die Verschlüsselung aus eingehenden e-Mails entfernen.

6. Wählen Sie unter **diese Regel anwenden, wenn** die Bedingungen aus, aus denen die Verschlüsselung aus Nachrichten entfernt werden soll, wie **der Empfänger** \> sich **innerhalb der Organisation**befindet.

7. Wählen Sie unter **Folgendes ausführen**die Option **Nachrichtensicherheit** \> ändern aus, um **die vorherige Version von OM zu entfernen**.

8. Klicken Sie auf **Speichern**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Verwenden Exchange Online PowerShell zum Erstellen einer Regel zum Entfernen der Verschlüsselung aus e-Mail-Antworten, die ohne die neuen OM-Funktionen verschlüsselt wurden

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Erstellen Sie mithilfe des Cmdlets **New-TransportRule** eine Regel, _RemoveOME_ und legen Sie `$true`den Parameter RemoveOME auf fest.

   In diesem Beispiel wird die Verschlüsselung von allen e-Mails entfernt, die an Empfänger in der Organisation gesendet wurden.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **Hinweise**:

   - Der eindeutige Name der neuen Regel lautet "Entfernen der Verschlüsselung aus eingehenden e-Mails".

   - Der Parameter _SentToScope_ gibt den Speicherort der Nachrichtenempfänger an. In diesem Beispiel wird der Wert `InOrganization` Wert verwendet, der Folgendes angibt:

     - Der Empfänger ist ein Postfach, ein e-Mail-Benutzer, eine Gruppe oder ein e-Mail-aktivierter Öffentlicher Ordner in Ihrer Organisation.

       oder

     - Die e-Mail-Adresse des Empfängers befindet sich in einer akzeptierten Domäne, die als autorisierende Domäne oder als interne Relay-Domäne in Ihrer Organisation konfiguriert ist, _und_ die Nachricht wurde über eine authentifizierte Verbindung gesendet oder empfangen.

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

## <a name="related-topics"></a>Verwandte Themen

[Verschlüsselung in Office 365](encryption.md)

[Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)

[Hinzufügen von Branding zu verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md)

[Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
