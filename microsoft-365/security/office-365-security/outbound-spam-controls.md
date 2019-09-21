---
title: Steuern ausgehender Spamnachrichten in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Wenn Ihre Organisation viele Massen-e-Mails sendet, die als Spam gekennzeichnet sind, können Sie das Senden von e-Mails mit Office 365 blockiert erhalten. Lesen Sie diesen Artikel, um mehr darüber zu erfahren, warum dies geschieht und was Sie dagegen tun können.
ms.openlocfilehash: 09aa71cd8b273a3235bc2673d3d17c3decf71da5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082419"
---
# <a name="controlling-outbound-spam-in-office-365"></a>Steuern ausgehender Spamnachrichten in Office 365

Wir nehmen die Verwaltung von ausgehenden Spam-Mails Ernst, weil unsere ein gemeinsamer Dienst ist.  Es gibt viele Kunden hinter einem gemeinsamen Pool von Ressourcen, bei dem ein Kunde ausgehende Spamnachrichten sendet, die ausgehende IP-Reputation des Diensts beeinträchtigen und die erfolgreiche Zustellung von e-Mails für andere Kunden beeinträchtigen kann.

> [!IMPORTANT]
> Die Benachrichtigung, wenn ein Absender eingeschränkt ist, ist nun Teil der Sicherheits #a0 Compliance Center-Benachrichtigungs Plattform (SCC). Anstatt die unten aufgeführten Methoden zum Senden von Benachrichtigungen zu verwenden, können Sie die Liste der Benutzer, die benachrichtigt werden sollen, in der Warnung "vom Senden von e-Mail eingeschränkter Benutzer" finden. Verwenden Sie die [Seite Warnungsrichtlinien](https://sip.protection.office.com/alertpolicies) im Security #a0 Compliance Center, um die Warnung zu konfigurieren, da die vorherige Methode in Zukunft entfernt wird. Erfahren Sie mehr über die neue [Benutzeroberfläche mit eingeschränkten Benutzern](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam). "

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Was Administratoren zum Steuern von ausgehenden Spam Aktionen tun können

- **Aktivieren von Benachrichtigungen, wenn ein Konto Spam sendet oder heruntergefahren wird**. Administratoren können Bcc abrufen, wenn eine Nachricht als ausgehender Spam markiert und über den hochriskanten Pool gesendet wird. Durch die Überwachung dieses Postfachs kann ein Administrator erkennen, ob er über ein kompromittiertes Konto in seinem Netzwerk verfügt oder ob der Spamfilter fälschlicherweise seine e-Mails als Spam markiert.  Weitere Informationen zum Einrichten der ausgehenden Spam Richtlinie finden Sie [hier](configure-the-outbound-spam-policy.md).
 
- **Manuelles Überprüfen von Spam Beschwerden von Drittanbieter-e-Mail-Anbietern**. Viele Drittanbieter-e-Mail-Dienste wie Outlook.com, Yahoo und AOL bieten eine Feedback Schleife, bei der ein Benutzer, der in seinem Dienst eine e-Mail von unserem Dienst als Spam markiert, die Nachricht verpackt und zur Überprüfung zurückgesendet wird. Weitere Informationen zur Absender Unterstützung für Outlook.com finden Sie [hier](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>Was EoP zum Steuern von ausgehenden Spam Aktionen tut 

1. **Trennung des ausgehenden Datenverkehrs in separate Pools von IPS**. Jede Nachricht, die Kunden über den Dienst ausgehend senden, wird auf Spam überprüft. Wenn es sich bei der Nachricht um Spam handelt, wird Sie über den Pool mit hoher Risikoverteilung weitergeleitet. Dieser IP-Pool enthält nichtzustellbare Statusbenachrichtigungen und Spam. Die Zustellung an den beabsichtigten Empfänger ist nicht gewährleistet, da viele Drittanbieter e-Mails nicht akzeptieren, da die Qualität der von ihr gesendeten e-Mails nicht akzeptiert wird.

Durch die Aufteilung des Datenverkehrs auf diese Weise wird sichergestellt, dass die e-Mails mit niedrigerer Qualität (Spam, Rückstreu-Unzustellbarkeitsberichte) die Reputation der regulären ausgehenden e-Mail-Pools nicht nach unten ziehen. Der Pool mit hohem Risiko hat in der Regel eine geringe Reputation bei vielen Empfängern rund um das Internet, obwohl dies nicht universell ist. 

2. **Überwachung der IP-Reputation**. Office 365 fragt verschiedene IP-blocklists von Drittanbietern ab und generiert Warnungen, wenn eines unserer ausgehenden IPS auf Ihnen aufgeführt ist. Auf diese Weise können wir schnell reagieren, wenn Spam unsere Reputation verschlechtert hat. Wenn eine Warnung generiert wird, haben wir eine interne Dokumentation, die die erforderlichen Schritte zum Abrufen der Delisting-Funktion unternimmt. 

3. **Deaktivieren von anstößigen Konten, wenn Sie zu viele e-Mails senden, die als Spam gekennzeichnet sind**. Auch wenn wir unsere Spam-und nicht-Spam-Mails in zwei getrennte ausgehende IP-Pools abtrennen, können die e-Mail-Konten nicht unbegrenzt Spam senden. Wir überwachen, welche Konten Spam senden, und wenn es einen nicht gebuchten Grenzwert überschreitet, wird das Konto vom Senden von Spam blockiert.

Eine einzelne Nachricht, die als Spam gekennzeichnet ist, kann eine falsche Klassifizierung des Spam Moduls sein und auch als falsch positives Ergebnis bezeichnet werden. Wir senden ihn über den High Risk-Pool, um ihm eine Chance zu geben, zu gehen; eine große Anzahl von Nachrichten in einem kurzen Zeitrahmen deutet jedoch auf ein Problem hin, und wenn dies geschieht, wird verhindert, dass das Konto weitere e-Mails sendet. Es gibt verschiedene Schwellenwerte für einzelne e-Mail-Konten sowie in aggregierter Form für den gesamten Mandanten.

4. **Deaktivieren von anstößigen Konten, wenn Sie zu viele e-Mails in einem zu kurzen Zeitrahmen senden**. Zusätzlich zu den oben genannten Grenzwerten, die nach einem Anteil von als Spam markierten Nachrichten suchen, gibt es auch Grenzwerte, mit denen Konten blockiert werden, wenn Sie einen Gesamtgrenzwert erreichen, unabhängig davon, ob die Nachrichten als Spam gekennzeichnet sind oder nicht. Der Grund für diesen Grenzwert liegt darin, dass ein kompromittiertes Konto den Zero-Day-Spam senden kann, der vom Spamfilter verpasst wird. Da es schwierig, wenn nicht gar unmöglich ist, manchmal den Unterschied zwischen einer legitimen Massen-e-Mail-Kampagne und einer massiven Spam Kampagne zu erkennen, werden diese Grenzwerte aktiviert, um potenzielle Schäden zu begrenzen.

> [!NOTE]
> Für #3 und #4 werben wir nicht für die genauen Grenzwerte.  Dadurch wird verhindert, dass Spammer das System spielen und sicherstellen, dass wir die Grenzwerte ändern können, wenn dies erforderlich ist. Die Grenzwertesind so hoch, dass ein durchschnittlicher Geschäftsbenutzer Sie nie erreichen wird und dass er den größten Teil des Schadens enthält, den ein Spammer zu beschädigen hat. 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Empfohlene Problemumgehungen für Kunden, die eine Vielzahl von e-Mails über EoP senden möchten

Es ist schwierig, ein Gleichgewichtzwischen Kunden zu finden, die eine große Anzahl von e-Mails senden möchten, und den Dienst vor kompromittierten Konten und Massen-e-Mails mit schlechten Listen Akquisitions Verfahren schützen. Auch hier ist die Kosten für eine ausgehende IP-Landung auf einer Drittanbieter-Sperrliste höher als das Blockieren eines Kunden vor dem Senden ausgehender e-Mails. Wie in der [Exchange Online-Dienstbeschreibung](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits)beschrieben, ist die Verwendung von EoP zum Senden von Massen-e-Mails keine unterstützte Nutzung des Diensts und nur auf der Grundlage einer "Best-Effort"-Basis zulässig. Für Kunden, die Massen-e-Mails senden möchten, wird Folgendes empfohlen:

a. **Senden Sie die Massen-e-Mails über eigene lokale e-Mail-Server**. Dies bedeutet, dass der Kunde seine eigene e-Mail-Infrastruktur für diesen e-Mail-Typ aufrecht erhalten muss.

b. **Verwenden Sie einen Drittanbieter-Massen-e-Mail, um die Massenkommunikation zu senden**. Es gibt mehrere Drittanbieter-Massen-e-Mails, deren einziges Geschäft es ist, Massen-e-Mails zu senden. Sie können mit Kunden zusammenarbeiten, um sicherzustellen, dass Sie über gute e-Mail-Methoden verfügen und Ressourcen für deren Durchsetzung bereitstellen. 

Die Arbeitsgruppe "Messaging, Mobile, Schadsoftware für Malware" (MAAWG) veröffentlicht [hier](http://www.maawg.org/about/roster)Ihr Mitgliederverzeichnis. Mehrere Massen-e-Mail-Anbieter befinden sich in der Liste und sind bekanntermaßen verantwortliche Internet Bürger. 
  
## <a name="for-more-information"></a>Weitere Informationen

[Beispiel Benachrichtigung, wenn ein Absender blockiert wird, der ausgehenden Spam sendet](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Antispamschutz für Office 365-E-Mails](anti-spam-protection.md)

[Antispoofingschutz in Office 365](anti-spoofing-protection.md)

[SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md)
