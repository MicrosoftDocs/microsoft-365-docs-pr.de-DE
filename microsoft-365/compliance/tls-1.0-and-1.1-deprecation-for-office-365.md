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
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332678"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Deaktivieren von TLS 1.0 und 1.1 für Microsoft 365

> [!IMPORTANT]
> Wir haben die Deaktivierung von TLS 1.0 und 1.1 für kommerzielle Kunden aufgrund von COVID-19 vorübergehend angehalten. Da lieferketten angepasst wurden und bestimmte Länder eine Back-up-Version öffnen, haben wir das TLS 1.2-Einführungsrollout am 15. Oktober 2020 neu gestartet. Das Rollout wird in den folgenden Wochen und Monaten fortgesetzt.

Ab dem 31. Oktober 2018 sind die Protokolle Transport Layer Security (TLS) 1.0 und 1.1 für den Microsoft 365-Dienst veraltet. Der Effekt für Endbenutzer ist minimal. Diese Änderung wurde seit mehr als zwei Jahren veröffentlicht, mit der ersten öffentlichen Ankündigung im Dezember 2017. Dieser Artikel soll nur den lokalen Office 365-Client in Bezug auf den Office 365-Dienst abdecken, kann aber auch auf lokale TLS-Probleme mit Office und Office Online Server/Office Web Apps angewendet werden.

Für SharePoint und OneDrive müssen Sie .NET aktualisieren und konfigurieren, um TLS 1.2 zu unterstützen. Weitere Informationen finden Sie unter [Aktivieren von TLS 1.2 auf Clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="office-365-and-tls-overview"></a>Übersicht über Office 365 und TLS

Der Office-Client verwendet den Windows-Webdienst (WINHTTP) zum Senden und Empfangen von Datenverkehr über TLS-Protokolle. Der Office-Client kann TLS 1.2 verwenden, wenn der Webdienst des lokalen Computers TLS 1.2 verwenden kann. Alle Office-Clients können TLS-Protokolle verwenden, da TLS- und SSL-Protokolle Teil des Betriebssystems und nicht spezifisch für den Office-Client sind.

### <a name="on-windows-8-and-later-versions"></a>On Windows 8 and later versions

Standardmäßig sind die Protokolle TLS 1.2 und 1.1 verfügbar, wenn keine Netzwerkgeräte für die Ablehnung von TLS 1.2-Datenverkehr konfiguriert sind.

### <a name="on-windows-7"></a>Unter Windows 7

TLS 1.1- und 1.2-Protokolle sind ohne das [Update KB 3140245 nicht verfügbar.](https://support.microsoft.com/help/3140245) Das Update behebt dieses Problem und fügt den folgenden Registrierungsunterschlüssel hinzu:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7-Benutzer, die nicht über dieses Update verfügen, sind ab dem 31. Oktober 2018 betroffen. [KB 3140245](https://support.microsoft.com/help/3140245) enthält Details zum Ändern von WINHTTP-Einstellungen zur Aktivierung von TLS-Protokollen.

#### <a name="more-information"></a>Weitere Informationen

Der Im KB-Artikel beschriebene Wert des **DefaultSecureProtocols-Registrierungsschlüssels** bestimmt, welche Netzwerkprotokolle verwendet werden können:

|DefaultSecureProtocols-Wert|Protokoll aktiviert|
|-|-|
|0x00000008|SSL 2.0 standardmäßig aktivieren|
|0x00000020|SSL 3.0 standardmäßig aktivieren|
|0x00000080|TLS 1.0 standardmäßig aktivieren|
|0x00000200|TLS 1.1 standardmäßig aktivieren|
|0x00000800|TLS 1.2 standardmäßig aktivieren|

## <a name="office-clients-and-tls-registry-keys"></a>Office-Clients und TLS-Registrierungsschlüssel

Sie können sich auf KB 4057306 Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365 beziehen.](https://support.microsoft.com/help/4057306) Dies ist ein allgemeiner Artikel für IT-Administratoren, und es handelt sich um eine offizielle Dokumentation zur TLS 1.2-Änderung.

In der folgenden Tabelle sind die entsprechenden Registrierungsschlüsselwerte in Office 365-Clients nach dem 31. Oktober 2018 aufgeführt.

|Aktivierte Protokolle für Office 365-Dienst nach dem 31. Oktober 2018|Hexadezimalwert|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Verwenden Sie nicht die PROTOKOLLE SSL 2.0 und 3.0, die auch mithilfe des **DefaultSecureProtocols-Schlüssels festgelegt werden** können. SSL 2.0 und 3.0 gelten als veraltete und unsichere Protokolle. Die bewährte Methode ist, die Verwendung von SSL 2.0 und SSL 3.0 zu beenden, obwohl die Entscheidung dafür letztendlich davon abhängt, was Ihre Produktanforderungen am besten erfüllt. Weitere Informationen zu SSL 3.0-Sicherheitsrisiken finden Sie unter [KB 3009008](https://support.microsoft.com/help/3009008).

Sie können den Standardmäßigen Windows-Rechner im Programmiermodus verwenden, um dieselben Referenzregistrierungsschlüsselwerte zu erstellen. Weitere Informationen finden Sie unter [KB 3140245 Update, um TLS 1.1 und TLS 1.2](https://support.microsoft.com/help/3140245)als sichere Standardprotokolle in WinHTTP in Windows zu aktivieren.

Unabhängig davon, ob das Windows 7-Update ([KB 3140245](https://support.microsoft.com/help/3140245)) installiert ist oder nicht, ist der Registrierungsunterschlüssel DefaultSecureProtocols nicht vorhanden und muss manuell oder über ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) hinzugefügt werden. Das heißt, wenn Sie nicht anpassen müssen, welche sicheren Protokolle aktiviert oder eingeschränkt sind, ist dieser Schlüssel nicht erforderlich. Sie benötigen nur das Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) Update.

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Aktualisieren und Konfigurieren der .NET Framework zur Unterstützung von TLS 1.2

Sie müssen Anwendungen aktualisieren, die Microsoft 365-APIs über TLS 1.0 oder TLS 1.1 aufrufen, um TLS 1.2 zu verwenden. .NET 4.5 ist standardmäßig auf TLS 1.1 festgelegt. Informationen zum Aktualisieren der .NET-Konfiguration finden Sie unter [Aktivieren von Transport Layer Security (TLS) 1.2 auf Clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="more-information"></a>Weitere Informationen

Weitere Informationen finden Sie unter [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="references"></a>Informationsquellen

Die folgenden Ressourcen bieten Anleitungen, um sicherzustellen, dass Ihre Clients TLS 1.2 oder eine spätere Version verwenden und TLS 1.0 und 1.1 deaktivieren:

- Wenn Sie Windows-7-Clients haben, die mit Office 365 verbunden sind, stellen Sie sicher, dass TLS 1.2 die standardmäßigen sicheren Protokolle in WinHTTP in Windows sind. Weitere Informationen finden Sie unter [KB 3140245 – Update, um TLS 1.1 und TLS 1.2](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)als sichere Standardprotokolle in WinHTTP in Windows zu aktivieren.
- Informationen zur Beseitigung einer schwachen TLS-Nutzung durch Entfernen von TLS 1.0- und 1.1-Abhängigkeiten finden Sie unter [TLS 1.2-Unterstützung bei Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [Die neue IIS-Funktionalität](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) erleichtert die Suche nach Clients unter [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) und [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334), die unter Verwendung von schwachen Sicherheitsprotokollen eine Verbindung mit dem Dienst herstellen.
- Hier finden Sie weitere Informationen zur [Lösung des TLS 1.0-Problems.](https://www.microsoft.com/download/details.aspx?id=55266)
- Allgemeine Informationen zu unserem Sicherheits-Ansatz finden Sie im [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Vorbereiten auf die Einstellung von TLS 1.0/1.1 – Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS-Leitfaden Teil 2: Enabling TLS 1.2 and Identifying Clients Not Using It](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS-Leitfaden Teil 3: TLS 1.0/1.1 abschalten](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Aktivieren des TLS 1.1- und TLS 1.2-Supports in Office Online-Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

