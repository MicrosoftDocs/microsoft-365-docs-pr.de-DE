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
ms.openlocfilehash: 684af01b2d90f44b2cda1cf050d1e4db70f92915
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289439"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland

In Azure AD eingebundene und registrierte Geräte, die mit Microsoft Cloud Deutschland verbunden sind, müssen nach Phase 9 und vor Phase 10 migriert werden. Die Migration eines Geräts hängt vom Gerätetyp, dem Betriebssystem und der Azure AD-Beziehung ab.

## <a name="azure-ad-joined-windows-10-devices"></a>In Azure AD eingebundene Windows 10-Geräte
Wenn ein Windows 10-Gerät in Azure AD eingebunden ist, muss es von Azure AD getrennt und erneut verbunden werden.

[ ![So binden Sie Geräte erneut in Azure AD ein](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Administratoren von Windows 10-Geräten, können die Registrierung des Geräts in Azure AD aufheben und es in drei Schritten erneut einbinden.

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Schritt 1: Ermitteln, ob das Gerät mit einer Azure-ID eingebunden ist

1. Melden Sie sich mit Ihrem Geschäftskonto an.
2. Wechseln Sie zu **Einstellungen** > **Konten** > **Auf Geschäfts- oder Schulkonto zugreifen**.
3. Suchen Sie in der Liste nach einem Konto, dass **mit [...] Azure AD verbunden** ist.
4. Wenn ein verbundenes Konto vorhanden ist, fahren Sie mit Schritt 2 fort.

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Schritt 2: Das Gerät von Azure AD trennen

1. Klicken Sie auf **Trennen** im verbundenen Arbeits- oder Schulkonto.
2. Bestätigen Sie die Trennung zweimal.
3. Geben Sie den Benutzernamen und das Kennwort für einen lokalen Administratoren ein. Die Verbindung mit dem Gerät wurde getrennt.
4. Starten Sie das Gerät neu.

### <a name="step-3-join-the-device-to-azure-ad"></a>Schritt 3: Das Gerät in Azure AD einbinden

1. Melden Sie sich mit den Anmeldeinformationen für das lokale Administratorkonto an.
2. Wechseln Sie zu **Einstellungen** > **Konten** > **Auf Geschäfts- oder Schulkonto zugreifen**.
3. Klicken Sie auf **Verbinden**.
4. **WICHTIG**: Klicken Sie auf **In Azure AD einbinden**.
5. Geben Sie die E-Mail-Adresse und das Kennwort Ihres Geschäftskontos ein. Das Gerät ist verbunden.
6. Starten Sie das Gerät neu.
7. Melden Sie sich mit der E-Mail-Adresse und dem Kennwort Ihres Geschäftskontos an.

Wenn der Benutzer kein Administrator des Geräts ist, kann ein globaler Azure AD-Administrator das lokale Administratorkonto auf dem Gerät mithilfe dieses Konfigurationspfads erstellen und die Verbindung mit dem Gerät trennen:

*Einstellungen > Konten > Andere Konten > Anmeldeinformationen unbekannt > Benutzer ohne Microsoft-Konto hinzufügen*

Für die Wiedereinbindung können in diesem Schritt die Anmeldeinformationen aller Geschäftskonten Ihrer Organisation verwendet werden.

Bitte beachten Sie, dass das für die Einbindung des Geräts verwendete Geschäftskonto automatisch als Administrator des Geräts eingestuft wird.
Jedes andere Geschäftskonto der Organisation kann sich im Gerät anmelden, hat aber keine Administratorrechte.

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>In Azure AD registrierte (in den Arbeitsplatz eingebunden) Windows 10-Geräte

Wenn ein Windows 10-Gerät in Azure AD registriert ist, muss es von Azure AD getrennt und erneut verbunden werden.

[ ![So registrieren Sie Geräte erneut in Azure AD](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>Schritt 1: Ermitteln, ob das Gerät mit einer Azure-ID registriert ist

1. Melden Sie sich mit Ihrem Benutzernamen und Kennwort an.
2. Wechseln Sie zu **Einstellungen** > **Konten** > **Auf Geschäfts- oder Schulkonto zugreifen**.
3. Suchen Sie in der Liste nach Ihrem Geschäftskonto und überprüfen Sie, ob es **mit [...] Azure AD verbunden** ist.

    Wenn Ihr Geschäftsskonto in der Liste aufgeführt ist, aber NICHT mit Azure AD verbunden ist, fahren Sie mit Schritt 2 fort.

    Andernfalls handelt es sich bei Ihrem Gerät um ein in Azure AD eingebundenes Gerät und Sie müssen den Informationen unter [In Azure AD eingebundene Windows 10-Geräte](#azure-ad-joined-windows-10-devices) folgen.

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Schritt 2: Das Gerät von Azure AD trennen

1. Klicken Sie auf Ihr Geschäftskonto. Die Schaltflächen *Info* und *Trennen* werden angezeigt.
2. Klicken Sie auf **Trennen**.
3. Bestätigen Sie das Entfernen des Kontos auf dem Gerät, indem Sie auf **Ja** klicken.

### <a name="step-3-connect-the-device-to-azure-ad"></a>Schritt 3: Das Gerät mit Azure AD verbinden

1. Klicken Sie auf **Verbinden**.
2. Geben Sie die E-Mail-Adresse Ihres Geschäftskontos ein und klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort Ihres Geschäftskontos ein und klicken Sie auf **Anmelden**.
4. Bestätigen Sie, indem Sie auf **Fertig** klicken. Ihr Geschäftskonto wird erneut aufgeführt.

## <a name="android"></a>Android

Für Android müssen Benutzer ihre Geräte abmelden und wieder registrieren. Dies kann mit der Microsoft Authenticator-App oder der Unternehmensportal-App geschehen.

- Aus der Microsoft Authenticator-App können die Benutzer zu **Einstellungen > Geräteregistrierung** gehen. Von dort aus können die Benutzer ihre Geräte abmelden und wieder registrieren.

- Aus dem Unternehmensportal können die Benutzer zu Registerkarte **Geräte** gehen und das Gerät entfernen. Danach registrieren Sie das Gerät erneut über das Unternehmensportal.

- Benutzer können das Gerät auch abmelden und wieder registrieren, indem Sie das Konto von der Seite „Kontoeinstellungen“ entfernen und dann das Geschäftskonto wieder hinzufügen.

Um das Gerät mit der Microsoft Authenticator-App auf Android abzumelden und wieder zu registrieren:

1. Öffnen Sie die Microsoft Authenticator-App und gehen Sie zu **Einstellungen**.
2. Wählen Sie **Geräteregistrierung**.
3. Melden Sie das Gerät ab, indem Sie **Registrierung aufheben** auswählen.
4. Für die **Geräteregistrierung** registrieren Sie das Gerät erneut, indem Sie Ihre E-Mail-Adresse eingeben und **Registrieren** auswählen.

Um ein Android-Gerät mit der Seite für Android-Einstellungen abzumelden und wieder zu registrieren:

1. Öffnen Sie **Geräteeinstellungen** und gehen sie zu **Konten**.
2. Wählen das Geschäftskonto aus, das Sie wieder registrieren wollen und wählen Sie **Konto entfernen**.
3. Nachdem das Konto entfernt wurde, wählen Sie von der **Konto**-Seite aus **Konto hinzufügen > Geschäftskonto**.
4. Für die **Arbeitsplatz-Verknüpfung** geben Sie Ihre E-Mail-Adresse ein und wählen Sie **Verknüpfung**, um die Registrierung des Geräts abzuschließen.

Um das Gerät auf Android über das Unternehmensportal abzumelden und neu zu registrieren:

1. Starten Sie das Unternehmensportal und gehen Sie zur Registerkarte **Geräte**.
2. Wählen Sie das Gerät aus, um die Gerätedetails zu sehen.
3. Aus dem Ellipsen-Menü (drei Punkte) wählen Sie **Gerät entfernen** und schließen das Entfernen ab, indem Sie dies im Dialogfeld bestätigen.
4. Sie sollten jetzt von der Unternehmensportal-App abgemeldet sein. Wählen Sie **Anmelden**, um das Gerät wieder zu registrieren.

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
3. Wenn Ihr Konto angezeigt wird, tippen Sie im Dialog auf **Registrierung des Geräts aufheben** und **Weiter**. Sie sollten danach kein Konto mehr sehen.

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Schritt 3: Abmelden aus individuellen Apps wenn notwendig.

Benutzer können zu individuellen Apps wie Outlook, Teams oder OneDrive wechseln und Konten aus diese Apps entfernen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wie kann ich feststellen, ob meine Organisation betroffen ist?**

Administratoren sollten überprüfen, `https://portal.microsoftazure.de` ob Geräte vorhanden sind, die in Azure AD registriert oder eingebunden sind. Wenn Geräte Ihrer Organisation in Azure AD registriert oder eingebunden sind, muss Ihre Organisation die Anweisungen auf dieser Seite befolgen.

**Wann müssen die Benutzer ihre Geräte wieder registrieren?**

Es ist wichtig für Ihren Erfolg, dass Sie die Registrierung Ihrer Geräte erst aufheben und wiederholen, nachdem [Phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) abgeschlossen ist. Sie müssen die erneute Registrierung abgeschlossen haben, bevor Phase 10 beginnt. Andernfalls könnten Sie den Zugriff auf Ihr Gerät verlieren.

**Wie stelle ich fest, ob alle meine Geräte in der Public Cloud registriert sind?**

Um zu prüfen, ob Ihre Geräte in der Public Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD-Portal in eine Excel-Tabelle exportieren und herunterladen. Filtern Sie anschließend die registrierten Geräte (verwenden Sie die Spalte _registeredTime_) nach dem Datum, an dem Ihre Organisation [Phase 9 des Migrationsprozesses](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) abgeschlossen hat.

## <a name="additional-considerations"></a>Zusätzliche Überlegungen

> [!IMPORTANT]
> Der Intune-Dienstprinzipal wird nach [Phase 3 des Migrationsprozesses](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) aktiviert, was die Aktivierung der Azure AD Device Registration impliziert. Wenn Sie Azure AD Device Registration vor der Migration blockiert haben, müssen Sie den Intune-Dienstprinzipal mit PowerShell deaktivieren, um die Azure AD-Geräteregistrierung mit dem Azure AD-Portal erneut zu deaktivieren. Sie können den Intune-Dienstprinzipal mit diesem Befehl im Azure Active Directory PowerShell für Graph-Modul deaktivieren.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

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
