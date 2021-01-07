---
title: TLS 1.0- und 1.1-Einstellungen für Office 365
description: Beschreibt TLS 1,0 und 1,1 als veraltet für Office 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777057"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="1f57a-103">TLS 1.0- und 1.1-Einstellungen für Office 365</span><span class="sxs-lookup"><span data-stu-id="1f57a-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1f57a-104">Wir haben die Durchsetzung von TLS 1,0 und 1,1 für kommerzielle Kunden aufgrund von COVID-19 vorübergehend angehalten, aber wenn sich die Lieferketten angepasst haben und einige Länder eine Sicherung durchführen, setzen wir die TLS-Erzwingung so um, dass Sie mit dem Oktober 15, 2020 beginnt und die Einführung in den folgenden Wochen und Monaten fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1f57a-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="1f57a-105">Ab dem 31. Oktober 2018 werden die Protokolle Transport Layer Security (TLS) 1,0 und 1,1 für den Office 365 Dienst veraltet.</span><span class="sxs-lookup"><span data-stu-id="1f57a-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="1f57a-106">Der Effekt für Endbenutzer wird voraussichtlich minimal sein.</span><span class="sxs-lookup"><span data-stu-id="1f57a-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="1f57a-107">Diese Änderung wurde seit mehr als zwei Jahren veröffentlicht, und die erste öffentliche Ankündigung erfolgte im Dezember 2017.</span><span class="sxs-lookup"><span data-stu-id="1f57a-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="1f57a-108">Dieser Artikel soll nur die Office 365 lokalen Clients in Bezug auf den Office 365 Dienst abdecken, kann aber auch auf lokale TLS-Probleme mit Office-und Office Online Server/Office-Webanwendungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f57a-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="1f57a-109">Office-und TLS-Übersicht</span><span class="sxs-lookup"><span data-stu-id="1f57a-109">Office and TLS overview</span></span>

<span data-ttu-id="1f57a-110">Der Office-Client verwendet den Windows-Webdienst (WinHTTP), um Datenverkehr über TLS-Protokolle zu senden und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="1f57a-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="1f57a-111">Der Office-Client kann TLS 1,2 verwenden, wenn der Webdienst des lokalen Computers TLS 1,2 verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="1f57a-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="1f57a-112">Alle Office-Clients können TLS-Protokolle verwenden, da TLS-und SSL-Protokolle Teil des Betriebssystems und nicht für den Office-Client spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1f57a-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="1f57a-113">In Windows 8 und höheren Versionen</span><span class="sxs-lookup"><span data-stu-id="1f57a-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="1f57a-114">Standardmäßig sind die Protokolle TLS 1,2 und 1,1 verfügbar, wenn keine Netzwerkgeräte so konfiguriert sind, dass der TLS 1,2-Datenverkehr abgelehnt wird.</span><span class="sxs-lookup"><span data-stu-id="1f57a-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="1f57a-115">Auf Windows 7</span><span class="sxs-lookup"><span data-stu-id="1f57a-115">On Windows 7</span></span>

<span data-ttu-id="1f57a-116">Die Protokolle TLS 1,1 und 1,2 sind ohne das Update der [KB 3140245](https://support.microsoft.com/help/3140245) nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1f57a-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="1f57a-117">Das Update behebt dieses Problem und fügt den folgenden Registrierungsunterschlüssel hinzu:</span><span class="sxs-lookup"><span data-stu-id="1f57a-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="1f57a-118">Windows 7 Benutzer, die dieses Update nicht haben, sind am 31. Oktober 2018 betroffen.</span><span class="sxs-lookup"><span data-stu-id="1f57a-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="1f57a-119">[KB 3140245](https://support.microsoft.com/help/3140245) enthält Details zum Ändern der WinHTTP-Einstellungen zur Aktivierung von TLS-Protokollen.</span><span class="sxs-lookup"><span data-stu-id="1f57a-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="1f57a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f57a-120">More information</span></span>

<span data-ttu-id="1f57a-121">Der Wert des Registrierungsschlüssels **DefaultSecureProtocols** , den der KB-Artikel beschreibt, bestimmt, welche Netzwerkprotokolle verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="1f57a-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="1f57a-122">DefaultSecureProtocols-Wert</span><span class="sxs-lookup"><span data-stu-id="1f57a-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="1f57a-123">Protokoll aktiviert</span><span class="sxs-lookup"><span data-stu-id="1f57a-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="1f57a-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="1f57a-124">0x00000008</span></span>|<span data-ttu-id="1f57a-125">SSL 2.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="1f57a-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="1f57a-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="1f57a-126">0x00000020</span></span>|<span data-ttu-id="1f57a-127">SSL 3.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="1f57a-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="1f57a-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="1f57a-128">0x00000080</span></span>|<span data-ttu-id="1f57a-129">TLS 1.0 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="1f57a-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="1f57a-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="1f57a-130">0x00000200</span></span>|<span data-ttu-id="1f57a-131">TLS 1.1 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="1f57a-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="1f57a-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1f57a-132">0x00000800</span></span>|<span data-ttu-id="1f57a-133">TLS 1.2 standardmäßig aktivieren</span><span class="sxs-lookup"><span data-stu-id="1f57a-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="1f57a-134">Office-Clients und TLS-Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="1f57a-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="1f57a-135">Sie können sich auf [KB 4057306 Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="1f57a-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="1f57a-136">Dies ist ein allgemeiner Artikel für IT-Administratoren und die offizielle Dokumentation zur TLS 1,2-Änderung.</span><span class="sxs-lookup"><span data-stu-id="1f57a-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="1f57a-137">In der folgenden Tabelle sind die entsprechenden Registrierungsschlüsselwerte in Office 365 Clients nach dem 31. Oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="1f57a-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="1f57a-138">Aktivierte Protokolle für Office 365 Dienst nach dem 31. Oktober 2018</span><span class="sxs-lookup"><span data-stu-id="1f57a-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="1f57a-139">Hexadezimalwert</span><span class="sxs-lookup"><span data-stu-id="1f57a-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="1f57a-140">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1f57a-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="1f57a-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="1f57a-141">0x00000A80</span></span>|
|<span data-ttu-id="1f57a-142">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1f57a-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="1f57a-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="1f57a-143">0x00000A00</span></span>|
|<span data-ttu-id="1f57a-144">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1f57a-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="1f57a-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="1f57a-145">0x00000880</span></span>|
|<span data-ttu-id="1f57a-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="1f57a-146">TLS 1.2</span></span>|<span data-ttu-id="1f57a-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1f57a-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="1f57a-148">Es wird nicht empfohlen, die SSL 2,0-und 3,0-Protokolle zu verwenden, die auch mithilfe des **DefaultSecureProtocols** -Schlüssels festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="1f57a-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="1f57a-149">SSL 2,0 und 3,0 werden als veraltete Protokolle betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1f57a-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="1f57a-150">Die bewährte Methode besteht darin, die Verwendung von SSL 2,0 und SSL 3,0 zu beenden, obwohl die Entscheidung dafür letztlich davon abhängt, was ihren Produktanforderungen am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="1f57a-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="1f57a-151">Weitere Informationen zu Sicherheitsanfälligkeiten in SSL 3,0 finden Sie unter [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="1f57a-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="1f57a-152">Sie können den standardmäßigen Windows-Rechner im Programmiermodus verwenden, um dieselben Referenz Registrierungsschlüsselwerte einzurichten.</span><span class="sxs-lookup"><span data-stu-id="1f57a-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="1f57a-153">Weitere Informationen finden Sie unter [KB 3140245 Update to enable TLS 1,1 and TLS 1,2 als Standard Secure Protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="1f57a-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="1f57a-154">Unabhängig davon, ob das Windows 7 Update ([KB 3140245](https://support.microsoft.com/help/3140245)) installiert ist oder nicht, ist der DefaultSecureProtocols-Registrierungsunterschlüssel nicht vorhanden und muss manuell oder über ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1f57a-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="1f57a-155">Das heißt, es sei denn, Sie müssen anpassen, welche sicheren Protokolle aktiviert oder eingeschränkt sind, dieser Schlüssel ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f57a-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="1f57a-156">Sie benötigen nur das Update Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="1f57a-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
