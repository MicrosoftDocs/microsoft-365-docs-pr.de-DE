---
title: Konfigurieren der privilegierten Zugriffsverwaltung in Office 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: In diesem Thema erfahren Sie mehr über die Konfiguration der privilegierten Zugriffsverwaltung in Office 365
ms.openlocfilehash: 36a473369ba539230bc4bbb2a630d74830844fc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601732"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Konfigurieren der privilegierten Zugriffsverwaltung in Office 365

>[!IMPORTANT]
>In diesem Thema werden Bereitstellungs-und Konfigurationsanleitungen für Features behandelt, die derzeit in Office 365 E5 und Advanced Compliance SKUs verfügbar sind.

Dieses Thema führt Sie durch das Aktivieren und Konfigurieren der privilegierten Zugriffsverwaltung in Ihrer Office 365 Organisation. Sie können entweder das Microsoft 365 Admin Center oder die Exchange-Verwaltungskonsole verwenden, um privilegierten Zugriff zu verwalten und zu verwenden. 

## <a name="enable-and-configure-privileged-access-management"></a>Aktivieren und Konfigurieren der privilegierten Zugriffsverwaltung

Führen Sie die folgenden Schritte zum Einrichten und Verwenden von privilegiertem Zugriff in Ihrer Office 365 Organisation aus:

- [Schritt 1: Erstellen einer Gruppe einer genehmigenden Person](privileged-access-management-configuration.md#step1)

    Bevor Sie mit dem Verwenden des Zugriffs auf Berechtigungen beginnen, müssen Sie ermitteln, wer Genehmigungsautorität für eingehende Anforderungen für den Zugriff auf Erweiterte und privilegierte Aufgaben benötigt. Jeder Benutzer, der Teil der Gruppe der genehmigenden Personen ist, kann Zugriffsanforderungen genehmigen. Diese Gruppe wird durch Erstellen einer e-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert.

- [Schritt 2: Aktivieren des privilegierten Zugriffs](privileged-access-management-configuration.md#step2)

    Der privilegierte Zugriff muss in Office 365 explizit mit der standardmäßigen genehmigenden Gruppe aktiviert sein, einschließlich einer Reihe von Systemkonten, die von der Zugriffssteuerung für privilegierte Zugriffsverwaltung ausgeschlossen werden sollen.

- [Schritt 3: Erstellen einer Zugriffsrichtlinie](privileged-access-management-configuration.md#step3)

    Durch das Erstellen einer Genehmigungsrichtlinie können Sie die spezifischen Genehmigungsanforderungen definieren, die auf einzelne Vorgänge beschränkt sind. Die Genehmigungs Typen Optionen sind **Auto** oder **manuell**.

- [Schritt 4: senden/genehmigen von Berechtigungen für privilegierte Zugriffe](privileged-access-management-configuration.md#step4)

    Nach Aktivierung erfordert der privilegierte Zugriff Genehmigungen für jede Aufgabe, für die eine zugeordnete Genehmigungsrichtlinie definiert ist. Für Aufgaben, die in einer Genehmigungsrichtlinie enthalten sind, müssen die Benutzer die Genehmigung für den Zugriff anfordern und erhalten, damit die erforderlichen Berechtigungen zum Ausführen der Aufgabe erteilt werden können.

Nachdem die Genehmigung erteilt wurde, kann der anfordernde Benutzer die vorgesehene Aufgabe ausführen, und der privilegierte Zugriff autorisiert und führt die Aufgabe im Namen des Benutzers aus. Die Genehmigung bleibt für die angeforderte Dauer gültig (die Standarddauer beträgt 4 Stunden), während der der Anforderer die beabsichtigte Aufgabe mehrmals ausführen kann. Alle derartigen Ausführungen werden protokolliert und zur Überwachung der Sicherheit und Compliance zur Verfügung gestellt. 

>[!NOTE]
>Wenn Sie die Exchange-Verwaltungs-PowerShell zum Aktivieren und Konfigurieren des privilegierten Zugriffs verwenden möchten, führen Sie die Schritte unter [Verbinden mit Exchange Online PowerShell mithilfe der mehrstufigen Authentifizierung](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) aus, um eine Verbindung mit Exchange Online PowerShell mit Ihren Office 365 Anmeldeinformationen herzustellen. Sie müssen die mehrstufige Authentifizierung für Ihre Office 365 Organisation nicht aktivieren, um die erforderlichen Schritte zum Aktivieren des privilegierten Zugriffs beim Herstellen einer Verbindung mit Exchange Online PowerShell durchführen zu können. Durch die Verbindung mit mehrstufiger Authentifizierung wird ein OAuth-Token erstellt, das von privilegiertem Zugriff zum Signieren Ihrer Anforderungen verwendet wird.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Schritt 1: Erstellen einer Gruppe einer genehmigenden Person

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **Gruppen** > **Hinzufügen einer Gruppe**.

3. Wählen Sie **e-Mail-aktivierte Sicherheitsgruppe** aus, und füllen Sie dann die Felder **Name**, **Gruppen-e-Mail-Adresse**und **Beschreibung** für die neue Gruppe aus.

4. Speichern Sie die Gruppe. Es kann einige Minuten dauern, bis die Gruppe vollständig konfiguriert und im Microsoft 365 Admin Center angezeigt wird.

5. Wählen Sie die Gruppe neue genehmigende Person aus, und wählen Sie **Bearbeiten** aus, um der Gruppe Benutzer hinzuzufügen.

6. Speichern Sie die Gruppe.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Schritt 2: Aktivieren des privilegierten Zugriffs

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **Einstellungen #a0 Einstellungen #a1 Security #a2 Privacy** > **privileged Access**.

3. Aktivieren Sie das Steuerelement **erforderliche Genehmigungen für privilegierte Aufgaben** .

4. Weisen Sie die Gruppe der genehmigenden Person, die Sie in Schritt 1 erstellt haben, als **Standard genehmigende Gruppe**zu.

5. **Speichern** und **Schließen**.

### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den privilegierten Zugriff zu aktivieren und die Gruppe der genehmigenden Person zuzuweisen:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Beispiel:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>Das Feature "System Konten" wird bereitgestellt, um sicherzustellen, dass bestimmte Automatisierungen in ihren Organisationen ohne Abhängigkeit von privilegiertem Zugriff funktionieren können, es wird jedoch empfohlen, dass diese Ausnahmen außergewöhnlich sind und diese genehmigt und überwacht werden dürfen. regelmäßig.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Schritt 3: Erstellen einer Zugriffsrichtlinie

Sie können bis zu 30 privilegierte Zugriffsrichtlinien für Ihre Office 365 Organisation erstellen und konfigurieren.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit #a0 Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **Richtlinien konfigurieren** aus, und wählen Sie **Richtlinie hinzufügen**aus.

5. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:
    
    **Richtlinientyp**: Aufgabe, Rolle oder Rollengruppe

    **Richtlinienbereich**: Exchange

    **Richtlinienname**: Wählen Sie aus den verfügbaren Richtlinien aus.

    **Genehmigungs**: manuell oder automatisch

    **Genehmigungsgruppe**: Wählen Sie die in Schritt 1 erstellte genehmigende Gruppe aus.

6. Klicken Sie auf **Erstellen** und dann auf **Schließen**. Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.

### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Zum Erstellen und Definieren einer Genehmigungsrichtlinie führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Beispiel:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Schritt 4: senden/genehmigen von Berechtigungen für privilegierte Zugriffe

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Anfordern von Höhen Autorisierung zum Ausführen privilegierter Aufgaben

Anforderungen für privilegierten Zugriff sind bis zu 24 Stunden nach der Übermittlung der Anforderung gültig. Wenn diese nicht genehmigt oder verweigert werden, laufen die Anforderungen ab, und der Zugriff ist nicht genehmigt.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit #a0 Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **neue Anforderung**aus. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Aufgabe, Rolle oder Rollengruppe

    **Anforderungsbereich**: Exchange

    **Anforderung für**: Wählen Sie aus den verfügbaren Richtlinien aus.

    **Dauer (Stunden)**: Anzahl der Stunden des angeforderten Zugriffs. Es gibt keinen Grenzwert für die Anzahl der Stunden, die angefordert werden können.

    **Kommentare**: Text Feld für Kommentare im Zusammenhang mit ihrer Zugriffsanfrage

5. Klicken Sie auf **Speichern** und dann auf **Schließen**. Ihre Anfrage wird per e-Mail an die Gruppe der genehmigenden Person gesendet.

#### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Genehmigungsanforderung an die Gruppe der genehmigenden Person zu erstellen und zu senden:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Beispiel:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Anzeigen des Status von Ansichts Anforderungen

Nach dem Erstellen einer Genehmigungsanforderung kann der Status der Ansichts Anforderung im Admin Center oder in der Exchange-Verwaltungskonsole mithilfe der zugeordneten Anforderungs-ID überprüft werden.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihren Anmeldeinformationen an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit #a0 Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **Ansicht** aus, um übermittelte Anforderungen nach **ausstehender**, **genehmigter**, **verweigerter**oder **Kunden sperrbox** -Status zu filtern.

#### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den Status einer Genehmigungsanforderung für eine bestimmte Anforderungs-ID anzuzeigen:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Beispiel:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Genehmigen einer Ansichts Autorisierungsanforderung

Wenn eine Genehmigungsanforderung erstellt wird, erhalten Mitglieder der entsprechenden genehmigenden Gruppe eine e-Mail-Benachrichtigung und können die Anforderung genehmigen, die der Anforderungs-ID zugeordnet ist. Der Anforderer wird über die Anforderungsgenehmigung oder Ablehnung per e-Mail-Nachricht benachrichtigt.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihren Anmeldeinformationen an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit #a0 Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie eine aufgeführte Anforderung aus, um die Details anzuzeigen und Aktionen für die Anforderung durchführen zu können.

5. Wählen Sie **genehmigen** , um die Anforderung zu genehmigen, oder wählen Sie **verweigern** aus, um die Anforderung zu verweigern. Für zuvor genehmigte Anforderungen kann der Zugriff aufgehoben werden, indem Sie **REVOKE**auswählen.

#### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Berechtigungsanforderung für Berechtigungen zu genehmigen:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Beispiel:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Berechtigungsanforderung für Berechtigungen zu verweigern:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Beispiel:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Löschen einer privilegierten Zugriffsrichtlinie in Office 365

Wenn Sie in Ihrer Organisation nicht mehr benötigt wird, können Sie eine privilegierte Zugriffsrichtlinie löschen.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit #a0 Zugriff auf Datenschutz** > **privilegiert**.

3. Wählen Sie **Zugriffsrichtlinien und-Anforderungen verwalten**aus.

4. Wählen Sie **configure Policies**aus.

5. Wählen Sie die Richtlinie aus, die Sie löschen möchten, und wählen Sie dann **Richtlinie entfernen**aus.

6. Wählen Sie **Schließen** aus.

### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine privilegierte Zugriffsrichtlinie zu löschen:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Deaktivieren des privilegierten Zugriffs in Office 365

Bei Bedarf können Sie die privilegierte Zugriffsverwaltung für Ihre Organisation deaktivieren. Durch Deaktivieren des privilegierten Zugriffs werden keine zugeordneten Genehmigungsrichtlinien oder genehmigenden Gruppen gelöscht.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **Einstellungen** > **Sicherheit #a0 Zugriff auf Datenschutz** > **privilegiert**.

3. Aktivieren Sie die **Berechtigung Genehmigungen für privilegierte Zugriffssteuerung erfordern** .

### <a name="in-exchange-management-powershell"></a>In der Exchange-Verwaltungs-PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den privilegierten Zugriff zu deaktivieren:

```PowerShell
Disable-ElevatedAccessControl
```
