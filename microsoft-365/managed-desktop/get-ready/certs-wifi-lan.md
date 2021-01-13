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
ms.openlocfilehash: cf31778d773a271ead6a1745197f04eca127ab5d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841095"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop  
 
Die zertifikatbasierte Authentifizierung ist eine häufige Anforderung für Kunden, die Microsoft Managed Desktop verwenden. Möglicherweise benötigen Sie Zertifikate für den Zugriff auf Wi-Fi oder LAN, für die Verbindung mit VPN-Lösungen oder für den Zugriff auf interne Ressourcen in Ihrer Organisation.   
 
Da Microsoft Managed #A0 mit Azure Active Directory (Azure AD) verbunden sind und von Microsoft Intune verwaltet werden, müssen Sie diese Zertifikate mithilfe einer #A1 (Simple Certificate Enrollment Protocol) oder eines #A2 (Public Key Cryptography Standard) bereitstellen, das in Intune integriert ist.    
 
## <a name="certificate-requirements"></a>Anforderungen für Zertifikate 
 
Stammzertifikate sind erforderlich, um Zertifikate über eine SCEP- oder #A0 bereitstellen zu können. Für andere Anwendungen und Dienste in Ihrer Organisation müssen möglicherweise Stammzertifikate auf Ihren Microsoft Managed Desktop-Geräten bereitgestellt werden.    
 
Bevor Sie SCEP- oder #A0 für Microsoft Managed Desktop bereitstellen, sollten Sie Anforderungen für jeden Dienst sammeln, der ein Benutzer- oder Gerätezertifikat in Ihrer Organisation erfordert. Um diese Aktivität zu vereinfachen, können Sie eine der folgenden Planungsvorlagen verwenden:  
 
- [#A0](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP-Zertifikatvorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi Konnektivitätsanforderungen

Damit ein Gerät automatisch mit der erforderlichen Wi-Fi für Ihr Unternehmensnetzwerk bereitgestellt werden kann, benötigen Sie möglicherweise ein Wi-Fi Konfigurationsprofil. Sie können Microsoft Managed Desktop so konfigurieren, dass diese Profile auf Ihren Geräten bereitgestellt werden. Wenn Ihre Netzwerksicherheit erfordert, dass Geräte Teil der lokalen Domäne sind, müssen Sie möglicherweise auch Ihre Wi-Fi-Netzwerkinfrastruktur auswerten, um sicherzustellen, dass sie mit Microsoft Managed Desktop-Geräten kompatibel ist (Microsoft Managed Desktop-Geräte sind nur mit Azure AD verbunden). 
 
Bevor Sie eine Wi-Fi auf Microsoft Managed Desktop-Geräten bereitstellen, müssen Sie die Anforderungen Ihrer Organisation für jedes Wi-Fi erfassen. Um diese Aktivität zu vereinfachen, können Sie diese [WiFi-Profilvorlage verwenden.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Anforderungen an kabelgebundene Verbindungen und 802.1x-Authentifizierung 
 
Wenn Sie die 802.1x-Authentifizierung verwenden, um den Zugriff von Geräten auf Ihr lokales Netzwerk (Local Area Network, LAN) zu sichern, müssen Sie die erforderlichen Konfigurationsdetails an Ihre Microsoft Managed Desktop-Geräte übertragen. Microsoft Managed #A0 mit Windows 10, Version 1809 oder höher, unterstützen die Bereitstellung einer 802.1x-Konfiguration über den #A1 (CSP). Weitere Informationen finden Sie in der [#A0 von WiredNetwork.](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) 
 
Bevor Sie ein kabelgebundenes Netzwerkkonfigurationsprofil auf Microsoft Managed Desktop-Geräten bereitstellen, sollten Sie die Anforderungen Ihrer Organisation für Ihr kabelgebundenes Unternehmensnetzwerk erfassen. Führen Sie hierfür die folgenden Schritte aus. 
 
 
1. Melden Sie sich bei einem Gerät an, auf dem Ihr vorhandenes 802.1x-Profil konfiguriert ist und das mit dem NETZWERK verbunden ist.  
2. Öffnen Sie eine Eingabeaufforderung mit Administratoranmeldeinformationen. 
3. Suchen Sie den Namen der LAN-Schnittstelle, indem Sie die **Netsh Interface Show Interface ausführen.** 
4. Exportieren Sie die LAN-Profil-XML, indem **Sie netsh lan export profile folder=ausführen.  Interface="interface_name"**. 
5. Wenn Sie Ihr exportiertes Profil auf einem Microsoft Managed Desktop-Gerät testen müssen, führen Sie **netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" aus.** 
 
 
## <a name="deploy-certificate-infrastructure"></a>Bereitstellen der Zertifikatinfrastruktur  
 
Wenn Sie bereits über eine SCEP- oder #A0 mit Intune verfügen und dieser Ansatz Ihren Anforderungen entspricht, können Sie ihn auch für Microsoft Managed Desktop verwenden. Wenn noch keine SCEP- oder #A0 vorhanden ist, müssen Sie eine vorbereiten.  
 
Weitere Informationen finden Sie unter [Konfigurieren eines Zertifikatprofils für Ihre Geräte in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure) 
 
 
 
## <a name="deploy-a-lan-profile"></a>Bereitstellen eines LAN-Profils 
 
Nachdem Ihr LAN-Profil exportiert wurde, können Sie die Richtlinie für Microsoft Managed Desktop vorbereiten, indem Sie die folgenden Schritte ausführen:   
 
1. Erstellen Sie ein benutzerdefiniertes Profil in Microsoft Intune für das LAN-Profil mit den folgenden Einstellungen (siehe Verwenden benutzerdefinierter Einstellungen für [Windows 10-Geräte in Intune).](https://docs.microsoft.com/intune/custom-settings-windows-10) Wählen **Sie in den benutzerdefinierten OMA-URI-Einstellungen** die Option **"Hinzufügen"** aus, und geben Sie dann die folgenden Werte ein: 
    - Name: *Modern Workplace-Windows 10 LAN Profile* 
    - Beschreibung: Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung sowie andere wichtige Details bietet. 
    - OMA-URI (Groß-/Kleinschreibung wird beachtet): Geben Sie *"./Device/Vendor/MSFT/WiredNetwork/LanXML" ein.*
    - Datentyp: Wählen **Sie Zeichenfolge (XML-Datei) aus.** 
    - Benutzerdefinierte XML: Laden Sie die exportierte XML-Datei hoch.
2. Übermitteln Sie eine Supportanfrage an Microsoft Managed Desktop IT Operations über das Microsoft Managed Desktop Admin-Portal, um das Konfigurationsprofil zu überprüfen und auf "Moderne Arbeitsplatzgeräte – Test" zu stellen. Microsoft Managed Desktop IT Operations teilen Ihnen mit, wann die Anforderung über die Supportanfrage im Verwaltungsportal abgeschlossen wurde.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Bereitstellen von Zertifikaten und WLAN/VPN-Profil 
 
 
Führen Sie zum Bereitstellen von Zertifikaten und Profilen die folgenden Schritte aus:

1. Erstellen Sie ein Profil für jedes Stamm- und Zwischenzertifikat (siehe Erstellen [von vertrauenswürdigen Zertifikatprofilen).](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles) Jedes dieser Profile muss eine Beschreibung enthalten, die ein Ablaufdatum im TT/MM/JJJJ-Format enthält. **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**
2. Erstellen Eines Profils für jedes SCEP- oder #A0 (siehe Erstellen eines [#A1](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) oder Erstellen eines PKCS-Zertifikatprofils) Jedes dieser Profile muss eine Beschreibung enthalten, die ein Ablaufdatum im DD/MM/JJJJ-Format enthält. [](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile) **Zertifikatprofile ohne Ablaufdatum werden nicht bereitgestellt.**
3. Erstellen Sie ein Profil für jedes [Unternehmens-WLAN-Netzwerk (siehe WLAN-Einstellungen für Windows 10 und höher).](https://docs.microsoft.com/intune/wi-fi-settings-windows)
4. Erstellen Sie ein Profil für jedes Unternehmens-VPN (siehe Windows 10- und Windows Holographic-Geräteeinstellungen zum Hinzufügen von [VPN-Verbindungen mithilfe von Intune).](https://docs.microsoft.com/intune/vpn-settings-windows-10)
5. Übermitteln Sie eine Supportanfrage mit dem Titel "Zertifikatbereitstellung" oder "Wi-Fi-Profilbereitstellung" an Microsoft Managed Desktop IT Operations, indem Sie das Microsoft Managed Desktop Admin Portal verwenden, um das Konfigurationsprofil unter "Moderne Arbeitsplatzgeräte – Test" zu überprüfen und bereitstellen. Microsoft Managed Desktop IT Operations teilen Ihnen mit, wann die Anforderung über die Supportanfrage im Verwaltungsportal abgeschlossen wurde. 
 
 
