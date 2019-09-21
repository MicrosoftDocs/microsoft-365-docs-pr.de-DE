---
title: Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME
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
ms.openlocfilehash: ad58b5663eaadf771ed1518edc01ce2f765f5202
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082626"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME

Damit alle S/MIME-geschützten Nachrichten in Exchange Online gesendet werden können, müssen die entsprechenden Zertifikate eingerichtet sein. Zum Senden von verschlüsselten Nachrichten über Exchange Online verwendet die e-Mail-App des Absenders das öffentliche Zertifikat des Empfängers zum Verschlüsseln der Nachricht. Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.

## <a name="to-sync-certificates-that-support-smime"></a>So synchronisieren Sie Zertifikate, die S/MIME unterstützen

Richten Sie S/MIME ein, indem Sie Zertifikate ausgeben und diese in Ihrem lokalen Active Directory-Domänendienst veröffentlichen. Weitere Informationen zum Verwalten von Zertifikaten in Exchange Server finden Sie unter [digitale Zertifikate und SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).

Nachdem Ihre Zertifikate veröffentlicht wurden, verwenden Sie Azure Active Directory-Synchronisierungstool, um Benutzerdaten aus der lokalen Exchange-Umgebung mit Office 365 zu synchronisieren. Weitere Informationen zu diesem Prozess finden Sie unter [DirSync: Versionsverlauf für das Verzeichnissynchronisierungstool](https://go.microsoft.com/fwlink/p/?LinkId=392587).

Zusammen mit dem Synchronisieren anderer Verzeichnisdaten für S/MIME-Zwecke synchronisiert das Tool die Attribute **userCertificate** und **userSMIMECertificate** für jedes Benutzerobjekt, damit die Daten zum Signieren und Verschlüsseln von Nachrichten verwendet werden können.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Azure Active Directory-Synchronisierungstool](https://go.microsoft.com/fwlink/p/?LinkId=392587)
