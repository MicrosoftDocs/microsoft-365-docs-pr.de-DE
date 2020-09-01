---
title: Anheften von apps an das App-Startfeld Ihrer Benutzer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Als globaler Administrator können Sie bis zu drei apps an das App-Startfeld Ihrer Benutzer anheften.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310875"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="fe0de-103">Anheften von apps an das App-Startfeld Ihrer Benutzer</span><span class="sxs-lookup"><span data-stu-id="fe0de-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="fe0de-104">Sie können Steuerelemente im Azure Active Directory-Portal verwenden, um bis zu drei apps an Office.com und das App-Startfeld für alle Benutzer in Ihrer Organisation zu fixieren.</span><span class="sxs-lookup"><span data-stu-id="fe0de-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="fe0de-105">Sie können auch Gruppen von Anwendungen organisieren.</span><span class="sxs-lookup"><span data-stu-id="fe0de-105">You can also organize groups of applications.</span></span> <span data-ttu-id="fe0de-106">Alle hinzugefügten Apps können später vom Benutzer jederzeit wieder aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="fe0de-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="fe0de-107">Um eine APP für Ihre Benutzer zu fixieren, müssen Sie ein Cloud-Anwendungsadministrator oder Anwendungsadministrator in Azure Active Directory oder ein globaler Administrator in Office 365 sein.</span><span class="sxs-lookup"><span data-stu-id="fe0de-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="fe0de-108">Weitere Informationen zu Administratorrollen finden Sie unter [Administratorrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) und [Administratorrollen in Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fe0de-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="fe0de-109">Weitere Informationen zum App-Startfeld und Office.com finden Sie unter [Meet the App Launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) und [Updates to Office.com and the-Office 365 App Launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) Blog article.</span><span class="sxs-lookup"><span data-stu-id="fe0de-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="fe0de-110">Verwenden des Azure Active Directory-Portals zum Anheften von apps</span><span class="sxs-lookup"><span data-stu-id="fe0de-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="fe0de-111">Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="fe0de-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="fe0de-112">Wählen Sie im linken Navigationsbereich **Alle anzeigen**aus, und wählen Sie unter **Admin Center**die Option **Azure Active Directory**aus.</span><span class="sxs-lookup"><span data-stu-id="fe0de-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="fe0de-113">Wählen Sie in **Azure Active Directory**die Option **Enterprise Applications**  >  **Users Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="fe0de-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="fe0de-114">Wählen Sie im Abschnitt **Office 365 Einstellungen** die Option **Anwendung hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fe0de-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="fe0de-115">Wählen Sie die Anwendungen aus, die Sie an das App-Startfeld von Benutzern anheften möchten, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="fe0de-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365-Einstellungen zum Anheften von apps.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="fe0de-117">Anheften einer benutzerdefinierten App</span><span class="sxs-lookup"><span data-stu-id="fe0de-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="fe0de-118">Auf der Benutzeroberfläche wird angegeben, ob Sie zusätzliche Azure AD Lizenzen erwerben müssen, um diese Funktion nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="fe0de-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="fe0de-119">Weitere Informationen finden Sie unter [Azure Active Directory Pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="fe0de-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="fe0de-120">Wählen Sie in **Azure Active Directory**unter **Enterprise Applications**  >  **New Application** oben auf der Seite **alle Anwendungen** .</span><span class="sxs-lookup"><span data-stu-id="fe0de-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="fe0de-121">Wählen Sie auf der Seite **Anwendung hinzufügen** die Option **nicht-Kataloganwendung** aus, oder erstellen Sie eine **eigene Anwendung** , wenn Sie sich in der Vorschauversion von Azure Active Directory befinden.</span><span class="sxs-lookup"><span data-stu-id="fe0de-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="fe0de-122">Geben Sie einen Namen für die Anwendung ein, und weisen Sie dann den Benutzer auf der Registerkarte **Benutzer und Gruppen** zu.</span><span class="sxs-lookup"><span data-stu-id="fe0de-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="fe0de-123">Verwenden Sie die Registerkarte **Eigenschaften** , um ein Symbol für die APP hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="fe0de-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="fe0de-124">Um der App eine URL zuzuweisen, wählen Sie auf der Registerkarte **einmaliges Anmelden** die Option **verknüpft** aus, und geben Sie dann eine URL ein.</span><span class="sxs-lookup"><span data-stu-id="fe0de-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="fe0de-125">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fe0de-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="fe0de-126">Erstellen von Anwendungssammlungen</span><span class="sxs-lookup"><span data-stu-id="fe0de-126">Create application collections</span></span>

<span data-ttu-id="fe0de-127">Sie können auch Anwendungssammlungen für die Benutzer in Ihrer Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe0de-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="fe0de-128">Anweisungen finden Sie unter [Erstellen von Sammlungen im Portal "meine apps" im Azure-Portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span><span class="sxs-lookup"><span data-stu-id="fe0de-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>