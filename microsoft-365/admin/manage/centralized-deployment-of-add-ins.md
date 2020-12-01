---
title: Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Ermitteln Sie, ob Ihr Mandant und die Benutzer die Anforderungen erfüllen, damit Sie die zentrale Bereitstellung für die Bereitstellung von Office-Add-Ins verwenden können.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519365"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert

Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Kunden, Office-Add-Ins für Benutzer und Gruppen in Ihrer Organisation bereitzustellen. Wenn Sie Administrator sind, ermitteln Sie anhand dieser Anleitung, ob Ihre Organisation und die Benutzer die Anforderungen erfüllen, damit Sie die zentralisierte Bereitstellung verwenden können.

Die zentrale Bereitstellung bietet die folgenden Vorteile:
  
- Ein globaler Administrator kann ein Add-in direkt einem Benutzer, mehreren Benutzern über eine Gruppe oder allen in der Organisation zuweisen.
    
- Wenn die entsprechende Office-Anwendung gestartet wird, lädt das Add-in automatisch herunter. Wenn das Add-in Add-in-Befehle unterstützt, wird das Add-in automatisch im Menüband in der Office-Anwendung angezeigt.
    
- Add-Ins werden nicht mehr für Benutzer angezeigt, wenn der Administrator das Add-in deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-in zugewiesen ist.

Die zentralisierte Bereitstellung unterstützt drei Windows-, Mac-und Online Office-Apps für Desktopplattformen. Die zentralisierte Bereitstellung unterstützt auch IOS und Android (nur Outlook Mobile-Add-Ins).

Es kann bis zu 24 Stunden dauern, bis ein Add-in für alle Benutzer für den Client angezeigt wird.
  
## <a name="requirements"></a>Anforderungen

Die zentrale Bereitstellung von Add-ins erfordert, dass die Benutzer Microsoft 365 Enterprise-SKUs verwenden: E3/E5/F3 oder Geschäfts-SKUs: Business Basic, Business Standard, Business Premium (und mit ihrer Organisations-ID bei Office angemeldet sind) und über Exchange Online und Active Exchange Online-Postfächer verfügen. Ihr Abonnement Verzeichnis muss sich entweder in oder im Verbund mit Azure Active Directory befinden.
Sie können die spezifischen Anforderungen für Office und Exchange unten anzeigen oder die [Kompatibilitätsprüfung für die zentrale Bereitstellung](#centralized-deployment-compatibility-checker)verwenden.

Folgendes wird von der zentralen Bereitstellung nicht unterstützt:
  
- Add-Ins, die Word, Excel oder PowerPoint in Office 2013 zum Ziel haben 
- Ein lokaler Verzeichnisdienst
- Add-in-Bereitstellung in einem Exchange-basierten Postfach
- Add-In-Bereitstellung in SharePoint  
- Microsoft Teams-apps
- Bereitstellung von Component Object Model (com) oder Visual Studio Tools für Office (VSTO)-Add-Ins.
- Bereitstellungen von Microsoft 365, die keine Exchange Online wie SKUs enthalten: Microsoft 365 apps for Business und Microsoft 365 apps for Enterprise.

### <a name="office-requirements"></a>Office-Anforderungen

- Für Word-, Excel-und PowerPoint-Add-Ins müssen die Benutzer eine der folgenden Optionen verwenden:
  - Auf einem Windows-Gerät Version 1704 oder höher von Microsoft 365 Enterprise-SKUs: E3/E5/F3 oder Business-SKUs: Business Basic, Business Standard, Business Premium.
  - Auf einem Mac, Version 15,34 oder höher.

- Für Outlook müssen die Benutzer eine der folgenden Optionen verwenden: 
  - Version 1701 oder höher von Microsoft 365 Enterprise-SKUs: E3/E5/F3 oder Business-SKUs: Business Basic, Business Standard, Business Premium.
  - Version 1808 oder höher von Office Professional Plus 2019 oder Office Standard 2019.
  - Version 16.0.4494.1000 oder höher von Office Professional Plus 2016 (MSI) oder Office Standard 2016 (MSI)\*
  - Version 15.0.4937.1000 oder höher von Office Professional Plus 2013 (MSI) oder Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 oder höher von Office 2016 für Mac 
- Version 2.75.0 oder höher von Outlook Mobile für IOS 
- Version 2.2.145 oder höher von Outlook Mobile für Android 
    
    * MSI-Versionen von Outlook zeigen Administrator installierte Add-Ins im entsprechenden Outlook-Menüband, nicht im Abschnitt "meine Add-Ins".

### <a name="exchange-online-requirements"></a>Exchange Online Anforderungen

Microsoft Exchange speichert die Add-in-Manifeste im Mandanten Ihrer Organisation. Der Administrator, der Add-ins bereitstellt, und die Benutzer, die diese Add-ins empfangen, müssen sich in einer Version von Exchange Online befinden, die die OAuth-Authentifizierung unterstützt.
  
Informieren Sie sich beim Exchange-Administrator Ihrer Organisation, um herauszufinden, welche Konfiguration verwendet wird. Die OAuth-Verbindung pro Benutzer kann überprüft werden, indem Sie das PowerShell-Cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) verwenden. 


### <a name="centralized-deployment-compatibility-checker"></a>Zentrale Bereitstellungs Kompatibilitätsprüfung

Mithilfe der zentralen Bereitstellungs Kompatibilitätsprüfung können Sie überprüfen, ob die Benutzer Ihres Mandanten für die Verwendung der zentralisierten Bereitstellung für Word, Excel und PowerPoint eingerichtet sind. Die Kompatibilitätsprüfung ist für die Unterstützung von Outlook nicht erforderlich. Laden Sie die Kompatibilitätsprüfung [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) herunter.
  
#### <a name="run-the-compatibility-checker"></a>Ausführen der Kompatibilitätsprüfung
  
1. Starten Sie ein Fenster mit erhöhten PowerShell.exe.
    
2. Führen Sie den folgenden Befehl aus:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Führen Sie den Befehl **Invoke-CompatabilityCheck** aus:

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Mit diesem Befehl werden Sie zur Eingabe von  *_TenantDomain_* aufgefordert (beispielsweise *TailspinToysIncorporated. onmicrosoft. </span> com*) und  *_TenantAdmin_* -Anmeldeinformationen (verwenden Sie Ihre globalen Administratoranmeldeinformationen), und fordert dann die Zustimmung an.
    
   > [!NOTE]
   > Je nach Anzahl der Benutzer Ihres Mandanten kann die Prüfung nach Minuten oder Stunden abgeschlossen sein. 
  
Sobald die Ausführung des Tools abgeschlossen ist, wird eine Ausgabedatei im CSV-Format (durch Trennzeichen getrenntes Format) erzeugt. Die Datei wird standardmäßig in " **system32** " gespeichert. Die Ausgabedatei enthält die folgenden Informationen:
  
- Benutzername
    
- Benutzer-ID (E-Mail-Adresse des Benutzers)
    
- Zentrale Bereitstellung bereit - Wenn die übrigen Punkte zutreffen
    
- Office-Plan – der Plan von Office, für den Sie lizenziert sind
    
- Office aktiviert - Wenn Office aktiviert ist
    
- Unterstütztes Postfach - Wenn das Postfach für OAuth aktiviert ist

> [!NOTE]
> Die mehrstufige Authentifizierung wird bei Verwendung des PowerShell-Moduls für die zentrale Bereitstellung nicht unterstützt.
  
## <a name="user-and-group-assignments"></a>Benutzer- und Gruppenzuordnungen

Das zentralisierte Bereitstellungsfeature unterstützt derzeit die Mehrzahl der von Azure Active Directory unterstützten Gruppen, einschließlich Microsoft 365-Gruppen, Verteilerlisten und Sicherheitsgruppen.
  
> [!NOTE]
> Nicht für E-Mail aktivierte Sicherheitsgruppen werden derzeit nicht unterstützt. 
  
Die zentralisierte Bereitstellung unterstützt Zuweisungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten. Die zentrale Bereitstellung unterstützt Benutzer in Gruppen der oberen Ebene oder Gruppen ohne übergeordnete Gruppen, jedoch keine Benutzer in geschachtelten Gruppen oder Gruppen, die über übergeordnete Gruppen verfügen.
   
Schauen Sie sich das folgende Beispiel an, in dem Sandra, Sofia und die Gruppe "Vertriebsabteilung" einem Add-In zugeordnet werden. Da es sich bei "Vertriebsabteilung Westküste" um eine geschachtelte Gruppe handelt, werden Bert und Fred keinem Add-In zugeordnet.
  
![Diagramm der Vertriebsabteilung](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Herausfinden, ob eine Gruppe geschachelte Gruppen enthält

Die einfachste Methode, um herauszufinden, ob eine Gruppe geschachtelte Gruppen enthält, besteht darin, in Outlook die Gruppenvisitenkarte anzuzeigen. Wenn Sie den Gruppennamen innerhalb des Felds **an** einer e-Mail eingeben und dann den Gruppennamen beim Auflösen auswählen, wird Ihnen angezeigt, ob Sie Benutzer oder geschachtelte Gruppen enthält. Im nachfolgenden Beispiel werden auf der Registerkarte **Mitglieder** der Outlook-Visitenkarte der Testgruppe keine Benutzer und nur zwei Untergruppen angezeigt. 
  
![Registerkarte "Mitglieder" der Outlook-Visitenkarte](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Sie können die umgekehrte Abfrage durchführen, indem Sie die Gruppe auflösen, um zu sehen, ob sie Mitglied einer anderen Gruppe ist. Im Beispiel unten können Sie auf der Registerkarte **Mitgliedschaft** der Outlook-Visitenkarte sehen, dass Untergruppe 1 ein Mitglied der Testgruppe ist. 
  
![Registerkarte "Mitgliedschaft" der Outlook-Visitenkarte](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Alternativ können Sie die Azure Active Directory Graph-API verwenden, um Abfragen auszuführen, um die Liste der Gruppen innerhalb einer Gruppe zu finden. Weitere Informationen finden Sie unter [Vorgänge mit Gruppen | Graph-API-Referenz](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Kontaktaufnahme mit dem Microsoft-Support

Wenn Sie oder Ihre Benutzer Probleme beim Laden des Add-ins bei der Verwendung von Office-Apps für das Internet (Word, Excel, etc.) haben, die zentral bereitgestellt wurden, müssen Sie sich möglicherweise an den Microsoft-Support wenden ([Weitere Informationen](../contact-support-for-business-products.md)). Geben Sie die folgenden Informationen zu Ihrer Microsoft 365-Umgebung im Support Ticket an.
  
|**Plattform**|**Debuginformationen**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler-Protokolle  <br/>  Mandanten-ID ( [So wird's gemacht](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationId. Zeigen Sie die Quelle einer der Office-Seiten an, und suchen Sie nach dem Wert der Korrelations-ID, und senden Sie ihn an Support:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Rich Clients (Windows, Mac)  <br/> | Charles/Fiddler-Protokolle  <br/>  Erstellen von Nummern der Client-app (vorzugsweise als Screenshot aus **Datei/Konto**)  <br/> |
   
