---
title: Vorbereiten von TLS 1.2 in Office 365 und Office 365 GCC
description: Erläutert die Vorbereitung der Verwendung von TLS 1.2 für alle Client-Server- und Browser-Server-Kombinationen in Office 365 und Office 365 GCC, nachdem die Unterstützung für TLS 1.0 und 1.1 eingestellt wurde.
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
- Office 365 Business
ms.openlocfilehash: 4cc1fc739ee7fbcc4b976ae6e3f220713a53a007
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681657"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Vorbereiten von TLS 1.2 in Office 365 und Office 365 GCC

## <a name="summary"></a>Zusammenfassung

Um unseren Kunden die bestmögliche Verschlüsselung zu bieten, planen wir, die Unterstützung für die TLS-Versionen 1.0 und 1.1 (Transport Layer Security) in Microsoft Office 365 und Office 365 GCC bald einzustellen. Wir verstehen, dass die Sicherheit Ihrer Daten wichtig ist, und wir legen großen Wert auf Transparenz bezüglich Änderungen, die Ihre Nutzung des TLS-Dienstes beeinträchtigen könnten.

Die [Implementierung von Microsoft TLS 1.0](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) hat keine bekannten Sicherheitsschwachstellen. Aufgrund des Potenzials für zukünftige Protokoll-Downgrade-Angriffe und andere TLS-Sicherheitsschwachstellen stellen wir aber die Unterstützung für die Verwendung von TLS 1.0 und 1.1 in Office 365 und Office 365 GCC ein.

Informationen zum Entfernen von TLS 1.0- und 1.1-Abhängigkeiten finden Sie im folgenden Whitepaper: [Lösen des TLS 1.0-Problems](https://www.microsoft.com/download/details.aspx?id=55266).

## <a name="more-information"></a>Weitere Informationen

Wir haben bereits mit der Abschreibung von TLS 1.0 und 1.1 ab Januar 2020 begonnen. Clients, Geräte oder Dienste, die über TLS 1.0 oder 1.1 in unseren hohen DoD- oder GCC-Instanzen eine Verbindung zu Office 365 herstellen, werden nicht unterstützt. Für unsere kommerziellen Kunden von Office 365 wird der veraltete TLS 1,0 und 1,1 mit dem 15. Oktober beginnen, 2020, und der Rollout wird in den folgenden Wochen und Monaten fortgesetzt. 

Sie sollten sicherstellen, dass alle Client-Server- und Browser-Server-Kombinationen TLS 1.2 (oder höher) verwenden, um die Verbindung zu Office 365-Services aufrechtzuerhalten. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen.

Die folgenden Clients können TLS 1.2 nicht verwenden. Bitte aktualisieren Sie Ihre Clients, um einen unterbrechungsfreien Zugriff auf den Dienst sicherzustellen.

- Android 4.3 und niedrigere Versionen
- Firefox Version 5.0 und frühere Versionen
- Internet Explorer 8-10 auf Windows 7 und frühere Versionen
- Internet Explorer 10 auf Windows Phone 8
- Safari 6.0.4/OS X10.8.4 und frühere Versionen

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 für Microsoft Teams Rooms und Surface Hub

Microsoft Teams Rooms (früher bekannt als Skype Room System V2 SRS V2) unterstützen TLS 1.2 seit Dezember 2018. Es wird empfohlen, dass Rooms-Geräte Microsoft Teams Rooms-App Version 4.0.64.0 oder höher installiert haben. Weitere Informationen finden Sie in den folgenden [Release-Informationen](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note). Die Änderungen sind rückwärts- und vorwärtskompatibel.

Surface Hub hat im Mai 2019 TLS 1.2-Unterstützung veröffentlicht.

Die TLS 1.2-Unterstützung für Microsoft Teams Rooms- und Surface Hub-Produkte erfordert außerdem die folgenden serverseitigen Codeänderungen:

- Die Serveränderungen von Skype for Business Online wurden im April 2019 live vorgenommen. Skype for Business Online unterstützt jetzt die Verbindung von Microsoft Teams Rooms und Surface Hub-Geräten mithilfe von TLS 1.2.
- Skype for Business Server-Kunden müssen ein kumulatives Update (CU) installieren, um TLS 1.2 für Teams Rooms Systems und Surface Hub verwenden zu können.

  - Für Skype for Business Server 2015 wird CU9 bereits im Mai 2019 veröffentlicht.
  - Für Skype for Business Server 2019 war CU1 ursprünglich für April 2019 geplant, verzögert sich jedoch auf Juni 2019.

  > [!NOTE]
  > Lokale Skype for Business-Kunden sollten TLS 1.0/1.1 nicht deaktivieren, bevor Sie bestimmte CUs für Skype for Business Server installieren.

Wenn Sie eine lokale Infrastruktur für Hybrid-Szenarien oder Active Directory-Verbunddienste verwenden, stellen Sie sicher, dass die Infrastruktur sowohl eingehende als auch ausgehende Verbindungen, die TLS 1.2 verwenden, unterstützen kann.

## <a name="references"></a>Informationsquellen

Die folgenden Ressourcen bieten Hilfe, um sicherzustellen, dass Ihre Clients TLS 1.2 oder eine höhere Version verwenden und um TLS 1.0 und 1.1 zu deaktivieren.

- Wenn Sie Windows-7-Clients haben, die mit Office 365 verbunden sind, stellen Sie sicher, dass TLS 1.2 die standardmäßigen sicheren Protokolle in WinHTTP in Windows sind. Weitere Informationen finden Sie unter [KB 3140245 - Update für die Aktivierung von TLS 1.1 und TLS 1.2 als standardmäßige sichere Protokolle in WinHTTP unter Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- Informationen zum Umgang mit schwacher TLS-Nutzung durch das Entfernen der Abhängigkeiten von TLS 1.0 und 1.1 finden Sie unter [TLS 1.2-Support bei Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [Die neue IIS-Funktionalität](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) erleichtert die Suche nach Clients unter [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) und [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334), die unter Verwendung von schwachen Sicherheitsprotokollen eine Verbindung mit dem Dienst herstellen.
- Hier erhalten Sie weitere Informationen zur [Lösung des TLS 1,0-Problems](https://www.microsoft.com/download/details.aspx?id=55266).
- Allgemeine Informationen zu unserem Sicherheits-Ansatz finden Sie im [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Vorbereiten auf die Einstellung von TLS 1.0/1.1 – Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS-Leitfaden Teil 2: Enabling TLS 1.2 and Identifying Clients Not Using It](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS-Leitfaden Teil 3: TLS 1.0/1.1 abschalten](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Aktivieren des TLS 1.1- und TLS 1.2-Supports in Office Online-Server](https://docs.microsoft.com/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
