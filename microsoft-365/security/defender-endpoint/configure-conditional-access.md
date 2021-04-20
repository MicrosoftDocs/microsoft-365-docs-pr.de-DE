---
title: Konfigurieren des bedingten Zugriffs in Microsoft Defender for Endpoint
description: Erfahren Sie mehr über die Schritte, die Sie in Intune, Microsoft Defender Security Center und Azure ausführen müssen, um bedingten Zugriff zu implementieren.
keywords: bedingter Zugriff, bedingter Zugriff, Geräterisiko, Risikostufe, Integration, Intune-Integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 482f86d4a0a181b72a0a33eeb1a857dce0664584
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893649"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d51ea-104">Konfigurieren des bedingten Zugriffs in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d51ea-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d51ea-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d51ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="d51ea-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d51ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d51ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d51ea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d51ea-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d51ea-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d51ea-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d51ea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d51ea-110">Dieser Abschnitt führt Sie durch alle Schritte, die Sie zum ordnungsgemäßen Implementieren des bedingten Zugriffs ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="d51ea-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="d51ea-111">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="d51ea-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="d51ea-112">Beachten Sie, dass in diesem Szenario registrierte Azure AD-Geräte nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d51ea-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="d51ea-113">Nur in Intune registrierte Geräte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d51ea-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="d51ea-114">Sie müssen sicherstellen, dass alle Ihre Geräte in Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="d51ea-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="d51ea-115">Sie können eine der folgenden Optionen verwenden, um Geräte in Intune zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="d51ea-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="d51ea-116">IT-Administrator: Weitere Informationen zum Aktivieren der automatischen Registrierung finden Sie unter [Windows-Registrierung.](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="d51ea-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="d51ea-117">Endbenutzer: Weitere Informationen zum Registrieren Ihres Windows 10-Geräts in Intune finden Sie unter [Registrieren Ihres Windows 10-Geräts in Intune.](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="d51ea-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="d51ea-118">Alternative für Endbenutzer: Weitere Informationen zum Beitritt zu einer Azure AD-Domäne finden Sie unter [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span><span class="sxs-lookup"><span data-stu-id="d51ea-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="d51ea-119">Es gibt Schritte, die Sie im Microsoft Defender Security Center, im Intune-Portal und im Azure AD-Portal ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="d51ea-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="d51ea-120">Es ist wichtig, die erforderlichen Rollen für den Zugriff auf diese Portale zu notieren und bedingten Zugriff zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="d51ea-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="d51ea-121">**Microsoft Defender Security Center** – Sie müssen sich beim Portal mit einer globalen Administratorrolle anmelden, um die Integration zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d51ea-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="d51ea-122">**Intune** : Sie müssen sich beim Portal mit Sicherheitsadministratorrechten mit Verwaltungsberechtigungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="d51ea-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="d51ea-123">**Azure AD-Portal** : Sie müssen sich als globaler Administrator, Sicherheitsadministrator oder Bedingter Zugriffsadministrator anmelden.</span><span class="sxs-lookup"><span data-stu-id="d51ea-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="d51ea-124">Sie benötigen eine Microsoft Intune-Umgebung, in der Intune verwaltet wird und Azure AD Windows 10-Geräten beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d51ea-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="d51ea-125">Gehen Sie wie folgt vor, um bedingten Zugriff zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d51ea-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="d51ea-126">Schritt 1: Aktivieren der Microsoft Intune-Verbindung von Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="d51ea-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="d51ea-127">Schritt 2: Aktivieren der Defender for Endpoint-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="d51ea-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="d51ea-128">Schritt 3: Erstellen der Compliancerichtlinie in Intune</span><span class="sxs-lookup"><span data-stu-id="d51ea-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="d51ea-129">Schritt 4: Zuweisen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d51ea-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="d51ea-130">Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="d51ea-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="d51ea-131">Schritt 1: Aktivieren der Microsoft Intune-Verbindung</span><span class="sxs-lookup"><span data-stu-id="d51ea-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="d51ea-132">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Erweiterte Features Microsoft**  >  **Intune-Verbindung aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="d51ea-133">Umschalten der Microsoft Intune-Einstellung auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="d51ea-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="d51ea-134">Klicken **Sie auf Einstellungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="d51ea-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="d51ea-135">Schritt 2: Aktivieren der Defender for Endpoint-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="d51ea-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="d51ea-136">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="d51ea-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d51ea-137">Wählen **Sie Gerätekonformität**  >  **Microsoft Defender ATP aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="d51ea-138">Legen **Sie Connect Windows 10.0.15063+** auf Microsoft Defender Advanced Threat Protection auf Ein **fest.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="d51ea-139">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d51ea-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="d51ea-140">Schritt 3: Erstellen der Compliancerichtlinie in Intune</span><span class="sxs-lookup"><span data-stu-id="d51ea-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="d51ea-141">Wählen Sie [im Azure-Portal](https://portal.azure.com) **Alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="d51ea-142">Wählen **Sie Gerätekonformitätsrichtlinien**  >    >  **Erstellen einer Richtlinie aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="d51ea-143">Geben Sie einen **Namen und** eine **Beschreibung ein.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="d51ea-144">Wählen **Sie unter Plattform** Windows **10 und höher aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="d51ea-145">Legen Sie in den  Einstellungen für **den** Geräteinte health die Einstellung Gerätebedrohungsstufe auf ihre bevorzugte Stufe festlegen:</span><span class="sxs-lookup"><span data-stu-id="d51ea-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="d51ea-146">**Gesichert:** Diese Stufe ist die sicherste.</span><span class="sxs-lookup"><span data-stu-id="d51ea-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="d51ea-147">Das Gerät kann keine vorhandenen Bedrohungen haben und weiterhin auf Unternehmensressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d51ea-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="d51ea-148">Wenn Bedrohungen gefunden werden, wird das Gerät als nicht konform ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="d51ea-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="d51ea-149">**Niedrig:** Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Ebene vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d51ea-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="d51ea-150">Geräte mit mittleren oder hohen Bedrohungsstufen sind nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="d51ea-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="d51ea-151">**Medium**: Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedrig oder mittel sind.</span><span class="sxs-lookup"><span data-stu-id="d51ea-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="d51ea-152">Wenn Bedrohungen auf hoher Ebene erkannt werden, wird das Gerät als nicht konform festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d51ea-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="d51ea-153">**High**: Diese Stufe ist die am wenigsten sichere Stufe und ermöglicht alle Bedrohungsstufen.</span><span class="sxs-lookup"><span data-stu-id="d51ea-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="d51ea-154">Geräte mit hohen, mittleren oder niedrigen Bedrohungsstufen werden daher als kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="d51ea-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="d51ea-155">Wählen **Sie OK** und **Erstellen** aus, um Ihre Änderungen zu speichern (und die Richtlinie zu erstellen).</span><span class="sxs-lookup"><span data-stu-id="d51ea-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="d51ea-156">Schritt 4: Zuweisen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d51ea-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="d51ea-157">Wählen Sie [im Azure-Portal](https://portal.azure.com) **Alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="d51ea-158">Wählen **Sie Gerätekonformitätsrichtlinien**  >  > Sie Ihre Microsoft Defender ATP-Konformitätsrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="d51ea-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="d51ea-159">Wählen Sie **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="d51ea-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="d51ea-160">Schließen Sie Ihre Azure AD-Gruppen ein, oder schließen Sie sie aus, um ihnen die Richtlinie zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d51ea-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="d51ea-161">Wählen Sie Speichern aus, um die Richtlinie für die Gruppen **zu bereitstellen.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="d51ea-162">Die benutzerorientierten Geräte, auf die die Richtlinie ausgerichtet ist, werden auf Compliance geprüft.</span><span class="sxs-lookup"><span data-stu-id="d51ea-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="d51ea-163">Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="d51ea-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="d51ea-164">Öffnen Sie [im Azure-Portal](https://portal.azure.com) **Azure Active Directory** Conditional  >  **Access**  >  **Neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d51ea-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="d51ea-165">Geben Sie einen **Richtliniennamen ein,** und wählen **Sie Benutzer und Gruppen aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="d51ea-166">Verwenden Sie die Optionen Include oder Exclude, um Ihre Gruppen für die Richtlinie hinzuzufügen, und wählen Sie **Fertig aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="d51ea-167">Wählen **Sie Cloud-Apps** aus, und wählen Sie aus, welche Apps geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d51ea-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="d51ea-168">Wählen Sie beispielsweise **Apps auswählen** aus, und wählen Sie **Office 365 SharePoint Online** und Office **365 Exchange Online aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="d51ea-169">Wählen Sie **Fertig** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d51ea-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="d51ea-170">Wählen **Sie Bedingungen**  >  **Client-Apps aus,** um die Richtlinie auf Apps und Browser anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d51ea-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="d51ea-171">Wählen Sie beispielsweise **Ja** aus, und aktivieren Sie **dann Browser-** und **Mobile-Apps und Desktopclients.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="d51ea-172">Wählen Sie **Fertig** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d51ea-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="d51ea-173">Wählen **Sie Gewähren** aus, um bedingten Zugriff basierend auf der Gerätekonformität anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d51ea-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="d51ea-174">Wählen Sie z. **B. Zugriff gewähren**  >  **Gerät als kompatibel markieren aus.**</span><span class="sxs-lookup"><span data-stu-id="d51ea-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="d51ea-175">Wählen **Sie Auswählen** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d51ea-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="d51ea-176">Wählen **Sie Richtlinie aktivieren** und dann **Erstellen** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d51ea-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="d51ea-177">Weitere Informationen finden Sie unter [Aktivieren von Microsoft Defender ATP mit bedingten Zugriff in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="d51ea-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="d51ea-178">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d51ea-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d51ea-179">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d51ea-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
