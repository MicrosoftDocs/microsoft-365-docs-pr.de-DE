---
title: Einrichten Office 365 Richtlinien für ATP-sichere Links
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Richten Sie Richtlinien für sichere Links ein, um Ihre Organisation vor bösartigen Links in Word-, Excel-, PowerPoint-und Visio-Dateien sowie in e-Mail-Nachrichten zu schützen.
ms.openlocfilehash: 928f13ec8f04506540d02177acd82b2403a74683
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588088"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Einrichten Office 365 Richtlinien für ATP-sichere Links

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[ATP-sichere Links](atp-safe-links.md), ein Feature von [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), können Ihnen helfen, Ihre Organisation vor bösartigen Links zu schützen, die in Phishing-und anderen Angriffen verwendet werden. Wenn Sie über die erforderlichen [Berechtigungen für das Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)verfügen, können Sie Richtlinien für ATP-sichere Links einrichten, um sicherzustellen, dass Ihre Organisation geschützt ist, wenn Personen auf Webadressen (URLs) klicken. Ihre Richtlinien für ATP-sichere Links können so konfiguriert werden, dass Sie URLs in e-Mails und URLs in Office-Dokumenten überprüfen.

Wenn ATP-sichere Links aktiviert sind und ein Benutzer auf einen Link in einer e-Mail klickt und die URL durch die Liste der benutzerdefinierten blockierten URLs in Ihrer Organisation blockiert wurde oder wenn die URL als bösartig eingestuft wird, wird eine Warnseite geöffnet.
  
[Neue Features werden kontinuierlich zu ATP hinzugefügt](office-365-atp.md#new-features-in-office-365-atp). Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren bestehenden Richtlinien für ATP-sichere Links vornehmen.

## <a name="what-to-do"></a>Nächste Schritte 
  
1. Überprüfen Sie die Voraussetzungen.
    
2. Überprüfen und bearbeiten Sie die Standardrichtlinie für ATP-sichere Links, die für alle gilt. Beispielsweise können Sie [die Liste der benutzerdefinierten blockierten URLs für ATP-sichere Links einrichten](set-up-a-custom-blocked-urls-list-atp.md).
    
3. Hinzufügen oder Bearbeiten von Richtlinien für bestimmte e-Mail-Empfänger, einschließlich [der Einrichtung Ihrer benutzerdefinierten Liste "nicht umschreiben" für ATP-sichere Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. Erfahren Sie mehr über die Richtlinienoptionen für ATP-sichere Links (in diesem Artikel), einschließlich der Einstellungen für die letzten Änderungen.
    
## <a name="step-1-review-the-prerequisites"></a>Schritt 1: Überprüfen der Voraussetzungen

- Stellen Sie sicher, dass Ihre Organisation über [Office 365 Advanced Threat Protection](office-365-atp.md)verfügt.
    
- Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen. Um ATP-Richtlinien zu definieren oder zu bearbeiten, muss Ihnen eine entsprechende Rolle zugewiesen sein. In der folgenden Tabelle werden einige Beispiele beschrieben: <br>

    |Rolle  |Wo/wie zugewiesen  |
    |---------|---------|
    |globaler Administrator |Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)         |
    |Sicherheitsadministrator |Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
    |Exchange Online-Organisationsverwaltung |Exchange Admin Center ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

    Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Stellen Sie sicher, dass Office-Clients für die Verwendung der [modernen Authentifizierung](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) konfiguriert sind (Dies gilt für den Schutz von ATP-Links in Office-Dokumenten).
    
- [Erfahren Sie mehr über die Richtlinienoptionen für ATP-sichere Links](#step-4-learn-about-atp-safe-links-policy-options) (in diesem Artikel). 

- Erlauben Sie bis zu 30 Minuten, bis Ihre neue oder aktualisierte Richtlinie auf alle Microsoft 365-Rechenzentren verteilt ist.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Schritt 2: definieren (oder überprüfen) der Richtlinie für ATP-sichere Links, die für alle Benutzer gilt

Wenn Sie [Office 365 Advanced Threat Protection](office-365-atp.md)haben, verfügen Sie über eine Standardrichtlinie für ATP-sichere Links, die auf alle Benutzer in Ihrer Organisation angewendet wird. Stellen Sie sicher, dass Sie die Standardrichtlinie überprüfen und bei Bedarf bearbeiten.
  
1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an. 
    
2. Wählen Sie im linken Navigationsbereich unter **Threat Management**die **Option \> Richtlinien** **sichere Links**aus.
    
3. Wählen Sie in den **Richtlinien für den Abschnitt gesamte Organisation** die Option **Standard**aus, und klicken Sie dann auf **Bearbeiten** (die Schaltfläche Bearbeiten ähnelt einem Bleistift).<br/>![Klicken Sie auf Bearbeiten, um die Standardrichtlinie für den Schutz von sicheren Links zu bearbeiten.](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Geben Sie im Abschnitt **folgende URLs blockieren** eine oder mehrere URLs an, die verhindern sollen, dass Personen in Ihrer Organisation besucht werden. (Weitere Informationen finden Sie unter [Einrichten einer Liste benutzerdefinierter blockierter URLs mithilfe von ATP-Sicherheits Links](set-up-a-custom-blocked-urls-list-atp.md).)
    
5. Wählen Sie im Abschnitt **Einstellungen für Inhalt außer e-Mail** die Optionen aus, die Sie verwenden möchten. (Es wird empfohlen, alle Optionen auszuwählen.) 
    
6. Wählen Sie **Speichern** aus.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Schritt 3: hinzufügen (oder bearbeiten) von Richtlinien für ATP-sichere Links, die für bestimmte e-Mail-Empfänger gelten

Nachdem Sie die Standardrichtlinie für ATP-sichere Links überprüft (oder bearbeitet) haben, die für alle gilt, müssen Sie im nächsten Schritt zusätzliche Richtlinien definieren, die für bestimmte Empfänger gelten. Sie können beispielsweise Ausnahmen für die Standardrichtlinie angeben, indem Sie eine zusätzliche Richtlinie definieren. 
  
1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an. 
    
2. Wählen Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.
    
3. Wählen Sie **sichere Links**aus.
    
4. Wählen Sie im Abschnitt **Richtlinien für bestimmte Empfänger** auswählen die Option **neu** aus (die Schaltfläche neu ähnelt einem Pluszeichen ( **+** )).<br/>![Wählen Sie neu aus, um eine Richtlinie zu sicheren Links für bestimmte e-Mail-Empfänger hinzuzufügen](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Geben Sie den Namen, die Beschreibung sowie Einstellungen für Ihre Richtlinie an.<br/>**Beispiel:** Um eine Richtlinie mit dem Namen "kein direkter Mausklick" einzurichten, mit der Personen in einer bestimmten Gruppe in Ihrer Organisation nicht durch Klicken auf eine bestimmte Website ohne den Schutz vor ATP-Links geschützt werden können, geben Sie möglicherweise die folgenden empfohlenen Einstellungen an: 
    
    - Geben Sie im Feld **Name** keinen direkten Mausklick ein.

    - Geben Sie im Feld **Beschreibung** eine Beschreibung ein, die verhindert, dass Personen in bestimmten Gruppen durch Klicken auf eine Website ohne Überprüfung der ATP-sichere Links durch klicken.

    - Wählen Sie im Abschnitt **Aktion auswählen die** Option **ein**aus.

    - Wählen Sie **Echt Zeit-URL-Überprüfung für verdächtige Links und Links anwenden, die auf Dateien verweisen,** Wenn Sie die URL-Detonation für verdächtige und Datei verweisende URLs aktivieren möchten (empfohlen). Und wählen Sie **warten, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht** übermitteln, wenn Sie möchten, dass nur Benutzer Nachrichten empfangen, nachdem die URLs vollständig überprüft wurden.

    - Wählen Sie **sichere Links auf Nachrichten anwenden, die innerhalb der Organisation gesendet** werden, wenn Sie sichere Links für Nachrichten aktivieren möchten, die zwischen Benutzern innerhalb Ihrer Organisation gesendet werden (empfohlen).

    - Wählen Sie nicht zulassen, dass Benutzer auf die **ursprüngliche URL klicken** , wenn Sie nicht möchten, dass die einzelnen Benutzer eine über *Prüfung in Progress* oder Benachrichtigungen über *Blockierte URLs* außer Kraft setzen.

    - (Dies ist optional) Geben Sie im Abschnitt **folgende URLs nicht umschreiben** eine oder mehrere URLs an, die als sicher für Ihre Organisation betrachtet werden. (Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten URL-Liste "nicht umschreiben" unter Verwendung von ATP-Sicherheits Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))

    - Wählen Sie im Abschnitt **angewendet für** **den Empfänger ist Mitglied von aus**, und wählen Sie dann die Gruppe (n) aus, die Sie in Ihre Richtlinie einschließen möchten. Klicken Sie auf **Hinzufügen**, und wählen Sie dann **OK**aus.
    
6. Wählen Sie **Speichern** aus.

> [!NOTE]
> Richtlinien für ATP-sichere Links mit höherer Priorität werden Vorrang haben. Wenn ein Benutzer zwei oder mehr Policen unterliegt, wird nur die Richtlinie mit höherer Priorität wirksam.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Schritt 4: Informationen zu Richtlinienoptionen für ATP-sichere Links

Wenn Sie Ihre ATP-Richtlinien für sichere Links einrichten oder bearbeiten, werden mehrere Optionen zur Verfügung gestellt. Wenn Sie sich Fragen, was diese Optionen sind, wird in der folgenden Tabelle jede und ihre Auswirkung beschrieben. Denken Sie daran, dass es zwei Hauptarten von Richtlinien für ATP-sichere Links gibt, die Sie definieren oder bearbeiten müssen:
- eine [Standardrichtlinie](#default-policy-options) , die für alle Benutzer gilt. und  
- zusätzliche [Richtlinien für bestimmte Empfänger](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Standardrichtlinien Optionen

Standardrichtlinien Optionen gelten für alle Benutzer in Ihrer Organisation.

|Diese Option  |Funktion  |
|---------|---------|
| **Blockieren der folgenden URLs** <br/>    | Ermöglicht Ihrer Organisation, eine benutzerdefinierte Liste von URLs zu haben, die automatisch blockiert werden. Wenn Benutzer auf eine URL in dieser Liste klicken, werden Sie zu einer [Warnungsseite](atp-safe-links-warning-pages.md) geleitet, in der erklärt wird, warum die URL blockiert ist. Weitere Informationen finden Sie unter [Einrichten einer Liste benutzerdefinierter blockierter URLs mit Office 365 ATP-Sicherheits Links](set-up-a-custom-blocked-urls-list-atp.md). |
| **Microsoft 365-Apps für Unternehmen, Office für IOS und Android** <br/>    | Wenn diese Option ausgewählt ist, der Schutz für ATP-sichere Office 365 Links wird auf URLs in Word-, Excel-und PowerPoint-Dateien unter Windows oder Mac OS, e-Mail-Nachrichten in Outlook, Office-Dokumenten auf IOS-oder Android-Geräten, Visio 2016-Dateien unter Windows und in den Webversionen von Office-Apps geöffneten Dateien (Word, PowerPoint, Excel, Outlook und OneNote) angewendet, voraus |
| **Nicht nachverfolgen, wenn Benutzer auf ATP-sichere Links klicken** <br/>  | Wenn diese Option ausgewählt ist, klicken Sie auf Daten für URLs in Word-, Excel-, PowerPoint-, Visio-Dokumenten und Outlook-e-Mail-Nachrichten werden nicht gespeichert.  <br/> |
|**Lassen Sie nicht zu, dass Benutzer durch ATP-sichere Links zur ursprünglichen URL klicken.** <br/> |Wenn diese Option ausgewählt ist, können Benutzer nicht über eine [Warnungsseite](atp-safe-links-warning-pages.md) an eine URL weiterleiten, die als bösartig eingestuft wird.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Richtlinien für bestimmte e-Mail-Empfänger

|Diese Option  |Funktion  |
|---------|---------|
|**Off** <br/> |Überprüft URLs in e-Mail-Nachrichten nicht.  <br/> Ermöglicht das Definieren einer Ausnahmeregel, beispielsweise eine Regel, die URLs in e-Mail-Nachrichten für eine bestimmte Empfängergruppe nicht überprüft.  <br/> |
|**On** <br/> |Umschreibt URLs, um Benutzer über ATP-Safe-Links-Schutz zu leiten, wenn die Benutzer auf URLs in e-Mail-Nachrichten klicken und ATP-sichere Links in Outlook (C2R) unter Windows aktiviert.  <br/> Überprüft eine URL, wenn auf eine Liste blockierter oder böswilliger URLs geklickt wird, und löst asynchron eine Detonation der URL im Hintergrund aus, wenn die URL nicht über eine gültige Reputation verfügt.  <br/> |
|**Übernehmen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen** <br/> |Wenn diese Option ausgewählt ist, werden verdächtige URLs und Links, die auf herunterladbaren Inhalt verweisen, überprüft.  <br/> |
|**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht liefern** <br/> |Wenn diese Option ausgewählt ist, werden Nachrichten, die zu scannende URLs enthalten, bis zum Abschluss der Überprüfung der URLs aufbewahrt und bestätigt, dass Sie sicher sind, bevor die Nachrichten zugestellt werden.  <br/> |
|**Anwenden von sicheren Links auf Nachrichten, die innerhalb der Organisation gesendet werden** <br/> | Wenn diese Option verfügbar und ausgewählt ist, wird der Schutz für ATP-sichere Links auf e-Mail-Nachrichten angewendet, die zwischen Personen in Ihrer Organisation gesendet werden, vorausgesetzt, die e-Mail-Konten werden in Office 365 gehostet.  <br/> |
|**Benutzerklicks nicht nachverfolgen** <br/> |Wenn diese Option ausgewählt ist, klicken Sie auf Daten für URLs in e-Mail von externen Absendern wird nicht gespeichert. Die URL-klickverfolgung für Links in e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden, wird derzeit nicht unterstützt.  <br/> |
|**Benutzer dürfen nicht auf die ursprüngliche URL klicken.** <br/> |Wenn diese Option ausgewählt ist, können Benutzer nicht über eine [Warnungsseite](atp-safe-links-warning-pages.md) an eine URL weiterleiten, die als bösartig eingestuft wird.  <br/> |
|**Folgende URLs dürfen nicht umgeschrieben werden** <br/> |Lässt URLs so wie Sie sind. Speichert eine benutzerdefinierte Liste sicherer URLs, die nicht für eine bestimmte Gruppe von e-Mail-Empfängern in Ihrer Organisation überprüft werden müssen.  Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste "nicht umschreiben"-URLs mit ATP-Sicherheits Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) , einschließlich der letzten Änderungen bei der Unterstützung von Platzhalter Sternchen ( \* ).  <br/> |
   
## <a name="next-steps"></a>Weitere Schritte

Sobald Ihre ATP-Richtlinien für sichere Links vorhanden sind, können Sie sehen, wie ATP für Ihre Organisation funktioniert, indem Sie Berichte anzeigen. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Verwenden des Explorers im Security &amp; Compliance Center](threat-explorer.md)

Bleiben Sie auf dem neuesten Stand neuer Features, die zu ATP kommen. Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
