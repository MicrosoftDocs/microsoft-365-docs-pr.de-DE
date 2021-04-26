---
title: Häufig gestellte Fragen zu Grundlegenden Fragen zu Mobilität und Sicherheit (FAQ)
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
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023893"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Häufig gestellte Fragen zu Grundlegenden Fragen zu Mobilität und Sicherheit (FAQ)

Dieser Artikel enthält häufig gestellte Fragen zu Basic Mobility and Security, einem Feature, mit dem Sie mobile Geräte in Microsoft 365 verwalten und sichern können. Wenn Sie keine Antwort auf Ihre Frage finden, teilen Sie uns dies mit, indem Sie einen Kommentar auf der Seite lassen, damit wir Ihre Frage zu diesem Artikel hinzufügen können.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Wie kann ich grundlegende Mobilität und Sicherheit erhalten? Ich kann es nicht im Microsoft 365 Admin Center sehen

1.  Aktivieren Sie Grundlegende Mobilität und Sicherheit, indem Sie zur [Seite Office 365 Security & Compliance](https://protection.office.com/) gelangen.

2.  Wechseln Sie zu Verhinderung von Datenverlust > Geräteverwaltung.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Wie kann ich mit der Geräteverwaltung in Basic Mobility and Security beginnen?

Es gibt vier Schritte für die ersten Schritte mit Basic Mobility and Security: 

1. Aktivieren Sie Grundlegende Mobilität und Sicherheit, indem Sie zu [Office 365 Security & Compliance gehen.](https://protection.office.com/)

2. Wechseln Sie zu Verhinderung von Datenverlust > Geräteverwaltung > Geräterichtlinien.
    
3. Erstellen Sie Geräteverwaltungsrichtlinien, und wenden Sie sie auf Benutzergruppen an, die in Sicherheitsgruppen eingerichtet sind. Es wird empfohlen, mit der Bereitstellung der Richtlinien in einer kleinen Testgruppe zu beginnen. Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md).

4. Benutzer, auf die eine Richtlinie angewendet wurde, werden aufgefordert, ihre Geräte zu registrieren, wenn sie versuchen, auf Microsoft 365-Daten zu zugreifen. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md).

Weitere Informationen finden Sie unter [Set up Basic Mobility and Security](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Ich versuche, grundlegende Mobilität und Sicherheit zu einrichten, aber es scheint hängen geblieben zu sein. Der Microsoft 365 Service Health zeigt seit einer Weile "Bereitstellung" an. Wie gehe ich vor?

Es kann einige Zeit dauern, bis der Dienst für Sie bereit ist. Nach Abschluss der Bereitstellung wird die Seite Grundlegende Mobilität und Sicherheit angezeigt. Wenn Sie 24 Stunden gewartet haben und der Status weiterhin bereitgestellt wird, wenden Sie sich bitte an den Support, und wir helfen Ihnen, herauszufinden, was das Problem ist.

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Was kann ich tun, wenn die Geräteregistrierung fehlschlägt?

Wenn Sie Probleme beim Registrieren eines Geräts haben, überprüfen Sie zunächst Folgendes:

- Stellen Sie sicher, dass das Gerät noch nicht bei einem anderen Anbieter für die Verwaltung mobiler Geräte registriert ist, z. B. Intune.

- Stellen Sie sicher, dass das Gerät auf das richtige Datum und die richtige Uhrzeit festgelegt ist.

- Wechseln Sie zu einem anderen WLAN oder Mobilfunknetzwerk auf dem Gerät.

- Deinstallieren und installieren Sie für Android- oder iOS-Geräte die Intune Company Portal-App auf dem Gerät.
    
Wenn die Registrierung weiterhin nicht funktioniert, finden Sie weitere Informationen unter [Troubleshoot Basic Mobility and Security](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Was ist der Unterschied zwischen Intune und Basic Mobility and Security?

Grundlegende Mobilität und Sicherheit werden vom Intune-Dienst gehostet. Es handelt sich um eine Teilmenge der Intune-Dienste, die als zusätzlichen Vorteil für Microsoft 365 bereitgestellt werden, und ist eine integrierte cloudbasierte Lösung zum Verwalten von Geräten in Ihrer Organisation. Einen vergleich der beiden Dienste, die Ihnen bei der Entscheidung helfen, ob die Verwendung von Intune oder Basic Mobility and Security für Microsoft 365 am besten geeignet ist, finden Sie unter [Choose between Basic Mobility Security and Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Wie funktionieren Richtlinien für grundlegende Mobilität und Sicherheit? Wie kann ich sie einrichten? Deaktivieren Sie sie?

Nachdem Sie die Ersteinrichtung für Grundlegende Mobilität und Sicherheit abgeschlossen haben, erstellen Sie Richtlinien und wenden sie auf Benutzergruppen im Security & Compliance Center an. Richtlinien erfordern, dass Benutzer der Richtlinien ihre Geräte in Basic Mobility and Security registrieren, bevor das Gerät für den Zugriff auf Microsoft 365-Daten verwendet werden kann. Die von Ihnen eingerichteten Richtlinien bestimmen Einstellungen für mobile Geräte, z. B. wie oft Kennwörter zurückgesetzt werden müssen oder ob Datenverschlüsselung erforderlich ist. Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md)und Microsoft   [365 Compliance Center](../../compliance/microsoft-365-compliance-center.md).

Schrittweise Anweisungen zum Erstellen und Bereitstellen von Geräterichtlinien finden Sie unter [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).

Wenn Sie ausschließen möchten, dass eine bestimmte Gruppe von Benutzern von Richtlinien betroffen ist, können Sie der Ausschlussgruppe eine Gruppe hinzufügen.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kann ich von Exchange ActiveSync zu Basic Mobility and Security für Microsoft 365 wechseln?

Wenn Sie bereits Exchange ActiveSync richtlinien zum Verwalten mobiler Geräte verwenden, können Sie mit der Verwendung von Basic Mobility and Security beginnen, indem Sie die Schritte zum Einrichten von Basic Mobility and Security ausführen. Weitere Informationen finden Sie unter [Schützen des Benutzer- und Gerätezugriffs](../../compliance/protect-access-to-data-and-services.md) und [einrichten von Basic Mobility and Security](set-up.md).

Wenn Sie die in Basic Mobility and Security erstellten Richtlinien auf Benutzergruppen anwenden, setzen diese Richtlinien Exchange ActiveSync Postfachrichtlinien für mobile Geräte und Gerätezugriffsregeln außer Kraft, die Sie zuvor im Exchange Admin Center für diese Benutzer erstellt haben.

Nachdem ein Gerät in Basic Mobility and Security registriert wurde, werden Exchange ActiveSync Postfachrichtlinie oder Gerätezugriffsregel für mobile Geräte ignoriert, die auf das Gerät angewendet wurde.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ich habe Grundlegende Mobilität und Sicherheit eingerichtet, aber jetzt möchte ich es entfernen. Was sind die Schritte?

Leider können Sie grundlegende Mobilität und Sicherheit nach der Einrichtung nicht einfach "unprovision". Sie können sie jedoch für Benutzergruppen entfernen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen. Sie können sie auch für alle Benutzer deaktivieren, indem Sie die Geräterichtlinien entfernen, damit sie nicht installiert sind und nicht erzwungen werden. Weitere Informationen finden Sie unter [Deaktivieren von Basic Mobility and Security](turn-off.md).