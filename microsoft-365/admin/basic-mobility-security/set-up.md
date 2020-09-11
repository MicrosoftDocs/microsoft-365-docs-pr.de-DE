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
description: Richten Sie grundlegende Mobilität und Sicherheit ein, um die mobilen Geräte ihrer Benutzer zu sichern und zu verwalten.
ms.openlocfilehash: cb010668d95e51edfbc913caa308ddd830d674e2
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430178"
---
# <a name="set-up-basic-mobility-and-security"></a>Einrichten von grundlegender Mobilität und Sicherheit

Die integrierte grundlegende Mobilität und Sicherheit für Microsoft 365 hilft Ihnen, Mobile Geräte von Benutzern wie iPhones, iPads, Androiden und Windows phones zu sichern und zu verwalten. Sie können Sicherheitsrichtlinien für Geräte erstellen und verwalten, ein Gerät aus der Ferne zurücksetzen und detaillierte Berichte zu Geräten anzeigen.

Haben Sie Fragen? Eine FAQ zur Behandlung häufig gestellter Fragen finden Sie unter [Basic Mobility and Security Frequently Asked Questions (FAQ)](frequently-asked-questions.md). Beachten Sie, dass Sie kein delegiertes Administratorkonto zum Verwalten von grundlegender Mobilität und Sicherheit verwenden können. Weitere Informationen finden Sie unter [Partner: Angebot Delegierte Verwaltung](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

Die Geräteverwaltung ist Teil des Security & Compliance Centers, sodass Sie dorthin gehen müssen, um das MDM-Setup zu starten.

## <a name="activate-the-basic-mobility-and-security-service"></a>Aktivieren des grundlegenden Mobilitäts-und Sicherheitsdiensts

1. Melden Sie sich bei Microsoft 365 mit ihrem globalen Administratorkonto an.
    

2. Wechseln Sie zu [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).
    
    Es kann einige Zeit dauern, bis die grundlegende Mobilität und Sicherheit aktiviert ist. Nach Abschluss dieses Vorgangs erhalten Sie eine e-Mail, in der die nächsten Schritte erläutert werden.

## <a name="set-up-mobile-device-management"></a>Einrichten der Verwaltung mobiler Geräte

Wenn der Dienst fertig ist, führen Sie die folgenden Schritte aus, um das Setup abzuschließen.

### <a name="step-1-required-configure-domains-for-mdm"></a>Schritt 1: (erforderlich) Konfigurieren von Domänen für MDM

Wenn Sie keine benutzerdefinierte Domäne haben, die Microsoft 365 zugeordnet ist, oder wenn Sie keine Windows-Geräte verwalten, können Sie diesen Abschnitt überspringen. Andernfalls müssen Sie DNS-Einträge für die Domäne auf Ihrem DNS-Host hinzufügen. Wenn Sie die Datensätze bereits hinzugefügt haben, sind Sie im Rahmen der Einrichtung Ihrer Domäne mit Microsoft 365 festgelegt. Nachdem Sie die Datensätze hinzugefügt haben, werden Microsoft 365-Benutzer in Ihrer Organisation, die sich auf Ihrem Windows-Gerät mit einer e-Mail-Adresse anmelden, die Ihre benutzerdefinierte Domäne verwendet, zur Registrierung für Basic Mobility and Security umgeleitet.

Benötigen Sie Hilfe beim Einrichten der Datensätze? Suchen Sie Ihre Domänenregistrierungsstelle, und wählen Sie den Namen der Registrierungsstelle aus, um zur schrittweisen Hilfe zum Erstellen von DNS-Einträgen in der Liste unter [Add DNS Records to connect your Domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)zu gelangen. Verwenden Sie diese Anweisungen zum Erstellen von CNAME-Einträgen, die unter [vereinfachen der Windows-Registrierung ohne Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)beschrieben werden.

Nachdem Sie die beiden CNAME-Einträge hinzugefügt haben, kehren Sie zum Security & Compliance Center zurück, und gehen Sie zu **Datenverlust Prevention**-  >  **Geräteverwaltung**,   um den nächsten Schritt abzuschließen.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Schritt 2: (erforderlich) Konfigurieren eines APNs-Zertifikats für IOS-Geräte

Um IOS-Geräte wie iPad und iPhones zu verwalten, müssen Sie ein APNs-Zertifikat erstellen.

1. Melden Sie sich bei Microsoft 365 mit ihrem globalen Administratorkonto an.   

2. Geben Sie im Browsertyp Folgendes ein:  [https://protection.office.com](https://protection.office.com/) .  

3. Wählen Sie **Data Loss Prevention**   >  **Device Management**aus, und wählen Sie **APNs-Zertifikat für IOS-Geräte**aus.   

4. Klicken Sie auf der Seite Einstellungen für den Apple Push Notification-Zertifikat auf **weiter**.  

5. Wählen Sie **Download your CSR File**aus,   und speichern Sie die Zertifikatsignaturanforderung an einer beliebigen Stelle auf Ihrem Computer, an der Sie sich erinnern. Wählen Sie **weiter**aus.
    
6. Auf der Seite APNs-Zertifikat erstellen:
    
    - Wählen Sie Apple APNS Portal aus, um das Apple Push Certificates-Portal zu öffnen.
    - Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    - Wählen Sie Zertifikat erstellen aus, und akzeptieren Sie die Nutzungsbedingungen.
    
    - Browseto die Zertifikatsignaturanforderung, die Sie von Microsoft 365 und selectUpload auf Ihren Computer heruntergeladen haben.
    
    - Download beginntThe APN-Zertifikat, das vom Apple Push Certificate Portal auf Ihrem Computer erstellt wurde.

    >[!TIP]
    >If you're having trouble downloading the certificate, refresh your browser.

7. Wechseln Sie zurück zu Microsoft 365, und wählen Sie **weiter**aus.   

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.   

9. Wählen Sie  **Fertig stellen**aus.  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Schritt 3: (empfohlen) Einrichten der mehrstufigen Authentifizierung

MFA unterstützt das Anmelden bei Microsoft 365 für die Registrierung mobiler Geräte, indem eine zweite Form der Authentifizierung erforderlich ist. Benutzer müssen nach der korrekten Eingabe Ihres Arbeitskonto Kennworts einen Telefonanruf, eine Textnachricht oder eine APP-Benachrichtigung auf Ihrem mobilen Gerät bestätigen. Sie können Ihr Gerät erst registrieren, nachdem diese zweite Authentifizierungsform abgeschlossen ist. Nachdem Benutzer Geräte in Basic Mobility and Security registriert wurden, können Benutzer nur über Ihr Arbeitskonto auf Microsoft 365-Ressourcen zugreifen.

Informationen zum Aktivieren von MFA im Azure AD-Portal finden Sie unter [Einrichten der mehrstufigen Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=519255).

Nachdem Sie MFA eingerichtet haben, kehren Sie zum Security & Compliance Center zurück, und navigieren Sie zu **Data Loss Prevention**   >  **Device Management**   >  **Device Policies**,   um den nächsten Schritt abzuschließen.

### <a name="step-4-recommended-manage-device-security-policies"></a>Schritt 4: (empfohlen) Verwalten von Gerätesicherheitsrichtlinien

Der nächste Schritt ist das Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien, die zum Schutz Ihrer Microsoft 365-Organisationsdaten beitragen. Sie können beispielsweise dazu beitragen, Datenverluste zu vermeiden, wenn ein Benutzer sein Gerät verliert, indem er eine Richtlinie zum Sperren von Geräten nach fünf Minuten Inaktivität und Abwischen von Geräten nach drei Anmeldefehlern erstellt.

1. Melden Sie sich bei Microsoft 365 mit ihrem globalen Administratorkonto an. 

2. Wählen Sie [Mobile Geräteverwaltung aktivieren](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)aus. Wenn der Dienst aktiviert ist, wird anstelle der Aktivierungsschritte ein Link zum Verwalten von [Geräten](https://admin.microsoft.com/adminportal/home#/MifoDevices)angezeigt   .
    
3. Wechseln Sie zu **Geräterichtlinien**.

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Sicherheits-und mobilitätsrichtlinien Einstellungen":::

4. Erstellen und Bereitstellen von für Ihre Organisation geeigneten Gerätesicherheitsrichtlinien, indem Sie die Schritte unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies.md)ausführen.

>[!TIP]
    - Wenn Sie eine neue Richtlinie erstellen, möchten Sie möglicherweise festlegen, dass die Richtlinie Zugriffs-und Richtlinienverstöße zulässt, bei denen ein Benutzergerät nicht mit der Richtlinie konform ist. Auf diese Weise können Sie sehen, wie viele mobile Geräte von der Richtlinie betroffen sind, ohne den Zugriff auf Microsoft 365 zu blockieren.<br/>– Bevor Sie eine neue Richtlinie für alle Benutzer in Ihrer Organisation bereitstellen, sollten Sie Sie auf den Geräten testen, die von einer kleinen Anzahl von Benutzern verwendet werden.<br/>– Informieren Sie Ihre Organisation vor dem Bereitstellen von Richtlinien darüber, welche potenziellen Auswirkungen das Registrieren eines Geräts in grundlegende Mobilität und Sicherheit haben kann. Je nachdem, wie Sie die Richtlinien einrichten, können Geräte, die nicht den Richtlinien entsprechen (nicht konforme Geräte), den Zugriff auf Microsoft 365 sperren. Für nicht konforme Geräte sind möglicherweise auch apps installiert, Fotos und andere persönliche Informationen, die auf einem registrierten Gerät gelöscht werden können, wenn das Gerät gelöscht wird. Weitere Informationen finden Sie unter [wischen eines mobilen Geräts in Basic Mobility and Security](wipe-mobile-device.md).
    
## <a name="make-sure-users-enroll-their-devices"></a>Sicherstellen, dass Benutzer ihre Geräte registrieren

Nachdem Sie eine Richtlinie für die Verwaltung mobiler Geräte erstellt und bereitgestellt haben, erhält jeder lizenzierte Microsoft 365-Benutzer in Ihrer Organisation, auf den die Geräterichtlinie angewendet wird, eine Registrierungsnachricht, wenn Sie sich das nächste Mal bei Microsoft 365 von Ihrem mobilen Gerät aus anmelden. Sie müssen die Registrierungs-und Aktivierungsschritte abschließen, bevor Sie auf Microsoft 365-e-Mails und-Dokumente zugreifen können. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).

>[!IMPORTANT]
>Wenn die bevorzugte Sprache eines Benutzers vom Registrierungsvorgang nicht unterstützt wird, erhalten Benutzer möglicherweise Registrierungs Benachrichtigungen und Schritte auf Ihren mobilen Geräten in einer anderen Sprache. Nicht alle in Microsoft 365 unterstützten Sprachen werden derzeit für den Registrierungsprozess auf mobilen Geräten unterstützt.

Benutzer mit Android-oder IOS-Geräten sind erforderlich, um die Unternehmens Portal-App im Rahmen des Registrierungsprozesses zu installieren.

## <a name="related-topics"></a>Verwandte Themen

[Funktionen der grundlegenden Mobilität und Sicherheit](capabilities.md)<br/>
[Erstellen von Gerätesicherheitsrichtlinien in grundlegender Mobilität und Sicherheit](create-device-security-policies.md)