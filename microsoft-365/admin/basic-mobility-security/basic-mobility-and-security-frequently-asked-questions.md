---
title: Grundlegende Mobilitäts-und Sicherheits häufig gestellte Fragen (FAQ)
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
description: Häufig gestellte Fragen zu grundlegender Mobilität und Sicherheit.
ms.openlocfilehash: a79b7df53f717d511603ec57e09ce4d6c523d14d
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336914"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Grundlegende Mobilitäts-und Sicherheits häufig gestellte Fragen (FAQ)

Dieser Artikel enthält häufig gestellte Fragen zu grundlegender Mobilität und Sicherheit, ein Feature, mit dem Sie mobile Geräte in Microsoft 365 verwalten und sichern können. Wenn Sie keine Antwort auf Ihre Frage finden, lassen Sie es uns wissen, indem Sie einen Kommentar auf der Seite hinterlassen, damit wir Ihre Frage zu diesem Artikel hinzufügen können.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Wie kann ich grundlegende Mobilität und Sicherheit erhalten? Ich sehe ihn nicht im Microsoft 365 Admin Center

1.  Aktivieren Sie die grundlegende Mobilität und Sicherheit, indem Sie auf die Seite [Office 365 Security & Compliance](https://protection.office.com/) wechseln.   

2.  Wechseln Sie zur Verhinderung von Datenverlust > Geräteverwaltung.   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Wie kann ich mit der Geräteverwaltung in Basic Mobility and Security beginnen?

Es gibt vier Schritte für die ersten Schritte mit grundlegender Mobilität und Sicherheit: 

1. Aktivieren Sie die grundlegende Mobilität und Sicherheit, indem Sie zur [Office 365 Security & Compliance](https://protection.office.com/)wechseln.
    
2. Wechseln Sie zu Verhinderung von Datenverlust > Geräteverwaltung > Geräterichtlinien.
    
3. Erstellen Sie Geräteverwaltungsrichtlinien, und wenden Sie diese auf Benutzergruppen an, die in Sicherheitsgruppen eingerichtet sind. Es wird empfohlen, zunächst die Richtlinien für eine kleine Testgruppe bereitzustellen. Weitere Informationen finden Sie unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md).      

4. Benutzer, denen eine Richtlinie zugewiesen wurde, werden aufgefordert, Ihre Geräte zu registrieren, wenn Sie versuchen, auf Microsoft 365-Daten zuzugreifen. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md).

Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up-basic-mobility-and-security.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Ich versuche, grundlegende Mobilitäts-und Sicherheitseinstellungen einzurichten, aber es scheint nicht mehr möglich zu sein. Die Microsoft 365-Dienst Integrität zeigt seit einiger Zeit "Prothesen". Wie gehe ich vor?

Es kann einige Zeit dauern, bis der Dienst für Sie verfügbar ist. Wenn die Einrichtung abgeschlossen ist, wird die Seite Mobile Geräteverwaltung für Microsoft 365 angezeigt. Wenn Sie 24 Stunden gewartet haben und der Status noch nicht zur Verfügung steht, wenden Sie sich an den Support, damit wir herausfinden, was das Problem ist. Supportoptionen finden Sie unter [noch benötigen Sie Hilfe?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Was kann ich tun, wenn die Geräteregistrierung fehlschlägt?

Wenn Sie Probleme beim Abrufen eines Geräts haben, überprüfen Sie zunächst Folgendes:

- Stellen Sie sicher, dass das Gerät nicht bereits mit einem anderen Anbieter für die Verwaltung mobiler Geräte wie InTune registriert ist.
    
- Stellen Sie sicher, dass das Gerät auf das richtige Datum und die korrekte Uhrzeit festgelegt ist.
    
- Wechseln Sie zu einem anderen WLAN-oder Mobilfunknetz auf dem Gerät.
    
- Für Android-oder IOS-Geräte deinstallieren Sie die Intune-Unternehmens Portal-App auf dem Gerät, und installieren Sie Sie erneut.
    
Wenn die Registrierung immer noch nicht funktioniert, finden Sie weitere Informationen unter [Troubleshoot Basic Mobility and Security](troubleshoot-basic-mobility-and-security.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Worin besteht der Unterschied zwischen InTune und grundlegender Mobilität und Sicherheit?

Grundlegende Mobilität und Sicherheit werden vom InTune-Dienst gehostet. Es handelt sich um eine Teilmenge von InTune-Diensten, die als zusätzlicher Vorteil für Microsoft 365 bereitgestellt werden, und ist eine integrierte Cloud-basierte Lösung für die Verwaltung von Geräten in Ihrer Organisation. Für einen nebeneinander Vergleich der beiden Dienste, der Ihnen bei der Entscheidung helfen soll, ob die Verwendung von InTune oder grundlegender Mobilität und Sicherheit für Microsoft 365 am besten geeignet ist, finden Sie unter [choose from Basic Mobility Security and InTune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Wie funktionieren Richtlinien für einfache Mobilität und Sicherheit? Wie richte ich Sie ein? Deaktivieren?

Nachdem Sie das anfängliche Setup für grundlegende Mobilität und Sicherheit abgeschlossen haben, erstellen Sie Richtlinien und wenden diese auf Benutzergruppen im Security & Compliance Center an. Richtlinien erfordern, dass Benutzer der Richtlinien Ihre Geräte in grundlegender Mobilität und Sicherheit registrieren, bevor das Gerät für den Zugriff auf Microsoft 365-Daten verwendet werden kann. Die Richtlinien, die Sie einrichten, bestimmen Einstellungen für mobile Geräte, beispielsweise wie häufig Kennwörter zurückgesetzt werden müssen oder ob eine Datenverschlüsselung erforderlich ist. Weitere Informationen finden Sie unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md)   und [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Eine Schritt-für-Schritt-Anleitung zum Erstellen und Bereitstellen von Geräterichtlinien finden Sie unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies-in-basic-mmobility-and-security.md).

Wenn Sie eine bestimmte Gruppe von Benutzern davon ausschließen möchten, dass Sie von den Richtlinien betroffen sind, können Sie der Ausschlussgruppe eine Gruppe hinzufügen.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Kann ich von der Exchange ActiveSync-Geräteverwaltung zu grundlegender Mobilität und Sicherheit für Microsoft 365 wechseln?

Wenn Sie bereits Exchange ActiveSync-Richtlinien zum Verwalten von mobilen Geräten verwenden, können Sie mit der Verwendung von Basic Mobility and Security beginnen, indem Sie die Schritte zum Einrichten von Basic Mobility and Security ausführen. Weitere Informationen finden Sie unter [Schützen des Benutzer-und Gerätezugriffs](https://go.microsoft.com/fwlink/?LinkId=615145) und Einrichten von grundlegender [Mobilität und Sicherheit](set-up-basic-mobility-and-security.md).

Wenn Sie die Richtlinien, die Sie in grundlegender Mobilität und Sicherheit erstellen, auf Benutzergruppen anwenden, setzen diese Richtlinien die Postfachrichtlinien für mobile Geräte von Exchange ActiveSync und Gerätezugriffsregeln außer Kraft, die Sie zuvor im Exchange Admin Center für diese Benutzer erstellt haben.

Nachdem ein Gerät in Basic Mobility and Security registriert wurde, werden alle Exchange ActiveSync-Postfachrichtlinien für mobile Geräte oder Gerätezugriffsregeln, die auf das Gerät angewendet werden, ignoriert.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ich habe grundlegende Mobilität und Sicherheit eingerichtet, aber jetzt möchte ich Sie entfernen. Was sind die Schritte?

Leider können Sie die grundlegende Mobilität und Sicherheit nicht einfach "aufheben", nachdem Sie Sie eingerichtet haben. Sie können Sie jedoch für Benutzergruppen entfernen, indem Sie Benutzersicherheitsgruppen aus den von Ihnen erstellten Geräterichtlinien entfernen. Sie können es auch für alle Benutzer deaktivieren, indem Sie die Geräterichtlinien entfernen, damit Sie nicht vorhanden sind und nicht erzwungen werden. Weitere Informationen finden Sie unter [Deaktivieren von Basic Mobility and Security](turn-off-basic-mobility-and-security.md).

