---
title: Referenz zu konfigurierbaren Einstellungen für Microsoft Managed Desktop
description: Festlegen von Kategorien für konfigurierbare Einstellungen in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051096"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="14f75-104">Referenz zu konfigurierbaren Einstellungen – Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="14f75-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="14f75-p101">In diesem Thema werden die Einstellungskategorien aufgelistet, die Kunden mit Microsoft Managed Desktop konfigurieren können. Jede Einstellungskategorie enthält Informationen zu Anforderungen, bewährten Methoden und zum Anpassen der Einstellungskategorie.</span><span class="sxs-lookup"><span data-stu-id="14f75-p101">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop. Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="14f75-107">Hintergrundbild des Desktops</span><span class="sxs-lookup"><span data-stu-id="14f75-107">Desktop background picture</span></span>
<span data-ttu-id="14f75-p102">Sie können das Desktophintergrundbild für Microsoft Managed Desktop-Geräte in Ihrer Organisation anpassen. Sie können dies verwenden, um eine Unternehmensmarke oder ein Marketing anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="14f75-p102">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization. You might use this to apply a company brand or marketing</span></span> 

### <a name="requirements"></a><span data-ttu-id="14f75-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14f75-110">Requirements</span></span>

<span data-ttu-id="14f75-111">Diese Anforderungen müssen für ein Desktophintergrundbild erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="14f75-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="14f75-112">Bilddateiformat-. jpg, JPEG oder. png</span><span class="sxs-lookup"><span data-stu-id="14f75-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="14f75-113">Dateispeicherort-Host auf einem vertrauenswürdigen HTTPS-Speicherort (Secure HTTP).</span><span class="sxs-lookup"><span data-stu-id="14f75-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="14f75-114">Nicht zulässig – http-und Dateifreigabe Adressen (UNC) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="14f75-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="14f75-115">Anpassen und Bereitstellen des Desktop Hintergrundbilds</span><span class="sxs-lookup"><span data-stu-id="14f75-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="14f75-116">**So fügen Sie ein benutzerdefiniertes Desktophintergrundbild hinzu**</span><span class="sxs-lookup"><span data-stu-id="14f75-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="14f75-117">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="14f75-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="14f75-118">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="14f75-119">Wählen Sie im **konfigurierbaren** Arbeitsbereich **Desktop Hintergrundbild**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="14f75-120">Geben Sie den Speicherort des Bilds ein, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="14f75-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="14f75-121">Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="14f75-121">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="14f75-122">Browser-Startseiten</span><span class="sxs-lookup"><span data-stu-id="14f75-122">Browser start pages</span></span>
<span data-ttu-id="14f75-p103">Browser Startseiten werden in einzelnen Registerkarten geöffnet, wenn Ihre Benutzer Microsoft Edge starten. Wenn Sie Ihren Benutzern das Öffnen einer Reihe von Websites erleichtern möchten, die häufig verwendet werden, fügen Sie eine Browser-Startseite für jede Website hinzu.</span><span class="sxs-lookup"><span data-stu-id="14f75-p103">Browser start pages open in individual tabs when your users start Microsoft Edge. If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="14f75-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14f75-125">Requirements</span></span>

<span data-ttu-id="14f75-p104">Sie müssen den vollqualifizierten Domänennamen (FQDN) für Intranet-oder Internet Websites für die Startseiten des Browsers angeben. Wenn interne Websites konfiguriert sind, können Sie den Benutzern mitteilen, dass der Zugriff auf diese Websites nur zulässig ist, wenn Sie im Büro oder mit einer VPN-Verbindung mit dem internen Netzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="14f75-p104">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages. If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="14f75-128">Anpassen und Bereitstellen von Browser Startseiten</span><span class="sxs-lookup"><span data-stu-id="14f75-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="14f75-129">**So fügen Sie eine Browser-Startseite hinzu**</span><span class="sxs-lookup"><span data-stu-id="14f75-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="14f75-130">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="14f75-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="14f75-131">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="14f75-132">Wählen Sie im **konfigurierbaren** Arbeitsbereich **Browser Startseiten**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="14f75-133">Wählen Sie **Startseite hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="14f75-134">Geben Sie auf der **Seite Browser Start hinzufügen**die URL für die Website ein, die Sie verwenden möchten, und wählen Sie dann **Startseite hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="14f75-135">Wiederholen Sie die Schritte 1-5 für zusätzliche Browser Startseiten.</span><span class="sxs-lookup"><span data-stu-id="14f75-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="14f75-136">Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="14f75-136">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="14f75-137">Speicherort der Website Liste für den Unternehmens Modus</span><span class="sxs-lookup"><span data-stu-id="14f75-137">Enterprise mode site list location</span></span>

<span data-ttu-id="14f75-p105">Wenn Sie bestimmte Websites und apps haben, von denen Sie wissen, dass Sie Kompatibilitätsprobleme mit Microsoft Edge haben, können Sie die Website Liste für den Unternehmens Modus verwenden, damit die Websites automatisch mit Internet Explorer 11 geöffnet werden. Wenn Sie wissen, dass Ihre Intranet-Websites mit Microsoft Edge nicht ordnungsgemäß funktionieren, können Sie auch festlegen, dass alle Intranet-Websites mit Internet Explorer 11 automatisch geöffnet werden. Wenn Sie den Enterprise-Modus verwenden, können Sie Microsoft Edge weiterhin als Standardbrowser verwenden und gleichzeitig sicherstellen, dass Ihre apps weiterhin mit Internet Explorer 11 arbeiten. Weitere Informationen zu Website Listen im Unternehmens Modus finden Sie unter [Enterprise Mode and Enterprise Mode Site lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span><span class="sxs-lookup"><span data-stu-id="14f75-p105">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11. Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11. For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="14f75-142">Sie können einen https://-Standort oder den Speicherort für eine interne Freigabe angeben, auf der Sie Ihre Unternehmens Modus-Website Liste gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="14f75-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="14f75-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14f75-143">Requirements</span></span>

<span data-ttu-id="14f75-144">Diese Anforderungen müssen für die Unternehmens Modus-Website Listendatei erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="14f75-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="14f75-145">Dateiformat-XML-Datei, die [Dateianforderungen](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file) erfüllt</span><span class="sxs-lookup"><span data-stu-id="14f75-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="14f75-146">Dateispeicherort-Host Datei an einem internen HTTPS-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="14f75-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="14f75-147">Nicht zulässig – das Hosten auf einer internen Dateifreigabe, wie *//ShareName*, ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="14f75-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="14f75-148">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="14f75-148">Best practices</span></span>

<span data-ttu-id="14f75-149">Diese bewährten Methoden helfen Kunden bei der Entscheidungsfindung bei der Modernisierung ihrer IT-Infrastruktur:</span><span class="sxs-lookup"><span data-stu-id="14f75-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="14f75-p106">**Wählen Sie eine begrenzte Anzahl von Websites** – Microsoft Managed Desktop verwendet Microsoft Edge als bevorzugten Browser, um die allgemeine Sicherheit für Ihre Organisation zu verbessern und die Benutzerfreundlichkeit zu erhöhen. Die meisten Websites in dieser Liste gelten für Legacy-Web-Apps, die eine ältere Version eines Browsers benötigen, die nicht so viele Sicherheitsfunktionen enthält.</span><span class="sxs-lookup"><span data-stu-id="14f75-p106">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users. Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="14f75-p107">**Betrachten Sie eine Alternative** – erwägen Sie einen anderen Standort oder eine Web-App, für die kein älterer Browser erforderlich ist. Sie sollten auch die Website aktualisieren, damit Sie neuere Browser verwenden kann. Neuere Browser verwenden die neueste Technologie und helfen bei der Verbesserung der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="14f75-p107">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser. Or, consider updating the site so that it can use newer browsers. Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="14f75-155">Anpassen und Bereitstellen des Speicherorts für den Unternehmenswebsite Modus</span><span class="sxs-lookup"><span data-stu-id="14f75-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="14f75-156">**So fügen Sie einen Speicherort für die Unternehmenswebsite Modus-Liste hinzu**</span><span class="sxs-lookup"><span data-stu-id="14f75-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="14f75-157">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="14f75-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="14f75-158">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="14f75-159">Wählen Sie unter **konfigurierbarer** Arbeitsbereich den Standort **Listenspeicherort des Unternehmens Modus**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="14f75-160">Geben Sie den HTTPS-Speicherort für Ihre Website Liste ein.</span><span class="sxs-lookup"><span data-stu-id="14f75-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="14f75-161">Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="14f75-161">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="14f75-162">Vertrauenswürdige Websites</span><span class="sxs-lookup"><span data-stu-id="14f75-162">Trusted sites</span></span>

<span data-ttu-id="14f75-p108">Vertrauenswürdige Websites ermöglichen Ihnen das Anpassen von Sicherheitszonen oder die Verwendung einer Website für verschiedene Websites. Zu den Sicherheitszonen gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="14f75-p108">Trusted sites allow you to customize security zones, or where a site can be used, for different sites. Security zones include:</span></span> 
- <span data-ttu-id="14f75-165">Zone 1 – Zone für lokales Intranet</span><span class="sxs-lookup"><span data-stu-id="14f75-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="14f75-166">Zone 2 – Zone für vertrauenswürdige Sites</span><span class="sxs-lookup"><span data-stu-id="14f75-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="14f75-167">Zone 3 – Internet Zone</span><span class="sxs-lookup"><span data-stu-id="14f75-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="14f75-168">Zone 4 – Zone mit eingeschränkten Websites</span><span class="sxs-lookup"><span data-stu-id="14f75-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="14f75-169">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14f75-169">Requirements</span></span>

<span data-ttu-id="14f75-170">Geben Sie den vollqualifizierten Domänennamen (FQDN) für Intranet-oder Internet Websites für jede vertrauenswürdige Website an.</span><span class="sxs-lookup"><span data-stu-id="14f75-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="14f75-171">Anpassen und Bereitstellen vertrauenswürdiger Websites</span><span class="sxs-lookup"><span data-stu-id="14f75-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="14f75-172">**So fügen Sie eine vertrauenswürdige Website hinzu**</span><span class="sxs-lookup"><span data-stu-id="14f75-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="14f75-173">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="14f75-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="14f75-174">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="14f75-175">Wählen Sie in **konfigurierbarer** Arbeitsbereich **Vertrauenswürdige Sites**aus, und wählen Sie dann **vertrauenswürdige Website hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="14f75-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="14f75-176">Geben Sie auf **vertrauenswürdige Website hinzufügen**die URL ein, wählen Sie eine Sicherheitszone aus, und wählen Sie dann **vertrauenswürdige Website hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="14f75-177">Wiederholen Sie die Schritte 1-4 für jede vertrauenswürdige Website, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="14f75-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="14f75-178">Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="14f75-178">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

<span data-ttu-id="14f75-179">**So entfernen Sie eine vertrauenswürdige Website**</span><span class="sxs-lookup"><span data-stu-id="14f75-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="14f75-180">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="14f75-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="14f75-181">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="14f75-182">Wählen Sie in **konfigurierbarer** Arbeitsbereich **Vertrauenswürdige Sites**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="14f75-183">Wählen Sie die Website aus, die Sie löschen möchten, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="14f75-184">Wiederholen Sie die Schritte 1-4 für jede vertrauenswürdige Website, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="14f75-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="14f75-185">Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="14f75-185">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="proxy"></a><span data-ttu-id="14f75-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="14f75-186">Proxy</span></span>
<span data-ttu-id="14f75-p109">Sie können Netzwerkproxyeinstellungen für Ihre Organisation verwalten. Fügen Sie Ihren Proxy Server und die Nummer der Portierung hinzu, und fügen Sie dann die Proxy Website-Ausnahmen hinzu. Microsoft Managed Desktop enthält eine Reihe von Standardproxy Ausnahmen, die für den Betrieb des Diensts erforderlich sind. Die standardmäßige Ausschlussliste kann nur vom Microsoft Managed Desktop-Dienst geändert werden.  Weitere Informationen finden Sie unter [Netzwerkkonfiguration für Microsoft Managed Desktop](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="14f75-p109">You can manage network proxy settings for your organization. Add your proxy server and port number, and then add your proxy site exceptions. Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate. The default exclusion list may only be modified by the Microsoft Managed Desktop service.  For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="14f75-192">Die Proxy Website-Ausnahmen, die Sie im Microsoft Managed Desktop-Portal hinzufügen, werden den Standardproxy Ausnahmen hinzugefügt, die in Microsoft Managed Desktop Service enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="14f75-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="14f75-p110">Das Aktualisieren der standardmäßigen Proxyausnahmeliste wird immer Vorrang vor Kundenbereitstellungen haben. Dies bedeutet, dass die Bereitstellung von Staging angehalten wird, wenn eine Bereitstellung für die Standardproxy Ausnahmeliste vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="14f75-p110">Updating the default proxy exception list is always prioritized over customer deployments. This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="14f75-195">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14f75-195">Requirements</span></span>

<span data-ttu-id="14f75-196">Diese Anforderungen müssen für Ausnahmen von Proxyservern und Proxy Websites erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="14f75-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="14f75-197">Muss eine gültige Serveradresse und-Nummer sein.</span><span class="sxs-lookup"><span data-stu-id="14f75-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="14f75-198">URLs müssen eine gültige HTTP-Website sein.</span><span class="sxs-lookup"><span data-stu-id="14f75-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="14f75-199">Anpassen und Bereitstellen von Proxys</span><span class="sxs-lookup"><span data-stu-id="14f75-199">Customize and deploy proxies</span></span>

<span data-ttu-id="14f75-200">**So fügen Sie eine einzelne Proxy Standort Ausnahme hinzu**</span><span class="sxs-lookup"><span data-stu-id="14f75-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="14f75-201">Anmelden beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="14f75-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="14f75-202">Wählen Sie unter **Einstellungen**die Option **konfigurierbar**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="14f75-203">Wählen Sie in **konfigurierbarer** Arbeitsbereich **Proxy**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="14f75-204">Geben Sie die **Adresse** und die **Nummer** für den Proxy Server ein, und wählen Sie **Proxyausnahme hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="14f75-205">Geben Sie die URL einer gültigen HTTP-Website ein, und wählen Sie **Proxyausnahme hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="14f75-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="14f75-206">Wiederholen Sie die Schritte 1-5 für jede vertrauenswürdige Website, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="14f75-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="14f75-207">Wählen Sie **bereitstellungSstufe** aus, um die Änderungen zu speichern und auf dem testring bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="14f75-207">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="14f75-208">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="14f75-208">Additional resources</span></span>
- [<span data-ttu-id="14f75-209">Übersicht über konfigurierbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="14f75-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="14f75-210">Bereitstellen von konfigurierbaren Einstellungen</span><span class="sxs-lookup"><span data-stu-id="14f75-210">Deploy configurable settings</span></span>](config-setting-deploy.md)