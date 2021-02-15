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
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Deaktivieren von TLS 1.0 und 1.1 für Microsoft 365

> [!IMPORTANT]
> Wir haben die Deaktivierung von TLS 1.0 und 1.1 für kommerzielle Kunden aufgrund von COVID-19 vorübergehend angehalten. Da sich die Lieferketten angepasst haben und bestimmte Länder wieder geöffnet werden, haben wir die Einführung der TLS 1.2-Erzwingung am 15. Oktober 2020 neu gestartet. Die Einführung wird in den folgenden Wochen und Monaten fortgesetzt.

Seit dem 31. Oktober 2018 sind die Protokolle TLS 1.0 und 1.1 für den Microsoft 365-Dienst veraltet. Die Auswirkungen für Endbenutzer sind minimal. Diese Änderung wurde über zwei Jahre lang veröffentlicht, mit der ersten öffentlichen Ankündigung im Dezember 2017. Dieser Artikel soll nur den lokalen Office 365-Client in Bezug auf den Office 365-Dienst abdecken, kann aber auch auf lokale TLS-Probleme mit Office und Office Online Server/Office Web Apps angewendet werden.

Für SharePoint und OneDrive müssen Sie .NET aktualisieren und konfigurieren, um TLS 1.2 zu unterstützen. Weitere Informationen finden Sie unter [Aktivieren von TLS 1.2 auf Clients.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Übersicht über Office 365 und TLS

Der Office-Client verwendet den Windows-Webdienst (WINHTTP) zum Senden und Empfangen von Datenverkehr über TLS-Protokolle. Der Office-Client kann TLS 1.2 verwenden, wenn der Webdienst des lokalen Computers TLS 1.2 verwenden kann. Alle Office-Clients können TLS-Protokolle verwenden, da TLS- und SSL-Protokolle Teil des Betriebssystems und nicht spezifisch für den Office-Client sind.

### <a name="on-windows-8-and-later-versions"></a>On Windows 8 and later versions

Standardmäßig sind die Protokolle TLS 1.2 und 1.1 verfügbar, wenn keine Netzwerkgeräte für die Ablehnung von TLS 1.2-Datenverkehr konfiguriert sind.

### <a name="on-windows-7"></a>Unter Windows 7

TLS 1.1- und 1.2-Protokolle sind ohne das [Update KB 3140245 nicht](https://support.microsoft.com/help/3140245) verfügbar. Das Update behebt dieses Problem und fügt den folgenden Registrierungsunterschlüssel hinzu:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7-Benutzer, die nicht über dieses Update verfügen, sind ab dem 31. Oktober 2018 betroffen. [KB 3140245](https://support.microsoft.com/help/3140245) enthält Details zum Ändern der WINHTTP-Einstellungen zum Aktivieren von TLS-Protokollen.

#### <a name="more-information"></a>Weitere Informationen

Der im Kb-Artikel beschriebene Wert des **Registrierungsschlüssels "DefaultSecureProtocols"** bestimmt, welche Netzwerkprotokolle verwendet werden können:

|DefaultSecureProtocols-Wert|Protokoll aktiviert|
|-|-|
|0x00000008|SSL 2.0 standardmäßig aktivieren|
|0x00000020|SSL 3.0 standardmäßig aktivieren|
|0x00000080|TLS 1.0 standardmäßig aktivieren|
|0x00000200|TLS 1.1 standardmäßig aktivieren|
|0x00000800|TLS 1.2 standardmäßig aktivieren|

## <a name="office-clients-and-tls-registry-keys"></a>Office-Clients und -TLS-Registrierungsschlüssel

Informationen zur Vorbereitung auf die obligatorische Verwendung von [TLS 1.2 in Office 365 finden Sie unter KB 4057306.](https://support.microsoft.com/help/4057306) Dies ist ein allgemeiner Artikel für IT-Administratoren, und es handelt sich um eine offizielle Dokumentation zur TLS 1.2-Änderung.

In der folgenden Tabelle sind die entsprechenden Registrierungsschlüsselwerte in Office 365-Clients nach dem 31. Oktober 2018 aufgeführt.

|Aktivierte Protokolle für den Office 365-Dienst nach dem 31. Oktober 2018|Hexadezimaler Wert|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Verwenden Sie nicht die SSL 2.0- und 3.0-Protokolle, die auch mit dem Schlüssel **"DefaultSecureProtocols" festgelegt werden** können. SSL 2.0 und 3.0 gelten als veraltete und unsichere Protokolle. Die bewährte Methode besteht im Beenden der Verwendung von SSL 2.0 und SSL 3.0, obwohl die Entscheidung dafür letztlich davon abhängt, was Ihren Produktanforderungen am besten entspricht. Weitere Informationen zu SSL 3.0-Sicherheitsrisiken finden Sie unter [KB 3009008](https://support.microsoft.com/help/3009008).

Sie können den standardmäßigen Windows-Rechner im Programmiermodus verwenden, um die gleichen Werte für den Registrierungsschlüssel zu erstellen. Weitere Informationen finden Sie unter [KB 3140245 Update, um TLS 1.1 und TLS 1.2](https://support.microsoft.com/help/3140245)als sichere Standardprotokolle in WinHTTP in Windows zu aktivieren.

Unabhängig davon, ob das Windows 7-Update ([KB 3140245](https://support.microsoft.com/help/3140245)) installiert ist oder nicht, ist der Registrierungsunterschlüssel "DefaultSecureProtocols" nicht vorhanden und muss manuell oder über ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) hinzugefügt werden. Das heißt, wenn Sie nicht anpassen müssen, welche sicheren Protokolle aktiviert oder eingeschränkt sind, ist dieser Schlüssel nicht erforderlich. Sie benötigen nur das Update für Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Aktualisieren und Konfigurieren von .NET Framework zur Unterstützung von TLS 1.2

Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden. .NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt. Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter Aktivieren [von TLS 1.2 (Transport Layer Security)](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)auf Clients.

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen finden Sie unter Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
