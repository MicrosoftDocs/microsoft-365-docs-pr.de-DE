---
title: Was ist EoP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Dieses Einführungsdokument hilft Ihnen, Exchange Online Schutz (EoP) und einige wichtige Terminologie zu verstehen. Dies gilt für Kunden, die Exchange Online in der Cloud gehosteten Postfächern und EOP-eigenständigen Kunden schützen, die lokale Postfächer wie Exchange Server 2016 schützen.
ms.openlocfilehash: dc08507a80db8e15d2e08ff5b954dec1905cfada
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630917"
---
# <a name="what-is-exchange-online-protection-eop"></a>Was ist Exchange Online Schutz (EoP)

Exchange Online Protection (EoP) ist ein Cloud-basierter e-Mail-Filterdienst, der Ihre Organisation vor Spam und Schadsoftware schützen kann. Wenn Sie über Postfächer in Microsoft 365 verfügen, werden diese automatisch von EoP geschützt, da Sie Teil des Diensts sind. Dies umfasst Organisationen mit Postfächern sowohl in Microsoft 365 als auch in lokalen, was gemeinhin als Hybrid Szenario bezeichnet wird. EoP Standalone steht auch Kunden zur Verfügung, die keine Postfächer in der Cloud haben, aber ihre lokalen Postfächer schützen möchten.

EoP versucht, Junk zu filtern, sodass Ihr Posteingang die Inhalte frei hält, die Benutzer nicht sehen möchten. Normalerweise werden Junk-e-Mails an den Junk-e-Mail-Ordner zugestellt. Einige Benutzer möchten sicherstellen, dass die Filterung das tut, was Sie möchten, damit der Junk-e-Mail-Ordner eine einfache Möglichkeit für Benutzer ist, sich selbst zu überprüfen.  

> [!TIP]
> Es ist eine gute Sache, wenn Junk-oder anderweitig ungültige e-Mails automatisch in den Junk-e-Mail-Ordner eingeht. Der Dienst tut, was erforderlich ist, basierend auf dem Status des Standard-oder benutzerdefinierten Administratoreinstellungen. In anderen Worten: Benutzer sollten sich keine Gedanken darüber machen, wie viele Spamnachrichten im Junk-e-Mail-Ordner angezeigt werden. Wenn Administratoren alle Junk-e-Mails aus dem Blickfeld ziehen möchten, sollte die Quarantäne konfiguriert werden. Weitere Informationen finden Sie im Artikel [Quarantäne-e-Mail-Nachrichten](quarantine-email-messages.md) .

## <a name="important-terms"></a>Wichtige Begriffe

**Eingehend**: Nachrichten, die in Microsoft 365 kommen.

**Outbound**: Nachrichten, die von Microsoft 365 ausgehen.

**Intern**: Nachrichten, die von einer Person innerhalb der Organisation an eine Person innerhalb der Organisation gesendet werden. Dies umfasst Kunden, die sich in Hybrid Szenarien befinden, und ein Postfach könnte lokal sein, und das andere Postfach befindet sich in der Cloud.

**Falsch negativ (FN)**: Spam und anderer Junk, der fälschlicherweise in den Posteingang gesendet wird.

**Falsch positiv (FP)**: legitime Nachrichten, die fälschlicherweise als Spam markiert und in den Junk-e-Mail-Ordner oder in die Quarantäne verschoben werden.

**Spam, auch als unerbetene e-Mail bezeichnet**: Dies erfolgt in Form von kommerzieller Werbung, Kettenbriefen, politischen Mailings usw. Hierbei handelt es sich um e-Mails, die Benutzer nicht für und von Spammern registrieren, die versuchen, Produkte anzufordern oder Betrugsversuche zu begehen.

**Phishing**: Phishing ist eine spezielle Art von Spam, die Sie dazu verleiten soll, persönliche Informationen zum Zwecke des Identitätsdiebstahls oder Betrugs zu verbieten. Dieser Nachrichtentyp enthält normalerweise einen böswilligen Link oder eine Anlage, jedoch nicht immer.

**Spoofing**: Spoofing ist, wenn Spammer die From-Kopfzeile fälschen, sodass Nachrichten von einer Person oder einem anderen als der tatsächlichen Quelle stammen. Dies kann Spam sein, wird aber am häufigsten für Phishing-Benutzer verwendet.

**Identitätswechsel**: diese Art von Spam ist auch eine Möglichkeit, die Absenderadresse zu fälschen, aber Sie erfolgt durch Ändern eines Teils des Namens oder der Domäne, sodass Sie wie die reale Quelle aussieht. Beispiel: Bi11@micr0s0ft.com, wobei das "l" in Bill tatsächlich die Zahl "11" und das "o" in Microsoft wurde durch die Zahl Null ersetzt.

**Bulk**: Massen-e-Mails werden normalerweise von Benutzern angefordert, auch wenn Unternehmen manchmal indirekt Informationen an andere Unternehmen verkaufen. Es ist üblich, dass sich Benutzer absichtlich für Massen-e-Mails (d. h. Briefsendungen) registrieren, aber später vergessen und denken, dass es sich um Spam handelt. Massen-e-Mails werden zu Spam, wenn Massen-e-Mail-Nachrichten mehr senden als Benutzer registrieren und die Reklamations Stufe zu hoch wird.
