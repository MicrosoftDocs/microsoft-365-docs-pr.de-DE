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
description: Ermitteln Sie, ob Der Mandant und die Benutzer die Anforderungen erfüllen, sodass Sie die zentrale Bereitstellung zum Bereitstellen von Office-Add-Ins verwenden können.
ms.openlocfilehash: c9f2879e989085042758cc1c5385bea45427e7ff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915458"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert

Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Kunden, Office-Add-Ins für Benutzer und Gruppen in Ihrer Organisation zu bereitstellen. Wenn Sie Administrator sind, verwenden Sie diese Anleitung, um festzustellen, ob Ihre Organisation und Ihre Benutzer die Anforderungen erfüllen, sodass Sie die zentrale Bereitstellung verwenden können.

Die zentrale Bereitstellung bietet die folgenden Vorteile:
  
- Ein globaler Administrator kann einem Benutzer, mehreren Benutzern über eine Gruppe oder allen Benutzern in der Organisation ein Add-In direkt zuweisen.
    
- Wenn die relevante Office-Anwendung gestartet wird, wird das Add-In automatisch heruntergeladen. Wenn das Add-In Add-In-Befehle unterstützt, wird das Add-In automatisch im Menüband in der Office-Anwendung angezeigt.
    
- Add-Ins werden für Benutzer nicht mehr angezeigt, wenn der Administrator das Add-In deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-In zugewiesen ist.

Die zentrale Bereitstellung unterstützt drei Desktopplattformen windows-, mac- und online-Office-Apps. Die zentrale Bereitstellung unterstützt auch iOS und Android (Nur Outlook Mobile-Add-Ins).

Es kann bis zu 24 Stunden dauern, bis ein Add-In für den Client für alle Benutzer verfügbar ist.
  
## <a name="requirements"></a>Anforderungen

Die zentrale Bereitstellung von Add-Ins erfordert, dass die Benutzer Microsoft 365 Enterprise SKUs verwenden: E3/E5/F3 oder Business SKUs: Business Basic, Business Standard, Business Premium (und mit ihrer Organisations-ID bei Office angemeldet sind) und über Exchange Online- und aktive Exchange Online-Postfächer verfügen. Ihr Abonnementverzeichnis muss sich entweder in oder in einem Verbund mit Azure Active Directory befinden.
Sie können unten bestimmte Anforderungen für Office und Exchange anzeigen oder die Kompatibilitätsprüfung für die zentrale [Bereitstellung verwenden.](#centralized-deployment-compatibility-checker)

Folgendes wird von der zentralen Bereitstellung nicht unterstützt:
  
- Add-Ins, die Word, Excel oder PowerPoint in Office 2013 zum Ziel haben 
- Ein lokaler Verzeichnisdienst
- Add-In-Bereitstellung in einem Exchange On-Prem-Postfach
- Add-In-Bereitstellung in SharePoint  
- Teams-Apps
- Bereitstellung von Component Object Model (COM) oder Visual Studio Tools for Office (VSTO)-Add-Ins.
- Bereitstellungen von Microsoft 365 ohne Exchange Online, z. B. SKUs: Microsoft 365 Apps for Business und Microsoft 365 Apps for Enterprise.

### <a name="office-requirements"></a>Office-Anforderungen

- Für Word-, Excel- und PowerPoint-Add-Ins müssen Ihre Benutzer eine der folgenden Optionen verwenden:
  - Auf einem Windows-Gerät, Version 1704 oder höher von Microsoft 365 Enterprise SKUs: E3/E5/F3 oder Business SKUs: Business Basic, Business Standard, Business Premium.
  - Auf einem Mac, Version 15.34 oder höher.

- Für Outlook müssen Ihre Benutzer eine der folgenden Optionen verwenden: 
  - Version 1701 oder höher von Microsoft 365 Enterprise SKUs: E3/E5/F3 oder Business SKUs: Business Basic, Business Standard, Business Premium.
  - Version 1808 oder höher von Office Professional Plus 2019 oder Office Standard 2019.
  - Version 16.0.4494.1000 oder höher von Office Professional Plus 2016 (MSI) oder Office Standard 2016 (MSI)\*
  - Version 15.0.4937.1000 oder höher von Office Professional Plus 2013 (MSI) oder Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 oder höher von Office 2016 für Mac 
- Version 2.75.0 oder höher von Outlook mobile für iOS 
- Version 2.2.145 oder höher von Outlook mobile für Android 
    
    *#A0 von Outlook zeigen admin-installierte #A1 im entsprechenden #A1 an, nicht im Abschnitt "Meine Add-Ins".

### <a name="exchange-online-requirements"></a>Exchange Online-Anforderungen

Microsoft Exchange speichert die Add-In-Manifeste im Mandanten Ihrer Organisation. Der Administrator, der Add-Ins bereitgestellt, und die Benutzer, die diese Add-Ins empfangen, müssen sich in einer Version von Exchange Online mit Unterstützung der OAuth-Authentifizierung begnnen.
  
Informieren Sie sich beim Exchange-Administrator Ihrer Organisation, um herauszufinden, welche Konfiguration verwendet wird. Die OAuth-Verbindung pro Benutzer kann überprüft werden, indem Sie das PowerShell-Cmdlet [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) verwenden. 


### <a name="centralized-deployment-compatibility-checker"></a>Kompatibilitätsprüfung für die zentrale Bereitstellung

Mithilfe der Kompatibilitätsprüfung für die zentrale Bereitstellung können Sie überprüfen, ob die Benutzer in Ihrem Mandanten für die Verwendung der zentralen Bereitstellung für Word, Excel und PowerPoint eingerichtet sind. Die Kompatibilitätsprüfung ist für die Unterstützung von Outlook nicht erforderlich. Laden Sie die Kompatibilitätsprüfung [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) herunter.
  
#### <a name="run-the-compatibility-checker"></a>Ausführen der Kompatibilitätsprüfung
  
1. Starten Sie ein Fenster mit PowerShell.exe Fenster.
    
2. Führen Sie den folgenden Befehl aus:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Führen Sie den **Befehl Invoke-CompatabilityCheck aus:**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Dieser Befehl fordert Sie zur Eingabe von  *_TenantDomain_* auf (z. B. *TailspinToysIncorporated.onmicrosoft). </span> com*) und  *_TenantAdmin-Anmeldeinformationen_* (verwenden Sie Ihre globalen Administratoranmeldeinformationen), und fordert dann die Zustimmung an.
    
   > [!NOTE]
   > Je nach Anzahl der Benutzer Ihres Mandanten kann die Prüfung nach Minuten oder Stunden abgeschlossen sein. 
  
Sobald die Ausführung des Tools abgeschlossen ist, wird eine Ausgabedatei im CSV-Format (durch Trennzeichen getrenntes Format) erzeugt. Die Datei wird standardmäßig in **C:\windows\system32** gespeichert. Die Ausgabedatei enthält die folgenden Informationen:
  
- Benutzername
    
- Benutzer-ID (E-Mail-Adresse des Benutzers)
    
- Zentrale Bereitstellung bereit - Wenn die übrigen Punkte zutreffen
    
- Office-Plan – Der Plan von Office, für den sie lizenziert sind
    
- Office aktiviert - Wenn Office aktiviert ist
    
- Unterstütztes Postfach - Wenn das Postfach für OAuth aktiviert ist

> [!NOTE]
> Die mehrstufige Authentifizierung wird bei Verwendung des PowerShell-Moduls für die zentrale Bereitstellung nicht unterstützt.
  
## <a name="user-and-group-assignments"></a>Benutzer- und Gruppenzuordnungen

Das Feature für die zentrale Bereitstellung unterstützt derzeit die Meisten von Azure Active Directory unterstützten Gruppen, einschließlich Microsoft 365-Gruppen, Verteilerlisten und Sicherheitsgruppen.
  
> [!NOTE]
> Nicht für E-Mail aktivierte Sicherheitsgruppen werden derzeit nicht unterstützt. 
  
Die zentrale Bereitstellung unterstützt Zuordnungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten. Die zentrale Bereitstellung unterstützt Benutzer in Gruppen der oberen Ebene oder Gruppen ohne übergeordnete Gruppen, jedoch keine Benutzer in geschachtelten Gruppen oder Gruppen, die über übergeordnete Gruppen verfügen.
   
Schauen Sie sich das folgende Beispiel an, in dem Sandra, Sofia und die Gruppe "Vertriebsabteilung" einem Add-In zugeordnet werden. Da es sich bei "Vertriebsabteilung Westküste" um eine geschachtelte Gruppe handelt, werden Bert und Fred keinem Add-In zugeordnet.
  
![Diagramm der Vertriebsabteilung](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Herausfinden, ob eine Gruppe geschachelte Gruppen enthält

Die einfachste Methode, um herauszufinden, ob eine Gruppe geschachtelte Gruppen enthält, besteht darin, in Outlook die Gruppenvisitenkarte anzuzeigen. Wenn Sie den Gruppennamen im Feld **An** einer E-Mail eingeben und dann den Gruppennamen auswählen, wenn er aufgelöst wird, wird angezeigt, ob er Benutzer oder geschachtelte Gruppen enthält. Im nachfolgenden Beispiel werden auf der Registerkarte **Mitglieder** der Outlook-Visitenkarte der Testgruppe keine Benutzer und nur zwei Untergruppen angezeigt. 
  
![Registerkarte Mitglieder der Outlook-Visitenkarte](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Sie können die umgekehrte Abfrage durchführen, indem Sie die Gruppe auflösen, um zu sehen, ob sie Mitglied einer anderen Gruppe ist. Im Beispiel unten können Sie auf der Registerkarte **Mitgliedschaft** der Outlook-Visitenkarte sehen, dass Untergruppe 1 ein Mitglied der Testgruppe ist. 
  
![Registerkarte "Mitgliedschaft" der Outlook-Visitenkarte](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Alternativ können Sie die Azure Active Directory Graph-API verwenden, um Abfragen auszuführen, um die Liste der Gruppen innerhalb einer Gruppe zu finden. Weitere Informationen finden Sie unter [Vorgänge mit Gruppen | Graph-API-Referenz](/previous-versions/azure/ad/graph/api/groups-operations).
  
### <a name="contacting-microsoft-for-support"></a>Kontaktaufnahme mit dem Microsoft-Support

Wenn bei der Verwendung von Office-Apps für das Web (Word, Excel usw.), die zentral bereitgestellt wurden, Probleme beim Laden des Add-Ins auftreten, müssen Sie sich möglicherweise an den Microsoft-Support wenden ( Erfahren[Sie,](../contact-support-for-business-products.md)wie ). Geben Sie im Supportticket die folgenden Informationen zu Ihrer Microsoft 365-Umgebung an.
  
|**Plattform**|**Debuginformationen**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler-Protokolle  <br/>  Mandanten-ID ( [So wird's gemacht](/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationID. Zeigen Sie die Quelle einer der Office-Seiten an, suchen Sie nach dem Korrelations-ID-Wert, und senden Sie ihn an die Unterstützung:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Rich Clients (Windows, Mac)  <br/> | Charles/Fiddler-Protokolle  <br/>  Erstellen von Nummern der Client-App (vorzugsweise als Screenshot aus **Datei/Konto**)  <br/> |
