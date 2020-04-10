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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Ermitteln Sie, ob Ihre Office 365 Mandanten und Benutzer die Anforderungen erfüllen, damit Sie die zentrale Bereitstellung für die Bereitstellung von Office-Add-Ins verwenden können.
ms.openlocfilehash: a3005d02522d0a2b22b1ca337d8f49ce7fa20fb3
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209748"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert

[] Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Methode für die meisten Kunden, um Office-Add-Ins für Benutzer und Gruppen in der Office 365-Organisation bereitzustellen. Wenn Sie Administrator sind, können Sie anhand dieser Anleitung ermitteln, ob Ihre Mandanten und Benutzer die Anforderungen erfüllen, damit Sie die zentralisierte Bereitstellung verwenden können.
Die zentralisierte Bereitstellung unterstützt Windows-, Mac-, Ios-, Android-und Online-Office-Apps.
Es kann bis zu 24 Stunden dauern, bis ein Add-in für alle Benutzer für den Client angezeigt wird.
  
## <a name="requirements"></a>Anforderungen

Die zentrale Bereitstellung von Add-ins erfordert, dass die Benutzer Office 365 ProPlus verwenden (und mit ihrer Organisations-ID bei Office angemeldet sind) und über Exchange Online und aktive Exchange Online Postfächer verfügen. Ihr Abonnement 'd-Verzeichnis muss entweder in oder Verbund mit Azure Active Directory sein.
Sie können die spezifischen Anforderungen für Office und Exchange unten anzeigen oder die [Office 365 zentrale Bereitstellungs Kompatibilitätsprüfung](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)verwenden.

Folgendes wird von der zentralen Bereitstellung nicht unterstützt:
  
- Add-Ins, die Word, Excel oder PowerPoint in Office 2013 zum Ziel haben
    
- Ein lokaler Verzeichnisdienst
    
- Add-In-Bereitstellung in SharePoint  

- Microsoft Teams-apps
   
- Bereitstellung der Add-Ins Component Object Model (COM) oder Visual Studio Tools für Office (VSTO)
    
- Bereitstellungen von Office 365 ohne Exchange, z. B. Office 365 Business

### <a name="office-requirements"></a>Office-Anforderungen

- Für Word-, Excel-und PowerPoint-Add-Ins müssen die Benutzer eine der folgenden Optionen verwenden:
  - Auf einem Windows-Gerät Version 1704 oder höher von Office 365 ProPlus.
  - Auf einem Mac, Version 15,34 oder höher.

- Für Outlook müssen die Benutzer eine der folgenden Optionen verwenden: 
  - Version 1701 oder höher von Office 365 ProPlus.
  - Version 1808 oder höher von Office Professional Plus 2019 oder Office Standard 2019.
  - Version 16.0.4494.1000 oder höher von Office Professional Plus 2016 (MSI) oder Office Standard 2016 (MSI)\*
  - Version 15.0.4937.1000 oder höher von Office Professional Plus 2013 (MSI) oder Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 oder höher von Office 2016 für Mac 
- Version 2.75.0 oder höher von Outlook Mobile für IOS 
- Version 2.2.145 oder höher von Outlook Mobile für Android 
    
    * MSI-Versionen von Outlook zeigen Administrator installierte Add-Ins im entsprechenden Outlook-Menüband, nicht im Abschnitt "meine Add-Ins".
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a>Herausfinden, ob Office 365 ProPlus installiert ist

Um Office 365 ProPlus verwenden zu können, muss ein Benutzer über ein Office 365 Konto verfügen, dem eine Lizenz zugewiesen sein muss. Weitere Informationen finden Sie unter [Übersicht über Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).

Die einfachste Möglichkeit zu erkennen, ob ein Benutzer Office 365 ProPlus installiert hat und ihn zuletzt verwendet hat, ist die Verwendung des Berichts über Microsoft Office Aktivierungen, der im Microsoft 365 Admin Center verfügbar ist. Im Bericht finden Sie eine Liste aller Benutzer, die Office 365 ProPlus innerhalb der letzten 7 Tage, der letzten 30 Tage, 90 Tage oder 180 Tage aktiviert haben. Im Zusammenhang mit der zentralen Bereitstellung sind die Desktopaktivierungen für Windows oder Mac die wichtigen Spalten im Bericht. Sie können den Bericht nach Excel exportieren. Weitere Informationen zu dem Bericht finden Sie unter [Office 365-Berichte im Admin Center - Microsoft Office-Aktivierungen](../activity-reports/microsoft-office-activations.md).
  
Wenn Sie den Aktivierungsbericht nicht verwenden möchten, können Sie einen Benutzer bitten, eine Office-Anwendung wie Word auf seinem Computer zu öffnen, und dann **Datei** \> **Konto**auswählen. Unter **Produktinformation** sollte **Abonnementprodukt** und **Microsoft Office 365 ProPlus** angezeigt, wie in der folgenden Abbildung gezeigt.

![Produktinformationen in einer Office-Anwendung](../../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
Hilfe zu Office 365 ProPlus finden Sie unter [Tipps zum Behandeln von Problemen mit Office 365](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-online-requirements"></a>Exchange Online Anforderungen

Microsoft Exchange speichert die Add-in-Manifeste im Mandanten Ihrer Organisation. Der Administrator, der Add-ins bereitstellt, und die Benutzer, die diese Add-ins empfangen, müssen sich in einer Version von Exchange Online befinden, die die OAuth-Authentifizierung unterstützt.
  
Informieren Sie sich beim Exchange-Administrator Ihrer Organisation, um herauszufinden, welche Konfiguration verwendet wird. Die OAuth-Verbindung pro Benutzer kann überprüft werden, indem Sie das PowerShell-Cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) verwenden. 


### <a name="office-365-centralized-deployment-compatibility-checker"></a>Kompatibilitätsprüfung für zentrale Bereitstellung in Office 365

Mithilfe der Kompatibilitätsprüfung für die zentrale Bereitstellung in Office 365 können Sie überprüfen, ob die Benutzer Ihres Mandanten für die Verwendung der zentralen Bereitstellung für Word, Excel und PowerPoint eingerichtet sind. Die Kompatibilitätsprüfung ist für die Unterstützung von Outlook nicht erforderlich. Laden Sie die Kompatibilitätsprüfung [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) herunter.
  
#### <a name="run-the-compatibility-checker"></a>Ausführen der Kompatibilitätsprüfung
  
1. Starten Sie ein erweitertes PowerShell. exe-Fenster.
    
2. Führen Sie den folgenden Befehl aus:

```powershell
Import-Module O365CompatibilityChecker
```
    
3. Führen Sie den Befehl **Invoke-CompatabilityCheck** aus:

```powershell
Invoke-CompatibilityCheck
```
   Sie werden aufgefordert, *_TenantDomain_* einzugeben (beispielsweise *TailspinToysIncorporated. onmicrosoft.</span> com*) und *_TenantAdmin_* -Anmeldeinformationen (verwenden Sie Ihre globalen Administratoranmeldeinformationen), und fordert dann die Zustimmung an.
    
> [!NOTE]
> Je nach Anzahl der Benutzer Ihres Mandanten kann die Prüfung nach Minuten oder Stunden abgeschlossen sein. 
  
Sobald die Ausführung des Tools abgeschlossen ist, wird eine Ausgabedatei im CSV-Format (durch Trennzeichen getrenntes Format) erzeugt. Die Datei wird standardmäßig in " **system32** " gespeichert. Die Ausgabedatei enthält die folgenden Informationen:
  
- Benutzername
    
- Benutzer-ID (E-Mail-Adresse des Benutzers)
    
- Zentrale Bereitstellung bereit - Wenn die übrigen Punkte zutreffen
    
- Office-Plan – der Plan von Office, für den Sie lizenziert sind
    
- Office aktiviert - Wenn Office aktiviert ist
    
- Unterstütztes Postfach - Wenn das Postfach für OAuth aktiviert ist


  
## <a name="user-and-group-assignments"></a>Benutzer- und Gruppenzuordnungen

Das Feature für die zentrale Bereitstellung unterstützt derzeit die Mehrzahl der Gruppen, die von Azure Active Directory unterstützt werden, einschließlich Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen.
  
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

Wenn Sie oder Ihre Benutzer Probleme beim Laden des Add-ins bei der Verwendung von Office-Apps für das Internet (Word, Excel, etc.) haben, die zentral bereitgestellt wurden, müssen Sie sich möglicherweise an den Microsoft-Support wenden ([Weitere Informationen](../contact-support-for-business-products.md)). Stellen Sie im Supportticket die folgenden Informationen zu Ihrer Office 365-Umgebung bereit.
  
|**Plattform**|**Debuginformationen**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler-Protokolle  <br/>  Mandanten-ID ( [So wird's gemacht](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))  <br/>  CorrelationId. Zeigen Sie die Quelle einer der Office-Seiten an, und suchen Sie nach dem Wert der Korrelations-ID, und senden Sie ihn an Support:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Rich Clients (Windows, Mac)  <br/> | Charles/Fiddler-Protokolle  <br/>  Erstellen von Nummern der Client-app (vorzugsweise als Screenshot aus **Datei/Konto**)  <br/> |
   

