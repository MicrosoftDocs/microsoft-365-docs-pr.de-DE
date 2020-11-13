---
title: Zusammenarbeit mit Personen außerhalb Ihrer Organisation
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365-apps wie Teams, OneDrive und SharePoint für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation konfigurieren.
ms.openlocfilehash: 60789041abca98769fa25e2f299ee2d7eebe0726
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029981"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="a7f27-103">Zusammenarbeit mit Personen außerhalb Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a7f27-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="a7f27-104">Die Funktionen zur externen Freigabe in Microsoft 365 bieten Personen in Ihrer Organisation die Möglichkeit, mit Partnern, Lieferanten, Kunden und anderen Personen zusammenzuarbeiten, die kein Konto in Ihrem Verzeichnis haben.</span><span class="sxs-lookup"><span data-stu-id="a7f27-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="a7f27-105">Sie können ganze Teams oder Standorte für Personen außerhalb Ihrer Organisation oder nur für einzelne Dateien freigeben.</span><span class="sxs-lookup"><span data-stu-id="a7f27-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="a7f27-106">Die Zusammenarbeit mit Personen außerhalb Ihrer Organisation besteht aus zwei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="a7f27-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="a7f27-107">**Freigabe aktivieren** : Konfigurieren Sie die Freigabe Steuerelemente in Azure Active Directory, Microsoft Teams, Microsoft 365-Gruppen und SharePoint, um die für Ihre Organisation gewünschte Freigabeebene zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a7f27-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="a7f27-108">**Aktivieren zusätzlicher Sicherheit** : während die grundlegenden Freigabefunktionen so konfiguriert werden können, dass Personen außerhalb Ihrer Organisation authentifiziert werden müssen, bietet Microsoft 365 zahlreiche zusätzliche Sicherheits-und Compliance-Funktionen, die Ihnen dabei helfen, Ihre Daten zu schützen und ihre Steuerungsrichtlinien beizubehalten, während Sie extern freigeben.</span><span class="sxs-lookup"><span data-stu-id="a7f27-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="a7f27-109">Freigabe aktivieren</span><span class="sxs-lookup"><span data-stu-id="a7f27-109">Enable sharing</span></span>

<span data-ttu-id="a7f27-110">Standardmäßig ist in Microsoft 365 die Freigabe für Personen außerhalb Ihrer Organisation für SharePoint und OneDrive aktiviert, aber für Teams deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7f27-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="a7f27-111">Viele SharePoint-und OneDrive-Szenarien für externe Freigaben funktionieren ohne weitere Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a7f27-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="a7f27-112">Wählen Sie eine der folgenden Optionen aus, um die Einstellungen für ein von Ihnen verwendetes Szenario zu bestätigen oder ein neues zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a7f27-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="a7f27-113">[Zusammenarbeit an Dokumenten](collaborate-on-documents.md) -erfahren Sie, wie Sie Microsoft 365 so konfigurieren, dass die Freigabe und Zusammenarbeit mit Personen außerhalb Ihrer Organisation (sowohl Gäste als auch nicht authentifizierte Benutzer) in Dateien und Ordnern zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="a7f27-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="a7f27-114">[Zusammenarbeiten an einer Website](collaborate-in-site.md) – erfahren Sie, wie Sie Microsoft 365 so konfigurieren, dass SharePoint-Websites für Gäste freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a7f27-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="a7f27-115">[Zusammenarbeit als Team](collaborate-as-team.md) -erfahren Sie, wie Sie Microsoft 365 so konfigurieren, dass die Zusammenarbeit von Gästen in Teams ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="a7f27-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="a7f27-116">Eine umfassende Übersicht über die in Microsoft 365 verfügbaren Gäste Freigabeeinstellungen finden Sie unter [Microsoft 365 Guest Sharing Settings Reference](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a7f27-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="a7f27-117">Aktivieren zusätzlicher Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a7f27-117">Enable additional security</span></span>

<span data-ttu-id="a7f27-118">Nachdem Sie das Szenario, das Sie für die Freigabe für Personen außerhalb Ihrer Organisation verwenden möchten, aktiviert haben, sollten Sie zusätzliche Schutzvorkehrungen zum Schutz Ihrer Inhalte vor versehentlicher oder vorsätzlicher ungeeigneter Freigaben ergreifen.</span><span class="sxs-lookup"><span data-stu-id="a7f27-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="a7f27-119">[Bewährte Methoden für die Freigabe von Dateien und Ordnern mit nicht authentifizierten Benutzern](best-practices-anonymous-sharing.md) – erfahren Sie mehr über bewährte Methoden für die Freigabe mit nicht authentifizierten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="a7f27-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="a7f27-120">[Begrenzen Sie die unbeabsichtigte Belichtung](share-limit-accidental-exposure.md) – erfahren Sie, wie Sie die Wahrscheinlichkeit verringern, dass vertrauliche Inhalte versehentlich mit Personen außerhalb Ihrer Organisation geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="a7f27-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="a7f27-121">[Erstellen Sie eine sichere Gast Freigabe Umgebung](create-secure-guest-sharing-environment.md) -erfahren Sie mehr über die in Microsoft 365 bereitgestellten Tools, um sicherzustellen, dass die Freigabe für Personen außerhalb Ihrer Organisation auf sichere und sichere Weise erfolgt und ihre Steuerungsanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a7f27-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="a7f27-122">Zusammenarbeit mit Partnerunternehmen</span><span class="sxs-lookup"><span data-stu-id="a7f27-122">Collaborate with partner companies</span></span>

<span data-ttu-id="a7f27-123">Wenn Sie an einem großen Projekt arbeiten, das viele Gäste aus einer anderen Organisation umfasst, oder wenn Sie eine ständige Lieferantenbeziehung haben, in der sich Gäste häufig ändern, können Sie die Verwaltung von Berechtigungen in Azure Active Directory verwenden, um die Verwaltung von Gast zu vereinfachen und das Partnerunternehmen in dieser Verantwortung zu teilen.</span><span class="sxs-lookup"><span data-stu-id="a7f27-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="a7f27-124">Weitere Informationen finden Sie unter [Erstellen eines B2B-Extranets mit verwalteten Gästen](b2b-extranet.md) .</span><span class="sxs-lookup"><span data-stu-id="a7f27-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="a7f27-125">Freigabe einschränken</span><span class="sxs-lookup"><span data-stu-id="a7f27-125">Limit sharing</span></span>

<span data-ttu-id="a7f27-126">Wenn einige der Freigabefeatures in Microsoft 365 mit ihren Steuerungsrichtlinien in Konflikt stehen, finden Sie unter [Limit Sharing in Microsoft 365](microsoft-365-limit-sharing.md) Informationen zu Optionen zum Einschränken der Freigabe.</span><span class="sxs-lookup"><span data-stu-id="a7f27-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7f27-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a7f27-127">Related topics</span></span>

[<span data-ttu-id="a7f27-128">Einführung in die Zusammenarbeit in Dateien in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7f27-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="a7f27-129">Planen der Zusammenarbeit von Dateien in SharePoint mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7f27-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
