---
title: Auf ein kompromittiertes E-Mail-Konto reagieren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Erfahren Sie, wie Sie ein angegriffenes E-Mail-Konto mit den in Microsoft 365 verfügbaren Tools erkennen und darauf reagieren.
ms.openlocfilehash: 2830fd10b633e094c92fd98fe61ce678a4da842b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200119"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="2c6cd-103">Auf ein kompromittiertes E-Mail-Konto reagieren</span><span class="sxs-lookup"><span data-stu-id="2c6cd-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2c6cd-104">**Zusammenfassung** Erfahren Sie, wie Sie ein angegriffenes E-Mail-Konto in Microsoft 365 erkennen und darauf reagieren.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="2c6cd-105">Was ist ein angegriffenes E-Mail-Konto in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2c6cd-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="2c6cd-106">Der Zugriff auf Microsoft 365-Postfächer, Daten und andere Dienste wird mithilfe von Anmeldeinformationen gesteuert, z. B. einem Benutzernamen und einem Kennwort oder einer PIN.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="2c6cd-107">Wenn es einer anderen Person gelingt, diese Anmeldeinformationen zu stehlen, gelten die Anmeldeinformationen als kompromittiert.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="2c6cd-108">Mit ihnen kann sich der Angreifer als der ursprüngliche Benutzer anmelden und unerlaubte Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="2c6cd-109">Mit den gestohlenen Anmeldeinformationen kann der Angreifer zudem auf das Microsoft 365-Postfach des Benutzers sowie auf SharePoint-Ordner oder -Dateien im OneDrive des Benutzers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="2c6cd-110">Angreifer senden häufig E-Mails im Namen des ursprünglichen Benutzers an Empfänger innerhalb und außerhalb der Organisation.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="2c6cd-111">Wenn der Angreifer Daten an externe Empfänger sendet, wird dies als Daten-Exfiltration bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="2c6cd-112">Symptome eines angegriffenen Microsoft-E-Mail-Kontos</span><span class="sxs-lookup"><span data-stu-id="2c6cd-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="2c6cd-113">Benutzer stellen möglicherweise ungewöhnliche Aktivitäten in ihren Microsoft 365-Postfächern fest und melden diese.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="2c6cd-114">Hier sind einige häufige Symptome:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="2c6cd-115">Verdächtige Aktivitäten, z. B. fehlende oder gelöschte E-Mails.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="2c6cd-116">Andere Benutzer haben möglicherweise E-Mails von dem angegriffenen Konto erhalten, ohne dass die entsprechende E-Mail im Ordner **Gesendete Elemente** des Absenders vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="2c6cd-117">Das Vorhandensein von Posteingangsregeln, die nicht vom entsprechenden Benutzer oder Administrator erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="2c6cd-118">Diese Regeln können automatisch E-Mails an unbekannte Adressen weiterleiten oder sie in die Ordner **Notizen**, **Junk-E-Mail** oder **RSS-Abonnements** verschieben.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="2c6cd-119">Der Anzeigename des Benutzers wurde möglicherweise in der globalen Adressliste geändert.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="2c6cd-120">Es können keine E-Mails aus dem Postfach des Benutzers gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="2c6cd-121">Die Ordner „Gesendete Elemente“ oder „Gelöschte Elemente“ in Microsoft Outlook oder Outlook im Web (früher als Outlook Web App bezeichnet) enthalten Nachrichten, die häufig im Zusammenhang mit gehackten Kontos stehen, z. B. „Ich sitze in London fest, sende Geld.“</span><span class="sxs-lookup"><span data-stu-id="2c6cd-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="2c6cd-122">Ungewöhnliche Profiländerungen, z. B. wurden der Name, die Telefonnummer oder die Postleitzahl aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="2c6cd-123">Ungewöhnliche Änderungen der Anmeldeinformationen, z. B. sind mehrere Kennwortänderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="2c6cd-124">Eine E-Mail-Weiterleitung wurde kürzlich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="2c6cd-125">Eine ungewöhnliche Signatur wurde kürzlich hinzugefügt, z. B. eine gefälschte Banksignatur oder eine Signatur für ein verschreibungspflichtiges Medikament.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="2c6cd-126">Wenn ein Benutzer eines der oben genannten Symptome meldet, sollten Sie weitere Untersuchungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="2c6cd-127">Das Microsoft 365 Security & Compliance Center und das Azure-Portal bieten Tools, mit denen Sie die Aktivität eines Benutzerkontos untersuchen können, von dem Sie vermuten, dass es angegriffen wurde.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="2c6cd-128">**Unified Audit Logs im Security & Compliance Center**: Überprüfen Sie alle Aktivitäten des verdächtigen Kontos, indem Sie die Ergebnisse nach dem Datumsbereich (unmittelbar vor dem Auftreten der verdächtigen Aktivität bis zum aktuellen Datum) filtern.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="2c6cd-129">Filtern Sie die Aktivitäten nicht während der Suche.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="2c6cd-130">**Administratorüberwachungsprotokolle im EAC**: In Exchange Online können Sie im Exchange Admin Center (EAC) Einträge im Administratorüberwachungsprotokoll durchsuchen und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="2c6cd-131">Im Administratorüberwachungsprotokoll werden bestimmte Aktionen aufgezeichnet, die basierend auf den jeweiligen Exchange Online PowerShell-Cmdlets von Administratoren und Benutzern mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="2c6cd-132">In Einträgen im Administratorüberwachungsprotokoll finden Sie Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="2c6cd-133">**Azure AD-Anmeldeprotokolle und andere Risikoberichte im Azure AD-Portal**: Überprüfen Sie die Werte in den folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="2c6cd-134">IP-Adresse überprüfen</span><span class="sxs-lookup"><span data-stu-id="2c6cd-134">Review IP address</span></span>
  - <span data-ttu-id="2c6cd-135">Anmeldeorte</span><span class="sxs-lookup"><span data-stu-id="2c6cd-135">sign-in locations</span></span>
  - <span data-ttu-id="2c6cd-136">Anmeldezeiten</span><span class="sxs-lookup"><span data-stu-id="2c6cd-136">sign-in times</span></span>
  - <span data-ttu-id="2c6cd-137">Anmeldeerfolge oder -fehler</span><span class="sxs-lookup"><span data-stu-id="2c6cd-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="2c6cd-138">Sichern und Wiederherstellen der E-Mail-Funktion für ein vermutlich angegriffenes Microsoft 365-Konto und -Postfach</span><span class="sxs-lookup"><span data-stu-id="2c6cd-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="2c6cd-139">Selbst nachdem Sie wieder Zugriff auf Ihr Konto haben, hat der Angreifer möglicherweise versteckte Zugangsmöglichkeiten hinzugefügt, durch die er wieder die Kontrolle über das Konto übernehmen kann.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="2c6cd-140">Sie müssen so früh wie möglich die folgenden Schritte durchführen, um wieder Zugriff auf Ihr Konto zu erhalten. So stellen Sie sicher, dass der Angreifer nicht wieder die Kontrolle über Ihr Konto übernimmt.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="2c6cd-141">Mit diesen Schritten können Sie alle versteckten Zugangsmöglichkeiten entfernen, die der Angreifer möglicherweise zu Ihrem Konto hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="2c6cd-142">Nachdem Sie diese Schritte ausgeführt haben, empfehlen wir, dass Sie einen Virusscan durchführen, um sicherzustellen, dass Ihr Computer nicht beeinträchtigt ist.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="2c6cd-143">Schritt 1: Setzen Sie das Benutzerkennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-143">Step 1 Reset the user's password</span></span>

<span data-ttu-id="2c6cd-144">Folgen Sie den Verfahren unter [Zurücksetzen eines Geschäftskennworts für eine andere Person](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="2c6cd-144">Follow the procedures in [Reset a business password for someone](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="2c6cd-145">Senden Sie das neue Kennwort nicht per E-Mail an den vorgesehenen Benutzer, da der Angreifer weiterhin Zugriff auf das Postfach hat.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-145">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="2c6cd-146">Stellen Sie sicher, dass das Kennwort sicher ist und dass es Groß- und Kleinbuchstaben, mindestens eine Zahl und mindestens ein Sonderzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-146">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="2c6cd-147">Verwenden Sie nicht eines Ihrer letzten fünf Kennwörter wieder.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-147">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="2c6cd-148">Obwohl die Kennwortverlaufsanforderung die Verwendung eines aktuelleren Kennworts zulässt, sollten Sie eines auswählen, das der Angreifer nicht erraten kann.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-148">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="2c6cd-149">Wenn Ihre lokale Identität mit Microsoft 365 verbunden ist, müssen Sie das Kennwort lokal ändern und dann Ihren Administrator über den Angriff benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-149">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="2c6cd-150">Sorgen Sie dafür, dass App-Kennwörter aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-150">Be sure to update app passwords.</span></span> <span data-ttu-id="2c6cd-151">App-Kennwörter werden nicht automatisch widerrufen, wenn ein Benutzerkontokennwort zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-151">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="2c6cd-152">Der Benutzer sollte vorhandene App-Kennwörter löschen und neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-152">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="2c6cd-153">Anweisungen hierzu finden Sie unter [Erstellen und Löschen von App-Kennwörtern über die Seite "Zusätzliche Sicherheitsüberprüfung"](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="2c6cd-153">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="2c6cd-154">Es wird dringend empfohlen, dass Sie die mehrstufige Authentifizierung (MFA) aktivieren, um Angriffe zu verhindern, insbesondere für Konten mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-154">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="2c6cd-155">Weitere Informationen zu MFA finden Sie unter [Einrichten der mehrstufigen Authentifizierung](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="2c6cd-155">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="2c6cd-156">Schritt 2: Entfernen Sie verdächtige E-Mail-Weiterleitungsadressen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-156">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="2c6cd-157">Öffnen Sie das Microsoft 365 Admin Center unter <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-157">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="2c6cd-158">Wechseln Sie zu **Benutzer** \> **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-158">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="2c6cd-159">Suchen Sie das fragliche Benutzerkonto, und wählen Sie den Benutzer (Zeile) aus, ohne das Kontrollkästchen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-159">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="2c6cd-160">Wählen Sie auf der daraufhin angezeigten Detail-Flyoutseite die Registerkarte **E-Mail** aus.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-160">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="2c6cd-161">Wenn der Wert im Abschnitt **E-Mail-Weiterleitung** **Angewendet** lautet, klicken Sie auf **E-Mail-Weiterleitung verwalten**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-161">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="2c6cd-162">Deaktivieren Sie auf der angezeigten **E-Mail-Weiterleitung**-Flyoutseite **Alle an dieses Postfach gesendeten E-Mails weiterleiten**, und klicken Sie dann auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-162">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="2c6cd-163">Schritt 3: Entfernen Sie verdächtige Posteingangsregeln.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-163">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="2c6cd-164">Melden Sie sich beim Postfach des Benutzers mithilfe von Outlook im Web an.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-164">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="2c6cd-165">Klicken Sie auf das Zahnradsymbol, und klicken Sie auf **E-Mail**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-165">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="2c6cd-166">Klicken Sie auf **Posteingangs- und Aufräumregeln**, und überprüfen Sie die Regeln.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-166">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="2c6cd-167">Deaktivieren oder löschen Sie verdächtige Regeln.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-167">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="2c6cd-168">Schritt 4: Sorgen Sie dafür, dass der Benutzer wieder E-Mails senden kann.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-168">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="2c6cd-169">Wenn das vermutlich angegriffene Postfach unerlaubt zum Senden von Spam-E-Mails verwendet wurde, ist es wahrscheinlich, dass das Senden von E-Mails aus dem Postfach gesperrt wurde.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-169">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="2c6cd-170">Um die Sperre aufzuheben, führen Sie die Schritte unter [Entfernen von Benutzern, Domänen oder IP-Adressen aus einer Sperrliste nach dem Senden von Spamnachrichten](removing-user-from-restricted-users-portal-after-spam.md) durch.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-170">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="2c6cd-171">Schritt 5 (optional): Sperren Sie die Anmeldung beim Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-171">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c6cd-172">Sie können die Anmeldung bei dem vermutlich angegriffenen Konto sperren, bis Sie glauben, dass es sicher ist, den Zugriff wieder zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-172">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="2c6cd-173">Öffnen Sie das Microsoft 365 Admin Center, und gehen Sie zu **Benutzer** \> **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-173">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="2c6cd-174">Suchen Sie das Benutzerkonto, wählen Sie es aus, klicken Sie auf ![Mehr-Symbol](../../media/ITPro-EAC-MoreOptionsIcon.png), und wählen Sie dann **Anmeldestatus bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-174">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="2c6cd-175">Wählen Sie im daraufhin angezeigten Bereich **Anmeldung blockieren** die Option **Anmeldung für diesen Benutzer blockieren** aus, und klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-175">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="2c6cd-176">Öffnen Sie das Exchange Admin Center (EAC) unter <admin.protection.outlook.com/ecp/>, und wechseln Sie zu **Empfänger > Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-176">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="2c6cd-177">Suchen Sie den Benutzer und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-177">Find and select the select the user.</span></span> <span data-ttu-id="2c6cd-178">Führen Sie im Detailbereich die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-178">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="2c6cd-179">Führen Sie im Abschnitt **Telefon- und Sprachfunktionen** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-179">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="2c6cd-180">Wählen Sie **Exchange ActiveSync deaktivieren** aus, und klicken Sie dann in der angezeigten Warnung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-180">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="2c6cd-181">Wählen Sie **OWA für Geräte deaktivieren** aus, und klicken Sie dann in der angezeigten Warnung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-181">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="2c6cd-182">Klicken Sie im Abschnitt **E-Mail-Konnektivität** für Outlook im Web auf **Deaktivieren**, und klicken Sie dann in der angezeigten Warnung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-182">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="2c6cd-183">Schritt 6 (optional): Entfernen Sie das vermutlich angegriffen Konto aus allen Administratorrollengruppen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-183">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="2c6cd-184">Die Mitgliedschaft bei der Administratorrollengruppe kann wiederhergestellt werden, nachdem das Konto gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-184">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="2c6cd-185">Melden Sie sich mit einem globalen Administratorkonto an:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-185">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="2c6cd-186">Führen Sie im Microsoft 365 Admin Center die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-186">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="2c6cd-187">Wechseln Sie zu **Benutzer** \> **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-187">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="2c6cd-188">Suchen Sie das Benutzerkonto, wählen Sie es aus, klicken Sie auf ![Mehr-Symbol](../../media/ITPro-EAC-MoreOptionsIcon.png), und wählen Sie dann **Rollen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-188">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="2c6cd-189">Entfernen Sie alle Administratorrollen, die dem Konto zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-189">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="2c6cd-190">Klicken Sie nach Abschluss des Vorgangs auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-190">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="2c6cd-191">Führen Sie im Security & Compliance Center unter <https://protection.office.com> die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-191">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="2c6cd-192">Wählen Sie **Berechtigungen** aus, wählen Sie die einzelnen Rollengruppen in der Liste aus, und suchen Sie auf der daraufhin angezeigten Detail-Flyoutseite im Abschnitt **Mitglieder** nach dem Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-192">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="2c6cd-193">Führen Sie die folgenden Schritte aus, wenn die Rollengruppe das Benutzerkonto enthält:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-193">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="2c6cd-194">a.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-194">a.</span></span> <span data-ttu-id="2c6cd-195">Klicken Sie neben **Mitglieder** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-195">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="2c6cd-196">b.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-196">b.</span></span> <span data-ttu-id="2c6cd-197">Klicken Sie auf der daraufhin angezeigten Flyoutseite **Mitglieder auswählen bearbeiten** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-197">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="2c6cd-198">c.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-198">c.</span></span> <span data-ttu-id="2c6cd-199">Wählen Sie auf der nun angezeigten Flyoutseite **Mitglieder auswählen** das Benutzerkonto aus, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-199">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="2c6cd-200">Klicken Sie abschließend auf **Fertig**, **Speichern** und dann**Schließen**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-200">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="2c6cd-201">Führen Sie im EAC unter <admin.protection.outlook.com/ecp/> die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-201">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="2c6cd-202">Wählen Sie **Berechtigungen**aus, wählen Sie die einzelnen Rollengruppen manuell aus, und überprüfen Sie im Detailbereich im Abschnitt **Mitglieder** die Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-202">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="2c6cd-203">Führen Sie die folgenden Schritte aus, wenn die Rollengruppe das Benutzerkonto enthält:</span><span class="sxs-lookup"><span data-stu-id="2c6cd-203">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="2c6cd-204">a.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-204">a.</span></span> <span data-ttu-id="2c6cd-205">Wählen Sie die Rollengruppe aus, und klicken Sie auf **Bearbeiten** ![Symbol „Bearbeiten“](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="2c6cd-205">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="2c6cd-206">b.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-206">b.</span></span> <span data-ttu-id="2c6cd-207">Wählen Sie im Abschnitt **Mitglieder** das Benutzerkonto aus, und klicken Sie dann auf **Entfernen** ![Symbol „Entfernen“](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="2c6cd-207">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="2c6cd-208">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-208">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="2c6cd-209">Schritt 7 (optional): Zusätzliche Vorsichtsmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="2c6cd-209">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="2c6cd-210">Stellen Sie sicher, dass Sie die gesendeten Elemente überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-210">Make sure that you verify your sent items.</span></span> <span data-ttu-id="2c6cd-211">Möglicherweise müssen Sie Personen in Ihrer Kontaktliste informieren, dass Ihr Konto manipuliert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-211">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="2c6cd-212">Angreifer können sie um Geld gebeten haben, z. B. unter dem Vorwand, dass Sie in einem anderen Land in einer Notsituation sind und Geld benötigen, oder der Angreifer hat ihnen möglicherweise einen Virus gesendet, um auch ihren Computer anzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-212">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="2c6cd-213">Alle anderen Dienste, die dieses Exchange-Konto als alternatives E-Mail-Konto verwendet haben, wurden möglicherweise auch manipuliert.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-213">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="2c6cd-214">Führen Sie zunächst diese Schritte für Ihr Microsoft 365-Abonnement aus, und führen Sie sie dann für Ihre anderen Konten aus.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-214">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="2c6cd-215">Stellen Sie sicher, dass Ihre Kontaktinformationen, z. B. Telefonnummern und Adressen, richtig sind.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-215">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="2c6cd-216">Sichern von Microsoft 365 wie ein Profi für Internetsicherheit</span><span class="sxs-lookup"><span data-stu-id="2c6cd-216">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="2c6cd-217">Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-217">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="2c6cd-218">Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-218">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="2c6cd-219">Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-219">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="2c6cd-220">Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-220">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="2c6cd-221">Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-221">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="2c6cd-222">Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-222">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="2c6cd-223">Über 90 Tage hinaus.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-223">Beyond 90 days.</span></span> <span data-ttu-id="2c6cd-224">Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2c6cd-224">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c6cd-225">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c6cd-225">See also</span></span>

- [<span data-ttu-id="2c6cd-226">Erkennen und Korrigieren von Outlook-Regeln und benutzerdefinierten Formularen für Einschleusungsangriffe in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c6cd-226">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="2c6cd-227">Internet Crime Complaint Center</span><span class="sxs-lookup"><span data-stu-id="2c6cd-227">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="2c6cd-228">Securities and Exchange Commission – Phishing-Betrug</span><span class="sxs-lookup"><span data-stu-id="2c6cd-228">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="2c6cd-229">Um Spam direkt an Microsoft und Ihren Admin zu melden, [verwenden Sie das Report Message-Add-In](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="2c6cd-229">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
