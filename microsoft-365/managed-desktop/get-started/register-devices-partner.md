---
title: Schritte für Partner zum Registrieren von Geräten
description: So können Partner Geräte registrieren, damit sie von Microsoft Managed Desktop verwaltet werden können
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445590"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="7f47b-104">Schritte für Partner zum Registrieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="7f47b-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="7f47b-105">In diesem Thema werden die Schritte beschrieben, die Partner befolgen müssen, um Geräte zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7f47b-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="7f47b-106">Der Prozess zum Registrieren von Geräten selbst ist unter Registrieren von Geräten [in Microsoft Managed Desktop selbst dokumentiert.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="7f47b-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="7f47b-107">Vorbereiten der Registrierung</span><span class="sxs-lookup"><span data-stu-id="7f47b-107">Prepare for registration</span></span> 
<span data-ttu-id="7f47b-108">Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit ihnen im [Partner Center einrichten.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="7f47b-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="7f47b-109">Weitere Informationen [zu diesem Prozess finden](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) Sie in der Zustimmungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7f47b-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="7f47b-110">Jeder #A0 kann Geräte im Namen eines beliebigen Kunden hinzufügen, solange der Kunde zuwilligt.</span><span class="sxs-lookup"><span data-stu-id="7f47b-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="7f47b-111">Weitere Informationen zu Partnerbeziehungen und Autopilotberechtigungen finden Sie in der [Partner Center-Hilfe.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="7f47b-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="7f47b-112">Diese Dokumentation ist nur für Partner und OEMs.</span><span class="sxs-lookup"><span data-stu-id="7f47b-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="7f47b-113">Der Prozess für die Selbstregistrierung ist unter Registrieren von Geräten [in Microsoft Managed Desktop selbst dokumentiert.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="7f47b-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="7f47b-114">Registrieren von Geräten mithilfe von Partner Center</span><span class="sxs-lookup"><span data-stu-id="7f47b-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="7f47b-115">Nachdem Sie die Beziehung zu Ihren Kunden eingerichtet haben, können Sie das Partner Center nutzen, um Autopilot Geräte für jeden Kunden hinzuzufügen, mit dem Sie eine Beziehung haben, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="7f47b-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="7f47b-116">Navigieren zu [Partner Center](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="7f47b-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="7f47b-117">Wählen **Sie im** Menü Partner Center die Option Kunden aus, und wählen Sie dann den Kunden aus, dessen Geräte Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="7f47b-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="7f47b-118">Wählen Sie auf der Detailseite des Kunden Geräte **aus.**</span><span class="sxs-lookup"><span data-stu-id="7f47b-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="7f47b-119">Wählen **Sie unter Profile auf** Geräte anwenden die Option Geräte hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7f47b-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="7f47b-120">Geben **Microsoft365Managed_Autopilot** für den Gruppennamen ein, und wählen Sie **dann Durchsuchen** aus, um die Kundenliste (im CSV-Dateiformat) in das Partner Center hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="7f47b-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="7f47b-121">Der Gruppenname muss genau **mit Microsoft365Managed_Autopilot** übereinstimmen, einschließlich Groß- und Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="7f47b-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="7f47b-122">Dadurch können die neu registrierten Geräte dem Microsoft Managed Desktop Autopilot-Profil zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7f47b-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="7f47b-123">Sie sollten diese CSV-Datei mit dem Gerätekauf erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="7f47b-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="7f47b-124">Wenn Sie keine CSV-Datei erhalten haben, können Sie diese selbst erstellen, indem Sie die Schritte unter Hinzufügen von Geräten [zu Windows Autopilot ausführen.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="7f47b-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="7f47b-125">Das Windows PowerShell-Skript ist anders als das für das [Microsoft Managed Desktop Admin-Portal .](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="7f47b-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="7f47b-126">Partner sollten [Get-WindowsAutoPilotInfo verwenden,](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) um Geräte für Microsoft Managed Desktop-Geräte im Partner Center zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="7f47b-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="7f47b-127">Wenn beim Hochladen der CSV-Datei eine Fehlermeldung angezeigt wird, überprüfen Sie das Format der Datei.</span><span class="sxs-lookup"><span data-stu-id="7f47b-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="7f47b-128">Stellen Sie sicher, dass die Spaltenreihenfolge mit den unter Verwenden von Windows Autopilot-Profilen auf neuen Geräten beschriebenen Informationen zum Anpassen der [out-of-box-Benutzererfahrung](/partner-center/autopilot#add-devices-to-a-customers-account)eines Kunden entspricht.</span><span class="sxs-lookup"><span data-stu-id="7f47b-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="7f47b-129">Sie können auch die CSV-Beispieldatei verwenden, die über den Link neben Geräte hinzufügen bereitgestellt wird, **um** eine Geräteliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f47b-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="7f47b-130">Weitere Informationen zu Autopilot in Partnerszenarien finden Sie unter Hinzufügen von Geräten [zum Kundenkonto](/partner-center/autopilot#add-devices-to-a-customers-account).</span><span class="sxs-lookup"><span data-stu-id="7f47b-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="7f47b-131">Registrieren von Geräten mithilfe der OEM-API</span><span class="sxs-lookup"><span data-stu-id="7f47b-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="7f47b-132">Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit ihnen einrichten.</span><span class="sxs-lookup"><span data-stu-id="7f47b-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="7f47b-133">Sie sollten über einen eindeutigen Link verfügen, der Ihren jeweiligen Kunden zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="7f47b-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="7f47b-134">Weitere [Informationen finden Sie unter Einrichten einer OEM-Beziehung.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="7f47b-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="7f47b-135">Nachdem Sie die Beziehung eingerichtet haben, können Sie mit der Registrierung von Geräten für Kunden beginnen, indem Sie das Gruppentag **Microsoft365Managed_Autopilot.**</span><span class="sxs-lookup"><span data-stu-id="7f47b-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f47b-136">Der Gruppenname muss genau **mit Microsoft365Managed_Autopilot** übereinstimmen, einschließlich Groß- und Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="7f47b-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="7f47b-137">Dadurch können die neu registrierten Geräte dem Microsoft Managed Desktop Autopilot-Profil zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7f47b-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>