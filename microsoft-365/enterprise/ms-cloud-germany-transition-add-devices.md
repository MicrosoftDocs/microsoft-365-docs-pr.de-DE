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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861304"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland

Mit Azure AD verbundene und registrierte Geräte, die mit Microsoft Cloud Deutschland verbunden sind, müssen nach Phase 9 und vor Phase 10 migriert werden. Die Migration eines Geräts hängt vom Gerätetyp, dem Betriebssystem und der AAD-Beziehung ab. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wie kann ich feststellen, ob meine Organisation betroffen ist?**

Administratoren sollten `https://portal.microsoftazure.de` überprüfen, ob sie über registrierte oder in Azure AD eingebundene Geräte verfügen. Wenn Ihre Organisation registrierte Geräte hat, sind Sie betroffen.

**Was sind die Auswirkungen für meine Benutzer?**

Benutzer von einem registrierten Gerät können sich nach Abschluss der [Migrationsphase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) nicht mehr anmelden, und die Endpunkte für Microsoft Cloud Deutschland wurden deaktiviert.  

Stellen Sie sicher, dass all Ihre Geräte mit dem weltweiten Endpunkt registriert sind, bevor die Verbindung Ihrer Organisation mit Microsoft Cloud Deutschland aufgehoben wird.
  
**Wann müssen meine Benutzer Ihre Geräte wieder registrieren?**

Für Ihren Erfolg ist es wichtig, dass Sie die Registrierung ihrer Geräte erst nach Abschluss der [Phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) aufheben und erneut registrieren. Sie müssen die erneute Registrierung vor Beginn der Phase 10 abschließen, andernfalls könnten Sie den Zugriff auf Ihr Gerät verlieren.

**Wie kann ich meinen Gerätstatus nach der Migration wiederherstellen?**

Für unternehmenseigene Windows Geräte, die bei Azure AD registriert sind, können Administratoren die Migration dieser Geräte über remote ausgelöste Workflows verwalten, die die Registrierung der alten Gerätezustände aufheben.
  
Für alle anderen Geräte, einschließliche persönliche Windows-Geräte, die in Azure AD registriert sind, muss der Benutzer diese Schritte manuell ausführen. Für mit Azure AD verbundene Geräte müssen Benutzer ein lokales Administratorkonto haben, um ihre Geräte abzumelden und dann wieder zu registrieren.

Ausführliche Anweisungen zum erfolgreichen Wiederherstellen von Gerätezuständen finden Sie weiter unten. 
 
**Wie stelle ich fest, ob alle meine Geräte in der Public Cloud registriert sind?**

Um zu prüfen, ob Ihre Geräte in der Public Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD-Portal in eine Excel-Tabelle exportieren und herunterladen. Filtern Sie danach die registrierten Geräte (verwenden Sie die Spalte _registeredTime_) nach der Migrationsphase [Trennen von der Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized).

## <a name="additional-considerations"></a>Zusätzliche Überlegungen
Die Geräteregistrierung ist nach der Migration des Mandanten deaktiviert und kann nicht mehr aktiviert oder deaktiviert werden. 

Wenn Sie Intune nicht verwenden, melden Sie sich bei Ihrem Abonnement an und führen Sie folgenden Befehl aus, um die Option wieder zu aktivieren:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**WICHTIG:** Der Intune-Dienstprinzipal wird nach der Commerce-Migration aktiviert, was die Aktivierung von Azure AD Device Registration impliziert. Wenn Sie Azure AD Device Registration vor der Migration blockiert haben, müssen Sie den Intune-Dienstprinzipal mit PowerShell deaktivieren, um die Azure AD-Geräteregistrierung mit dem Azure AD-Portal erneut zu deaktivieren. Sie können den Intune-Dienstprinzipal mit diesem Befehl im Azure Active Directory PowerShell für Graph-Modul deaktivieren.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Azure AD Join
Dies gilt für Windows 10 Geräte. 

Wenn ein Gerät mit Azure AD verbunden ist, muss es von Azure AD getrennt und erneut verbunden werden. 

[![Azure AD-GeräteRe-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Wenn der Benutzer ein Administrator auf dem Windows 10 Gerät ist, kann der Benutzer die Registrierung des Geräts bei Azure AD aufheben und es erneut verknüpfen. Wenn er über keine Administratorrechte verfügt, benötigt der Benutzer Anmeldeinformationen eines lokalen Administratorkontos auf diesem Computer. 


Ein Administrator kann ein lokales Administratorkonto auf dem Gerät erstellen, das folgendem Konfigurationspfad folgt:

*Einstellungen > Konten > Andere Konten > Anmeldeinformationen unbekannt > Benutzer ohne Microsoft-Konto hinzufügen*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Schritt 1: Ermitteln, ob das Gerät mit azure-ID verknüpft ist
1.  Melden Sie sich mit E-Mail-Adresse und Kennwort des Benutzers an.
2.  Wechseln Sie zu Einstellungen > Konten, > auf Arbeits- oder Schulkonto zugreifen. 
3.  Suchen Sie nach einem Benutzer in der Liste, der **mit ... Azure AD .** 
4.  Wenn ein verbundener Benutzer vorhanden ist, fahren Sie mit Schritt 2 fort. Wenn nicht, ist keine weitere Aktion erforderlich.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Schritt 2: Trennen des Geräts von Azure AD
1.  Tippen Sie auf **"Trennen"** für das verbundene Geschäfts-, Schul- oder Unikonto. 
2.  Bestätigen Sie die Verbindung zweimal. 
3.  Geben Sie den Benutzernamen und das Kennwort des lokalen Administrators ein. Das Gerät wird getrennt.
4.  Starten Sie das Gerät neu.
### <a name="step-3-join-the-device-to-azure-ad"></a>Schritt 3: Verknüpfen des Geräts mit Azure AD
1.  Der Benutzer meldet sich mit den Anmeldeinformationen des lokalen Administrators an.
2.  Wechseln Sie zu **Einstellungen** **dann** konten, und greifen Sie dann auf Arbeit oder **Schule zu**
3.  Tippen **auf Verbinden**
4.  **WICHTIG:** Tippen **Sie auf "Beitritt zu Azure AD"**
5.  Geben Sie die E-Mail-Adresse und das Kennwort des Benutzers ein. Das Gerät ist verbunden
6.  Starten Sie das Gerät neu. 
7.  sign with your e-mail address and password

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

- [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md)
- [Hilfe zur Microsoft Cloud Deutschland-Migration Assistance](https://aka.ms/germanymigrateassist)
- [So können Sie sich für die Migration anmelden](ms-cloud-germany-migration-opt-in.md)
- [Kundenerfahrung während der Migration](ms-cloud-germany-transition-experience.md)

Der Weg durch die Umstellung:

- [Phasen, Aktionen und Auswirkungen der Migration](ms-cloud-germany-transition-phases.md)
- [Zusätzliche Vorarbeit](ms-cloud-germany-transition-add-pre-work.md)
- Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-Apps:

- [Informationen zum Dynamics 365-Migrationsprogramm](/dynamics365/get-started/migrate-data-german-region)
- [Informationen zum Power BI-Migrationsprogramm](/power-bi/admin/service-admin-migrate-data-germany)
- [Erste Schritte mit dem Upgrade von Microsoft Teams](/microsoftteams/upgrade-start-here)