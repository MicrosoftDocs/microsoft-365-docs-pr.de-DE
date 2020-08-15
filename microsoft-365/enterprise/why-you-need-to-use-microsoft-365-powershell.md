---
title: Warum Sie PowerShell für Microsoft 365 verwenden müssen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Zusammenfassung: Hier erfahren Sie, warum Sie PowerShell zum Verwalten von Microsoft 365, in einigen Fällen effizienter und in anderen Fällen erforderlich verwenden müssen.'
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690306"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Warum Sie PowerShell für Microsoft 365 verwenden müssen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Mit dem Microsoft 365 Admin Center können Sie nicht nur Ihre Microsoft 365-Benutzerkonten und-Lizenzen verwalten, sondern auch Ihre Microsoft 365-Dienste wie Exchange Online, Teams und SharePoint Online verwalten. Sie können diese Elemente jedoch auch mit PowerShell-Befehlen verwalten, indem Sie eine Befehlszeilen-und Skriptsprachen Umgebung für Geschwindigkeit, Automatisierung und zusätzliche Funktionen nutzen.
  
In diesem Artikel erfahren Sie, wie Sie PowerShell zum Verwalten von Microsoft 365 verwenden können:
  
- Aufdecken zusätzlicher Informationen, die im Microsoft 365 Admin Center nicht angezeigt werden
    
- Konfigurieren von Features und Einstellungen nur mit PowerShell möglich
    
- Ausführen von Massenvorgängen
    
- Filtern von Daten
    
- Drucken oder Speichern von Daten
    
- Verwalten von Across-Diensten
    
Bevor Sie beginnen, sollten Sie wissen, dass PowerShell für Microsoft 365 eine Reihe von Modulen für Windows PowerShell ist, eine Befehlszeilenumgebung für Windows-basierte Dienste und Plattformen. Diese Umgebung erstellt eine Befehlsshell-Sprache, die um zusätzliche Module erweitert werden kann, und bietet eine Möglichkeit zum Ausführen einfacher oder komplexer Befehle oder Skripts. Wenn Sie beispielsweise die PowerShell für Microsoft 365-Module installiert und eine Verbindung mit Ihrem Microsoft 365-Abonnement hergestellt haben, können Sie diesen Befehl ausführen, um alle Benutzerpostfächer für Microsoft Exchange Online aufzulisten:
  
```powershell
Get-Mailbox
```

Das erhalten der Liste der Postfächer kann auch problemlos über das Microsoft 365 Admin Center erfolgen, aber die Anzahl der Elemente in allen Listen für alle Websites für alle Ihre Webanwendungen kann nicht einfach ausgeführt werden.
  
Beachten Sie, dass PowerShell für Microsoft 365 darauf ausgelegt ist, ihre Fähigkeit zum Verwalten von Microsoft 365 zu erweitern und zu verbessern, nicht um das Microsoft 365 Admin Center zu ersetzen. Als Administrator müssen Sie sich mit der Verwendung von PowerShell für Microsoft 365 zumindest vertraut machen, da es einige Konfigurationsverfahren gibt, die nur mit PowerShell für Microsoft 365-Befehle ausgeführt werden können. In diesen Fällen müssen Sie sich mit den folgenden Themen vertraut machen:
  
- Installieren Sie die PowerShell für Microsoft 365-Module (nur einmal für jeden Administratorcomputer ausgeführt).
    
- Stellen Sie eine Verbindung zu Ihrem Microsoft 365-Abonnement her (einmal für jede PowerShell-Sitzung ausgeführt).
    
- Sammeln Sie die Informationen, die zum Ausführen der erforderlichen PowerShell für Microsoft 365-Befehle benötigt werden.
    
- Führen Sie die PowerShell für Microsoft 365-Befehle erfolgreich aus.
    
Nachdem Sie diese grundlegenden Fähigkeiten erlernt haben, müssen Sie Ihre Postfachbenutzer nicht mit dem Befehl **Get-Mailbox** auflisten, und Sie müssen nicht verstehen, wie ein neuer Befehl wie der vorherige erstellt wird, um alle Elemente in allen Listen für alle Standorte für alle Web-Apps zu zählen. Microsoft und die Community von Administratoren können Ihnen bei Bedarf behilflich sein.
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a>PowerShell für Microsoft 365 kann zusätzliche Informationen aufdecken, die Sie mit dem Microsoft 365 Admin Center nicht sehen können.

Im Microsoft 365 Admin Center werden viele nützliche Informationen angezeigt, aber das bedeutet nicht, dass alle möglichen Informationen angezeigt werden, die von Microsoft 365 für Benutzer, Lizenzen, Postfächer und Websites gespeichert werden. Im folgenden finden Sie ein Beispiel für **Benutzer und Gruppen** im Microsoft 365 Admin Center:
  
![Beispiel für die Anzeige von Benutzern und Gruppen im Microsoft 365 Admin Center.](../media/o365-powershell-users-and-groups.png)
  
Hier werden für zahlreiche Zwecke die benötigten Informationen angezeigt. Es kann jedoch vorkommen, dass Sie mehr benötigen. Beispielsweise hängen Microsoft 365-Lizenzierung (und die Microsoft 365-Funktionen, die einem Benutzer zur Verfügung stehen) teilweise von dem geografischen Standort dieses Benutzers ab. Die Richtlinien und Features, die Sie auf einen Benutzer erweitern können, der in den USA lebt, sind möglicherweise nicht die gleichen Richtlinien und Features, die Sie auf einen Benutzer erweitern können der in Indien oder in Belgien lebt. Sie können das Microsoft 365 Admin Center verwenden, um den geografischen Standort eines Benutzers mit den folgenden Schritten zu ermitteln:
  
1. Doppelklicken Sie auf den **Anzeigenamen** des Benutzers.
    
2. Klicken Sie im Bereich "Benutzereigenschaften" auf **Details**.
    
3. Klicken Sie unter "Details" auf **Zusätzliche Details**.
    
4. Führen Sie einen Bildlauf nach unten bis zu **Land oder Region** aus.
    
     ![Beispiel für die Regionsinformationen für einen Benutzer im Microsoft 365 Admin Center.](../media/o365-powershell-usage-location.png)
  
5. Notieren Sie den Anzeigenamen des Benutzers auf einem Blatt Papier, oder kopieren ihn in Editor. 
    
Sie müssen diese Vorgehensweise für jeden Benutzer wiederholen. Bei zahlreichen Benutzern kann dies eine mühsame Aufgabe sein. Mit PowerShell für Microsoft 365 können Sie diese Informationen für alle Benutzer mit dem folgenden Befehl anzeigen:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen ( **Get-AzureADUser** ), aber nur den Namen und den Speicherort für jeden Benutzer anzeigen ( **Select DisplayName, UsageLocation** ).
  
Da PowerShell für Microsoft 365 eine Command Shell-Sprache unterstützt, können Sie die Informationen, die Sie über den Befehl **Get-AzureADUser** erhalten haben, weiter bearbeiten. Vielleicht möchten Sie diese Benutzer beispielsweise nach Ihrem Standort sortieren, alle brasilianischen Benutzer zusammen gruppieren, alle Benutzer in den USA zusammen usw. Hier ist der Befehl:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, zeigen Sie jedoch nur den Namen und den Speicherort für jeden Benutzer an, und sortieren Sie diese zuerst nach ihrem Speicherort und anschließend nach Ihren Namen ( **Sort UsageLocation, DisplayName** ).
  
Sie können auch eine zusätzliche Filterung verwenden. Wenn Sie beispielsweise nur Informationen zu Benutzern in Brasilien anzeigen möchten, verwenden Sie den folgenden Befehl:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, deren Standort Brasilien ist ( **wobei {$ \_ . UsageLocation-EQ "br"}** ), und zeigen Sie dann den Namen und den Speicherort für jeden Benutzer an.
  
 **Ein kurzer Hinweis zu größeren Domänen**
  
Wenn Sie eine sehr große Domäne mit Zehntausenden von Benutzers haben, könnte dies bei einigen Beispielen in diesem Artikel zu "Einschränkungen" kommen. Je nach Computerleistung und verfügbarer Bandbreite möchten Sie zu viel auf einmal. Aus diesem Grund möchten größere Organisationen möglicherweise einige dieser PowerShell für Microsoft 365-Befehle in zwei Befehle aufteilen. Dieser einer Befehle gibt beispielsweise alle Benutzerkonten zurück und zeigt den Namen und Standort für jedes Konto an:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Das funktioniert auch gut bei kleineren Domänen. In großen Organisationen müssen Sie den Befehl möglicherweise in zwei Befehle aufteilen: Ein Befehl zum Speichern der Benutzerkontoinformationen in einer Variablen und ein anderer Befehl zum Anzeigen der erforderlichen Informationen. Es folgt ein Beispiel:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

Die Interpretation dieses Satzes von PowerShell-Befehlen lautet:
- Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen mit dem Namen $x ( **$x = Get-AzureADUser** ).
- Den Inhalt der Variablen „$x“ anzeigen, dabei aber für jeden Benutzer nur Namen und Standort einschließen (**$x | Select DisplayName, UsageLocation**)
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 verfügt über Features, die Sie nur mit PowerShell für Microsoft 365 konfigurieren können.

Das Microsoft 365 Admin Center soll den Zugriff auf die am häufigsten oder bedeutsamsten administrativen Aufgaben ermöglichen, die für die meisten Personen gelten. Das heißt, das Microsoft 365 Admin Center wurde so konzipiert, dass der typische Administrator mithilfe des Tools die am häufigsten verwendeten Verwaltungsaufgaben ausführen kann. Mit dieser Definition bedeutet dies, dass es einige Aufgaben gibt, die nicht mithilfe des Microsoft 365 Admin Center ausgeführt werden können.
  
Das Skype for Business Online Admin Center bietet beispielsweise ein paar Optionen zum Erstellen benutzerdefinierter Besprechungseinladungen:
  
![Beispiel für die Anzeige von benutzerdefinierten Besprechungseinladungen im Skype for Business Online Admin Center](../media/o365-powershell-meeting-invitation.png)
  
Mit diesen Einstellungen können Sie Besprechungseinladungen eine gewisse persönliche Note und Professionalität verleihen. Besprechungskonfigurationseinstellungen erlauben Ihnen jedoch mehr, als einfach benutzerdefinierte Besprechungseinladungen zu erstellen. Besprechungen ermöglichen standardmäßig beispielsweise Folgendes:
  
- anonymen Benutzern, automatischen Zugang zu jeder Besprechung zu erhalten
    
- Teilnehmern, die Besprechung aufzuzeichnen.
    
- das Festlegen aller Benutzer in Ihrer Organisation als Referenten, wenn sie an der Besprechung teilnehmen.
    
Diese Einstellungen sind im Skype for Business Online Admin Center nicht verfügbar. Sie können Sie jedoch über PowerShell für Microsoft 365 steuern. Nachfolgend sehen Sie einen Befehl, der diese drei Einstellungen deaktiviert:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Für diesen Befehl müssen Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366) installieren. 
  
> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: für die Einstellungen für neue Skype for Business Online Besprechungen (" **CsMeetingConfiguration** "), deaktivieren Sie die Möglichkeit, dass anonyme Benutzer automatisch an Besprechungen teilnehmen können ( **-AdmitAnonymousUsersByDefault $false** ), deaktivieren Sie die Möglichkeit, Besprechungen zu erfassen ( **-AllowConferenceRecording $false** ), und legen Sie nicht alle Benutzer aus Ihrer Organisation als Referenten fest ( **-DesignateAsPresenter "None"** ).
  
Wenn Sie Ihre Meinung ändern und diese Standardeinstellungen wiederherstellen möchten (alle aktiviert), führen Sie den folgenden Befehl aus:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Dies ist nur ein Beispiel. Es gibt andere, daher müssen Sie sich als Administrator mit der Ausführung von PowerShell für Microsoft 365-Befehle vertraut machen.
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a>PowerShell für Microsoft 365 eignet sich hervorragend zum Ausführen von Massenvorgängen

Historisch gesehen sind visuelle Schnittstellen wie das Microsoft 365 Admin Center besonders wertvoll, wenn Sie einen einzelnen Vorgang ausführen müssen. Wenn Sie beispielsweise ein Benutzerkonto deaktivieren müssen, können Sie das Microsoft 365 Admin Center verwenden, um ein CheckBox-Steuerelement schnell zu finden und zu deaktivieren. Dies kann einfacher sein, als eine ähnliche Operation in PowerShell durchführen.
  
Wenn Sie jedoch viele Dinge oder einige ausgewählte Dinge in einer großen Menge anderer Dinge ändern müssen, ist das Microsoft 365 Admin Center möglicherweise nicht die beste Nutzung ihrer Zeit. Wenn Sie beispielsweise das Präfix für Tausende von Telefonnummern ändern oder einen bestimmten Benutzer, Ken Myers, von all Ihren SharePoint Online Websites entfernen mussten, wie würden Sie dies im Microsoft 365 Admin Center tun?
  
Beim zweiten Beispiel haben Sie mehrere Hundert SharePoint Online-Standorte und wissen nicht einmal, bei welchen Ken Meyer ein Mitglied ist. Das bedeutet, dass Sie am Microsoft 365 Admin Center beginnen und dann dieses Verfahren für jeden Standort ausführen müssen:
  
1. Klicken Sie auf die **URL** des Standorts.
    
2. Klicken Sie im Feld **Websitesammlungs-Eigenschaften** auf den Link **Websiteadresse**, um die Website zu öffnen.
    
3. Klicken Sie auf der Website auf **Freigabe**.
    
4. Klicken Sie im Dialogfeld **Freigabe** auf den Link, der Ihnen alle Benutzer mit Berechtigungen für die Website zeigt:
    
     ![Beispiel der Anzeige der Mitglieder einer SharePoint Online-Website im SharePoint Online Admin Center.](../media/o365-powershell-view-permissions.png)
  
5. Klicken Sie im Dialogfeld **Freigegeben für** auf **Erweitert**.
    
6. Führen Sie in der Liste der Benutzer einen Bildlauf nach unten zu Ken Myer durch, wählen Sie ihn aus (angenommen, dass er Berechtigungen für diese Website besitzt), und klicken Sie dann auf **Benutzerberechtigungen entfernen**.
    
Dies kann bei mehreren Hundert Seiten lange dauern.
  
Die Alternative besteht darin, PowerShell für Microsoft 365 und den folgenden Befehl zum Entfernen von Ken Myers von allen ihren Websites zu verwenden:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Für diesen Befehl müssen Sie das [SharePoint Online PowerShell-Modul](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installieren. 
  
> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement ( **Get-SPOSite** ) ab, und entfernen Sie für jeden Standort Ken Meyer aus der Liste der Benutzer, die darauf zugreifen können ( **foreach {Remove-Ehepartner-Site $ \_ . URL-LoginName "kenmyer@litwareinc.com"}** ).
  
Da wir Microsoft 365 sagen, Ken Meyer von jeder Website zu entfernen, einschließlich derer, in denen er keinen Zugriff hat, zeigt die Anzeige dieses Befehls Fehler für die Websites an, in denen der Zugriff derzeit nicht erfolgt. Wir können eine zusätzliche Bedingung für diesen Befehl verwenden, um Ken Meyer nur von den Standorten zu entfernen, an denen er in der Anmeldeliste vorhanden ist, die aufgeführten Fehler richten jedoch an den Standorten selbst keinen Schaden an. Dieser Befehl kann einige Minuten dauern, bis Hunderte von Websites ausgeführt werden, statt Stunden lang über das Microsoft 365 Admin Center zu arbeiten.
  
Nachfolgend finden Sie ein weiteres Beispiel für eine Massenoperation. Verwenden Sie diesen Befehl, um Bonnie Kearney, einen neuen SharePoint-Administrator, zu allen Standorten in der Organisation hinzuzufügen:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement und für jede Website ab, und gewähren Sie Bonnie Kearney Zugriff, indem Sie Ihren Anmeldenamen zur Mitgliedergruppe der Website hinzufügen ( **foreach {Add-Partner-Site $ \_ . URL-LoginName "bkearney@litwareinc.com"-Gruppe "Members"}** ).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell für Microsoft 365 eignet sich hervorragend zum Filtern von Daten

Das Microsoft 365 Admin Center bietet verschiedene Möglichkeiten zum Filtern Ihrer Daten, um eine gezielte Teilmenge von Informationen schnell und einfach zu finden. Mit Exchange können Sie beispielsweise leicht nach praktisch jeder Eigenschaft eines Benutzerpostfachs filtern. Nachfolgend sehen Sie beispielsweise die Liste der Postfächer aller Benutzer, die in Bloomington wohnen:
  
![Beispiel für eine erweiterte Suche im Microsoft 365 Admin Center für die Liste der Postfächer für alle Benutzer, die in der Stadt Bloomington Leben.](../media/o365-powershell-advanced-search.png)
  
Im Exchange Admin Center können Sie auch Filterkriterien kombinieren. Sie können beispielsweise nach den Postfächern aller in Bloomington lebenden Personen suchen, die zudem in der Finanzabteilung arbeiten. 
  
Es gibt jedoch Einschränkungen dafür, was mit dem Exchange Admin Center alles möglich ist. Vielleicht möchten Sie beispielsweise die Postfächer aller in Bloomington oder San Diego lebenden Personen suchen oder die Postfächer aller Personen, die nicht in Bloomington leben. 
  
Mit PowerShell für Microsoft 365 können Sie eine Liste von Postfächern für alle Personen erhalten, die in den Städten Bloomington oder San Diego mit folgendem Befehl Leben:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Abrufen aller Benutzer des aktuellen Microsoft 365-Abonnements mit einem Postfach in den Städten San Diego oder Bloomington ( **wobei {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-und ($ \_ . City-EQ "San Diego"-oder $ \_ . City-EQ "Bloomington")}** ), und zeigen Sie dann den Namen und die Stadt für jeden an ( **Wählen Sie DisplayName, Ort** ) aus.
  
Verwenden Sie den folgenden Befehl, um alle Postfächer von Benutzern aufzuführen, die überall leben, nur nicht in Bloomington:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Benutzer des aktuellen Microsoft 365-Abonnements ab, deren Postfach sich nicht in der Stadt Bloomington befindet ( **wobei {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-und $ \_ . City-ne "Bloomington"}** ), und zeigen Sie dann den Namen und die Stadt für jeden an.
  
Sie können auch Platzhalterzeichen in ihren PowerShell-Filtern verwenden, um einen Teil eines Namens abzugleichen. Angenommen, Sie suchen nach einem Benutzerkonto, und Sie können sich nur daran erinnern, dass der Nachname Anderson oder vielleicht Henderson oder vielleicht aber auch Jorgenson war.
  
Sie können den Benutzer im Microsoft 365 Admin Center nachverfolgen, indem Sie das Such Tool verwenden und drei verschiedene Suchvorgänge ausführen:
  
- Eine für  *Anderson* 
    
- Eine für  *Henderson* 
    
- Und eine für  *Jorgenson* 
    
Da alle drei Namen in "Son" enden, können Sie PowerShell mitteilen, dass alle Benutzer angezeigt werden sollen, deren Name in "Son" endet. Hier ist der Befehl:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, aber einen Filter verwenden, der nur die Benutzer auflistet, deren Nachname in "Son" endet ( **-Filter ' {LastName-like " \* Son"} '** ). Der \* steht für eine beliebige Gruppe von Zeichen, bei denen es sich um Buchstaben im Fall des Nachnamens des Benutzers handelt.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell für Microsoft 365 erleichtert das Drucken oder Speichern von Daten

Im Microsoft 365 Admin Center können Sie Listen mit Daten anzeigen. Nachfolgend sehen Sie ein Beispiel im Skype for Business Online Admin Center, bei dem eine Liste von Benutzern angezeigt wird, die für Skype for Business Online aktiviert wurden.
  
![Beispiel für das Skype for Business Online Admin Center, in dem eine Liste von Benutzern angezeigt wird, die für Skype for Business Online aktiviert wurden.](../media/o365-powershell-lync-users.png)
  
Um diese Informationen in einer Datei zu speichern, müssen Sie sie kopieren und in ein Dokument oder in Excel einfügen. Für das Kopieren ist auf jeden Fall eine zusätzliche Formatierung erforderlich. Darüber hinaus bietet das Microsoft 365 Admin Center keine Möglichkeit, die angezeigte Liste direkt zu drucken.
  
Glücklicherweise können Sie PowerShell verwenden, um die Liste nicht nur anzuzeigen, sondern in einer Datei zu speichern, die problemlos in Excel importiert werden kann. Nachfolgend sehen Sie einen Beispielbefehl, um Skype for Business Online-Benutzerdaten in einer CSV-Datei (durch Trennzeichen getrennte Datei) zu speichern, die einfach als Tabelle in ein Excel-Arbeitsblatt importiert werden kann.
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
![Beispiel für eine Tabelle, die in ein Excel-Arbeitsblatt importiert wurde, mit Skype for Business Online-Benutzerdaten, die als CSV-Datei gespeichert wurden.](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Skype for Business Online Benutzer im aktuellen Microsoft 365-Abonnement ab ( **Get-CsOnlineUser** ), beziehen Sie nur den Benutzernamen, den UPN und den Speicherort ( **Wählen Sie DisplayName, userPrincipalName, UsageLocation** ) aus, und speichern Sie diese Informationen dann in der CSV-Datei namens C: \\ Logs \\SfBUsers.csv ( **Export-CSV-Path "C: \\ Logs \\SfBUsers.csv"-NoTypeInformation**
  
Sie können auch Optionen verwenden, um diese Liste als XML-Datei oder als HTML-Seite zu speichern. Mit zusätzlichen PowerShell-Befehlen könnten Sie die Datei direkt als Excel-Datei mit beliebigen benutzerdefinierten Formatierungen speichern. 
  
Sie können auch die Ausgabe eines PowerShell-Befehls senden, mit dem eine Liste direkt an den Standarddrucker in Windows angezeigt wird. Nachfolgend sehen Sie einen Beispielbefehl:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Das gedruckte Dokument sieht wie folgt aus:
  
![Beispiel für ein gedrucktes Dokument, bei dem es sich um die Ausgabe eines PowerShell-Befehls handelt, der direkt auf dem Standarddrucker in Windows aufgeführt ist.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Skype for Business Online Benutzer im aktuellen Microsoft 365-Abonnement ab, beziehen Sie nur den Benutzernamen, den UPN und den Speicherort, und senden Sie diese Informationen dann an den standardmäßigen Windows-Drucker ( **Out-Printer** ).
  
Das gedruckte Dokument hat dieselbe einfache Formatierung wie die Anzeige im PowerShell-Befehlsfenster, aber nachdem Sie einen PowerShell-Befehl erstellt haben, um die benötigten Elemente aufzulisten, fügen Sie einfach **| Out-Printer** an das Ende des Befehls, um eine Kopie aus dem Arbeitsspeicher zu erhalten.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Mit PowerShell für Microsoft 365 können Sie serverübergreifende Produkte verwalten.

Die verschiedenen Komponenten, aus denen Microsoft 365 besteht, sind für die Zusammenarbeit konzipiert. Nehmen Sie beispielsweise an, dass Sie einen neuen Benutzer zu Microsoft 365 hinzufügen und, wenn Sie dies tun, diese Informationen als Abteilung und Telefonnummer des Benutzers angeben. Diese Informationen sind dann verfügbar, wenn Sie über einen der Microsoft 365-Dienste auf die Informationen des Benutzers zugreifen: Skype for Business Online, Exchange oder SharePoint Online.
  
Hierbei handelt es sich um allgemeine Informationen, die für die ganze Produktsuite gleich sind. Produktspezifische Informationen, wie die zu einem Exchange-Benutzerpostfach, sind in der Regel nicht in der gesamten Suite verfügbar. Wenn Sie beispielsweise wissen möchten, ob das Postfach eines Benutzers aktiviert ist oder nicht, sind diese Informationen nur im Exchange Admin Center verfügbar. 
  
Angenommen, Sie möchten einen Bericht erstellen, in dem die folgenden Informationen für alle Benutzer enthalten sind:
  
- Den Anzeigenamen des Benutzers
    
- Ob der Benutzer für Microsoft 365 lizenziert ist
    
- Ob das Exchange-Postfach des Benutzers aktiviert wurde
    
- Ob der Benutzer für Skype for Business Online aktiviert ist
    
Sie können derzeit nicht das Microsoft 365 Admin Center verwenden, um einen solchen Bericht problemlos zu erstellen. Stattdessen müssen Sie ein separates Dokument erstellen, um die Informationen wie ein Excel-Arbeitsblatt zu speichern und alle Benutzernamen und Lizenzierungsinformationen aus dem Microsoft 365 Admin Center abzurufen, Postfachinformationen aus dem Exchange Admin Center abzurufen, Skype for Business Online Informationen aus dem Skype for Business Online Admin Center abzurufen und diese Informationen dann zusammenzufassen und zu kombinieren.
  
Die Alternative besteht darin, ein PowerShell-Skript zu verwenden, um diesen Bericht für Sie zu kompilieren.
  
Das folgende Beispielskript ist komplizierter als die bisher in diesem Artikel gezeigten Befehle. Es zeigt jedoch das Potenzial der Verwendung von PowerShell, um Ansichten von Informationen zu erstellen, die ansonsten sehr schwierig zu tun sind. Nachfolgend sehen Sie das Skript, das die erforderliche Liste kompilieren und anzeigen kann:
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

Nachfolgend sehen Sie ein Beispiel der Anzeige:
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

Die Interpretation dieses PowerShell-Skripts lautet:  

- Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen mit dem Namen $x ( **$x = Get-AzureADUser** ).
- Eine Schleife starten, die über alle Benutzer in der Variablen mit dem Namen $x ausgeführt wird (**foreach ($i in $x)**).  
- Eine Variable mit dem Namen $y definieren und die Postfachinformationen des Benutzers darin speichern (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).
- Eine neue Eigenschaft zu den Benutzerinformationen mit dem Namen IsMailBoxEnabled hinzufügen und diese als Wert der IsMailBoxEnabled-Eigenschaft des Benutzerpostfachs hinzufügen (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).
- Eine Variable mit dem Namen $y definieren und die Skype for Business Online-Informationen des Benutzers darin speichern (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).
- Eine neue Eigenschaft mit dem Namen EnabledForSfB zu den Benutzerinformationen hinzufügen und diese auf den Wert der Enabled-Eigenschaft der Skype_for_Business_Online-Informationen des Benutzers festlegen (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).
- Die Benutzerliste anzeigen, dabei aber jeweils nur den Namen, den Lizenzstatus und die beiden neuen Eigenschaften einschließen, die angeben, ob das Postfach aktiviert ist und ob der jeweilige Benutzer für Skype for Business Online aktiviert ist (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**)
  
## <a name="see-also"></a>Siehe auch

[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwenden der Windows PowerShell zum Erstellen von Berichten in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)

