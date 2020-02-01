---
title: Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Damit S/MIME-geschützte Nachrichten versendet werden können, müssen die entsprechenden Zertifikate eingerichtet werden. Zum Senden von verschlüsselten Nachrichten über Exchange Online verwendet das E-Mail-Programm das öffentliche Zertifikat des Empfängers, um die Nachricht zu verschlüsseln. Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598192"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME

Damit alle S/MIME-geschützten Nachrichten in Exchange Online gesendet werden können, müssen die entsprechenden Zertifikate eingerichtet sein. Zum Senden von verschlüsselten Nachrichten über Exchange Online verwendet die e-Mail-App des Absenders das öffentliche Zertifikat des Empfängers zum Verschlüsseln der Nachricht. Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.

## <a name="to-sync-certificates-that-support-smime"></a>So synchronisieren Sie Zertifikate, die S/MIME unterstützen

Richten Sie S/MIME ein, indem Sie Zertifikate ausgeben und diese in Ihrem lokalen Active Directory-Domänendienst veröffentlichen. Weitere Informationen finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Nachdem Ihre Zertifikate veröffentlicht wurden, verwenden Sie das Azure AD Connect-Tool, um Benutzerdaten aus Ihrer lokalen Exchange-Umgebung mit Office 365 zu synchronisieren. Weitere Informationen zu diesem Prozess finden Sie unter [Azure AD Connect Sync: Understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Zusammen mit dem Synchronisieren anderer Verzeichnisdaten für S/MIME-Zwecke synchronisiert das Tool die Attribute **userCertificate** und **userSMIMECertificate** für jedes Benutzerobjekt, damit die Daten zum Signieren und Verschlüsseln von Nachrichten verwendet werden können.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Was ist Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
