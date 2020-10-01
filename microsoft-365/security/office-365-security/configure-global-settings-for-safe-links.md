---
title: Konfigurieren globaler Einstellungen für Einstellungen für sichere Links in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie globale Einstellungen (die Liste "folgende URLs blockieren" und Schutz für Office 365-Apps) für sichere Links in Office 365 Advanced Threat Protection (ATP) anzeigen und konfigurieren.
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328533"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="b2b05-103">Konfigurieren globaler Einstellungen für sichere Links in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b2b05-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="b2b05-104">Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="b2b05-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="b2b05-105">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="b2b05-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b2b05-106">Sichere Links sind ein Feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) , das die URL-Überprüfung eingehender e-Mail-Nachrichten im Nachrichtenfluss und die Zeit der Klick Überprüfung von URLs und Links in e-Mail-Nachrichten und an anderen Speicherorten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b2b05-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="b2b05-107">Weitere Informationen finden Sie unter [sichere Links in Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="b2b05-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="b2b05-108">Sie konfigurieren die meisten Einstellungen für sichere Links in Richtlinien für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="b2b05-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="b2b05-109">Anweisungen finden Sie unter [Einrichten von Richtlinien zu sicheren Links in Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2b05-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="b2b05-110">Aber sichere Links verwendet auch globale Einstellungen, die für alle Benutzer gelten, die in allen aktiven Richtlinien für sichere Links enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b2b05-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="b2b05-111">Dieser Bereich für globale Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b2b05-111">These global settings area:</span></span>

- <span data-ttu-id="b2b05-112">Die Liste **folgende URLs blockieren**</span><span class="sxs-lookup"><span data-stu-id="b2b05-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="b2b05-113">Weitere Informationen finden Sie in [der Liste "folgende URLs blockieren" für sichere Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="b2b05-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="b2b05-114">Schutz für sichere Links für Office 365-apps.</span><span class="sxs-lookup"><span data-stu-id="b2b05-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="b2b05-115">Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="b2b05-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="b2b05-116">Sie können die globalen Einstellungen für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Office 365 ATP-Add-on-Abonnements) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2b05-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b2b05-117">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="b2b05-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b2b05-118">Die Features, die von globalen Einstellungen für sichere Links bereitgestellt werden, werden nur auf Benutzer angewendet, die in Active Safe Links-Richtlinien enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b2b05-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="b2b05-119">Es gibt keine integrierte Richtlinie oder Standardrichtlinie für sichere Links, daher müssen Sie mindestens eine Richtlinie für sichere Links erstellen, damit diese globalen Einstellungen aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="b2b05-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="b2b05-120">Anweisungen finden Sie unter [Einrichten von Richtlinien zu sicheren Links in Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2b05-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="b2b05-121">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b2b05-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b2b05-122">Wenn Sie direkt zur Seite **ATP-sichere Links** wechseln möchten, verwenden Sie <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="b2b05-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="b2b05-123">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2b05-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b2b05-124">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2b05-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b2b05-125">Um die globalen Einstellungen für sichere Links anzuzeigen und zu konfigurieren, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="b2b05-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="b2b05-126">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b2b05-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="b2b05-127">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b2b05-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b2b05-128">Unsere empfohlenen Werte für die globalen Einstellungen für sichere Links finden Sie unter [Safe Links Settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="b2b05-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="b2b05-129">Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2b05-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b2b05-130">[Neue Features werden kontinuierlich zu ATP hinzugefügt](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="b2b05-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="b2b05-131">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren bestehenden Richtlinien für sichere Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b2b05-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="b2b05-132">Konfigurieren der Liste "folgende URLs blockieren" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b2b05-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="b2b05-133">In der Liste der **folgenden URLs blockieren** werden die Links aufgeführt, die immer durch das Scannen sicherer Hyperlinks in unterstützten apps blockiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="b2b05-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="b2b05-134">Weitere Informationen finden Sie in [der Liste "folgende URLs blockieren" für sichere Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="b2b05-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="b2b05-135">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**, und klicken Sie dann auf **globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b2b05-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b2b05-136">Wechseln Sie in der Liste **Richtlinie für sichere Links für Ihre Organisation** , die angezeigt wird, zum Feld **folgende URLs blockieren** .</span><span class="sxs-lookup"><span data-stu-id="b2b05-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="b2b05-137">Konfigurieren Sie einen oder mehrere Einträge wie unter [Eingabesyntax für die Liste "Blockieren der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2b05-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="b2b05-138">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b2b05-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="b2b05-139">Konfigurieren der Liste "Blockieren der folgenden URLs" in PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b05-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="b2b05-140">Ausführliche Informationen zur Eingabesyntax finden Sie unter [Entry-Syntax für die Liste "Blockieren der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="b2b05-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="b2b05-141">Sie können das Cmdlet **Get-AtpPolicyForO365** verwenden, um vorhandene Einträge in der _BlockURLs_ -Eigenschaft anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2b05-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="b2b05-142">Verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell, um Werte hinzuzufügen, die vorhandene Einträge ersetzen sollen:</span><span class="sxs-lookup"><span data-stu-id="b2b05-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="b2b05-143">In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="b2b05-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="b2b05-144">Blockieren Sie die Domäne, Unterdomänen und Pfade für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="b2b05-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="b2b05-145">Untersuchung der Unterdomäne blockieren, jedoch nicht die übergeordnete Domäne oder andere Unterdomänen in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="b2b05-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="b2b05-146">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinflussen:</span><span class="sxs-lookup"><span data-stu-id="b2b05-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="b2b05-147">In diesem Beispiel wird ein neuer Eintrag für adatum.com hinzugefügt, und der Eintrag für fabrikam.com wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="b2b05-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="b2b05-148">Konfigurieren von Schutz für sichere Links für Office 365 apps im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b2b05-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="b2b05-149">Sicherer Links Schutz für Office 365 apps gilt für Dokumente in unterstützten Office-Desktop-, Mobil-und Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="b2b05-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="b2b05-150">Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="b2b05-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="b2b05-151">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**, und klicken Sie dann auf **globale Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b2b05-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="b2b05-152">Konfigurieren Sie in der angezeigten **Richtlinie für sichere Links für Ihre Organisation** , die angezeigt wird, die folgenden Einstellungen im Abschnitt **Einstellungen, die für Inhalt außer e-Mail gelten** :</span><span class="sxs-lookup"><span data-stu-id="b2b05-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="b2b05-153">**Office 365 Anwendungen**: Stellen Sie sicher, dass die Umschaltfläche auf der rechten Seite ist, um sichere Links für unterstützte Office 365 apps zu aktivieren: ![ Einschalten ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="b2b05-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="b2b05-154">**Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken**: bewegen Sie die Umschaltfläche nach links, um Benutzerklicks in Bezug auf blockierte URLs in unterstützten Office 365 apps nachzuverfolgen: ![ Deaktivieren ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="b2b05-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="b2b05-155">**Benutzer können nicht über sichere Links auf die ursprüngliche URL klicken**: Vergewissern Sie sich, dass die Umschaltfläche auf der rechten Seite ist, um zu verhindern, dass Benutzer die ursprüngliche Blockierte URL in unterstützten Office 365 apps: ![ Einschalten ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="b2b05-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="b2b05-156">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b2b05-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="b2b05-157">Konfigurieren von Schutz für sichere Links für Office 365 apps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b05-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="b2b05-158">Wenn Sie lieber mithilfe von PowerShell den Schutz für sichere Links für Office 365 apps konfigurieren möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b2b05-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="b2b05-159">In diesem Beispiel werden die folgenden Einstellungen für den Schutz von sicheren Links in Office 365 apps konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="b2b05-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="b2b05-160">Sichere Links für Office 365 apps sind aktiviert (der Parameter _EnableSafeLinksForO365Clients_ wird nicht verwendet, und der Standardwert ist $true).</span><span class="sxs-lookup"><span data-stu-id="b2b05-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="b2b05-161">Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-apps werden nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="b2b05-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="b2b05-162">Benutzer dürfen nicht auf die ursprüngliche Blockierte URL in unterstützten Office 365 apps klicken (der Parameter _AllowClickThrough_ wird nicht verwendet, und der Standardwert ist $false).</span><span class="sxs-lookup"><span data-stu-id="b2b05-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="b2b05-163">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="b2b05-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b2b05-164">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="b2b05-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="b2b05-165">Führen Sie einen der folgenden Schritte aus, um sicherzustellen, dass Sie die globalen Einstellungen für sichere Links erfolgreich konfiguriert haben (die Liste **folgende URLs blockieren** und die Office 365 Einstellungen für den App-Schutz):</span><span class="sxs-lookup"><span data-stu-id="b2b05-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="b2b05-166">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links**, klicken Sie auf **globale Einstellungen**, und überprüfen Sie die Einstellungen in der angezeigten ausklapp Leiste.</span><span class="sxs-lookup"><span data-stu-id="b2b05-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="b2b05-167">Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b2b05-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="b2b05-168">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="b2b05-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
