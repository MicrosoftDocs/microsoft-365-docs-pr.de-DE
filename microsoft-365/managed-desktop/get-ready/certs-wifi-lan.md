---
title: Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop
description: certs/WiFi/LAN
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0c3edda92e28b45b7f7b48c1d5002014f71116f6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596572"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop  
 
Die zertifikatbasierte Authentifizierung ist eine häufige Voraussetzung für Kunden, die Microsoft Managed Desktop verwenden. Möglicherweise benötigen Sie Zertifikate für den Zugriff auf WLAN oder LAN, eine Verbindung mit VPN-Lösungen oder für den Zugriff auf interne Ressourcen in Ihrer Organisation.   
 
Da Microsoft Managed Desktop-Geräte mit Azure Active Directory (Azure AD) verbunden und von Microsoft InTune verwaltet werden, müssen Sie diese Zertifikate mithilfe eines SCEP (Simple Certificate Enrollment Protocol) oder eines Public Key Cryptography Standard (PKCS) bereitstellen. Zertifikatinfrastruktur, die in InTune integriert ist.    
 
## <a name="certificate-requirements"></a>Anforderungen für Zertifikate 
 
Stammzertifikate sind erforderlich, um Zertifikate über eine SCEP-oder PKCS-Infrastruktur bereitzustellen. Für andere Anwendungen und Dienste in Ihrer Organisation ist es möglicherweise erforderlich, dass Stammzertifikate auf Ihren von Microsoft verwalteten Desktop Geräten bereitgestellt werden.    
 
Vor dem Bereitstellen von SCEP-oder PKCS-Zertifikaten für Microsoft Managed Desktop sollten Sie Anforderungen für jeden Dienst erfassen, der ein Benutzer-oder Gerätezertifikat in Ihrer Organisation erfordert. Um dies zu vereinfachen, können Sie eine der folgenden Planungsvorlagen verwenden:  
 
- [PKCS-Zertifikatvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-Zertifikatvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>Derzeit werden nur SCEP-Zertifikat Profile für die Bereitstellung von WLAN-Profilen in Microsoft Managed Desktop unterstützt, wenn Sie einen EAP-Typ verwenden. PKCS-Zertifikat Profile werden nicht unterstützt. Weitere Informationen finden Sie unter [Hinzufügen von Wi-Fi-Einstellungen für Windows 10-Geräte in InTune](https://docs.microsoft.com/intune/wi-fi-settings-windows) .

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi-Verbindungsanforderungen

Damit ein Gerät automatisch mit der erforderlichen WLAN-Konfiguration für Ihr Unternehmensnetzwerk bereitgestellt werden kann, benötigen Sie möglicherweise ein Wi-Fi-Konfigurationsprofil. Sie können Microsoft Managed Desktop so konfigurieren, dass diese Profile auf Ihren Geräten bereitgestellt werden. Wenn Ihre Netzwerksicherheit erfordert, dass Geräteteil der lokalen Domäne sind, müssen Sie möglicherweise auch Ihre WLAN-Netzwerkinfrastruktur auswerten, um sicherzustellen, dass Sie mit den von Microsoft verwalteten Desktopgeräten kompatibel ist (Microsoft Managed Desktop-Geräte sind Azure AD verbunden Only). 
 
Vor dem Bereitstelleneiner WLAN-Konfiguration für Microsoft Managed Desktop-Geräte müssen Sie die Anforderungen Ihrer Organisation für jedes WLAN-Netzwerk erfassen. Um dies zu vereinfachen, können Sie diese [WiFi-Profilvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)verwenden.
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Kabel Verbindungsanforderungen und 802.1 x-Authentifizierung 
 
Wenn Sie die 802.1 x-Authentifizierung verwenden, um den Zugriff von Geräten auf Ihr lokales Netzwerk (Local Area Network, LAN) sicherzustellen, müssen Sie die erforderlichen Konfigurationsdetails auf Ihre verwalteten Desktop Geräte von Microsoft pushen. Microsoft Managed Desktop-Geräte mit Windows 10, Version 1809 oder höher, unterstützen die Bereitstellung einer 802.1 x-Konfiguration über den WiredNetwork-Konfigurationsdienst Anbieter (CSP). Weitere Informationen finden Sie unter [WiredNetwork CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) Documentation. 
 
Bevor Sie ein kabelgebundenes Netzwerk Konfigurationsprofil für Microsoft Managed Desktop-Geräte bereitstellen, erfassen Sie die Anforderungen Ihrer Organisation für Ihr drahtgebundenes Unternehmensnetzwerk. Führen Sie hierfür die folgenden Schritte aus. 
 
 
1. Melden Sie sich bei einem Gerät an, auf dem Ihr vorhandenes 802.1 x-Profil konfiguriert ist und das mit dem LAN-Netzwerk verbunden ist.  
2. Öffnen Sie eine Eingabeaufforderung mit administrativen Anmeldeinformationen. 
3. Suchen Sie den Namen der LAN-Schnittstelle durch Ausführung der **Netsh Interface Show-Schnittstelle**. 
4. Exportieren Sie das LAN-Profil-XML, indem Sie **Netsh LAN Export Profile Folder = ausführen.  Interface = "INTERFACE_NAME"**. 
5. Wenn Sie Ihr exportiertes Profil auf dem Microsoft Managed Desktop-Gerät testen müssen, führen Sie **Netsh LAN Add profile filename = "PATH_AND_FILENAME. xml" Interface = "INTERFACE_NAME"** aus. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Bereitstellen der Zertifikatinfrastruktur  
 
Wenn Sie bereits über eine vorhandene SCEP-oder PKCS-Infrastruktur mit InTune verfügen und diese Ihren Anforderungen entspricht, können Sie Sie auch für Microsoft Managed Desktop verwenden. Wenn keine SCEP-oder PKCS-Infrastruktur bereits vorhanden ist, müssen Sie eine vorbereiten.  
 
Weitere Informationen finden Sie unter [Konfigurieren eines Zertifikat Profils für Ihre Geräte in Microsoft InTune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Bereitstellen eines LAN-Profils 
 
Nachdem Sie Ihr LAN-Profil exportiert haben, können Sie die Richtlinie für Microsoft Managed Desktop folgendermaßen vorbereiten:   
 
1. Erstellen Sie ein benutzerdefiniertes Profil in Microsoft InTune für das LAN-Profil mit den folgenden Einstellungen (siehe [Verwenden von benutzerdefinierten Einstellungen für Windows 10-Geräte in InTune](https://docs.microsoft.com/intune/custom-settings-windows-10)). Wählen Sie unter **benutzerdefinierte Oma-URI-Einstellungen**die Option **Hinzufügen**aus, und geben Sie dann die folgenden Werte ein: 
    - Name: *moderner Arbeitsplatz – LAN-Profil für Windows 10* 
    - Beschreibung: Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung und weitere wichtige Details enthält. 
    - Oma-URI (Groß-/Kleinschreibung beachten): Enter *./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - Datentyp: SELECT **String (XML File)**. 
    - Benutzerdefiniertes XML: Hochladen der exportierten XML-Datei.
2. Übermitteln Sie eine Support Anfrage an den Microsoft Managed Desktop-IT-Betrieb mithilfe des Verwaltungsportals von Microsoft Managed Desktop, um das Konfigurationsprofil auf "moderne Arbeitsplatz Geräte – Test" zu überprüfen und bereitzustellen. Microsoft Managed Desktop-IT-Betrieb informiert Sie, wenn die Anforderung über die Support Anfrage im Administratorportal abgeschlossen wird.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Bereitstellen von Zertifikaten und Wi-Fi/VPN-Profil 
 
 
Führen Sie die folgenden Schritte aus, um Zertifikate und Profile bereitzustellen:

1. Erstellen Sie ein Profil für jedes der Stamm-und Zwischenzertifikate (siehe [Create Trusted Certificate Profiles](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles). Jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format tt/mm/jjjj enthält. **Zertifikat profile ohne Ablaufdatum werden nicht bereitgestellt.**
2. Erstellen eines Profils für jedes SCEP-oder PKCS-Zertifikat (siehe [Erstellen eines SCEP-Zertifikats Profils](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) oder [Erstellen eines PKCS-Zertifikat Profils](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) jedes dieser Profile muss eine Beschreibung aufweisen, die ein Ablaufdatum im Format tt/mm/jjjj enthält. **Zertifikat profile ohne Ablaufdatum werden nicht bereitgestellt.**
3. Erstellen Sie ein Profil für jedes Firmen-WLAN-Netzwerk (siehe [WLAN-Einstellungen für Geräte unter Windows 10 und höher](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Erstellen Sie ein Profil für jedes Unternehmens VPN (siehe [Windows 10 und Windows holographische Geräteeinstellungen zum Hinzufügen von VPN-Verbindungen mit InTune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Übermitteln einer Support Anforderung mit dem Titel "Zertifikatbereitstellung" oder "WLAN-Profil Bereitstellung" an von Microsoft verwaltete Desktop-IT-Vorgänge mithilfe des Verwaltungsportals von Microsoft Managed Desktop zum Überprüfen und Bereitstellen des Konfigurationsprofils für "moderne Arbeitsplatz Geräte – Test ". Microsoft Managed Desktop-IT-Betrieb informiert Sie darüber, wann die Anforderung über die Support Anfrage im Administratorportal abgeschlossen wurde. 
 
 
