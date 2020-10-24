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
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754106"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Warum Sie PowerShell für Microsoft 365 verwenden müssen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Mit dem Microsoft 365 Admin Center können Sie Ihre Microsoft 365-Benutzerkonten und-Lizenzen verwalten. Sie können auch Ihre Microsoft 365-Dienste wie Exchange Online, Teams und SharePoint Online verwalten. Wenn Sie stattdessen PowerShell verwenden, um diese Dienste zu verwalten, können Sie die Befehlszeilen-und Skriptsprachen Umgebung für Geschwindigkeit, Automatisierung und zusätzliche Funktionen nutzen.
  
In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell Microsoft 365 für Folgendes verwalten:
  
- Aufdecken zusätzlicher Informationen, die im Microsoft 365 Admin Center nicht angezeigt werden
    
- Konfigurieren von Features und Einstellungen nur mit PowerShell möglich
    
- Massenvorgänge
    
- Filtern von Daten
    
- Drucken oder Speichern von Daten
    
- Verwalten von Across-Diensten
    
Beachten Sie, dass es sich bei PowerShell für Microsoft 365 um eine Reihe von Modulen für Windows PowerShell handelt, bei denen es sich um eine Befehlszeilenumgebung für Windows-basierte Dienste und Plattformen handelt. Diese Umgebung erstellt eine Command-Shell-Sprache, die um zusätzliche Module erweitert werden kann. Es bietet eine Möglichkeit zur Ausführung einfacher oder komplexer Befehle oder Skripts. Nachdem Sie beispielsweise die PowerShell für Microsoft 365-Module installiert und eine Verbindung mit Ihrem Microsoft 365-Abonnement hergestellt haben, können Sie den folgenden Befehl ausführen, um alle Benutzerpostfächer für Microsoft Exchange Online aufzulisten:
  
```powershell
Get-Mailbox
```

Sie können die Liste der Postfächer auch mithilfe des Microsoft 365 Admin Center abrufen, aber die Elemente in allen Listen für alle Websites für alle Ihre Webanwendungen sind nicht einfach zu zählen.
  
PowerShell für Microsoft 365 wurde entwickelt, um Sie bei der Verwaltung von Microsoft 365 und nicht beim Ersetzen des Microsoft 365 Admin Center zu unterstützen. Administratoren müssen in der Lage sein, PowerShell für Microsoft 365 zu verwenden, da es einige Konfigurationsverfahren gibt, die nur über PowerShell für Microsoft 365-Befehle ausgeführt werden können. In diesen Fällen müssen Sie wissen, wie Sie:
  
- Installieren Sie die PowerShell für Microsoft 365-Module (nur einmal für jeden Administratorcomputer ausgeführt).
    
- Stellen Sie eine Verbindung zu Ihrem Microsoft 365-Abonnement her (einmal für jede PowerShell-Sitzung).
    
- Sammeln Sie die Informationen, die zum Ausführen der erforderlichen PowerShell für Microsoft 365-Befehle benötigt werden.
    
- Führen Sie PowerShell für Microsoft 365-Befehle aus.
    
Nachdem Sie diese grundlegenden Fertigkeiten kennen gelernt haben, müssen Sie die Postfachbenutzer nicht mithilfe des Befehls **Get-Mailbox** auflisten. Sie müssen auch nicht verstehen, wie Sie einen neuen Befehl wie den zuvor zitierten Befehl erstellen, um alle Elemente in allen Listen für alle Websites für alle Ihre Webanwendungen zu zählen. Microsoft und die Community von Administratoren können Ihnen bei diesen Aufgaben bei Bedarf behilflich sein.
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell für Microsoft 365 kann Informationen aufdecken, die Sie mit dem Microsoft 365 Admin Center nicht sehen können.

Im Microsoft 365 Admin Center werden viele nützliche Informationen angezeigt. Allerdings werden nicht alle möglichen Informationen angezeigt, die von Microsoft 365 über Benutzer, Lizenzen, Postfächer und Websites gespeichert werden. Im folgenden finden Sie ein Beispiel für *Benutzer und Gruppen* im Microsoft 365 Admin Center:
  
![Beispiel für die Anzeige von Benutzern und Gruppen im Microsoft 365 Admin Center.](../media/o365-powershell-users-and-groups.png)
  
Diese Ansicht stellt die Informationen bereit, die Sie in vielen Fällen benötigen. Es kann jedoch vorkommen, dass Sie mehr benötigen. Beispielsweise hängt die Microsoft 365-Lizenzierung (und die Microsoft 365-Funktionen, die einem Benutzer zur Verfügung stehen) teilweise vom geografischen Standort des Benutzers ab. Die Richtlinien und Features, die Sie auf einen Benutzer erweitern können, der in den Vereinigten Staaten lebt, sind möglicherweise nicht identisch mit denen, die Sie auf einen Benutzer in Indien oder Belgien erweitern können. Führen Sie die folgenden Schritte im Microsoft 365 Admin Center aus, um den geografischen Standort eines Benutzers zu ermitteln:
  
1. Doppelklicken Sie auf den **Anzeigenamen** des Benutzers.
    
2. Wählen Sie im Bereich Anzeige der Benutzereigenschaften die Option **Details**aus.
    
3. Wählen Sie in der Detailanzeige **Weitere Details**aus.
    
4. Scrollen Sie, bis Sie die Überschrift **Land oder Region**finden:
    
     ![Beispiel für die Regionsinformationen für einen Benutzer im Microsoft 365 Admin Center.](../media/o365-powershell-usage-location.png)
  
5. Notieren Sie den Anzeigenamen des Benutzers auf einem Blatt Papier, oder kopieren ihn in Editor.
    
Sie müssen diese Vorgehensweise für jeden Benutzer wiederholen. Wenn Sie viele Benutzer haben, kann dieser Vorgang langwierig sein. Mit PowerShell für Microsoft 365 können Sie diese Informationen für alle Benutzer mithilfe des folgenden Befehls anzeigen:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core unterstützt das Microsoft Azure Active Directory Modul für Windows PowerShell Modul und Cmdlets mit *MSOL* in Ihrem Namen nicht. Sie müssen diese Cmdlets aus Windows PowerShell ausführen.
>

Hier sehen Sie ein Beispiel der Ergebnisse:
  
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

Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen (**Get-AzureADUser**), aber nur den Namen und den Speicherort für jeden Benutzer anzeigen (**Select DisplayName, UsageLocation**).
  
Da PowerShell für Microsoft 365 eine Command-Shell-Sprache unterstützt, können Sie die durch den Befehl **Get-AzureADUser** erhaltenen Informationen weiter bearbeiten. Vielleicht möchten Sie diese Benutzer beispielsweise nach Ihrem Standort sortieren, alle brasilianischen Benutzer zusammen gruppieren, alle Benutzer in den Vereinigten Staaten zusammen und so weiter. Hier ist der Befehl:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

Hier sehen Sie ein Beispiel der Ergebnisse:
  
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

Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, zeigen Sie jedoch nur den Namen und den Speicherort für jeden Benutzer an, und sortieren Sie diese zuerst nach ihrem Speicherort und dann nach dem Namen (**Sort UsageLocation, DisplayName**).
  
Sie können auch zusätzliche Filterung verwenden. Wenn Sie beispielsweise nur Informationen zu Benutzern in Brasilien anzeigen möchten, verwenden Sie den folgenden Befehl:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

Hier sehen Sie ein Beispiel der Ergebnisse:
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, deren Standort Brasilien ist (**wobei {$ \_ . UsageLocation-EQ "br"}**), und zeigen Sie dann den Namen und den Speicherort für jeden Benutzer an.
  
 **Hinweis zu großen Domänen**
  
Wenn Sie eine große Domäne mit Zehntausenden von Benutzern haben, können Sie versuchen, einige der in diesem Artikel gezeigten Beispiele zu Einschränkungen führen. Basierend auf Faktoren wie Rechenleistung und verfügbarer Netzwerkbandbreite versuchen Sie möglicherweise, zu viel auf einmal zu tun. Große Organisationen möchten möglicherweise einige dieser PowerShell-Vorgänge in zwei Befehle aufteilen.

Der folgende Befehl gibt beispielsweise alle Benutzerkonten zurück und zeigt den Namen und den Speicherort für jede an:
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

Das funktioniert auch gut bei kleineren Domänen. In einer großen Organisation können Sie diesen Vorgang jedoch in zwei Befehle aufteilen: einen Befehl zum Speichern der Benutzerkontoinformationen in einer Variablen und einen anderen, um die erforderlichen Informationen anzuzeigen. Hier ein Beispiel:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

Die Interpretation dieses Satzes von PowerShell-Befehlen lautet:
1. Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen mit dem Namen $x (**$x = Get-AzureADUser**).
1.  Zeigt den Inhalt der Variablen *$x*an, enthält aber nur den Namen und den Speicherort für jeden Benutzer (**$x | Wählen Sie DisplayName, UsageLocation**).
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 verfügt über Features, die Sie nur mit PowerShell für Microsoft 365 konfigurieren können.

Das Microsoft 365 Admin Center soll den Zugriff auf allgemeine, nützliche Verwaltungsaufgaben ermöglichen, die für die meisten Umgebungen gelten. Das heißt, das Microsoft 365 Admin Center wurde so konzipiert, dass der typische Administrator die am häufigsten verwendeten Verwaltungsaufgaben ausführen kann. Es gibt jedoch einige Aufgaben, die im Admin Center nicht ausgeführt werden können.
  
Das Skype for Business Online Admin Center bietet beispielsweise ein paar Optionen zum Erstellen benutzerdefinierter Besprechungseinladungen:
  
![Beispiel für die Anzeige von benutzerdefinierten Besprechungseinladungen im Skype for Business Online Admin Center](../media/o365-powershell-meeting-invitation.png)
  
Mit diesen Einstellungen können Sie Besprechungseinladungen eine gewisse persönliche Note und Professionalität verleihen. Aber es gibt mehr für die Besprechungs Konfigurationseinstellungen, als einfach benutzerdefinierte Besprechungseinladungen zu erstellen. Besprechungen ermöglichen standardmäßig beispielsweise Folgendes:
  
- anonymen Benutzern, automatischen Zugang zu jeder Besprechung zu erhalten
    
- Teilnehmern, die Besprechung aufzuzeichnen.
    
- das Festlegen aller Benutzer in Ihrer Organisation als Referenten, wenn sie an der Besprechung teilnehmen.
    
Diese Einstellungen stehen im Skype for Business Online Admin Center nicht zur Verfügung. Sie können diese von PowerShell für Microsoft 365 steuern. Hier ist ein Befehl, mit dem diese drei Einstellungen deaktiviert werden:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> Zum Ausführen dieses Befehls müssen Sie das [Skype for Business Online PowerShell-Modul ](https://www.microsoft.com/download/details.aspx?id=39366)installieren.
  
Die Interpretation dieses PowerShell-Befehls lautet wie folgt:
 
1. Deaktivieren Sie in den Einstellungen für neue Skype for Business Online Besprechungen ("**CsMeetingConfiguration**") die Möglichkeit, dass anonyme Benutzer automatisch an Besprechungen teilnehmen können (**-AdmitAnonymousUsersByDefault $false**).
2.  Deaktivieren Sie die Möglichkeit für Teilnehmer, Besprechungen aufzuzeichnen (**-AllowConferenceRecording $false**).
3. Bezeichnen Sie nicht alle Benutzer aus Ihrer Organisation als Referenten (**-DesignateAsPresenter "None"**).
  
Um diese Standardeinstellungen wiederherzustellen (aktivieren Sie die Optionen), führen Sie den folgenden Befehl aus:
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

Es gibt auch andere ähnliche Szenarien, weshalb Administratoren wissen sollten, wie PowerShell für Microsoft 365-Befehle ausgeführt wird.
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>PowerShell für Microsoft 365 eignet sich hervorragend für Massenvorgänge

Visuelle Schnittstellen wie das Microsoft 365 Admin Center sind besonders wertvoll, wenn Sie einen einzigen Vorgang ausführen müssen. Wenn Sie beispielsweise ein Benutzerkonto deaktivieren müssen, können Sie mithilfe des Admin Centers schnell ein Kontrollkästchen suchen und deaktivieren. Dies ist möglicherweise einfacher als das Ausführen eines ähnlichen Vorgangs in PowerShell.
  
Wenn Sie jedoch viele Dinge oder einige ausgewählte Dinge in einer großen Menge anderer Dinge ändern müssen, ist das Microsoft 365 Admin Center möglicherweise nicht das beste Tool. Angenommen, Sie müssen das Präfix für Tausende von Telefonnummern ändern oder den spezifischen Benutzer *Ken Myers* aus allen SharePoint Online Websites entfernen. Wie würden Sie das im Microsoft 365 Admin Center tun?
  
Für das letzte Beispiel sagen, Sie haben mehrere hundert SharePoint Online Websites, und Sie wissen nicht, von welchen Ken Meyer ein Mitglied ist. Sie müssen mit dem Microsoft 365 Admin Center beginnen und dann dieses Verfahren für jeden Standort ausführen:
  
1. Wählen Sie die **URL** der Website aus.
    
2. Wählen Sie im Feld **Eigenschaften der Websitesammlung** den Link Website **Adresse** aus, um die Website zu öffnen.
    
3. Wählen Sie auf der Website **Freigeben**aus.
    
4. Wählen Sie im Dialogfeld **Freigeben** den Link aus, mit dem alle Benutzer angezeigt werden, die über Berechtigungen für die Website verfügen:
    
     ![Beispiel der Anzeige der Mitglieder einer SharePoint Online-Website im SharePoint Online Admin Center.](../media/o365-powershell-view-permissions.png)
  
5. Wählen Sie im Dialogfeld **freigegeben für** die Option **erweitert**aus.
    
6. Scrollen Sie in der Liste der Benutzer nach unten, suchen und wählen Sie Ken Myers aus (vorausgesetzt, er verfügt über Berechtigungen für die Website), und wählen Sie dann **Benutzerberechtigungen entfernen**aus.
    
Dies würde eine *lange* Zeit für mehrere hundert Standorte dauern.
  
Alternativ können Sie den folgenden Befehl in PowerShell für Microsoft 365 ausführen, um Ken Myers von allen Websites zu entfernen:
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> Für diesen Befehl müssen Sie das [SharePoint Online PowerShell-Modul](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)installieren. 
  
Die Interpretation dieses PowerShell-Befehls lautet: Rufen Sie alle SharePoint-Websites im aktuellen Microsoft 365-Abonnement (**Get-SPOSite**) ab, und entfernen Sie für jede Website Ken Meyer aus der Liste der Benutzer, die darauf zugreifen können (**foreach {Remove-Ehepartner-Site $ \_ . URL-LoginName "kenmyer \@ litwareinc.com"}**).
  
Microsoft 365 wird mitgeteilt, dass Ken Meyer von jeder Website entfernt werden soll, einschließlich derer, auf die er keinen Zugriff hat. Die Ergebnisse zeigen also Fehler für jene Websites an, auf die er keinen Zugriff hat. Wir können eine zusätzliche Bedingung für diesen Befehl verwenden, um Ken Meyer nur von den Websites zu entfernen, auf denen er sich in ihrer Anmeldeliste befindet. Die zurückgegebenen Fehler verursachen jedoch keinen Schaden für die Websites selbst. Dieser Befehl kann einige Minuten dauern, bis Hunderte von Websites ausgeführt werden, statt Stunden lang über das Microsoft 365 Admin Center zu arbeiten.
  
Hier ist ein weiteres Beispiel für Massenvorgänge. Verwenden Sie diesen Befehl, um *Bonnie Kearney*, einen neuen SharePoint-Administrator, zu allen Websites in der Organisation hinzuzufügen:
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

Die Interpretation dieses PowerShell-Befehls lautet: Abrufen aller SharePoint-Websites im aktuellen Microsoft 365-Abonnement und für jede Website ermöglichen Bonnie Kearney Zugriff durch Hinzufügen Ihres Anmeldenamens zur Gruppe Mitglieder der Website (**foreach {Add-Ehepartner-Site $ \_ . URL-LoginName "bkearney \@ litwareinc.com"-Gruppe "Members"}**).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>PowerShell für Microsoft 365 eignet sich hervorragend zum Filtern von Daten

Das Microsoft 365 Admin Center bietet verschiedene Möglichkeiten zum Filtern Ihrer Daten, um eine gezielte Teilmenge von Informationen zu finden. Mit Exchange können Sie beispielsweise leicht nach praktisch jeder Eigenschaft eines Benutzerpostfachs filtern. Hier ist beispielsweise die Liste der Postfächer für alle Benutzer, die in der Stadt Bloomington Leben:
  
![Beispiel für eine erweiterte Suche im Microsoft 365 Admin Center für die Liste der Postfächer für alle Benutzer, die in der Stadt Bloomington Leben.](../media/o365-powershell-advanced-search.png)
  
Im Exchange Admin Center können Sie auch Filterkriterien kombinieren. Beispielsweise können Sie die Postfächer für alle Personen finden, die in Bloomington Leben, und in der Finanzabteilung arbeiten.
  
Es gibt jedoch Einschränkungen, was Sie im Exchange Admin Center tun können. Sie können beispielsweise nicht so einfach die Postfächer von Personen finden, die in Bloomington *oder* San Diego Leben, oder die Postfächer für alle Personen, die nicht in Bloomington Leben.
  
Sie können den folgenden PowerShell für Microsoft 365-Befehl verwenden, um eine Liste von Postfächern für alle Personen zu erhalten, die in Bloomington oder San Diego Leben:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

Hier sehen Sie ein Beispiel der Ergebnisse:
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, die über ein Postfach in der Stadt San Diego oder Bloomington verfügen (**wobei {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-und ($ \_ . City-EQ "San Diego"-oder $ \_ . City-EQ "Bloomington")}**), und zeigen Sie dann den Namen und die Stadt für jeden an (**Wählen Sie DisplayName, Ort**) aus.
  
Und hier ist der Befehl zum Auflisten aller Postfächer für Personen, die an einer beliebigen Stelle mit Ausnahme von Bloomington Leben:
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

Hier sehen Sie ein Beispiel der Ergebnisse:
  
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

Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, deren Postfach sich nicht in der Stadt Bloomington befindet (**wobei {$ \_ . RecipientTypeDetails-EQ "User Mailbox"-und $ \_ . City-ne "Bloomington"}**), und zeigen Sie dann den Namen und die Stadt für jede an.
  
### <a name="use-wildcards"></a>Verwenden von Platzhaltern

Sie können auch Platzhalterzeichen in ihren PowerShell-Filtern verwenden, um einen Teil eines Namens abzugleichen. Nehmen wir beispielsweise an, dass Sie nach einem Benutzerkonto suchen. Sie können daran denken, dass der Nachname des Benutzers *Anderson* oder Maybe *Henderson* oder *Jorgenson*war.
  
Sie können den Benutzer im Microsoft 365 Admin Center nachverfolgen, indem Sie das Such Tool verwenden und drei verschiedene Suchvorgänge ausführen:
  
- Eine für  *Anderson* 
    
- Eine für  *Henderson* 
    
- Und eine für  *Jorgenson* 
    
Da alle drei Namen in "Son" enden, können Sie PowerShell mitteilen, dass alle Benutzer angezeigt werden sollen, deren Name in "Son" endet. Hier ist der Befehl:
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

Die Interpretation dieses PowerShell-Befehls lautet: alle Benutzer im aktuellen Microsoft 365-Abonnement abrufen, aber einen Filter verwenden, der nur die Benutzer auflistet, deren Nachname in "Son" endet (**-Filter ' {LastName-like " \* Son"} '**). Der \* steht für eine beliebige Gruppe von Zeichen, bei denen es sich um Buchstaben des Nachnamens des Benutzers handelt.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell für Microsoft 365 erleichtert das Drucken oder Speichern von Daten

Im Microsoft 365 Admin Center können Sie Listen mit Daten anzeigen. Hier ist ein Beispiel für die Skype for Business Online Admin Center mit einer Liste der Benutzer, die für Skype for Business Online aktiviert wurden:
  
![Beispiel für das Skype for Business Online Admin Center, in dem eine Liste von Benutzern angezeigt wird, die für Skype for Business Online aktiviert wurden.](../media/o365-powershell-lync-users.png)
  
Um diese Informationen in einer Datei zu speichern, müssen Sie Sie in ein Dokument oder Microsoft Excel Arbeitsblatt einfügen. In beiden Fällen ist möglicherweise eine zusätzliche Formatierung erforderlich. Darüber hinaus bietet das Microsoft 365 Admin Center keine Möglichkeit, die angezeigte Liste direkt zu drucken.
  
Glücklicherweise können Sie PowerShell verwenden, um die Liste nicht nur anzuzeigen, sondern in einer Datei zu speichern, die problemlos in Excel importiert werden kann. Im folgenden finden Sie einen Beispielbefehl zum Speichern von Skype for Business Online Benutzerdaten in einer CSV-Datei (Comma-Separated Values), die dann problemlos als Tabelle in ein Excel-Arbeitsblatt importiert werden kann:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

Hier sehen Sie ein Beispiel der Ergebnisse:
  
![Beispiel für eine Tabelle, die in ein Excel-Arbeitsblatt für Skype for Business Online Benutzerdaten importiert wurde, die in einer Datei mit Komma getrennten Werten gespeichert wurden.](../media/o365-powershell-data-in-excel.png)
  
Die Interpretation dieses PowerShell-Befehls lautet: Abrufen aller Skype for Business Online Benutzer im aktuellen Microsoft 365-Abonnement (**Get-CsOnlineUser**); Abrufen von Benutzername, UPN und Speicherort (**Select DisplayName, userPrincipalName, UsageLocation**); und speichern Sie diese Informationen dann in einer CSV-Datei namens c: \\ Logs \\SfBUsers.csv (**Export-CSV-Path "C: \\ Logs \\SfBUsers.csv"-NoTypeInformation**).
  
Sie können auch Optionen verwenden, um diese Liste als XML-Datei oder HTML-Seite zu speichern. Mit zusätzlichen PowerShell-Befehlen können Sie Sie in der Tat direkt als Excel-Datei speichern, wobei Sie eine beliebige benutzerdefinierte Formatierung wünschen.
  
Sie können auch die Ausgabe eines PowerShell-Befehls senden, mit dem eine Liste direkt an den Standarddrucker in Windows angezeigt wird. Hier ist ein Beispielbefehl:
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

Das gedruckte Dokument sieht wie folgt aus:
  
![Beispiel für ein gedrucktes Dokument, bei dem es sich um die Ausgabe eines PowerShell-Befehls handelt, der direkt an den Standarddrucker in Windows gesendet wurde.](../media/o365-powershell-printed-data.png)
  
Die Interpretation dieses PowerShell-Befehls lautet: Abrufen aller Skype for Business Online Benutzer im aktuellen Microsoft 365-Abonnement; nur den Benutzernamen, den UPN und den Speicherort abrufen; und senden Sie diese Informationen dann an den standardmäßigen Windows-Drucker (**Out-Printer**).
  
Das gedruckte Dokument hat dieselbe einfache Formatierung wie die Anzeige im PowerShell-Befehlsfenster. Um eine harte Kopie zu erhalten, fügen Sie einfach **| Out-Printer** an das Ende des Befehls.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Mit PowerShell für Microsoft 365 können Sie serverübergreifende Produkte verwalten.

Die Komponenten, aus denen Microsoft 365 besteht, sind für die Zusammenarbeit konzipiert. Nehmen wir beispielsweise an, Sie fügen einen neuen Benutzer zu Microsoft 365 hinzu, und geben Sie diese Informationen als Abteilung und Telefonnummer des Benutzers an. Diese Informationen sind dann verfügbar, wenn Sie auf die Benutzerinformationen in einem der Microsoft 365-Dienste zugreifen: Skype for Business Online, Exchange oder SharePoint.
  
Hierbei handelt es sich um allgemeine Informationen, die für die ganze Produktsuite gleich sind. Produktspezifische Informationen wie Informationen zum Exchange-Postfach eines Benutzers sind in der Regel nicht in der gesamten Suite verfügbar. Informationen darüber, ob das Postfach eines Benutzers aktiviert ist oder nicht, sind beispielsweise nur im Exchange Admin Center verfügbar.
  
Angenommen, Sie möchten einen Bericht erstellen, in dem die folgenden Informationen für alle Benutzer enthalten sind:
  
- Den Anzeigenamen des Benutzers
    
- Ob der Benutzer für Microsoft 365 lizenziert ist
    
- Ob das Exchange-Postfach des Benutzers aktiviert wurde
    
- Ob der Benutzer für Skype for Business Online aktiviert ist
    
Sie können einen solchen Bericht nicht ganz einfach im Microsoft 365 Admin Center erstellen. Stattdessen müssen Sie ein separates Dokument zum Speichern der Informationen erstellen, beispielsweise ein Excel-Arbeitsblatt. Anschließend rufen Sie alle Benutzernamen und Lizenzierungsinformationen aus dem Microsoft 365 Admin Center ab, erhalten Postfachinformationen aus dem Exchange Admin Center, erhalten Skype for Business Online Informationen aus dem Skype for Business Online Admin Center und kombinieren diese Informationen anschließend.
  
Die Alternative besteht darin, ein PowerShell-Skript zu verwenden, um den Bericht für Sie zu kompilieren.
  
Das folgende Beispielskript ist komplizierter als die Befehle, die Sie bisher in diesem Artikel gesehen haben. Es zeigt jedoch das Potenzial der Verwendung von PowerShell zum Erstellen von Informationsansichten, die sonst schwierig zu erhalten sind. Hier ist das Skript zum Kompilieren und Anzeigen der benötigten Liste:
  
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

Hier sehen Sie ein Beispiel der Ergebnisse:
  
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

1. Rufen Sie alle Benutzer im aktuellen Microsoft 365-Abonnement ab, und speichern Sie die Informationen in einer Variablen namens *$x* (**$x = Get-AzureADUser**).
1. Starten Sie eine Schleife, die über alle Benutzer in der Variablen $x (**foreach ($i in $x)**) ausgeführt wird.  
1. Definieren Sie eine Variable mit dem Namen *$y* , und speichern Sie die Postfachinformationen des Benutzers darin (**$y = Get-Mailbox-Identity $i. userPrincipalName**).
1. Fügen Sie den Benutzerinformationen mit dem Namen *IsMailBoxEnabled*eine neue Eigenschaft hinzu. Legen Sie den Wert der IsMailBoxEnabled-Eigenschaft des Postfachs des Benutzers fest (**$i | Add-Member-MemberType NoteProperty-Name IsMailBoxEnabled-Value $y. IsMailBoxEnabled**).
1. Definieren Sie eine Variable mit dem Namen *$y*, und speichern Sie die Skype for Business Online Informationen des Benutzers darin (**$y = Get-CsOnlineUser-Identity $i. userPrincipalName**).
1. Fügen Sie den Benutzerinformationen mit dem Namen *EnabledForSfB*eine neue Eigenschaft hinzu. Legen Sie den Wert der Enabled-Eigenschaft der Skype for Business Online Informationen des Benutzers fest (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-Value $y. Enabled**).
1. Zeigt die Liste der Benutzer an, enthält jedoch nur den Namen, unabhängig davon, ob Sie lizenziert sind, sowie die beiden neuen Eigenschaften, die angeben, ob Ihr Postfach aktiviert ist und ob Sie für Skype for Business Online aktiviert sind (**$x | Wählen Sie DisplayName, islicensed, IsMailboxEnabled, EnabledforSfB**).
  
## <a name="see-also"></a>Siehe auch

[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwenden der Windows PowerShell zum Erstellen von Berichten in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
