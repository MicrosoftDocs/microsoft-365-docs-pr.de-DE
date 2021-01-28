---
title: Nachrichtenflussintelligenz
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratoren können mithilfe von Connectors (auch als Nachrichtenflussintelligenz bekannt) mehr über die Fehlercodes erfahren, die der Nachrichtenzustellung zugeordnet sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7d4277d1ce3baeabcb5b1795b5d57583fbc8245
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029256"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="5da93-103">Intelligenter Nachrichtenfluss in EOP</span><span class="sxs-lookup"><span data-stu-id="5da93-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5da93-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verwenden Sie normalerweise einen Connector, um E-Mail-Nachrichten von EOP an Ihre lokale E-Mail-Umgebung weiter zu routen.</span><span class="sxs-lookup"><span data-stu-id="5da93-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="5da93-105">Sie können auch einen Connector verwenden, um Nachrichten von Microsoft 365 an eine Partnerorganisation weiter zu routen.</span><span class="sxs-lookup"><span data-stu-id="5da93-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="5da93-106">Wenn Microsoft 365 diese Nachrichten nicht über den Connector zu senden kann, werden sie in die Warteschlange in Microsoft 365 eingereiht.</span><span class="sxs-lookup"><span data-stu-id="5da93-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="5da93-107">Microsoft 365 wird die Zustellung für jede Nachricht 24 Stunden lang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="5da93-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="5da93-108">Nach 24 Stunden läuft die Nachricht in der Warteschlange ab, und die Nachricht wird an den ursprünglichen Absender in einem Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bekannt) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5da93-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="5da93-109">Microsoft 365 generiert einen Fehler, wenn eine Nachricht nicht über einen Connector zugestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5da93-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="5da93-110">Die häufigsten Fehler und deren Lösungen werden in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5da93-110">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="5da93-111">Warteschlangen- und Benachrichtigungsfehler für nicht zustellbare Nachrichten, die über Connectors gesendet werden, werden als _Nachrichtenflussintelligenz bezeichnet._</span><span class="sxs-lookup"><span data-stu-id="5da93-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="5da93-112">Fehlercode: 450 4.4.312 DNS-Abfragefehler</span><span class="sxs-lookup"><span data-stu-id="5da93-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="5da93-113">Dieser Fehler bedeutet normalerweise, dass Microsoft 365 versucht hat, eine Verbindung mit dem smarthost herzustellen, der im Connector angegeben ist, aber die DNS-Abfrage, um die IP-Adressen des Smarthosts zu finden, ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="5da93-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="5da93-114">Mögliche Ursachen für diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="5da93-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="5da93-115">Es gibt ein Problem mit dem DNS-Hostingdienst Ihrer Domäne (Partei, die die autoritativen Namensserver für Ihre Domäne verwaltet).</span><span class="sxs-lookup"><span data-stu-id="5da93-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="5da93-116">Ihre Domäne ist vor kurzem abgelaufen. D.h. der MX-Eintrag kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5da93-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="5da93-117">Der MX-Eintrag Ihrer Domäne hat sich kürzlich geändert, und die DNS-Server verfügen weiterhin über zuvor zwischengespeicherte DNS-Informationen für Ihre Domäne.</span><span class="sxs-lookup"><span data-stu-id="5da93-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="5da93-118">Wie behebt ich fehlercode 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="5da93-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="5da93-119">Arbeiten Sie mit Ihrem DNS-Hostingdienst zusammen, um das Problem mit Ihrer Domäne zu identifizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5da93-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="5da93-120">Wenn der Fehler von Ihrer Partnerorganisation (z. B. einem Drittanbieter für Clouddienste) auftritt, wenden Sie sich an Ihren Partner, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5da93-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="5da93-121">Fehlercode: 450 4.4.315 Timeout bei der Verbindung</span><span class="sxs-lookup"><span data-stu-id="5da93-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="5da93-122">In der Regel bedeutet dies, dass Microsoft 365 keine Verbindung mit dem Ziel-E-Mail-Server herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="5da93-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="5da93-123">Die Fehlerdetails erläutern das Problem.</span><span class="sxs-lookup"><span data-stu-id="5da93-123">The error details will explain the problem.</span></span> <span data-ttu-id="5da93-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5da93-124">For example:</span></span>

- <span data-ttu-id="5da93-125">Der lokale E-Mail-Server ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5da93-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="5da93-126">Es liegt ein Fehler in den Smarthosteinstellungen des Connectors vor, sodass Microsoft 365 versucht, eine Verbindung mit der falschen IP-Adresse herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5da93-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="5da93-127">Wie kann ich fehlercode 450 4.4.315 beheben?</span><span class="sxs-lookup"><span data-stu-id="5da93-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="5da93-128">Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor.</span><span class="sxs-lookup"><span data-stu-id="5da93-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="5da93-129">Wenn beispielsweise der Nachrichtenfluss ordnungsgemäß funktioniert hat und Sie die Connectoreinstellungen nicht geändert haben, müssen Sie Ihre lokale E-Mail-Umgebung überprüfen, um zu überprüfen, ob der Server nicht verfügbar ist oder ob Änderungen an Ihrer Netzwerkinfrastruktur vorgenommen wurden (z. B. haben Sie Internetdienstanbieter geändert, sodass Sie jetzt über unterschiedliche IP-Adressen verfügen).</span><span class="sxs-lookup"><span data-stu-id="5da93-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="5da93-130">Wenn der Fehler von Ihrer Partnerorganisation (z. B. einem Drittanbieter für Clouddienste) auftritt, wenden Sie sich an Ihren Partner, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5da93-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="5da93-131">Fehlercode: 450 4.4.316 Verbindung abgelehnt</span><span class="sxs-lookup"><span data-stu-id="5da93-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="5da93-132">Dieser Fehler bedeutet in der Regel, dass microsoft 365 beim Herstellen einer Verbindung mit dem Ziel-E-Mail-Server einen Verbindungsfehler festgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="5da93-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="5da93-133">Eine wahrscheinliche Ursache für diesen Fehler ist, dass Ihre Firewall Verbindungen von Microsoft 365-IP-Adressen blockiert.</span><span class="sxs-lookup"><span data-stu-id="5da93-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="5da93-134">Dieser Fehler kann entwurfsweise sein, wenn Sie Ihr lokales E-Mail-System vollständig zu Microsoft 365 migriert und Ihre lokale E-Mail-Umgebung heruntergefahren haben.</span><span class="sxs-lookup"><span data-stu-id="5da93-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="5da93-135">Wie kann ich fehlercode 450 4.4.316 beheben?</span><span class="sxs-lookup"><span data-stu-id="5da93-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="5da93-136">Wenn Sich Postfächer in Ihrer lokalen Umgebung befinden, müssen Sie Ihre Firewalleinstellungen ändern, um Verbindungen von Microsoft 365-IP-Adressen auf dem TCP-Port 25 zu Ihren lokalen E-Mail-Servern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5da93-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="5da93-137">Eine Liste der Microsoft 365-IP-Adressen finden Sie unter [Microsoft 365-URLs und -IP-Adressbereiche.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="5da93-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="5da93-138">Wenn keine weiteren Nachrichten an Ihre lokale Umgebung zugestellt werden sollen, klicken Sie **in** der Warnung auf "Jetzt korrigieren", damit Microsoft 365 die Nachrichten mit ungültigen Empfängern sofort ablehnen kann.</span><span class="sxs-lookup"><span data-stu-id="5da93-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="5da93-139">Dadurch wird das Risiko verringert, dass das Kontingent für ungültige Empfänger Ihrer Organisation überschritten wird, wodurch die normale Nachrichtenübermittlung beeinträchtigt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="5da93-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="5da93-140">Alternativ können Sie das Problem mit den folgenden Anweisungen manuell beheben:</span><span class="sxs-lookup"><span data-stu-id="5da93-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="5da93-141">Deaktivieren oder löschen Sie in der Exchange Admin [Center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)den Connector, der E-Mails von Microsoft 365 an Ihre lokale E-Mail-Umgebung übermittelt:</span><span class="sxs-lookup"><span data-stu-id="5da93-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="5da93-142">Wechseln Sie in der EAC zu **"Nachrichtenflussconnectors".** \> </span><span class="sxs-lookup"><span data-stu-id="5da93-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="5da93-143">Wählen Sie den Connector mit dem **"Von"-Wert** **"Office 365"** und dem **"To** value **Your organization's email server"** aus, und gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="5da93-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="5da93-144">Löschen des Connectors durch Klicken **auf** das Symbol ![ "Entfernen löschen"](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="5da93-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="5da93-145">Deaktivieren Sie den Connector, indem Sie **auf** das Bearbeitungssymbol klicken ![ und es ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **deaktivieren.**</span><span class="sxs-lookup"><span data-stu-id="5da93-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="5da93-146">Ändern Sie die akzeptierte Domäne in Microsoft 365, die Ihrer lokalen E-Mail-Umgebung zugeordnet ist, von **"Internes Relay"** in **"Autoritativ".**</span><span class="sxs-lookup"><span data-stu-id="5da93-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="5da93-147">Anweisungen finden Sie unter ["Verwalten akzeptierter Domänen in Exchange Online".](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="5da93-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="5da93-148">**Hinweis:** In der Regel dauert es zwischen 30 Minuten und einer Stunde, bis diese Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="5da93-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="5da93-149">Stellen Sie nach einer Stunde sicher, dass der Fehler nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5da93-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="5da93-150">Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.</span><span class="sxs-lookup"><span data-stu-id="5da93-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="5da93-151">Fehlercode: 450 4.4.317 Fehler beim Herstellen der Verbindung mit Remote-Server</span><span class="sxs-lookup"><span data-stu-id="5da93-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="5da93-152">Dieser Fehler bedeutet normalerweise, dass Microsoft 365 mit dem Ziel-E-Mail-Server verbunden ist, der Server jedoch mit einem sofortigen Fehler geantwortet hat oder die Verbindungsanforderungen nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="5da93-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="5da93-153">Die Fehlerdetails erläutern das Problem.</span><span class="sxs-lookup"><span data-stu-id="5da93-153">The error details will explain the problem.</span></span> <span data-ttu-id="5da93-154">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5da93-154">For example:</span></span>

- <span data-ttu-id="5da93-155">Der Ziel-E-Mail-Server hat mit dem Fehler "Dienst nicht verfügbar" geantwortet, was darauf hinweist, dass der Server keine Kommunikation mit Microsoft 365 aufrecht erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="5da93-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="5da93-156">Der Connector ist so konfiguriert, dass TLS erforderlich ist, aber der Ziel-E-Mail-Server unterstützt TLS nicht.</span><span class="sxs-lookup"><span data-stu-id="5da93-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="5da93-157">Wie kann ich fehlercode 450 4.4.317 beheben?</span><span class="sxs-lookup"><span data-stu-id="5da93-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="5da93-158">Überprüfen Sie die TLS-Einstellungen und -Zertifikate auf Ihren lokalen E-Mail-Servern und die TLS-Einstellungen auf dem Connector.</span><span class="sxs-lookup"><span data-stu-id="5da93-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="5da93-159">Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.</span><span class="sxs-lookup"><span data-stu-id="5da93-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="5da93-160">Fehlercode: 450 4.4.318 Verbindung wurde plötzlich geschlossen</span><span class="sxs-lookup"><span data-stu-id="5da93-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="5da93-161">Dieser Fehler bedeutet normalerweise, dass Microsoft 365 Schwierigkeiten hat, mit Ihrer lokalen E-Mail-Umgebung zu kommunizieren, sodass die Verbindung gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="5da93-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="5da93-162">Mögliche Ursachen für diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="5da93-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="5da93-163">Ihre Firewall verwendet SMTP-Paketprüfungsregeln, und diese Regeln funktionieren nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="5da93-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="5da93-164">Ihr lokales E-Mail-Server funktioniert nicht ordnungsgemäß (z. B. Dienst hängt ab, stürzt ab oder geringe Systemressourcen), was dazu führt, dass der Server ein Zeit zeitverziert und die Verbindung mit Microsoft 365 schließt.</span><span class="sxs-lookup"><span data-stu-id="5da93-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="5da93-165">Es gibt Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5da93-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="5da93-166">Wie kann ich fehlercode 450 4.4.318 beheben?</span><span class="sxs-lookup"><span data-stu-id="5da93-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="5da93-167">Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor.</span><span class="sxs-lookup"><span data-stu-id="5da93-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="5da93-168">Wenn das Problem durch Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365 verursacht wird, wenden Sie sich zur Problembehandlung an Ihr Netzwerkteam.</span><span class="sxs-lookup"><span data-stu-id="5da93-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="5da93-169">Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.</span><span class="sxs-lookup"><span data-stu-id="5da93-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="5da93-170">Fehlercode: 450 4.7.320 Zertifikatüberprüfungsfehler</span><span class="sxs-lookup"><span data-stu-id="5da93-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="5da93-171">Dieser Fehler bedeutet normalerweise, dass microsoft 365 beim Versuch, das Zertifikat des Ziel-E-Mail-Servers zu überprüfen, einen Fehler festgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="5da93-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="5da93-172">Die Fehlerdetails erläutern den Fehler.</span><span class="sxs-lookup"><span data-stu-id="5da93-172">The error details will explain the error.</span></span> <span data-ttu-id="5da93-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5da93-173">For example:</span></span>

- <span data-ttu-id="5da93-174">Zertifikat abgelaufen</span><span class="sxs-lookup"><span data-stu-id="5da93-174">Certificate expired</span></span>

- <span data-ttu-id="5da93-175">Konflikt mit dem Zertifikatantragsteller</span><span class="sxs-lookup"><span data-stu-id="5da93-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="5da93-176">Zertifikat ist nicht mehr gültig</span><span class="sxs-lookup"><span data-stu-id="5da93-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="5da93-177">Wie behebt ich den Fehlercode 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="5da93-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="5da93-178">Korrigieren Sie das Zertifikat oder die Einstellungen auf dem Connector, sodass Nachrichten in der Warteschlange in Microsoft 365 zugestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="5da93-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="5da93-179">Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.</span><span class="sxs-lookup"><span data-stu-id="5da93-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="5da93-180">Andere Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="5da93-180">Other error codes</span></span>

<span data-ttu-id="5da93-181">Microsoft 365 hat Schwierigkeiten beim Senden von Nachrichten an Ihren lokalen E-Mail-Server oder Partner-E-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="5da93-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="5da93-182">Verwenden Sie die Informationen zum **Zielserver** im Fehler, um das Problem in Ihrer Umgebung zu untersuchen, oder ändern Sie den Konnektor bei einem Konfigurationsfehler.</span><span class="sxs-lookup"><span data-stu-id="5da93-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="5da93-183">Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.</span><span class="sxs-lookup"><span data-stu-id="5da93-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
