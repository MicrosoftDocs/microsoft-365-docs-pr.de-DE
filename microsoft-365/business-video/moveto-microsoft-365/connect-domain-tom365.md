---
title: Verbinden Ihrer Domäne zu Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihre Domäne mit Microsoft 365 verbinden.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925110"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="ac4d0-103">Verbinden Ihrer Domäne mit Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ac4d0-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="ac4d0-104">Nachdem Sie Microsoft 365 eingerichtet und Ihre E-Mail-Daten aus Google Workspace verschoben haben, können Sie Ihre Domäne mit Microsoft 365 verbinden.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="ac4d0-105">Zuerst müssen Sie vorhandene DNS-Einträge aus Google löschen, dann können wir neue DNS-Einträge aus Microsoft 365 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="ac4d0-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="ac4d0-106">Try it!</span></span>

1. <span data-ttu-id="ac4d0-107">Melden Sie sich bei Ihrer Google Workspace-Verwaltungskonsole [unter admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="ac4d0-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="ac4d0-108">Select **Domains**, **Manage domains**, View **details**, **Manage domain**, then **DNS** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="ac4d0-109">Scrollen Sie nach unten zu **synthetischen Datensätzen,** öffnen **Sie Google Workspace,** wählen **Sie "Löschen"** und **dann** erneut "Löschen" aus.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="ac4d0-110">Scrollen Sie nach unten zu **benutzerdefinierten** Ressourceneinträgen, und löschen Sie alle vorhandenen DNS-Einträge, die angezeigt werden, einschließlich aller, die Sie möglicherweise zuvor für Microsoft 365 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="ac4d0-111">Wechseln Sie zum [Microsoft 365 Admin Center.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ac4d0-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="ac4d0-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="ac4d0-113">Wählen Sie dann Ihre Standarddomäne aus.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="ac4d0-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="ac4d0-115">Scrollen Sie nach unten, um die DNS-Einträge, die nach Google kopiert werden müssen, zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="ac4d0-116">Öffnen **Sie MX-Einträge,** und kopieren Sie den Eintrag unter "Verweist auf **Adresse"** oder "Wert".</span><span class="sxs-lookup"><span data-stu-id="ac4d0-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="ac4d0-117">Kehren Sie zu Google zurück, und öffnen Sie im Abschnitt **"Benutzerdefinierte Ressourceneinträge"** das Eintragstypdropdown, und wählen Sie **MX aus.**</span><span class="sxs-lookup"><span data-stu-id="ac4d0-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="ac4d0-118">Fügen Sie **in das Feld "Daten"** den kopierten Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="ac4d0-119">Wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-119">Then select **Add**.</span></span>
1. <span data-ttu-id="ac4d0-120">Wiederholen Sie den Vorgang für CNAME- und TXT-Einträge, und fügen Sie die Werte auf der Google #A0 hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="ac4d0-121">Kehren Sie zum Microsoft 365 Admin Center zurück, und wählen Sie **"Weiter" aus.**</span><span class="sxs-lookup"><span data-stu-id="ac4d0-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="ac4d0-122">Ihre Domäneneinrichtung ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ac4d0-122">Your domain setup is complete.</span></span>