---
title: Verschieben einer OneDrive-Website an einen anderen geografischen Standort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Hier finden Sie Informationen zum Verschieben OneDrive Standorts an einen anderen geografischen Standort, einschließlich der Planung von Standortbewegungen und der Kommunikation von Erwartungen an Benutzer.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690261"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>Verschieben einer OneDrive-Website an einen anderen geografischen Standort 

Mit OneDrive geo move können Sie die Benutzerdaten OneDrive an einen anderen geografischen Standort verschieben. OneDrive geo move wird vom SharePoint Online-Administrator oder vom globalen Microsoft 365 durchgeführt. Bevor Sie mit einer OneDrive beginnen, müssen Sie den Benutzer benachrichtigen, dessen OneDrive verschoben wird, und empfehlen, alle Dateien für die Dauer des Verschiebens zu schließen. (Wenn der Benutzer während des Verschiebens ein Dokument mit dem Office-Client geöffnet hat, muss das Dokument nach Abschluss des Verschiebens am neuen Speicherort gespeichert werden.) Die Bewegung kann bei Bedarf für eine zukünftige Zeit geplant werden.

Der OneDrive verwendet Azure Blob Storage zum Speichern von Inhalten. Das Storage-Blob, das der Benutzeradresse OneDrive zugeordnet ist, wird innerhalb von 40 Tagen nach dem OneDrive, das dem Benutzer zur Verfügung steht, von der Quelle an den geografischen Zielspeicherort verschoben. Der Zugriff auf die Benutzerdaten OneDrive wird wiederhergestellt, sobald die Zieladresse OneDrive verfügbar ist.

In dem Zeitfenster, in dem geografische Standorte in OneDrive verschoben werden (ca. 2 bis 6 Stunden), ist die OneDrive-Umgebung des Benutzers schreibgeschützt. Der Benutzer kann weiterhin auf seine Dateien über den OneDrive-Synchronisierungsclient oder die OneDrive-Website in SharePoint Online zugreifen. Nach Abschluss des Verschiebevorgangs des geografischen Standorts in OneDrive wird der Benutzer automatisch mit OneDrive an seinem geografischen Zielstandort verbunden, wenn er in dem Microsoft 365-App-Startfeld zu OneDrive navigiert. Der Synchronisierungsclient startet automatisch die Synchronisierung an dem neuen Ort.

Für die Vorgehensweisen in diesem Artikel ist das [Microsoft SharePoint Online PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=35588) erforderlich.

## <a name="communicating-to-your-users"></a>Kommunikation mit Benutzern

Beim Verschieben von OneDrive-Websites zwischen geografischen Standorten, ist es wichtig, dass Sie Ihren Benutzer kommunizieren, was sie zu erwarten haben. Auf diese Weise werden Verunsicherungen seitens der Benutzer und Anrufe bei Ihrem Help Desk verhindert. Schreiben Sie Ihren Benutzer vor der Verschiebung eine E-Mail, und teilen Sie ihnen die folgenden Informationen mit:

- Wann die Verschiebung voraussichtlich stattfinden soll und wie lange sie dauern wird.
- An welchen geografischen Standort OneDrive verschoben wird sowie die URL zum Zugreifen auf den neuen Standort.
- Der Benutzer sollte alle Dateien schließen und während der Verschiebung keine Änderungen vornehmen.
- Dateiberechtigungen und Freigabe werden als Ergebnis der Verschiebung nicht geändert.
- Erwartungen im Hinblick auf die [Benutzererfahrung in einer Multi-Geo-Umgebung](multi-geo-user-experience.md)

Vergessen Sie nicht, Ihren Benutzer eine E-Mail zu schicken, wenn die Verschiebung erfolgreich abgeschlossen wurde, um sie darüber zu informieren, dass sie ihre Arbeit in OneDrive fortsetzen können.

## <a name="scheduling-onedrive-site-moves"></a>Planen der Verschiebung von OneDrive-Sites

Sie können die Verschiebung von OneDrive-Sites im Voraus planen (weiter unten in diesem Artikel beschrieben). Wir empfehlen, zunächst mit einer kleinen Anzahl Benutzer zu beginnen, um die Arbeitsabläufe und Kommunikationsstrategien zu überprüfen. Sobald Sie mit dem Prozess vertraut sind, können Sie die Verschiebungen wie folgt planen:

- Sie können bis zu 4.000 Verschiebungen zugleich planen.
- Wenn mit dem Verschieben begonnen wird, können Sie weitere planen, bis zu maximal jeweils 4.000 ausstehenden Verschiebungen in der Warteschlange.
- Die maximale Größe eines OneDrive, das verschoben werden kann, beträgt 1 TB (1 TB).

## <a name="moving-a-onedrive-site"></a>Verschieben einer OneDrive-Website

Um eine OneDrive ausführen zu können, muss der Mandantenadministrator zunächst den bevorzugten Datenspeicherort (Preferred Data Location, PDL) des Benutzers auf den entsprechenden geografischen Standort festlegen. Nachdem die PDL festgelegt wurde, warten Sie mindestens 24 Stunden, bis das PDL-Update über die geografischen Standorte synchronisiert wird, bevor Sie mit der OneDrive beginnen.

Stellen Sie bei Verwendung der Geo move-Cmdlets eine Verbindung mit dem #A0 am aktuellen standort OneDrive des Benutzers mithilfe der folgenden Syntax auf:

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

Beispiel: Zum Verschieben OneDrive Benutzer "Matt@contosoenergy.onmicrosoft.com" stellen Sie eine Verbindung mit dem EUR SharePoint Admin Center ein, da sich die OneDrive des Benutzers im geografischen Standort "EUR" befindet:

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Screenshot des PowerShell-Fensters mit Connect-SPOService-Cmdlet](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>Überprüfen der Umgebung

Bevor Sie mit dem Verschieben von geografischen Standorten in OneDrive beginnen, sollten Sie die Umgebung überprüfen.

Um sicherzustellen, dass alle geografischen Standorte kompatibel sind, führen Sie den folgenden Befehl aus:

`Get-SPOGeoMoveCrossCompatibilityStatus`

Angezeigt wird eine Liste Ihrer geografischen Standorte und Informationen dazu, ob Inhalte zwischen diesen verschoben werden können, indem die entsprechenden Standorte als "kompatibel" bezeichnet werden. Wenn der Befehl „Nicht kompatibel“ zurückgibt, versuchen Sie zu einem späteren Zeitpunkt erneut, den Status zu überprüfen.

Wenn eine OneDrive-Umgebung beispielsweise eine Unterwebsite umfasst, kann sie nicht verschoben werden. Sie können das Start-SPOUserAndContentMove-Cmdlet mit dem -ValidationOnly-Parameter verwenden, um zu überprüfen, ob die OneDrive-Umgebung verschoben werden kann:

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

Dieses gibt „Success“ zurück, wenn OneDrive verschoben werden kann, oder „Fail“, wenn die gesetzliche Aufbewahrungspflicht aktiviert ist oder eine Unterwebsite vorhanden ist, die die Verschiebung verhindert. Nachdem Sie überprüft haben, dass die OneDrive-Umgebung verschoben werden kann, können Sie mit der Verschiebung beginnen.

## <a name="start-a-onedrive-geo-move"></a>Starten einer Verschiebung von geografischen Standorten in OneDrive

Um mit der Verschiebung zu beginnen, führen Sie den folgenden Befehl aus:  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

Verwenden Sie die folgenden Parameter:

-   _UserPrincipalName_ – Benutzerprinzipalname des Benutzers, dessen OneDrive-Umgebung verschoben wird.

-   _DestinationDataLocation_ – Geo-Location, OneDrive verschoben werden muss. Dies sollte mit dem bevorzugten Datenspeicherort des Benutzers identisch sein.

Führen Sie zum Beispiel zum Verschieben von OneDrive von matt@contosoenergy.onmicrosoft.com von EUR nach AUS den folgenden Befehl durch:

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Screenshot des PowerShell-Fensters mit dem Start-SPOUserAndContentMove-Cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

Wenn Sie die Verschiebung eines geografischen Standorts zu einem späteren Zeitpunkt durchführen möchten, verwenden Sie einen der folgenden Parameter:

-   _PreferredMoveBeginDate_ – Die Verschiebung beginnt zu diesem Zeitpunkt. Die Zeit muss in koordinierter Weltzeit (UTC) angegeben werden.

-   _PreferredMoveEndDate_ – Die Verschiebung endet basieren auf dem Best-Effort-Prinzip zu diesem Zeitpunkt. Die Zeit muss in koordinierter Weltzeit (UTC) angegeben werden. 

## <a name="cancel-a-onedrive-geo-move"></a>Abbrechen einer Verschiebung von geografischen Standorten in OneDrive 

Sie können die geografische Bewegung der Benutzerdaten OneDrive, vorausgesetzt, die Bewegung wird nicht ausgeführt oder mithilfe des Cmdlets abgeschlossen:

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

Dabei ist _UserPrincipalName_ der Benutzerprinzipalname des Benutzers, dessen OneDrive-Verschiebung beendet werden soll.

## <a name="determining-current-status"></a>Bestimmen des aktuellen Status

Sie können den Status einer geografischen OneDrive in oder aus dem Geografischen überprüfen, mit dem Sie verbunden sind, indem Sie das cmdlet Get-SPOUserAndContentMoveState verwenden.

Die Statuswerte der Verschiebung werden in der folgenden Tabelle beschrieben.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Status</strong></th>
<th align="left"><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">Die Verschiebung wurde noch nicht begonnen.</td>
</tr>
<tr class="even">
<td align="left">InProgress (<em>n</em>/4)</td>
<td align="left">Die Verschiebung wird ausgeführt, wenn einer der folgenden Statuswerte angezeigt wird: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</td>
</tr>
<tr class="odd">
<td align="left">Success</td>
<td align="left">Die Verschiebung wurde erfolgreich ausgeführt.</td>
</tr>
<tr class="even">
<td align="left">Failed</td>
<td align="left">Beim Verschieben ist ein Fehler aufgetreten.</td>
</tr>
</tbody>
</table>

Verwenden Sie den Parameter UserPrincipalName, um den Status der Bewegung eines bestimmten Benutzers zu finden:

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

Verwenden Sie den Parameter MoveState mit einem der folgenden Werte: NotStarted, InProgress, Success, Failed, All, um den Status aller Bewegungen in oder aus dem geografischen Standort zu finden, mit dem Sie verbunden sind.

`Get-SPOUserAndContentMoveState -MoveState <value>`

Sie können auch den `-Verbose`-Parameter für weitere ausführliche Beschreibungen des Status der Verschiebung hinzufügen.

## <a name="user-experience"></a>Benutzererfahrung

OneDrive-Benutzer sollten minimale Unterbrechungen feststellen, wenn ihre OneDrive-Umgebung an einen anderen geografischen Standort verschoben wird. Neben einem kurzzeitigen Schreibschutz während des Verschiebevorgangs funktionieren vorhandene Links und Berechtigungen weiterhin wie gewohnt, sobald die Verschiebung abgeschlossen ist.

### <a name="onedrive-for-business"></a>OneDrive for Business

Während der Bewegung wird der Benutzer OneDrive schreibgeschützt festgelegt. Sobald die Bewegung abgeschlossen ist, wird der Benutzer OneDrive an den neuen geografischen Standort geleitet, wenn er zu OneDrive dem Microsoft 365-App-Startfeld oder einem Webbrowser navigiert.

### <a name="permissions-on-onedrive-content"></a>Berechtigungen für OneDrive-Inhalte

Benutzer mit Berechtigungen OneDrive Inhalten haben während des Verschiebens und nach Abschluss des Vorgangs weiterhin Zugriff auf die Inhalte.

### <a name="onedrive-sync-client"></a>OneDrive-Synchronisierungsclient 

Der OneDrive-Synchronisierungsclient überträgt die Synchronisierung automatisch an den neuen OneDrive-Standort, sobald die Verschiebung des geografischen Standorts abgeschlossen ist. Der Benutzer muss sich weder erneut anmelden noch eine andere Aktion durchführen. ( (Version 17.3.6943.0625 oder höher des Synchronisierungsclients erforderlich.)

Wenn ein Benutzer eine Datei aktualisiert, während die Verschiebung des geografischen OneDrive-Standorts ausgeführt wird, benachrichtigt der Synchronisierungsclient den Benutzer, dass Dateiuploads ausstehen, während die Verschiebung ausgeführt wird.

### <a name="sharing-links"></a>Freigabelinks 

Nach Abschluss der geografischen Standortverschiebung in OneDrive werden vorhandene Freigabelinks für verschobene Dateien automatisch zu den Dateien an dem neuen geografischen Standort weiterleiten.

### <a name="onenote-experience"></a>OneNote-Benutzererfahrung 

OneNote-Win32-Client und UWP-App werden automatisch erkannt und synchronisieren nahtlos die Notizbücher mit dem neuen geografischen OneDrive-Standort, nachdem die geografische Standortverschiebung von OneDrive abgeschlossen wurde. Der Benutzer muss sich weder erneut anmelden noch eine andere Aktion durchführen. Der einzige für den Benutzer sichtbare Indikator ist, dass beim Synchronisieren des Notizbuchs ein Fehler auftritt, während die geografische Standortverschiebung von OneDrive ausgeführt wird. Diese Erfahrung gilt für die folgenden OneNote-Clientversionen:

-   OneNote-Win32 – Version 16.0.8326.2096 (und höher)

-   OneNote UWP – Version 16.0.8431.1006 (und höher)

-   Mobile OneNote-App – Version 16.0.8431.1011 (und höher)

### <a name="teams-app"></a>Teams-App

Nach Abschluss der geografischen Standortverschiebung von OneDrive haben Benutzer Zugriff auf ihre OneDrive-Dateien in der Teams-App. Darüber hinaus können die über Teams-Chat in OneDrive vor der Verschiebung freigegebenen Dateien weiterhin verwendet werden, sobald die Verschiebung abgeschlossen ist.

### <a name="onedrive-for-business-mobile-app-ios"></a>Mobile OneDrive for Business-App (iOS) 

Nach Abschluss der geografischen Standortverschiebung von OneDrive müssen sich Benutzer abmelden und erneut in der mobilen iOS-App anmelden, damit mit dem neuen OneDrive-Standort synchronisiert wird.

### <a name="existing-followed-groups-and-sites"></a>Vorhandene gefolgte Gruppen und Websites

Gefolgte Websites und Gruppen werden unabhängig vom geografischen Standort OneDrive Benutzer angezeigt. Websites und Gruppen, die an einem anderen geografischen Standort gehostet werden, werden auf einer separaten Registerkarte geöffnet.

### <a name="delve-geo-url-updates"></a>Delve Geo-URL-Updates

Benutzer werden an die Delve, die ihrem PDL entspricht, erst gesendet, nachdem ihre OneDrive in den neuen Geografischen verschoben wurde.
