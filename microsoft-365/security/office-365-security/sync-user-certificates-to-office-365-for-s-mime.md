---
title: Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie geeignete Zertifikate in Office 365 veröffentlichen, bevor Sie S/MIME-geschützte Nachrichten in Exchange Online senden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916454"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Bevor jeder S/MIME-geschützte Nachrichten in Exchange Online senden kann, müssen die entsprechenden Zertifikate eingerichtet werden. Zum Senden verschlüsselter Nachrichten über Exchange Online verwendet die E-Mail-App des Absenders das öffentliche Zertifikat des Empfängers, um die Nachricht zu verschlüsseln. Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.

## <a name="to-sync-certificates-that-support-smime"></a>So synchronisieren Sie Zertifikate, die S/MIME unterstützen

Richten Sie S/MIME ein, indem Sie Zertifikate ausgeben und diese in Ihrem lokalen Active Directory-Domänendienst veröffentlichen. Weitere Informationen finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Nachdem Ihre Zertifikate veröffentlicht wurden, verwenden Sie das Azure AD Connect-Tool, um Benutzerdaten aus Ihrer lokalen Exchange-Umgebung mit Office 365 zu synchronisieren. Weitere Informationen zu diesem Prozess finden Sie unter [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Neben der Synchronisierung anderer Verzeichnisdaten für S/MIME-Zwecke synchronisiert das Tool die  **Attribute userCertificate** und **userSMIMECertificate** für jedes Benutzerobjekt, sodass die Daten zum Signieren und Verschlüsseln von Nachrichten verwendet werden können.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Was ist Azure AD Connect?](/azure/active-directory/hybrid/whatis-azure-ad-connect)