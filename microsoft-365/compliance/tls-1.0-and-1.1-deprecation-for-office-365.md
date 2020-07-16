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
ms.openlocfilehash: 270d04974cec9c36fa31a77bda401375fdac0471
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148147"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>TLS 1.0- und 1.1-Einstellungen für Office 365
> [!IMPORTANT]
> Wir haben die Durchsetzung von TLS 1,0 und 1,1 für kommerzielle Kunden aufgrund von covid-19 vorübergehend angehalten, aber wenn sich die Zustellungs Ketten angepasst haben und einige Länder eine Sicherung durchlaufen, setzen wir die TLS-Erzwingung so um, dass der 15. Oktober 2020 gestartet wird. 

Ab dem 31. Oktober 2018 werden die Protokolle Transport Layer Security (TLS) 1,0 und 1,1 für den Office 365 Dienst veraltet. Der Effekt für Endbenutzer wird voraussichtlich minimal sein. Diese Änderung wurde seit mehr als zwei Jahren veröffentlicht, und die erste öffentliche Ankündigung erfolgte im Dezember 2017. Dieser Artikel soll nur die Office 365 lokalen Clients in Bezug auf den Office 365 Dienst abdecken, kann aber auch auf lokale TLS-Probleme mit Office-und Office Online Server/Office-Webanwendungen angewendet werden.

## <a name="office-and-tls-overview"></a>Office-und TLS-Übersicht

Der Office-Client verwendet den Windows-Webdienst (WinHTTP), um Datenverkehr über TLS-Protokolle zu senden und zu empfangen. Der Office-Client kann TLS 1,2 verwenden, wenn der Webdienst des lokalen Computers TLS 1,2 verwenden kann. Alle Office-Clients können TLS-Protokolle verwenden, da TLS-und SSL-Protokolle Teil des Betriebssystems und nicht für den Office-Client spezifisch sind.

### <a name="on-windows-8-and-later-versions"></a>In Windows 8 und höheren Versionen

Standardmäßig sind die Protokolle TLS 1,2 und 1,1 verfügbar, wenn keine Netzwerkgeräte so konfiguriert sind, dass der TLS 1,2-Datenverkehr abgelehnt wird.

### <a name="on-windows-7"></a>Auf Windows 7

Die Protokolle TLS 1,1 und 1,2 sind ohne das Update der [KB 3140245](https://support.microsoft.com/help/3140245) nicht verfügbar. Das Update behebt dieses Problem und fügt den folgenden Registrierungsunterschlüssel hinzu:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 Benutzer, die dieses Update nicht haben, sind am 31. Oktober 2018 betroffen. [KB 3140245](https://support.microsoft.com/help/3140245) enthält Details zum Ändern der WinHTTP-Einstellungen zur Aktivierung von TLS-Protokollen.

#### <a name="more-information"></a>Weitere Informationen

Der Wert des Registrierungsschlüssels **DefaultSecureProtocols** , den der KB-Artikel beschreibt, bestimmt, welche Netzwerkprotokolle verwendet werden können:

|DefaultSecureProtocols-Wert|Protokoll aktiviert|
|-|-|
|0x00000008|SSL 2.0 standardmäßig aktivieren|
|0x00000020|SSL 3.0 standardmäßig aktivieren|
|0x00000080|TLS 1.0 standardmäßig aktivieren|
|0x00000200|TLS 1.1 standardmäßig aktivieren|
|0x00000800|TLS 1.2 standardmäßig aktivieren|

## <a name="office-clients-and-tls-registry-keys"></a>Office-Clients und TLS-Registrierungsschlüssel

Sie können sich auf [KB 4057306 Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306). Dies ist ein allgemeiner Artikel für IT-Administratoren und die offizielle Dokumentation zur TLS 1,2-Änderung.

In der folgenden Tabelle sind die entsprechenden Registrierungsschlüsselwerte in Office 365 Clients nach dem 31. Oktober 2018.

|Aktivierte Protokolle für Office 365 Dienst nach dem 31. Oktober 2018|Hexadezimalwert|
|-|-|
|TLS 1,0 + 1,1 + 1,2|0x00000A80|
|TLS 1,1 + 1,2|0x00000A00|
|TLS 1,0 + 1,2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Es wird nicht empfohlen, die SSL 2,0-und 3,0-Protokolle zu verwenden, die auch mithilfe des **DefaultSecureProtocols** -Schlüssels festgelegt werden können. SSL 2,0 und 3,0 werden als veraltete Protokolle betrachtet. Die bewährte Methode besteht darin, die Verwendung von SSL 2,0 und SSL 3,0 zu beenden, obwohl die Entscheidung dafür letztlich davon abhängt, was ihren Produktanforderungen am besten entspricht. Weitere Informationen zu Sicherheitsanfälligkeiten in SSL 3,0 finden Sie unter [KB 3009008](https://support.microsoft.com/help/3009008).

Sie können den standardmäßigen Windows-Rechner im Programmiermodus verwenden, um dieselben Referenz Registrierungsschlüsselwerte einzurichten. Weitere Informationen finden Sie unter [KB 3140245 Update to enable TLS 1,1 and TLS 1,2 als Standard Secure Protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).

Unabhängig davon, ob das Windows 7 Update ([KB 3140245](https://support.microsoft.com/help/3140245)) installiert ist oder nicht, ist der DefaultSecureProtocols-Registrierungsunterschlüssel nicht vorhanden und muss manuell oder über ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) hinzugefügt werden. Das heißt, es sei denn, Sie müssen anpassen, welche sicheren Protokolle aktiviert oder eingeschränkt sind, dieser Schlüssel ist nicht erforderlich. Sie benötigen nur das Update Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).
