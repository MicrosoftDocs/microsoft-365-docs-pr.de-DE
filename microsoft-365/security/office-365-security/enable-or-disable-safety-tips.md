---
title: Aktivieren oder Deaktivieren von Sicherheitstipps in Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Teilt Office 365-und EOP-Administratoren mit, wie Sicherheitstipps in e-Mail-Nachrichten aktiviert und deaktiviert werden.
ms.openlocfilehash: ae8a3bc9811aa54b0c5ae4cc8a0e2eb9aa80aef0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086249"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Aktivieren oder Deaktivieren von Sicherheitstipps in Office 365

Exchange Online Schutz (EoP) fügt einen Sicherheitshinweis zu e-Mail-Nachrichten hinzu, die von ihm übermittelt werden. Diese Sicherheitstipps bieten Empfängern eine schnelle und visuelle Möglichkeit, um festzustellen, ob eine Nachricht von einem sicheren, verifizierten Absender stammt, wenn die Nachricht von Office 365 als Spam gekennzeichnet wurde, wenn die Nachricht etwas Verdächtiges wie einen Phishing-Betrug enthält oder wenn externe Bilder blockiert. Office 365-und EOP-eigenständige Administratoren können eine Spam Richtlinieneinstellung bearbeiten, um zu aktivieren oder zu deaktivieren, dass Sicherheitstipps in e-Mails in Outlook und anderen Desktop-e-Mail-Clients nicht angezeigt werden.

Office 365 aktiviert standardmäßig Sicherheitstipps für Ihre Organisation, und es wird empfohlen, dass Sie diese aktiviert lassen, um Spam-und Phishing-Angriffe zu bekämpfen. Sicherheitstipps für Outlook im Internet können nicht deaktiviert werden.

Beispiele und Informationen zu den unter Sicherheitstipps angezeigten Informationen finden Sie unter [Sicherheitstipps in e-Mail-Nachrichten in Office 365.](safety-tips-in-office-365.md)

Inhalt dieses Themas:

- [So aktivieren oder deaktivieren Sie Sicherheitstipps mithilfe des Office 365 Security &amp; Compliance Center](enable-or-disable-safety-tips.md#SandCCsafetytip)

- [So aktivieren oder deaktivieren Sie Sicherheitstipps mithilfe von PowerShell](enable-or-disable-safety-tips.md#pshellsafetytip)

## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>So aktivieren oder deaktivieren Sie Sicherheitstipps mithilfe des Office 365 Security &amp; Compliance Center
<a name="SandCCsafetytip"> </a>

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).

2. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.

3. Wählen Sie **Bedrohungs Verwaltungs** \> **Richtlinie**aus.

4. Wählen Sie auf der Seite **Richtlinie** **Anti-Spam**aus.

    ![In diesem Screenshot wird gezeigt, wie Sie zur Seite Antispameinstellungen im Security &amp; Compliance Center gelangen.](../../media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)

5. Wählen Sie auf der Seite **Anti-Spam-Einstellungen** die Registerkarte **Benutzerdefiniert** aus.

    ![Dieser Screenshot zeigt den Speicherort der benutzerdefinierten Registerkarte auf der Seite Anti-Spam-Einstellungen im &amp; Security Compliance Center.](../../media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)

6. Wählen Sie bei Bedarf die Option **benutzerdefinierte Einstellungen** aus, um benutzerdefinierte Einstellungen zu aktivieren. Wenn die Option benutzerdefinierte Einstellungen auf **aus**festgelegt ist, können Sie keine Spamfilter Richtlinien ändern.

    ![Dieser Screenshot zeigt, dass benutzerdefinierte Anti-Spam-Filterrichtlinien Einstellungen deaktiviert wurden.](../../media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)

7. Erweitern Sie die Spam Richtlinie, die Sie ändern möchten, und klicken Sie dann auf **Richtlinie bearbeiten**. Wählen Sie beispielsweise den Abwärtspfeil neben **Standard-Spamfilter Richtlinie**aus. Wenn Sie möchten, können Sie eine neue Richtlinie erstellen, indem Sie **eine Richtlinie hinzufügen**auswählen.

8. Erweitern Sie **Spam-und Massen** Aktionen.

9. Aktivieren Sie unter **Sicherheitstipps**das Kontrollkästchen **ein** , um Sicherheitstipps zu aktivieren. Wenn Sie Sicherheitstipps deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **ein** .

10. Wählen Sie **Speichern** aus.

## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>So aktivieren oder deaktivieren Sie Sicherheitstipps mithilfe von PowerShell
<a name="pshellsafetytip"> </a>

Administratoren können Exchange Online PowerShell verwenden, um Sicherheitstipps zu aktivieren oder zu deaktivieren. Verwenden Sie das Cmdlet "hostedcontentfilterpolicy dient zum", um Sicherheitstipps in einer Spamfilter Richtlinie zu aktivieren oder zu deaktivieren.

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Weitere Informationen finden Sie unter [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Führen Sie das Cmdlet "hostedcontentfilterpolicy dient zum" aus, um Sicherheitstipps zu aktivieren oder zu deaktivieren:

   ```powershell
   Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true | $false>
   ```

Dabei gilt:

- *Richtlinienname* ist der Name der Richtlinie, die Sie ändern möchten, beispielsweise **default**.

- `$true`aktiviert Sicherheitstipps für die Spamfilter Richtlinie.

- `$false`deaktiviert Sicherheitstipps für die Spamfilter Richtlinie.

Um beispielsweise Sicherheitstipps für die standardmäßige Spamfilter Richtlinie zu deaktivieren, führen Sie den folgenden Befehl aus:

```powershell
Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-hostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).

## <a name="still-need-help"></a>Benötigen Sie weitere Hilfe?
<a name="pshellsafetytip"> </a>

Wenn Sie Sicherheitstipps deaktiviert haben und diese dennoch in Ihren e-Mail-Nachrichten angezeigt werden, überprüfen Sie Folgendes:

- Sicherheitstipps für Outlook im Internet können nicht deaktiviert werden. Versuchen Sie, die gleiche e-Mail in einem anderen Client wie Outlook anzuzeigen.

- Sicherheitstipps für jeden, der EoP verwendet, sind standardmäßig aktiviert, dies schließt alle ein, die über Office 365 verfügen. Um Sicherheitstipps zu deaktivieren, die in e-Mails angezeigt werden, müssen Sie Sie wie in diesem Thema beschrieben mithilfe einer Spamfilter Richtlinie deaktivieren. Nachdem Sie die Richtlinie eingerichtet haben, stellen Sie sicher, dass Sie aktiviert ist. Informationen zum Aktivieren von Spamfilter Richtlinien finden Sie unter [configure your Spamfilter Policies](configure-your-spam-filter-policies.md).

Weitere Möglichkeiten zum bekämpfen von Spam und Phishing finden Sie unter [Office 365 e-Mail Anti-Spam Protection](anti-spam-protection.md).
