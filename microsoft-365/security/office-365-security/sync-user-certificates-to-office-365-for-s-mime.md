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
ms.openlocfilehash: 8c6d3968d617bcb503057c47567182091010c726
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290201"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Synchronisierung von Benutzerzertifikaten nach Office 365 für S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Bevor jemand S/MIME-geschützte Nachrichten in Exchange Online senden kann, müssen die entsprechenden Zertifikate eingerichtet werden. Um verschlüsselte Nachrichten über Exchange Online zu senden, verwendet die E-Mail-App des Absenders das öffentliche Zertifikat des Empfängers, um die Nachricht zu verschlüsseln. Dieses öffentliche X.509-Zertifikat muss in Office 365 veröffentlicht werden.

## <a name="to-sync-certificates-that-support-smime"></a>So synchronisieren Sie Zertifikate, die S/MIME unterstützen

Richten Sie S/MIME ein, indem Sie Zertifikate ausgeben und diese in Ihrem lokalen Active Directory-Domänendienst veröffentlichen. Weitere Informationen finden Sie unter [Active Directory-Zertifikatdienste: Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Nachdem Ihre Zertifikate veröffentlicht wurden, verwenden Sie das Azure AD Connect-Tool, um Benutzerdaten aus Ihrer lokalen Exchange-Umgebung mit Office 365 zu synchronisieren. Weitere Informationen zu diesem Prozess finden Sie unter [Azure AD Connect-Synchronisierung: Verstehen und Anpassen der Synchronisierung.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

Neben der Synchronisierung anderer Verzeichnisdaten synchronisiert das Tool für S/MIME-Zwecke die  **Attribute userCertificate** und **userSMIMECertificate** für jedes Benutzerobjekt, sodass die Daten zum Signieren und Verschlüsseln von Nachrichten verwendet werden können.

## <a name="more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)

[Was ist Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
