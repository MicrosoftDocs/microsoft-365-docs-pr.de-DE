---
title: Verwenden von Microsoft Teams-Klassen in Ihrem Lernverwaltungssystem
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
description: Integrieren von Microsoft Teams-Klassen in Ihr Lernverwaltungssystem
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327787"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="c006d-103">Verwenden von Microsoft Teams-Klassen in Ihrem Lernverwaltungssystem</span><span class="sxs-lookup"><span data-stu-id="c006d-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c006d-104">Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="c006d-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c006d-105">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="c006d-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c006d-106">Microsoft Teams-Kursteams ist eine LTI-App (Learning Tools Interoperability), die Lehrkräften und Schülern dabei hilft, problemlos zwischen ihrem Lernverwaltungssystem (Learning Management System, LMS) und Teams zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="c006d-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="c006d-107">Benutzer können direkt in ihrem LMS auf ihre Kursteams zugreifen, die ihrem Kurs zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c006d-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="c006d-108">Genehmigen der App im Microsoft Azure-Mandanten</span><span class="sxs-lookup"><span data-stu-id="c006d-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="c006d-109">Die folgenden Aufgaben werden vom Microsoft Office 365-Administrator und dem Blackboard Learn Ultra-Administrator ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c006d-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="c006d-110">Vor der Verwaltung der Integration in Blackboard Learn Ultra muss der Microsoft Office 365-Administrator die Blackboard **MSFT Teams for Learn Ultra Azure-App** für den Microsoft Azure-Mandanten der Institution genehmigen.</span><span class="sxs-lookup"><span data-stu-id="c006d-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="c006d-111">Suchen Sie Nach Ihrer Microsoft-Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="c006d-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="c006d-112">Erfahren [Sie, wie Sie den Mandanten finden.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)</span><span class="sxs-lookup"><span data-stu-id="c006d-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="c006d-113">Leiten Sie den Microsoft Identity Platform Admin Consent Endpoint gemäß dem folgenden Beispiel um:</span><span class="sxs-lookup"><span data-stu-id="c006d-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="c006d-114">Ersetzen Sie {tenant} durch die Microsoft-Mandanten-ID Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c006d-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="c006d-115">Registrieren der Integrations-Apps</span><span class="sxs-lookup"><span data-stu-id="c006d-115">Register the integration apps</span></span>

<span data-ttu-id="c006d-116">Als Blackboard Learn Ultra-Administrator müssen Sie 2 LTI 1.3-Integrations-Apps in Ihrer Testumgebung registrieren:</span><span class="sxs-lookup"><span data-stu-id="c006d-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="c006d-117">Die Blackboard Learn Class Teams-Integration zur Unterstützung der Dienstplansynchronisierung</span><span class="sxs-lookup"><span data-stu-id="c006d-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="c006d-118">Die Microsoft Teams-Team-LTI-App</span><span class="sxs-lookup"><span data-stu-id="c006d-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="c006d-119">Notieren Sie sich die folgenden LTI-Client-IDs für beide Apps:</span><span class="sxs-lookup"><span data-stu-id="c006d-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="c006d-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="c006d-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="c006d-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="c006d-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="c006d-122">Greifen Sie auf den Administratorbereich zu, und suchen Sie unter **Integrationen** nach den LTI-Toolanbietern.</span><span class="sxs-lookup"><span data-stu-id="c006d-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![Dies ist das Dialogfeld LTI-Toolanbieter, in dem eine Liste der Anbieter angezeigt wird](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="c006d-124">Wählen **Sie LTI1.3/Advantage Tool registrieren aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="c006d-125">Geben Sie die erste der bereitgestellten Client-IDs (Blackboard oder Microsoft) ein, und wählen Sie **Übermitteln aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![Das LTI-Registrierungstool mit einem Feld zur Eingabe der Client-ID](../media/lti-media/register-tool.png)

5. <span data-ttu-id="c006d-127">Überprüfen Sie die vordefinierten Einstellungen, und stellen Sie sicher, dass der Toolstatus als genehmigt gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="c006d-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="c006d-128">Scrollen Sie nach unten, und wählen Sie dann **Absenden aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="c006d-129">Wiederholen Sie die vorherigen Schritte, um die zweite der LTI-Apps in Ihrer Umgebung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c006d-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="c006d-130">Einrichten der REST-Anwendung und der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="c006d-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="c006d-131">Der Blackboard Learn Ultra-Administrator muss außerdem die REST-Anwendung und die Konfiguration für die cross Origin Resource Sharing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c006d-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="c006d-132">Führen Sie die folgenden Schritte aus, um die REST-Anwendung zu einrichten</span><span class="sxs-lookup"><span data-stu-id="c006d-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="c006d-133">Greifen Sie auf die Lernverwaltungstools zu, und wählen Sie dann **REST-API-Integrationen** im **Abschnitt Integrationen** aus.</span><span class="sxs-lookup"><span data-stu-id="c006d-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c006d-134">Wählen **Sie Integrationen erstellen** aus, und geben Sie dieselbe Anwendungs-/Client-ID ein, die Sie für das Blackboard Learn Class Teams Integration LTI-Tool eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="c006d-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="c006d-135">Geben Sie den Benutzer lernen ein (dies kann Ihr eigener Benutzername für den Lernadministrator sein), oder wählen Sie **Durchsuchen** aus, um zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c006d-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="c006d-136">Wählen **Sie Ja** für **Endbenutzerzugriff aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="c006d-137">Wählen **Sie Ja** für **Autorisiert als Benutzer handeln aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="c006d-138">Wählen **Sie Senden** aus, sobald sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c006d-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="c006d-139">Einrichten der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="c006d-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="c006d-140">Greifen Sie auf die Lernverwaltungstools zu, und wählen Sie im Abschnitt **Integrationen** die Option **Cross-Origin Resource Sharing** aus.</span><span class="sxs-lookup"><span data-stu-id="c006d-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="c006d-141">Wählen **Sie Konfiguration erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="c006d-142">Geben `https://bb-ms-teams-ultra-ext.api.blackboard.com` Sie den Ursprung ein.</span><span class="sxs-lookup"><span data-stu-id="c006d-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="c006d-143">Fügen Sie das Wort **Autorisierung** in den **zulässigen Kopfzeilen hinzu.**</span><span class="sxs-lookup"><span data-stu-id="c006d-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="c006d-144">Set **Available** to **Yes**.</span><span class="sxs-lookup"><span data-stu-id="c006d-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="c006d-145">Wählen **Sie Senden** aus, sobald sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c006d-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="c006d-146">Aktivieren von Kursteams in Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="c006d-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="c006d-147">Nachdem Sie die LTI-Tools aktiviert haben, besteht Der nächste Schritt in der Einrichtung der Microsoft Class Teams-Integration von Ihrem Microsoft Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c006d-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="c006d-148">Dazu können Sie die folgenden Schritte als Blackboard Learn Ultra Admin ausführen.</span><span class="sxs-lookup"><span data-stu-id="c006d-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="c006d-149">Wählen **Sie unter Learn Admin** Tools and  >  **Utilities** die Option Microsoft Teams Integration Admin **aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![Das Dialogfeld Tools und Dienstprogramme mit einer Liste der verfügbaren Tools](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="c006d-151">Aktivieren Sie das Kontrollkästchen Microsoft **Teams aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="c006d-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="c006d-152">Geben Sie Ihre Mandanten-ID wie im Abschnitt unter Microsoft O365 Admin referenziert ein.</span><span class="sxs-lookup"><span data-stu-id="c006d-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="c006d-153">Sie können die Einstellungen erst speichern, wenn die App vom O365-Administrator genehmigt wurde. Weitere [Informationen finden Sie unter Genehmigen der App im Microsoft Azure-Mandanten](#approve-the-app-in-the-microsoft-azure-tenant).</span><span class="sxs-lookup"><span data-stu-id="c006d-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="c006d-154">Wenn der globale O365-Administrator die Blackboard Teams-Anwendung in Ihrem Microsoft Mandant genehmigt hat, wählen Sie **Übermitteln aus.**</span><span class="sxs-lookup"><span data-stu-id="c006d-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
