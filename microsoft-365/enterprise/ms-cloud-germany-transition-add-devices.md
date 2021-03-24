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
description: 'Zusammenfassung: Zusätzliche Geräteinformationen für Dienste beim Übergang von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928156"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wie kann ich feststellen, ob meine Organisation betroffen ist?**

Administratoren sollten `https://portal.microsoftazure.de` überprüfen, um festzustellen, ob sie registrierte Geräte haben. Wenn Ihre Organisation registrierte Geräte hat, sind Sie betroffen.

**Was sind die Auswirkungen für meine Benutzer?**

Benutzer mit registrierten Geräten können sich nicht mehr anmelden, sobald Ihre Migration mit der Migrationsphase [Azure AD abschließen](ms-cloud-germany-transition.md#how-is-the-migration-organized) beginnt.  

Stellen Sie sicher, dass all Ihre Geräte mit dem weltweiten Endpunkt registriert sind, bevor die Verbindung Ihrer Organisation mit Microsoft Cloud Deutschland aufgehoben wird.
  
**Wann müssen meine Benutzer Ihre Geräte wieder registrieren?**

Es ist für Ihren Erfolg kritisch, dass Sie Ihre Geräte nur während der Migrationsphase [Trennen von Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) abmelden und wieder registrieren.

**Wie kann ich meinen Gerätstatus nach der Migration wiederherstellen?**

Bei mit Azure AD Hybrid verbundenen und bei firmeneigenen Windows-Geräten, die bei Azure AD registriert sind, können Administratoren die Migration dieser Geräte über remote ausgelöste Workflows verwalten, bei denen die Registrierung der alten Gerätezustände aufgehoben wird.
  
Für alle anderen Geräte, einschließliche persönliche Windows-Geräte, die in Azure AD registriert sind, muss der Benutzer diese Schritte manuell ausführen. Für mit Azure AD verbundene Geräte müssen Benutzer ein lokales Administratorkonto haben, um ihre Geräte abzumelden und dann wieder zu registrieren.

Microsoft wird Anweisungen veröffentlichen, wie Sie den Gerätestatus erfolgreich wiederherstellen können. 
 
**Wie stelle ich fest, ob alle meine Geräte in der Public Cloud registriert sind?**

Um zu prüfen, ob Ihre Geräte in der Public Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD-Portal in eine Excel-Tabelle exportieren und herunterladen. Filtern Sie danach die registrierten Geräte (verwenden Sie die Spalte _registeredTime_) nach der Migrationsphase [Trennen von der Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized).

Die Geräteregistrierung ist nach der Migration des Mandanten deaktiviert und kann nicht mehr aktiviert oder deaktiviert werden. Wenn Sie Intune nicht verwenden, melden Sie sich bei Ihrem Abonnement an und führen Sie folgenden Befehl aus, um die Option wieder zu aktivieren:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Azure AD Hybrid Join

### <a name="windows-down-level"></a>Kompatibles Windows

_Kompatible Windows-Geräte_ sind Windows-Geräte, welche eine frühere Version von Windows ausführen (wie z. B. Windows 8.1 oder Windows 7), oder die Windows Server-Versionen vor 2019 und 2016 ausführen. Wenn solche Geräte früher registriert wurden, müssen Sie diese Geräte abmelden und wieder registrieren. 

Um herauszufinden, ob ein kompatibles Windows-Gerät früher mit Azure AD verbunden wurde, führen Sie auf dem Gerät folgenden Befehl aus:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Wenn das Gerät früher mit Azure AD verbunden war, und wenn das Gerät eine Netzwerkverbindung mit globalen Azure AD-Endpunkten hat, würden Sie die folgende Ausgabe sehen:

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

Die betroffenen Geräte werden einen „Gerätestatus“ mit Wert „Unbekannt“ haben. Für Geräte mit Ausgabewert „Gerät nicht verbunden“ oder für Geräte mit „Gerätestatus“-Wert „Okay“ können Sie die folgende Anleitung ignorieren.

Nur für Geräte, die anzeigen, dass das Gerät verbunden ist (aufgrund von Geräte-ID, Fingerabdruck usw.) und deren „Gerätestatus“-Wert „Unbekannt“ ist, sollten Administratoren den folgenden Befehl im Kontext eines Domänenbenutzers ausführen, der sich bei einem solchen kompatiblen Gerät anmeldet:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

Der vorstehende Befehl muss nur einmal pro Domänenbenutzer ausgeführt werden, der sich auf dem kompatiblen Windows-Gerät anmeldet. Dieser Befehl sollte im Kontext eines sich anmeldenden Domänenbenutzers ausgeführt werden. 

Es muss sichergestellt werden, dass dieser Befehl nicht ausgeführt wird, wenn sich der Benutzer anschließend anmeldet. Wenn der vorhergehende Befehl ausgeführt wird, wird der verbundene Status des lokalen Azure AD Hybrid-verbundenen Computers für den Benutzer gelöscht, der sich angemeldet hat. Und wenn der Computer im Mandanten immer noch als Azure AD Hybrid-verbunden konfiguriert ist, wird er versuchen, sich wieder zu verknüpfen, wenn der Benutzer sich anmeldet.

### <a name="windows-current"></a>Aktuelles Windows

#### <a name="unjoin"></a>Verknüpfung auflösen

Um herauszufinden, ob ein Windows 10-Gerät früher mit Azure AD verbunden wurde, führen Sie auf dem Gerät folgenden Befehl aus:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Wenn das Gerät Azure AD Hybrid-verbunden ist, würde der Administrator die folgende Ausgabe sehen:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Wenn die Ausgabe „AzureAdJoined: Nein“ ist, können Sie die folgende Anleitung ignorieren.

Führen Sie nur für Geräte, die anzeigen, dass das Gerät mit Azure AD verbunden ist, den folgenden Befehl als Administrator aus, um den verbundenen Status des Geräts zu entfernen.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Der vorstehende Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden.

#### <a name="hybrid-ad-joinre-registration"></a>AD Hybrid Beitritt/Wieder-Registrierung

Das Gerät wird automatisch ohne Benutzer- oder Administratoreingriff mit Azure AD verbunden, solange das Gerät über eine Netzwerkverbindung zu globalen Azure AD-Endpunkten verfügt. 


## <a name="azure-ad-join"></a>Azure AD Join

**WICHTIG:** Der Intune-Dienstprinzipal wird nach der Commerce-Migration aktiviert, was die Aktivierung von Azure AD Device Registration impliziert. Wenn Sie Azure AD Device Registration vor der Migration blockiert haben, müssen Sie den Intune-Dienstprinzipal mit PowerShell deaktivieren, um die Azure AD-Geräteregistrierung mit dem Azure AD-Portal erneut zu deaktivieren. Sie können den Intune-Dienstprinzipal mit diesem Befehl im Azure Active Directory PowerShell für Graph-Modul deaktivieren.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Verknüpfung auflösen

Um herauszufinden, ob ein Windows 10-Gerät früher mit Azure AD verbunden wurde, kann der Benutzer oder Administrator auf dem Gerät folgenden Befehl ausführen:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Wenn das Gerät mit Azure AD verbunden ist, würden der Benutzer oder der Administrator die folgende Ausgabe sehen:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Wenn die Ausgabe „AzureAdJoined: NEIN“ ist, können Sie die folgende Anleitung ignorieren.

Benutzer: Wenn das Gerät mit Azure AD verbunden ist, kann ein Benutzer die Verknüpfung des Geräts in den Einstellungen auflösen. Stellen Sie sicher, dass ein lokales Administratorkonto auf dem Gerät vorhanden ist, bevor Sie die Verknüpfung des Geräts mit Azure AD aufheben. Das lokale Administratorkonto wird benötigt, um sich wieder am Gerät anzumelden.

Administrator: Wenn der Administrator einer Organisation die Verknüpfung der Azure AD-verbundenen Geräte eines Benutzers aufheben will, kann er dies durch das Ausführen des folgenden Befehls auf jedem der Geräte machen, indem er einen Mechanismus wie z. B. die Gruppenrichtlinie verwendet. Der Administrator muss sicherstellen, dass ein lokales Administratorkonto auf dem Gerät vorhanden ist, bevor er die Verknüpfung des Geräts mit Azure AD aufhebt. Das lokale Administratorkonto ist notwendig, um sich wieder am Gerät anzumelden.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Der vorstehende Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden. 

### <a name="azure-ad-joinre-registration"></a>Azure AD Beitritt/Wieder-Registrierung

Der Benutzer kann das Gerät über die Windows-Einstellungen zu Azure AD verknüpfen: **Einstellungen > Konten > Zugriff auf Arbeit oder Schule > Verbinden**.
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD-registriert (Unternehmensbesitz)

Um herauszufinden, ob ein Windows 10-Gerät Azure AD-registriert ist, führen Sie auf dem Gerät folgenden Befehl aus:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Wenn das Gerät Azure AD-registriert ist, würden Sie folgende Ausgabe sehen:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Um das bestehende Azure AD-registrierte Konto auf dem Gerät zu entfernen:

- Um das bestehende Azure AD-registrierte Konto auf dem Gerät zu entfernen verwenden Sie CleanupWPJ, ein Tool, das Sie hier herunterladen können: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extrahieren Sie die ZIP-Datei und führen Sie **WPJCleanup.cmd** aus. Dieses Tool wird basierend auf der Windows-Version auf dem Gerät die richtige ausführbare Datei starten.

- Wenn Sie einen Mechanismus wie die Gruppenrichtlinie verwenden, kann der Administrator den Befehl im Kontext jedes auf dem Gerät angemeldeten Benutzers ausführen.

Um die Web Account Manager-Eingabeaufforderungen zur Registrierung des Geräts in Azure AD zu deaktivieren, fügen Sie folgenden Registry-Wert hinzu: 

- Ort: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Typ: DWORD (32 bit)
- Name: BlockAADWorkplaceJoin
- Wertdaten: 1

Das Vorhandensein dieses Registry-Werts sollte die Arbeitsplatz-Verknüpfung blockieren und verhindern, dass Benutzer Eingabeaufforderungen zum Verknüpfen des Geräts sehen.

## <a name="android"></a>Android

Für Android müssen Benutzer ihre Geräte abmelden und wieder registrieren. Dies kann mit der Microsoft Authenticator-App oder der Unternehmensportal-App geschehen. 

- Aus der Microsoft Authenticator-App können die Benutzer zu **Einstellungen > Geräteregistrierung** gehen. Von dort aus können die Benutzer ihre Geräte abmelden und wieder registrieren.
 
- Aus dem Unternehmensportal können die Benutzer zu Registerkarte **Geräte** gehen und das Gerät entfernen. Danach registrieren Sie das Gerät erneut über das Unternehmensportal.
 
- Benutzer können das Gerät auch abmelden und wieder registrieren, indem Sie das Konto von der Seite „Kontoeinstellungen“ entfernen und dann das Geschäftskonto wieder hinzufügen.

Um das Gerät mit der Microsoft Authenticator-App auf Android abzumelden und wieder zu registrieren:

1.  Öffnen Sie die Microsoft Authenticator-App und gehen Sie zu **Einstellungen**.
2.  Wählen Sie **Geräteregistrierung**.
3.  Melden Sie das Gerät ab, indem Sie **Registrierung aufheben** auswählen.
4.  Für die **Geräteregistrierung** registrieren Sie das Gerät erneut, indem Sie Ihre E-Mail-Adresse eingeben und **Registrieren** auswählen.

Um ein Android-Gerät mit der Seite für Android-Einstellungen abzumelden und wieder zu registrieren:

1.  Öffnen Sie **Geräteeinstellungen** und gehen sie zu **Konten**.
2.  Wählen das Geschäftskonto aus, das Sie wieder registrieren wollen und wählen Sie **Konto entfernen**.
3.  Nachdem das Konto entfernt wurde, wählen Sie von der **Konto**-Seite aus **Konto hinzufügen > Geschäftskonto**.
4.  Für die **Arbeitsplatz-Verknüpfung** geben Sie Ihre E-Mail-Adresse ein und wählen Sie **Verknüpfung**, um die Registrierung des Geräts abzuschließen.

Um das Gerät auf Android über das Unternehmensportal abzumelden und neu zu registrieren:

1.  Starten Sie das Unternehmensportal und gehen Sie zur Registerkarte **Geräte**.
2.  Wählen Sie das Gerät aus, um die Gerätedetails zu sehen.
3.  Aus dem Ellipsen-Menü (drei Punkte) wählen Sie **Gerät entfernen** und schließen das Entfernen ab, indem Sie dies im Dialogfeld bestätigen.
4.  Sie sollten jetzt von der Unternehmensportal-App abgemeldet sein. Wählen Sie **Anmelden**, um das Gerät wieder zu registrieren.

Weitere Informationen zu Aktionen, die während der Migrationsphase dieses Workloads erforderlich sind, oder zu Auswirkungen auf die Verwaltung oder Verwendung finden Sie in den Informationen zu Azure Active Directory (Azure AD) unter [Zusätzliche Azure AD-Informationen für die Migration von Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).

## <a name="ios"></a>iOS

Auf iOS-Geräten muss ein Benutzer alle zwischengespeicherten Konten manuell aus dem Microsoft Authenticator entfernen, die Registrierung des Geräts aufheben und sich von allen nativen Apps auf dem Gerät abmelden.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Schritt 1: Wenn vorhanden, entfernen Sie das Konto aus der Microsoft Authenticator-App

1. Tippen Sie auf des Konto in der Microsoft Authenticator-App.
2. Tippen Sie auf das Symbol **Einstellungen** in der oberen rechten Ecke.  Wenn Sie das Symbol **Einstellungen** nicht sehen, verwenden Sie möglicherweise nicht die aktuelle Version des Microsoft Authenticator.
3. Tippen Sie die Schaltfläche **Konto entfernen**.
4. Tippen Sie auf **Alle Apps auf diesem Gerät**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Schritt 2: Registrierung des Geräts in der Microsoft Authenticator-App aufheben

1. Tippen Sie auf das Menu-Symbol in der oberen rechten Ecke. 
2. Tippen Sie **Einstellungen** und dann **Geräteregistrierung**.
4. Wenn Ihr Konto angezeigt wird, tippen Sie im Dialog auf **Registrierung des Geräts aufheben** und **Weiter**. Sie sollten danach kein Konto mehr sehen.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Schritt 3: Abmelden aus individuellen Apps wenn notwendig.

Benutzer können zu individuellen Apps wie Outlook, Teams oder OneDrive wechseln und Konten aus diese Apps entfernen.

## <a name="more-information"></a>Weitere Informationen

Erste Schritte:

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)