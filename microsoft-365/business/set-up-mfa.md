---
title: Einrichten der mehrstufigen Authentifizierung
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
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Einrichten der mehrstufigen Authentifizierung für Microsoft 365 Business.
ms.openlocfilehash: 59a3ff7a9494ccfc44fa701c6f605a9bd9eeafcf
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715057"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="a02da-103">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a02da-103">Multi-factor authentication</span></span>

<span data-ttu-id="a02da-104">Bei der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) müssen sich Benutzer mit einer zweiten Methode anmelden, um Ihre Identität mit einem Telefonanruf oder mit einer Authentifikator-APP zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a02da-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a02da-105">Einrichten von MFA im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="a02da-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a02da-106">[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="a02da-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="a02da-107">Melden Sie sich mit ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="a02da-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="a02da-108">Klicken Sie im linken Navigationsbereich auf **Setup**.</span><span class="sxs-lookup"><span data-stu-id="a02da-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="a02da-109">Wählen Sie auf der Seite Setup die Option **View** on the **aktivieren Multi-Factor Authentication (MFA)** Card aus.</span><span class="sxs-lookup"><span data-stu-id="a02da-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="a02da-110">Wählen Sie auf der Seite **MFA aktivieren** die Option **Erste Schritte**aus, oder **Verwalten** Sie, wenn Sie bereits MFA eingerichtet haben und Änderungen vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="a02da-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  <span data-ttu-id="a02da-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot von aktivieren Sie die MFA-Seite.":::</span><span class="sxs-lookup"><span data-stu-id="a02da-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot of turn on MFA page.":::</span></span>

5. <span data-ttu-id="a02da-112">Überprüfen Sie im Bereich " **Anmeldungssicherheit verstärken** ", ob die **mehrstufige Authentifizierung für Administratoren erforderlich**ist, und wählen Sie dann **Richtlinie erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a02da-112">On the **Strengthen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
