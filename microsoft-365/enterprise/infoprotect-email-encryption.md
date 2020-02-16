---
title: 'Schritt 6: Konfigurieren der E-Mail-Verschlüsselung'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Verstehen und Konfigurieren von Privileged Access Management für Office 365.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067184"
---
# <a name="step-6-configure-email-encryption"></a>Schritt 6: Konfigurieren der E-Mail-Verschlüsselung

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Es gibt drei Arten von e-Mail-Verschlüsselung in Microsoft 365.

|||
|:-------|:-----|
| Office-Nachrichtenverschlüsselung (Office Message Encryption, OME) | Verschlüsselung für Exchange Online e-Mails, die außerhalb Ihrer Organisation gesendet werden. |
| Verwaltung von Informationsrechten (Information Rights Management, IRM) | Verschlüsselung und Berechtigungen, die mit der e-Mail Reisen. |
| Secure/Multipurpose Internet Mail Extensions (S/MIME) | E-Mail-Schutz mit Verschlüsselung und digitaler Signatur. |
|||

## <a name="office-365-message-encryption"></a>Office 365-Nachrichtenverschlüsselung

Mit OM kann Ihre Organisation verschlüsselte e-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. OM kann mit Outlook.com, Yahoo!, Gmail und anderen e-Mail-Diensten verwendet werden. Die e-Mail-Nachrichtenverschlüsselung hilft sicherzustellen, dass nur vorgesehene Empfänger die Nachricht anzeigen können.

![OM-Verschlüsselung von e-Mail-Nachrichten](../media/infoprotect-email-encryption/ome-encryption.png)

Sie richten Transportregeln ein, die die Bedingungen für die Verschlüsselung definieren. Wenn ein Benutzer eine Nachricht sendet, die mit einer Regel übereinstimmt, wird die Verschlüsselung automatisch angewendet.

Um verschlüsselte Nachrichten anzuzeigen, können Empfänger entweder einen einmaligen Zugangscode erhalten, sich mit einem Microsoft-Konto anmelden oder sich mit einem Arbeits-oder Schulkonto anmelden, das Microsoft 365 zugeordnet ist. Empfänger können auch verschlüsselte Antworten senden. Sie benötigen kein eigenes Microsoft 365-Abonnement, um verschlüsselte Nachrichten anzuzeigen oder verschlüsselte Antworten zu senden.

Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).

## <a name="irm"></a>IRM

IRM in Microsoft 365 hilft Ihnen bei der Sicherung Ihrer Informationen mit zusätzlicher Verschlüsselung und durch Anwendung einer intelligenten Richtlinie, die angibt, wer Zugriff hat, was Sie tun können. Bei e-Mail-Nachrichten können Sie IRM für die Verschlüsselung verwenden und Nutzungseinschränkungen anwenden. Sie können beispielsweise angeben, dass einige Empfänger über alle Möglichkeiten zum Verwalten der e-Mail verfügen und andere nicht die Möglichkeit haben, die e-Mail zu drucken oder weiterzuleiten. 

IRM-Richtlinien werden in Microsoft 365 konfiguriert und können auf Dokumente in SharePoint Online und e-Mail-Nachrichten angewendet werden. Eine durch IRM geschützte e-Mail enthält die angewendeten Richtlinieneinstellungen, die angewendet werden und mit der Sie Reisen. 

![IRM-Schutz für e-Mail-Nachrichten](../media/infoprotect-email-encryption/irm-protection.png)

Wenn der Empfänger die e-Mail mit der eingeschlossenen Richtlinie öffnet, werden die Richtlinieneinstellungen verwendet, um die Nachricht zu entschlüsseln und festzulegen, was der Empfänger damit tun kann. 

Weitere Informationen finden Sie unter [Verwaltung von Informationsrechten in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).

## <a name="smime"></a>S/MIME

S/MIME ist eine digitale zertifikatbasierte e-Mail-basierte Schutzlösung, mit der Sie eine Nachricht sowohl verschlüsseln als auch digital signieren können. Die Nachrichtenverschlüsselung hilft Ihnen bei der Sicherstellung, dass nur der beabsichtigte Empfänger die Nachricht öffnen und lesen kann. Eine digitale Signatur hilft dem Empfänger, die Identität des Absenders zu überprüfen und festzustellen, ob der Absender ihn nur gesendet hätte.

![S/MIME-Schutz für e-Mail-Nachrichten](../media/infoprotect-email-encryption/smime-protection.png)

S/MIME kann für e-Mails an andere Postfächer in Ihrem Microsoft 365-Abonnement oder für externe Benutzer verwendet werden.
Sowohl Nachrichtenverschlüsselung als auch digitale Signaturen werden mithilfe digitaler Zertifikate ermöglicht, die die öffentlichen und privaten Schlüssel zum Verschlüsseln oder Entschlüsseln von Nachrichten sowie zum Erstellen und Überprüfen digitaler Signaturen enthalten.
Damit S/MIME verwendet werden kann, müssen Sie über die öffentlichen Schlüssel für jeden Empfänger verfügen. Empfänger verwalten ihre eigenen privaten Schlüssel, die sicher bleiben müssen. Wenn Ihr privater Schlüssel kompromittiert ist, müssen Sie ein neues digitales Zertifikat erhalten und öffentliche Schlüssel auf alle potenziellen Absender verteilen.

Weitere Informationen finden Sie unter [S/MIME für die Nachrichtensignierung und -verschlüsselung](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).


Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step6) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 7](../media/stepnumbers/Step7.png)|[Konfigurieren von Privileged Access Management für Office 365](infoprotect-configure-privileged-access-management.md)|
