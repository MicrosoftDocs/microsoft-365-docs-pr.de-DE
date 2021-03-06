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
- AdminTemplateSet
search.appverid:
- MET150
description: Richten Sie Basic Mobility and Security ein, um die mobilen Geräte Ihrer Benutzer zu sichern und zu verwalten, indem Sie Aktionen wie das Remotezurücksetzen eines Geräts ausführen.
ms.openlocfilehash: d878569c691fc25c8c91c5a5a29215e6284a5d71
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393283"
---
# <a name="set-up-basic-mobility-and-security"></a>Einrichten von grundlegender Mobilität und Sicherheit

Die integrierte grundlegende Mobilität und Sicherheit für Microsoft 365 hilft Ihnen, die mobilen Geräte von Benutzern wie iPhones, iPads, Androids und Windows Telefone zu schützen und zu verwalten. Sie können Sicherheitsrichtlinien für Geräte erstellen und verwalten, ein Gerät aus der Ferne zurücksetzen und detaillierte Berichte zu Geräten anzeigen.

Haben Sie Fragen? Häufig gestellte Fragen (FAQ) zu allgemeinen Fragen finden Sie unter ["Grundlegende Mobilität und Sicherheit".](frequently-asked-questions.yml) Beachten Sie, dass Sie kein delegiertes Administratorkonto verwenden können, um grundlegende Mobilität und Sicherheit zu verwalten. Weitere Informationen finden Sie unter ["Partner: Delegierte Verwaltung anbieten".](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

Die Geräteverwaltung ist Teil des Security & Compliance Centers, sodass Sie dorthin gehen müssen, um das Setup für grundlegende Mobilität und Sicherheit zu starten.

## <a name="activate-the-basic-mobility-and-security-service"></a>Aktivieren des Basic Mobility and Security-Diensts

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Wechseln Sie zu ["Grundlegende Mobilität und Sicherheit aktivieren".](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Die Aktivierung von Basic Mobility and Security kann einige Zeit in Anspruch nehmen. Nach Abschluss des Vorgangs erhalten Sie eine E-Mail, in der die nächsten Schritte erläutert werden.

## <a name="set-up-mobile-device-management"></a>Einrichten der Verwaltung mobiler Geräte

Wenn der Dienst bereit ist, führen Sie die folgenden Schritte aus, um das Setup abzuschließen.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Schritt 1: (Erforderlich) Konfigurieren von Domänen für grundlegende Mobilität und Sicherheit

Wenn Sie Microsoft 365 keine benutzerdefinierte Domäne zugeordnet haben oder wenn Sie Windows Geräte nicht verwalten, können Sie diesen Abschnitt überspringen. Andernfalls müssen Sie DNS-Einträge für die Domäne bei Ihrem DNS-Host hinzufügen. Wenn Sie die Datensätze bereits im Rahmen der Einrichtung Ihrer Domäne mit Microsoft 365 hinzugefügt haben, sind Sie alle festgelegt. Nachdem Sie die Datensätze hinzugefügt haben, werden Microsoft 365 Benutzer in Ihrer Organisation, die sich auf ihrem Windows Gerät mit einer E-Mail-Adresse anmelden, die Ihre benutzerdefinierte Domäne verwendet, umgeleitet, sich bei Basic Mobility and Security zu registrieren.

Benötigen Sie Hilfe beim Einrichten der Datensätze? Suchen Sie Ihre Domänenregistrierungsstelle, und wählen Sie den Registrierungsstellennamen aus, um zur schrittweisen Hilfe zum Erstellen von DNS-Einträgen in der Liste unter Hinzufügen von [DNS-Einträgen zum Verbinden Ihrer Domäne zu](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)gelangen. Verwenden Sie diese Anweisungen, um CNAME-Einträge zu erstellen, die unter [Vereinfachen Windows Registrierung ohne Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)beschrieben sind.

Nachdem Sie die beiden CNAME-Einträge hinzugefügt haben, wechseln Sie zurück zum Security & Compliance Center, und wechseln Sie zur Geräteverwaltung zur **Verhinderung von Datenverlust,**  >     um den nächsten Schritt abzuschließen.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Schritt 2: (Erforderlich) Konfigurieren eines APNs-Zertifikats für iOS-Geräte

Um iOS-Geräte wie iPad und iPhones zu verwalten, müssen Sie ein APNs-Zertifikat erstellen.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. In Ihrem Browsertyp:  [https://protection.office.com](https://protection.office.com/) .

3. Wählen Sie  **"Geräteverwaltung zur Verhinderung von Datenverlust"**   >  **** aus, und wählen Sie **"APNs-Zertifikat" für iOS-Geräte** aus.

4. Wählen Sie auf der Seite "Apple Push Notification Certificate Einstellungen" die Option **"Weiter"** aus.

5. Wählen Sie **"CSR-Datei herunterladen"**   aus, und speichern Sie die Zertifikatsignierungsanforderung an einer Stelle auf Ihrem Computer, an die Sie sich erinnern werden. Wählen Sie **"Weiter"** aus.

6. Auf der Seite zum Erstellen eines APNs-Zertifikats:

   - Wählen Sie das Apple APNS-Portal aus, um das Apple Push Certificates Portal zu öffnen.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Wählen Sie "Zertifikat erstellen" aus, und akzeptieren Sie die Nutzungsbedingungen.
   - Navigieren Sie zu der Zertifikatsignierungsanforderung, die Sie von Microsoft 365 auf Ihren Computer heruntergeladen haben, und wählen Sie "Upload" aus.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Wechseln Sie zurück zu Microsoft 365, und wählen Sie **"Weiter"** aus.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Wählen Sie  **"Fertig stellen"** aus.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Schritt 3: (Empfohlen) Einrichten der mehrstufigen Authentifizierung

MFA trägt dazu bei, die Anmeldung bei Microsoft 365 für die Registrierung mobiler Geräte zu sichern, indem eine zweite Authentifizierungsform erforderlich ist. Benutzer müssen einen Telefonanruf, eine SMS oder eine App-Benachrichtigung auf ihrem mobilen Gerät bestätigen, nachdem sie ihr Geschäftskontokennwort ordnungsgemäß eingegeben haben. Sie können ihr Gerät erst registrieren, nachdem diese zweite Authentifizierungsform abgeschlossen ist. Nachdem Benutzergeräte in Basic Mobility and Security registriert wurden, können Benutzer nur mit ihrem Geschäftskonto auf Microsoft 365 Ressourcen zugreifen.

Informationen zum Aktivieren von MFA im Azure AD-Portal finden Sie unter Einrichten der [mehrstufigen Authentifizierung.](../security-and-compliance/set-up-multi-factor-authentication.md)

Nachdem Sie MFA eingerichtet haben, wechseln Sie zurück zum Security & Compliance Center, und navigieren Sie zu Geräterichtlinien **zur Verhinderung von Datenverlust,**   >     >  ****   um den nächsten Schritt abzuschließen.

### <a name="step-4-recommended-manage-device-security-policies"></a>Schritt 4: (Empfohlen) Verwalten von Gerätesicherheitsrichtlinien

Der nächste Schritt besteht darin, Gerätesicherheitsrichtlinien zu erstellen und bereitzustellen, um Ihre Microsoft 365 Unternehmensdaten zu schützen. Sie können beispielsweise Datenverluste verhindern, wenn ein Benutzer sein Gerät verliert, indem Sie eine Richtlinie zum Sperren von Geräten nach fünf Minuten Inaktivität erstellen und Geräte nach drei Anmeldefehlern zurücksetzen.

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Microsoft 365 an.

2. Wählen Sie ["Mobile Geräteverwaltung aktivieren" aus.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Wenn der Dienst aktiviert ist, sehen Sie stattdessen die Aktivierungsschritte einen Link zum [Verwalten von Geräten.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Wechseln Sie zu **"Geräterichtlinien".**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits- und Mobilitätsrichtlinieneinstellungen":::

4. Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien, die für Ihre Organisation geeignet sind, und befolgen Sie die Schritte unter [Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security.](create-device-security-policies.md)

> [!TIP]
>
> - Wenn Sie eine neue Richtlinie erstellen, sollten Sie die Richtlinie so festlegen, dass der Zugriff zugelassen und ein Richtlinienverstoß gemeldet wird, wenn ein Benutzergerät nicht mit der Richtlinie kompatibel ist. Dadurch können Sie sehen, wie viele mobile Geräte von der Richtlinie betroffen sind, ohne den Zugriff auf Microsoft 365 zu blockieren.
>
> - Bevor Sie eine neue Richtlinie für alle Benutzer in Ihrer Organisation bereitstellen, empfehlen wir, sie auf den Geräten zu testen, die von einer kleinen Anzahl von Benutzern verwendet werden.
>
> - Informieren Sie Ihre Organisation außerdem vor der Bereitstellung von Richtlinien über die potenziellen Auswirkungen der Registrierung eines Geräts in Basic Mobility and Security. Je nachdem, wie Sie die Richtlinien einrichten, können Geräte, die nicht den Richtlinien entsprechen (nicht kompatible Geräte), am Zugriff auf Microsoft 365 gehindert werden. Auf nicht kompatiblen Geräten sind möglicherweise auch Apps, Fotos und andere persönliche Informationen installiert, die auf einem registrierten Gerät gelöscht werden können, wenn das Gerät gelöscht wird. Weitere Informationen finden Sie unter ["Zurücksetzen eines mobilen Geräts in Basic Mobility and Security".](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Stellen Sie sicher, dass Benutzer ihre Geräte registrieren

Nachdem Sie eine Richtlinie für die Verwaltung mobiler Geräte erstellt und bereitgestellt haben, erhält jeder lizenzierte Microsoft 365 Benutzer in Ihrer Organisation, auf den die Geräterichtlinie angewendet wird, bei der nächsten Anmeldung bei Microsoft 365 von ihrem mobilen Gerät eine Registrierungsnachricht. Sie müssen die Registrierungs- und Aktivierungsschritte abschließen, bevor sie auf Microsoft 365 E-Mails und Dokumente zugreifen können. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Wenn die bevorzugte Sprache eines Benutzers vom Registrierungsprozess nicht unterstützt wird, erhalten Benutzer möglicherweise Registrierungsbenachrichtigungen und Schritte auf ihren mobilen Geräten in einer anderen Sprache. Nicht alle in Microsoft 365 unterstützten Sprachen werden derzeit für den Registrierungsprozess auf mobilen Geräten unterstützt.

Benutzer mit Android- oder iOS-Geräten müssen die Unternehmensportal-App im Rahmen des Registrierungsvorgangs installieren.

## <a name="related-content"></a>Verwandte Inhalte

[Funktionen der grundlegenden Mobilität und Sicherheit](capabilities.md) (Artikel)\
[Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md) (Artikel)