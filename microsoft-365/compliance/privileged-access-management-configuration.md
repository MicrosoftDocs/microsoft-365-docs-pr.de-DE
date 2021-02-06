---
title: Erste Schritte mit der Verwaltung des privilegierten Zugriffs
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: In diesem Artikel erfahren Sie mehr über das Aktivieren und Konfigurieren von Privileged Access Management in Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126532"
---
# <a name="get-started-with-privileged-access-management"></a>Erste Schritte mit der Verwaltung des privilegierten Zugriffs

In diesem Thema werden Sie durch das Aktivieren und Konfigurieren von Privileged Access Management in Ihrer Organisation begleitet. Sie können entweder das Microsoft 365 Admin Center oder Exchange Management PowerShell verwenden, um privilegierten Zugriff zu verwalten und zu verwenden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie mit privileged Access Management beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Für den Zugriff auf und die Verwendung von Privileged Access Management muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 E3-Abonnement (oder Office 365 E3-Abonnement + Enterprise Mobility and Security E3-Abonnement) + das Microsoft 365 E5 Compliance-Add-On
- Alle Microsoft 365-, Office 365-, Exchange-, SharePoint- oder OneDrive for #A0 + das Microsoft 365 E5-Insider-Risikomanagement-Add-On  
- Microsoft 365 A5-Abonnement (kostenpflichtig oder Testversion)
- Microsoft 365 A3-Abonnement (oder Office 365 A3-Abonnement + Enterprise Mobility and Security A3-Abonnement) + das Microsoft A5 Compliance-Add-On
- Alle Microsoft 365-, Office 365-, Exchange-, SharePoint- oder OneDrive for #A0 + das Microsoft 365 A5-Insider-Risikomanagement-Add-On
- Office 365 Enterprise E5-Abonnement (kostenpflichtig oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (nicht mehr verfügbar für neue Abonnements, siehe Hinweis)

Benutzern, die Anforderungen zur Verwaltung des privilegierten Zugriffs übermitteln und darauf antworten, muss eine der oben genannten Lizenzen zugewiesen sein.

>[!IMPORTANT]
>Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden zu einem der oben genannten Abonnements überwechseln, das dieselben oder zusätzliche Compliancefeatures enthält.

Wenn Sie nicht über einen vorhandenen Office 365 Enterprise E5-Plan verfügen und die Verwaltung des privilegierten Zugriffs ausprobieren [](https://www.microsoft.com/microsoft-365/enterprise) möchten, können Sie [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) zu Ihrem vorhandenen Office 365-Abonnement hinzufügen oder sich für eine Testversion von Microsoft 365 Enterprise E5 registrieren.

## <a name="enable-and-configure-privileged-access-management"></a>Aktivieren und Konfigurieren von Privileged Access Management

Führen Sie die folgenden Schritte aus, um privilegierten Zugriff in Ihrer Organisation einrichten und verwenden zu können:

- [Schritt 1: Erstellen einer Gruppe genehmigende Benutzer](privileged-access-management-configuration.md#step1)

    Bevor Sie mit dem Verwenden von privilegiertem Zugriff beginnen, bestimmen Sie, wer die Berechtigung zum Genehmigen eingehender Anforderungen für den Zugriff auf Aufgaben mit erhöhten und privilegierten Rechten benötigt. Jeder Benutzer, der zur Gruppe "Genehmiger" gehört, kann Zugriffsanforderungen genehmigen. Diese Gruppe wird durch Erstellen einer E-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert.

- [Schritt 2: Aktivieren des privilegierten Zugriffs](privileged-access-management-configuration.md#step2)

    Privilegierter Zugriff muss in Office 365 explizit mit der Standardgenehmigungsgruppe aktiviert werden, einschließlich einer Reihe von Systemkonten, die Sie aus der Privileged Access Management-Zugriffssteuerung ausschließen möchten.

- [Schritt 3: Erstellen einer Zugriffsrichtlinie](privileged-access-management-configuration.md#step3)

    Die Erstellung einer Genehmigungsrichtlinie ermöglicht es Ihnen, die spezifischen Genehmigungsanforderungen für einzelne Aufgaben zu definieren. Die Optionen für den Genehmigungstyp sind **Automatisch** oder **Manuell**.

- [Schritt 4: Übermitteln/Genehmigen von Privilegierten Zugriffsanforderungen](privileged-access-management-configuration.md#step4)

    Nach der Aktivierung erfordert der privilegierte Zugriff Genehmigungen für jede Aufgabe, für die eine entsprechende Genehmigungsrichtlinie definiert ist. Für Aufgaben, die in einer Genehmigungsrichtlinie enthalten sind, müssen Benutzer eine Zugriffsgenehmigung anfordern und erhalten, um über die zur Ausführung der Aufgabe erforderlichen Berechtigungen zu verfügen.

Nachdem die Genehmigung erteilt wurde, kann der anfragende Benutzer die beabsichtigte Aufgabe ausführen, und der privilegierte Zugriff autorisiert und führt die Aufgabe im Namen des Benutzers aus. Die Genehmigung bleibt für die beantragte Dauer gültig (Standarddauer ist 4 Stunden), während der der Antragsteller die beabsichtigte Aufgabe mehrmals ausführen kann. Alle derartigen Ausführungen werden protokolliert und für Sicherheits- und Compliance-Audits zur Verfügung gestellt. 

>[!NOTE]
>Wenn Sie die Exchange-Verwaltungs-PowerShell verwenden möchten, um privilegierten Zugriff zu aktivieren und zu konfigurieren, führen Sie die Schritte unter Herstellen einer Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) mithilfe der mehrstufigen Authentifizierung aus, um eine Verbindung mit Exchange Online PowerShell mit Ihren Office 365-Anmeldeinformationen herzustellen. Sie müssen die mehrstufige Authentifizierung nicht aktivieren, damit Ihre Organisation die Schritte zum Aktivieren des privilegierten Zugriffs beim Herstellen einer Verbindung mit Exchange Online PowerShell ausführen kann. Beim Herstellen einer Verbindung mit der mehrstufigen Authentifizierung wird ein OAuth-Token erstellt, das vom privilegierten Zugriff zum Signieren Ihrer Anforderungen verwendet wird.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Schritt 1: Erstellen einer Gruppe genehmigende Benutzer

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365](https://admin.microsoft.com) Admin Center an.

2. Wechseln Sie im Admin Center zu **"Gruppen**  >  **Hinzufügen einer Gruppe".**

3. Wählen **Sie E-Mail-aktivierte Sicherheitsgruppe** aus, und  füllen Sie dann die Felder **"Name",**"Gruppen-E-Mail-Adresse" und "Beschreibung" für die neue Gruppe aus. 

4. Speichern Sie die Gruppe.  Es kann ein paar Minuten dauern, bis die Gruppe vollständig konfiguriert ist und im Microsoft 365 Admin Center angezeigt wird.

5. Wählen Sie die Gruppe der neuen genehmigende Benutzer aus, und wählen Sie **"Bearbeiten"** aus, um der Gruppe Benutzer hinzuzufügen.

6. Speichern Sie die Gruppe.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Schritt 2: Aktivieren des privilegierten Zugriffs

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **"Einstellungen** der  >    >  **Organisationseinstellungen" & Zugriff auf**  >  **"Datenschutzrechte".**

3. Aktivieren Sie das **Steuerelement "Genehmigungen für privilegierte Aufgaben erforderlich".**

4. Weisen Sie die gruppe der genehmigern Benutzer, die Sie in Schritt 1 erstellt haben, als **Standardgruppe der genehmigern Benutzer zu.**

5. **Speichern** und **Schließen**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um privilegierten Zugriff zu aktivieren und die Gruppe der genehmigenden Benutzer zuzuordnen:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Beispiel:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>Das Feature "Systemkonten" wird verfügbar gemacht, um sicherzustellen, dass bestimmte Automatisierungen in Ihrer Organisation ohne Abhängigkeit von privilegiertem Zugriff funktionieren können. Es wird jedoch empfohlen, dass solche Ausschlüsse aussergewöhnlich sind und die zulässigen Automatisierungen regelmäßig genehmigt und überwacht werden sollten.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Schritt 3: Erstellen einer Zugriffsrichtlinie

Sie können bis zu 30 Richtlinien für privilegierten Zugriff für Ihre Organisation erstellen und konfigurieren.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **"Einstellungen**  >  **der**  >  **Organisationseinstellungen" & Zugriff auf**  >  **"Datenschutzrechte".**

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen **Sie "Richtlinien konfigurieren"** und dann **"Richtlinie hinzufügen" aus.**

5. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:
    
    **Richtlinientyp**: Aufgabe, Rolle oder Rollengruppe

    **Geltungsbereich der Richtlinie**: Exchange

    **Richtlinienname**: Aus den verfügbaren Richtlinien auswählen

    **Genehmigungstyp**: Manuell oder automatisch

    **Genehmigungsgruppe**: Wählen Sie die in Schritt 1 erstellte Gruppe der genehmigenden Personen aus.

6. Wählen Sie **"Erstellen"** und dann **"Schließen" aus.** Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Genehmigungsrichtlinie zu erstellen und zu definieren:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Beispiel:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Schritt 4: Übermitteln/Genehmigen von Privilegierten Zugriffsanforderungen

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Anforderung einer Erhebungsberechtigung zur Ausführung privilegierter Aufgaben

Anforderungen für einen privilegierten Zugriff sind bis zu 24 Stunden nach Einreichung der Anforderung gültig. Wenn sie nicht genehmigt oder abgelehnt werden, verfallen die Anforderungen und der Zugriff wird nicht genehmigt.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **"Einstellungen**  >  **der**  >  **Organisationseinstellungen" & Zugriff auf**  >  **"Datenschutzrechte".**

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen Sie **"Neue Anforderung" aus.** Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Aufgabe, Rolle oder Rollengruppe

    **Geltungsbereich der Anforderung**: Exchange

    **Anforderung für**: Aus den verfügbaren Richtlinien auswählen

    **Dauer (Stunden)**: Anzahl der Stunden, die für den angeforderten Zugriff erforderlich sind. Die Anzahl der Stunden, die angefordert werden können, ist nicht begrenzt.

    **Kommentare**: Textfeld für Kommentare im Zusammenhang mit Ihrer Zugriffsanforderung

5. Wählen Sie **"Speichern"** und dann **"Schließen" aus.** Ihre Anforderung wird per E-Mail an die Gruppe der genehmigende Nachricht gesendet.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Genehmigungsanforderung an die Gruppe der genehmigenden Benutzer zu erstellen und zu übermitteln:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Beispiel:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Anzeigen des Status von Anforderungen für erhöhte Rechte

Nachdem eine Genehmigungsanforderung erstellt wurde, kann der Status der Erweiterungsanforderung im Admin Center oder in Exchange Management PowerShell mithilfe der zugeordneten Anforderungs-ID überprüft werden.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen** für Organisationseinstellungen  >    >  **Sicherheit &**  >  **Privilegierter Zugriff.**

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um einen Genehmigungsanforderungsstatus für eine bestimmte Anforderungs-ID anzeigen zu können:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Beispiel:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Genehmigen einer Berechtigungsanforderung für erhöhte Rechte

Wenn eine Genehmigungsanforderung erstellt wird, erhalten Mitglieder der relevanten Genehmigende Gruppe eine E-Mail-Benachrichtigung und können die Anforderung genehmigen, die der Anforderungs-ID zugeordnet ist. Der Antragsteller wird über die Genehmigung oder Ablehnung der Anforderung per E-Mail benachrichtigt.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen** für Organisationseinstellungen  >    >  **Sicherheit & Zugriff auf**  >  **Datenschutzrechte.**

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen Sie eine aufgelistete Anforderung aus, um die Details anzuzeigen und Maßnahmen für die Anforderung zu ergreifen.

5. Wählen **Sie "Genehmigen"** aus, um die Anforderung zu genehmigen, oder wählen Sie "Verweigern" aus, um die Anforderung zu verweigern.  Zuvor genehmigte Anforderungen können den Zugriff widerrufen haben, indem Sie **"Widerrufen" auswählen.**

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie zum Genehmigen einer Berechtigungsanforderung für erhöhte Rechte den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Beispiel:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Anforderung zur Erhöhung der Rechteerweiterung zu verweigern:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Beispiel:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Löschen einer Richtlinie für privilegierten Zugriff in Office 365

Wenn sie in Ihrer Organisation nicht mehr benötigt wird, können Sie eine Richtlinie für privilegierten Zugriff löschen.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365](https://admin.microsoft.com) Admin Center an.

2. Wechseln Sie im Admin Center zu **Einstellungen** für Organisationseinstellungen  >    >  **Sicherheit &**  >  **Privilegierter Zugriff.**

3. Wählen **Sie Zugriffsrichtlinien und -anforderungen verwalten aus.**

4. Wählen Sie **"Richtlinien konfigurieren" aus.**

5. Wählen Sie die Richtlinie aus, die Sie löschen möchten, und wählen Sie dann **"Richtlinie entfernen" aus.**

6. Wählen Sie **Schließen** aus.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online Powershell aus, um eine Richtlinie für privilegierten Zugriff zu löschen:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Deaktivieren des privilegierten Zugriffs in Office 365

Bei Bedarf können Sie die Verwaltung des privilegierten Zugriffs für Ihre Organisation deaktivieren. Durch das Deaktivieren des privilegierten Zugriffs werden keine zugeordneten Genehmigungsrichtlinien oder Genehmigergruppen gelöscht.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich [beim Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **"Einstellungen** der  >    >  **Organisationseinstellungen" & Zugriff auf**  >  **"Datenschutzrechte".**

3. Aktivieren Sie die **Option "Genehmigungen für privilegierte Zugriffssteuerung erforderlich".**

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie zum Deaktivieren des privilegierten Zugriffs den folgenden Befehl in Exchange Online Powershell aus:

```PowerShell
Disable-ElevatedAccessControl
```
