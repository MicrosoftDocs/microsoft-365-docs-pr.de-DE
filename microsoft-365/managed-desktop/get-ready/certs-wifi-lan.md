---
title: Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop
description: certs/wifi/lan
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9f4490711c1ea051afe9d8efb081a2f7a141f8ba
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909118"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop  
 
Die zertifikatbasierte Authentifizierung ist eine häufige Anforderung für Kunden, die Microsoft Managed Desktop verwenden. Möglicherweise benötigen Sie Zertifikate, um auf Wi-Fi oder LAN zu zugreifen, eine Verbindung mit VPN-Lösungen herzustellen oder um auf interne Ressourcen in Ihrer Organisation zu zugreifen.   
 
Da Microsoft Managed #A0 Azure Active Directory (Azure AD) beigetreten sind und von Microsoft Intune verwaltet werden, müssen Sie diese Zertifikate mithilfe einer in Intune integrierten Zertifikatinfrastruktur für die einfache Zertifikatregistrierung (Simple Certificate Enrollment Protocol, SCEP) oder #A1 (Public Key Cryptography Standard) bereitstellen.    
 
## <a name="certificate-requirements"></a>Anforderungen für Zertifikate 
 
Stammzertifikate sind erforderlich, um Zertifikate über eine SCEP- oder #A0 bereitstellen zu können. Für andere Anwendungen und Dienste in Ihrer Organisation müssen möglicherweise Stammzertifikate auf Ihren Microsoft Managed Desktop-Geräten bereitgestellt werden.    
 
Bevor Sie SCEP- oder #A0 auf Microsoft Managed Desktop bereitstellen, sollten Sie Anforderungen für jeden Dienst sammeln, für den ein Benutzer- oder Gerätezertifikat in Ihrer Organisation erforderlich ist. Um diese Aktivität zu vereinfachen, können Sie eine der folgenden Planungsvorlagen verwenden:  
 
- [#A0](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-Zertifikatvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi Konnektivitätsanforderungen

Damit ein Gerät automatisch mit der erforderlichen Wi-Fi für Ihr Unternehmensnetzwerk bereitgestellt werden kann, benötigen Sie möglicherweise ein Wi-Fi Konfigurationsprofil. Sie können Microsoft Managed Desktop so konfigurieren, dass diese Profile auf Ihren Geräten bereitgestellt werden. Wenn ihre Netzwerksicherheit erfordert, dass Geräte Teil der lokalen Domäne sind, müssen Sie möglicherweise auch Ihre Wi-Fi-Netzwerkinfrastruktur auswerten, um sicherzustellen, dass sie mit Microsoft Managed Desktop-Geräten kompatibel ist (Microsoft Managed Desktop-Geräte sind nur mit Azure AD verbunden). 
 
Bevor Sie eine Wi-Fi auf Microsoft Managed Desktop-Geräten bereitstellen, müssen Sie die Anforderungen Ihrer Organisation für jedes Wi-Fi sammeln. Um diese Aktivität zu vereinfachen, können Sie diese [WLAN-Profilvorlage verwenden.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Anforderungen an kabelgebundene Verbindungen und 802.1x-Authentifizierung 
 
Wenn Sie die 802.1x-Authentifizierung verwenden, um den Zugriff von Geräten auf Das lokale Netzwerk (LAN) zu sichern, müssen Sie die erforderlichen Konfigurationsdetails an Ihre Microsoft Managed Desktop-Geräte übertragen. Microsoft Managed Desktop-Geräte mit Windows 10, Version 1809 oder höher, unterstützen die Bereitstellung einer 802.1x-Konfiguration über den WiredNetwork-Konfigurationsdienstanbieter (CSP). Weitere Informationen finden Sie unter [WiredNetwork CSP-Dokumentation.](/windows/client-management/mdm/wirednetwork-csp) 
 
Bevor Sie ein Verkabelungsnetzwerkkonfigurationsprofil auf Microsoft Managed Desktop-Geräten bereitstellen, müssen Sie die Anforderungen Ihrer Organisation für Ihr verkabelte Unternehmensnetzwerk erfassen. Führen Sie hierfür die folgenden Schritte aus. 
 
 
1. Melden Sie sich bei einem Gerät an, auf dem Ihr vorhandenes 802.1x-Profil konfiguriert ist und mit dem LAN-Netzwerk verbunden ist.  
2. Öffnen Sie eine Eingabeaufforderung mit administrativen Anmeldeinformationen. 
3. Suchen Sie den Namen der LAN-Schnittstelle, indem Sie **die Netsh-Schnittstelle anzeigen.** 
4. Exportieren Sie die LAN-Profil-XML, indem Sie **netsh lan export profile folder=ausführen.  Interface="interface_name"**. 
5. Wenn Sie Ihr exportiertes Profil auf dem Microsoft Managed Desktop-Gerät testen müssen, führen Sie **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" aus.** 
 
 
## <a name="deploy-certificate-infrastructure"></a>Bereitstellen der Zertifikatinfrastruktur  
 
Wenn Sie bereits über eine vorhandene SCEP- oder #A0 mit Intune verfügen und dieser Ansatz Ihren Anforderungen entspricht, können Sie ihn auch für Microsoft Managed Desktop verwenden. Wenn noch keine SCEP- oder #A0 vorhanden ist, müssen Sie eine vorbereiten.  
 
Weitere Informationen finden Sie unter [Configure a certificate profile for your devices in Microsoft Intune](/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Bereitstellen eines LAN-Profils 
 
Nachdem Ihr LAN-Profil exportiert wurde, können Sie die Richtlinie für Microsoft Managed Desktop vorbereiten, indem Sie die folgenden Schritte ausführen:   
 
1. Erstellen Sie ein benutzerdefiniertes Profil in Microsoft Intune für das LAN-Profil mit den folgenden Einstellungen (siehe Verwenden benutzerdefinierter Einstellungen für [Windows 10-Geräte in Intune](/intune/custom-settings-windows-10)). Wählen **Sie unter Benutzerdefinierte OMA-URI-Einstellungen** **Hinzufügen** aus, und geben Sie dann die folgenden Werte ein: 
    - Name: *Modern Workplace-Windows 10 LAN Profile* 
    - Beschreibung: Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung sowie alle anderen wichtigen Details enthält. 
    - OMA-URI (Groß-/Kleinschreibung): Geben Sie *./Device/Vendor/MSFT/WiredNetwork/LanXML ein.*
    - Datentyp: Wählen Sie **String (XML-Datei)** aus. 
    - Benutzerdefinierter XML-Code: Laden Sie die exportierte XML-Datei hoch.
2. Senden Sie eine Supportanfrage an Microsoft Managed Desktop IT Operations mithilfe des Microsoft Managed Desktop Admin-Portals, um das Konfigurationsprofil für "Moderne Arbeitsplatzgeräte – Test" zu überprüfen und zu bereitstellen. Microsoft Managed Desktop-IT-Vorgänge teilen Ihnen mit, wann die Anforderung über die Supportanfrage im Administratorportal abgeschlossen wurde.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Bereitstellen von Zertifikaten und WLAN/VPN-Profil 
 
 
Führen Sie zum Bereitstellen von Zertifikaten und Profilen die folgenden Schritte aus:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe [Erstellen von vertrauenswürdigen Zertifikatprofilen.](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Jedes dieser Profile muss eine Beschreibung enthalten, die ein Ablaufdatum im DD/MM/JJJJ-Format enthält. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**
2. Erstellen Sie ein Profil für jedes SCEP- oder #A0 (siehe Erstellen eines [#A1](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) oder Erstellen eines [#A1](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Jedes dieser Profile muss eine Beschreibung enthalten, die ein Ablaufdatum im DD/MM/JJJ-Format enthält. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**
3. Erstellen Sie ein Profil für jedes [Unternehmens-WLAN-Netzwerk (siehe WLAN-Einstellungen für Windows 10 und höher).](/intune/wi-fi-settings-windows)
4. Erstellen Sie ein Profil für jedes Unternehmens-VPN (siehe Windows 10- und Windows Holographic-Geräteeinstellungen zum Hinzufügen [von VPN-Verbindungen mithilfe von Intune](/intune/vpn-settings-windows-10)).
5. Senden Sie eine Supportanfrage mit dem Titel "Zertifikatbereitstellung" oder "Wlan-Profilbereitstellung" an Microsoft Managed Desktop IT Operations, indem Sie das Microsoft Managed Desktop Admin-Portal verwenden, um das Konfigurationsprofil zu überprüfen und auf "Moderne Arbeitsplatzgeräte – Test" zu installieren. Microsoft Managed Desktop-IT-Vorgänge teilen Ihnen mit, wann die Anforderung über die Supportanfrage im Administratorportal abgeschlossen wurde. 
 
