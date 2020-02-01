---
title: Deaktivieren der Junk-E-Mail-Berichterstattung in Outlook im Web
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Als Office 365 Administrator können Sie die Möglichkeit deaktivieren, dass Personen e-Mails als Junk-e-Mails melden.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598122"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Deaktivieren der Junk-E-Mail-Berichterstattung in Outlook im Web

Sie können Junk-e-Mails, Phishing-und nicht-Junk-Nachrichten zur Analyse mithilfe der Optionen für Junk-e-Mail-Berichte im Outlook im Internet (früher als Outlook Web App bezeichnet) senden, wie in [melden von Junk-e-Mails und Phishing-Scams in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)beschrieben. Wenn Sie diese Optionen nicht verwenden möchten, können Administratoren Sie über das Cmdlet "Cmdlet [festlegen-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) " deaktivieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?
<a name="sectionSection0"> </a>

- Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten

- Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Postfachrichtlinien für Outlook im Internet" in [Exchange Online Berechtigungen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Deaktivieren von Junk-, Phishing-und nicht-Junk-Berichten an Microsoft
<a name="sectionSection1"> </a>

Führen Sie zunächst den folgenden Befehl aus, um die Namen der verfügbaren Outlook im webpostfach-Richtlinien abzurufen:

```
Get-OwaMailboxPolicy | Format-Table Name
```

Verwenden Sie als nächstes die folgende Syntax, um Junk-und nicht-Junk-Berichte an Microsoft in Outlook im Internet zu aktivieren oder zu deaktivieren:

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

In diesem Beispiel wird die Berichterstellung in der standardmäßigen Outlook-Webanwendung-Postfachrichtlinie deaktiviert:

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) und [Sets-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?
<a name="sectionSection2"> </a>

Führen Sie **Get-OwaMailboxPolicy** aus, um die Parameterwerte zu überprüfen, und öffnen Sie dann Outlook im Internet für einen betroffenen Benutzer (auf den die Outlook im WebPost Fach Richtlinie angewendet wurde), und stellen Sie sicher, dass die Optionen zum Melden von Junk-, Phishing-und nicht-Junk-e-Mails nicht verfügbar sind. Sie können Nachrichten weiterhin als Junk, Phishing und nicht als Junk markieren, aber Sie können Sie nicht melden.
