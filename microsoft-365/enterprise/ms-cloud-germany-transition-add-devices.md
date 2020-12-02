---
title: Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: weitere Geräteinformationen zu Diensten beim Wechsel von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) zu Office 365 Diensten im neuen rechenzentrumsbereich.'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551953"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Woran kann ich erkennen, ob meine Organisation betroffen ist?**

Administratoren sollten überprüfen `https://portal.microsoftazure.de` , ob Sie über registrierte Geräte verfügen. Wenn Ihre Organisation über registrierte Geräte verfügt, sind Sie davon betroffen.

**Was sind die Auswirkungen auf meine Benutzer?**

Benutzer von einem registrierten Gerät können sich nicht mehr anmelden, nachdem die Migration in die Azure AD Migrationsphase [abgeschlossen](ms-cloud-germany-transition.md#how-is-the-migration-organized) wurde.  

Stellen Sie sicher, dass alle Ihre Geräte beim weltweiten Endpunkt registriert sind, bevor Ihre Organisation von Microsoft Cloud Deutschland getrennt ist.
  
**Wann werden meine Benutzer ihre Geräte erneut registrieren?**

Entscheidend für Ihren Erfolg ist, dass Sie Ihre Geräte nur in der [separaten Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) -Migrationsphase aufheben und neu registrieren.

**Wie stelle ich den Gerätestatus nach der Migration wieder her?**

Für Hybrid Azure AD-geteilte und unternehmenseigene Windows-Geräte, die bei Azure AD registriert sind, können Administratoren die Migration dieser Geräte über Remote ausgelöste Workflows verwalten, mit denen die Registrierung der alten Gerätezustände aufgehoben wird.
  
Für alle anderen Geräte, einschließlich persönlicher Windows-Geräte, die in Azure AD registriert sind, muss der Endbenutzer diese Schritte manuell ausführen. Für Azure AD-verbundene Geräte müssen Benutzer über ein lokales Administratorkonto verfügen, um die Registrierung aufzuheben und die Geräte dann erneut zu registrieren.

Microsoft veröffentlicht Anweisungen zur erfolgreichen Wiederherstellung des Gerätestatus. 
 
**Woher weiß ich, dass alle meine Geräte in der öffentlichen Cloud registriert sind?**

Um zu überprüfen, ob Ihre Geräte in der öffentlichen Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD Portal in ein Excel-Arbeitsblatt exportieren und herunterladen. Filtern Sie dann die Geräte, die registriert sind (mithilfe der Spalte " _registered_ Zeit") nach der [separaten Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) -Migrationsphase.

Die Geräteregistrierung wird nach der Migration des Mandanten deaktiviert und kann nicht aktiviert oder deaktiviert werden. Wenn InTune nicht verwendet wird, melden Sie sich bei Ihrem Abonnement an, und führen Sie diesen Befehl aus, um die Option erneut zu aktivieren:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows-Hybrid Azure AD beitreten

### <a name="windows-down-level"></a>Windows-Down-Level

_Windows-untergeordnete Geräte_ sind Windows-Geräte, die derzeit frühere Versionen von Windows (beispielsweise Windows 8.1 oder Windows 7) ausführen oder die Windows Server-Versionen vor 2019 und 2016 ausführen. Wenn diese Geräte zuvor registriert wurden, müssen Sie diese Geräte aufheben und erneut registrieren. 

Verwenden Sie den folgenden Befehl auf dem Gerät, um festzustellen, ob ein Windows-Gerät auf der untersten Ebene zuvor zu Azure AD hinzugefügt wurde:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Wenn das Gerät zuvor mit Azure AD verbunden wurde und das Gerät über eine Netzwerkverbindung mit globalen Azure AD Endpunkten verfügt, wird die folgende Ausgabe angezeigt:

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

Die betroffenen Geräte haben den "Gerätestatus" mit dem Wert "unbekannt". Wenn die Ausgabe "Device not Joined" ist oder deren Wert "Gerätestatus" "OK" lautet, ignorieren Sie die folgende Anleitung.

Nur für Geräte, die anzeigen, dass das Gerät verbunden ist (aufgrund von Geräte-und Fingerabdruck usw.) und dessen Wert "Gerätestatus" "unbekannt" ist, sollten Administratoren den folgenden Befehl im Kontext eines Domänenbenutzers ausführen, der sich auf einem solchen untergeordneten Gerät anmeldet:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

Der obige Befehl muss nur einmal pro Domänenbenutzer ausgeführt werden, der sich auf dem Windows-Down-Level-Gerät anmeldet. Dieser Befehl sollte im Kontext des Domänenbenutzers ausgeführt werden, der sich anmeldet. 

Es muss ausreichend darauf geachtet werden, diesen Befehl nicht auszuführen, wenn der Benutzer sich anschließend anmeldet. Wenn der obige Befehl ausgeführt wird, wird der verbundene Status des lokalen Hybriden Azure AD-verbundenen Computers für den Benutzer, der sich angemeldet hat, gelöscht. Wenn der Computer noch als Hybrid Azure AD konfiguriert ist – im Mandanten verbunden, versucht er, sich anzumelden, wenn sich der Benutzer erneut anmeldet.

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Trennungs

Führen Sie den folgenden Befehl auf dem Gerät aus, um festzustellen, ob das Windows 10-Gerät zuvor zu Azure AD hinzugefügt wurde:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Wenn das Gerät Hybrid Azure AD – Joined ist, würde der Administrator die folgende Ausgabe sehen:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Wenn die Ausgabe "AzureAdJoined: No" lautet, ignorieren Sie die folgende Anleitung.

Führen Sie den folgenden Befehl als Administrator aus, um den verbundenen Status des Geräts zu entfernen, nur für Geräte, die anzeigen, dass das Gerät mit Azure AD verbunden ist.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Der obige Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden.

#### <a name="hybrid-ad-joinre-registration"></a>Hybrid-AD-Join\Re-Registration

Das Gerät wird automatisch mit Azure AD ohne Benutzer-oder Administratoreingriff verbunden, solange das Gerät über eine Netzwerkverbindung mit globalen Azure AD Endpunkten verfügt. 


## <a name="windows-azure-ad-join"></a>Windows Azure AD beitreten

### <a name="unjoin"></a>Trennungs

Um zu ermitteln, ob das Windows 10-Gerät zuvor mit Azure AD verbunden wurde, kann der Benutzer oder Administrator den folgenden Befehl auf dem Gerät ausführen:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Wenn das Gerät mit Azure AD verbunden ist, wird dem Benutzer oder Administrator die folgende Ausgabe angezeigt:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Wenn die Ausgabe "AzureAdJoined: No" lautet, ignorieren Sie die folgende Anleitung.

Benutzer: Wenn das Gerät Azure AD verbunden ist, kann ein Benutzer die Verknüpfung des Geräts von den Einstellungen trennen. Stellen Sie sicher, dass auf dem Gerät ein lokales Administratorkonto vorhanden ist, bevor Sie von Azure AD auf das Gerät aufschließen. Das lokale Administratorkonto muss sich wieder am Gerät anmelden.

Admin: Wenn der Administrator der Organisation die Verknüpfung der Benutzer Geräte aufheben möchte, die Azure AD – beigetreten sind, können Sie den folgenden Befehl auf jedem der Geräte mithilfe eines Mechanismus wie der Gruppenrichtlinie ausführen. Der Administrator muss überprüfen, ob ein lokales Administratorkonto auf dem Gerät vorhanden ist, bevor die Verbindung mit dem Gerät von Azure AD entfernt wird. Das lokale Administratorkonto wird benötigt, um sich wieder am Gerät anzumelden.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Der obige Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden. 

### <a name="azure-ad-joinre-registration"></a>Azure AD beitreten/erneute Registrierung

Der Benutzer kann dem Gerät Azure AD von Windows-Einstellungen hinzufügen: **Einstellungen > Konten > Access work oder School > Connect**.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD registriert (im Unternehmen)

Führen Sie den folgenden Befehl auf dem Gerät aus, um festzustellen, ob das Gerät Windows 10 Azure AD – registriert ist:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Wenn das Gerät Azure AD registriert ist, wird die folgende Ausgabe angezeigt:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

So entfernen Sie das vorhandene Azure AD registrierte Konto auf dem Gerät:

- Verwenden Sie zum Entfernen des Azure AD-registrierten Kontos auf dem Gerät CleanupWPJ, ein Tool, das Sie hier herunterladen können: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extrahieren Sie die ZIP-Datei, und führen Sie **WPJCleanup. cmd** aus. Dieses Tool startet die richtige ausführbare Datei basierend auf der Windows-Version auf dem Gerät.

- Mithilfe eines Mechanismus wie Gruppenrichtlinie kann der Administrator den Befehl auf dem Gerät im Kontext eines beliebigen Benutzers ausführen, der auf dem Gerät angemeldet ist.

Um die Eingabeaufforderung des Webkonto-Managers zum Registrieren des Geräts in Azure AD zu deaktivieren, fügen Sie diesen Registrierungswert hinzu: 

- Speicherort: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Typ: DWORD (32 Bit)
- Name: BlockAADWorkplaceJoin
- Wert Daten: 1

Das vorhanden sein dieses Registrierungswerts sollte einen Arbeitsplatz Beitritt blockieren und verhindern, dass Benutzer Ansagen zum Beitritt zum Gerät anzeigen können.

## <a name="android"></a>Android

Für Android müssen Benutzer die Registrierung aufheben und Ihre Geräte erneut registrieren. Dies kann über die Microsoft Authenticator-APP oder die Unternehmens Portal-App erfolgen. 

- Von der Microsoft Authenticator-App aus können Benutzer zu **Einstellungen > Geräteregistrierung** wechseln. Von dort können Benutzer die Registrierung Ihres Geräts aufheben und erneut registrieren.
 
- Über das Unternehmens Portal können Benutzer zur Registerkarte **Geräte** wechseln und das Gerät entfernen. Registrieren Sie das Gerät anschließend mithilfe des Unternehmensportals neu.
 
- Benutzer können die Registrierung und erneute Registrierung auch aufheben, indem Sie das Konto auf der Seite Kontoeinstellungen entfernen und dann das Arbeitskonto erneut hinzufügen.

So heben Sie die Registrierung und das erneute Registrieren des Geräts unter Android mithilfe der Microsoft Authenticator-App auf:

1.  Öffnen Sie die Microsoft Authenticator-APP, und wechseln Sie zu **Einstellungen**.
2.  Wählen Sie **Geräteregistrierung** aus.
3.  Heben Sie die Registrierung des Geräts auf, indem Sie **Aufheben der Registrierung** auswählen.
4.  Registrieren Sie das Gerät bei der **Geräteregistrierung** erneut, indem Sie Ihre e-Mail-Adresse eingeben, und wählen Sie dann **registrieren** aus.

So heben Sie die Registrierung und das erneute Registrieren eines Android-Geräts mit der Android-Einstellungsseite auf:

1.  Öffnen Sie die **Geräteeinstellungen** , und wechseln Sie zu **Konten**.
2.  Wählen Sie das Arbeitskonto aus, das Sie erneut registrieren möchten, und wählen Sie **Konto entfernen** aus.
3.  Nachdem das Konto entfernt wurde, wählen Sie auf der Seite **Konten** die Option **Konto > Arbeitskonto hinzufügen** aus.
4.  Geben Sie für **Workplace Join** Ihre e-Mail-Adresse ein, und wählen Sie **beitreten** aus, um die Registrierung des Geräts abzuschließen.

So heben Sie die Registrierung und Erneutes Registrieren des Geräts unter Android im Unternehmens Portal auf:

1.  Starten Sie das Unternehmens Portal, und wechseln Sie zur Registerkarte **Geräte** .
2.  Wählen Sie das Gerät aus, um die Gerätedetails anzuzeigen.
3.  Wählen Sie im Menü Ellipsen (drei Punkte) die Option **Gerät entfernen** aus, und schließen Sie das Entfernen ab, indem Sie im Dialogfeld bestätigen.
4.  Sie sollten jetzt von der Unternehmens Portal-App abgemeldet werden. Wählen Sie **Anmelden** aus, um das Gerät erneut zu registrieren.

Weitere Informationen zu Aktionen, die während der Migrationsphase dieser Arbeitsauslastung erforderlich sind, oder die Auswirkungen auf die Verwaltung oder Verwendung, finden Sie in den Informationen zu Azure Active Directory in [weiteren allgemeinen Informationen für die Migration von Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).

## <a name="ios"></a>iOS

Auf IOS-Geräten muss ein Benutzer alle zwischengespeicherten Konten manuell aus dem Microsoft Authenticator entfernen, die Registrierung des Geräts aufheben und sich von allen systemeigenen apps auf dem Gerät abmelden.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Schritt 1: Entfernen Sie das Konto, falls vorhanden, aus der Microsoft Authenticator-app.

1. Tippen Sie auf das Konto in der Microsoft Authenticator-app.
2. Tippen Sie in der oberen rechten Ecke auf das Symbol " **Einstellungen** ". Wenn das Symbol " **Einstellungen** " nicht angezeigt wird, verwenden Sie möglicherweise nicht die neueste Version von Microsoft Authenticator.
3. Tippen Sie auf die Schaltfläche **Konto entfernen** .
4. Tippen Sie **auf alle apps auf diesem Gerät**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Schritt 2: Aufheben der Registrierung des Geräts über die Microsoft Authenticator-App

1. Tippen Sie auf das Menüsymbol in der oberen rechten Ecke.
2. Tippen Sie auf **Einstellungen** und dann auf **Geräteregistrierung**.
4. Wenn Ihr Konto angezeigt wird, tippen Sie auf **Gerät aufheben** und im Dialogfeld auf **weiter** . Danach sollte kein Konto angezeigt werden.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Schritt 3: Abmelden von einzelnen Apps bei Bedarf

Benutzer können zu einzelnen apps wie Outlook, Microsoft Teams und OneDrive wechseln und Konten aus diesen apps entfernen.

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Navigieren durch den Übergang:

- [Migrationsphasen-Aktionen und-Auswirkungen](ms-cloud-germany-transition-phases.md)
- [Zusätzliche vorab Arbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Diensten](ms-cloud-germany-transition-add-general.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](https://aka.ms/d365ceoptin)
- [Informationen zum Power BI-Migrationsprogramm](https://aka.ms/pbioptin)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
