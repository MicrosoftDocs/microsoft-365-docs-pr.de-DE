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
description: 'Zusammenfassung: Beschreibt die IPv6-Unterstützung in Microsoft Office 365-Komponenten und in Office 365 Government-Angeboten.'
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028907"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-Unterstützung in Office 365-Diensten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Office 365 unterstützt sowohl IPv6 als auch IPv4. Allerdings sind nicht alle Office 365-Features mit IPv6 vollständig aktiviert. Dies bedeutet, dass Sie sowohl IPv4 als auch IPv6 verwenden müssen, um eine Verbindung mit Office 365 herzustellen. Wenn Sie Ihren ausgehenden Datenverkehr zu Office 365 filtern, finden Sie die vollständige Liste der IPv6-Adressen, die von Office 365 unterstützt werden, im Artikel [Office 365-URLs und IP-Adressbereiche.](urls-and-ip-address-ranges.md) Nachdem Ihr Netzwerk konfiguriert und die entsprechenden IPv6-Adressen zulässig sind, können Sie den [Office 365 IPv6-Testplan](https://go.microsoft.com/fwlink/?LinkId=293447) aus dem Microsoft Download Center herunterladen.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-Unterstützung im Office 365-Abonnementdienst

### <a name="exchange-online-and-ipv6"></a>Exchange Online und IPv6

Wenn das Programm, mit dem Sie eine Verbindung mit Exchange Online herstellen, IPv6 unterstützt, wird IPv6 standardmäßig in kabelgebundenen und drahtlosen Netzwerken verwendet. Wenn Sie die Kommunikation mit Exchange Online steuern möchten, verwenden Sie die IP-Adressbereiche in [Office 365-URLs und IP-Adressbereichen.](urls-and-ip-address-ranges.md)
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online und IPv6

 **Office 365 Government G1/G3/G4/K1** Wenn das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, wird versucht, IPv6 standardmäßig zu verwenden.
  
 **Öffentliche mehrinstanzenfähige Cloud** Microsoft aktiviert SharePoint Online IPv6 auf Ihre Anforderung. Sie müssen die notierten CIDR-IP-Adressen für die DNS-Infrastruktur Ihrer Organisation angeben. Beachten Sie, dass diese DNS-Infrastruktur nicht von anderen Organisationen gemeinsam genutzt werden kann, damit IPv6 für Ihren Mandanten aktiviert wird. Wenn IPv6 aktiviert ist und das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, wird IPv6 standardmäßig verwendet.
  
Wenn das Programm, mit dem Sie eine Verbindung mit SharePoint Online herstellen, IPv6 unterstützt, verwendet es IPv6 standardmäßig in kabelgebundenen und drahtlosen Netzwerken. Wenn Sie die Kommunikation mit SharePoint Online steuern möchten, verwenden Sie die IP-Adressbereiche in [Office 365-URLs und IP-Adressbereichen.](urls-and-ip-address-ranges.md)
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business und IPv6

Bitte beachten Sie, dass IPv6 in Skype for Business nicht unterstützt wird und nicht mehr aktiviert werden kann.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams und IPV6

Microsoft Teams Direct Routing unterstützt nur IPv4. Der Microsoft Teams-Dienst und -Client unterstützen sowohl IPv4 als auch IPv6. Wenn Sie die Kommunikation mit Microsoft Teams steuern möchten, verwenden Sie die IP-Adressbereiche in [Office 365-URLs und IP-Adressbereichen.](urls-and-ip-address-ranges.md)
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection und IPv6

Exchange Online Protection (EOP) unterstützt IPv6, wenn die Übertragung über das Transport Layer Security Protocol erfolgt. Verwenden Sie für den [EOP-Bereich Office 365-URLs und IP-Adressbereiche.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-Unterstützung für Office 365 Government-Angebote

Die Office 365 IPv6-Unterstützung für Behördenangebote entspricht dem Office of Management and Budget (OMB)-Projekt für Chief Information Officers der Geschäftsleitungen und Behörden sowie der Einführung der Internetprotokollversion 6 (IPv6) durch die Regierung. [Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) ist ein mehrinstanzenfähiger Dienst, der Daten von US-Behörden in einer getrennten Community-Cloud speichert. Wie andere Office 365-Angebote bietet es Produktivitäts- und Zusammenarbeitsdienste, einschließlich Exchange Online, Skype for Business, SharePoint Online und Microsoft 365 Apps for Enterprise. 

Die Microsoft Office 365 Government-Angebote gelten nur für 2013 und höher. Weitere Informationen zu den Office 365 Government-Angeboten finden Sie unter [Ankündigung von Office 365 for Government: A US Government Community Cloud.](https://go.microsoft.com/fwlink/p/?LinkId=325414) International Traffic in Arms Regulations (ITAR) ist eine Reihe von US-Regierungsvorschriften, die den Export und Import von Verteidigungsartikeln und -diensten in der [US-Munitionsliste (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)steuern. 

Microsoft Office 365 for Enterprises bietet dedizierte Hostingdienste für Microsoft-Produktivitätslösungen, die die Sicherheits-, Datenschutz- und Complianceanforderungen für US-Bundesbehörden unterstützen, die fisma-Zertifizierungen (Federal Information Security Management) und kommerzielle Entitäten erfordern, die ITAR unterliegen.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Zu berücksichtigende Aspekte bei der Verwendung von IPv6 und Office 365

Es wird empfohlen, IPv6 nicht zu deaktivieren. Weitere Informationen finden Sie in diesem [Anleitungsartikel.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users) Um zu ermitteln, welche IP-Versionen in Ihrem Netzwerk verwendet werden, berücksichtigen Sie Folgendes:
  
- Wenn die Anzeige des **IPConfig-Befehls** an der Eingabeaufforderung Zeilen mit dem Namen "IPv6-Adresse" oder "Temporäre IPv6-Adresse" enthält, ist IPv6 in Ihrer Umgebung vorhanden.

- Wenn alle IPv6-Adressen mit "fe80" beginnen und Zeilen mit dem Namen "Link-Local IPv6 Address" entsprechen, ist IPv6 in Ihrer Umgebung nicht vorhanden.

Diese Überlegungen können für Ihr Netzwerk gelten:
  
- Der öffentliche Abonnementdienst unterstützt den Kauf per Kreditkarte über IPv6 nicht. Dies gilt nicht für die Government Community Cloud (GCC), da Die Behörden über Eine Enterprise Agreement (EA)-Lizenzierung verfügen.

- IPv6 unterstützt einige RMS-Szenarien (Rights Management Services) nicht.

- IPv6 unterstützt BlackBerry® Enterprise Server (BES) nicht, da BlackBerry IPv6 nicht unterstützt.

- Wenn Sie Active Directory-Verbunddienste (AD FS) mit Office 365 verwenden, wird das Anzeigen Ihres AD FS-Netzwerkendpunkts für Office 365 mit IPv6 nicht unterstützt. Sie sollten bei Verwendung von Exchange Online keine AAAA-Einträge in den AD FS-DNS-Eintrag einschließen. 

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Weitere Artikel

[IPv6-Lern-Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Leitfaden zur IPv6-Wiesn](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
