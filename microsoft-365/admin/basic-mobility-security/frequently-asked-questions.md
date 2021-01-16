---
title: Häufig gestellte Fragen (FAQ) zu Grundlegenden Mobilität und Sicherheit
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
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
description: Häufig gestellte Fragen zu Basic Mobility and Security.
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876876"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ) zu Grundlegenden Mobilität und Sicherheit

Dieser Artikel enthält häufig gestellte Fragen zu Basic Mobility and Security, einem Feature, mit dem Sie mobile Geräte in Microsoft 365 verwalten und schützen können. Wenn Sie keine Antwort auf Ihre Frage finden können, teilen Sie uns dies mit, indem Sie einen Kommentar auf der Seite abgeben, damit wir Ihre Frage zu diesem Artikel hinzufügen können.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Wie kann ich grundlegende Mobilität und Sicherheit erhalten? Ich kann sie im Microsoft 365 Admin Center nicht sehen.

1.  Aktivieren Sie "Basic Mobility and Security", indem Sie die [Seite "Office 365 Security & Compliance"](https://protection.office.com/) öffnen.

2.  Wechseln Sie zu "Verhinderung von Datenverlust" > Geräteverwaltung.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Wie kann ich mit der Geräteverwaltung in Basic Mobility and Security beginnen?

Es gibt vier Schritte für die ersten Schritte mit Basic Mobility and Security: 

1. Aktivieren Sie Basic Mobility and Security, indem Sie zum [Office 365 Security & Compliance -Programm gehen.](https://protection.office.com/)

2. Wechseln Sie zu "Verhinderung von Datenverlust" > Geräteverwaltung > Geräterichtlinien.
    
3. Erstellen Sie Geräteverwaltungsrichtlinien, und wenden Sie sie auf Benutzergruppen an, die in Sicherheitsgruppen eingerichtet sind. Es wird empfohlen, mit der Bereitstellung der Richtlinien für eine kleine Testgruppe zu beginnen. Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md).

4. Benutzer, auf die eine Richtlinie angewendet wurde, werden aufgefordert, ihre Geräte zu registrieren, wenn sie versuchen, auf Microsoft 365-Daten zu zugreifen. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).

Weitere Informationen finden Sie unter [Set up Basic Mobility and Security](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Ich versuche, Basic Mobility and Security zu einrichten, aber es scheint hängen geblieben zu sein. Der Microsoft 365 Service Health zeigt seit einer Weile "Bereitstellung" an. Wie gehe ich vor?

Es kann einige Zeit dauern, bis der Dienst für Sie bereit ist. Nach Abschluss der Bereitstellung wird die Seite "Basic Mobility and Security" angezeigt. If you've waited 24 hours and the status is still provisioning, please contact Support and we'll help figure out what the issue is. Supportoptionen finden Sie unter Weitere [Hilfe?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp)

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Was kann ich tun, wenn die Geräteregistrierung fehlschlägt?

Wenn Sie Probleme beim Registrieren eines Geräts haben, überprüfen Sie zunächst Folgendes:

- Stellen Sie sicher, dass das Gerät noch nicht bei einem anderen Anbieter für die Verwaltung mobiler Geräte registriert ist, z. B. Intune.

- Stellen Sie sicher, dass das Gerät auf das richtige Datum und die richtige Uhrzeit festgelegt ist.

- Wechseln Sie auf dem Gerät zu einem anderen WLAN oder Mobilfunknetz.

- Deinstallieren Sie für Android- oder iOS-Geräte die Intune-Unternehmensportal-App auf dem Gerät, und installieren Sie sie erneut.
    
Wenn die Registrierung weiterhin nicht funktioniert, lesen Sie die Informationen zur Problembehandlung für [grundlegende Mobilität und Sicherheit.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Was ist der Unterschied zwischen Intune und Basic Mobility and Security?

Basic Mobility and Security wird vom Dienst Intune gehostet. Es handelt sich um eine Teilmenge der Intune-Dienste, die als zusätzlichen Vorteil für Microsoft 365 bereitgestellt werden, und ist eine integrierte cloudbasierte Lösung zum Verwalten von Geräten in Ihrer Organisation. Einen vergleich der beiden Dienste, die Ihnen bei der Entscheidung helfen, ob die Verwendung von Intune oder Basic Mobility and Security für Microsoft 365 am besten geeignet ist, finden Sie unter ["Wählen](choose-between-basic-mobility-and-security-and-intune.md)zwischen Basic Mobility Security und Intune".

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Wie funktionieren Richtlinien für grundlegende Mobilität und Sicherheit? Wie kann ich sie einrichten? Deaktivieren Sie sie?

Nachdem Sie die Ersteinrichtung für Basic Mobility and Security abgeschlossen haben, erstellen Sie Richtlinien und wenden sie auf Benutzergruppen im Security & Compliance Center an. Richtlinien erfordern, dass Benutzer der Richtlinien ihre Geräte in Basic Mobility and Security registrieren, bevor das Gerät für den Zugriff auf Microsoft 365-Daten verwendet werden kann. Die von Ihnen eingerichteten Richtlinien bestimmen Einstellungen für mobile Geräte, z. B. wie oft Kennwörter zurückgesetzt werden müssen oder ob eine Datenverschlüsselung erforderlich ist. Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien im Basic Mobility and Security](create-device-security-policies.md)und Microsoft   [365 Compliance Center.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

Schrittweise Anweisungen zum Erstellen und Bereitstellen von Geräterichtlinien finden Sie unter Erstellen von Gerätesicherheitsrichtlinien [in Basic Mobility and Security](create-device-security-policies.md).

Wenn Sie eine bestimmte Gruppe von Benutzern von Richtlinien ausschließen möchten, können Sie der Ausschlussgruppe eine Gruppe hinzufügen.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kann ich von Exchange ActiveSync A0 zu Basic Mobility and Security für Microsoft 365 wechseln?

Wenn Sie bereits Exchange ActiveSync für die Verwaltung mobiler Geräte verwenden, können Sie mit der Verwendung von Basic Mobility and Security beginnen, indem Sie die Schritte zum Einrichten von Basic Mobility and Security ausführen. Weitere Informationen finden Sie unter ["Benutzer- und Gerätezugriff schützen"](https://go.microsoft.com/fwlink/?LinkId=615145) und ["Grundlegende Mobilität und Sicherheit einrichten".](set-up.md)

Wenn Sie die in Basic Mobility and Security erstellten Richtlinien auf Benutzergruppen anwenden, setzen diese Richtlinien Exchange ActiveSync Postfachrichtlinien für mobile Geräte und Gerätezugriffsregeln außer Kraft, die Sie zuvor im Exchange Admin Center für diese Benutzer erstellt haben.

Nachdem ein Gerät in Basic Mobility and Security registriert wurde, Exchange ActiveSync auf das Gerät angewendete Postfachrichtlinie oder Gerätezugriffsregel für mobile Geräte ignoriert.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ich habe Basic Mobility and Security eingerichtet, aber jetzt möchte ich es entfernen. Was sind die Schritte?

Leider können Sie die Grundlegende Mobilität und Sicherheit nicht einfach "entsprovisionen", nachdem Sie sie eingerichtet haben. Sie können sie jedoch für Benutzergruppen entfernen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen. Sie können sie auch für alle Benutzer deaktivieren, indem Sie die Geräterichtlinien entfernen, damit sie nicht aktiviert und nicht erzwungen werden. Weitere Informationen finden Sie unter [Deaktivieren von Basic Mobility and Security](turn-off.md).