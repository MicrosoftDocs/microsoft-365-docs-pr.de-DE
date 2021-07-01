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
description: Verwenden Sie diesen Artikel, um mehr über das Aktivieren und Konfigurieren der Verwaltung von privilegiertem Zugriff in Office 365 zu erfahren.
ms.openlocfilehash: 13b600c60e1b9c88285ee58efcf80a7ff5ea17fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226119"
---
# <a name="get-started-with-privileged-access-management"></a>Erste Schritte mit der Verwaltung des privilegierten Zugriffs

Dieses Thema führt Sie durch das Aktivieren und Konfigurieren der Verwaltung des privilegierten Zugriffs in Ihrer Organisation. Sie können entweder die Microsoft 365 Admin Center oder Exchange Management PowerShell verwenden, um privilegierten Zugriff zu verwalten und zu verwenden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie mit der Verwaltung des privilegierten Zugriffs beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und alle Add-Ons bestätigen. Um auf die Verwaltung des privilegierten Zugriffs zuzugreifen und diese zu verwenden, muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft 365 E5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 E3 Abonnement (oder Office 365 E3-Abonnement + Enterprise Mobility and Security E3-Abonnement) + das Microsoft 365 E5 Compliance-Add-On
- Jedes Microsoft 365-, Office 365-, Exchange-, SharePoint- oder OneDrive for Business-Abonnement sowie das Microsoft 365 E5-Insider-Risikomanagement-Add-On
- Microsoft 365 A5-Abonnement (kostenpflichtige oder Testversion)
- Microsoft 365 A3 Abonnement (oder Office 365 A3 Abonnement + Enterprise Mobility and Security A3-Abonnement) + das Microsoft A5 Compliance-Add-On
- Jedes Microsoft 365-, Office 365-, Exchange-, SharePoint- oder OneDrive für Education-Abonnement sowie das Microsoft 365 A5-Add-On "Insider-Risikomanagement"
- Office 365 Enterprise E5-Abonnement (kostenpflichtige version oder Testversion)
- Office 365 Enterprise E3-Abonnement + das Office 365 Advanced Compliance-Add-On (für neue Abonnements nicht mehr verfügbar, siehe Hinweis)

Benutzern, die Verwaltungsanforderungen für privilegierten Zugriff übermitteln und beantworten, muss eine der oben genannten Lizenzen zugewiesen werden.

> [!IMPORTANT]
> Office 365 Advanced Compliance wird nicht mehr als eigenständiges Abonnement verkauft. Wenn aktuelle Abonnements ablaufen, sollten Kunden auf eines der oben genannten Abonnements umsteigen, die die gleichen oder zusätzlichen Compliancefeatures enthalten.

Wenn Sie keinen vorhandenen Office 365 Enterprise E5-Plan haben und die Verwaltung des privilegierten Zugriffs ausprobieren möchten, können Sie Ihrem vorhandenen Office 365-Abonnement [Microsoft 365 hinzufügen](/office365/admin/try-or-buy-microsoft-365) oder sich für eine Testversion von Microsoft 365 Enterprise E5 [registrieren.](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="enable-and-configure-privileged-access-management"></a>Aktivieren und Konfigurieren der Verwaltung des privilegierten Zugriffs

Führen Sie die folgenden Schritte aus, um privilegierten Zugriff in Ihrer Organisation einzurichten und zu verwenden:

- [Schritt 1: Erstellen einer Gruppe genehmigende Personen](privileged-access-management-configuration.md#step1)

    Bevor Sie mit dem Verwenden von privilegiertem Zugriff beginnen, bestimmen Sie, wer die Berechtigung zum Genehmigen eingehender Anforderungen für den Zugriff auf Aufgaben mit erhöhten und privilegierten Rechten benötigt. Jeder Benutzer, der zur Gruppe "Genehmiger" gehört, kann Zugriffsanforderungen genehmigen. Diese Gruppe wird durch Erstellen einer E-Mail-aktivierten Sicherheitsgruppe in Office 365 aktiviert.

- [Schritt 2: Aktivieren des privilegierten Zugriffs](privileged-access-management-configuration.md#step2)

    Privilegierter Zugriff muss in Office 365 explizit mit der Standardgenehmigungsgruppe aktiviert werden, einschließlich einer Reihe von Systemkonten, die Sie aus der Privileged Access Management-Zugriffssteuerung ausschließen möchten.

- [Schritt 3: Erstellen einer Zugriffsrichtlinie](privileged-access-management-configuration.md#step3)

    Die Erstellung einer Genehmigungsrichtlinie ermöglicht es Ihnen, die spezifischen Genehmigungsanforderungen für einzelne Aufgaben zu definieren. Die Optionen für den Genehmigungstyp sind **Automatisch** oder **Manuell**.

- [Schritt 4: Übermitteln/Genehmigen von Anforderungen für privilegierten Zugriff](privileged-access-management-configuration.md#step4)

    Nach der Aktivierung erfordert der privilegierte Zugriff Genehmigungen für jede Aufgabe, für die eine entsprechende Genehmigungsrichtlinie definiert ist. Für Aufgaben, die in einer Genehmigungsrichtlinie enthalten sind, müssen Benutzer eine Zugriffsgenehmigung anfordern und erhalten, um über die zur Ausführung der Aufgabe erforderlichen Berechtigungen zu verfügen.

Nachdem die Genehmigung erteilt wurde, kann der anfragende Benutzer die beabsichtigte Aufgabe ausführen, und der privilegierte Zugriff autorisiert und führt die Aufgabe im Namen des Benutzers aus. Die Genehmigung bleibt für die beantragte Dauer gültig (Standarddauer ist 4 Stunden), während der der Antragsteller die beabsichtigte Aufgabe mehrmals ausführen kann. Alle derartigen Ausführungen werden protokolliert und für Sicherheits- und Compliance-Audits zur Verfügung gestellt.

> [!NOTE]
> Wenn Sie Exchange Management PowerShell verwenden möchten, um den privilegierten Zugriff zu aktivieren und zu konfigurieren, führen Sie die Schritte in [Verbinden aus, um PowerShell mithilfe der mehrstufigen Authentifizierung zu Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) PowerShell mit Ihren Office 365 Anmeldeinformationen zu Exchange Online. Sie müssen die mehrstufige Authentifizierung für Ihre Organisation nicht aktivieren, um die Schritte zum Aktivieren des privilegierten Zugriffs beim Herstellen einer Verbindung mit Exchange Online PowerShell zu verwenden. Durch die Verbindung mit der mehrstufigen Authentifizierung wird ein OAuth-Token erstellt, das vom privilegierten Zugriff zum Signieren Ihrer Anforderungen verwendet wird.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Schritt 1: Erstellen einer Gruppe genehmigende Personen

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **"Gruppen**  >  **hinzufügen".**

3. Wählen Sie **E-Mail-aktivierte Sicherheitsgruppe** aus, und füllen Sie dann die Felder **"Name",** **"Gruppen-E-Mail-Adresse"** und **"Beschreibung"** für die neue Gruppe aus.

4. Speichern Sie die Gruppe.  Es kann ein paar Minuten dauern, bis die Gruppe vollständig konfiguriert ist und im Microsoft 365 Admin Center angezeigt wird.

5. Wählen Sie die Gruppe der neuen genehmigenden Person aus, und wählen Sie **"Bearbeiten"** aus, um der Gruppe Benutzer hinzuzufügen.

6. Speichern Sie die Gruppe.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Schritt 2: Aktivieren des privilegierten Zugriffs

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Aktivieren Sie die **Berechtigung "Genehmigungen für privilegierte Aufgaben** anfordern".

4. Weisen Sie die Gruppe der genehmigenden Person, die Sie in Schritt 1 erstellt haben, als Gruppe der **standardmäßigen Genehmiger** zu.

5. **Speichern** und **schließen**.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den privilegierten Zugriff zu aktivieren und die Gruppe der genehmigenden Person zuzuweisen:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Beispiel:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> Das Feature "Systemkonten" wird zur Verfügung gestellt, um sicherzustellen, dass bestimmte Automatisierungen innerhalb Ihrer Organisation ohne Abhängigkeit von privilegiertem Zugriff funktionieren können. Es wird jedoch empfohlen, solche Ausschlüsse in Ausnahme zu nehmen und die zulässigen Ausnahmen regelmäßig zu genehmigen und zu überwachen.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Schritt 3: Erstellen einer Zugriffsrichtlinie

Sie können bis zu 30 Richtlinien für den privilegierten Zugriff für Ihre Organisation erstellen und konfigurieren.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Wählen Sie **"Zugriffsrichtlinien und -anforderungen verwalten" aus.**

4. Wählen Sie **"Richtlinien konfigurieren"** und **"Richtlinie hinzufügen"** aus.

5. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Richtlinientyp**: Aufgabe, Rolle oder Rollengruppe

    **Geltungsbereich der Richtlinie**: Exchange

    **Richtlinienname**: Aus den verfügbaren Richtlinien auswählen

    **Genehmigungstyp**: Manuell oder automatisch

    **Genehmigungsgruppe**: Wählen Sie die in Schritt 1 erstellte Gruppe der genehmigenden Personen aus.

6. Wählen Sie **"Erstellen"** und dann **"Schließen"** aus. Es kann einige Minuten dauern, bis die Richtlinie vollständig konfiguriert und aktiviert ist.

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

## <a name="step-4-submitapprove-privileged-access-requests"></a>Schritt 4: Übermitteln/Genehmigen von Anforderungen für privilegierten Zugriff

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Anforderung einer Erhebungsberechtigung zur Ausführung privilegierter Aufgaben

Anforderungen für einen privilegierten Zugriff sind bis zu 24 Stunden nach Einreichung der Anforderung gültig. Wenn sie nicht genehmigt oder abgelehnt werden, verfallen die Anforderungen und der Zugriff wird nicht genehmigt.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Wählen Sie **"Zugriffsrichtlinien und -anforderungen verwalten" aus.**

4. Wählen Sie **"Neue Anforderung"** aus. Wählen Sie in den Dropdownfeldern die entsprechenden Werte für Ihre Organisation aus:

    **Anforderungstyp**: Aufgabe, Rolle oder Rollengruppe

    **Geltungsbereich der Anforderung**: Exchange

    **Anforderung für**: Aus den verfügbaren Richtlinien auswählen

    **Dauer (Stunden)**: Anzahl der Stunden, die für den angeforderten Zugriff erforderlich sind. Es gibt keinen Grenzwert für die Anzahl der Stunden, die angefordert werden können.

    **Kommentare:** Textfeld für Kommentare im Zusammenhang mit Ihrer Zugriffsanforderung

5. Wählen Sie **"Speichern"** und dann **"Schließen"** aus. Ihre Anforderung wird per E-Mail an die Gruppe der genehmigenden Person gesendet.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Genehmigungsanforderung zu erstellen und an die Gruppe der genehmigenden Person zu senden:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Beispiel:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Anzeigen des Status von Anforderungen für erhöhte Rechte

Nachdem eine Genehmigungsanforderung erstellt wurde, kann der Status der Rechteerweiterungsanforderung im Admin Center oder in Exchange Management PowerShell mithilfe der anforderungs-ID überprüft werden.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Wählen Sie **"Zugriffsrichtlinien und -anforderungen verwalten" aus.**

4. Wählen Sie **"Ansicht"** aus, um gesendete Anforderungen nach dem Status **"Ausstehend",** **"Genehmigt",** **"Abgelehnt"** oder **"Kunden-Lockbox" zu** filtern.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um einen Genehmigungsanforderungsstatus für eine bestimmte Anforderungs-ID anzuzeigen:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Beispiel:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Genehmigen einer Berechtigungsanforderung für erhöhte Rechte

Wenn eine Genehmigungsanforderung erstellt wird, erhalten Mitglieder der entsprechenden Genehmigergruppe eine E-Mail-Benachrichtigung und können die Anfrage genehmigen, die der Anforderungs-ID zugeordnet ist. Der Antragsteller wird über die Genehmigung oder Ablehnung der Anforderung per E-Mail benachrichtigt.

#### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Wählen Sie **"Zugriffsrichtlinien und -anforderungen verwalten" aus.**

4. Wählen Sie eine aufgeführte Anforderung aus, um die Details anzuzeigen und Maßnahmen für die Anforderung zu ergreifen.

5. Wählen Sie **"Genehmigen"** aus, um die Anforderung zu genehmigen, oder wählen Sie **"Verweigern"** aus, um die Anforderung zu verweigern. Zuvor genehmigte Anforderungen können zugriff widerrufen werden, indem Sie **"Widerrufen"** auswählen.

#### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Berechtigungsanforderung für erhöhte Rechte zu genehmigen:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Beispiel:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Um eine Berechtigungsanforderung für erhöhte Rechte zu verweigern, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Beispiel:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Löschen einer Richtlinie für privilegierten Zugriff in Office 365

Wenn sie in Ihrer Organisation nicht mehr benötigt wird, können Sie eine Richtlinie für den privilegierten Zugriff löschen.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Wählen Sie **"Zugriffsrichtlinien und -anforderungen verwalten" aus.**

4. Wählen Sie **"Richtlinien konfigurieren"** aus.

5. Wählen Sie die Richtlinie aus, die Sie löschen möchten, und wählen Sie dann **Richtlinie entfernen aus.**

6. Wählen Sie **Schließen** aus.

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um eine Richtlinie für privilegierten Zugriff zu löschen:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Deaktivieren des privilegierten Zugriffs in Office 365

Bei Bedarf können Sie die Verwaltung des privilegierten Zugriffs für Ihre Organisation deaktivieren. Durch das Deaktivieren des privilegierten Zugriffs werden keine zugehörigen Genehmigungsrichtlinien oder Genehmigungsgruppen gelöscht.

### <a name="in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Wechseln Sie im Admin Center zu **Einstellungen**  >  **Org Einstellungen** Security &  >  **Privacy**  >  **Privileged Access.**

3. Aktivieren Sie die **Option "Genehmigungen für privilegierte Zugriffssteuerung anfordern".**

### <a name="in-exchange-management-powershell"></a>In Exchange Management PowerShell

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um den privilegierten Zugriff zu deaktivieren:

```PowerShell
Disable-ElevatedAccessControl
```
