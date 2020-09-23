---
title: IPv6-Unterstützung in Office 365-Diensten
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Zusammenfassung: Beschreibung der IPv6-Unterstützung in Microsoft Office 365-Komponenten und in Office 365 Government-angeboten.'
ms.openlocfilehash: f671e8caf868ebbed628a155b73ce6fe413949a9
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235606"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-Unterstützung in Office 365-Diensten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Office 365 unterstützt sowohl IPv6 als auch IPv4; Allerdings sind nicht alle Office 365 Funktionen mit IPv6 vollständig aktiviert. Dies bedeutet, dass Sie sowohl IPv4 als auch IPv6 verwenden müssen, um eine Verbindung mit Office 365 herzustellen. Wenn Sie den ausgehenden Datenverkehr auf Office 365 filtern, finden Sie die vollständige Liste der von Office 365 unterstützten IPv6-Adressen im Artikel [Office 365-URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md). Nachdem Ihr Netzwerk konfiguriert wurde und die entsprechenden IPv6-Adressen zulässig sind, können Sie den [Office 365 IPv6-Testplan](https://go.microsoft.com/fwlink/?LinkId=293447) aus dem Microsoft Download Center herunterladen.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-Unterstützung in Office 365 Abonnementdienst

### <a name="exchange-online-and-ipv6"></a>Exchange Online und IPv6

Wenn das Programm, mit dem Sie eine Verbindung mit Exchange Online herstellen, IPv6 unterstützt, wird IPv6 standardmäßig in drahtgebundenen und drahtlosen Netzwerken verwendet. Wenn Sie die Kommunikation mit Exchange Online steuern möchten, verwenden Sie die IP-Adressbereiche in [Office 365-URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online und IPv6

 **Office 365 Government G1/G3/G4/K1** Wenn das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, wird versucht, IPv6 standardmäßig zu verwenden.
  
 **Öffentliche Multi-Mandanten-Cloud** Microsoft aktiviert SharePoint Online IPv6 auf Ihre Anforderung. Sie müssen die CIDR notated-IP-Adressen für die DNS-Infrastruktur Ihrer Organisation bereitstellen. Beachten Sie, dass diese DNS-Infrastruktur nicht von anderen Organisationen gemeinsam genutzt werden kann, damit IPv6 für Ihren Mandanten aktiviert wird. Wenn IPv6 aktiviert ist und das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, wird IPv6 standardmäßig verwendet.
  
Wenn das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, wird IPv6 standardmäßig in drahtgebundenen und drahtlosen Netzwerken verwendet. Wenn Sie die Kommunikation mit SharePoint Online steuern möchten, verwenden Sie die IP-Adressbereiche in [Office 365-URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md).
  
 **Office 365 Government G1/G3/G4/K1** Wenn das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, wird versucht, IPv6 standardmäßig zu verwenden.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business und IPv6

Beachten Sie, dass IPv6 in Skype for Business nicht unterstützt wird und nicht mehr aktiviert werden kann.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams und IPv6

Das direkte Routing von Microsoft Teams unterstützt nur IPv4. Der Microsoft Teams-Dienst und der Client unterstützen IPv4 und IPv6. Wenn Sie die Kommunikation mit Microsoft Teams steuern möchten, verwenden Sie die IP-Adressbereiche in [Office 365-URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md).
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Schutz und IPv6

Exchange Online Protection (EoP) unterstützt IPv6, wenn die Übertragung über das Transport Layer Security Protocol erfolgt. Verwenden Sie für den EoP-Bereich [Office 365-URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md).
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-Unterstützung für Office 365 staatliche Angebote

Office 365 IPv6-Unterstützung für Regierungs Angebote entspricht dem Office of Management and Budget (OMB)-Memorandum für Chief Information Officers of Executive Departments and Agencies, sowie der Einführung von Internet Protocol Version 6 (IPv6) Memorandum durch die Bundesregierung. [Microsoft Office 365 für Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) ist ein Multi-Mandanten Dienst, der US-Regierungsdaten in einer getrennten Community-Cloud speichert. Wie bei anderen Office 365-angeboten bietet es Produktivitäts-und Zusammenarbeitsdienste, einschließlich Exchange Online-, Skype for Business-, SharePoint Online-und Microsoft 365-Apps für Unternehmen. 

Die Microsoft Office 365 Government-Angebote gelten nur für 2013 und höher. Weitere Informationen zu den Office 365 staatlichen Angeboten finden Sie unter [Bekanntgabe Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414). International Traffic in Arms Regulations (ITAR) ist eine Reihe von US-Regierungsverordnungen, die den Export und Import von verteidigungsbezogenen Artikeln und Diensten auf der [US-Munitions Liste (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)steuern. 

Microsoft Office 365 für Unternehmen stellt dedizierte Hosting-Dienste für Microsoft-Produktivitätslösungen bereit, die die Sicherheits-, Datenschutz-und behördlichen Compliance-Anforderungen für US-Bundesbehörden unterstützen, in denen die Federal Information Security Management (FISMA)-Zertifizierung und kommerzielle Entitäten ITAR unterliegen.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Zu berücksichtigende Aspekte bei der Verwendung von IPv6 und Office 365

Es wird empfohlen, IPv6 nicht zu deaktivieren. Weitere Informationen finden Sie in diesem [Leitfaden Artikel](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Um zu ermitteln, welche IP-Versionen in Ihrem Netzwerk verwendet werden, sollten Sie folgendes befolgen:
  
- Wenn die Anzeige des Befehls **ipconfig** an der Eingabeaufforderung Zeilen mit dem Namen "IPv6 Address" oder "Temporary IPv6 Address" enthält, haben Sie IPv6 in Ihrer Umgebung.

- Wenn alle IPv6-Adressen mit "FE80" beginnen und den Zeilen mit dem Namen "Link-Local IPv6 Address" entsprechen, verfügen Sie nicht über IPv6 in Ihrer Umgebung.

Diese Überlegungen gelten möglicherweise für Ihr Netzwerk:
  
- Der öffentliche Abonnementdienst unterstützt den Kauf per Kreditkarte über IPv6 nicht. Dies gilt nicht für die Government Community Cloud (gcc), da Regierungen eine Enterprise Agreement (EA)-Lizenzierung haben.

- Einige RMS-Szenarien (Rights Management Services, Rechteverwaltungsdienst) werden von IPv6 nicht unterstützt.

- BlackBerry® Enterprise Server (BES) wird von IPv6 nicht unterstützt, da BlackBerry IPv6 nicht unterstützt.

- Wenn Sie Active Directory Verbunddienste (AD FS) mit Office 365 verwenden, wird das Annoncieren Ihres AD FS-Netzwerk Endpunkts in Office 365 mit IPv6 nicht unterstützt. Sie sollten keine AAAA-Einträge in den AD FS-DNS-Eintrag einbeziehen, wenn Sie Exchange Online verwenden. 

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)
  
## <a name="see-also"></a>Weitere Artikel

[IPv6 Learning-Roadmap](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 Survival Guide](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
