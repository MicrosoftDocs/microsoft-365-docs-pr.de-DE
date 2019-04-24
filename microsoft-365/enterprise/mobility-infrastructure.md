---
title: 'Phase 5: Verwaltung mobiler Geräte'
description: Microsoft 365 Enterprise umfasst die Verwaltung mobiler Geräte mit Microsoft InTune. Überprüfung der Anforderungen und Voraussetzungen, Einrichten von InTune mithilfe ihrer Azure Active Directory-Ressource, Registrieren von iOS-, macOS-, Android-und Windows-Geräten, Bereitstellen von apps, Erstellen eines Konfigurationsprofils, verwenden einer Konformitätsrichtlinie und Aktivieren des bedingten Zugriffs für Mobilgeräte Geräteverwaltung mit Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Mobile Device Management, InTune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 35fa9f53b555de48f4a5acc09d0619ba978ca87a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291210"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Phase 5: Verwaltung mobiler Geräte für Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Diese Funktion gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

Microsoft 365 Enterprise bietet Funktionen zum Verwalten von Geräten und ihren apps in Ihrer Organisation. Mit Microsoft InTune können Sie iOS, Android, macOS und Windows-Geräte verwalten, um den Zugriff auf die Ressourcen Ihrer Organisation, einschließlich Ihrer Daten, zu schützen. InTune integriert sich in Azure Active Directory (Azure AD) und aktiviert die folgenden Geschäftsszenarien für Microsoft 365:

- Speichern und Freigeben von Dateien innerhalb und außerhalb Ihrer Organisation für eine nahtlose Zusammenarbeit über Organisationsgrenzen hinweg
- Sicheres Arbeiten überall und jederzeit von Ihrem Gerät aus, um bei einem flexiblen Arbeitsstil produktiver zu arbeiten
- Beruhigendes Gefühl dank Steuerungen und Sichtbarkeit für branchengeprüfte Konformität mit globalen Standards
- Schützen Ihrer Informationen und Reduzierung des Risikos von Datenverlusten
- Schutz vor externen Bedrohungen
- Überwachen, melden und Analysieren von Aktivitäten, um sofort auf die Sicherheit der Organisation zu reagieren
- Schützen der Benutzer und ihrer Konten

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

In dieser Phase registrieren Sie Ihre Geräte in InTune und erstellen und erzwingen Richtlinien, um die Sicherheit und den Schutz Ihrer Daten zu gewährleisten. Die gesamte Bibliothek der InTune-Dokumentation ist [online verfügbar](https://docs.microsoft.com/intune). Außerdem empfiehlt es sich, den Leitfaden für die [Planung, den Entwurf und die Implementierung von InTune](https://docs.microsoft.com/intune/planning-guide) zu überarbeiten, bevor Sie beginnen.

## <a name="step-1-plan-for-your-scenario"></a>Schritt 1: Planen des Szenarios

Einer der Hauptgründe für die Verwaltung mobiler Geräte besteht darin, die Ressourcen Ihrer Organisation zu sichern und zu schützen. [Allgemeine Verwendungsmöglichkeiten für Microsoft InTune](https://docs.microsoft.com/intune/common-scenarios) sind einige Beispiele aus der Praxis, einschließlich der Sicherung von Office 365-e-Mails und-Daten.

InTune bietet Ihnen Optionen zum Verwalten des Zugriffs auf Ihre Organisation mithilfe von [Mobile Device Management (MDM) oder Mobile Application Management (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM ist der Zeitpunkt, zu dem Benutzer ihre Geräte in InTune "registrieren". Nach der Registrierung handelt es sich um verwaltete Geräte, die von Ihrer Organisation verwendete Richtlinien, Regeln und Einstellungen empfangen können. Sie können beispielsweise spezifische apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten möchten Ihre Geräte möglicherweise nicht registrieren oder von InTune und ihren Richtlinien verwaltet werden. Sie müssen jedoch weiterhin die Ressourcen und Daten Ihrer Organisation schützen. In diesem Szenario können Sie Ihre apps mit MAM schützen. Sie können beispielsweise eine MAM-Richtlinie verwenden, bei der ein Benutzer beim Zugriff auf SharePoint auf dem Gerät eine PIN eingeben muss.

Außerdem bestimmen Sie, wie Sie persönliche oder organisationseigene Geräte verwalten. Sie können geräteabhängig von ihrer Verwendung unterschiedlich behandeln. Sie können beispielsweise unterschiedliche Pläne für Benutzer in personalABTEILUNGEN (HR) oder Benutzer im Vertrieb wünschen. [Identifizieren Sie die Verwaltung mobiler Geräte mithilfe von Fall Szenarien](https://docs.microsoft.com/intune/planning-guide-scenarios) können Sie mit den ersten Schritten beginnen und einige Anleitungen zu diesen verschiedenen Szenarien finden.

## <a name="step-2-get-your-prerequisites"></a>Schritt 2: Abrufen der erforderlichen Komponenten

Als nächstes erhalten Sie Ihre Voraussetzungen basierend auf Ihren Anforderungen und ihren Szenarien, die Sie im vorherigen Schritt erstellt haben. [Implementieren Sie Ihren Plan](https://docs.microsoft.com/intune/planning-guide-onboarding) alle Anforderungen. Nachfolgend finden Sie die wichtigsten Elemente, die Sie für InTune mit Microsoft 365 benötigen:

- **InTune-Abonnement**: enthalten in Microsoft 365 und Zugriff auf Microsoft InTune im [Azure-Portal](https://portal.azure.com)
- **Office 365-Abonnement**: im Lieferumfang von Microsoft 365 und wird für Office-Apps verwendet, einschließlich e-Mail
- **Azure Active Directory (Azure AD) Premium**: in Microsoft 365 enthalten und zum Erstellen von Benutzer-oder Sicherheitsgruppen verwendet. Diese Gruppen erhalten InTune-Richtlinien, die Sie erstellen, beispielsweise Erzwingen einer Kennwortlänge zum Entsperren eines Geräts. Die Gruppen, die Sie in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) erstellen, können verwendet werden.

Je nach den Anforderungen Ihrer Organisation gibt es möglicherweise einige zusätzliche Anforderungen. Wenn Sie beispielsweise iOS-Geräte verwalten, benötigen Sie ein Apple MDM Push-Zertifikat. Wenn Sie lokalen Exchange verwenden, benötigen Sie den lokalen Exchange-Connector. Diese zusätzlichen Anforderungen werden erläutert, wenn Sie diese Schritte ausführen.

## <a name="step-3-set-up-intune"></a>Schritt 3: Einrichten von InTune

InTune verwendet viele Features in Azure AD, einschließlich Ihrer Domäne, ihrer Benutzer und ihrer Gruppen. Sie können auch neue Benutzer und neue Gruppen erstellen, die Ihren Unternehmensanforderungen entsprechen. Sie können beispielsweise eine Gruppe mit dem Namen **IOS-Geräte**oder **alle HR-Benutzer**erstellen.  Nutzen Sie [dynamische Gruppen](https://docs.microsoft.com/intune/groups-add) , mit denen Sie Benutzer-oder Gerätegruppen basierend auf einfachen oder erweiterten Regeln erstellen können.

In diesem Schritt wird das Einrichten von InTune und das Bereitstellen der Verwaltung Ihrer Geräte erläutert.

1. **[Bestätigen Sie, dass Ihre Geräte unterstützt werden](https://docs.microsoft.com/intune/supported-devices-browsers)**. Bestätigen Sie, dass iOS, macOS, Android, Galaxy und Windows-Geräte von InTune unterstützt werden. Wenn Ihre Organisation Geräte enthält, die nicht unterstützt werden, werden die Richtlinien nicht auf diese Geräte angewendet.

2. **[Passen Sie Ihren Domänennamen](https://docs.microsoft.com/intune/custom-domain-name-configure)** an. Standardmäßig wird in Azure AD automatisch eine Domäne mit dem Namen **your-Domain.onmicrosoft.com** erstellt. **onmicrosoft.com** kann für Ihre Organisation angepasst werden. Bei der Anpassung erhalten Benutzer eine vertraute Domäne beim Herstellen einer Verbindung mit InTune und Ressourcen.

3. **[Melden Sie sich bei InTune an](https://docs.microsoft.com/intune/account-sign-up)**. Wenn Sie sich anmelden, werden Sie möglicherweise aufgefordert, Informationen zu Ihrer Organisation einzugeben. InTune ist in Microsoft 365 enthalten und kann direkt im [microsoft 365 Admin Center](https://admin.microsoft.com)geöffnet werden. Sie können InTune auch direkt über das [Azure-Portal](https://portal.azure.com)öffnen.

4. **[Wählen Sie die Verwaltungskonfiguration für mobile Geräte aus](https://docs.microsoft.com/intune/mdm-authority-set)**. Wenn Sie InTune zum ersten Mal verwenden, müssen Sie die Geräteverwaltung aktivieren. InTune kann als Cloud-only-Dienst, als Hybride mit InTune und System Center Configuration Manager oder zur Verwendung der mobilen Geräteverwaltung für Office 365 verwendet werden. Sie können auswählen, welches Setup für Ihre Organisation am besten geeignet ist.

5. **[Hinzufügen von Benutzern](https://docs.microsoft.com/intune/users-add)** und **[Hinzufügen von Gruppen](https://docs.microsoft.com/intune/groups-add)** 

   Sie können Benutzer manuell hinzufügen oder eine Verbindung mit Azure AD herstellen, um Benutzer mit InTune zu synchronisieren. Sie können auch Administratorrollen für bestimmte Benutzer erteilen. Benutzer sind erforderlich, es sei denn, Ihre Geräte sind Benutzerlos-Geräte wie Kiosk Geräte.

   Azure AD-Gruppen werden verwendet, um die Verwaltung von Geräten und Benutzern in InTune zu vereinfachen. Mithilfe von Gruppen können Sie viele verschiedene Aufgaben ausführen. Beispielsweise möchte Ihre Organisation eine bestimmte App auf Android-Geräten benötigen. Sie können eine Android-Gerätegruppe erstellen und eine Richtlinie mit dieser app in der Gruppe bereitstellen.

    In InTune können Sie Benutzer oder Gruppen hinzufügen, die Sie in [Phase 2 erstellen: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Lizenzen zuweisen](https://docs.microsoft.com/intune/licenses-assign)**. Damit Benutzer oder Geräte sich in InTune registrieren können, benötigen Sie eine Lizenz auf dem Gerät. Für jedes Benutzer-oder Benutzerlos Gerät ist eine InTune-Lizenz für den Zugriff auf den InTune-Dienst erforderlich. Diese Lizenzen sind in Microsoft 365 enthalten und müssen in InTune zugewiesen werden.

## <a name="step-4-enroll-devices"></a>Schritt 4: Registrieren von Geräten

Um Geräte zu verwalten, müssen die Geräte in InTune registriert sein. Als Administrator richten Sie Registrierungs Einschränkungen und-Richtlinien für Ihre Benutzer und Geräte ein. Jede Geräteplattform (iOS, Android, macOS und Windows) verfügt über eine Vielzahl von Optionen. Ihre Benutzer können sich selbst registrieren. Sie können auch die Registrierung automatisieren, sodass sich Benutzer einfach beim Gerät anmelden.

Die Registrierung ist ein wichtiger Schritt bei der Verwendung von InTune. [Registrieren von Geräten](https://docs.microsoft.com/intune/device-enrollment) listet die Schritte für die verschiedenen Geräte auf.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: iOS-und Android-Geräteregistrierung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Schritt 5: Hinzufügen und Bereitstellen von apps

Apps auf mobilen Geräten sind häufig die schnellste Möglichkeit für den Zugriff von Benutzern auf Ihre Unternehmensressourcen. 

Es gibt Herausforderungen bei der Verwendung von apps, da es unterschiedliche Geräte gibt, einschließlich persönlicher Geräte und unternehmensgeräte. Und Sie möchten die Ressourcen Ihrer Organisation und Ihre Daten schützen und gleichzeitig sicherstellen, dass die Benutzer produktiv sind.

InTune kann apps verwalten, einschließlich apps hinzufügen, Sie verschiedenen Benutzern oder Gruppen zuweisen und andere Schlüssel Details überarbeiten. Sie können beispielsweise erkennen, welche apps nicht installiert werden, ob Sie die Version einer APP und vieles mehr überprüfen.

Wenn Benutzer ein mobiles Gerät erhalten, ist eine der ersten Aufgaben der Zugriff auf Organisations-e-Mails und-Dokumente. Mit InTune können Sie e-Mail-Einstellungen mithilfe von e-Mail-apps [Erstellen und Bereitstellen](https://docs.microsoft.com/intune/email-settings-configure) , die auf den Geräten vorinstalliert sind. 

[Apps hinzufügen](https://docs.microsoft.com/intune/app-management) enthält eine Liste der Schritte zum Hinzufügen, bereitstellen, überwachen, konfigurieren und schützen von apps auf Geräten innerhalb Ihrer Organisation.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: Device Compliance Policies](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Schritt 6: Aktivieren der Kompatibilität und des bedingten Zugriffs

In den vorherigen Schritten haben Sie die Umgebung eingerichtet und InTune aktiviert. Jetzt sind Sie bereit, einige Richtlinien mithilfe von Compliance und bedingtem Zugriff zu erstellen.

Compliance und bedingter Zugriff sind wichtig für die Verwaltung von Geräten. **[Konformitätsrichtlinien](https://docs.microsoft.com/intune/device-compliance-get-started)** werden erstellt, um die Ressourcen Ihrer Organisation zu schützen. Wenn Sie eine Konformitätsrichtlinie erstellen, definieren Sie die Standard-oder die "Baseline" eines Geräts. Sie können beispielsweise eine akzeptable (oder inakzeptabel) Bedrohungsstufe auswählen, Geräte mit jailbroken blockieren, eine Kennwortlänge erfordern und vieles mehr. Wenn diese Geräte ihre Regeln nicht erfüllen, was bedeutet, dass Sie nicht kompatibel sind, können Sie den Zugriff auf Ihre Ressourcen blockieren.

Diese Blockierung führt zu einem **[bedingten Zugriff](https://docs.microsoft.com/intune/conditional-access)**. Wenn ein Gerät als nicht kompatibel gilt, können Sie den Zugriff auf e-Mails, SharePoint und vieles mehr blockieren.

InTune im [Azure-Portal](https://portal.azure.com) können Sie diese Richtlinien erstellen und auf Ihre Benutzer und Geräte anwenden. Als bewährte Methode sollten Sie klein beginnen und einen stufenweisen Ansatz verwenden. Erstellen Sie beispielsweise eine iOS-Richtlinie, die jailbroken-Geräte blockiert. Wenden Sie die Richtlinie ("Assign" in InTune) auf eine Pilot-oder Testgruppe an. Fügen Sie nach anfänglichen Tests der Pilotgruppe weitere Benutzer hinzu. Mit einer stufenweisen Vorgehensweise können Sie Feedback aus einer Vielzahl von Benutzertypen abrufen.

Erste [Schritte mit Geräte Konformitätsrichtlinien](https://docs.microsoft.com/intune/device-compliance-get-started) und [dem bedingten Zugriff?](https://docs.microsoft.com/intune/conditional-access) unterstützt Sie bei den ersten Schritten.

## <a name="step-7-apply-features-and-settings"></a>Schritt 7: Anwenden von Features und Einstellungen

Diese Features und Einstellungen gelten oft als der "kühle" Teil von InTune und sind sehr leistungsfähig. Nachdem Sie einige Kompatibilitätsrichtlinien mithilfe des bedingten Zugriffs erfolgreich erzwungen haben, können Sie **Geräteprofile**erstellen.

InTune im [Azure-Portal](https://portal.azure.com) ermöglicht das Erstellen unterschiedlicher Profile basierend auf Ihrer Geräteplattform-IOS, MacOS, Android und Windows. Sie verfügen über folgende Möglichkeiten:

- Verwenden Sie Endpunktschutz auf Windows 10-Geräten, um unterschiedliche BitLocker-Optionen, einschließlich Verschlüsselung, zu aktivieren.
- Verwenden Sie das Feature Eingeschränkte apps auf iOS-Geräten, um eine Liste der genehmigten apps zu erstellen, die installiert werden können. Oder erstellen Sie eine Liste der verbotenen apps.
- Verwenden Sie die Kiosk-Einstellungen, um auszuwählen, welche apps auf Android-Geräten verwendet werden können, die im Kiosk-Modus ausgeführt werden.
- Wenden Sie eine WLAN-Verbindung und Ihre Einstellungen, einschließlich des Sicherheitstyps, auf Geräten mit macOS an.
- Und mehr

[Was sind Microsoft InTune-Geräteprofile?](https://docs.microsoft.com/intune/device-profiles) eignet sich hervorragend für Profile, Informationen zum Erstellen eines Profils und vieles mehr.

Denken Sie daran, beginnen Sie klein und verwenden Sie einen stufenweisen Ansatz. Weisen Sie das Profil einer Pilot-oder Testgruppe zu. Weisen Sie das Profil dann mehreren Pilotgruppen zu.

## <a name="step-8-get-to-know-the-other-features"></a>Schritt 8: Kennenlernen der anderen Features

InTune ist ein leistungsstarker Dienst und enthält zahlreiche Features. Im folgenden finden Sie einige weitere Aufgaben, die Sie mit InTune durchführen können:

- Verwalten von Software und Updates auf Windows- [Geräten](https://docs.microsoft.com/intune/windows-update-for-business-configure) & ,[PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)und [IOS](https://docs.microsoft.com/intune/software-updates-ios) -Geräten
- Aktivieren Sie [Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) auf Ihren Windows 10-Geräten, und verwenden Sie Compliance und bedingten Zugriff, um den Zugriff auf Unternehmensressourcen wie SharePoint oder Exchange Online zu schützen.
- Verwenden von [Lookout](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)und anderen Bedrohungs Partnern für mobile Verteidigung
- Hinzufügen einer Partner Zertifizierungs [Stelle](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) zum ausgeben und erneuern von Zertifikaten
- [Bieten Sie Ihren Endbenutzern eine Orientierungshilfe](https://docs.microsoft.com/intune/end-user-educate) in der Unternehmens Portal-APP, erhalten Sie apps und vieles mehr.
- ÜberWachen Sie [apps](https://docs.microsoft.com/intune/apps-monitor), überwachen Sie die [Geräte Konformität](https://docs.microsoft.com/intune/compliance-policy-monitor), überwachen Sie [Konfigurationsprofile](https://docs.microsoft.com/intune/compliance-policy-monitor)und mehr Telemetrie mithilfe der Überwachungsprotokolle. Sie können auch eine Verbindung mit dem [InTune-Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) herstellen und Power BI für noch mehr Berichterstattungsanforderungen verwenden.


## <a name="identity-and-device-access-recommendations"></a>Empfehlungen für den Identitäts- und Gerätezugriff

Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können. Verwenden Sie für den Geräte Zugriff die Empfehlungen und Einstellungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:

- [Voraussetzungen](identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie, wie IT-Experten bei Microsoft die EMS-und Geräteverwaltung mit diesen Ressourcen geplant und bereitgestellt haben:

- [Verwalten der mobilen Produktivität mit Enterprise Mobility + Security](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [Herstellen einer Verbindung mit Microsoft Intune, um auf Ihrem Windows 10-Gerät zu arbeiten](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [Aktivieren der mobilen Produktivität für iOS-, OS X- und Android-Geräte bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives Multi-nationales Unternehmen, [Ihre Infrastruktur für Mobile Geräteverwaltung](contoso-mdm.md) mit Microsoft 365 Cloud Services bereitgestellt hat.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

[Infrastruktur-Exit-Kriterien für die Verwaltung mobiler Geräte](mobility-infrastructure-exit-criteria.md)

