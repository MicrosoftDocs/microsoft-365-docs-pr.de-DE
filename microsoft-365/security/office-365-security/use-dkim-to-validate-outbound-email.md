---
title: Verwenden von DKIM für E-Mail in Ihrer benutzerdefinierten Domäne
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie DomainKeys Identified Mail (DKIM) mit Microsoft 365 verwenden können, um sicherzustellen, dass die von Ihrer benutzerdefinierten Domäne gesendeten Nachrichten von den Ziel-E-Mail-Systemen als vertrauenswürdig eingestuft werden.
ms.openlocfilehash: 66f352b6c3a5d3b3beff3043a3f0d1a435d1e5d1
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560884"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="6094d-103">Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden</span><span class="sxs-lookup"><span data-stu-id="6094d-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="6094d-104">**Zusammenfassung:** In diesem Artikel wird erläutert, wie Sie DomainKeys Identified Mail (DKIM) mit Microsoft 365 verwenden, um sicherzustellen, dass Ziel-E-Mail-Systeme ausgehenden Nachrichten vertrauen, die von Ihrer benutzerdefinierten Domäne gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="6094d-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="6094d-105">Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Spoofers Nachrichten senden, die aussehen, als würden sie von Ihrer Domäne stammen.</span><span class="sxs-lookup"><span data-stu-id="6094d-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="6094d-106">Mit DKIM können Sie ausgehenden E-Mail-Nachrichten in der Nachrichtenkopfzeile eine digitale Signatur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6094d-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="6094d-107">Das mag kompliziert klingen, ist es aber nicht.</span><span class="sxs-lookup"><span data-stu-id="6094d-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="6094d-108">Wenn Sie DKIM konfigurieren, autorisieren Sie Ihre Domäne mithilfe der kryptografischen Authentifizierung, ihren Namen mit einer E-Mail-Nachricht zu verknüpfen oder zu signieren.</span><span class="sxs-lookup"><span data-stu-id="6094d-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="6094d-109">E-Mail-Systeme, die E-Mails von Ihrer Domäne empfangen, können diese digitale Signatur verwenden, um zu ermitteln, ob eingehende E-Mails legitim sind.</span><span class="sxs-lookup"><span data-stu-id="6094d-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="6094d-110">Im Wesentlichen verwenden Sie einen privaten Schlüssel zum Verschlüsseln der Kopfzeile in ausgehenden E-Mails Ihrer Domäne.</span><span class="sxs-lookup"><span data-stu-id="6094d-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="6094d-111">Sie veröffentlichen einen öffentlichen Schlüssel für die DNS-Einträge Ihrer Domäne, die empfangende Server verwenden können, um die Signatur zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="6094d-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="6094d-112">Sie verwenden den öffentlichen Schlüssel, um sicherzustellen, dass die Nachrichten wirklich von Ihnen und nicht von einer Person kommen, die Ihre Domäne mit *Spoofing* beschädigen möchte.</span><span class="sxs-lookup"><span data-stu-id="6094d-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="6094d-113">Microsoft 365 richtet DKIM automatisch für die "onmicrosoft.com"-Anfangsdomänen ein.</span><span class="sxs-lookup"><span data-stu-id="6094d-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="6094d-114">Das bedeutet, dass Sie keine weiteren Aktionen durchführen müssen, um DKIM für jegliche Anfangsdomänennamen einzurichten (z. B. litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="6094d-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="6094d-115">Weitere Informationen zu Domänen finden Sie unter [Häufig gestellte Fragen (FAQ) zu Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="6094d-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="6094d-116">Für DKIM für Ihre benutzerdefinierte Domäne müssen Sie ebenfalls nichts weiter unternehmen.</span><span class="sxs-lookup"><span data-stu-id="6094d-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="6094d-117">Wenn Sie DKIM nicht für Ihre benutzerdefinierte Domäne einrichten, erstellt Microsoft 365 ein Paar aus privatem und öffentlichem Schlüssel, aktiviert die DKIM-Signierung und konfiguriert die Microsoft 365-Standardrichtlinie für Ihre benutzerdefinierte Domäne.</span><span class="sxs-lookup"><span data-stu-id="6094d-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="6094d-118">Obwohl dies für die meisten Kunden ausreicht, sollten Sie DKIM unter folgenden Umständen manuell für Ihre benutzerdefinierte Domäne konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="6094d-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="6094d-119">Sie haben mehr als eine benutzerdefinierte Domäne in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6094d-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="6094d-120">Sie richten auch DMARC ein (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="6094d-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="6094d-121">Sie möchten die Kontrolle über Ihren privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6094d-121">You want control over your private key</span></span>

- <span data-ttu-id="6094d-122">Sie möchten Ihre CNAME-Einträge anpassen.</span><span class="sxs-lookup"><span data-stu-id="6094d-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="6094d-123">Sie möchten DKIM-Schlüssel für E-Mails von Drittanbieterdomänen einrichten, beispielsweise bei Verwendung eines Drittanbietermassenversenders von E-Mails.</span><span class="sxs-lookup"><span data-stu-id="6094d-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="6094d-124">Inhalt dieses Artikels:</span><span class="sxs-lookup"><span data-stu-id="6094d-124">In this article:</span></span>

- [<span data-ttu-id="6094d-125">So funktioniert DKIM besser als SPF, um Spoofing zu verhindern</span><span class="sxs-lookup"><span data-stu-id="6094d-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="6094d-126">Manuelles Upgrade Ihrer 1024-Bit-Schlüssel auf 2048-Bit-DKIM-Verschlüsselungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="6094d-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="6094d-127">Schritte zum manuellen Einrichten von DKIM</span><span class="sxs-lookup"><span data-stu-id="6094d-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="6094d-128">Konfigurieren von DKIM für mehrere benutzerdefinierte Domänen</span><span class="sxs-lookup"><span data-stu-id="6094d-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="6094d-129">Deaktivieren der DKIM-Signierungsrichtlinie für eine benutzerdefinierte Domäne</span><span class="sxs-lookup"><span data-stu-id="6094d-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="6094d-130">Standardverhalten für DKIM und Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6094d-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="6094d-131">Einrichten von DKIM, damit ein Drittanbieterdienst E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden oder fälschen kann</span><span class="sxs-lookup"><span data-stu-id="6094d-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="6094d-132">Nächste Schritte: Nach dem Einrichten von DKIM für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6094d-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="6094d-133">So funktioniert DKIM besser als SPF, um Spoofing zu verhindern</span><span class="sxs-lookup"><span data-stu-id="6094d-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="6094d-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="6094d-p105">SPF fügt Informationen einem Nachrichtenumschlag hinzu, aber DKIM verschlüsselt tatsächlich eine Signatur in der Nachrichtenkopfzeile. Wenn Sie eine Nachricht weiterleiten, können Teile dieses Nachrichtenumschlags vom Weiterleitungsserver entfernt werden. Da die digitale Signatur bei der E-Mail-Nachricht bleibt, da er Teil der E-Mail-Kopfzeile ist, funktioniert DKIM selbst dann, wenn eine Nachricht weitergeleitet wurde, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6094d-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagramm, in dem eine weitergeleitete Nachricht gezeigt wird, bei der die DKIM-Authentifizierung übergangen wird, wenn die SPF-Prüfung fehlschlägt.](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="6094d-p106">Wenn Sie in diesem Beispiel nur einen SPF TXT-Eintrag für Ihre Domäne veröffentlicht hätten, könnte der E-Mail-Server des Empfängers Ihre E-Mail als Spam markiert und ein falsch positives Ergebnis generiert haben. Das Hinzufügen von DKIM in diesem Szenario reduziert die Meldung von falsch positivem Spam. Da DKIM die Verschlüsselung öffentlicher Schlüssel und nicht nur IP-Adressen zur Authentifizierung benötigt, wird DKIM als deutlich stärkere Form der Authentifizierung als SPF betrachtet. Wir empfehlen, SPF und DKIM sowie DMARC in Ihrer Bereitstellung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6094d-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="6094d-p107">Das Wesentliche: DKIM verwendet einen privaten Schlüssel, um eine verschlüsselte Signatur in die Nachrichtenkopfzeile einzufügen. Sie signierende oder ausgehende Domäne wird als Wert des Felds **d=** in die Kopfzeile eingefügt. Die überprüfende Domäne oder Empfängerdomäne verwendet dann das Feld **d=**, um den öffentlichen Schlüssel in DNS nachzuschlagen und die Nachricht zu authentifizieren. Wenn die Nachricht verifiziert wird, ist die DKIM-Überprüfung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6094d-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="6094d-147">Manuelles Upgrade Ihrer 1024-Bit-Schlüssel auf 2048-Bit-DKIM-Verschlüsselungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="6094d-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="6094d-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="6094d-149">Da sowohl 1024-Bit als auch 2048-Bit für DKIM-Schlüssel unterstützt wird, erfahren Sie in diesen Anweisungen, wie Sie Ihren 1024-Bit-Schlüssel auf 2048 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6094d-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="6094d-150">Die nachstehenden Schritte werden auf zwei Anwendungsfälle angewandt. Wählen Sie die Variante aus, die Ihren Anforderungen am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="6094d-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="6094d-151">Wenn Sie **DKIM bereits konfiguriert haben**, können Sie Bitanzahl wie folgt wechseln:</span><span class="sxs-lookup"><span data-stu-id="6094d-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="6094d-152">[Stellen Sie die Verbindung zu Office 365-Workloads über PowerShell her](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="6094d-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="6094d-153">(Das Cmdlet stammt von Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="6094d-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="6094d-154">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-154">Run the following command:</span></span>

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="6094d-155">Oder für eine **neue Implementierung von DKIM**:</span><span class="sxs-lookup"><span data-stu-id="6094d-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="6094d-156">[Stellen Sie die Verbindung zu Office 365-Workloads über PowerShell her](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="6094d-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="6094d-157">(Hierbei handelt es sich um ein Exchange Online-Cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="6094d-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="6094d-158">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="6094d-159">Behalten Sie die Verbindung mit Microsoft 365 bei, um die Konfiguration zu *überprüfen*.</span><span class="sxs-lookup"><span data-stu-id="6094d-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="6094d-160">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="6094d-161">Dieser neue 2048-Bit-Schlüssel wird zum RotateOnDate wirksam und sendet E-Mails in der Zwischenzeit mit dem 1024-Bit-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="6094d-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="6094d-162">Nach vier Tagen können Sie einen erneuten Test mit dem 2048-Bit-Schlüssel ausführen (also, wenn der Wechsel auf den zweiten Selektor angewendet wird).</span><span class="sxs-lookup"><span data-stu-id="6094d-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="6094d-163">Wenn Sie zum zweiten Selektor wechseln möchten, haben Sie folgende Möglichkeiten: a) Sie lassen den Wechseln des Selektors durch den Microsoft 365-Dienst durchführen und aktualisieren auf 2048-Bit innerhalb der nächsten 6 Monate, oder b) nach 4 Tagen, und wechseln den zweiten Selektorschlüssel manuell unter Verwendung des entsprechenden, oben aufgeführten Cmdlets, nachdem Sie zuvor sichergestellt haben, dass 2048-Bit-Schlüssel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6094d-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="6094d-164">Schritte zum manuellen Einrichten von DKIM</span><span class="sxs-lookup"><span data-stu-id="6094d-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="6094d-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="6094d-166">Um DKIM zu konfigurieren, müssen Sie diese Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6094d-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="6094d-167">Veröffentlichen von zwei CNAME-Einträgen für Ihre benutzerdefinierte Domäne in DNS</span><span class="sxs-lookup"><span data-stu-id="6094d-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="6094d-168">Aktivieren der DKIM-Signierung für Ihre benutzerdefinierte Domäne</span><span class="sxs-lookup"><span data-stu-id="6094d-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="6094d-169">Veröffentlichen von zwei CNAME-Einträgen für Ihre benutzerdefinierte Domäne in DNS</span><span class="sxs-lookup"><span data-stu-id="6094d-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="6094d-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="6094d-171">Für jede Domäne, für die Sie eine DKIM-Signatur in DNS hinzufügen möchten, müssen Sie zwei CNAME-Einträge veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6094d-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="6094d-172">Wenn Sie nicht den gesamten Artikel gelesen haben, haben Sie möglicherweise diese zeitsparenden Informationen zur PowerShell-Verbindung verpasst: [Herstellen einer Verbindung zu Office 365-Workloads über PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="6094d-172">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="6094d-173">(Das Cmdlet stammt von Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="6094d-173">(The cmdlet comes from Exchange Online.)</span></span> 

<span data-ttu-id="6094d-174">Führen Sie die folgenden Befehle aus, um die Selektor-Einträge zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6094d-174">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="6094d-175">Wenn Sie neben der ersten Domäne zusätzliche benutzerdefinierte Domänen in Microsoft 365 bereitgestellt haben, müssen Sie zwei CNAME-Einträge für jede zusätzliche Domäne veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6094d-175">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="6094d-176">Wenn Sie also zwei Domänen haben, müssen Sie zwei zusätzliche CNAME-Einträge veröffentlichen usw.</span><span class="sxs-lookup"><span data-stu-id="6094d-176">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="6094d-177">Verwenden Sie für CNAME-Einträge das folgende Format.</span><span class="sxs-lookup"><span data-stu-id="6094d-177">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6094d-178">Wenn Sie zu unseren GCC High-Kunden gehören, berechnen wir _domainGuid_ anders!</span><span class="sxs-lookup"><span data-stu-id="6094d-178">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="6094d-179">Anstatt den MX-Eintrag für Ihre _initialDomain_ zur Berechnung von _domainGuid_ zu suchen, wird diese direkt aus der angepassten Domäne heraus berechnet.</span><span class="sxs-lookup"><span data-stu-id="6094d-179">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="6094d-180">Wenn Ihre benutzerdefinierte Domäne z. B. "contoso.com" lautet, wird Ihre "domainGuid" zu "contoso-com", wobei alle Punkte durch Bindestriche ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6094d-180">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="6094d-181">Unabhängig von dem MX-Eintrag, auf den Ihre „initialDomain“ verweist, verwenden Sie also immer die oben genannte Methode, um die in den CNAME-Einträgen verwendete „domainGuid“ zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="6094d-181">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="6094d-182">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="6094d-182">Where:</span></span>

- <span data-ttu-id="6094d-183">Für Microsoft 365 sind die Selektoren immer „selector1“ oder „selector2“.</span><span class="sxs-lookup"><span data-stu-id="6094d-183">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="6094d-184">_domainGUID_ ist identisch mit _domainGUID_ im angepassten MX-Eintrag für Ihre benutzerdefinierte Domäne, der vor „mail.protection.outlook.com“ angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6094d-184">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="6094d-185">Im folgenden MX-Eintrag für die Domäne "contoso.com" ist die _domainGUID_ z. B. "contoso-com":</span><span class="sxs-lookup"><span data-stu-id="6094d-185">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="6094d-186">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6094d-186">contoso.com.</span></span>  <span data-ttu-id="6094d-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6094d-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="6094d-188">_initialDomain_ ist die Domäne, die Sie bei der Anmeldung für Microsoft 365 verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="6094d-188">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="6094d-189">Anfangsdomänen enden immer auf "onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="6094d-189">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="6094d-190">Informationen zum Ermitteln Ihrer ersten Domäne finden Sie unter [Häufig gestellte Fragen zu Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="6094d-190">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="6094d-191">Wenn Sie beispielsweise als erste Domäne „cohovineyardandwinery.onmicrosoft.com“ und zwei benutzerdefinierte Domänen „cohovineyard.com“ und „cohowinery.com“ haben, müssten Sie zwei CNAME-Einträge für jede zusätzliche Domäne einrichten, also insgesamt vier CNAME-Einträge.</span><span class="sxs-lookup"><span data-stu-id="6094d-191">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="6094d-192">Es ist wichtig, den zweiten Eintrag zu erstellen, aber zum Zeitpunkt der Erstellung wird möglicherweise nur einer der Selektoren verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="6094d-192">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="6094d-193">Im Wesentlichen verweist der zweite Selektor möglicherweise auf eine noch nicht erstellte Adresse.</span><span class="sxs-lookup"><span data-stu-id="6094d-193">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="6094d-194">Es empfiehlt sich trotzdem, den zweiten CNAME-Eintrag zu erstellen, da Ihre Schlüsselrotation dann nahtlos ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6094d-194">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>


### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="6094d-195">Aktivieren der DKIM-Signierung für Ihre benutzerdefinierte Domäne</span><span class="sxs-lookup"><span data-stu-id="6094d-195">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="6094d-196"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-196"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="6094d-197">Nachdem Sie die CNAME-Einträge im DNS veröffentlicht haben, können Sie die DKIM-Signierung über Microsoft 365 aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6094d-197">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="6094d-198">Sie können dies über das Microsoft 365 Admin Center oder mithilfe von PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="6094d-198">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="6094d-199">So aktivieren Sie die DKIM-Signierung für Ihre benutzerdefinierte Domäne über das Admin Center</span><span class="sxs-lookup"><span data-stu-id="6094d-199">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="6094d-200">[Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="6094d-200">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="6094d-201">Klicken Sie oben links auf das App-Startsymbol, und wählen Sie **Admin** aus.</span><span class="sxs-lookup"><span data-stu-id="6094d-201">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="6094d-202">Erweitern Sie im unteren linken Navigationsbereich **Admin**, und klicken Sie dann auf **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="6094d-202">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="6094d-203">Wechseln Sie zu **Schutz** \> **dkim**.</span><span class="sxs-lookup"><span data-stu-id="6094d-203">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="6094d-p120">Wählen Sie die Domäne aus, für die Sie DKIM aktivieren möchten, und wählen Sie dann für **Nachrichten für diese Domäne mit DKIM-Signaturen signieren** die Option **Aktivieren** aus. Wiederholen Sie diesen Schritt für jede benutzerdefinierte Domäne.</span><span class="sxs-lookup"><span data-stu-id="6094d-p120">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="6094d-206">So aktivieren Sie die DKIM-Signierung für Ihre benutzerdefinierte Domäne mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="6094d-206">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="6094d-207">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6094d-207">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6094d-208">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-208">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="6094d-209">Dabei ist _domain_ der Name der benutzerdefinierten Domäne, für die Sie die DKIM-Signierung aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6094d-209">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="6094d-210">Beispiel für die Domäne „contoso.com“:</span><span class="sxs-lookup"><span data-stu-id="6094d-210">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="6094d-211">So bestätigen Sie, dass die DKIM-Signierung ordnungsgemäß für Microsoft 365 konfiguriert ist</span><span class="sxs-lookup"><span data-stu-id="6094d-211">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="6094d-p121">Warten Sie einige Minuten, bevor Sie diese Schritte ausführen, um zu bestätigen, dass Sie DKIM ordnungsgemäß konfiguriert haben. Dadurch ist genug Zeit vorhanden, um die DKIM-Informationen zur Domäne im gesamten Netzwerk zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="6094d-p121">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="6094d-214">Senden Sie eine Nachricht von einem Konto in Ihrer Microsoft 365-Domäne mit aktiviertem DKIM an ein anderes E-Mail-Konto wie „outlook.com“ oder „Hotmail.com“.</span><span class="sxs-lookup"><span data-stu-id="6094d-214">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="6094d-p122">Verwenden Sie zu Testzwecken kein „aol.com“-Konto. AOL überspringt möglicherweise die DKIM-Überprüfung, wenn die SPF-Prüfung erfolgreich ist. Dadurch hat der Test keine Relevanz.</span><span class="sxs-lookup"><span data-stu-id="6094d-p122">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="6094d-p123">Öffnen Sie die Nachricht, und sehen Sie sich die Überschrift an. Anweisungen zum Anzeigen der Kopfzeile der Nachricht variieren je nach Messagingclient. Anweisungen zum Anzeigen der Kopfzeilen von Nachrichten in Outlook finden Sie unter [Anzeigen der Kopfzeilen von Internetnachrichten in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="6094d-p123">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="6094d-p124">Die mit DKIM signierte Nachricht enthält den Hostnamen und die Domäne, die Sie definiert haben, wenn Sie die CNAME-Einträge veröffentlicht haben. Die Nachricht sieht in etwa wie im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-p124">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="6094d-p125">Suchen Sie nach der „Authentication-Results“-Kopfzeile. Obwohl jeder empfangende Dienst ein geringfügig anderes Format verwendet, um die eingehenden E-Mail-Nachrichten mit Zeitstempeln zu versehen, sollte das Ergebnis immer etwas wie **DKIM=pass** oder **DKIM=OK** enthalten.</span><span class="sxs-lookup"><span data-stu-id="6094d-p125">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="6094d-225">Konfigurieren von DKIM für mehrere benutzerdefinierte Domänen</span><span class="sxs-lookup"><span data-stu-id="6094d-225">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="6094d-226"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-226"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="6094d-227">Wenn Sie zu einem bestimmten Zeitpunkt in der Zukunft eine weitere benutzerdefinierte Domäne hinzufügen und DKIM für die neue Domäne aktivieren möchten, müssen Sie die Schritte in diesem Artikel für jede Domäne ausführen.</span><span class="sxs-lookup"><span data-stu-id="6094d-227">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="6094d-228">Schließen Sie insbesondere alle Schritte in [Schritte zum manuellen Einrichten von DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365) ab.</span><span class="sxs-lookup"><span data-stu-id="6094d-228">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="6094d-229">Deaktivieren der DKIM-Signierungsrichtlinie für eine benutzerdefinierte Domäne</span><span class="sxs-lookup"><span data-stu-id="6094d-229">Disabling the DKIM signing policy for a custom domain</span></span> 
<span data-ttu-id="6094d-230"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-230"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="6094d-231">Durch das Deaktivieren der Signierungsrichtlinie wird DKIM nicht vollständig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6094d-231">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="6094d-232">Nach einer bestimmten Zeitspanne übernimmt Microsoft 365 automatisch die Standardrichtlinie für Ihre Domäne.</span><span class="sxs-lookup"><span data-stu-id="6094d-232">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="6094d-233">Weitere Informationen finden Sie unter [Standardverhalten für DKIM und Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="6094d-233">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="6094d-234">So deaktivieren Sie die DKIM-Signierungsrichtlinie mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6094d-234">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="6094d-235">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6094d-235">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6094d-236">Führen Sie einen der folgenden Befehle für jede Domäne aus, für die Sie die DKIM-Signierung deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6094d-236">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="6094d-237">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6094d-237">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="6094d-238">Oder</span><span class="sxs-lookup"><span data-stu-id="6094d-238">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="6094d-239">Wobei _number_ der Index der Richtlinie ist.</span><span class="sxs-lookup"><span data-stu-id="6094d-239">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="6094d-240">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6094d-240">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="6094d-241">Standardverhalten für DKIM und Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6094d-241">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="6094d-242"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-242"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="6094d-243">Wenn Sie DKIM nicht aktivieren, erstellt Microsoft 365 automatisch einen öffentlichen 1024-Bit-DKIM-Schlüssel für Ihre Standarddomäne und den zugehörigen privaten Schlüssel, der intern in unserem Rechenzentrum gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="6094d-243">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="6094d-244">Standardmäßig verwendet Microsoft 365 eine standardmäßige Signierkonfiguration für Domänen, die keine Richtlinie eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="6094d-244">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="6094d-245">Dies bedeutet, dass, wenn Sie DKIM nicht selbst einrichten, Microsoft 365 seine Standardrichtlinie und Standardschlüssel verwendet, die erstellt wurden, um DKIM für Ihre Domäne zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6094d-245">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="6094d-246">Wenn Sie die DKIM-Signatur nach der Aktivierung nach einer bestimmten Zeit wieder deaktivieren, wendet Microsoft 365 automatisch die Standardrichtlinie für Ihre Domäne an.</span><span class="sxs-lookup"><span data-stu-id="6094d-246">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="6094d-247">Im folgenden Beispiel wird angenommen, dass DKIM für „fabrikam.com" durch Microsoft 365 und nicht durch den Administrator der Domäne aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="6094d-247">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="6094d-248">Das bedeutet, dass die erforderlichen CNAME-Einträge nicht in DNS vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="6094d-248">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="6094d-249">DKIM-Signaturen für E-Mail-Nachrichten aus dieser Domäne sehen in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-249">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="6094d-250">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span><span class="sxs-lookup"><span data-stu-id="6094d-250">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="6094d-251">Schließlich wird jede einzelne Nachricht, die von Microsoft 365 gesendet wird, mit DKIM signiert.</span><span class="sxs-lookup"><span data-stu-id="6094d-251">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="6094d-252">Wenn Sie DKIM selbst aktivieren, ist die Domäne identisch mit der Domäne in der „From:“-Adresse, in diesem Fall „fabrikam.com“.</span><span class="sxs-lookup"><span data-stu-id="6094d-252">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="6094d-253">If you don't, it will not align and instead will use your organization's initial domain.</span><span class="sxs-lookup"><span data-stu-id="6094d-253">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="6094d-254">Informationen zum Ermitteln Ihrer ersten Domäne finden Sie unter [Häufig gestellte Fragen zu Domänen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="6094d-254">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="6094d-255">Einrichten von DKIM, damit ein Drittanbieterdienst E-Mails im Auftrag Ihrer benutzerdefinierten Domäne senden oder fälschen kann</span><span class="sxs-lookup"><span data-stu-id="6094d-255">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="6094d-256"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-256"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="6094d-257">Bei einigen Anbietern von Massen-E-Mail-Diensten oder Software-as-a-Service-Anbietern können Sie DKIM-Schlüssel für E-Mails einrichten, die aus dem jeweiligen Dienst stammen.</span><span class="sxs-lookup"><span data-stu-id="6094d-257">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="6094d-258">Dies erfordert eine Koordination zwischen Ihnen und dem Drittanbieter, damit die erforderlichen DNS-Einträge eingerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="6094d-258">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="6094d-259">Einige Server von Drittanbietern können eigene CNAME-Einträge mit unterschiedlichen Selektoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="6094d-259">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="6094d-260">Keine zwei Organisationen führen dies auf die gleiche Weise durch.</span><span class="sxs-lookup"><span data-stu-id="6094d-260">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="6094d-261">Der Prozess hängt vollständig von der Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="6094d-261">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="6094d-262">Eine Beispielnachricht mit einer ordnungsgemäßen DKIM-Konfiguration für „contoso.com“ und „bulkemailprovider.com“ kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="6094d-262">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="6094d-263">In diesem Beispiel sind zu diesem Zweck die folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6094d-263">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="6094d-264">Der Massen-E-Mail-Anbieter hat einen öffentlichen DKIM-Schlüssel für Contoso bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6094d-264">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="6094d-265">Contoso hat den DKIM-Schlüssel für den DNS-Eintrag veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="6094d-265">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="6094d-p133">Beim Senden der E-Mail signiert der Massen-E-Mail-Anbieter den Schlüssel mit dem entsprechenden privaten Schlüssel. So hat der Massen-E-Mail-Anbieter die DKIM-Signatur an die Kopfzeile der Nachricht angefügt.</span><span class="sxs-lookup"><span data-stu-id="6094d-p133">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="6094d-268">Beim Empfangen von E-Mails führen Systeme eine DKIM-Überprüfung durch, indem der d=\<domain\>-Wert der DKIM-Signatur mit der Domäne im Feld „Von: (5322.From)" der Nachricht verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="6094d-268">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="6094d-269">In diesem Beispiel entsprechen die Werte den folgenden:</span><span class="sxs-lookup"><span data-stu-id="6094d-269">In this example, the values match:</span></span>

   > <span data-ttu-id="6094d-270">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="6094d-270">sender@**contoso.com**</span></span>

   > <span data-ttu-id="6094d-271">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="6094d-271">d=**contoso.com**</span></span>
   
## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="6094d-272">Domänen identifizieren, die keine E-Mails senden</span><span class="sxs-lookup"><span data-stu-id="6094d-272">Identify domains that do not send email</span></span>

<span data-ttu-id="6094d-273">Organisationen sollten explizit angeben, ob eine Domäne keine E-Mails sendet, indem sie `v=DKIM1; p=` im DKIM-Eintrag für diese Domänen angeben.</span><span class="sxs-lookup"><span data-stu-id="6094d-273">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="6094d-274">Dies weist empfangende E-Mail-Server darauf hin, dass es keine gültigen öffentlichen Schlüssel für die Domäne gibt. Jede E-Mail, die vorgibt, von dieser Domäne zu stammen, sollte abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="6094d-274">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="6094d-275">Sie sollten dies für jede Domäne und Subdomäne mit einem Wildcard-DKIM tun.</span><span class="sxs-lookup"><span data-stu-id="6094d-275">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="6094d-276">Der DKIM-Eintrag sieht beispielsweise wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6094d-276">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="6094d-277">Nächste Schritte: Nach dem Einrichten von DKIM für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6094d-277">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="6094d-278"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="6094d-278"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="6094d-279">Obwohl DKIM Spoofing verhindern soll, funktioniert DKIM besser mit SPF und DMARC.</span><span class="sxs-lookup"><span data-stu-id="6094d-279">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="6094d-280">Sobald Sie DKIM eingerichtet haben, sollten Sie auch SPF einrichten, falls noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="6094d-280">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="6094d-281">Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="6094d-281">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="6094d-282">Ausführlichere Informationen zur Verwendung von SPF durch Microsoft 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="6094d-282">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="6094d-283">Lesen Sie danach [Verwenden von DMARC zur Überprüfung von E-Mails](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="6094d-283">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="6094d-284">[Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) umfassen die Syntax- und Kopfzeilenfelder, die von Microsoft 365 für DKIM-Überprüfungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6094d-284">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="6094d-285">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6094d-285">More information</span></span>

<span data-ttu-id="6094d-286">Schlüsselrotation über PowerShell [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)</span><span class="sxs-lookup"><span data-stu-id="6094d-286">Key rotation via PowerShell [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
