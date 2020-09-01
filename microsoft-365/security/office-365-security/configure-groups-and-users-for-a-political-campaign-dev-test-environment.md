---
title: Konfigurieren von Gruppen & Benutzern ⁠– politische Kampagne, Entwicklungs-/Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Zusammenfassung: Informationen zum Erstellen von Office 365- und Enterprise Mobility + Security-Testabonnements (EMS) mit Benutzern und Gruppen für eine Entwicklungs-/Testumgebung für eine politische Kampagne.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7282659399d2541b50c43dffc9fc8690baecd803
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308439"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung

 **Zusammenfassung:** Informationen zum Erstellen von Office 365- und Enterprise Mobility + Security-Testabonnements (EMS) mit Benutzern und Gruppen für eine Entwicklungs-/Testumgebung für eine politische Kampagne.

Folgen Sie den Anweisungen in diesem Artikel beim Erstellen einer Entwicklungs-/Testumgebung, die vereinfachte Benutzerkonten und Gruppen für die Lösung [Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) enthält.

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Phase 1: Erstellen Ihrer Office 365-Entwicklungs-/Testumgebung

In dieser Phase erhalten Sie Testabonnements für Office 365 E5 und Enterprise Mobility + Security (EMS) E5 für eine fiktive Organisation, die eine politische Kampagne darstellt.

Befolgen Sie zunächst die Anweisungen unter **Phase 2** von [Einfache Basiskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Als Nächstes registrieren Sie sich für das EMS E5-Testabonnement und fügen es derselben Organisation wie Ihr Testabonnement hinzu.

1. Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Testabonnement beim Admin Center an. Hilfe finden Sie unter [Wo kann ich mich anmelden?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Klicken Sie auf die Kachel **Admin**.

3. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in Ihrem Browser im linken Navigationsbereich auf **Abrechnung > Dienste kaufen**.

4. Suchen Sie auf der Seite **Dienste kaufen** den Artikel **Enterprise Mobility + Security E5**. Platzieren Sie den Mauszeiger auf dem Artikelnamen, und klicken Sie auf **Start free trial**.

5. Klicken Sie auf der Seite für die **Bestätigung Ihrer Bestellung** auf **Jetzt versuchen**.

6. Klicken Sie auf der Seite **Bestellbestätigung** auf **Weiter**.

Aktivieren Sie als Nächstes die EMS E5-Lizenz für Ihr globales Administratorkonto.

1. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in Ihrem Browser im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.

2. Klicken Sie auf Ihr globales Administratorkonto und dann auf **Bearbeiten**, um die **Produktlizenzen** anzuzeigen.

3. Setzen Sie im Bereich **Product licenses** die Produktlizenz für **Enterprise Mobility + Security E5** auf **On**. Klicken Sie auf **Speichern** und dann auf **Schließen**.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Phase 2: Erstellen und Konfigurieren der Azure Active Directory(AD)-Gruppen

In dieser Phase werden die Azure AD-Gruppen für Ihre Kampagne erstellt und konfiguriert.

Erstellen Sie zuerst eine Reihe von Gruppen für eine typische politische Kampagne mit dem Azure-Portal.

1. Wechseln Sie auf einer neuen Registerkarte im Browser zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com). Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Office 365 E5-Testabonnement an.

2. Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.

3. Führen Sie die folgenden Schritte für jeden Gruppenname in dieser Liste durch:

   - Senior-Mitarbeiter und strategische Mitarbeiter

   - IT-Mitarbeiter

   - Analytiker

   - Stammpersonal

   - Betriebspersonal

   - Außendienstmitarbeiter

1. Klicken Sie auf dem Blatt **Alle Gruppen** auf **+ Neue Gruppe**.

2. Geben Sie den Gruppennamen aus der Liste unter **Name** ein.

3. Wählen Sie unter **Mitgliedschaft** **Dynamischer Benutzer** aus.

4. Klicken Sie auf **Ja** für **Office-Features aktivieren**.

5. Klicken Sie auf **Dynamische Abfrage hinzufügen**.

6. Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.

7. Wählen Sie im nächsten Feld **Gleich** aus.

8. Geben Sie im nächsten Feld den Gruppennamen aus der Liste ein.

9. Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.

10. Klicken Sie auf **Benutzer und Gruppen – Alle Gruppen**.

Konfigurieren Sie als Nächstes die Gruppen so, dass Mitgliedern automatisch Office 365 E5- und EMS E5-Lizenzen zugewiesen werden.

1. Klicken Sie im Azure-Portal auf **Azure Active Directory > Lizenzen > Alle Produkte**.

2. Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **+ Zuweisen**.

3. Klicken Sie auf dem Blatt **Lizenz zuweisen** auf **Benutzer und Gruppen**.

4. Wählen Sie in der Liste der Gruppen Folgendes aus:

   - Analytiker

   - Außendienstmitarbeiter

   - IT-Mitarbeiter

   - Betriebspersonal

   - Stammpersonal

   - Senior-Mitarbeiter und strategische Mitarbeiter

5. Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.

6. Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.

## <a name="phase-3-add-your-user-accounts"></a>Phase 3: Hinzufügen von Benutzerkonten

In dieser Phase werden beispielhafte Benutzerkonten für Ihre politische Kampagne hinzugefügt.

Zunächst müssen Sie [eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul herstellen](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).

Geben Sie anschließend den Namen Ihrer Organisation, Ihren Standort und ein gemeinsames Kennwort ein, und führen Sie dann die folgenden Befehle an der PowerShell-Eingabeaufforderung oder in der ISE-Umgebung ein (Integrated Script Environment) aus:

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> Die Verwendung eines gemeinsamen Kennworts an dieser Stelle dient der Automatisierung und einfacher Konfiguration für eine Entwicklungs-/Testumgebung. Für die Verwendung in Produktionsabonnements wird dies nicht empfohlen. Beim Anmelden mit einem dieser neuen Benutzerkonten werden Sie dazu aufgefordert, das Kennwort zu ändern.

Gehen Sie folgendermaßen vor, um sicherzustellen, dass die dynamische Gruppenmitgliedschaft und gruppenbasierte Lizenzierung ordnungsgemäß funktionieren.

1. Klicken Sie auf der Registerkarte **Microsoft Office Home** in Ihrem Browser auf die Kachel **Admin**.

2. Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** des Browsers auf **Benutzer**.

3. Klicken Sie in der Benutzerliste auf **Kandidat**.

4. Stellen Sie im Bereich mit den Eigenschaften für das Benutzerkonto **Kandidat** Folgendes sicher:

   - Ist Mitglied der Gruppe **Senior-Mitarbeiter und strategische Mitarbeiter** (unter **Gruppenmitgliedschaften**).

   - Dem Benutzerkonto wurden **Enterprise Mobilität + Security E5**- und **Office 365 Enterprise E5**-Lizenzen (unter **Produktlizenzen**) zugewiesen.

5. Schließen Sie den Bereich für das Benutzerkonto **Kandidat**.

## <a name="record-values-for-future-reference"></a>Notieren von Werten für zukünftige Verwendung

Notieren Sie diese Werte für die Arbeit mit Office 365- und EMS-Testabonnements für diese Entwicklung-/Testumgebung:

- Organisationsname für das Testabonnement: ![Unterstrichen](../../media/Common-Images/TableLine.png)

  Für den Domänennamen contoso.onmicrosoft.com des Testabonnements lautet der Name der Organisation zum Beispiel „contoso“.

- Name des globalen Administrators: ![Unterstrichen](../../media/Common-Images/TableLine.png).onmicrosoft.com

  Notieren Sie sich das Kennwort für dieses Konto und das gemeinsame ursprüngliche Kennwort für die anderen Benutzerkonten, und bewahren Sie diese an einem sicheren Ort auf.

## <a name="next-step"></a>Nächster Schritt

Erstellen Sie die vier verschiedenen Arten von SharePoint Online-Teamwebsites in dieser Entwicklungs-/Testumgebung mit [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).

## <a name="see-also"></a>Siehe auch

[Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Cloudakzeptanz und Hybridlösungen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
