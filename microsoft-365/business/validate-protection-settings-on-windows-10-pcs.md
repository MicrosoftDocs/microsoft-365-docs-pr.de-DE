---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Erfahren Sie, wie Sie Microsoft 365 Business App Protection-Einstellungen in Windows 10-Geräten überprüfen.
ms.openlocfilehash: c54b053c1f6efbca8fd02431c416793a044c6821
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721858"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="3c75c-103">Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="3c75c-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="3c75c-104">Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf Unternehmensgeräten kopieren können</span><span class="sxs-lookup"><span data-stu-id="3c75c-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="3c75c-105">Nachdem Sie [App-Schutzrichtlinien eingerichtet haben](protection-settings-for-windows-10-devices.md), kann es einige Stunden dauern, bis die Richtlinie für die Geräte der Benutzer wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="3c75c-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="3c75c-106">Wenn Sie das **Kopieren von Unternehmensdaten in persönliche Dateien durch Benutzer verhindern aktiviert haben und Sie zum Speichern von Arbeitsdateien in OneDrive für Unternehmen** Einstellung für unternehmenseigene Geräte zwingen, können Sie dies auf dem Gerät des Benutzers überprüfen, nachdem **Sie eine Verbindung** mit Azure AD hergestellt und sich angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="3c75c-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="3c75c-107">**Überprüfen der Verbindungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="3c75c-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="3c75c-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="3c75c-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="3c75c-111">Auf der Seite **verwaltet nach** \<Mandantenname\> werden die **Verbindungsinformationen** angezeigt, die eine **Verwaltungs Server Adresse** enthalten, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3c75c-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="3c75c-113">**Sicherstellen, dass keine Unternehmensdaten in eine nicht verwaltete app eingefügt werden können**</span><span class="sxs-lookup"><span data-stu-id="3c75c-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="3c75c-114">Öffnen Sie das von Microsoft 365 Business installierte Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="3c75c-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="3c75c-115">Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.</span><span class="sxs-lookup"><span data-stu-id="3c75c-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="3c75c-116">Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c75c-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="3c75c-117">Sie erhalten eine Fehlermeldung, die besagt, dass die APP nicht auf Inhalte zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3c75c-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="3c75c-119">Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c75c-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="3c75c-120">Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf persönlichen Geräten kopieren können</span><span class="sxs-lookup"><span data-stu-id="3c75c-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="3c75c-121">**Überprüfen der Verbindungseinstellungen**</span><span class="sxs-lookup"><span data-stu-id="3c75c-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="3c75c-122">Wechseln Sie auf Ihrem persönlichen Windows 10-Gerät, in dem Sie als lokaler Benutzer angemeldet sind, zu **Windows-Einstellungen**, und klicken oder tippen Sie auf **Konten** \> **Zugriff für Arbeit oder Schule**.</span><span class="sxs-lookup"><span data-stu-id="3c75c-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="3c75c-123">Klicken Sie unter **Auf Arbeits- oder Schulkonto zugreifen** auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3c75c-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="3c75c-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="3c75c-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="3c75c-125">Wählen Sie auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** die Option **Geschäfts-, Schul- oder Unikonto** und dann **Informationen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c75c-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Klicken oder tippen Sie im Dialogfeld Arbeit oder Schulkonto auf Informationen.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="3c75c-127">Auf der Seite **Access work oder School** können Sie die **Verbindungsinformationen** sehen, die eine **Verwaltungs Server Adresse** enthalten, wie in der folgenden Abbildung dargestellt, und enthält die Wörter *WIP* und *MAM* in.</span><span class="sxs-lookup"><span data-stu-id="3c75c-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="3c75c-129">**Sicherstellen, dass keine Unternehmensdaten in eine nicht verwaltete app eingefügt werden können**</span><span class="sxs-lookup"><span data-stu-id="3c75c-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="3c75c-130">Öffnen Sie Outlook 2016, und fügen Sie bei Bedarf Ihr Microsoft 365 Business-Konto hinzu. Melden Sie sich dann mit Ihren Microsoft 365 Business-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="3c75c-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="3c75c-131">Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.</span><span class="sxs-lookup"><span data-stu-id="3c75c-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="3c75c-132">Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c75c-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="3c75c-133">Sie erhalten eine Fehlermeldung, dass besagt, dass APP nicht auf Inhalte zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3c75c-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="3c75c-135">Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.</span><span class="sxs-lookup"><span data-stu-id="3c75c-135">You can, however, paste the same content into Word 2016.</span></span>
    

