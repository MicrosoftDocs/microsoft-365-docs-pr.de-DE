---
title: Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 for Business-Plänen
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Schützen Sie Ihre geschäftlichen e-Mails und Daten vor Cyber-Bedrohungen, einschließlich Ransomware, Phishing und böswilligen Anlagen. '
ms.openlocfilehash: 12a8d036a043cfdd162b5aa47e1d6d5023a42c81
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005630"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 for Business-Plänen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Wenn Sie eine kleine oder mittelgroße Organisation mit einem der Geschäftspläne von Microsoft verwenden und Ihr Organisationstyp von Cyber-Kriminellen und Hackern abzielt, verwenden Sie die Anleitungen in diesem Artikel, um die Sicherheit Ihrer Organisation zu verbessern. Dieser Leitfaden hilft Ihrer Organisation, die im [Handbuch zur Kampagne](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409)"Harvard Kennedy School Cyber" beschriebenen Ziele zu erreichen.
  
Microsoft empfiehlt, die in der folgenden Tabelle aufgeführten Aufgaben abzuschließen, die für Ihren Dienstplan gelten. 
  
||**Aufgabe**|**Microsoft 365 Business Standard**|**Microsoft 365 Business Premium**|
|:-----|:-----|:-----|:-----|
|1   <br/> |[Einrichten der mehrstufigen Authentifizierung](secure-your-business-data.md#setup) <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|2   <br/> |[Schulen der Benutzer](secure-your-business-data.md#train) <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|3   <br/> |[Verwenden dedizierter Administratorkonten](secure-your-business-data.md#admin) <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|4   <br/> |[Erhöhen des Schutzniveaus gegen Schadsoftware in Mail](secure-your-business-data.md#malware) <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|5   <br/> |[Schutz vor Ransomware](secure-your-business-data.md#ransomware) <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|6   <br/> |[Beenden der automatischen Weiterleitung für e-Mail](secure-your-business-data.md#forwarding) <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|7   <br/> |[Verwenden der Office-Nachrichtenverschlüsselung](secure-your-business-data.md#encryption) <br/> ||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|8   <br/> |[Schützen Ihrer e-Mails vor Phishing-Angriffen](secure-your-business-data.md#phishing) <br/> ||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9   <br/> |[Schutz vor böswilligen Anlagen und Dateien mit sicheren ATP-Anlagen](secure-your-business-data.md#atp) <br/> ||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|10   <br/> |[Schutz vor Phishing-Angriffen durch ATP-sichere Links](secure-your-business-data.md#phishingatp) <br/> ||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
   
Bevor Sie beginnen, überprüfen Sie Ihre [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) im Microsoft 365 Security Center. Über ein zentralisiertes Dashboard können Sie die Sicherheit für Ihre Microsoft 365-Identitäten,-Daten,-apps,-Geräte und-Infrastruktur überwachen und verbessern. Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben (beispielsweise zum Anzeigen von Berichten) oder zur Adressierung von Empfehlungen mit Anwendungen oder Software eines Drittanbieters. Dank zusätzlicher Einblicke und größerer Transparenz in einer breiteren Palette von Microsoft-Produkten und-Diensten können Sie sich sicher fühlen, dass Sie über die Sicherheitsintegrität in Ihrer Organisation berichten.
  
![Screenshot von Microsoft Secure Score](../../media/secure-score.png)
  
## <a name="1-set-up-multi-factor-authentication"></a>1: Einrichten der mehrstufigen Authentifizierung
<a name="setup"> </a>

Die Verwendung der mehrstufigen Authentifizierung ist eine der einfachsten und effektivsten Methoden, um die Sicherheit Ihrer Organisation zu verbessern. Einfacher als es klingt – Wenn Sie sich anmelden, bedeutet mehrstufige Authentifizierung, dass Sie einen Code von Ihrem Telefon eingeben, um Zugriff auf Microsoft 365 zu erhalten. Dadurch kann verhindert werden, dass Hacker die übernehmen, wenn Sie Ihr Kennwort kennen. Die mehrstufige Authentifizierung wird auch als Überprüfung in zwei Schritten bezeichnet. Einzelpersonen können die Überprüfung in zwei Schritten für die meisten Konten problemlos hinzufügen, beispielsweise für Ihr Google-oder Microsoft-Konto. Hier erfahren Sie, wie Sie [Ihrem persönlichen Microsoft-Konto eine Überprüfung mit zwei Schritten hinzufügen](https://go.microsoft.com/fwlink/?linkid=2016403&amp;clcid=0x409).
  
Fügen Sie für Unternehmen, die Microsoft 365 verwenden, eine Einstellung hinzu, mit der sich Ihre Benutzer mit mehrstufiger Authentifizierung anmelden müssen. Wenn Sie diese Änderung vornehmen, werden die Benutzer aufgefordert, Ihr Mobiltelefon für die zweistufige Authentifizierung einzurichten, wenn Sie sich das nächste Mal anmelden.
Ein Schulungsvideo zur Einrichtung von MFA und zur Fertigstellung von Benutzern finden Sie unter [Einrichten von MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) und [Benutzer einrichten](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225).
  
So richten Sie die mehrstufige Authentifizierung ein:

1. Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822)die Option **Users**  >  **Active Users**aus.

2. Wählen Sie im Abschnitt **aktive Benutzer** die Option **mehrstufige Authentifizierung**aus.

3. Wählen Sie auf der Seite mehrstufige **Authentifizierung** die Option **Benutzer** aus, wenn Sie dies für einen Benutzer aktivieren, oder Sie können eine **Massenaktualisierung**durchführen.

4. Wählen Sie unter **Quick Steps**die Option **enable** aus.

5. Wählen Sie im Popupfenster die **Option mehrstufige Authentifizierung aktivieren**aus.


Nachdem Sie die mehrstufige Authentifizierung für Ihre Organisation eingerichtet haben, müssen die Benutzer auf ihren Geräten die Prüfung in zwei Schritten einrichten. Weitere Informationen finden Sie unter [Einrichten der Überprüfung in zwei Schritten für Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).
  
Ausführliche Informationen und umfassende Empfehlungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung für Benutzer](set-up-multi-factor-authentication.md).
  
## <a name="2-train-your-users"></a>2: Schulen Ihrer Benutzer
<a name="train"> </a>

Das Harvard Kennedy School [Cyber Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) bietet eine hervorragende Anleitung zum Einrichten einer starken Kultur des Sicherheitsbewusstseins in Ihrer Organisation, einschließlich der Schulung von Benutzern zur Identifizierung von Phishing-Angriffen. 
  
Zusätzlich zu diesen Anleitungen empfiehlt Microsoft, dass Ihre Benutzer die in diesem Artikel beschriebenen Aktionen ausführen: [schützen Sie Ihr Konto und Ihre Geräte vor Hackern und Schadsoftware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Diese setzen sich wie folgt zusammen:
  
- Verwenden sicherer Kennwörter
    
- Schützen von Geräten
    
- Aktivieren von Sicherheitsfunktionen auf Windows 10-und Mac-PCs
    
Microsoft empfiehlt auch, dass Benutzer Ihre persönlichen e-Mail-Konten schützen, indem Sie die in den folgenden Artikeln empfohlenen Aktionen ausführen:
  
- [Schützen Ihres Outlook.com-e-Mail-Kontos](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [Schützen Ihres gmail-Kontos mit zweistufiger Überprüfung](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
    
## <a name="3-use-dedicated-admin-accounts"></a>3: Verwenden dedizierter Administratorkonten
<a name="admin"> </a>

Die Administratorkonten, die Sie zum Verwalten Ihrer Microsoft 365-Umgebung verwenden, umfassen erweiterte Berechtigungen. Dies sind wertvolle Ziele für Hacker und Cyber-Kriminelle. Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für reguläre, nicht administrative Zwecke verfügen und bei Bedarf nur Ihr Administratorkonto verwenden, um eine Aufgabe abzuschließen, die ihrer Auftragsfunktion zugeordnet ist. Weitere Empfehlungen:
  
- Stellen Sie sicher, dass auch Administratorkonten für die mehrstufige Authentifizierung eingerichtet sind. 
    
- Schließen Sie vor der Verwendung von Administratorkonten alle nicht verwandten Browsersitzungen und apps, einschließlich persönlicher e-Mail-Konten.
    
- Nachdem Sie die Administratoraufgaben abgeschlossen haben, müssen Sie sich bei der Browsersitzung abmelden.
    
## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: erhöhen des Schutzniveaus gegen Schadsoftware in Mail
<a name="malware"> </a>

Ihre Microsoft 365-Umgebung umfasst Schutz vor Schadsoftware, aber Sie können diesen Schutz verbessern, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden. Um den Schutz vor Schadsoftware in e-Mails zu erhöhen, sehen Sie sich ein [kurzes Schulungsvideo](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)an, oder führen Sie die folgenden Schritte aus:
  
1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit den Anmeldeinformationen Ihres Administratorkontos an. 
    
2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Threat Management**die Option **Policy** \> **Anti-Malware**aus.
    
3. Doppelklicken Sie auf die Standardrichtlinie, um diese unternehmensweite Richtlinie zu bearbeiten.
    
4. Wählen Sie **Einstellungen** aus.
    
5. Wählen Sie unter **Allgemeine Filter für Anlagentypen**die Option **ein**aus. Die blockierten Dateitypen werden im Fenster direkt unterhalb dieses Steuerelements aufgeführt. Sie können Dateitypen bei Bedarf später hinzufügen oder löschen.
    
6. Wählen Sie **Speichern aus.**
    
Weitere Informationen finden Sie unter [Anti-Malware Protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="5-protect-against-ransomware"></a>5: Schutz vor Ransomware
<a name="ransomware"> </a>

Ransomware schränkt den Zugriff auf Daten ein, indem Dateien verschlüsselt oder Computerbildschirme gesperrt werden. Er versucht dann, Geld von den Opfern zu erpressen, indem er nach "Lösegeld" fragt, normalerweise in Form von cryptocurrencies wie Bitcoin, im Gegenzug für den Zugriff auf Daten. 
  
Sie können Schutz vor Ransomware durch Erstellen einer oder mehrerer Nachrichtenfluss Regeln zum Blockieren von Dateierweiterungen, die häufig für Ransomware verwendet werden, oder zum warnen von Benutzern, die diese Anlagen in e-Mails erhalten, schützen. Ein guter Ausgangspunkt besteht darin, zwei Regeln zu erstellen:
  
- Warnen Sie die Benutzer vor dem Öffnen von Office-Dateianlagen, die Makros enthalten. Ransomware können in Makros ausgeblendet werden, sodass die Benutzer gewarnt werden, diese Dateien nicht von Personen zu öffnen, die Sie nicht kennen. 
    
- Blockieren von Dateitypen, die Ransomware oder anderen bösartigen Code enthalten könnten. Wir beginnen mit einer allgemeinen Liste von ausführbaren Dateien (in der Tabelle unten aufgeführt). Wenn in Ihrer Organisation eine dieser ausführbaren Typen verwendet wird und Sie davon ausgehen, dass diese in einer e-Mail gesendet werden, fügen Sie diese der vorherigen Regel hinzu (warnen Sie Benutzer).
    
Um eine e-Mail-Transportregel zu erstellen, zeigen Sie ein [kurzes Schulungsvideo](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)an, oder führen Sie die folgenden Schritte aus:
  
1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

2. Wählen Sie in der Kategorie **Nachrichtenfluss** die Option **Regeln**aus.
    
3. Wählen Sie aus **+** , und erstellen Sie dann **eine neue Regel**.
    
4. Wählen Sie am unteren Rand des Dialogfelds die Option * * * * aus, um den vollständigen Optionssatz anzuzeigen. 
    
5. Wenden Sie die Einstellungen in der folgenden Tabelle für jede Regel an. Lassen Sie die restlichen Einstellungen standardmäßig unverändert, es sei denn, Sie möchten diese ändern.
    
6. Klicken Sie auf **Speichern**.
    
|**Einstellung**|**Benutzer vor dem Öffnen von Anlagen von Office-Dateien warnen**|**Blockieren von Dateitypen, die Ransomware oder anderen bösartigen Code enthalten könnten**|
|:-----|:-----|:-----|
|Name  <br/> |Anti-Ransomware-Regel: Benutzer warnen  <br/> |Anti-Ransomware-Regel: Blockieren von Dateitypen  <br/> |
|Wenden Sie diese Regel an, wenn. . .  <br/> |Jede Anlage. . . Dateierweiterung entspricht. . .  <br/> |Jede Anlage. . . Dateierweiterung entspricht. . .  <br/> |
|Angeben von Wörtern oder Ausdrücken  <br/> |Fügen Sie diese Dateitypen hinzu:  <br/> DOTM, DOCM, XLSM, sltm, XLA, xlam, XLL, PPTM, POTM, PPAM, PPSM, sldm  <br/> |Fügen Sie diese Dateitypen hinzu:  <br/> Ade, ADP, Ani, Bas, bat, CHM, cmd, com, CPL, CRT, HLP, HT, HTA, inf, ins, ISP, Job, JS, JSE, lnk, MDA, MDB, MDE, MDZ, MSC, MSI, MSP, MST, PCD, SHS, URL, VB, Visual Basic, VBS, WSC, WSF, WSH, exe, PIF  <br/> |
|Führen Sie die folgenden Schritte aus. . .  <br/> |Empfänger durch Nachricht benachrichtigen  <br/> |Blockiert die Nachricht. . . Ablehnen der Nachricht und Einschließen einer Erklärung  <br/> |
|Nachrichtentext bereitstellen  <br/> |Öffnen Sie diese Dateitypen nicht, es sei denn, Sie haben Sie erwartet, da die Dateien möglicherweise bösartigen Code enthalten und der Absender wissen, dass es sich nicht um eine Sicherheitsgarantie handelt.  <br/> ||
   
> [!TIP]
> Sie können auch die zu sperrenden Dateien zur Liste der Antischadsoftware in [Schritt 4](#4-raise-the-level-of-protection-against-malware-in-mail)hinzufügen.

Weitere Informationen finden Sie unter:
  
- [Umgang mit Ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Wiederherstellen der OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)
    
## <a name="6-stop-auto-forwarding-for-email"></a>6: Beenden der automatischen Weiterleitung für e-Mail
<a name="forwarding"> </a>

Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können e-Mails exfiltrieren, indem Sie das Postfach So konfigurieren, dass e-Mails automatisch weitergeleitet werden. Dies kann auch ohne das Bewusstsein des Benutzers geschehen. Sie können dies verhindern, indem Sie eine e-Mail-Fluss Regel konfigurieren. 
  
So erstellen Sie eine e-Mail-Transportregel:
  
1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

2. Wählen Sie in der Kategorie **Nachrichtenfluss** die Option **Regeln**aus.
    
3. Wählen Sie aus **+** , und erstellen Sie dann **eine neue Regel**.
    
4. Wählen Sie im unteren Bereich des Dialogfelds **Weitere Optionen** aus, um den vollständigen Optionssatz anzuzeigen. 
    
5. Wenden Sie die Einstellungen in der folgenden Tabelle an. Lassen Sie die restlichen Einstellungen standardmäßig unverändert, es sei denn, Sie möchten diese ändern.
    
6. Klicken Sie auf **Speichern**.
    
|**Einstellung**|**Ablehnen automatischer Weiterleitung von e-Mails an externe Domänen**|
|:-----|:-----|
|Name  <br/> |Verhindern der automatischen Weiterleitung von e-Mails an externe Domänen  <br/> |
|Diese Regel anwenden, wenn...  <br/> |Absender. . . ist extern/intern. . . Innerhalb der Organisation  <br/> |
|Bedingung hinzufügen  <br/> |Empfänger. . . ist extern/intern. . . Außerhalb der Organisation  <br/> |
|Bedingung hinzufügen  <br/> |Die Nachrichteneigenschaften. . . Geben Sie den Nachrichtentyp ein. . . Automatische Weiterleitung  <br/> |
|Führen Sie die folgenden Schritte aus...  <br/> |Blockiert die Nachricht. . . die Nachricht ablehnen und eine Erklärung einschließen.  <br/> |
|Nachrichtentext bereitstellen  <br/> |Die automatische Weiterleitung von e-Mails außerhalb dieser Organisation wird aus Sicherheitsgründen verhindert.  <br/> |
   
## <a name="7-use-office-message-encryption"></a>7: Verwenden der Office-Nachrichtenverschlüsselung
<a name="encryption"> </a>

Die Office-Nachrichtenverschlüsselung ist in Microsoft 365 enthalten. Er ist bereits eingerichtet. Mit der Office-Nachrichtenverschlüsselung kann Ihre Organisation verschlüsselte e-Mail-Nachrichten zwischen Personen innerhalb und außerhalb Ihrer Organisation senden und empfangen. Die Office 365-Nachrichtenverschlüsselung funktioniert mit Outlook.com, Yahoo!, Gmail und anderen E-Mail-Diensten. Die E-Mail-Nachrichtenverschlüsselung sorgt dafür, dass nur vorgesehene Empfänger verschlüsselte Nachrichten ansehen können.
  
Die Office-Nachrichtenverschlüsselung bietet beim Senden von e-Mails zwei Schutzoptionen:
  
- Nicht weiterleiten
    
- Verschlüsseln
    
Ihre Organisation hat möglicherweise zusätzliche Optionen konfiguriert, mit denen eine Bezeichnung auf e-Mail angewendet wird, beispielsweise vertraulich.
  
### <a name="to-send-protected-email"></a>So senden Sie geschützte e-Mails

Wählen Sie in Outlook für PC die Option **Optionen** in der e-Mail aus, und wählen Sie dann **Berechtigungen**aus. 
  
![Verschlüsselung von e-Mail-Nachrichten in Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)
  
Wählen Sie in Outlook.com in der e-Mail **schützen** aus. Der Standardschutz ist " **nicht weiterleiten**". Um dies zu verschlüsseln zu ändern, wählen Sie **Change Permissions** \> **Encrypt**aus. 
  
![Verschlüsselung von e-Mail-Nachrichten in Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)
  
### <a name="to-receive-encrypted-email"></a>So empfangen Sie verschlüsselte e-Mails

Wenn der Empfänger über Outlook 2013 oder Outlook 2016 und ein Microsoft-e-Mail-Konto verfügt, wird eine Warnung zu den eingeschränkten Berechtigungen des Elements im Lesebereich angezeigt. Nach dem Öffnen der Nachricht kann der Empfänger die Nachricht wie jede andere anzeigen.
  
Wenn der Empfänger einen anderen e-Mail-Client oder ein e-Mail-Konto wie Gmail oder Yahoo verwendet, wird ein Link angezeigt, über den Sie sich entweder anmelden können, um die e-Mail-Nachricht zu lesen, oder um einen einmaligen Zugangscode zum Anzeigen der Nachricht in einem Webbrowser anzufordern. Wenn Benutzer die e-Mail nicht erhalten, überprüfen Sie deren Spam-oder Junk-Ordner. 
  
Weitere Informationen finden Sie unter [senden, anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).
  
## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Schützen Ihrer e-Mails vor Phishing-Angriffen
<a name="phishing"> </a>

Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Microsoft 365-Umgebung konfiguriert haben, können Sie den gezielten Schutz gegen Phishing konfigurieren. Der ATP-Schutz gegen Phishing, ein Teil Office 365 Advanced Threat Protection, kann zum Schutz Ihrer Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Phishing-Angriffen beitragen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.
  
Es wird empfohlen, dass Sie mit diesem Schutz beginnen, indem Sie eine Richtlinie zum Schutz ihrer wichtigsten Benutzer und Ihrer benutzerdefinierten Domäne erstellen. 
  
![Erstellen einer ATP-Richtlinie zum Schutz vor Phishing](../../media/security-and-compliance-center.png)
  
Um eine ATP-Anti-Phishing-Richtlinie zu erstellen, sehen Sie sich ein [kurzes Schulungsvideo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)an, oder führen Sie die folgenden Schritte aus:
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com). 
    
2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.
    
3. Wählen Sie auf der Seite Richtlinie die Option **ATP Anti-Phishing**aus.
    
4. Wählen Sie auf der Seite Anti-Phishing die Option **+ Create**aus. Ein Assistent wird gestartet, der Sie schrittweise durch die Definition ihrer Anti-Phishing-Richtlinie führt.
    
5. Geben Sie den Namen, die Beschreibung und die Einstellungen für Ihre Richtlinie wie im folgenden Diagramm empfohlen an. Weitere Informationen finden Sie unter [Learn about ATP Anti-Phishing Policy Options](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) . 
    
6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie **Diese Richtlinie erstellen** oder **Speichern**(je nach Bedarf) aus.


|**Einstellung oder Option**|**Empfohlene Einstellung** <br/>|
|:-----|:-----|
|Name  <br/> |Domäne und die wertvollsten Kampagnen Mitarbeiter  <br/> |
|Beschreibung  <br/> |Stellen Sie sicher, dass die meisten wichtigen Mitarbeiter und unsere Domäne nicht angenommen werden.  <br/> |
|Zu schützende Benutzer hinzufügen  <br/> |Wählen Sie **+ Bedingung hinzufügen, ist der Empfänger**. Geben Sie Benutzernamen ein, oder geben Sie die e-Mail-Adresse des Kandidaten, des Kampagnen Managers und anderer wichtiger Mitarbeiter ein. Sie können bis zu 20 interne und externe Adressen hinzufügen, die Sie vor dem Identitätswechsel schützen möchten.  <br/> |
|Zu schützende Domänen hinzufügen  <br/> |Wählen Sie **+ Bedingung hinzufügen, die Empfängerdomäne ist**. Geben Sie die benutzerdefinierte Domäne, die Ihrem Microsoft 365-Abonnement zugeordnet ist, ein, wenn Sie eine definiert haben. Sie können mehr als eine Domäne eingeben.  <br/> |
|Aktionen auswählen  <br/> |Wenn e-Mail von einem imitierten Benutzer gesendet wird: Wählen Sie **Nachricht an eine andere e-Mail-Adresse umleiten**aus, und geben Sie dann die e-Mail-Adresse des Sicherheitsadministrators ein. Beispiel: securityadmin@contoso.com.          Wenn e-Mail von einer imitierten Domäne gesendet wird: Wählen Sie **Quarantäne Nachricht**aus.  <br/> |
|Mailbox Intelligence  <br/> |Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.  <br/> |
|Vertrauenswürdige Absender und Domänen hinzufügen  <br/> |Definieren Sie in diesem Beispiel keine Außerkraftsetzungen.  <br/> |
|Angewendet auf  <br/> |Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, beispielsweise contoso.com, in der Liste, und wählen Sie dann **Hinzufügen**aus. Wählen Sie **Fertig** aus.  <br/> |
|
   
Weitere Informationen finden Sie unter [Einrichten von Office 365 ATP-Richtlinien zum Schutz vor Phishing](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  
## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9: Schutz vor böswilligen Anlagen und Dateien mit sicheren ATP-Anlagen
<a name="atp"> </a>

Personen senden, empfangen und teilen regelmäßig Anlagen wie Dokumente, Präsentationen, Tabellenkalkulationen und vieles mehr. Es ist nicht immer einfach zu erkennen, ob eine Anlage sicher oder böswillig ist, indem nur eine e-Mail-Nachricht angezeigt wird. Office 365 Advanced Threat Protection umfasst den Schutz von ATP-Sicherheitsanlagen, dieser Schutz ist jedoch nicht standardmäßig aktiviert. Es wird empfohlen, dass Sie eine neue Regel erstellen, um mit diesem Schutz zu beginnen. Dieser Schutz erstreckt sich auf Dateien in SharePoint, OneDrive und Microsoft Teams.
  
Um eine Richtlinie für eine ATP-sichere Anlage zu erstellen, sehen Sie sich ein [kurzes Schulungsvideo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)an, oder führen Sie die folgenden Schritte aus:
  
1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit Ihrem Administratorkonto an. 
    
2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.
    
3. Wählen Sie auf der Seite Richtlinie die Option **ATP-sichere Anlagen**aus.
    
4. Wenden Sie diesen Schutz auf der Seite sichere Anlagen allgemein an, indem Sie das Kontrollkästchen **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** aktivieren. 
    
5. Wählen Sie diese Option aus **+** , um eine neue Richtlinie zu erstellen. 
    
6. Wenden Sie die Einstellungen in der folgenden Tabelle an. 
    
7. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie **Diese Richtlinie erstellen** oder **Speichern**(je nach Bedarf) aus.
    

|**Einstellung oder Option**|**Empfohlene Einstellung** <br/>|
|:-----|:-----|
|Name  <br/> |Blockiert aktuelle und zukünftige e-Mails mit erkannter Schadsoftware.  <br/> |
|Beschreibung  <br/> |Blockiert aktuelle und zukünftige e-Mails und Anlagen mit erkannter Schadsoftware.  <br/> |
|Anhänge speichern unbekannte Schadsoftware-Antwort  <br/> |Wählen Sie **die Option Blockieren der aktuellen und zukünftigen e-Mails und Anlagen mit erkannter Schadsoftware**aus.  <br/> |
|Umleitungs Anlage bei der Erkennung  <br/> |Umleitung aktivieren (aktivieren Sie dieses Kontrollkästchen) geben Sie das Administratorkonto oder ein Post Fach Setup für Quarantäne ein.          Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung nach Anlagen ein Timeout oder ein Fehler auftritt (aktivieren Sie dieses Kontrollkästchen).  <br/> |
|Angewendet auf  <br/> |Die Empfängerdomäne ist. . . Wählen Sie Ihre Domäne aus.  <br/> |
|
   
Weitere Informationen finden Sie unter [Einrichten von Office 365 ATP-Richtlinien zum Schutz vor Phishing](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  
## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10: Schutz vor Phishing-Angriffen mit ATP-Safe-Links
<a name="phishingatp"> </a>

Hacker verbergen manchmal böswillige Websites in Links in e-Mails oder anderen Dateien. Office 365 ATP-sichere Links (ATP-sichere Links), ein Teil Office 365 Advanced Threat Protection, können zum Schutz Ihrer Organisation beitragen, indem Sie die Zeit-für-Klick-Überprüfung von Webadressen (URLs) in e-Mail-Nachrichten und Office-Dokumenten ermöglichen. Der Schutz wird durch Richtlinien für ATP-sichere Links definiert.
  
Es wird empfohlen, dass Sie die folgenden Schritte ausführen:
  
- Ändern Sie die Standardrichtlinie, um den Schutz zu verbessern.
    
- Fügen Sie eine neue Richtlinie hinzu, die für alle Empfänger in Ihrer Domäne vorgesehen ist.
    
Um auf ATP-sichere Links zu gelangen, sehen Sie sich ein [kurzes Schulungsvideo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)an, oder führen Sie die folgenden Schritte aus:
  
1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit Ihrem Administratorkonto an. 
    
2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.
    
3. Wählen Sie auf der Seite Richtlinie die Option **ATP-sichere Links**aus.
    
So ändern Sie die Standardrichtlinie:
  
1. Doppelklicken Sie auf der Seite sichere Links unter **Richtlinien, die für die gesamte Organisation gelten**, auf die **Standard** Richtlinie. 
    
2. Geben Sie unter **Einstellungen, die für Inhalte in Office 365 gelten**, eine URL ein, die blockiert werden soll, beispielsweise _example.com_, und wählen Sie aus **+** .

3. Wählen Sie unter **Einstellungen für Inhalte mit Ausnahme von e-Mail**die Option **Office 365 Anwendungen**aus, **verfolgen Sie nicht nach, wann Benutzer auf sichere Links klicken**, und **lassen Sie keine Benutzer durch sichere Links zur ursprünglichen URL klicken**.
    
4. Klicken Sie auf **Speichern**. 
    
So erstellen Sie eine neue Richtlinie, die für alle Empfänger in Ihrer Domäne vorgesehen ist:
  
1. Wählen Sie auf der Seite "sichere Links" unter **Richtlinien, die für bestimmte Empfänger gelten**, die Option aus, **+** um eine neue Richtlinie zu erstellen. 
    
2. Wenden Sie die in der folgenden Tabelle aufgeführten Einstellungen an.
    
3. Klicken Sie auf **Speichern**. 
    
|**Einstellung oder Option**|**Empfohlene Einstellung** <br/>|
|:-----|:-----|
|Name  <br/> |Richtlinie für sichere Links für alle Empfänger in der Domäne  <br/> |
|Auswählen der Aktion für unbekannte potenziell bösartige URLs in Nachrichten  <br/> |Select **on-URLs werden umgeschrieben und anhand einer Liste bekannter böswilliger Links überprüft, wenn der Benutzer auf den Link klickt**.  <br/> |
|Übernehmen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen  <br/> |Aktivieren Sie dieses Kontrollkästchen.  <br/> |
|Angewendet auf  <br/> |Die Empfängerdomäne ist. . . Wählen Sie Ihre Domäne aus.  <br/> |
|
   
Weitere Informationen finden Sie unter [Office 365 ATP-sichere Links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).
