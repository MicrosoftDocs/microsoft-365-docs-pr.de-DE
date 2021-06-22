---
title: Verwenden Microsoft Teams Klassen mit Blackboard
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrieren Microsoft Teams Klassen in Ihr Learning-Verwaltungssystem
ms.openlocfilehash: 047f640befa967b78597c5eba93f9c64f22ec1c2
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053251"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="c9c3f-103">Verwenden Microsoft Teams Klassen mit Blackboard</span><span class="sxs-lookup"><span data-stu-id="c9c3f-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9c3f-104">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c9c3f-105">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c9c3f-106">Microsoft Teams Klassen ist eine Learning Tools Interoperability (LTI)-App, die Lehrkräften und Schülern hilft, problemlos zwischen ihrem Learning Management System (LMS) und Teams zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="c9c3f-107">Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="c9c3f-108">Genehmigen der App im Microsoft Azure Mandanten</span><span class="sxs-lookup"><span data-stu-id="c9c3f-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="c9c3f-109">Die folgenden Aufgaben werden vom Microsoft Office 365-Administrator und dem Blackboard Learn Ultra-Administrator abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="c9c3f-110">Vor der Verwaltung der Integration in Blackboard Learn Ultra muss der Microsoft Office 365-Administrator die **Blackboard-MSFT-Teams für die Learn Ultra Azure-App** für den Microsoft Azure Mandanten der Bildungseinrichtung genehmigen.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="c9c3f-111">Suchen Sie Ihre Microsoft-Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="c9c3f-112">Erfahren [Sie, wie Sie den Mandanten finden.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)</span><span class="sxs-lookup"><span data-stu-id="c9c3f-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="c9c3f-113">Leiten Sie den Microsoft Identity Platform Admin Consent-Endpunkt gemäß dem folgenden Beispiel um:</span><span class="sxs-lookup"><span data-stu-id="c9c3f-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="c9c3f-114">Ersetzen Sie {tenant} durch die Microsoft-Mandanten-ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="c9c3f-115">Registrieren der Integrations-Apps</span><span class="sxs-lookup"><span data-stu-id="c9c3f-115">Register the integration apps</span></span>

<span data-ttu-id="c9c3f-116">Als Blackboard Learn Ultra-Administrator müssen Sie 2 LTI 1.3-Integrations-Apps in Ihrer Testumgebung registrieren:</span><span class="sxs-lookup"><span data-stu-id="c9c3f-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="c9c3f-117">Die Blackboard Learn Class Teams Integration zur Unterstützung der Listensynchronisierung</span><span class="sxs-lookup"><span data-stu-id="c9c3f-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="c9c3f-118">Die LTI-App für Microsoft Teams Klassenteam</span><span class="sxs-lookup"><span data-stu-id="c9c3f-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="c9c3f-119">Notieren Sie sich die folgenden LTI-Client-IDs für beide Apps:</span><span class="sxs-lookup"><span data-stu-id="c9c3f-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="c9c3f-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="c9c3f-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="c9c3f-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="c9c3f-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="c9c3f-122">Greifen Sie auf den Admin-Bereich zu, und suchen Sie unter **"Integrationen"** nach den LTI-Toolanbietern.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![Im Dialogfeld "LTI-Toolanbieter" wird eine Liste der Anbieter angezeigt.](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="c9c3f-124">Wählen Sie **"LTI1.3/Advantage-Tool registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="c9c3f-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="c9c3f-125">Geben Sie die erste der bereitgestellten Client-IDs ein (Blackboard oder Microsoft), und wählen Sie **"Übermitteln"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![das LTI-Registertool mit einem Feld zum Eingeben der Client-ID](../media/lti-media/register-tool.png)

5. <span data-ttu-id="c9c3f-127">Überprüfen Sie die vordefinierten Einstellungen, und stellen Sie sicher, dass der Toolstatus als genehmigt gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="c9c3f-128">Scrollen Sie nach unten, und wählen Sie dann **"Absenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="c9c3f-129">Wiederholen Sie die vorherigen Schritte, um die zweite der LTI-Apps in Ihrer Umgebung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="c9c3f-130">Einrichten der REST-Anwendung und der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="c9c3f-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="c9c3f-131">Der Blackboard Learn Ultra-Administrator muss auch die REST-Anwendung und die Konfiguration für die Ursprungsübergreifende Ressourcenfreigabe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="c9c3f-132">Führen Sie die folgenden Schritte aus, um die REST-Anwendung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="c9c3f-133">Greifen Sie auf die Lernverwaltungstools zu, und wählen Sie dann im Abschnitt **"Integrationen"** DIE **REST-API-Integrationen** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c9c3f-134">Wählen Sie **Integrationen erstellen** aus, und geben Sie die gleiche Anwendungs-/Client-ID ein, die Sie für das Tool "Blackboard Learn Class Teams Integration LTI" eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="c9c3f-135">Geben Sie den Benutzer "Lernen" ein (dies könnte Ihr eigener Administratorbenutzernamen "Lernen" sein), oder wählen Sie **"Durchsuchen"** aus, um zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="c9c3f-136">Wählen Sie **"Ja"** für **den Endbenutzerzugriff aus.**</span><span class="sxs-lookup"><span data-stu-id="c9c3f-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="c9c3f-137">Wählen Sie **"Ja"** **aus, um autorisiert zu sein, als Benutzer zu fungieren**</span><span class="sxs-lookup"><span data-stu-id="c9c3f-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="c9c3f-138">Wählen Sie Nach Abschluss **absenden** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="c9c3f-139">Einrichten der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="c9c3f-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="c9c3f-140">Greifen Sie auf die Lernverwaltungstools zu, und wählen Sie im Abschnitt **"Integrationen"** die Option **"Cross-Origin Resource Sharing"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c9c3f-141">Wählen Sie **"Konfiguration erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="c9c3f-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="c9c3f-142">Geben Sie `https://bb-ms-teams-ultra-ext.api.blackboard.com` den Ursprung ein.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="c9c3f-143">Fügen Sie das Wort **Autorisierung** in den **zulässigen Kopfzeilen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="c9c3f-144">**Auf "Verfügbar"** auf **"Ja"** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="c9c3f-145">Wählen Sie Nach Abschluss **absenden** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="c9c3f-146">Aktivieren von Klassen-Teams in Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="c9c3f-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="c9c3f-147">Nachdem Sie die LTI-Tools aktiviert haben, müssen Sie im nächsten Schritt die Microsoft-Klasse Teams Integration von Ihrem eigenen Microsoft Office 365 Mandanten einrichten.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="c9c3f-148">Sie können dies tun, indem Sie diese Schritte als Blackboard Learn Ultra-Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="c9c3f-149">Wählen Sie unter **"Administratortools**  >  **und Hilfsprogramme** lernen" **Microsoft Teams Integrationsadministrator** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![Das Dialogfeld "Tools und Dienstprogramme" mit einer Liste der verfügbaren Tools](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="c9c3f-151">Aktivieren Sie das Kontrollkästchen zum **Aktivieren Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="c9c3f-152">Geben Sie Ihre Mandanten-ID ein, wie im Abschnitt unter "Microsoft O365-Administrator" angegeben.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="c9c3f-153">Sie können die Einstellungen erst speichern, wenn die App vom O365-Administrator genehmigt wurde. Weitere Informationen finden Sie unter [Genehmigen der App in Microsoft Azure Mandanten.](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="c9c3f-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="c9c3f-154">Wenn der globale O365-Administrator die Blackboard-Teams-Anwendung in Ihrem Microsoft-Mandanten genehmigt hat, wählen Sie **"Übermitteln"** aus.</span><span class="sxs-lookup"><span data-stu-id="c9c3f-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
