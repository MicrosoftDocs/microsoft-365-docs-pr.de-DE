---
title: Pools für die Zustellung ausgehender Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie die Übermittlungspools verwendet werden, um den Ruf von E-Mail-Servern in den Microsoft 365 Rechenzentren zu schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137718"
---
# <a name="outbound-delivery-pools"></a>Pools für die Zustellung ausgehender Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-Mail-Server in den Microsoft 365 Rechenzentren sind möglicherweise vorübergehend unerschnaufend für das Senden von Spam. Beispielsweise ein Schadsoftware- oder bösartiger Spamangriff in einer lokalen E-Mail-Organisation, die ausgehende E-Mails über Microsoft 365 sendet, oder kompromittierte Microsoft 365 Konten. Angreifer versuchen auch, die Erkennung zu vermeiden, indem sie Nachrichten über Microsoft 365 Weiterleitung weiterleiten.

Diese Szenarien können dazu führen, dass die IP-Adresse der betroffenen Microsoft 365 Rechenzentrumsservern auf Blocklisten von Drittanbietern angezeigt wird. Ziel-E-Mail-Organisationen, die diese Sperrlisten verwenden, weisen E-Mails aus diesen Nachrichtenquellen zurück.

## <a name="high-risk-delivery-pool"></a>Übermittlungspool mit hohem Risiko
Um dies zu verhindern, werden alle ausgehenden Nachrichten von Microsoft 365 Rechenzentrumsservern, die als Spam eingestuft werden oder die Sendegrenzwerte [der Dienst-](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder [ausgehenden Spamrichtlinien](configure-the-outbound-spam-policy.md) überschreiten, über den _Übermittlungspool mit hohem Risiko_ gesendet.

Der Übermittlungspool mit hohem Risiko ist ein separater IP-Adresspool für ausgehende E-Mails, der nur zum Senden von Nachrichten mit niedriger Qualität verwendet wird (z. B. Spam und [Rückscatter).](backscatter-messages-and-eop.md) Die Verwendung des Übermittlungspools mit hohem Risiko verhindert, dass der normale IP-Adresspool für ausgehende E-Mails Spam sendet. Der normale IP-Adresspool für ausgehende E-Mails behält die Zuverlässigkeit beim Senden von Nachrichten mit hoher Qualität bei, wodurch die Wahrscheinlichkeit reduziert wird, dass diese IP-Adresse in IP-Sperrlisten angezeigt wird.

Die sehr reale Möglichkeit, dass IP-Adressen im Übermittlungspool mit hohem Risiko in IP-Sperrlisten platziert werden, bleibt bestehen, aber dies ist beabsichtigt. Die Zustellung an die beabsichtigten Empfänger ist nicht garantiert, da viele E-Mail-Organisationen keine Nachrichten aus dem Übermittlungspool mit hohem Risiko akzeptieren.

Weitere Informationen finden Sie unter [Steuern ausgehender Spamnachrichten.](outbound-spam-controls.md)

> [!NOTE]
> Nachrichten, bei denen die Quell-E-Mail-Domäne keinen A-Eintrag und keinen im öffentlichen DNS definierten MX-Eintrag aufweist, werden immer über den Übermittlungspool mit hohem Risiko weitergeleitet, unabhängig von ihrer Spam- oder Sendelimitdisposition.

### <a name="bounce-messages"></a>Unzustellbarkeitsnachrichten

Der Übermittlungspool mit hohem Risiko für ausgehende Nachrichten verwaltet die Zustellung für alle Unzustellbarkeitsberichte (auch als Unzustellbarkeitsberichte, Unzustellbarkeitsnachrichten, Benachrichtigungen zum Zustellungsstatus oder DSNs bezeichnet).

Mögliche Ursachen für einen Anstieg in NDRs sind:

- Eine Spoofingkampagne, die einen der Kunden betrifft, die den Dienst verwenden.
- Ein Verzeichnisernteangriff.
- Ein Spamangriff.
- Ein nicht autorisierter E-Mail-Server.

All diese Probleme können zu einem plötzlichen Anstieg der Anzahl von NDRs führen, die vom Dienst verarbeitet werden. Häufig werden diese Unzustellbarkeitsberichte als Spam an andere E-Mail-Server und -Dienste (auch als _[Rückscatter](backscatter-messages-and-eop.md)_ bezeichnet) angezeigt.


### <a name="relay-pool"></a>Relaypool

Nachrichten, die in bestimmten Szenarien über Microsoft 365 weitergeleitet oder weitergeleitet werden, werden mithilfe eines speziellen Relaypools gesendet, da das Ziel Microsoft 365 nicht als tatsächlicher Absender betrachten sollte. Es ist wichtig, dass wir diesen E-Mail-Datenverkehr isolieren, da es legitime und ungültige Szenarien für die automatische Weiterleitung oder Weiterleitung von E-Mails aus Microsoft 365 gibt. Ähnlich wie beim Übermittlungspool mit hohem Risiko wird ein separater IP-Adresspool für weitergeleitete E-Mails verwendet. Dieser Adresspool wird nicht veröffentlicht, da er sich häufig ändern kann und nicht Teil des veröffentlichten SPF-Eintrags für Microsoft 365 ist.

Microsoft 365 muss überprüfen, ob der ursprüngliche Absender legitim ist, damit wir die weitergeleitete Nachricht sicher übermitteln können.

Die weitergeleitete/weitergeleitete Nachricht sollte eines der folgenden Kriterien erfüllen, um die Verwendung des Relaypools zu vermeiden:

- Der ausgehende Absender befindet sich in einer [akzeptierten Domäne.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- SPF wird übergeben, wenn die Nachricht an Microsoft 365 kommt.
- DKIM in der Absenderdomäne wird übergeben, wenn die Nachricht an Microsoft 365 kommt.
 
Sie können feststellen, dass eine Nachricht über den Relaypool gesendet wurde, indem Sie sich die IP des ausgehenden Servers ansehen (der Relaypool befindet sich im Bereich 40.95.0.0/16) oder indem Sie sich den Namen des ausgehenden Servers ansehen (der Name enthält "rly").

In Fällen, in denen wir den Absender authentifizieren können, verwenden wir Sender Rewriting Scheme (SRS), um dem Empfänger-E-Mail-System zu helfen, zu wissen, dass die weitergeleitete Nachricht von einer vertrauenswürdigen Quelle stammt. Sie können mehr darüber erfahren, wie dies funktioniert und was Sie tun können, um sicherzustellen, dass die sendende Domäne die Authentifizierung im [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme)besteht.

Damit DKIM funktioniert, stellen Sie sicher, dass Sie DKIM für das Senden einer Domäne aktivieren. Beispielsweise ist fabrikam.com Teil von contoso.com und in den akzeptierten Domänen der Organisation definiert. Wenn der Absender der Nachricht sender@fabrikam.com ist, muss DKIM für fabrikam.com aktiviert werden. Sie können lesen, wie Sie bei [Verwendung von DKIM aktivieren können, um ausgehende E-Mails zu überprüfen, die von Ihrer benutzerdefinierten Domäne gesendet wurden.](use-dkim-to-validate-outbound-email.md)

Führen Sie die Schritte unter [Hinzufügen einer Domäne zu Microsoft 365 aus, um eine](../../admin/setup/add-domain.md)benutzerdefinierte Domäne hinzuzufügen.
