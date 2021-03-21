---
title: Deaktivieren von TLS 1.0 und 1.1 für Microsoft 365
description: Beschreibt die Veraltetheit und Deaktivierung von TLS 1.0 und 1.1 für Microsoft 365.
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
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919301"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="3aec3-103">Deaktivieren von TLS 1.0 und 1.1 für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3aec3-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3aec3-104">Wir haben die Deaktivierung von TLS 1.0 und 1.1 für kommerzielle Kunden aufgrund von COVID-19 vorübergehend angehalten.</span><span class="sxs-lookup"><span data-stu-id="3aec3-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="3aec3-105">Da lieferketten angepasst wurden und bestimmte Länder eine Back-up-Version öffnen, haben wir das TLS 1.2-Einführungsrollout am 15. Oktober 2020 neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="3aec3-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="3aec3-106">Das Rollout wird in den folgenden Wochen und Monaten fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="3aec3-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="3aec3-107">Ab dem 31. Oktober 2018 sind die Protokolle Transport Layer Security (TLS) 1.0 und 1.1 für den Microsoft 365-Dienst veraltet.</span><span class="sxs-lookup"><span data-stu-id="3aec3-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="3aec3-108">Der Effekt für Endbenutzer ist minimal.</span><span class="sxs-lookup"><span data-stu-id="3aec3-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="3aec3-109">Diese Änderung wurde seit mehr als zwei Jahren veröffentlicht, mit der ersten öffentlichen Ankündigung im Dezember 2017.</span><span class="sxs-lookup"><span data-stu-id="3aec3-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="3aec3-110">Dieser Artikel soll nur den lokalen Office 365-Client in Bezug auf den Office 365-Dienst abdecken, kann aber auch auf lokale TLS-Probleme mit Office und Office Online Server/Office Web Apps angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3aec3-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="3aec3-111">Für SharePoint und OneDrive müssen Sie .NET aktualisieren und konfigurieren, um TLS 1.2 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3aec3-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="3aec3-112">Weitere Informationen finden Sie unter [Aktivieren von TLS 1.2 auf Clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span><span class="sxs-lookup"><span data-stu-id="3aec3-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="3aec3-113">Übersicht über Office 365 und TLS</span><span class="sxs-lookup"><span data-stu-id="3aec3-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="3aec3-114">Der Office-Client verwendet den Windows-Webdienst (WINHTTP) zum Senden und Empfangen von Datenverkehr über TLS-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="3aec3-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="3aec3-115">Der Office-Client kann TLS 1.2 verwenden, wenn der Webdienst des lokalen Computers TLS 1.2 verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="3aec3-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="3aec3-116">Alle Office-Clients können TLS-Protokolle verwenden, da TLS- und SSL-Protokolle Teil des Betriebssystems und nicht spezifisch für den Office-Client sind.</span><span class="sxs-lookup"><span data-stu-id="3aec3-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="3aec3-117">On Windows 8 and later versions</span><span class="sxs-lookup"><span data-stu-id="3aec3-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="3aec3-118">Standardmäßig sind die Protokolle TLS 1.2 und 1.1 verfügbar, wenn keine Netzwerkgeräte für die Ablehnung von TLS 1.2-Datenverkehr konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="3aec3-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="3aec3-119">Unter Windows 7</span><span class="sxs-lookup"><span data-stu-id="3aec3-119">On Windows 7</span></span>

<span data-ttu-id="3aec3-120">TLS 1.1- und 1.2-Protokolle sind ohne das [Update KB 3140245 nicht verfügbar.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="3aec3-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="3aec3-121">Das Update behebt dieses Problem und fügt den folgenden Registrierungsunterschlüssel hinzu:</span><span class="sxs-lookup"><span data-stu-id="3aec3-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="3aec3-122">Windows 7-Benutzer, die nicht über dieses Update verfügen, sind ab dem 31. Oktober 2018 betroffen.</span><span class="sxs-lookup"><span data-stu-id="3aec3-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="3aec3-123">[KB 3140245](https://support.microsoft.com/help/3140245) enthält Details zum Ändern von WINHTTP-Einstellungen zur Aktivierung von TLS-Protokollen.</span><span class="sxs-lookup"><span data-stu-id="3aec3-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="3aec3-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aec3-124">More information</span></span>

<span data-ttu-id="3aec3-125">Der Im KB-Artikel beschriebene Wert des **DefaultSecureProtocols-Registrierungsschlüssels** bestimmt, welche Netzwerkprotokolle verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="3aec3-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="3aec3-126">DefaultSecureProtocols-Wert</span><span class="sxs-lookup"><span data-stu-id="3aec3-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="3aec3-127">Protokoll aktiviert</span><span class="sxs-lookup"><span data-stu-id="3aec3-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="3aec3-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="3aec3-128">0x00000008</span></span>|<span data-ttu-id="3aec3-129">SSL 2.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="3aec3-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="3aec3-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="3aec3-130">0x00000020</span></span>|<span data-ttu-id="3aec3-131">SSL 3.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="3aec3-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="3aec3-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="3aec3-132">0x00000080</span></span>|<span data-ttu-id="3aec3-133">TLS 1.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="3aec3-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="3aec3-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="3aec3-134">0x00000200</span></span>|<span data-ttu-id="3aec3-135">TLS 1.1 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="3aec3-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="3aec3-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="3aec3-136">0x00000800</span></span>|<span data-ttu-id="3aec3-137">TLS 1.2 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="3aec3-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="3aec3-138">Office-Clients und TLS-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="3aec3-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="3aec3-139">Sie können sich auf KB 4057306 Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365 beziehen.](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="3aec3-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="3aec3-140">Dies ist ein allgemeiner Artikel für IT-Administratoren, und es handelt sich um eine offizielle Dokumentation zur TLS 1.2-Änderung.</span><span class="sxs-lookup"><span data-stu-id="3aec3-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="3aec3-141">In der folgenden Tabelle sind die entsprechenden Registrierungsschlüsselwerte in Office 365-Clients nach dem 31. Oktober 2018 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3aec3-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="3aec3-142">Aktivierte Protokolle für Office 365-Dienst nach dem 31. Oktober 2018</span><span class="sxs-lookup"><span data-stu-id="3aec3-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="3aec3-143">Hexadezimalwert</span><span class="sxs-lookup"><span data-stu-id="3aec3-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="3aec3-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="3aec3-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="3aec3-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="3aec3-145">0x00000A80</span></span>|
|<span data-ttu-id="3aec3-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="3aec3-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="3aec3-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="3aec3-147">0x00000A00</span></span>|
|<span data-ttu-id="3aec3-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="3aec3-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="3aec3-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="3aec3-149">0x00000880</span></span>|
|<span data-ttu-id="3aec3-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="3aec3-150">TLS 1.2</span></span>|<span data-ttu-id="3aec3-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="3aec3-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="3aec3-152">Verwenden Sie nicht die PROTOKOLLE SSL 2.0 und 3.0, die auch mithilfe des **DefaultSecureProtocols-Schlüssels festgelegt werden** können.</span><span class="sxs-lookup"><span data-stu-id="3aec3-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="3aec3-153">SSL 2.0 und 3.0 gelten als veraltete und unsichere Protokolle.</span><span class="sxs-lookup"><span data-stu-id="3aec3-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="3aec3-154">Die bewährte Methode ist, die Verwendung von SSL 2.0 und SSL 3.0 zu beenden, obwohl die Entscheidung dafür letztendlich davon abhängt, was Ihre Produktanforderungen am besten erfüllt.</span><span class="sxs-lookup"><span data-stu-id="3aec3-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="3aec3-155">Weitere Informationen zu SSL 3.0-Sicherheitsrisiken finden Sie unter [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="3aec3-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="3aec3-156">Sie können den Standardmäßigen Windows-Rechner im Programmiermodus verwenden, um dieselben Referenzregistrierungsschlüsselwerte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3aec3-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="3aec3-157">Weitere Informationen finden Sie unter [KB 3140245 Update, um TLS 1.1 und TLS 1.2](https://support.microsoft.com/help/3140245)als sichere Standardprotokolle in WinHTTP in Windows zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3aec3-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="3aec3-158">Unabhängig davon, ob das Windows 7-Update ([KB 3140245](https://support.microsoft.com/help/3140245)) installiert ist oder nicht, ist der Registrierungsunterschlüssel DefaultSecureProtocols nicht vorhanden und muss manuell oder über ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3aec3-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="3aec3-159">Das heißt, wenn Sie nicht anpassen müssen, welche sicheren Protokolle aktiviert oder eingeschränkt sind, ist dieser Schlüssel nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3aec3-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="3aec3-160">Sie benötigen nur das Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) Update.</span><span class="sxs-lookup"><span data-stu-id="3aec3-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="3aec3-161">Aktualisieren und Konfigurieren der .NET Framework zur Unterstützung von TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="3aec3-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="3aec3-162">Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aec3-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="3aec3-163">.NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3aec3-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="3aec3-164">Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter [Aktivieren von Transport Layer Security (TLS) 1.2 auf Clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span><span class="sxs-lookup"><span data-stu-id="3aec3-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="3aec3-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aec3-165">More information</span></span>

<span data-ttu-id="3aec3-166">Weitere Informationen finden Sie unter [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="3aec3-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>