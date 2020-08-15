---
title: Herstellen einer Verbindung mit Exchange Online Mandanten mit Remote Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Zusammenfassung: Verwenden Sie eine Remotesitzung von Windows PowerShell, um eine Verbindung mit Exchange Online anhand des DelegatedOrg-Werts herzustellen.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690639"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="88ed9-103">Verbinden mit Exchange Online-Mandanten über eine Remotesitzung von Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permissions, DAP)</span><span class="sxs-lookup"><span data-stu-id="88ed9-103">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="88ed9-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="88ed9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88ed9-p101">Die Verfahren in diesem Thema gelten nur für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP). Wenn Sie kein DAP-Partner sind, verwenden Sie nicht die Verfahren in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="88ed9-p101">The procedures in this topic are only for Delegated Access Permission (DAP) partners. If you aren't a DAP partner, don't use the procedures in this topic.</span></span> 
  
<span data-ttu-id="88ed9-107">DAP-Partner sind Syndication- und Cloudlösungsanbieter-Partner (CSP-Partner).</span><span class="sxs-lookup"><span data-stu-id="88ed9-107">DAP partners are Syndication and Cloud Solution Providers (CSP) partners.</span></span> <span data-ttu-id="88ed9-108">Häufig handelt es sich um Netzwerk- oder Telekom-Anbieter für andere Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="88ed9-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="88ed9-109">Sie bündeln Abonnements in ihren Serviceangeboten für ihre Kunden.</span><span class="sxs-lookup"><span data-stu-id="88ed9-109">They bundle subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="88ed9-110">Sie besitzen eine Partner Mandantschaft, die automatisch verwaltet im Namen von (AOBO) Berechtigungen für Ihre Microsoft 365-Kundenmandanten erteilt wird, damit Sie alle Ihre Kundenmandanten verwalten und melden können.</span><span class="sxs-lookup"><span data-stu-id="88ed9-110">They own a partner tenancy that is automatically granted Administer On Behalf Of (AOBO) permissions to their Microsoft 365 customer tenancies so they can administer and report on all of their customer tenancies.</span></span>

<span data-ttu-id="88ed9-111">DAP-Partner können Exchange Online PowerShell verwenden, um Kunden Exchange Online Einstellungen zu verwalten und Microsoft 365-Berichte über die Befehlszeile zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="88ed9-111">DAP partners can use Exchange Online PowerShell to manage customer Exchange Online settings and get Microsoft 365 reports from the command line.</span></span> <span data-ttu-id="88ed9-112">Sie verwenden Windows PowerShell auf dem lokalen Computer, um eine PowerShell-Remotesitzung mit Exchange Online zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88ed9-112">You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online.</span></span> <span data-ttu-id="88ed9-113">Es handelt sich um einen einfachen dreistufigen Prozess, in dem Sie Ihre Anmeldeinformationen eingeben, die erforderlichen Verbindungseinstellungen bereitstellen und dann die Exchange Online-Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren, damit Sie Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="88ed9-113">It's a simple three-step process where you enter your credentials, provide the required connection settings, and then import the Exchange Online cmdlets into your local Windows PowerShell session so that you can use them.</span></span>

> [!NOTE]
> <span data-ttu-id="88ed9-p104">DAP-Partner können nicht die Verfahren in [Verbinden mit Exchange Online PowerShell per mehrstufiger Authentifizierung](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) verwenden, um eine Verbindung zu ihren Kundenmandantenorganisationen in Exchange Online PowerShell herzustellen. Die mehrstufige Authentifizierung und das Remote-PowerShell-Modul von Exchange Online funktionieren nicht mit der delegierten Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="88ed9-p104">DAP partners can't use the procedures in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) to connect to their customer tenant organizations in Exchange Online PowerShell. MFA and the Exchange Online Remote PowerShell Module don't work with delegated authentication.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="88ed9-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="88ed9-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="88ed9-117">Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten</span><span class="sxs-lookup"><span data-stu-id="88ed9-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="88ed9-118">Sie können folgende Versionen von Windows verwenden:</span><span class="sxs-lookup"><span data-stu-id="88ed9-118">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="88ed9-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="88ed9-119">Windows 10</span></span>

  - <span data-ttu-id="88ed9-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="88ed9-120">Windows 8.1</span></span>

  - <span data-ttu-id="88ed9-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="88ed9-121">Windows Server 2016</span></span>

  - <span data-ttu-id="88ed9-122">Windows Server 2012 oder Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="88ed9-122">Windows Server 2012 or Windows Server 2012 R2</span></span>

  - <span data-ttu-id="88ed9-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88ed9-123">Windows 7 Service Pack 1 (SP1)<sup>\*</sup></span></span>

  - <span data-ttu-id="88ed9-124">Windows Server 2008 R2 SP1<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="88ed9-124">Windows Server 2008 R2 SP1<sup>\*</sup></span></span>

    <span data-ttu-id="88ed9-p105"><sup>\*</sup> Für ältere Versionen von Windows müssen Sie Microsoft.NET Framework 4.5 oder höher installieren und dann eine aktualisierte Version von Windows Management Framework installieren: 3.0, 4.0 oder 5.1 (nur eine). Weitere Informationen finden Sie unter [ Installation von .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) und [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span><span class="sxs-lookup"><span data-stu-id="88ed9-p105"><sup>\*</sup> For older versions of Windows, you need to install the Microsoft.NET Framework 4.5 or later and then an updated version of the Windows Management Framework: 3.0, 4.0, or 5.1 (only one). For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344), and [Windows Management Framework 5.1](https://aka.ms/wmf5download).</span></span>

- <span data-ttu-id="88ed9-p106">Windows PowerShell muss zum Ausführen von Skripts konfiguriert werden. Standardmäßig ist dies nicht der Fall. Beim Versucht, eine Verbindung herzustellen, wird der folgende Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="88ed9-p106">Windows PowerShell needs to be configured to run scripts, and by default, it isn't. You'll get the following error when you try to connect:</span></span>

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  <span data-ttu-id="88ed9-129">Um anzufordern, dass alle PowerShell-Skripts, die Sie aus dem Internet herunterladen, von einem vertrauenswürdigen Herausgeber signiert werden, müssen Sie den folgenden Befehl in einem Windows PowerShell-Fenster mit erhöhten Rechten ausführen (ein Windows PowerShell-Fenster, das Sie durch Auswahl von **Als Administrator ausführen**) geöffnet haben:</span><span class="sxs-lookup"><span data-stu-id="88ed9-129">To require all PowerShell scripts that you download from the internet are signed by a trusted publisher, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  <span data-ttu-id="88ed9-130">Sie müssen diese Einstellung nur einmalig auf Ihrem Computer konfigurieren, und nicht bei jedem Verbindungsaufbau.</span><span class="sxs-lookup"><span data-stu-id="88ed9-130">You need to configure this setting only once on your computer, not every time you connect.</span></span>

- <span data-ttu-id="88ed9-131">Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen in der Exchange-Verwaltungskonsole](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span><span class="sxs-lookup"><span data-stu-id="88ed9-131">For information about keyboard shortcuts that might apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkId=534017).</span></span>

## <a name="connect-to-exchange-online-for-customer-organizations"></a><span data-ttu-id="88ed9-132">Herstellen einer Verbindung mit Exchange Online für Kundenorganisationen</span><span class="sxs-lookup"><span data-stu-id="88ed9-132">Connect to Exchange Online for customer organizations</span></span>

1. <span data-ttu-id="88ed9-133">Öffnen Sie auf Ihrem lokalen Computer Windows PowerShell, und führen Sie dann den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="88ed9-133">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="88ed9-134">Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** Ihren DAP-Administratorbenutzernamen und das Kennwort ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="88ed9-134">In the **Windows PowerShell Credential Request** dialog box, enter your DAP administrator user name and password, and then click **OK**.</span></span>
    
2. <span data-ttu-id="88ed9-135">Ersetzen _\<customer tenant domain name\>_ Sie durch den Namen der Mandantendomäne, mit der Sie eine Verbindung herstellen möchten, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88ed9-135">Replace _\<customer tenant domain name\>_ with the name of the tenant domain that you want to connect to, and run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    <span data-ttu-id="88ed9-136">Der wichtigste Schritt für diesen Befehl ist anzugeben, auf welchen Kunden für die Berichtsinformationen zugegriffen werden soll.</span><span class="sxs-lookup"><span data-stu-id="88ed9-136">The key step in this command is specifying which customer to access for the reporting information.</span></span> <span data-ttu-id="88ed9-137">Hierzu geben Sie den  _ConnectionURI_ -Parameter an, in dem Sie den FQDN des ersten Domänennamens als Wert für angeben `?DelegatedOrg=` .</span><span class="sxs-lookup"><span data-stu-id="88ed9-137">You do this in the  _ConnectionURI_ parameter, where you provide the FQDN of the initial domain name as the value for `?DelegatedOrg=`.</span></span> <span data-ttu-id="88ed9-138">Dieser Wert gibt den richtigen Exchange Online PowerShell-Endpunkt an, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="88ed9-138">This value indicates the correct Exchange Online PowerShell endpoint to connect to.</span></span> <span data-ttu-id="88ed9-139">Remote-PowerShell muss bei jedem Ausführen eines Berichts eine Verbindung mit Microsoft 365-Berichterstellung im Kontext eines bestimmten Kunden herstellen.</span><span class="sxs-lookup"><span data-stu-id="88ed9-139">Remote PowerShell must connect to Microsoft 365 reporting in the context of a specific customer each time a report is run.</span></span> <span data-ttu-id="88ed9-140">Nachdem Sie eine Verbindung mit Exchange Online PowerShell hergestellt haben, werden alle nachfolgenden Befehle im Kontext des Kunden ausgeführt, wodurch Sie Zugriff auf alle verfügbaren Berichte für den Kunden haben.</span><span class="sxs-lookup"><span data-stu-id="88ed9-140">After you connect to Exchange Online PowerShell, all subsequent commands are run in the context of the customer, which gives you access to all of the available reports for the customer.</span></span>
    
3. <span data-ttu-id="88ed9-141">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="88ed9-141">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> <span data-ttu-id="88ed9-p108">Es können höchstens drei Sitzungen gleichzeitig unter einem Konto ausgeführt werden. Stellen Sie sicher, dass die Remote-PowerShell-Sitzung getrennt wird, wenn Sie alle Aufgaben ausgeführt haben. Wenn Sie das Windows PowerShell-Fenster schließen, ohne die Sitzung zu trennen, verbrauchen Sie möglicherweise alle Remote-PowerShell-Sitzungen, die Ihnen zur Verfügung stehen, sodass Sie dann warten müssen, bis die Sitzungen abgelaufen sind. Führen Sie zum Trennen der PowerShell-Remotesitzung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88ed9-p108">There's a limit of three simultaneous sessions that can run under one account. Be sure to disconnect the remote PowerShell session when you're finished. If you close the Windows PowerShell window without disconnecting the session, you can use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire. To disconnect the remote PowerShell session, run the following command:</span></span>

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="88ed9-146">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="88ed9-146">How do you know this worked?</span></span>

<span data-ttu-id="88ed9-p109">Nach Schritt 3 werden die Exchange Online-Cmdlets in Ihre lokale Windows PowerShell-Sitzung importiert. Der Fortschritt des Importvorgangs wird in einer Statusanzeige dargestellt. Wenn Sie keine Fehlermeldungen erhalten, wurde die Verbindung erfolgreich hergestellt. Ein schneller Test ist die Ausführung eines Exchange Online-Cmdlets, z. B. von **Get-Mailbox**, und die Betrachtung der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="88ed9-p109">After Step 3, the Exchange Online cmdlets are imported into your local Windows PowerShell session as tracked by a progress bar. If you don't receive any errors, you connected successfully. A quick test is to run an Exchange Online cmdlet (for example, **Get-Mailbox**) and see the results.</span></span>
  
<span data-ttu-id="88ed9-150">Wenn Sie Fehlermeldungen erhalten, überprüfen Sie die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="88ed9-150">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="88ed9-p110">Ein häufig auftretendes Problem ist ein falsches Kennwort. Führen Sie die drei Schritte erneut durch und achten Sie besonders auf die korrekte Eingabe des Benutzernamens und Kennworts in Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="88ed9-p110">A common problem is an incorrect password. Run the three steps again and pay close attention to the user name and password you enter in Step 1.</span></span>
    
- <span data-ttu-id="88ed9-p111">Das Benutzerkonto, mit dem Sie die Verbindung mit Exchange Online herstellen, muss für Remote-PowerShell aktiviert sein. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span><span class="sxs-lookup"><span data-stu-id="88ed9-p111">The account you use to connect to Exchange Online must be enabled for remote PowerShell. For more information, see [Enable or disable access to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534018).</span></span>
    
- <span data-ttu-id="88ed9-p112">TCP-Port 80 muss zwischen dem lokalen Computer und dem Remoteserver geöffnet sein. Er ist wahrscheinlich offen, es kann jedoch vorkommen, dass Ihre Organisation eine eingeschränkte Internetzugriffsrichtlinie verfolgt.</span><span class="sxs-lookup"><span data-stu-id="88ed9-p112">TCP port 80 traffic needs to be open between your local computer and Exchange Online. It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.</span></span>
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a><span data-ttu-id="88ed9-157">Direktes Aufrufen des Cmdlets mit Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="88ed9-157">Call the cmdlet directly with Invoke-Command</span></span>

<span data-ttu-id="88ed9-p113">Das Importieren einer PowerShell-Remotesitzung (Schritt 3) kann ein langwieriger Vorgang sein, da _alle_ Exchange Online-Cmdlets mit einbezogen werden. Dies kann bei der Stapelverarbeitung ein Problem sein, wenn Sie z. B. Berichte ausführen oder Massenänderungen für verschiedene Mandanten durchführen. Als Alternative zur Verwendung von **Import-PSSession** können Sie Cmdlets, die Sie verwenden möchten, direkt mit **Invoke-Command** aufrufen. Um zum Beispiel das **Get-Milbox**-Cmdlet aufzurufen, ersetzen Sie diese Syntax für den `Import-PSSession $Session`-Befehl in Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="88ed9-p113">Importing a remote PowerShell session (Step 3) can be a lengthy process because it brings in _all_ Exchange Online cmdlets. This can be an issue in batch processing (for example, when you're running reports or making bulk changes for different tenants). As an alternative to using **Import-PSSession**, you can call cmdlets you want to use directly with **Invoke-Command**. For example, to call the **Get-Milbox** cmdlet, substitute this syntax for the `Import-PSSession $Session` command in Step 3:</span></span>
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a><span data-ttu-id="88ed9-162">Weitere Berichterstellungs-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="88ed9-162">More reporting cmdlets</span></span>

<span data-ttu-id="88ed9-p114">Die Cmdlets, die Sie in diesem Thema verwenden, sind Windows PowerShell-Cmdlets. Weitere Informationen zu diesen Cmdlets finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="88ed9-p114">The cmdlets that you used in this topic are Windows PowerShell cmdlets. For more information about these cmdlets, see the following topics:</span></span>
  
- [<span data-ttu-id="88ed9-165">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="88ed9-165">Get-Credential</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [<span data-ttu-id="88ed9-166">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="88ed9-166">New-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [<span data-ttu-id="88ed9-167">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="88ed9-167">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [<span data-ttu-id="88ed9-168">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="88ed9-168">Remove-PSSession</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [<span data-ttu-id="88ed9-169">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="88ed9-169">Set-ExecutionPolicy</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

