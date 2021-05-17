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
description: 'Zusammenfassung: Beschreibt die IPv6-Unterstützung in Microsoft Office 365 und in Office 365 Government-Angeboten.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909682"
---
# <a name="ipv6-support-in-office-365-services"></a>IPv6-Unterstützung in Office 365-Diensten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Office 365 unterstützt sowohl IPv6 als auch IPv4. Allerdings sind nicht alle Office 365 mit IPv6 vollständig aktiviert. Dies bedeutet, dass Sie sowohl IPv4 als auch IPv6 verwenden müssen, um eine Verbindung mit Office 365. Wenn Sie den ausgehenden Datenverkehr nach Office 365 filtern, finden Sie die vollständige Liste der von Office 365 unterstützten IPv6-Adressen im Artikel Office 365 URLs und [IP-Adressbereiche](urls-and-ip-address-ranges.md). Nachdem Ihr Netzwerk konfiguriert wurde und die entsprechenden IPv6-Adressen zulässig sind, können Sie den Office 365 [IPv6-Testplan](https://go.microsoft.com/fwlink/?LinkId=293447) aus dem Microsoft Download Center herunterladen.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>IPv6-Support in Office 365 Abonnementdienst

### <a name="exchange-online-and-ipv6"></a>Exchange Online und IPv6

Wenn das Programm, das Sie zum Herstellen einer Verbindung mit Exchange Online verwenden, IPv6 unterstützt, wird IPv6 standardmäßig sowohl für kabelgebundene als auch für drahtlose Netzwerke verwendet. Wenn Sie die Kommunikation mit Exchange Online steuern möchten, verwenden Sie die IP-Adressbereiche in Office 365 [URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online und IPv6

 **Office 365 Government G1/G3/G4/K1** Wenn das Programm, das Sie zum Herstellen einer Verbindung mit SharePoint Online verwenden, IPv6 unterstützt, wird standardmäßig versucht, IPv6 zu verwenden.
  
 **Öffentliche Mehr-Mandanten-Cloud** Microsoft aktiviert SharePoint Online-IPv6 auf Ihre Anfrage. Sie müssen die CIDR-notierten IP-Adressen für die DNS-Infrastruktur Ihrer Organisation bereitstellen. Beachten Sie, dass diese DNS-Infrastruktur nicht von anderen Organisationen gemeinsam genutzt werden kann, damit IPv6 für Ihren Mandanten aktiviert wird. Nachdem IPv6 aktiviert wurde, wird IPv6 standardmäßig verwendet, wenn das Programm, das Sie zum Herstellen einer Verbindung mit SharePoint Online verwenden, IPv6 unterstützt.
  
Wenn das Programm, das Sie zum Herstellen einer Verbindung mit SharePoint Online verwenden, IPv6 unterstützt, wird IPv6 standardmäßig für kabelgebundene und drahtlose Netzwerke verwendet. Wenn Sie die Kommunikation mit SharePoint Online steuern möchten, verwenden Sie die IP-Adressbereiche in Office 365 [URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md).
  
 **Office 365 Government G1/G3/G4/K1** Wenn das Programm, das Sie zum Herstellen einer Verbindung mit SharePoint Online verwenden, IPv6 unterstützt, wird standardmäßig versucht, IPv6 zu verwenden.
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business und IPv6

Bitte beachten Sie, dass IPv6 in den Skype for Business nicht mehr unterstützt wird und nicht mehr aktiviert werden kann.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams und IPV6

Microsoft Teams Direct Routing unterstützt nur IPv4. Der Microsoft Teams-Dienst und der Client unterstützen sowohl IPv4 als auch IPv6. Wenn Sie die Kommunikation mit Microsoft Teams steuern möchten, verwenden Sie die IP-Adressbereiche in Office 365 [URLs und IP-Adressbereichen](urls-and-ip-address-ranges.md).
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection und IPv6

Exchange Online Protection (EOP) unterstützt IPv6, wenn die Übertragung über das Transport Layer Security Protocol erfolgt. Verwenden Sie für den EOP-Bereich [Office 365 URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md).
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>IPv6-Unterstützung für Office 365 Government-Angebote

Office 365 Die IPv6-Unterstützung für Regierungsangebote entspricht dem Office of Management and Budget (OMB)-Memo für Chief Information Officers of Executive Departments and Agencies sowie dem Federal Government Adoption of Internet Protocol Version 6 (IPv6)-Memorandum. [Microsoft Office 365 für Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) ist ein mehr mandantenbasierter Dienst, der US-Regierungsdaten in einer getrennten Community-Cloud speichert. Wie andere Office 365 bietet es Dienste für Produktivität und Zusammenarbeit, einschließlich Exchange Online, Skype for Business, SharePoint Online und Microsoft 365 Apps for Enterprise. 

Die Microsoft Office 365 gelten nur für 2013 und höher. Weitere Informationen zu den Office 365 finden Sie unter [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414). International Traffic in Arms Regulations (ITAR) ist eine Reihe von US-Regierungsvorschriften, die den Export und Import von Verteidigungsartikeln und -diensten auf der [USML (United States Munitions List) steuern.](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 for Enterprises bietet dedizierte Hostingdienste für Microsoft-Produktivitätslösungen, die die Sicherheits-, Datenschutz- und behördlichen Complianceanforderungen für US-Bundesbehörden unterstützen, die eine Zertifizierung der Federal Information Security Management (FISMA) und kommerzielle Entitäten erfordern, die ITAR unterliegen.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Bei der Verwendung von IPv6 und Office 365

Es wird empfohlen, IPv6 nicht zu deaktivieren. Weitere Informationen finden Sie in diesem [Anleitungsartikel](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Berücksichtigen Sie folgendes, um zu bestimmen, welche IP-Versionen in Ihrem Netzwerk verwendet werden:
  
- Wenn die Anzeige des **Befehls IPConfig** an der Eingabeaufforderung Zeilen mit dem Namen "IPv6-Adresse" oder "Temporäre IPv6-Adresse" enthält, haben Sie IPv6 in Ihrer Umgebung.

- Wenn alle IPv6-Adressen mit "fe80" beginnen und Zeilen mit dem Namen "Link-Local IPv6 Address" entsprechen, verfügen Sie nicht über IPv6 in Ihrer Umgebung.

Diese Überlegungen können für Ihr Netzwerk gelten:
  
- Der öffentliche Abonnementdienst unterstützt den Kauf per Kreditkarte über IPv6 nicht. Dies gilt nicht für die Government Community Cloud (GCC), da Regierungen über Enterprise Agreement (EA)-Lizenzierung verfügen.

- IPv6 unterstützt einige Rights Management Services (RMS)-Szenarien nicht.

- IPv6 unterstützt BlackBerry® Enterprise Server (BES) nicht, da BlackBerry IPv6 nicht unterstützt.

- Wenn Sie Active Directory Federation Services (AD FS) mit Office 365 verwenden, wird die Werbung für Ihren AD FS-Netzwerkendpunkt Office 365 IPv6 nicht unterstützt. Sie sollten keine AAAA-Einträge in den AD FS-DNS-Eintrag bei verwendung von Exchange Online. 

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Weitere Artikel

[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6-Überlebenshandbuch](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)