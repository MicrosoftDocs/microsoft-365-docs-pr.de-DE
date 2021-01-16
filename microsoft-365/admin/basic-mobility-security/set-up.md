---
title: Einrichten von grundlegender Mobilität und Sicherheit
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Richten Sie Basic Mobility and Security ein, um die mobilen Geräte Ihrer Benutzer zu sichern und zu verwalten.
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876864"
---
# <a name="set-up-basic-mobility-and-security"></a>Einrichten von grundlegender Mobilität und Sicherheit

Mit der integrierten Basismobilität und -sicherheit für Microsoft 365 können Sie mobile Geräte von Benutzern wie iPhones, iPads, Androids und Windows Phones sichern und verwalten. Sie können Sicherheitsrichtlinien für Geräte erstellen und verwalten, ein Gerät aus der Ferne zurücksetzen und detaillierte Berichte zu Geräten anzeigen.

Haben Sie Fragen? Häufig gestellte Fragen (FAQ) zu häufig gestellten Fragen finden Sie unter "Häufig gestellte Fragen (FAQ) zu Basic [Mobility and Security".](frequently-asked-questions.md) Beachten Sie, dass Sie kein delegiertes Administratorkonto zum Verwalten von Basic Mobility and Security verwenden können. Weitere Informationen finden Sie unter ["Partner: Anbieten einer delegierten Verwaltung".](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

Die Geräteverwaltung ist Teil des Security & Compliance Center, daher müssen Sie dort hingehen, um die Einrichtung von Basic Mobility and Security zu starten.

## <a name="activate-the-basic-mobility-and-security-service"></a>Aktivieren des Grundlegenden Mobilitäts- und Sicherheitsdiensts

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Wechseln Sie zu ["Grundlegende Mobilität und Sicherheit aktivieren".](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Es kann einige Zeit dauern, bis Basic Mobility and Security aktiviert ist. Nach Abschluss des Schritts erhalten Sie eine E-Mail, in der die nächsten Schritte erläutert werden.

## <a name="set-up-mobile-device-management"></a>Einrichten der Verwaltung mobiler Geräte

Wenn der Dienst bereit ist, führen Sie die folgenden Schritte aus, um das Setup abzuschließen.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Schritt 1: (Erforderlich) Konfigurieren von Domänen für grundlegende Mobilität und Sicherheit

Wenn Microsoft 365 keine benutzerdefinierte Domäne zugeordnet ist oder Sie keine Windows-Geräte verwalten, können Sie diesen Abschnitt überspringen. Andernfalls müssen Sie die DNS-Einträge für die Domäne bei Ihrem DNS-Host hinzufügen. Wenn Sie die Einträge bereits im Rahmen der Einrichtung Ihrer Domäne bei Microsoft 365 hinzugefügt haben, sind Sie alle festgelegt. Nachdem Sie die Einträge hinzugefügt haben, werden Microsoft 365-Benutzer in Ihrer Organisation, die sich auf ihrem Windows-Gerät mit einer E-Mail-Adresse anmelden, die Ihre benutzerdefinierte Domäne verwendet, umgeleitet, um sich bei Basic Mobility and Security zu registrieren.

Benötigen Sie Hilfe beim Einrichten der Datensätze? Suchen Sie Ihre Domänenregistrierungsstelle, und wählen Sie den Registrierungsstellennamen aus, um zur schrittweisen Hilfe zum Erstellen eines DNS-Eintrags in der Liste zu wechseln, die unter "Hinzufügen von DNS-Einträgen zum Herstellen einer Verbindung mit Ihrer Domäne" bereitgestellt [wird.](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Verwenden Sie diese Anweisungen, um #A0 zu erstellen, die unter "Vereinfachen der [#A1 ohne Azure AD Premium" beschrieben werden.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

Nachdem Sie die beiden & hinzugefügt haben, wechseln Sie zurück zum Security & Compliance Center, und wechseln Sie zur Geräteverwaltung zur Verhinderung von Datenverlust, um den nächsten  >     Schritt zu abschließen.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Schritt 2: (Erforderlich) Konfigurieren eines APNs-Zertifikats für iOS-Geräte

Um iOS-Geräte wie iPads und iPhones zu verwalten, müssen Sie ein APNs-Zertifikat erstellen.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. In Ihrem Browsertyp:  [https://protection.office.com](https://protection.office.com/) .

3. Wählen  **Sie "Verwaltung von Geräten zur Verhinderung** von   >  **Datenverlust"** und **"APNs-Zertifikat für iOS-Geräte" aus.**

4. On the Apple Push Notification Certificate Settings page, choose **Next**.

5. Wählen **Sie "CSR-Datei herunterladen"** aus, und speichern Sie die Zertifikatsignieranforderung an einem Ort auf Ihrem Computer, den   Sie sich merken werden. Wählen Sie **"Weiter" aus.**

6. Auf der Seite zum Erstellen eines APNs-Zertifikats:

   - Wählen Sie das Apple-APNS-Portal aus, um das Apple Push Certificates Portal zu öffnen.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Wählen Sie "Zertifikat erstellen" aus, und akzeptieren Sie die Nutzungsbedingungen.
   - Navigieren Sie zu der Zertifikatsignieranforderung, die Sie von Microsoft 365 auf Ihren Computer heruntergeladen haben, und wählen SieUpload aus.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Wechseln Sie zurück zu Microsoft 365, und wählen Sie **"Weiter" aus.**

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Select  **Finish**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Schritt 3: (empfohlen) Einrichten der mehrstufigen Authentifizierung

MFA trägt dazu bei, die Anmeldung bei Microsoft 365 für die Registrierung mobiler Geräte zu sichern, indem eine zweite Authentifizierungsform erforderlich ist. Benutzer müssen einen Telefonanruf, eine Sms oder eine App-Benachrichtigung auf ihrem mobilen Gerät bestätigen, nachdem sie ihr Kennwort für das Arbeitskonto richtig eingegeben haben. Sie können ihr Gerät erst registrieren, nachdem diese zweite Authentifizierungsform abgeschlossen ist. Nachdem Benutzergeräte in Basic Mobility and Security registriert wurden, können Benutzer nur mit ihrem Arbeitskonto auf Microsoft 365-Ressourcen zugreifen.

Informationen zum Aktivieren von MFA im Azure AD-Portal finden Sie unter [Einrichten der mehrstufigen Authentifizierung.](https://go.microsoft.com/fwlink/p/?LinkId=519255)

Nachdem Sie die MFA eingerichtet haben, wechseln Sie wieder **** zum Security & Compliance Center, und navigieren Sie zu Geräterichtlinien zur Verhinderung von Datenverlust, um den nächsten   >     >  ****   Schritt zu vervollständigen.

### <a name="step-4-recommended-manage-device-security-policies"></a>Schritt 4: (Empfohlen) Verwalten von Gerätesicherheitsrichtlinien

Der nächste Schritt besteht im Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien zum Schutz Ihrer Microsoft 365-Organisationsdaten. Sie können z. B. dazu beitragen, Datenverluste zu verhindern, wenn ein Benutzer sein Gerät verliert, indem Sie eine Richtlinie zum Sperren von Geräten nach fünf Minuten Inaktivität erstellen und Geräte nach drei Anmeldefehlern löschen.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Wählen [Sie "Mobile Geräteverwaltung aktivieren" aus.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Wenn der Dienst aktiviert ist, werden stattdessen die Aktivierungsschritte mit einem Link zum Verwalten [von Geräten angezeigt.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Wechseln Sie zu **Geräterichtlinien.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits- und Mobilitätsrichtlinieneinstellungen":::

4. Erstellen und bereitstellen Sie Gerätesicherheitsrichtlinien, die für Ihre Organisation geeignet sind, und folgen Sie den Schritten unter "Erstellen von Gerätesicherheitsrichtlinien [in Basic Mobility and Security ".](create-device-security-policies.md)

> [!TIP]
>
> - Wenn Sie eine neue Richtlinie erstellen, sollten Sie die Richtlinie so festlegen, dass der Zugriff und die Meldung von Richtlinienverstößen zulässig sind, wenn ein Benutzergerät nicht mit der Richtlinie kompatibel ist. Dadurch können Sie sehen, wie viele mobile Geräte von der Richtlinie betroffen sind, ohne den Zugriff auf Microsoft 365 zu blockieren.
>
> - Bevor Sie eine neue Richtlinie für alle Benutzer in Ihrer Organisation bereitstellen, sollten Sie sie auf den Geräten testen, die von einer kleinen Anzahl von Benutzern verwendet werden.
>
> - Teilen Sie Ihrer Organisation außerdem vor der Bereitstellung von Richtlinien die potenziellen Auswirkungen der Registrierung eines Geräts in Basic Mobility and Security mit. Je nachdem, wie Sie die Richtlinien einrichten, können Geräte, die nicht den Richtlinien entsprechen (nicht kompatible Geräte), am Zugriff auf Microsoft 365 blockiert werden. Auf nicht kompatiblen Geräten können auch Apps, Fotos und andere persönliche Informationen installiert sein, die auf einem registrierten Gerät gelöscht werden können, wenn das Gerät gelöscht wird. Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Sicherstellen, dass Benutzer ihre Geräte registrieren

Nachdem Sie eine Richtlinie für die Verwaltung mobiler Geräte erstellt und bereitgestellt haben, erhält jeder lizenzierte Microsoft 365-Benutzer in Ihrer Organisation, für den die Geräterichtlinie gilt, eine Registrierungsnachricht, wenn er sich das nächste Mal von seinem mobilen Gerät bei Microsoft 365 anmeldet. Sie müssen die Registrierungs- und Aktivierungsschritte abschließen, bevor sie auf Microsoft 365-E-Mails und -Dokumente zugreifen können. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).

> [!IMPORTANT]
> Wenn die bevorzugte Sprache eines Benutzers vom Registrierungsprozess nicht unterstützt wird, erhalten Benutzer möglicherweise eine Registrierungsbenachrichtigung und Schritte auf ihren mobilen Geräten in einer anderen Sprache. Nicht alle Sprachen, die in Microsoft 365 unterstützt werden, werden derzeit für den Registrierungsprozess auf mobilen Geräten unterstützt.

Benutzer mit Android- oder iOS-Geräten müssen die Unternehmensportal-App im Rahmen des Registrierungsprozesses installieren.

## <a name="related-topics"></a>Verwandte Themen

[Funktionen von grundlegender Mobilität und Sicherheit](capabilities.md)<br/>
[Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md)