---
title: 'Phase 5: Verwaltung mobiler Geräte'
description: Microsoft 365 Enterprise umfasst die Verwaltung von mobilen Geräten mit Microsoft Intune. Überprüfen Sie die Anforderungen und Voraussetzungen, richten Sie Intune Ihrer Azure Active Directory-Ressource verwenden, registrieren iOS, Mac OS, Android und Windows-Geräten, erstellen Sie ein Profil konfigurieren, verwenden Sie eine Compliance-Richtlinie und Aktivieren des bedingten Zugriffs für Mobile Bereitstellen von apps Gerätemanagement mit Microsoft 365 Enterprise.
keywords: Microsoft 365 Microsoft 365 Enterprise Microsoft 365 Dokumentation, Verwaltung von mobilen Geräten, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 3afc28f0d21918c027a6a1622a40318e333f7ab4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868216"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Phase 5: Verwaltung von mobilen Geräten für Microsoft 365 Enterprise.

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Dieses Feature gilt für die E3 und E5 Versionen von Microsoft 365 Enterprise*

Microsoft 365 Enterprise umfasst Features zum Verwalten von Geräten und ihre apps, innerhalb Ihrer Organisation. Microsoft Intune können Sie zum Zugriff auf Ressourcen Ihrer Organisation, einschließlich der Daten zu schützen iOS, Android, Mac OS und Windows-Geräte verwalten. Intune Integration in Azure Active Directory (AD Azure) sowie die folgenden Geschäftsszenarien für Microsoft 365 aktiviert:

- Speichern und Freigeben von Dateien innerhalb und außerhalb Ihrer Organisation für eine nahtlose Zusammenarbeit über Organisationsgrenzen hinweg
- Sicheres Arbeiten überall und jederzeit von Ihrem Gerät aus, um bei einem flexiblen Arbeitsstil produktiver zu arbeiten
- Beruhigendes Gefühl dank Steuerungen und Sichtbarkeit für branchengeprüfte Konformität mit globalen Standards
- Schützen Ihrer Informationen und Reduzierung des Risikos von Datenverlusten
- Erkennung von und Schutz gegen externe Bedrohungen
- Überwachen, gemeldet und Analysieren der Aktivität, um umgehend reagieren, um die Sicherheit in der Organisation bereitstellen
- Schützen Sie Ihre Benutzer und ihre Konten

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

In dieser Phase Registrieren Ihrer Geräte in Intune, und erstellen und Erzwingen von Richtlinien zum Schutz Ihrer Daten sicher und geschützt werden. Ist die gesamte Bibliothek Intune Dokumentation [verfügbaren online](https://docs.microsoft.com/intune). Es ist außerdem empfehlenswert, [Intune bereitstellungsplanung, Entwurf und Implementierung Handbuch](https://docs.microsoft.com/intune/planning-guide) lesen, bevor Sie beginnen.

## <a name="step-1-plan-for-your-scenario"></a>Schritt 1: Planen des Szenarios

Einer der Hauptgründe für die Verwaltung von Mobilgeräten ist sichern und schützen den Ressourcen Ihrer Organisation. [Allgemeine Verfahren zum Verwenden von Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) listet einige reale Beispiele, einschließlich Office 365-e-Mail und Daten sichern.

Intune bietet Ihnen die Optionen zum Verwalten des Zugriffs auf Ihre Organisation über [Mobile Geräte Management (MDM) oder Mobile Application Management (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM ist, wenn Benutzer ihren Geräten in Intune "registrieren". Sobald registriert, sie sind verwalteten Geräten, und erhalten alle Richtlinien, Regeln und Einstellungen, die von Ihrer Organisation verwendet werden. Sie können beispielsweise Einzelheiten apps installieren, erstellen eine Kennwortrichtlinie, installieren, eine VPN-Verbindung und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten sollten nicht auf ihren Geräten registrieren oder Intune und Ihrer Richtlinien verwaltet werden. Weiterhin benötigen jedoch zum Schutz Ihrer Organisation Ressourcen und Daten. In diesem Szenario können Sie Ihre apps mithilfe von MAM schützen. Beispielsweise können Sie eine Richtlinie MAM verwenden, die einen Benutzer eine PIN eingeben, beim Zugriff auf SharePoint auf dem Gerät erforderlich sind.

Sie können auch bestimmen, wie Sie persönliche oder im Besitz der Organisation Geräte verwalten möchten. Sie möchten Geräte unterschiedlich, je nach ihrer Verwendung zu behandeln. Beispielsweise sollten Sie verschiedene Pläne für Benutzer in Human Resources (HR) oder die Benutzer in Sales. [Identifizieren Mobilgerät - Anwendungsfall Verwaltungsszenarien](https://docs.microsoft.com/intune/planning-guide-scenarios) erhalten Sie die Schritte, und enthält einige Hinweise auf diese verschiedenen Szenarien.

## <a name="step-2-get-your-prerequisites"></a>Schritt 2: Abrufen der erforderlichen Komponenten

Im nächsten Schritt rufen Sie die erforderlichen Komponenten basierend auf Ihren Anforderungen und Ihre Szenarien, die im vorherigen Schritt erstellt haben. [Implementieren des Plans](https://docs.microsoft.com/intune/planning-guide-onboarding) werden alle Anforderungen aufgelistet. Hier sind die wichtigsten Punkte für Intune mit Microsoft 365 benötigten:

- **Intune-Abonnement**: in Microsoft 365 und bietet Zugriff auf Microsoft Intune im [Azure Portal](https://portal.azure.com) enthalten
- **Office 365-Abonnements**: in Microsoft 365 enthalten und wird für die Office-apps, einschließlich e-Mail
- **Azure Active Directory (AD) Premium**: in Microsoft 365 enthalten und wird verwendet, um Benutzer oder Sicherheitsgruppen erstellen. Diese Gruppen erhalten Intune-Richtlinien, die Sie erstellt haben, wie etwa eine Kennwortlänge zum Entsperren eines Geräts zu erzwingen. Sie in erstellen Gruppen [Phase 2: Identität](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) verwendet werden kann.

Möglicherweise gibt es einige zusätzlichen Anforderungen, je nach Anforderungen Ihrer Organisation. Wenn Sie iOS-Geräte verwalten, benötigen Sie ein Zertifikat Apple MDM Push eingetragenen. Wenn Sie lokale Exchange, und klicken Sie dann die erforderlichen des lokalen Exchange-Connectors verwenden. Wenn die entsprechenden Schritte angezeigt wird, werden diese zusätzlichen Anforderungen beschrieben.

## <a name="step-3-set-up-intune"></a>Schritt 3: Einrichten von Intune

Intune verwendet viele Funktionen in Azure AD, einschließlich Ihrer Domäne, die Benutzer und Gruppen. Sie können auch neue Benutzer und Gruppen, um Unternehmen maßgeschneiderte erstellen. Beispielsweise können Sie eine Gruppe namens **iOS-Geräte**oder **alle HR-Benutzer**erstellen.  Nutzen Sie [Dynamische Gruppen](https://docs.microsoft.com/intune/groups-add) , bei denen Sie Benutzer oder Gerätegruppen auf der Basis einfacher oder erweiterter Regeln erstellen können.

Dieser Schritt konzentriert sich auf das Einrichten Intune und Vorbereitung für die Geräte verwalten.

1. **[Bestätigen Sie Ihre Geräte unterstützt werden](https://docs.microsoft.com/intune/supported-devices-browsers)**. Vergewissern Sie sich Ihre iOS, Mac OS, Android, Galaxy und Windows-Geräte werden vom Intune unterstützt. Wenn Ihre Organisation Geräte, die nicht unterstützt werden umfasst, werden nicht die Richtlinien für diese Geräte angewendet.

2. **[Anpassen von Ihren Domänennamen](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Standardmäßig mit eine Domäne der etwa **your domain.onmicrosoft.com** automatisch in Azure Active Directory erstellt wird. **"onmicrosoft.com"** können für Ihre Organisation angepasst werden. Wenn Sie anpassen, es auch ermöglicht es den Benutzern eine vertraute Domäne beim Herstellen einer Verbindung zu Intune und Verwenden von Ressourcen.

3. **[Melden Sie sich bei Intune](https://docs.microsoft.com/intune/account-sign-up)**. Wenn Sie sich anmelden, werden Sie möglicherweise zur Eingabe von Informationen über Ihre Organisation aufgefordert. Intune gehört zum Lieferumfang von Microsoft 365 und direkt vom [Office 365-Verwaltungsportal](https://portal.office.com/)geöffnet werden kann. Sie können auch direkt über das [Portal Azure](https://portal.azure.com)Intune öffnen.

4. **[Wählen Sie die Konfiguration des mobilen Geräts Management](https://docs.microsoft.com/intune/mdm-authority-set)**. Der ersten Verwendung Intune, müssen Sie die Verwaltung von Geräten aktivieren. Intune kann als nur-Cloud-Dienst, einer Hybriden mit Intune und System Center Configuration Manager oder mithilfe der Verwaltung mobiler Geräte für Office 365 verwendet werden. Sie können auswählen, welche Setup am besten für Ihre Organisation.

5. **[Hinzufügen von Benutzern](https://docs.microsoft.com/intune/users-add)** und **[Gruppen hinzufügen](https://docs.microsoft.com/intune/groups-add)**. 

   Sie können manuell hinzufügen von Benutzern oder Verbinden mit Azure Active Directory Sync-Benutzern mit Intune. Sie können auch Administratorrollen auf bestimmte Benutzer zuweisen. Benutzer sind erforderlich, es sei denn, die Geräte "userless" Geräte, wie Kiosk-Geräte können.

   Azure Active Directory-Gruppen dienen zum vereinfachen, wie Sie die Geräte und Benutzer in Intune verwalten. Verwendung von Gruppen können Sie viele verschiedene Aufgaben durchführen. Ihre Organisation möchte beispielsweise eine bestimmte app für Android-Geräte erforderlich. Sie können erstellen Sie eine Gruppe von Android-Geräte, und stellen eine Richtlinie mit diese app in der Gruppe.

    Sie können in Intune, hinzufügen, Benutzer oder Gruppen, die Sie in erstellen [Phase 2: Identität](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Zuweisen von Lizenzen](https://docs.microsoft.com/intune/licenses-assign)**. Für Benutzer oder Geräte in Intune registrieren benötigen sie eine Lizenz auf dem Gerät. Jeder Benutzer oder userless Verbindung erfordert, dass eine Intune Lizenz Intune-Dienst zugreifen. Diese Lizenzen sind in Microsoft 365 enthalten und müssen in Intune zugewiesen werden.

## <a name="step-4-enroll-devices"></a>Schritt 4: Registrieren von Geräten

Zum Verwalten von Geräten müssen die Geräte Intune registriert werden. Als Administrator benötigen Sie Registrierung Einschränkungen und Richtlinien für Benutzer und Geräte einrichten. Jedes Geräteplattform (iOS, Android, Mac OS und Windows) weist eine Reihe von Optionen. Sie können die Benutzer selbst registriert haben. Oder Registrierung kann automatisiert werden, damit Benutzer einfach auf das Gerät anmelden.

Registrierung ist ein wichtiger Schritt beim Intune verwenden. [Registrieren Geräte](https://docs.microsoft.com/intune/device-enrollment) führt die Schritte für verschiedene Geräte.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: iOS und Android-Gerät Registrierung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Schritt 5: Hinzufügen und Bereitstellen von apps

Apps auf mobilen Geräten sind häufig die schnellste Möglichkeit Benutzer Zugriff auf die Unternehmensressourcen zu erhalten. 

Probleme werden beim-apps verwenden verschiedene Geräte, einschließlich der persönlichen Geräte und im Unternehmen vorhanden sind. Und Schützen Ihrer Organisation Ressourcen und deren Daten gleichzeitig auch sicherstellen, dass Benutzer produktiv werden soll.

Intune kann apps, einschließlich verwalten hinzufügen von apps, weisen Sie diese anderen Benutzern oder Gruppen, und überprüfen Sie andere wichtige Details. Beispielsweise können Sie sehen, welche apps nicht installieren, überprüfen Sie die Version von einer app und vieles mehr.

Wenn Benutzer auf ein mobiles Gerät eingeht, wird eine der ersten Aufgaben Organisationseinheit e-Mails und Dokumente zugreifen. Intune verwenden, können Sie [Erstellen und Bereitstellen von e-Mail-Einstellungen für](https://docs.microsoft.com/intune/email-settings-configure) die Geräte über e-Mail-apps, die bereits installiert sind. 

[Hinzufügen von apps](https://docs.microsoft.com/intune/app-management) führt die Schritte zum Hinzufügen, bereitstellen, überwachen, konfigurieren und Schützen von apps auf Geräten in Ihrer org

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: Gerät Kompatibilitätsrichtlinien](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Schritt 6: Aktivieren der Einhaltung von Vorschriften und bedingten Zugriff

In den vorherigen Schritten richten Sie Ihre Umgebung und Intune aktiviert. Jetzt können Sie nun einige Richtlinien mithilfe der Einhaltung von Vorschriften und bedingte Access erstellen.

Einhaltung von Vorschriften und bedingte Access sind zum Verwalten von Geräten wichtig. **[Richtlinien für die Kompatibilität](https://docs.microsoft.com/intune/device-compliance-get-started)** werden erstellt, um den Ressourcen Ihrer Organisation zu schützen. Wenn Sie eine Compliance-Richtlinie erstellen, definieren Sie die Standard- oder "Baseline" was ein Gerät verfügen muss. Sie können beispielsweise eine veränderte akzeptable (oder inakzeptabel) wählen, Jailbroken Geräte blockieren, erfordern eine Kennwortlänge und vieles mehr. Wenn diese Geräte nicht Ihrer Regeln erfüllen, was bedeutet, dass sie nicht kompatibel sind, können Sie Zugriff auf Ihre Ressourcen blockieren.

Dies "blockieren" werden **[bedingte Access](https://docs.microsoft.com/intune/conditional-access)** vorgestellt. Wenn ein Gerät nicht kompatibel ist, können Sie Zugriff auf e-Mail, SharePoint und mehr blockieren.

Intune im [Azure Portal](https://portal.azure.com) können Sie diese Richtlinien erstellen und anwenden auf Benutzer und Geräte. Es empfiehlt sich starten Sie kleine, und verwenden Sie einen mehrstufigen Ansatz. Beispielsweise erstellen Sie eine iOS-Richtlinie, die Jailbroken Geräte blockiert. (In Intune "zuweisen" bezeichnet) wird die Richtlinie auf eine Gruppe Pilot- oder Test anwenden. Fügen Sie nach der anfänglichen Testen, mehr Benutzer in der Pilotgruppe. Mit einer mehrstufigen Ansatz können Sie Feedback aus einer Vielzahl von Benutzertypen abrufen.

[Erste Schritte mit Gerät Kompatibilitätsrichtlinien](https://docs.microsoft.com/intune/device-compliance-get-started) und [Was bedingten Zugriff ist?](https://docs.microsoft.com/intune/conditional-access) helfen Ihnen den Einstieg.

## <a name="step-7-apply-features-and-settings"></a>Schritt 7: Anwenden von Features und Einstellungen

Diese Features und Einstellungen gelten häufig den "coolen" Teil Intune, und sind sehr leistungsfähig. Nachdem Sie einige Richtlinien für die Kompatibilität mit bedingten Access erfolgreich erzwungen haben, können Sie **Device Profile**erstellen.

Intune im [Azure Portal](https://portal.azure.com) können Sie verschiedene Profile basierend auf Ihrem Geräteplattform - iOS, Mac OS, Android und Windows zu erstellen. Sie können beispielsweise folgende Aktionen ausführen:

- Verwenden Sie Endpoint Protection auf Geräten mit Windows 10, um verschiedene BitLocker-Optionen, einschließlich der Verschlüsselung aktivieren.
- Verwenden Sie das Feature eingeschränkte apps auf iOS-Geräte, eine Liste der zugelassenen apps erstellen, die installiert werden kann. Oder erstellen Sie eine Liste der verbotene apps.
- Verwenden Sie die Kiosk-Einstellungen auswählen, welche apps auf Android-Geräte ausgeführt wird, im Kioskmodus verwendet werden können.
- Wenden Sie eine Wi-Fi-Verbindung und die zugehörigen Einstellungen, einschließlich den Sicherheitstyp auf Mac OS-Geräten.
- Und vieles mehr.

[Was Intune Microsoft Device Profile sind?](https://docs.microsoft.com/intune/device-profiles) eignet sich zum Lesen Sie Informationen zu Benutzerprofilen finden Sie unter Gewusst wie: Erstellen eines Profils und vieles mehr.

Denken Sie daran, klein anfangen und einen mehrstufigen Ansatz verwenden. Weisen Sie das Profil zu einer Gruppe Pilot- oder Test. Klicken Sie dann weitere pilot Gruppen zuweisen des Profils.

## <a name="step-8-get-to-know-the-other-features"></a>Schritt 8: Erste Schritte mit anderen features

Intune ist eine leistungsstarke Webdienst, und enthält zahlreiche Features. Es folgen einige andere Aufgaben, die Sie mittels Intune ausführen können:

- Verwalten von Software und Updates auf Windows- [Geräte](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)und [iOS](https://docs.microsoft.com/intune/software-updates-ios) -Geräte
- Aktivieren Sie [Windows Defender erweiterte Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) auf Ihren Windows-10-Geräten, und verwenden Sie Einhaltung von Vorschriften und bedingte Access Schutz des Zugriffs auf Unternehmensressourcen wie SharePoint oder Exchange Online
- Verwenden Sie [Lookout](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)und anderen mobilen Defense Bedrohung Partner
- Hinzufügen einer [Partner-Zertifizierungsstelle (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) zum Ausstellen und Erneuern von Zertifikaten
- [Provide Anleitung für die Endbenutzer](https://docs.microsoft.com/intune/end-user-educate) auf die app Unternehmensportal, erste apps und mehr
- Überwachen von [apps](https://docs.microsoft.com/intune/apps-monitor), Monitor [Gerät Compliance](https://docs.microsoft.com/intune/compliance-policy-monitor), Monitor [Konfigurationsprofile](https://docs.microsoft.com/intune/compliance-policy-monitor)und weitere Telemetrie verwenden die Überwachungsprotokolle. Sie können auch eine Verbindung mit dem [Data Warehouse Intune](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) und Power BI für noch mehr reporting Anforderungen.


## <a name="identity-and-device-access-recommendations"></a>Identität und Gerät Access Empfehlungen

Microsoft bietet eine Reihe von Empfehlungen für die [Identität und Gerät Zugriff](microsoft-365-policies-configurations.md) auf eine sichere und produktive Belegschaft sicherzustellen. Verwenden Sie für den Gerätezugriff der Empfehlungen und Einstellungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:

- [Voraussetzungen](identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Hier erfahren Sie, wie IT-Experten von Microsoft für geplant und zur Abstimmung und Gerät Management mit diesen Ressourcen bereitgestellt:

- [Verwalten der mobilen Produktivität mit Enterprise Mobility + Security](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [Herstellen einer Verbindung mit Microsoft Intune, um auf Ihrem Windows 10-Gerät zu arbeiten](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [Aktivieren der mobilen Produktivität für iOS-, OS X- und Android-Geräte bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Finden Sie unter wie der Contoso Corporation, ein fiktives aber repräsentative multinationale Unternehmen, [ihre mobilen Geräteverwaltungsinfrastruktur bereitgestellt](contoso-mdm.md) , mit Microsoft 365 cloud-Diensten.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

[Mobiles Gerät Management Infrastructure abschlusskriterien](mobility-infrastructure-exit-criteria.md)

