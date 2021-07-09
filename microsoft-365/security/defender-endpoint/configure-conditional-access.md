---
title: Konfigurieren des bedingten Zugriffs in Microsoft Defender für Endpunkt
description: Erfahren Sie mehr über die Schritte, die Sie in Intune, Microsoft 365 Defender und Azure ausführen müssen, um bedingten Zugriff zu implementieren.
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
ms.openlocfilehash: 2c9462fa0d4be4d6ff78ba3e5db2cd4fa71fef0b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339514"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="882ae-104">Konfigurieren des bedingten Zugriffs in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="882ae-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="882ae-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="882ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="882ae-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="882ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="882ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="882ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="882ae-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="882ae-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="882ae-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="882ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="882ae-110">Dieser Abschnitt führt Sie durch alle Schritte, die Sie ausführen müssen, um den bedingten Zugriff ordnungsgemäß zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="882ae-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="882ae-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="882ae-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="882ae-112">Es ist wichtig zu beachten, dass registrierte Azure AD-Geräte in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="882ae-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="882ae-113">Nur in Intune registrierte Geräte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="882ae-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="882ae-114">Sie müssen sicherstellen, dass alle Ihre Geräte in Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="882ae-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="882ae-115">Sie können eine der folgenden Optionen verwenden, um Geräte in Intune zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="882ae-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="882ae-116">IT-Administrator: Weitere Informationen zum Aktivieren der automatischen Registrierung finden Sie unter [Windows-Registrierung.](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="882ae-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="882ae-117">Endbenutzer: Weitere Informationen zum Registrieren Ihres Windows 10 Geräts in Intune finden Sie unter [Registrieren Ihres Windows 10 Geräts in Intune.](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="882ae-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="882ae-118">Alternative Endbenutzer: Weitere Informationen zum Beitreten zu einer Azure AD-Domäne finden Sie unter [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span><span class="sxs-lookup"><span data-stu-id="882ae-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="882ae-119">Es gibt Schritte, die Sie in Microsoft 365 Defender, im Intune-Portal und im Azure AD-Portal ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="882ae-119">There are steps you'll need to take in Microsoft 365 Defender, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="882ae-120">Es ist wichtig, die erforderlichen Rollen zu beachten, um auf diese Portale zuzugreifen und den bedingten Zugriff zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="882ae-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="882ae-121">**Microsoft 365 Defender** : Sie müssen sich mit einer globalen Administratorrolle beim Portal anmelden, um die Integration zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="882ae-121">**Microsoft 365 Defender** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="882ae-122">**Intune** : Sie müssen sich beim Portal mit Sicherheitsadministratorrechten mit Verwaltungsberechtigungen anmelden.</span><span class="sxs-lookup"><span data-stu-id="882ae-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="882ae-123">**Azure AD-Portal** – Sie müssen sich als globaler Administrator, Sicherheitsadministrator oder Administrator für bedingten Zugriff anmelden.</span><span class="sxs-lookup"><span data-stu-id="882ae-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="882ae-124">Sie benötigen eine Microsoft Intune-Umgebung mit intune-verwalteten und Azure AD-Windows 10 Geräten.</span><span class="sxs-lookup"><span data-stu-id="882ae-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="882ae-125">Führen Sie die folgenden Schritte aus, um den bedingten Zugriff zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="882ae-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="882ae-126">Schritt 1: Aktivieren der Microsoft Intune Verbindung von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="882ae-126">Step 1: Turn on the Microsoft Intune connection from Microsoft 365 Defender</span></span>
- <span data-ttu-id="882ae-127">Schritt 2: Aktivieren der Defender für Endpunkt-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="882ae-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="882ae-128">Schritt 3: Erstellen der Compliancerichtlinie in Intune</span><span class="sxs-lookup"><span data-stu-id="882ae-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="882ae-129">Schritt 4: Zuweisen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="882ae-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="882ae-130">Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="882ae-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="882ae-131">Schritt 1: Aktivieren der Microsoft Intune Verbindung</span><span class="sxs-lookup"><span data-stu-id="882ae-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="882ae-132">Wählen Sie im Navigationsbereich **Einstellungen**  >    >  **Endpoints General**  >  **Advanced features** Microsoft Intune  >  **connection** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-132">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="882ae-133">Umschalten der einstellung Microsoft Intune auf **"Ein".**</span><span class="sxs-lookup"><span data-stu-id="882ae-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="882ae-134">Klicken Sie auf **"Einstellungen speichern".**</span><span class="sxs-lookup"><span data-stu-id="882ae-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="882ae-135">Schritt 2: Aktivieren der Defender für Endpunkt-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="882ae-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="882ae-136">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="882ae-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="882ae-137">Wählen Sie **Die Gerätekompatibilität**  >  **von Microsoft Defender ATP aus.**</span><span class="sxs-lookup"><span data-stu-id="882ae-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="882ae-138">Legen Sie **Verbinden Windows 10.0.15063+-Geräte auf Microsoft Defender Advanced Threat Protection** auf **"Ein" fest.**</span><span class="sxs-lookup"><span data-stu-id="882ae-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="882ae-139">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="882ae-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="882ae-140">Schritt 3: Erstellen der Compliancerichtlinie in Intune</span><span class="sxs-lookup"><span data-stu-id="882ae-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="882ae-141">Wählen Sie im [Azure-Portal](https://portal.azure.com) **alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="882ae-142">Wählen Sie **"Gerätekompatibilitätsrichtlinien**  >    >  **erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="882ae-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="882ae-143">Geben Sie einen **Namen** und eine **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="882ae-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="882ae-144">Wählen Sie **in** **"Plattform"** Windows 10 und höher aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="882ae-145">Legen Sie in den Einstellungen für die **Geräteintegrität** fest, **dass sich das Gerät auf oder unter der Geräte-Bedrohungsstufe auf** Die bevorzugte Ebene befinden soll:</span><span class="sxs-lookup"><span data-stu-id="882ae-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="882ae-146">**Gesichert:** Diese Stufe ist die sicherste.</span><span class="sxs-lookup"><span data-stu-id="882ae-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="882ae-147">Das Gerät kann keine vorhandenen Bedrohungen haben und weiterhin auf Unternehmensressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="882ae-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="882ae-148">Wenn Bedrohungen gefunden werden, wird das Gerät als nicht konform ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="882ae-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="882ae-149">**Niedrig:** Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Ebene vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="882ae-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="882ae-150">Geräte mit mittleren oder hohen Bedrohungsstufen sind nicht konform.</span><span class="sxs-lookup"><span data-stu-id="882ae-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="882ae-151">**Mittel:** Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedrig oder mittel sind.</span><span class="sxs-lookup"><span data-stu-id="882ae-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="882ae-152">Wenn Bedrohungen auf hoher Ebene erkannt werden, wird das Gerät als nicht konform eingestuft.</span><span class="sxs-lookup"><span data-stu-id="882ae-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="882ae-153">**Hoch:** Diese Stufe ist am wenigsten sicher und lässt alle Bedrohungsebenen zu.</span><span class="sxs-lookup"><span data-stu-id="882ae-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="882ae-154">Geräte mit hohen, mittleren oder niedrigen Bedrohungsstufen werden daher als konform betrachtet.</span><span class="sxs-lookup"><span data-stu-id="882ae-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="882ae-155">Wählen Sie **"OK"** und **"Erstellen"** aus, um Ihre Änderungen zu speichern (und die Richtlinie zu erstellen).</span><span class="sxs-lookup"><span data-stu-id="882ae-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="882ae-156">Schritt 4: Zuweisen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="882ae-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="882ae-157">Wählen Sie im [Azure-Portal](https://portal.azure.com) **alle Dienste** aus, filtern Sie nach **Intune,** und wählen Sie **Microsoft Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="882ae-158">Wählen Sie **"Gerätekompatibilitätsrichtlinien"**  >   aus,> Wählen Sie Ihre Microsoft Defender für Endpunkt-Compliancerichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="882ae-159">Wählen Sie **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="882ae-160">Schließen Sie Ihre Azure AD-Gruppen ein, oder schließen Sie sie aus, um ihnen die Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="882ae-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="882ae-161">Um die Richtlinie für die Gruppen bereitzustellen, wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="882ae-162">Die Benutzergeräte, auf die die Richtlinie abzielt, werden auf Compliance ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="882ae-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="882ae-163">Schritt 5: Erstellen einer Azure AD-Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="882ae-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="882ae-164">Öffnen Sie im [Azure-Portal](https://portal.azure.com) **Azure Active Directory**  >  Neue Richtlinie für **bedingten Zugriff.**  >  </span><span class="sxs-lookup"><span data-stu-id="882ae-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="882ae-165">Geben Sie einen **Richtliniennamen** ein, und wählen Sie **"Benutzer und Gruppen"** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="882ae-166">Verwenden Sie die Optionen "Einschließen" oder "Ausschließen", um Ihre Gruppen für die Richtlinie hinzuzufügen, und wählen Sie **"Fertig"** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="882ae-167">Wählen Sie **Cloud-Apps** aus, und wählen Sie aus, welche Apps geschützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="882ae-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="882ae-168">Wählen Sie beispielsweise **"Apps auswählen"** und **"Office 365 SharePoint Online"** und **"Office 365 Exchange Online"** aus.</span><span class="sxs-lookup"><span data-stu-id="882ae-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="882ae-169">Wählen Sie **Fertig** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="882ae-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="882ae-170">Wählen Sie "Bedingungen"-Client-Apps  >   aus, um die Richtlinie auf Apps und Browser anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="882ae-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="882ae-171">Wählen Sie beispielsweise **"Ja"** aus, und aktivieren Sie dann **Browser-** und **mobile Apps und Desktopclients.**</span><span class="sxs-lookup"><span data-stu-id="882ae-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="882ae-172">Wählen Sie **Fertig** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="882ae-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="882ae-173">Wählen Sie **"Gewähren"** aus, um bedingten Zugriff basierend auf der Gerätekompatibilität anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="882ae-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="882ae-174">Wählen Sie beispielsweise **"Zugriff gewähren"** aus,  >  **damit das Gerät als kompatibel gekennzeichnet ist.**</span><span class="sxs-lookup"><span data-stu-id="882ae-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="882ae-175">Wählen Sie **"Auswählen"** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="882ae-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="882ae-176">Wählen Sie **"Richtlinie aktivieren"** und dann **"Erstellen"** aus, um Die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="882ae-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="882ae-177">Weitere Informationen finden Sie unter Erzwingen der [Compliance für Microsoft Defender für Endpunkt mit bedingtem Zugriff in Intune.](/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="882ae-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="882ae-178">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="882ae-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="882ae-179">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="882ae-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
