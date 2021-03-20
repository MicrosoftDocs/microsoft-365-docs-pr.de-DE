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
ms.openlocfilehash: 2f74307d41d83dd2e6fce2b68283ce0966e850e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906240"
---
# <a name="set-up-basic-mobility-and-security"></a>Einrichten von grundlegender Mobilität und Sicherheit

Die integrierte Grundlegende Mobilität und Sicherheit für Microsoft 365 hilft Ihnen, mobile Geräte wie iPhones, iPads, Androids und Windows-Telefone zu sichern und zu verwalten. Sie können Sicherheitsrichtlinien für Geräte erstellen und verwalten, ein Gerät aus der Ferne zurücksetzen und detaillierte Berichte zu Geräten anzeigen.

Haben Sie Fragen? Häufig gestellte Fragen (FAQ) finden Sie unter [Basic Mobility and Security Frequently-asked questions (FAQ).](frequently-asked-questions.md) Beachten Sie, dass Sie kein delegiertes Administratorkonto zum Verwalten der grundlegenden Mobilität und Sicherheit verwenden können. Weitere Informationen finden Sie unter [Partner: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

Die Geräteverwaltung ist Teil des Security & Compliance Center, daher müssen Sie dort hingehen, um das Grundlegende Einrichten von Mobilität und Sicherheit zu starten.

## <a name="activate-the-basic-mobility-and-security-service"></a>Aktivieren des Grundlegenden Mobilitäts- und Sicherheitsdiensts

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Wechseln Sie [zu Grundlegende Mobilität und Sicherheit aktivieren.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Es kann einige Zeit dauern, die Grundlegende Mobilität und Sicherheit zu aktivieren. Nach Abschluss des Schritts erhalten Sie eine E-Mail, in der die nächsten Schritte erläutert werden.

## <a name="set-up-mobile-device-management"></a>Einrichten der Verwaltung mobiler Geräte

Wenn der Dienst bereit ist, führen Sie die folgenden Schritte aus, um das Setup abzuschließen.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Schritt 1: (Erforderlich) Konfigurieren von Domänen für grundlegende Mobilität und Sicherheit

Wenn Microsoft 365 keine benutzerdefinierte Domäne zugeordnet ist oder Sie keine Windows-Geräte verwalten, können Sie diesen Abschnitt überspringen. Andernfalls müssen Sie auf Ihrem DNS-Host DNS-Einträge für die Domäne hinzufügen. Wenn Sie die Datensätze bereits hinzugefügt haben, sind Sie alle im Rahmen der Einrichtung Ihrer Domäne mit Microsoft 365 festgelegt. Nachdem Sie die Datensätze hinzugefügt haben, werden Microsoft 365-Benutzer in Ihrer Organisation, die sich auf ihrem Windows-Gerät mit einer E-Mail-Adresse anmelden, die Ihre benutzerdefinierte Domäne verwendet, umgeleitet, um sich bei Basic Mobility and Security zu registrieren.

Benötigen Sie Hilfe beim Einrichten der Datensätze? Suchen Sie nach Ihrer Domänenregistrierungsstelle, und wählen Sie den Registrierungsstellennamen aus, um schritt-für-Schritt-Hilfe zum Erstellen eines DNS-Eintrags in der Liste unter Hinzufügen von DNS-Einträgen zum Verbinden Ihrer [Domäne zu wechseln.](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Verwenden Sie diese Anweisungen, um #A0 zu erstellen, die unter Vereinfachen der [#A1 ohne Azure AD Premium beschrieben werden.](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

Nachdem Sie die beiden & hinzugefügt haben, wechseln Sie zurück zum Security & Compliance Center, und wechseln Sie zu Verhinderung von Datenverlust Geräteverwaltung, um den  >     nächsten Schritt zu machen.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Schritt 2: (Erforderlich) Konfigurieren eines APNs-Zertifikats für iOS-Geräte

Zum Verwalten von iOS-Geräten wie iPad und iPhones müssen Sie ein APNs-Zertifikat erstellen.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. In Ihrem Browsertyp:  [https://protection.office.com](https://protection.office.com/) .

3. Wählen  **Sie Verhinderung von Datenverlust**   >  **Geräteverwaltung** aus, und wählen Sie **APNs-Zertifikat für iOS-Geräte aus.**

4. Wählen Sie auf der Seite Apple Push Notification Certificate Settings die Option **Weiter aus.**

5. Wählen **Sie Csr-Datei herunterladen aus,** und speichern Sie die Zertifikatsignieranforderung an einem Ort auf Ihrem Computer, den   Sie sich merken werden. Wählen Sie **Weiter** aus.

6. Auf der Seite ApNs-Zertifikat erstellen:

   - Wählen Sie Apple APNS Portal aus, um das Apple Push Certificates Portal zu öffnen.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Wählen Sie Zertifikat erstellen aus, und akzeptieren Sie die Nutzungsbedingungen.
   - Navigieren Sie zur Zertifikatsignieranforderung, die Sie von Microsoft 365 auf Ihren Computer heruntergeladen haben, und wählenUpload aus.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Wechseln Sie zurück zu Microsoft 365, und wählen Sie **Weiter aus.**

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Wählen Sie  **Fertig stellen** aus.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Schritt 3: (Empfohlen) Einrichten der mehrstufigen Authentifizierung

MFA trägt dazu bei, die Anmeldung bei Microsoft 365 für die Registrierung mobiler Geräte zu sichern, indem eine zweite Form der Authentifizierung erforderlich ist. Benutzer müssen einen Anruf, eine SMS oder eine App-Benachrichtigung auf ihrem mobilen Gerät bestätigen, nachdem sie ihr Kennwort für das Arbeitskonto richtig eingegeben haben. Sie können ihr Gerät erst registrieren, nachdem diese zweite Authentifizierungsform abgeschlossen ist. Nachdem Benutzergeräte in Basic Mobility and Security registriert wurden, können Benutzer nur mit ihrem Arbeitskonto auf Microsoft 365-Ressourcen zugreifen.

Informationen zum Aktivieren von MFA im Azure AD-Portal finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md).

Nachdem Sie MFA eingerichtet haben, wechseln Sie zum Security ****& Compliance Center, und navigieren Sie zu Verhinderung von Datenverlust Geräteverwaltung Geräterichtlinien, um den   >     >  ****   nächsten Schritt zu abschließen.

### <a name="step-4-recommended-manage-device-security-policies"></a>Schritt 4: (Empfohlen) Verwalten von Gerätesicherheitsrichtlinien

Der nächste Schritt besteht im Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien zum Schutz Ihrer Microsoft 365-Organisationsdaten. Beispielsweise können Sie Datenverluste verhindern, wenn ein Benutzer sein Gerät verliert, indem Sie eine Richtlinie zum Sperren von Geräten nach fünf Minuten Inaktivität erstellen und Geräte nach drei Anmeldefehlern löschen.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Wählen [Sie Mobile Geräteverwaltung aktivieren aus.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Wenn der Dienst aktiviert ist, werden stattdessen die Aktivierungsschritte mit einem Link zum [Verwalten von Geräten angezeigt.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Wechseln Sie zu **Geräterichtlinien**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits- und Mobilitätsrichtlinieneinstellungen":::

4. Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien für Ihre Organisation entsprechend den Schritten unter Erstellen von Gerätesicherheitsrichtlinien [in Basic Mobility and Security](create-device-security-policies.md).

> [!TIP]
>
> - Wenn Sie eine neue Richtlinie erstellen, sollten Sie die Richtlinie so festlegen, dass Sie Zugriff auf Richtlinienverletzungen zulassen und diese melden, wenn ein Benutzergerät nicht mit der Richtlinie kompatibel ist. Dadurch können Sie sehen, wie viele mobile Geräte von der Richtlinie betroffen sind, ohne den Zugriff auf Microsoft 365 zu blockieren.
>
> - Bevor Sie eine neue Richtlinie für alle Benutzer in Ihrer Organisation bereitstellen, wird empfohlen, sie auf den Geräten zu testen, die von einer kleinen Anzahl von Benutzern verwendet werden.
>
> - Teilen Sie Ihrer Organisation außerdem vor der Bereitstellung von Richtlinien die potenziellen Auswirkungen der Registrierung eines Geräts in Basic Mobility and Security mit. Je nachdem, wie Sie die Richtlinien einrichten, können Geräte, die nicht den Richtlinien entsprechen (nicht kompatible Geräte), der Zugriff auf Microsoft 365 blockiert werden. Auf nicht kompatiblen Geräten sind möglicherweise auch Apps, Fotos und andere persönliche Informationen installiert, die auf einem registrierten Gerät gelöscht werden können, wenn das Gerät gelöscht wird. Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Sicherstellen, dass Benutzer ihre Geräte registrieren

Nachdem Sie eine Verwaltungsrichtlinie für mobile Geräte erstellt und bereitgestellt haben, erhält jeder lizenzierte Microsoft 365-Benutzer in Ihrer Organisation, den die Geräterichtlinie angewendet hat, eine Registrierungsnachricht, sobald er sich das nächste Mal von seinem mobilen Gerät bei Microsoft 365 anmeldet. Sie müssen die Registrierungs- und Aktivierungsschritte ausführen, bevor sie auf Microsoft 365-E-Mails und -Dokumente zugreifen können. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md).

> [!IMPORTANT]
> Wenn die bevorzugte Sprache eines Benutzers vom Registrierungsprozess nicht unterstützt wird, erhalten Benutzer möglicherweise Registrierungsbenachrichtigungen und Schritte auf ihren mobilen Geräten in einer anderen Sprache. Nicht alle in Microsoft 365 unterstützten Sprachen werden derzeit für den Registrierungsprozess auf mobilen Geräten unterstützt.

Benutzer mit Android- oder iOS-Geräten müssen die Unternehmensportal-App im Rahmen des Registrierungsprozesses installieren.

## <a name="related-topics"></a>Verwandte Themen

[Funktionen von grundlegender Mobilität und Sicherheit](capabilities.md)<br/>
[Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md)