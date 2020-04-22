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
description: Neben dem Office 365 Trust Center, das Informationen zu Sicherheit, Datenschutz und Compliance für Microsoft 365 bereitstellt, möchten Sie vielleicht wissen, wie Microsoft Geheimnisse schützt, die Sie in ihren Rechenzentren speichern. Wir verwenden eine Technologie namens Distributed Key Manager (DKM).
ms.openlocfilehash: 17a7fbbd54a725edcd87681f011ddc6633a1f4aa
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615979"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Wie vertrauliche Daten in E-Mails in Exchange Online geschützt werden

In diesem Artikel wird beschrieben, wie Microsoft Ihre e-Mail-Geheimnisse in ihren Rechenzentren sichert.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Wie sichern wir geheime Informationen, die von Ihnen bereitgestellt werden?

Neben dem Office 365 Trust Center, das Informationen zu [Sicherheit, Datenschutz und Compliance für Office 365](https://go.microsoft.com/fwlink/?linkid=874644)bereitstellt, sollten Sie wissen, wie Microsoft die in den Rechenzentren bereitgestellten Geheimnisse schützt. Wir verwenden eine Technologie namens Distributed Key Manager (DKM).
  
[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) ist eine clientseitige Funktionalität, die eine Reihe von geheimen Schlüsseln zum Verschlüsseln und Entschlüsseln von Informationen verwendet. Nur Mitglieder einer bestimmten Sicherheitsgruppe in Active Directory-Domänendienste können auf diese Schlüssel zugreifen, um die von DKM verschlüsselten Daten zu entschlüsseln. In Exchange Online sind nur bestimmte Dienstkonten, unter denen die Exchange-Prozesse ausgeführt werden, Teil dieser Sicherheitsgruppe. Im Rahmen des standardmäßigen betriebsverfahrens im Rechenzentrum werden keinem Menschen Anmeldeinformationen zugewiesen, die Teil dieser Sicherheitsgruppe sind, und daher hat kein Mensch Zugriff auf die Schlüssel, die diese Geheimnisse entschlüsseln können.
  
Zum Debuggen, zur Problembehandlung oder zu Überwachungszwecken muss ein Rechenzentrums Administrator erhöhten Zugriff anfordern, um temporäre Anmeldeinformationen zu erhalten, die Teil der Sicherheitsgruppe sind. Für diesen Prozess sind mehrere Ebenen der rechtlichen Genehmigung erforderlich. Wenn der Zugriff gewährt wird, werden alle Aktivitäten protokolliert und überwacht. Darüber hinaus wird der Zugriff nur für ein festgelegtes Zeitintervall gewährt, nach dem es automatisch abläuft.
  
Für zusätzlichen Schutz umfasst die DKM-Technologie einen automatisierten Schlüssel Rollover und eine Archivierung. Dadurch wird auch sichergestellt, dass Sie weiterhin auf Ihre älteren Inhalte zugreifen können, ohne sich auf unbestimmte Zeit auf denselben Schlüssel verlassen zu müssen.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Wo verwendet Exchange Online DKM?

Microsoft verwendet den [verteilten Schlüssel-Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) , um ihre Geheimnisse in Exchange Online-Rechenzentren zu verschlüsseln. Beispiel:
  
- E-Mail-Kontoanmeldeinformationen für verbundene Konten. Verbundene Konten sind Drittanbieter Konten wie Hotmail, Gmail und Yahoo!. e-Mail-Konten.

- Kundenschlüssel. Wenn Sie die [Dienst Verschlüsselung mit dem Kundenschlüssel](customer-key-overview.md)verwenden, verwenden Sie [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) , um ihre Geheimnisse zu schützen.

## <a name="related-topics"></a>Verwandte Themen

[Verschlüsselung in Office 365](encryption.md)
  
[Technische Referenzdetails zur Verschlüsselung](technical-reference-details-about-encryption.md)
  
[Dienst Assurance im Security &amp; Compliance Center](https://go.microsoft.com/fwlink/?linkid=874645)
  

