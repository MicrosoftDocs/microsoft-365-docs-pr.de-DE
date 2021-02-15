---
title: Deaktivieren von TLS 1.0 und 1.1 für Microsoft 365
description: Beschreibt die Einstellung und Deaktivierung von TLS 1.0 und 1.1 für Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233097"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="9f7dd-103">Deaktivieren von TLS 1.0 und 1.1 für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9f7dd-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f7dd-104">Wir haben die Deaktivierung von TLS 1.0 und 1.1 für kommerzielle Kunden aufgrund von COVID-19 vorübergehend angehalten.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="9f7dd-105">Da sich die Lieferketten angepasst haben und bestimmte Länder wieder geöffnet werden, haben wir die Einführung der TLS 1.2-Erzwingung am 15. Oktober 2020 neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="9f7dd-106">Die Einführung wird in den folgenden Wochen und Monaten fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="9f7dd-107">Seit dem 31. Oktober 2018 sind die Protokolle TLS 1.0 und 1.1 für den Microsoft 365-Dienst veraltet.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="9f7dd-108">Die Auswirkungen für Endbenutzer sind minimal.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="9f7dd-109">Diese Änderung wurde über zwei Jahre lang veröffentlicht, mit der ersten öffentlichen Ankündigung im Dezember 2017.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="9f7dd-110">Dieser Artikel soll nur den lokalen Office 365-Client in Bezug auf den Office 365-Dienst abdecken, kann aber auch auf lokale TLS-Probleme mit Office und Office Online Server/Office Web Apps angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="9f7dd-111">Für SharePoint und OneDrive müssen Sie .NET aktualisieren und konfigurieren, um TLS 1.2 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="9f7dd-112">Weitere Informationen finden Sie unter [Aktivieren von TLS 1.2 auf Clients.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="9f7dd-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="9f7dd-113">Übersicht über Office 365 und TLS</span><span class="sxs-lookup"><span data-stu-id="9f7dd-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="9f7dd-114">Der Office-Client verwendet den Windows-Webdienst (WINHTTP) zum Senden und Empfangen von Datenverkehr über TLS-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="9f7dd-115">Der Office-Client kann TLS 1.2 verwenden, wenn der Webdienst des lokalen Computers TLS 1.2 verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="9f7dd-116">Alle Office-Clients können TLS-Protokolle verwenden, da TLS- und SSL-Protokolle Teil des Betriebssystems und nicht spezifisch für den Office-Client sind.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="9f7dd-117">On Windows 8 and later versions</span><span class="sxs-lookup"><span data-stu-id="9f7dd-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="9f7dd-118">Standardmäßig sind die Protokolle TLS 1.2 und 1.1 verfügbar, wenn keine Netzwerkgeräte für die Ablehnung von TLS 1.2-Datenverkehr konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="9f7dd-119">Unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="9f7dd-119">On Windows 7</span></span>

<span data-ttu-id="9f7dd-120">TLS 1.1- und 1.2-Protokolle sind ohne das [Update KB 3140245 nicht](https://support.microsoft.com/help/3140245) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="9f7dd-121">Das Update behebt dieses Problem und fügt den folgenden Registrierungsunterschlüssel hinzu:</span><span class="sxs-lookup"><span data-stu-id="9f7dd-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="9f7dd-122">Windows 7-Benutzer, die nicht über dieses Update verfügen, sind ab dem 31. Oktober 2018 betroffen.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="9f7dd-123">[KB 3140245](https://support.microsoft.com/help/3140245) enthält Details zum Ändern der WINHTTP-Einstellungen zum Aktivieren von TLS-Protokollen.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="9f7dd-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f7dd-124">More information</span></span>

<span data-ttu-id="9f7dd-125">Der im Kb-Artikel beschriebene Wert des **Registrierungsschlüssels "DefaultSecureProtocols"** bestimmt, welche Netzwerkprotokolle verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="9f7dd-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="9f7dd-126">DefaultSecureProtocols-Wert</span><span class="sxs-lookup"><span data-stu-id="9f7dd-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="9f7dd-127">Protokoll aktiviert</span><span class="sxs-lookup"><span data-stu-id="9f7dd-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="9f7dd-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="9f7dd-128">0x00000008</span></span>|<span data-ttu-id="9f7dd-129">SSL 2.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f7dd-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="9f7dd-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="9f7dd-130">0x00000020</span></span>|<span data-ttu-id="9f7dd-131">SSL 3.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f7dd-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="9f7dd-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="9f7dd-132">0x00000080</span></span>|<span data-ttu-id="9f7dd-133">TLS 1.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f7dd-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="9f7dd-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="9f7dd-134">0x00000200</span></span>|<span data-ttu-id="9f7dd-135">TLS 1.1 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f7dd-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="9f7dd-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="9f7dd-136">0x00000800</span></span>|<span data-ttu-id="9f7dd-137">TLS 1.2 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="9f7dd-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="9f7dd-138">Office-Clients und -TLS-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="9f7dd-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="9f7dd-139">Informationen zur Vorbereitung auf die obligatorische Verwendung von [TLS 1.2 in Office 365 finden Sie unter KB 4057306.](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="9f7dd-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="9f7dd-140">Dies ist ein allgemeiner Artikel für IT-Administratoren, und es handelt sich um eine offizielle Dokumentation zur TLS 1.2-Änderung.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="9f7dd-141">In der folgenden Tabelle sind die entsprechenden Registrierungsschlüsselwerte in Office 365-Clients nach dem 31. Oktober 2018 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="9f7dd-142">Aktivierte Protokolle für den Office 365-Dienst nach dem 31. Oktober 2018</span><span class="sxs-lookup"><span data-stu-id="9f7dd-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="9f7dd-143">Hexadezimaler Wert</span><span class="sxs-lookup"><span data-stu-id="9f7dd-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="9f7dd-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="9f7dd-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="9f7dd-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="9f7dd-145">0x00000A80</span></span>|
|<span data-ttu-id="9f7dd-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="9f7dd-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="9f7dd-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="9f7dd-147">0x00000A00</span></span>|
|<span data-ttu-id="9f7dd-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="9f7dd-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="9f7dd-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="9f7dd-149">0x00000880</span></span>|
|<span data-ttu-id="9f7dd-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="9f7dd-150">TLS 1.2</span></span>|<span data-ttu-id="9f7dd-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="9f7dd-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="9f7dd-152">Verwenden Sie nicht die SSL 2.0- und 3.0-Protokolle, die auch mit dem Schlüssel **"DefaultSecureProtocols" festgelegt werden** können.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="9f7dd-153">SSL 2.0 und 3.0 gelten als veraltete und unsichere Protokolle.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="9f7dd-154">Die bewährte Methode besteht im Beenden der Verwendung von SSL 2.0 und SSL 3.0, obwohl die Entscheidung dafür letztlich davon abhängt, was Ihren Produktanforderungen am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="9f7dd-155">Weitere Informationen zu SSL 3.0-Sicherheitsrisiken finden Sie unter [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="9f7dd-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="9f7dd-156">Sie können den standardmäßigen Windows-Rechner im Programmiermodus verwenden, um die gleichen Werte für den Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="9f7dd-157">Weitere Informationen finden Sie unter [KB 3140245 Update, um TLS 1.1 und TLS 1.2](https://support.microsoft.com/help/3140245)als sichere Standardprotokolle in WinHTTP in Windows zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="9f7dd-158">Unabhängig davon, ob das Windows 7-Update ([KB 3140245](https://support.microsoft.com/help/3140245)) installiert ist oder nicht, ist der Registrierungsunterschlüssel "DefaultSecureProtocols" nicht vorhanden und muss manuell oder über ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="9f7dd-159">Das heißt, wenn Sie nicht anpassen müssen, welche sicheren Protokolle aktiviert oder eingeschränkt sind, ist dieser Schlüssel nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="9f7dd-160">Sie benötigen nur das Update für Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="9f7dd-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="9f7dd-161">Aktualisieren und Konfigurieren von .NET Framework zur Unterstützung von TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="9f7dd-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="9f7dd-162">Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="9f7dd-163">.NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="9f7dd-164">Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter Aktivieren [von TLS 1.2 (Transport Layer Security)](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)auf Clients.</span><span class="sxs-lookup"><span data-stu-id="9f7dd-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="9f7dd-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f7dd-165">More information</span></span>

<span data-ttu-id="9f7dd-166">Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="9f7dd-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
