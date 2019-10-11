---
title: Verwalten von Empfängern in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) bietet mehrere Möglichkeiten zur Verwaltung Ihrer E-Mail-Empfänger. Als Administrator können Sie bestimmte Verwaltungsaufgaben im Exchange Admin Center (EAC) oder mithilfe von Remote Windows PowerShell durchführen und andere Verwaltungsaufgaben im Microsoft 365 Admin Center überprüfen.
ms.openlocfilehash: f1bac7d19b52d175589f63216b49ce3b0985307c
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441472"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="0cfd8-104">Verwalten von Empfängern in EOP</span><span class="sxs-lookup"><span data-stu-id="0cfd8-104">Manage recipients in EOP</span></span>

<span data-ttu-id="0cfd8-105">Microsoft Exchange Online Protection (EOP) bietet mehrere Möglichkeiten zur Verwaltung Ihrer E-Mail-Empfänger.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="0cfd8-106">Als Administrator können Sie bestimmte Verwaltungsaufgaben im Exchange Admin Center (EAC) oder mithilfe von Remote Windows PowerShell durchführen und andere Verwaltungsaufgaben im Microsoft 365 Admin Center überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="0cfd8-107">EOP unterstützt die folgenden Typen von Empfängern:</span><span class="sxs-lookup"><span data-stu-id="0cfd8-107">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="0cfd8-108">**E-Mail-Benutzer**: e-Mail-Benutzer sind Empfänger in ihren verwalteten EoP-Domänen.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-108">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="0cfd8-109">Diese Empfänger verfügen über Anmeldeinformationen in Ihrer Office 365 Organisation, haben jedoch externe e-Mail-Adressen, was bedeutet, dass sich Ihre Empfängerpostfächer außerhalb ihrer Cloud-Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-109">These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="0cfd8-110">Sie können e-Mail-Benutzer hinzufügen, damit Sie e-Mails empfangen können, und Sie können auch Nachrichtenfluss Regeln (auch bekannt als Transportregeln) für bestimmte Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="0cfd8-111">Sie können auch e-Mail-Benutzern in Ihrer Organisation Rollen zuweisen; Benutzer mit Berechtigungen der Verwaltungsrollengruppe können auf das Exchange Admin Center (EAC) zugreifen und bestimmte Verwaltungsaufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="0cfd8-112">Weitere Informationen zu Benutzerrollen und zum Zuweisen von Benutzerrollen in EoP finden Sie unter [Manage Administrator Role Group Permissions in EoP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0cfd8-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="0cfd8-113">Weitere Informationen zum Verwalten von E-Mail-Benutzer in EOP finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0cfd8-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="0cfd8-114">**Gruppen**: e-Mail-Benutzer können in Verteilergruppen oder Sicherheitsgruppen zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-114">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="0cfd8-115">Weitere Informationen zum Verwalten von Gruppen in EOP finden Sie unter [Verwalten von Gruppen in EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0cfd8-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
