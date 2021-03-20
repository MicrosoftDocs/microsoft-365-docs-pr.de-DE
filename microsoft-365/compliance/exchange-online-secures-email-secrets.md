---
title: Schützen von vertraulichen Inhalten in E-Mails mit Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Neben dem Office 365 Trust Center, das Sicherheits-, Datenschutz- und Complianceinformationen für Microsoft 365 bietet, sollten Sie wissen, wie Microsoft beim Schutz von geheimen Schlüsseln hilft, die Sie in ihren Rechenzentren speichern. Wir verwenden eine Technologie namens Distributed Key Manager (DKM).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906961"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Wie vertrauliche Daten in E-Mails in Exchange Online geschützt werden

In diesem Artikel wird beschrieben, wie Microsoft Ihre E-Mail-Schlüssel in ihren Rechenzentren sichert.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Wie sichern wir von Ihnen bereitgestellte geheime Informationen?

Neben dem Office 365 Trust Center, das Sicherheits-, Datenschutz- und Complianceinformationen für [Office 365](./get-started-with-service-trust-portal.md)bietet, möchten Sie vielleicht wissen, wie Microsoft beim Schutz von geheimen Daten unterstützt, die Sie in ihren Rechenzentren bereitstellen. Wir verwenden eine Technologie namens Distributed Key Manager (DKM).
  
[Der verteilte Schlüssel-Manager (Distributed Key Manager,](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) DKM) ist eine clientseitige Funktionalität, die eine Reihe von geheimen Schlüsseln zum Verschlüsseln und Entschlüsseln von Informationen verwendet. Nur Mitglieder einer bestimmten Sicherheitsgruppe in Active Directory Domain Services können auf diese Schlüssel zugreifen, um die durch DKM verschlüsselten Daten zu entschlüsseln. In Exchange Online sind nur bestimmte Dienstkonten, unter denen die Exchange-Prozesse ausgeführt werden, Teil dieser Sicherheitsgruppe. Im Rahmen der standardbetriebsprozedur im Datencenter erhalten keine Menschen Anmeldeinformationen, die Teil dieser Sicherheitsgruppe sind, und daher hat kein Mensch Zugriff auf die Schlüssel, die diese Geheimschlüssel entschlüsseln können.
  
Zum Debuggen, zur Problembehandlung oder zur Überwachung muss ein Rechenzentrumsadministrator erhöhten Zugriff anfordern, um temporäre Anmeldeinformationen zu erhalten, die Teil der Sicherheitsgruppe sind. Dieser Prozess erfordert mehrere Ebenen der rechtlichen Genehmigung. Wenn der Zugriff gewährt wird, werden alle Aktivitäten protokolliert und überwacht. Darüber hinaus wird der Zugriff nur für einen festgelegten Zeitraum gewährt, nach dem er automatisch abläuft.
  
Für zusätzlichen Schutz umfasst die DKM-Technologie das automatische Schlüsselrollover und die Archivierung. Dadurch wird auch sichergestellt, dass Sie weiterhin auf Ihre älteren Inhalte zugreifen können, ohne sich auf unbestimmte Zeit auf denselben Schlüssel verlassen zu müssen.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Wo nutzt Exchange Online DKM?

Microsoft verwendet [den Verteilten Schlüssel-Manager,](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) um Ihre Geheimschlüssel in Exchange Online-Rechenzentren zu verschlüsseln. Beispiel:
  
- E-Mail-Kontoanmeldeinformationen für verbundene Konten. Verbundene Konten sind Drittanbieterkonten wie Hotmail, Gmail und Yahoo! E-Mail-Konten.

- Kundenschlüssel. Wenn Sie die [Dienstverschlüsselung mit dem Kundenschlüssel](customer-key-overview.md)verwenden, verwenden Sie [Azure Key Vault,](/azure/key-vault/key-vault-whatis) um Ihre Geheimschlüssel zu schützen.

## <a name="related-topics"></a>Verwandte Themen

[Verschlüsselung in Office 365](encryption.md)
  
[Technische Details zur Verschlüsselung](technical-reference-details-about-encryption.md)
  
[Dienstsicherheit im Security &amp; Compliance Center](./service-assurance.md)
