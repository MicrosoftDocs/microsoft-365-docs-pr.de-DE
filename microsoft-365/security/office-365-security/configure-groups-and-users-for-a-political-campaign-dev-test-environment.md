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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Zusammenfassung: Informationen zum Erstellen von Office 365- und Enterprise Mobility + Security-Testabonnements (EMS) mit Benutzern und Gruppen für eine Entwicklungs-/Testumgebung für eine politische Kampagne.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d23539951e4d51fcd29417ab71ce599853d7537
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165703"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="32fdd-103">Konfigurieren von Gruppen und Benutzern für eine politische Kampagne in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="32fdd-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="32fdd-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="32fdd-104">**Applies to**</span></span>
- [<span data-ttu-id="32fdd-105">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="32fdd-105">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

 <span data-ttu-id="32fdd-106">**Zusammenfassung:** Informationen zum Erstellen von Office 365- und Enterprise Mobility + Security-Testabonnements (EMS) mit Benutzern und Gruppen für eine Entwicklungs-/Testumgebung für eine politische Kampagne.</span><span class="sxs-lookup"><span data-stu-id="32fdd-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="32fdd-107">Folgen Sie den Anweisungen in diesem Artikel beim Erstellen einer Entwicklungs-/Testumgebung, die vereinfachte Benutzerkonten und Gruppen für die Lösung [Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) enthält.</span><span class="sxs-lookup"><span data-stu-id="32fdd-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="32fdd-108">Phase 1: Erstellen Ihrer Office 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="32fdd-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="32fdd-109">In dieser Phase erhalten Sie Testabonnements für Office 365 E5 und Enterprise Mobility + Security (EMS) E5 für eine fiktive Organisation, die eine politische Kampagne darstellt.</span><span class="sxs-lookup"><span data-stu-id="32fdd-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="32fdd-110">Befolgen Sie zunächst die Anweisungen unter **Phase 2** von [Einfache Basiskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="32fdd-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="32fdd-111">Als Nächstes registrieren Sie sich für das EMS E5-Testabonnement und fügen es derselben Organisation wie Ihr Testabonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="32fdd-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="32fdd-112">Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Testabonnement beim Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="32fdd-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="32fdd-113">Hilfe finden Sie unter [Wo kann ich mich anmelden?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="32fdd-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="32fdd-114">Klicken Sie auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="32fdd-115">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in Ihrem Browser im linken Navigationsbereich auf **Abrechnung > Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="32fdd-p102">Suchen Sie auf der Seite **Dienste kaufen** den Artikel **Enterprise Mobility + Security E5**. Platzieren Sie den Mauszeiger auf dem Artikelnamen, und klicken Sie auf **Start free trial**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="32fdd-118">Klicken Sie auf der Seite für die **Bestätigung Ihrer Bestellung** auf **Jetzt versuchen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="32fdd-119">Klicken Sie auf der Seite **Bestellbestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="32fdd-120">Aktivieren Sie als Nächstes die EMS E5-Lizenz für Ihr globales Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="32fdd-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="32fdd-121">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in Ihrem Browser im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="32fdd-122">Klicken Sie auf Ihr globales Administratorkonto und dann auf **Bearbeiten**, um die **Produktlizenzen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="32fdd-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="32fdd-123">Setzen Sie im Bereich **Product licenses** die Produktlizenz für **Enterprise Mobility + Security E5** auf **On**. Klicken Sie auf **Speichern** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="32fdd-124">Phase 2: Erstellen und Konfigurieren der Azure Active Directory(AD)-Gruppen</span><span class="sxs-lookup"><span data-stu-id="32fdd-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="32fdd-125">In dieser Phase werden die Azure AD-Gruppen für Ihre Kampagne erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="32fdd-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="32fdd-126">Erstellen Sie zuerst eine Reihe von Gruppen für eine typische politische Kampagne mit dem Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="32fdd-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="32fdd-127">Erstellen Sie eine separate Registerkarte in Ihrem Browser, und wechseln Sie dann zum Azure-Portal unter <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="32fdd-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="32fdd-128">Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Office 365 E5-Testabonnement an.</span><span class="sxs-lookup"><span data-stu-id="32fdd-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="32fdd-129">Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="32fdd-130">Führen Sie die folgenden Schritte für jeden Gruppenname in dieser Liste durch:</span><span class="sxs-lookup"><span data-stu-id="32fdd-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="32fdd-131">Senior-Mitarbeiter und strategische Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="32fdd-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="32fdd-132">IT-Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="32fdd-132">IT staff</span></span>

   - <span data-ttu-id="32fdd-133">Analytiker</span><span class="sxs-lookup"><span data-stu-id="32fdd-133">Analytics staff</span></span>

   - <span data-ttu-id="32fdd-134">Stammpersonal</span><span class="sxs-lookup"><span data-stu-id="32fdd-134">Regular core staff</span></span>

   - <span data-ttu-id="32fdd-135">Betriebspersonal</span><span class="sxs-lookup"><span data-stu-id="32fdd-135">Operations staff</span></span>

   - <span data-ttu-id="32fdd-136">Außendienstmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="32fdd-136">Field staff</span></span>

1. <span data-ttu-id="32fdd-137">Klicken Sie auf dem Blatt **Alle Gruppen** auf **+ Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="32fdd-138">Geben Sie den Gruppennamen aus der Liste unter **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="32fdd-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="32fdd-139">Wählen Sie unter **Mitgliedschaft** **Dynamischer Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="32fdd-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="32fdd-140">Klicken Sie auf **Ja** für **Office-Features aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="32fdd-141">Klicken Sie auf **Dynamische Abfrage hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="32fdd-142">Wählen Sie unter **Benutzer hinzufügen** die Option **Abteilung** aus.</span><span class="sxs-lookup"><span data-stu-id="32fdd-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="32fdd-143">Wählen Sie im nächsten Feld **Gleich** aus.</span><span class="sxs-lookup"><span data-stu-id="32fdd-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="32fdd-144">Geben Sie im nächsten Feld den Gruppennamen aus der Liste ein.</span><span class="sxs-lookup"><span data-stu-id="32fdd-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="32fdd-145">Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="32fdd-146">Klicken Sie auf **Benutzer und Gruppen – Alle Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="32fdd-147">Konfigurieren Sie als Nächstes die Gruppen so, dass Mitgliedern automatisch Office 365 E5- und EMS E5-Lizenzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="32fdd-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="32fdd-148">Klicken Sie im Azure-Portal auf **Azure Active Directory > Lizenzen > Alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="32fdd-149">Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **+ Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="32fdd-150">Klicken Sie auf dem Blatt **Lizenz zuweisen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="32fdd-151">Wählen Sie in der Liste der Gruppen Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="32fdd-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="32fdd-152">Analytiker</span><span class="sxs-lookup"><span data-stu-id="32fdd-152">Analytics staff</span></span>

   - <span data-ttu-id="32fdd-153">Außendienstmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="32fdd-153">Field staff</span></span>

   - <span data-ttu-id="32fdd-154">IT-Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="32fdd-154">IT staff</span></span>

   - <span data-ttu-id="32fdd-155">Betriebspersonal</span><span class="sxs-lookup"><span data-stu-id="32fdd-155">Operations staff</span></span>

   - <span data-ttu-id="32fdd-156">Stammpersonal</span><span class="sxs-lookup"><span data-stu-id="32fdd-156">Regular core staff</span></span>

   - <span data-ttu-id="32fdd-157">Senior-Mitarbeiter und strategische Mitarbeiter</span><span class="sxs-lookup"><span data-stu-id="32fdd-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="32fdd-158">Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="32fdd-159">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="32fdd-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="32fdd-160">Phase 3: Hinzufügen von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="32fdd-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="32fdd-161">In dieser Phase werden beispielhafte Benutzerkonten für Ihre politische Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="32fdd-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="32fdd-162">Zunächst müssen Sie [eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul herstellen](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="32fdd-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).</span></span>

<span data-ttu-id="32fdd-163">Geben Sie anschließend den Namen Ihrer Organisation, Ihren Standort und ein gemeinsames Kennwort ein, und führen Sie dann die folgenden Befehle an der PowerShell-Eingabeaufforderung oder in der ISE-Umgebung ein (Integrated Script Environment) aus:</span><span class="sxs-lookup"><span data-stu-id="32fdd-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

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
> <span data-ttu-id="32fdd-p104">Die Verwendung eines gemeinsamen Kennworts an dieser Stelle dient der Automatisierung und einfacher Konfiguration für eine Entwicklungs-/Testumgebung. Für die Verwendung in Produktionsabonnements wird dies nicht empfohlen. Beim Anmelden mit einem dieser neuen Benutzerkonten werden Sie dazu aufgefordert, das Kennwort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="32fdd-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="32fdd-167">Gehen Sie folgendermaßen vor, um sicherzustellen, dass die dynamische Gruppenmitgliedschaft und gruppenbasierte Lizenzierung ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="32fdd-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="32fdd-168">Klicken Sie auf der Registerkarte **Microsoft Office Home** in Ihrem Browser auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="32fdd-169">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** des Browsers auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="32fdd-170">Klicken Sie in der Benutzerliste auf **Kandidat**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="32fdd-171">Stellen Sie im Bereich mit den Eigenschaften für das Benutzerkonto **Kandidat** Folgendes sicher:</span><span class="sxs-lookup"><span data-stu-id="32fdd-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="32fdd-172">Ist Mitglied der Gruppe **Senior-Mitarbeiter und strategische Mitarbeiter** (unter **Gruppenmitgliedschaften**).</span><span class="sxs-lookup"><span data-stu-id="32fdd-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="32fdd-173">Dem Benutzerkonto wurden **Enterprise Mobilität + Security E5**- und **Office 365 Enterprise E5**-Lizenzen (unter **Produktlizenzen**) zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="32fdd-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="32fdd-174">Schließen Sie den Bereich für das Benutzerkonto **Kandidat**.</span><span class="sxs-lookup"><span data-stu-id="32fdd-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="32fdd-175">Notieren von Werten für zukünftige Verwendung</span><span class="sxs-lookup"><span data-stu-id="32fdd-175">Record values for future reference</span></span>

<span data-ttu-id="32fdd-176">Notieren Sie diese Werte für die Arbeit mit Office 365- und EMS-Testabonnements für diese Entwicklung-/Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="32fdd-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="32fdd-177">Organisationsname für das Testabonnement:</span><span class="sxs-lookup"><span data-stu-id="32fdd-177">Your trial subscription organization name:</span></span> ![Unterstrichen](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="32fdd-179">Für den Domänennamen contoso.onmicrosoft.com des Testabonnements lautet der Name der Organisation zum Beispiel „contoso“.</span><span class="sxs-lookup"><span data-stu-id="32fdd-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="32fdd-180">Name des globalen Administrators:</span><span class="sxs-lookup"><span data-stu-id="32fdd-180">The global administrator name:</span></span> ![Unterstrichen](../../media/Common-Images/TableLine.png)<span data-ttu-id="32fdd-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="32fdd-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="32fdd-183">Notieren Sie sich das Kennwort für dieses Konto und das gemeinsame ursprüngliche Kennwort für die anderen Benutzerkonten, und bewahren Sie diese an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="32fdd-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="32fdd-184">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="32fdd-184">Next step</span></span>

<span data-ttu-id="32fdd-185">Erstellen Sie die vier verschiedenen Arten von SharePoint Online-Teamwebsites in dieser Entwicklungs-/Testumgebung mit [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="32fdd-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32fdd-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32fdd-186">See also</span></span>

[<span data-ttu-id="32fdd-187">Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützigen Organisationen und andere agile Organisationen</span><span class="sxs-lookup"><span data-stu-id="32fdd-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="32fdd-188">Erstellen von Teamwebsites in einer Entwicklungs-/Testumgebung für eine politische Kampagne</span><span class="sxs-lookup"><span data-stu-id="32fdd-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="32fdd-189">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="32fdd-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="32fdd-190">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="32fdd-190">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
