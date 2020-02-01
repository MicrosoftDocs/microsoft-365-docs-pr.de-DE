---
title: Pool für besonders riskante Zustellungen für ausgehende Nachrichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Wenn das E-Mail-System eines Kunden durch Schadsoftware oder einen böswilligen Spamangriff kompromittiert wurde und ausgehende Spamnachrichten durch den gehosteten Filterdienst sendet, kann dies dazu führen, dass die IP-Adressen der Office 365-Server im Rechenzentrum in Blockierungslisten von Drittanbietern aufgenommen werden.
ms.openlocfilehash: 19987ae74b9c78a796ddb5f13cf8291a5ed269ad
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599232"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Pool für besonders riskante Zustellungen für ausgehende Nachrichten

Wenn das E-Mail-System eines Kunden durch Schadsoftware oder einen böswilligen Spamangriff kompromittiert wurde und ausgehende Spamnachrichten durch den gehosteten Filterdienst sendet, kann dies dazu führen, dass die IP-Adressen der Office 365-Server im Rechenzentrum in Blockierungslisten von Drittanbietern aufgenommen werden. Zielserver, die nicht den gehosteten Filterdienst, aber diese Sperrlisten verwenden, lehnen alle E-Mails ab, die von einer der gehosteten IP-Filterungsadressen gesendet werden, die diesen Listen hinzugefügt wurden. Um dies zu verhindern, werden alle ausgehenden Nachrichten, die den Spamschwellenwert überschreiten, über einen Pool für besonders riskante Zustellungen übermittelt. Dieser sekundäre Pool für ausgehende E-Mails wird nur zum Senden von Nachrichten mit möglicherweise schlechter Qualität gesendet werden. Dies dient dazu, dass der Rest des Netzwerks vor dem Versenden von Nachrichten geschützt wird, die mit höherer Wahrscheinlichkeit dazu führen, dass die sendende IP-Adresse gesperrt wird.
  
Indem ein dedizierter Pool für besonders riskante Zustellungen verwendet wird, wird dazu beigetragen, dass der normale Pool für ausgehende Nachrichten nur Nachrichten sendet, die bekanntermaßen von hoher Qualität sind. Mit diesem sekundären IP-Pool wird die Wahrscheinlichkeit verringert, dass der normale IP-Pool für ausgehende Nachrichten einer Sperrliste hinzugefügt wird. Es verbleibt das Risiko, dass der Pool für besonders riskante Zustellungen in eine Sperrliste aufgenommen wird. Dies ist so beabsichtigt.
  
Nachrichten, bei denen die sendende Domäne nicht über einen Adresseintrag (A-Datensatz) verfügt, der die IP-Adresse der Domäne enthält, und nicht über einen MX-Eintrag, mit dem E-Mails an die Server geleitet werden können, die die E-Mail für eine bestimmte Domäne im DNS erhalten sollen: Derartige Nachrichten werden stets durch den Pool für besonders riskante Zustellungen geleitet, unabhängig von ihrer Spameinschätzung.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>Grundlegendes zu Nachrichten für die Benachrichtigung über den Übermittlungsstatus (Delivery Status Notification, DSN)

Der Pool für besonders riskante Zustellungen für ausgehende Nachrichten verwaltet die Zustellung aller Nachrichten mit "Unzustellbar" oder "Fehler".
  
Mögliche Ursachen für einen Anstieg der DSN-Meldungen sind die folgenden:
  
- Eine Spoofingkampagne, die Auswirkungen auf einen Kunden des Diensts hat
    
- Ein Verzeichnisdiebstahl-Angriff (Directory Harvest Attack)
    
- Ein Spamangriff
    
- Ein nicht autorisierter SMTP-Server
    
Jedes dieser Probleme kann dazu führen, dass die Anzahl der DSN-Meldungen, die der Dienst verarbeitet, plötzlich ansteigt. Häufig werden diese DSN-Meldungen von anderen E-Mail-Servern und -Diensten als Spam klassifiziert.
  
## <a name="for-more-information"></a>Weitere Informationen

[Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md)
  
[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)
  

