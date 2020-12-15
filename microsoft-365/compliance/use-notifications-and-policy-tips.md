---
title: Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Informationen zum Hinzufügen eines Richtlinien Tipps zu einer DLP-Richtlinie (Data Loss Prevention), um einen Benutzer darüber zu informieren, dass er mit Inhalten arbeitet, die mit einer DLP-Richtlinie in Konflikt stehen.
ms.openlocfilehash: 4f8855e3dce2adaf457b9a2453ca9dd827de5bcd
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682948"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien

Sie können eine DLP-Richtlinie (Data Loss Prevention) verwenden, um vertrauliche Informationen über Office 365 zu identifizieren, zu überwachen und zu schützen. Sie möchten, dass Personen in Ihrer Organisation, die mit diesen vertraulichen Informationen arbeiten, mit ihren DLP-Richtlinien konform bleiben, Sie sollten Sie jedoch nicht unnötig daran hindern, ihre Arbeit zu erledigen. Hier können e-Mail-Benachrichtigungen und Richtlinien Tipps hilfreich sein.
  
![Nachrichtenleiste zeigt richtlinientipp in Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Ein richtlinientipp ist eine Benachrichtigung oder Warnung, die angezeigt wird, wenn ein Benutzer mit Inhalten arbeitet, die mit einer DLP-Richtlinie in Konflikt stehen (beispielsweise Inhalte wie eine Excel-Arbeitsmappe auf einer OneDrive für Unternehmen Website, die personenbezogene Informationen (PII) enthält und für einen externen Benutzer freigegeben ist.
  
Sie können e-Mail-Benachrichtigungen und Richtlinien Tipps verwenden, um die Bekanntheit zu verbessern und Personen über die Richtlinien Ihrer Organisation zu informieren. Sie können Benutzern auch die Möglichkeit geben, die Richtlinie außer Kraft zu setzen, damit Sie nicht blockiert werden, wenn Sie eine gültige geschäftliche Anforderung haben oder wenn die Richtlinie ein falsch positives Ergebnis erkennt.
  
&amp;Wenn Sie im Security Compliance Center eine DLP-Richtlinie erstellen, können Sie die Benutzer Benachrichtigungen für Folgendes konfigurieren:
  
- Senden Sie eine e-Mail-Benachrichtigung an die Personen, die Sie auswählen, die das Problem beschreibt.
    
- Anzeigen eines Richtlinien Tipps für Inhalte, die mit der DLP-Richtlinie in Konflikt stehen:
    
  - Bei e-Mails in Outlook im Internet und Outlook 2013 und höher wird die RichtlinienInfo oben in einer Nachricht oberhalb der Empfänger angezeigt, während die Nachricht verfasst wird.
    
  - Für Dokumente in einem OneDrive für Unternehmen Konto oder SharePoint Online Website wird der richtlinientipp durch ein Warnsymbol angezeigt, das auf dem Element angezeigt wird. Um weitere Informationen anzuzeigen, können Sie ein Element auswählen und dann  ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in der rechten oberen Ecke der Seite auf Informations Informationsbereichs Symbol klicken, um den Detailbereich zu öffnen. 
    
  - Für Excel-, PowerPoint-und Word-Dokumente, die auf einer OneDrive für Unternehmen Website oder SharePoint Online Website gespeichert sind, die in der DLP-Richtlinie enthalten ist, wird der richtlinientipp in  der Statusleiste und im Backstage-Ansicht (Menü \> **Informationen** für Dateien) angezeigt.
    
## <a name="add-user-notifications-to-a-dlp-policy"></a>Hinzufügen von Benutzer Benachrichtigungen zu einer DLP-Richtlinie

Wenn Sie eine DLP-Richtlinie erstellen, können Sie **Benutzer Benachrichtigungen** aktivieren. Wenn Benutzer Benachrichtigungen aktiviert sind, sendet Microsoft 365 sowohl e-Mail-Benachrichtigungen als auch Richtlinien Tipps. Sie können anpassen, an wen die Benachrichtigungs-e-Mails gesendet werden, den Text für e-Mail und richtlinientipp.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an. Sie befinden sich jetzt im Security &amp; Compliance Center.
    
3. Im Security &amp; Compliance Center \> Links Navigations Richtlinie zur \> **Verhinderung von Datenverlust** und \>  \> **Erstellen einer Richtlinie**.
    
    ![Erstellen einer Richtlinien Schaltfläche](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Wählen Sie die DLP-Richtlinienvorlage aus, die die Typen von vertraulichen Informationen schützt, die Sie \> **als nächstes** benötigen.
    
    Um mit einer leeren Vorlage zu beginnen,  wählen Sie \>  \> **als nächstes** benutzerdefinierte Richtlinie aus.
    
5. Nennen Sie die Richtlinie \> **als nächstes**.
    
6. Führen Sie einen der folgenden Schritte aus, um die Speicherorte auszuwählen, die von der DLP-Richtlinie geschützt werden sollen:
    
   - Wählen Sie **in Office 365 Next alle Standorte aus** \> .
    
   - Wählen Sie **Let Me Choose specific Locations** \> **Next** aus.
    
   Wenn Sie einen gesamten Standort wie alle Exchange-e-Mails oder alle OneDrive-Konten einschließen oder ausschließen möchten, wechseln Sie den **Status** dieser Position ein oder aus. 
    
   Wenn Sie nur bestimmte SharePoint-Websites oder OneDrive-Konten einschließen möchten, wechseln Sie den **Status** auf ein, und klicken Sie dann auf die Links unter **einschließen** , um bestimmte Websites oder Konten auszuwählen. 
    
7. Wählen Sie weiter **Erweiterte Einstellungen verwenden** aus \> .
    
8. Wählen Sie **+ Neue Regel** aus.
    
9. Wechseln Sie im Regel-Editor unter **Benutzer Benachrichtigungen** auf den Status.
    
    ![Abschnitt "Benutzer Benachrichtigungen" des Regel-Editors](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> DLP-Richtlinien gelten für alle Dokumente, die mit der Richtlinie übereinstimmen, unabhängig davon, ob diese Dokumente neu oder vorhanden sind. Eine e-Mail-Benachrichtigung wird jedoch nur generiert, wenn neue Inhalte einer vorhandenen DLP-Richtlinie entsprechen. Vorhandene Inhalte werden geschützt, es wird jedoch keine Benutzerbenachrichtigung per e-Mail generiert.
  
## <a name="options-for-configuring-email-notifications"></a>Optionen zum Konfigurieren von e-Mail-Benachrichtigungen

Für jede Regel in einer DLP-Richtlinie haben Sie folgende Möglichkeiten:
  
- Senden Sie die Benachrichtigung an die Personen, die Sie auswählen. Diese Personen können den Besitzer des Inhalts, die Person, die den Inhalt zuletzt geändert hat, den Besitzer der Website, auf der der Inhalt gespeichert ist, oder einen bestimmten Benutzer einschließen.
    
- Passen Sie den Text an, der in der Benachrichtigung enthalten ist, indem Sie HTML oder Token verwenden. Weitere Informationen hierzu finden Sie im nachstehenden Abschnitt.
    
> [!NOTE]
>  E-Mail-Benachrichtigungen können nur an einzelne Empfänger gesendet werden, nicht an Gruppen oder Verteilerlisten. Nur neue Inhalte können eine e-Mail-Benachrichtigung auslösen. Durch das Bearbeiten vorhandener Inhalte werden Richtlinien Tipps ausgelöst, jedoch keine e-Mail-Benachrichtigung. 
  
![E-Mail-Benachrichtigungsoptionen](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a>Standardmäßige e-Mail-Benachrichtigung

Benachrichtigungen weisen eine Betreffzeile auf, die mit der ausgeführten Aktion beginnt, beispielsweise "Benachrichtigung", "Nachricht blockiert" für e-Mail oder "Zugriff blockiert" für Dokumente. Wenn es sich bei der Benachrichtigung um ein Dokument handelt, enthält der Benachrichtigungstext einen Link, der Sie zu der Website führt, auf der das Dokument gespeichert ist, und den richtlinientipp für das Dokument öffnet, in dem Sie Probleme beheben können (Weitere Informationen finden Sie im Abschnitt weiter unten unter Richtlinien Tipps). Wenn es sich bei der Benachrichtigung um eine Nachricht handelt, enthält die Benachrichtigung als Anlage die Nachricht, die mit einer DLP-Richtlinie übereinstimmt.
  
![Benachrichtigungsmeldung](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
Standardmäßig werden bei Benachrichtigungen für ein Element auf einer Website Text ähnlich der folgenden angezeigt. Der Benachrichtigungstext wird für jede Regel separat konfiguriert, sodass der angezeigte Text unterschiedlich ist, je nachdem, welche Regel abgeglichen wird.

|**Wenn die DLP-Richtlinienregel dies tut...**|**Die Standardbenachrichtigung für SharePoint-oder OneDrive für Unternehmen-Dokumente lautet dann...**|**Dann lautet die Standardbenachrichtigung für Outlook-Nachrichten...**|
|:-----|:-----|:-----|
|Sendet eine Benachrichtigung, aber keine Außerkraftsetzung zulässt  <br/> |Dieses Element steht in Konflikt mit einer Richtlinie in Ihrer Organisation.  <br/> |Ihre e-Mail-Nachricht steht in Konflikt mit einer Richtlinie in Ihrer Organisation.  <br/> |
|Blockiert den Zugriff, sendet eine Benachrichtigung und ermöglicht Außerkraftsetzung  <br/> |Dieses Element steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Wenn Sie diesen Konflikt nicht beheben, wird möglicherweise der Zugriff auf diese Datei blockiert.  <br/> |Ihre e-Mail-Nachricht steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Die Nachricht wurde nicht an alle Empfänger übermittelt.  <br/> |
|Blockiert den Zugriff und sendet eine Benachrichtigung.  <br/> |Dieses Element steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Der Zugriff auf dieses Element wird für alle Benutzer mit Ausnahme des Besitzers, des letzten Modifikators und des primären Websitesammlungsadministrators blockiert.  <br/> |Ihre e-Mail-Nachricht steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Die Nachricht wurde nicht an alle Empfänger übermittelt.  <br/> |
   
### <a name="custom-email-notification"></a>Benutzerdefinierte e-Mail-Benachrichtigung

Sie können eine benutzerdefinierte e-Mail-Benachrichtigung erstellen, anstatt die standardmäßige e-Mail-Benachrichtigung an Ihre Endbenutzer oder Administratoren zu senden. Die benutzerdefinierte e-Mail-Benachrichtigung unterstützt HTML und hat einen Grenzwert von 5.000 Zeichen. Sie können HTML verwenden, um Bilder, Formatierungen und andere Branding-Zeichen in die Benachrichtigung einzubeziehen.
  
Sie können auch die folgenden Token verwenden, um die e-Mail-Benachrichtigung anzupassen. Diese Token sind Variablen, die durch bestimmte Informationen in der gesendeten Benachrichtigung ersetzt werden.

|**Token**|**Beschreibung**|
|:-----|:-----|
|%% AppliedActions%%  <br/> |Die Aktionen, die auf den Inhalt angewendet werden.  <br/> |
|%% ContentURL%%  <br/> |Die URL des Dokuments auf der SharePoint Online Website oder OneDrive für Unternehmen Website.  <br/> |
|%%MatchedConditions%%  <br/> |Die Bedingungen, die mit dem Inhalt übereinstimmen. Verwenden Sie dieses Token, um Personen über mögliche Probleme mit dem Inhalt zu informieren.  <br/> |
   
![Benachrichtigungsmeldung, die angibt, wo Token angezeigt werden](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a>Optionen zum Konfigurieren von Richtlinien Tipps

Für jede Regel in einer DLP-Richtlinie können Sie Richtlinien Tipps für Folgendes konfigurieren:
  
- Benachrichtigen Sie einfach die Person, dass der Inhalt mit einer DLP-Richtlinie in Konflikt steht, damit Sie Aktionen zur Lösung des Konflikts ausführen können. Sie können den Standardtext verwenden (siehe unten stehende Tabellen) oder benutzerdefinierten Text zu den spezifischen Richtlinien Ihrer Organisation eingeben.
    
- Zulassen, dass die DLP-Richtlinie von der Person außer Kraft gesetzt wird. Optional können Sie Folgendes tun:
    
  - Die Person muss eine geschäftliche Begründung eingeben, um die Richtlinie außer Kraft zu setzen. Diese Informationen werden protokolliert und können in den DLP-Berichten im Abschnitt **Berichte** des Security &amp; Compliance Centers angezeigt werden. 
    
  - Zulassen, dass die Person eine falsch positive Meldung meldet und die DLP-Richtlinie außer Kraft setzt. Diese Informationen werden auch für die Berichterstellung protokolliert, sodass Sie falsch positive Ergebnisse zur Feinabstimmung Ihrer Regeln verwenden können.
    
![Optionen für Richtlinien Tipps](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
Möglicherweise wird eine DLP-Richtlinie auf OneDrive für Unternehmen Websites angewendet, die personenbezogene Informationen (PII) erkennen, und diese Richtlinie hat drei Regeln:
  
1. Erste Regel: Wenn in einem Dokument weniger als fünf Instanzen dieser vertraulichen Informationen erkannt werden und das Dokument für Personen innerhalb der Organisation freigegeben wird, wird mit der Aktion **Benachrichtigung senden** ein richtlinientipp angezeigt. Für Richtlinien Tipps sind keine Außerkraftsetzungsoptionen erforderlich, da diese Regel lediglich Personen benachrichtigt und nicht den Zugriff blockiert. 
    
2. Zweite Regel: Wenn mehr als fünf Instanzen dieser vertraulichen Informationen in einem Dokument erkannt werden und das Dokument für Personen innerhalb der Organisation freigegeben wird, schränkt die Aktion **Zugriff auf Inhalt blockieren** die Berechtigungen für die Datei ein, und die Aktion **Benachrichtigung senden** ermöglicht Benutzern das außer Kraft setzen der Aktionen in dieser Regel durch die Bereitstellung einer geschäftlichen Begründung. In Ihrem Unternehmen ist es manchmal erforderlich, dass interne Personen PII-Daten freigeben, und dass ihre DLP-Richtlinie diese Arbeit nicht blockiert. 
    
3. Dritte Regel: Wenn mehr als fünf Instanzen dieser vertraulichen Informationen in einem Dokument erkannt werden und das Dokument für Personen außerhalb der Organisation freigegeben wird, schränkt die Aktion **Zugriff auf Inhalt blockieren** die Berechtigungen für die Datei ein, und mit der Aktion **Benachrichtigung senden** können Benutzer die Aktionen in dieser Regel außer Kraft setzen, da die Informationen extern freigegeben werden. In keinem Fall dürfen Personen in Ihrer Organisation PII-Daten außerhalb der Organisation freigeben. 
    
Hier sind einige feine Punkte, die Sie bei der Verwendung eines Richtlinien Tipps zum Überschreiben einer Regel verstehen:
  
- Die Option zum außer Kraft setzen ist pro Regel und setzt alle Aktionen in der Regel außer Kraft (mit Ausnahme des Sendens einer Benachrichtigung, die nicht überschrieben werden kann).
    
- Es ist möglich, dass Inhalte mehreren Regeln in einer DLP-Richtlinie entsprechen, aber nur der richtlinientipp aus der restriktivsten, die höchste Priorität Regel wird angezeigt. So hat beispielsweise der Richtlinientipp zu einer Regel, die Zugriff auf Inhalte blockiert, Vorrang gegenüber dem Richtlinientipp zu einer Regel, die einfach nur eine Benachrichtigung sendet. Dadurch wird verhindert, dass Benutzern eine umfangreiche Liste von Richtlinientipps angezeigt wird.
    
- Wenn die Richtlinientipps in der restriktivsten Regel Benutzern erlauben, die Regel außer Kraft zu setzen, werden dadurch auch alle anderen Regeln überschrieben, die für den Inhalt gelten.
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>Richtlinien Tipps für OneDrive für Unternehmen Websites und SharePoint Online Websites

Wenn ein Dokument auf einer OneDrive für Unternehmen Website oder SharePoint Online Website einer Regel in einer DLP-Richtlinie entspricht und diese Regelrichtlinien Tipps verwendet, zeigen die Richtlinien Tipps spezielle Symbole im Dokument an:
  
1. Wenn die Regel eine Benachrichtigung über die Datei sendet, wird das Warnsymbol angezeigt.
    
2. Wenn die Regel den Zugriff auf das Dokument blockiert, wird das Symbol blockiert angezeigt.
    
   ![Richtlinientipp Symbole für Dokumente in einem OneDrive-Konto](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
Um Aktionen für ein Dokument durchführen zu können, wählen Sie \>  ![ in der oberen rechten Ecke der Seite ein Element Informations Informationsbereich auswählen ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) aus, um den Detailbereich \> **Ansichts richtlinientipp** zu öffnen.
  
Der richtlinientipp listet die Probleme mit dem Inhalt auf, und wenn die Richtlinien Tipps mit diesen Optionen konfiguriert sind, können Sie **Auflösen** auswählen und dann den richtlinientipp **außer Kraft setzen** oder ein falsch positives Ergebnis **melden** . 
  
![Informationsbereich mit richtlinientipp](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![Richtlinientipp mit Option zum außer Kraft setzen](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
DLP-Richtlinien werden mit Websites synchronisiert und Inhalte werden regelmäßig und asynchron mit diesen bewertet, sodass es möglicherweise eine kurze Verzögerung zwischen dem Zeitpunkt der Erstellung der DLP-Richtlinie und dem Zeitpunkt, zu dem die Richtlinien Tipps angezeigt werden, geben kann. Es kann eine ähnliche Verzögerung geben, wenn Sie einen richtlinientipp auflösen oder außer Kraft setzen, wenn das Symbol auf dem Dokument auf der Website verschwindet.
  
### <a name="default-text-for-policy-tips-on-sites"></a>Standardtext für Richtlinien Tipps auf Websites

Standardmäßig werden in Richtlinien Tipps für ein Element auf einer Website Text ähnlich der folgenden angezeigt. Der Benachrichtigungstext wird für jede Regel separat konfiguriert, sodass der angezeigte Text unterschiedlich ist, je nachdem, welche Regel abgeglichen wird.

|**Wenn die DLP-Richtlinienregel dies tut...**|**Dann lautet der Standardrichtlinien Tipp...**|
|:-----|:-----|
|Sendet eine Benachrichtigung, aber keine Außerkraftsetzung zulässt  <br/> |Dieses Element steht in Konflikt mit einer Richtlinie in Ihrer Organisation.  <br/> |
|Blockiert den Zugriff, sendet eine Benachrichtigung und ermöglicht Außerkraftsetzung  <br/> |Dieses Element steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Wenn Sie diesen Konflikt nicht beheben, wird möglicherweise der Zugriff auf diese Datei blockiert.  <br/> |
|Blockiert den Zugriff und sendet eine Benachrichtigung.  <br/> |Dieses Element steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Der Zugriff auf dieses Element wird für alle Benutzer mit Ausnahme des Besitzers, des letzten Modifikators und des primären Websitesammlungsadministrators blockiert.  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a>Benutzerdefinierter Text für Richtlinien Tipps auf Websites

Sie können den Text für Richtlinien Tipps separat von der e-Mail-Benachrichtigung anpassen. Im Gegensatz zu benutzerdefiniertem Text für e-Mail-Benachrichtigungen (siehe Abschnitt oben) akzeptiert der benutzerdefinierte Text für Richtlinien Tipps weder HTML noch Token. Stattdessen ist benutzerdefinierter Text für Richtlinien Tipps nur Text mit einem Grenzwert von 256 Zeichen.
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Richtlinien Tipps in Outlook im Internet und Outlook 2013 und höher

Wenn Sie eine neue e-Mail in Outlook im Internet und Outlook 2013 und höher erstellen, wird ein richtlinientipp angezeigt, wenn Sie Inhalte hinzufügen, die einer Regel in einer DLP-Richtlinie entsprechen, und diese Regel verwendet Richtlinien Tipps. Der richtlinientipp wird oben in der Nachricht oberhalb der Empfänger angezeigt, während die Nachricht zusammengesetzt wird.
  
![Richtlinientipp am Anfang einer zusammengesetzten Nachricht](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
Richtlinien Tipps funktionieren, ob die vertraulichen Informationen im Nachrichtentext, in der Betreffzeile oder sogar in einer Nachrichtenanlage angezeigt werden, wie hier dargestellt.
  
![Richtlinientipp, der zeigt, dass eine Anlage mit einer DLP-Richtlinie kollidiert](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
Wenn die Richtlinien Tipps so konfiguriert sind, dass Außerkraftsetzung zulässig ist, können Sie **Details anzeigen** \> **Außerkraftsetzung** \> Enter a Business Rechtfertigung oder Bericht eine falsch positive \> **Außerkraftsetzung** auswählen.
  
![Richtlinientipp in Nachricht erweitert zur Anzeige der Außerkraftsetzungsoption](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![Dialogfeld richtlinientipp, in dem Sie den richtlinientipp außer Kraft setzen können](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
Beachten Sie, dass beim Hinzufügen vertraulicher Informationen zu einer e-Mail möglicherweise Wartezeit zwischen dem Hinzufügen vertraulicher Informationen und dem Erscheinen der Richtlinien Tipps besteht.

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>Outlook 2013 und höher unterstützt das Anzeigen von Richtlinien Tipps für nur einige Bedingungen.

Derzeit unterstützt Outlook 2013 und höher nur für diese Bedingungen Richtlinien Tipps anzeigen:

- Inhalt enthält
- Inhalt ist freigegeben

Beachten Sie, dass alle diese Bedingungen in Outlook funktionieren, in denen Sie Inhalte abgleichen und Schutzaktionen für Inhalte erzwingen können. Das Anzeigen von Richtlinien Tipps für Benutzer wird jedoch noch nicht unterstützt.
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a>Richtlinien Tipps im Exchange Admin Center vs. Security &amp; Compliance Center

Richtlinien Tipps können entweder mit DLP-Richtlinien und Nachrichtenfluss Regeln funktionieren, die im Exchange Admin Center erstellt wurden, oder mit DLP-Richtlinien, die im Security &amp; Compliance Center erstellt wurden, jedoch nicht in beiden. Dies liegt daran, dass diese Richtlinien an unterschiedlichen Speicherorten gespeichert werden, aber Richtlinien Tipps nur von einem einzelnen Speicherort aus gezeichnet werden können.
  
Wenn Sie Richtlinien Tipps im Exchange Admin Center konfiguriert haben, werden alle Richtlinien Tipps, die Sie im Security &amp; Compliance Center konfigurieren, nicht für Benutzer in Outlook im Internet und Outlook 2013 und höher angezeigt, bis Sie die Tipps im Exchange Admin Center deaktivieren. Dadurch wird sichergestellt, dass Ihre aktuellen Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) weiterhin funktionsfähig sind, bis Sie sich für die Umstellung auf das Security &amp; Compliance Center entschieden haben.
  
Beachten Sie, dass Richtlinien Tipps zwar nur von einem einzigen Speicherort aus gezeichnet werden können, e-Mail-Benachrichtigungen jedoch immer gesendet werden, selbst wenn Sie DLP-Richtlinien sowohl im Security Compliance Center als auch im &amp; Exchange Admin Center verwenden.
  
### <a name="default-text-for-policy-tips-in-email"></a>Standardtext für Richtlinien Tipps in e-Mail

Standardmäßig wird in Richtlinien Tipps für e-Mails Text ähnlich der folgenden angezeigt.

|**Wenn die DLP-Richtlinienregel dies tut...**|**Dann lautet der Standardrichtlinien Tipp...**|
|:-----|:-----|
|Sendet eine Benachrichtigung, aber keine Außerkraftsetzung zulässt  <br/> |Ihre e-Mail-Nachricht steht in Konflikt mit einer Richtlinie in Ihrer Organisation.  <br/> |
|Blockiert den Zugriff, sendet eine Benachrichtigung und ermöglicht Außerkraftsetzung  <br/> |Ihre e-Mail-Nachricht steht in Konflikt mit einer Richtlinie in Ihrer Organisation.  <br/> |
|Blockiert den Zugriff und sendet eine Benachrichtigung.  <br/> |Ihre e-Mail-Nachricht steht in Konflikt mit einer Richtlinie in Ihrer Organisation.  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a>Richtlinien Tipps in Excel, PowerPoint und Word

Wenn Personen in den Desktop Versionen von Excel, PowerPoint und Word mit vertraulichen Inhalten arbeiten, können Richtlinien Tipps Sie in Echtzeit darüber informieren, dass der Inhalt mit einer DLP-Richtlinie in Konflikt steht. Dies erfordert Folgendes:
  
- Das Office-Dokument wird auf einer OneDrive für Unternehmen Website oder SharePoint Online Website gespeichert.
    
- Die Website ist in einer DLP-Richtlinie enthalten, die für die Verwendung von Richtlinien Tipps konfiguriert ist.
    
Office-Desktop Programme synchronisieren DLP-Richtlinien automatisch direkt von Office 365 und Scannen dann Ihre Dokumente, um sicherzustellen, dass Sie nicht mit ihren DLP-Richtlinien in Konflikt stehen und Richtlinien Tipps in Echtzeit anzeigen.

> [!NOTE]
> Office-Desktop Apps überprüfen Dokumente selbst, um zu ermitteln, ob DLP-Richtlinien Tipps angezeigt werden sollen; Es werden keine Richtlinien Tipps angezeigt, die SharePoint Online Websites oder OneDrive für Unternehmen Websites bereits ermittelt haben, sollten in einer Datei angezeigt werden. Daher wird möglicherweise nicht immer ein DLP-richtlinientipp in den Desktop-Apps angezeigt, die auf den Websites SharePoint Online Websites oder OneDrive für Unternehmen angezeigt werden. Im Gegensatz dazu zeigen die Office-Anwendungen im Internet nur DLP-Richtlinien Tipps, die SharePoint Online Websites oder OneDrive für Unternehmen Websites bereits ermittelt haben, sollten angezeigt werden.
  
Je nachdem, wie Sie die Richtlinien Tipps in der DLP-Richtlinie konfigurieren, können die Benutzer entscheiden, ob Sie den richtlinientipp einfach ignorieren, die Richtlinie mit oder ohne geschäftliche Begründung außer Kraft setzen oder ein falsch positives Ergebnis melden möchten.
  
Richtlinien Tipps werden auf der Statusleiste angezeigt.
  
![Nachrichtenleiste zeigt richtlinientipp in Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Außerdem werden Richtlinien Tipps im Backstage-Ansicht angezeigt (auf der Registerkarte **Datei** ). 
  
![Backstage zeigt richtlinientipp in Excel 2016](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
Wenn Richtlinien Tipps in der DLP-Richtlinie mit diesen Optionen konfiguriert sind, können Sie **Auflösen** auswählen, um einen richtlinientipp **außer Kraft zu setzen** oder ein falsch positives Ergebnis zu **melden** . 
  
![Optionen für richtlinientipp in Backstage in Excel 2016](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
In jedem dieser Office-Desktop Programme können Benutzer auswählen, dass Sie Richtlinien Tipps deaktivieren möchten. Wenn diese Option deaktiviert ist, werden Richtlinien Tipps, die einfache Benachrichtigungen sind, nicht auf der Statusleiste oder Backstage-Ansicht angezeigt (auf der Registerkarte **Datei** ). Es werden jedoch weiterhin Richtlinien Tipps zum Blockieren und außer Kraft setzen angezeigt, und Sie erhalten weiterhin die e-Mail-Benachrichtigung. Außerdem werden durch das Deaktivieren von Richtlinien Tipps das Dokument nicht von den darauf angewendeten DLP-Richtlinien ausgenommen. 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Standardtext für Richtlinien Tipps in Excel 2016, PowerPoint 2016 und Word 2016

Standardmäßig werden in der Nachrichtenleiste und Backstage-Ansicht eines geöffneten Dokuments Text ähnlich der folgenden angezeigt. Der Benachrichtigungstext wird für jede Regel separat konfiguriert, sodass der angezeigte Text unterschiedlich ist, je nachdem, welche Regel abgeglichen wird.

|**Wenn die DLP-Richtlinienregel dies tut...**|**Dann lautet der Standardrichtlinien Tipp...**|
|:-----|:-----|
|Sendet eine Benachrichtigung, aber keine Außerkraftsetzung zulässt  <br/> |Diese Datei steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Weitere Informationen finden Sie im Menü **Datei** .  <br/> |
|Blockiert den Zugriff, sendet eine Benachrichtigung und ermöglicht Außerkraftsetzung  <br/> |Diese Datei steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Wenn Sie diesen Konflikt nicht beheben, wird möglicherweise der Zugriff auf diese Datei blockiert. Weitere Informationen finden Sie im Menü **Datei** .  <br/> |
|Blockiert den Zugriff und sendet eine Benachrichtigung.  <br/> |Diese Datei steht in Konflikt mit einer Richtlinie in Ihrer Organisation. Wenn Sie diesen Konflikt nicht beheben, wird möglicherweise der Zugriff auf diese Datei blockiert. Weitere Informationen finden Sie im Menü **Datei** .  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a>Benutzerdefinierter Text für Richtlinien Tipps in Excel, PowerPoint und Word

Sie können den Text für Richtlinien Tipps separat von der e-Mail-Benachrichtigung anpassen. Im Gegensatz zu benutzerdefiniertem Text für e-Mail-Benachrichtigungen (siehe Abschnitt oben) akzeptiert der benutzerdefinierte Text für Richtlinien Tipps weder HTML noch Token. Stattdessen ist benutzerdefinierter Text für Richtlinien Tipps nur Text mit einem Grenzwert von 256 Zeichen.
  
## <a name="more-information"></a>Weitere Informationen

- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)
    
- [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md)
    
- [Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI- oder anderen Eigenschaften](protect-documents-that-have-fci-or-other-properties.md)
    
- [Bestandteile von DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md)
    
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
