---
title: Erfahren Sie mehr über Informationsbarrieren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Verwenden Sie Informationsbarrieren, um die Kommunikation mit Microsoft Teams in Ihrer Organisation sicherzustellen.
ms.openlocfilehash: f063a18dcadf5de74b43b2efeba3910f65e40102
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153497"
---
# <a name="information-barriers"></a><span data-ttu-id="6cf13-103">Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="6cf13-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="6cf13-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="6cf13-104">Overview</span></span>

<!--

# Information barriers (click-through test)

## Overview



 [![Click-Through for Information Barriers](./media/information-barriers/clickthrough-information-barriers-thumbnail.png)](./media/information-barriers/clickthrough-information-barriers.pdf)


Click through an overview of Information Barriers: [PDF](./media/information-barriers/clickthrough-information-barriers.pdf) | [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/Clickthrough-Information-Barriers.pptx)

OLD: Move comment field here

 [![Click-Through for Information Barriers](./media/information-barriers/Clickthrough_InformationBarriers_Thumbnail.png)](./media/information-barriers/Clickthrough_InformationBarriers.pdf)

For the PowerPoint slide of this Click-Through, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/InfoBarriersExample.pptx).

>[!Tip]
>Try this new [Click-Through on information barriers](media/information-barriers/Clickthrough_InformationBarriers.pdf) for a quick overview of the essential facts.
>

--> 


<span data-ttu-id="6cf13-105">Microsoft Cloud Services umfassen leistungsstarke Funktionen für Kommunikation und Zusammenarbeit.</span><span class="sxs-lookup"><span data-stu-id="6cf13-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="6cf13-106">Angenommen, Sie möchten die Kommunikation zwischen zwei Gruppen einschränken, um zu verhindern, dass in Ihrer Organisation ein Interessenkonflikt auftritt.</span><span class="sxs-lookup"><span data-stu-id="6cf13-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="6cf13-107">Oder Sie möchten möglicherweise die Kommunikation zwischen bestimmten Personen innerhalb Ihrer Organisation einschränken, um interne Informationen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6cf13-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="6cf13-108">Microsoft 365 ermöglicht die Kommunikation und Zusammenarbeit zwischen Gruppen und Organisationen, gibt es also eine Möglichkeit, die Kommunikation zwischen bestimmten Benutzergruppen einzuschränken, wenn dies erforderlich ist?</span><span class="sxs-lookup"><span data-stu-id="6cf13-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="6cf13-109">Mit Informationsbarrieren, können Sie!</span><span class="sxs-lookup"><span data-stu-id="6cf13-109">With information barriers, you can!</span></span> 

<span data-ttu-id="6cf13-110">Informationsbarrieren werden jetzt, beginnend mit Microsoft Teams, ausgerollt.</span><span class="sxs-lookup"><span data-stu-id="6cf13-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="6cf13-111">Unter der Voraussetzung, dass Ihr [Abonnement](#required-licenses-and-permissions) Informationsbarrieren enthält, kann ein Compliance-Administrator oder ein Administrator für Informationsbarrieren Richtlinien definieren, um die Kommunikation zwischen Benutzergruppen in Microsoft Teams zu ermöglichen oder zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6cf13-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="6cf13-112">Richtlinien für Informationsbarrieren können für Situationen wie diese verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6cf13-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="6cf13-113">Benutzer in der Day Trader-Gruppe sollten nicht mit dem Marketing Team kommunizieren</span><span class="sxs-lookup"><span data-stu-id="6cf13-113">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="6cf13-114">Finanz Personal, das an vertraulichen Unternehmensinformationen arbeitet, sollte nicht mit bestimmten Gruppen innerhalb Ihrer Organisation kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="6cf13-114">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="6cf13-115">Ein internes Team mit Geschäfts geheimem Material sollte nicht online mit Personen in bestimmten Gruppen innerhalb Ihrer Organisation anrufen oder chatten.</span><span class="sxs-lookup"><span data-stu-id="6cf13-115">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="6cf13-116">Ein Forschungsteam sollte nur online mit einem Produktentwicklungsteam anrufen oder chatten</span><span class="sxs-lookup"><span data-stu-id="6cf13-116">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cf13-117">Informationsbarrieren ***unterstützen nur*** zwei-Wege-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="6cf13-117">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="6cf13-118">Unidirektionale Einschränkungen wie Marketing können mit Day Traders kommunizieren, aber Day Trader können nicht mit Marketing kommunizieren ***wird nicht unterstützt***.</span><span class="sxs-lookup"><span data-stu-id="6cf13-118">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="6cf13-119">Für alle diese Beispielszenarien (und mehr) können Richtlinien für Informationsbarrieren definiert werden, um die Kommunikation in Microsoft Teams zu verhindern oder zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="6cf13-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="6cf13-120">Mithilfe solcher Richtlinien kann verhindert werden, dass Personen Anrufe oder Chats mit Personen durchlaufen, die Sie nicht haben sollten, oder dass Personen nur mit bestimmten Gruppen in Microsoft Teams kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="6cf13-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="6cf13-121">Wenn die Richtlinien für Informationsbarrieren wirksam sind und Benutzer, die von diesen Richtlinien abgedeckt werden, versuchen, mit anderen Personen in Microsoft Teams zu kommunizieren, werden Überprüfungen durchgeführt, um die Kommunikation zu verhindern (oder zulassen) (gemäß den Richtlinien für Informationsbarrieren).</span><span class="sxs-lookup"><span data-stu-id="6cf13-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="6cf13-122">Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Information Barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="6cf13-122">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cf13-123">Derzeit gelten Informationsbarrieren nicht für e-Mail-Kommunikationen oder für die Dateifreigabe über SharePoint Online oder OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6cf13-123">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="6cf13-124">Darüber hinaus sind Informationsbarrieren unabhängig von [Compliance-Grenzen](set-up-compliance-boundaries.md).</span><span class="sxs-lookup"><span data-stu-id="6cf13-124">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="6cf13-125">Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, müssen Sie sicherstellen, dass in Ihrer Organisation keine [Exchange-adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="6cf13-125">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="6cf13-126">(Informationsbarrieren basieren auf adressbuchrichtlinien.)</span><span class="sxs-lookup"><span data-stu-id="6cf13-126">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="6cf13-127">Was geschieht mit Informationsbarrieren?</span><span class="sxs-lookup"><span data-stu-id="6cf13-127">What happens with information barriers</span></span>

<span data-ttu-id="6cf13-128">Wenn Richtlinien für Informationsbarrieren vorhanden sind, können Personen, die nicht mit anderen bestimmten Benutzern kommunizieren sollten, diese Benutzer nicht finden, auswählen, chatten oder anrufen.</span><span class="sxs-lookup"><span data-stu-id="6cf13-128">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="6cf13-129">Mit Informationsbarrieren sind Überprüfungen vorhanden, um eine unbefugte Kommunikation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6cf13-129">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="6cf13-130">Anfänglich gelten Informationsbarrieren nur für Chats und Kanäle von Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6cf13-130">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="6cf13-131">In Microsoft Teams bestimmen und verhindern Richtlinien für Informationsbarrieren die folgenden Arten von nicht autorisierter Kommunikation:</span><span class="sxs-lookup"><span data-stu-id="6cf13-131">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="6cf13-132">Suchen nach einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="6cf13-132">Searching for a user</span></span>
- <span data-ttu-id="6cf13-133">Hinzufügen eines Mitglieds zu einem Team</span><span class="sxs-lookup"><span data-stu-id="6cf13-133">Adding a member to a team</span></span>
- <span data-ttu-id="6cf13-134">Starten einer Chatsitzung mit einer Person</span><span class="sxs-lookup"><span data-stu-id="6cf13-134">Starting a chat session with someone</span></span>
- <span data-ttu-id="6cf13-135">Starten eines Gruppenchats</span><span class="sxs-lookup"><span data-stu-id="6cf13-135">Starting a group chat</span></span>
- <span data-ttu-id="6cf13-136">Einladen von Personen zum teilnehmen an einer Besprechung</span><span class="sxs-lookup"><span data-stu-id="6cf13-136">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="6cf13-137">Freigeben eines Bildschirms</span><span class="sxs-lookup"><span data-stu-id="6cf13-137">Sharing a screen</span></span>
- <span data-ttu-id="6cf13-138">Platzieren eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="6cf13-138">Placing a call</span></span> 

<span data-ttu-id="6cf13-139">Wenn die beteiligten Personen in eine Informations Sperrrichtlinie einbezogen werden, um die Aktivität zu verhindern, können Sie nicht fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6cf13-139">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="6cf13-140">Darüber hinaus kann potenziell jeder, der in eine Richtlinie für Informationsbarrieren eingeschlossen ist, für die Kommunikation mit anderen Personen in Microsoft Teams gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="6cf13-140">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="6cf13-141">Wenn Personen, die von Richtlinien für Informationsbarrieren betroffen sind, Teil desselben Teams oder Gruppenchats sind, werden Sie möglicherweise aus diesen Chatsitzungen entfernt, und die weitere Kommunikation mit der Gruppe ist möglicherweise nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="6cf13-141">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="6cf13-142">Weitere Informationen zur Benutzererfahrung mit Informationsbarrieren finden Sie unter [Information Barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="6cf13-142">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="6cf13-143">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6cf13-143">Required licenses and permissions</span></span>

<span data-ttu-id="6cf13-144">Informationsbarrieren werden jetzt ausgerollt und in Abonnements eingeschlossen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="6cf13-144">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="6cf13-145">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6cf13-145">Microsoft 365 E5</span></span>
- <span data-ttu-id="6cf13-146">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="6cf13-146">Office 365 E5</span></span>
- <span data-ttu-id="6cf13-147">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="6cf13-147">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="6cf13-148">Microsoft 365 E5 – Informationsschutz und Compliance</span><span class="sxs-lookup"><span data-stu-id="6cf13-148">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="6cf13-149">Weitere Informationen finden Sie unter [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span><span class="sxs-lookup"><span data-stu-id="6cf13-149">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="6cf13-150">Um [Richtlinien für Informationsbarrieren zu definieren oder zu bearbeiten](information-barriers-policies.md), muss Ihnen eine der folgenden Rollen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="6cf13-150">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="6cf13-151">Microsoft 365 globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6cf13-151">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="6cf13-152">Office 365 globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6cf13-152">Office 365 global administrator</span></span>
- <span data-ttu-id="6cf13-153">Complianceadministrator</span><span class="sxs-lookup"><span data-stu-id="6cf13-153">Compliance administrator</span></span>
- <span data-ttu-id="6cf13-154">IB-Konformitätsverwaltung (Dies ist eine neue Rolle!)</span><span class="sxs-lookup"><span data-stu-id="6cf13-154">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="6cf13-155">(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span><span class="sxs-lookup"><span data-stu-id="6cf13-155">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="6cf13-156">Sie müssen mit PowerShell-Cmdlets vertraut sein, um Richtlinien für Informationsbarrieren zu definieren, zu validieren oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6cf13-156">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="6cf13-157">Obwohl wir einige Beispiele für PowerShell-Cmdlets im [How-to-Artikel](information-barriers-policies.md)bereitstellen, müssen Sie zusätzliche Details wie Parameter für Ihre Organisation kennen.</span><span class="sxs-lookup"><span data-stu-id="6cf13-157">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6cf13-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6cf13-158">Next steps</span></span>

- [<span data-ttu-id="6cf13-159">Weitere Informationen zu Informationsbarrieren in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cf13-159">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="6cf13-160">Siehe die Attribute, die für Richtlinien für Informationsbarrieren verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6cf13-160">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="6cf13-161">Definieren von Richtlinien für Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="6cf13-161">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="6cf13-162">Bearbeiten (oder entfernen) von Richtlinien für Informationsbarrieren</span><span class="sxs-lookup"><span data-stu-id="6cf13-162">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 
