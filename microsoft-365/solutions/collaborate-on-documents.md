---
title: Zusammenarbeit mit Gästen an einem Dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: Hier erfahren Sie, wie Sie mit Gästen in einem Dokument in SharePoint und OneDrive zusammenarbeiten.
ms.openlocfilehash: 33d9300343b23702d5024ac0b489930ac815be7e
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002265"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="a9526-103">Zusammenarbeit mit Gästen an einem Dokument</span><span class="sxs-lookup"><span data-stu-id="a9526-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="a9526-104">Wenn Sie mit Personen außerhalb Ihrer Organisation in Dokumenten in SharePoint oder OneDrive zusammenarbeiten müssen, können Sie Ihnen einen Freigabe Link an das Dokument senden.</span><span class="sxs-lookup"><span data-stu-id="a9526-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="a9526-105">In diesem Artikel werden die Microsoft 365-Konfigurationsschritte durchlaufen, die erforderlich sind, um Freigabelinks für SharePoint und OneDrive für die Anforderungen Ihrer Organisation einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a9526-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a9526-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="a9526-106">Video demonstration</span></span>

<span data-ttu-id="a9526-107">Dieses Video zeigt die in diesem Dokument beschriebenen Konfigurationsschritte.</span><span class="sxs-lookup"><span data-stu-id="a9526-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="a9526-108">Azure Organizational Relationships-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a9526-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="a9526-109">Die Freigabe in Microsoft 365 wird auf der höchsten Ebene durch die Einstellungen für organisatorische Beziehungen in Azure Active Directory gesteuert.</span><span class="sxs-lookup"><span data-stu-id="a9526-109">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="a9526-110">Wenn die Gast Freigabe in Azure AD deaktiviert oder eingeschränkt ist, werden alle Freigabeeinstellungen, die Sie in Microsoft 365 konfigurieren, außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="a9526-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="a9526-111">Überprüfen Sie die Einstellungen für Organisationsbeziehungen, um sicherzustellen, dass die Freigabe für Gäste nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9526-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Screenshot der Seite mit den Einstellungen für die Azure Active Directory-Organisationsbeziehungen](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="a9526-113">So legen Sie Einstellungen für die Organisationsbeziehung fest</span><span class="sxs-lookup"><span data-stu-id="a9526-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="a9526-114">Melden Sie sich bei Microsoft Azure [https://portal.azure.com](https://portal.azure.com)an an.</span><span class="sxs-lookup"><span data-stu-id="a9526-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a9526-115">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a9526-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="a9526-116">Klicken Sie im Bereich **Übersicht** auf **Organisationsbeziehungen**.</span><span class="sxs-lookup"><span data-stu-id="a9526-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="a9526-117">Klicken Sie im Bereich **Organisationsbeziehungen** auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a9526-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="a9526-118">Stellen Sie sicher, dass **Administratoren und Benutzer in der Rolle "Gast einladender" eingeladen** werden und **Mitglieder einladen können** , beide auf " **Ja**" festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="a9526-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="a9526-119">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9526-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="a9526-120">Beachten Sie die Einstellungen im Abschnitt Einschränkungen für die **Zusammenarbeit** .</span><span class="sxs-lookup"><span data-stu-id="a9526-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="a9526-121">Stellen Sie sicher, dass die Domänen der Gäste, mit denen Sie zusammenarbeiten möchten, nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9526-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="a9526-122">SharePoint-Freigabeeinstellungen auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="a9526-122">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="a9526-123">Damit Personen außerhalb Ihrer Organisation Zugriff auf ein Dokument in SharePoint oder OneDrive haben, müssen die Freigabeeinstellungen für SharePoint und OneDrive auf Organisationsebene die Freigabe für Personen außerhalb Ihrer Organisation zulassen.</span><span class="sxs-lookup"><span data-stu-id="a9526-123">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="a9526-124">Die Einstellungen auf Organisationsebene für SharePoint bestimmen, welche Einstellungen für einzelne SharePoint-Websites verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9526-124">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="a9526-125">Websiteeinstellungen dürfen nicht so restriktiv wie die Einstellungen auf Organisationsebene sein.</span><span class="sxs-lookup"><span data-stu-id="a9526-125">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="a9526-126">Die Einstellung auf Organisationsebene für OneDrive legt fest, welche Freigabeebene in den OneDrive-Bibliotheken der Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a9526-126">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="a9526-127">Wenn Sie für SharePoint und OneDrive die nicht authentifizierte Datei-und Ordnerfreigabe zulassen möchten, wählen Sie **jeden**aus.</span><span class="sxs-lookup"><span data-stu-id="a9526-127">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="a9526-128">Wenn Sie sicherstellen möchten, dass sich Personen außerhalb Ihrer Organisation authentifizieren müssen, wählen Sie **neue und vorhandene Gäste**aus.</span><span class="sxs-lookup"><span data-stu-id="a9526-128">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="a9526-129">*Jeder* Link ist die einfachste Möglichkeit zur Freigabe: Personen außerhalb Ihrer Organisation können die Verknüpfung ohne Authentifizierung öffnen und können Sie an andere weitergeben.</span><span class="sxs-lookup"><span data-stu-id="a9526-129">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="a9526-130">Wählen Sie für SharePoint die frei zügigste Einstellung aus, die von einer beliebigen Website in Ihrer Organisation benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a9526-130">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Screenshot der SharePoint-Freigabeeinstellungen auf Organisationsebene](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="a9526-132">So legen Sie Freigabeeinstellungen für SharePoint-Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="a9526-132">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="a9526-133">Klicken Sie im Microsoft 365 Admin Center in der linken Navigationsleiste unter **Admin Centers**auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a9526-133">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="a9526-134">Klicken Sie im SharePoint Admin Center links in der Navigation auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="a9526-134">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="a9526-135">Stellen Sie sicher, dass die externe Freigabe für SharePoint oder OneDrive auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a9526-135">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="a9526-136">(Beachten Sie, dass die OneDrive-Einstellung nicht restriktiver als die SharePoint-Einstellung sein kann.)</span><span class="sxs-lookup"><span data-stu-id="a9526-136">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="a9526-137">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9526-137">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="a9526-138">Standard Link Einstellungen für SharePoint-Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="a9526-138">SharePoint organization level default link settings</span></span>

<span data-ttu-id="a9526-139">Die Standardeinstellungen für Datei-und Ordnerverknüpfung legen fest, welche Link Option dem Benutzer standardmäßig angezeigt wird, wenn er eine Datei oder einen Ordner freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="a9526-139">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="a9526-140">Benutzer können den Verknüpfungstyp vor der Freigabe bei Bedarf in eine der anderen Optionen ändern.</span><span class="sxs-lookup"><span data-stu-id="a9526-140">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="a9526-141">Beachten Sie, dass sich diese Einstellung auf SharePoint-Websites in Ihrer Organisation sowie auf OneDrive auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a9526-141">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="a9526-142">Wählen Sie den Linktyp aus, der standardmäßig ausgewählt ist, wenn Benutzer Dateien und Ordner freigeben:</span><span class="sxs-lookup"><span data-stu-id="a9526-142">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="a9526-143">**Jeder, der über den Link verfügt** – wählen Sie diese Option aus, wenn Sie eine Vielzahl von nicht authentifizierten Datei-und Ordner Freigaben erwarten.</span><span class="sxs-lookup"><span data-stu-id="a9526-143">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="a9526-144">Wenn Sie *alle* Links zulassen möchten, jedoch über versehentliche nicht authentifizierte Freigaben besorgt sind, sollten Sie eine der anderen Optionen als Standard verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9526-144">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="a9526-145">Dieser Linktyp ist nur verfügbar, wenn Sie die Freigabe von **Benutzern** aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="a9526-145">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="a9526-146">**Nur Personen in Ihrer Organisation** – wählen Sie diese Option aus, wenn Sie davon ausgehen, dass die meisten Datei-und Ordner Freigaben für Personen in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="a9526-146">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="a9526-147">**Bestimmte Personen** – diese Option wird empfohlen, wenn Sie eine Vielzahl von Datei-und Ordner Freigaben für Gäste erwarten.</span><span class="sxs-lookup"><span data-stu-id="a9526-147">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="a9526-148">Diese Art von Link funktioniert mit Gästen und erfordert die Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a9526-148">This type of link works with guests and requires them to authenticate.</span></span>
 
![Screenshot der Freigabeeinstellungen auf Organisationsebene für Dateien und Ordner in SharePoint und OneDrive](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="a9526-150">So legen Sie die Standard Link Einstellungen für SharePoint und OneDrive auf Organisationsebene fest</span><span class="sxs-lookup"><span data-stu-id="a9526-150">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="a9526-151">Navigieren Sie im SharePoint Admin Center zur Seite Freigabe.</span><span class="sxs-lookup"><span data-stu-id="a9526-151">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="a9526-152">Wählen Sie unter **Datei-und Ordner Links**den standardmäßigen Freigabe Link aus, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a9526-152">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="a9526-153">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9526-153">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="a9526-154">Freigabeeinstellungen für SharePoint-Websiteebene</span><span class="sxs-lookup"><span data-stu-id="a9526-154">SharePoint site level sharing settings</span></span>

<span data-ttu-id="a9526-155">Wenn Sie Dateien und fodlers in einer SharePoint-Website freigeben, müssen Sie auch die Freigabeeinstellungen auf Websiteebene für diese Website überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a9526-155">If you're sharing files and fodlers that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Screenshot der externen SharePoint-Freigabeeinstellungen](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="a9526-157">So legen Sie Freigabeeinstellungen auf Websiteebene fest</span><span class="sxs-lookup"><span data-stu-id="a9526-157">To set site-level sharing settings</span></span>
1. <span data-ttu-id="a9526-158">Erweitern Sie im SharePoint Admin Center links in der Navigation **Sites** und klicken Sie auf **Aktive Sites**.</span><span class="sxs-lookup"><span data-stu-id="a9526-158">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="a9526-159">Wählen Sie die Website aus, die Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a9526-159">Select the site that you just created.</span></span>
3. <span data-ttu-id="a9526-160">Klicken Sie im Menüband auf **Freigabe**. </span><span class="sxs-lookup"><span data-stu-id="a9526-160">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="a9526-161">Stellen Sie sicher, dass die Freigabe auf " **jeder** " oder " **neue und vorhandene Gäste**" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a9526-161">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="a9526-162">Wenn Sie Änderungen vorgenommen haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a9526-162">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="a9526-163">Benutzer einladen</span><span class="sxs-lookup"><span data-stu-id="a9526-163">Invite users</span></span>

<span data-ttu-id="a9526-164">Die Einstellungen für die Gast Freigabe sind jetzt konfiguriert, sodass Benutzer nun Dateien und Ordner für Personen außerhalb Ihrer Organisation freigeben können.</span><span class="sxs-lookup"><span data-stu-id="a9526-164">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="a9526-165">Weitere Informationen finden Sie unter [Freigeben von OneDrive-Dateien und-Ordnern](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) und Freigeben von [SharePoint-Dateien oder-Ordnern](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="a9526-165">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9526-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9526-166">See Also</span></span>

[<span data-ttu-id="a9526-167">Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="a9526-167">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="a9526-168">Einschränken des Risikos der versehentlichen Gefährdung von Dateien bei der Freigabe für Gäste</span><span class="sxs-lookup"><span data-stu-id="a9526-168">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)