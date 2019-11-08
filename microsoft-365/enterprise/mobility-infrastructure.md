---
title: 'Phase 5: Verwaltung mobiler Geräte'
description: Microsoft 365 Enterprise umfasst die Verwaltung mobiler Geräte mithilfe von Microsoft InTune. Überprüfen Sie die Anforderungen und Voraussetzungen, richten Sie InTune mithilfe ihrer Azure Active Directory-Ressource ein, registrieren Sie IOS-, macOS-, Android-und Windows-Geräte, stellen Sie apps bereit, erstellen Sie ein configure-Profil, verwenden Sie eine Konformitätsrichtlinie, und aktivieren Sie den bedingten Zugriff für Mobile Geräteverwaltung mit Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Verwaltung mobiler Geräte, InTune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 72ddad03486bf2c7dcba682453fa3bcfbdd1162b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031150"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Phase 5: Verwaltung mobiler Geräte für Microsoft 365 Enterprise

![Phase 5: Verwaltung mobiler Geräte](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Dieses Feature gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

Microsoft 365 Enterprise umfasst Features zur Unterstützung der Verwaltung von Geräten und deren apps in Ihrer Organisation. Mithilfe von Microsoft InTune können Sie IOS-, Android-, macOS-und Windows-Geräte verwalten, um den Zugriff auf die Ressourcen Ihrer Organisation einschließlich Ihrer Daten zu schützen. 

In dieser Phase registrieren Sie Ihre Geräte in InTune und erstellen und erzwingen Richtlinien, um die Sicherheit und den Schutz Ihrer Daten zu gewährleisten. Die gesamte Dokumentation zur InTune-Bibliothek steht [Online zur Verfügung](https://docs.microsoft.com/intune). Es empfiehlt sich auch, den Leitfaden zur [Planung, Entwurf und Implementierung von InTune-Bereitstellungen](https://docs.microsoft.com/intune/planning-guide) zu lesen, bevor Sie loslegen.

## <a name="step-1-plan-for-your-scenario"></a>Schritt 1: Planen des Szenarios

Einer der Hauptgründe für die Verwaltung mobiler Geräte ist die Sicherung und der Schutz der Ressourcen Ihrer Organisation. [Häufige Verwendungsweisen von Microsoft InTune](https://docs.microsoft.com/intune/common-scenarios) sind einige Beispiele aus der realen Welt, einschließlich der Sicherung Office 365 e-Mails und Daten.

InTune bietet Ihnen Optionen zum Verwalten des Zugriffs auf Ihre Organisation mithilfe von MDM (Mobile Device Management) oder MAM (Mobile Application Management). MDM ist, wenn Benutzer ihre Geräte in InTune "registrieren". Sobald die Registrierung erfolgt ist, handelt es sich um verwaltete Geräte und kann alle Richtlinien, Regeln und Einstellungen empfangen, die von Ihrer Organisation verwendet werden. Beispielsweise können Sie bestimmte apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.

Benutzer mit ihren eigenen persönlichen Geräten möchten möglicherweise Ihre Geräte nicht registrieren oder von InTune und ihren Richtlinien verwalten. Sie müssen jedoch dennoch die Ressourcen und Daten Ihrer Organisation schützen. In diesem Szenario können Sie Ihre apps mit MAM schützen. Sie können beispielsweise eine MAM-Richtlinie verwenden, bei der ein Benutzer eine PIN beim Zugriff auf SharePoint auf dem Gerät eingeben muss.

Darüber hinaus bestimmen Sie, wie Sie persönliche oder organisationseigene Geräte verwalten werden. Sie sollten Geräte je nach Verwendung unterschiedlich behandeln. Beispielsweise können Sie unterschiedliche Pläne für Benutzer in "Personalwesen" oder "Benutzer im Vertrieb" wünschen. [Identifizieren der Verwaltung mobiler Geräte verwenden – Fall Szenarien](https://docs.microsoft.com/intune/planning-guide-scenarios) können Ihnen den Einstieg erleichtern und einige Anleitungen zu diesen verschiedenen Szenarien enthalten.

## <a name="step-2-get-your-prerequisites"></a>Schritt 2: Abrufen Ihrer Voraussetzungen

Als nächstes erhalten Sie Ihre Voraussetzungen basierend auf Ihren Anforderungen und Szenarien, die im vorherigen Schritt erstellt wurden. [Implementieren Ihres Plans](https://docs.microsoft.com/intune/planning-guide-onboarding) listet alle Anforderungen auf. Hier sind die wichtigen Elemente, die Sie für InTune mit Microsoft 365 benötigen:

- **InTune-Abonnement**: im Lieferumfang von Microsoft 365 enthalten und erhalten Sie Zugriff auf Microsoft InTune im [Azure-Portal](https://portal.azure.com)
- **Office 365 Abonnement**: in Microsoft 365 enthalten und wird für Office-Apps einschließlich e-Mail verwendet
- **Azure Active Directory (Azure AD) Premium**: in Microsoft 365 enthalten und wird zum Erstellen von Benutzer-oder Sicherheitsgruppen verwendet. Diese Gruppen erhalten von Ihnen erstellte InTune-Richtlinien, beispielsweise das Erzwingen einer Kennwortlänge zum Entsperren eines Geräts. Die Gruppen, die Sie in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) erstellen, können verwendet werden.

Es gibt möglicherweise einige zusätzliche Anforderungen, je nach den Anforderungen Ihrer Organisation. Wenn Sie beispielsweise IOS-Geräte verwalten, benötigen Sie ein Apple MDM Push-Zertifikat. Wenn Sie lokale Exchange-Umgebung verwenden, benötigen Sie den lokalen Exchange Connector. Diese zusätzlichen Anforderungen werden beschrieben, wenn Sie zu diesen Schritten gelangen.

## <a name="step-3-set-up-intune"></a>Schritt 3: Einrichten von InTune

InTune verwendet viele Features in Azure AD, einschließlich Ihrer Domäne, ihrer Benutzer und ihrer Gruppen. Sie können auch neue Benutzer und neue Gruppen erstellen, die Ihren Unternehmensanforderungen entsprechen. Sie können beispielsweise eine Gruppe mit dem Namen **IOS-Geräte**oder **alle HR-Benutzer**erstellen.  Nutzen Sie [dynamische Gruppen](https://docs.microsoft.com/intune/groups-add) , mit denen Sie Benutzer-oder Gerätegruppen basierend auf einfachen oder erweiterten Regeln erstellen können.

Dieser Schritt konzentriert sich auf die Einrichtung von InTune und die Vorbereitung für die Verwaltung Ihrer Geräte.

1. **[Bestätigen Sie, dass Ihre Geräte unterstützt werden](https://docs.microsoft.com/intune/supported-devices-browsers)**. Bestätigen Sie, dass Ihre IOS-, macOS-, Android-, Galaxy-und Windows-Geräte von InTune unterstützt werden. Wenn Ihre Organisation Geräte enthält, die nicht unterstützt werden, werden die Richtlinien nicht auf diese Geräte angewendet.

2. **[Passen Sie Ihren Domänennamen](https://docs.microsoft.com/intune/custom-domain-name-configure)** an. Standardmäßig wird in Azure AD automatisch eine Domäne mit dem Namen "something like **your-Domain.onmicrosoft.com** " erstellt. **onmicrosoft.com** können für Ihre Organisation angepasst werden. Wenn Sie anpassen, erhalten Benutzer auch eine vertraute Domäne beim Herstellen einer Verbindung mit InTune und Verwenden von Ressourcen.

3. **[Melden Sie sich bei InTune an](https://docs.microsoft.com/intune/account-sign-up)**. Wenn Sie sich anmelden, werden Sie möglicherweise aufgefordert, Informationen zu Ihrer Organisation einzugeben. InTune ist in Microsoft 365 enthalten und kann direkt im [Microsoft 365 Admin Center](https://admin.microsoft.com)geöffnet werden. Sie können InTune auch direkt über das [Azure-Portal](https://portal.azure.com)öffnen.

4. **[Wählen Sie die Verwaltungskonfiguration für mobile Geräte aus](https://docs.microsoft.com/intune/mdm-authority-set)**. Wenn Sie InTune zum ersten Mal verwenden, müssen Sie die Geräteverwaltung aktivieren. InTune kann als Cloud-only-Dienst, als Hybrid mit InTune und System Center Configuration Manager oder mithilfe der Verwaltung mobiler Geräte für Office 365 verwendet werden. Sie können auswählen, welches Setup für Ihre Organisation am besten geeignet ist.

5. **[Hinzufügen von Benutzern](https://docs.microsoft.com/intune/users-add)** und **[Hinzufügen von Gruppen](https://docs.microsoft.com/intune/groups-add)**. 

   Sie können Benutzer manuell hinzufügen oder Hybrid Identitäten verwenden und Azure AD Connect herstellen, um Ihre lokalen Benutzerkonten mit InTune zu synchronisieren. Sie können auch Administratorrollen bestimmten Benutzern zuweisen. Benutzer sind erforderlich, es sei denn, Ihre Geräte sind "Benutzer"-Geräte wie Kiosk Geräte.

   Azure Ad Gruppen werden verwendet, um die Verwaltung von Geräten und Benutzern in InTune zu vereinfachen. Bei Verwendung von Gruppen können Sie viele verschiedene Aufgaben ausführen. Ihre Organisation möchte beispielsweise eine bestimmte App auf Android-Geräten benötigen. Sie können eine Gruppe von Android-Geräten erstellen und eine Richtlinie mit dieser APP für die Gruppe bereitstellen.

    In InTune können Sie Benutzer oder Gruppen hinzufügen, die Sie in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) erstellen

6. **[Zuweisen von Lizenzen](https://docs.microsoft.com/intune/licenses-assign)**. Damit Benutzer oder Geräte sich in InTune registrieren können, benötigen Sie eine Microsoft 365-Lizenz, wobei der InTune-Dienst für den Zugriff auf den InTune-Dienst aktiviert ist. Sie weisen Microsoft 365-Lizenzen zu, bei denen der Microsoft InTune-Dienst standardmäßig im Microsoft 365 Admin Center oder mit PowerShell aktiviert ist.

## <a name="step-4-enroll-devices"></a>Schritt 4: Registrieren von Geräten

Zum Verwalten von Geräten müssen die Geräte in InTune registriert sein. Als Administrator richten Sie Registrierungs Einschränkungen und-Richtlinien für Ihre Benutzer und Geräte ein. Jede Geräteplattform (Ios, Android, macOS und Windows) verfügt über eine Vielzahl von Optionen. Sie können Ihre Benutzer selbst registrieren lassen. Oder Sie können die Registrierung automatisieren, sodass sich Benutzer einfach beim Gerät anmelden.

Die Registrierung ist ein wichtiger Schritt bei der Verwendung von InTune. [Geräte registrieren](https://docs.microsoft.com/intune/device-enrollment) listet die Schritte für die verschiedenen Geräte auf.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Umgebungs Anleitung: IOS-und Android-Geräteregistrierung](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Schritt 5: Hinzufügen und Bereitstellen von apps

Apps auf mobilen Geräten sind häufig der schnellste Weg, den Benutzer auf Ihre Unternehmensressourcen erhalten. 

Es gibt Herausforderungen bei der Verwendung von apps, da es verschiedene Geräte gibt, einschließlich persönlicher Geräte und unternehmensgeräte. Außerdem möchten Sie die Ressourcen und Daten Ihrer Organisation schützen und gleichzeitig sicherstellen, dass die Benutzer produktiv sind.

InTune kann apps verwalten, einschließlich apps hinzufügen, Sie verschiedenen Benutzern oder Gruppen zuweisen und andere wichtige Details überprüfen. Beispielsweise können Sie sehen, welche apps nicht installiert werden, überprüfen Sie die Version einer APP und vieles mehr.

Wenn Benutzer ein mobiles Gerät erhalten, besteht eine der ersten Aufgaben im Zugriff auf Organisations-e-Mails und-Dokumente. Mithilfe von InTune können Sie e-Mail-Einstellungen mithilfe von e-Mail-apps [Erstellen und Bereitstellen](https://docs.microsoft.com/intune/email-settings-configure) , die auf den Geräten vorinstalliert sind. 

Der Artikel [apps hinzufügen](https://docs.microsoft.com/intune/apps/apps-add) enthält eine Liste der Schritte zum Hinzufügen, bereitstellen, überwachen, konfigurieren und schützen von apps auf Geräten in Ihrer Organisation.

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Umgebungs Anleitung: Geräte Konformitätsrichtlinien](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Schritt 6: Aktivieren der Kompatibilität und des bedingten Zugriffs

In den vorherigen Schritten richten Sie Ihre Umgebung ein und aktivieren InTune. Jetzt können Sie einige Richtlinien mit Compliance und bedingtem Zugriff erstellen.

Compliance und bedingter Zugriff sind für die Verwaltung von Geräten wichtig. [Konformitätsrichtlinien](https://docs.microsoft.com/intune/device-compliance-get-started) werden erstellt, um die Ressourcen Ihrer Organisation zu schützen. Wenn Sie eine Konformitätsrichtlinie erstellen, definieren Sie die Standard-oder die "Baseline", die ein Gerät aufweisen muss. Sie können beispielsweise eine akzeptable (oder nicht akzeptable) Bedrohungsstufe auswählen, jailbroken-Geräte blockieren, eine Kennwortlänge und vieles mehr benötigen. Wenn diese Geräte Ihren Regeln nicht entsprechen, was bedeutet, dass Sie nicht kompatibel sind, können Sie den Zugriff auf Ihre Ressourcen blockieren.

Durch dieses "blockieren" wird der [bedingte Zugriff](https://docs.microsoft.com/intune/conditional-access)eingeführt. Wenn ein Gerät als nicht kompatibel gilt, können Sie den Zugriff auf e-Mails, SharePoint und vieles mehr blockieren.

Mit InTune im [Azure-Portal](https://portal.azure.com) können Sie diese Richtlinien erstellen und auf Ihre Benutzer und Geräte anwenden. Als bewährte Methode sollten Sie klein beginnen und einen mehrstufigen Ansatz verwenden. Erstellen Sie beispielsweise eine IOS-Richtlinie, die jailbroken von Geräten blockiert. Apply (genannt "Assign" in InTune) die Richtlinie auf ein Pilotprojekt oder eine Testgruppe. Fügen Sie der Pilotgruppe nach dem ersten testen weitere Benutzer hinzu. Mithilfe eines stufenweisen Ansatzes können Sie Feedback aus einer Vielzahl von Benutzertypen erhalten.

Weitere Informationen finden Sie unter [Erste Schritte mit Geräte Konformitätsrichtlinien](https://docs.microsoft.com/intune/device-compliance-get-started) und Informationen [zum bedingten Zugriff und zu InTune](https://docs.microsoft.com/intune/conditional-access) .

## <a name="step-7-apply-features-and-settings"></a>Schritt 7: Anwenden von Features und Einstellungen

Diese Features und Einstellungen werden häufig als der "coole" Teil von InTune betrachtet und sind sehr leistungsfähig. Nachdem Sie einige Konformitätsrichtlinien mithilfe des bedingten Zugriffs erfolgreich durchgesetzt haben, können Sie **Geräteprofile**erstellen.

InTune im [Azure-Portal](https://portal.azure.com) ermöglicht Ihnen das Erstellen unterschiedlicher Profile basierend auf Ihrer Geräteplattform – IOS, macOS, Android und Windows. Beispielsweise können Sie folgende Aktionen ausführen:

- Verwenden Sie den Endpunktschutz auf Windows 10-Geräten, um verschiedene BitLocker-Optionen einschließlich Verschlüsselung zu aktivieren.
- Verwenden Sie das Feature für eingeschränkte apps auf IOS-Geräten, um eine Liste der genehmigten apps zu erstellen, die installiert werden können. Oder erstellen Sie eine Liste der verbotenen apps.
- Verwenden Sie die Kiosk Einstellungen, um auszuwählen, welche apps auf Android-Geräten verwendet werden können, die im Kiosk-Modus ausgeführt werden.
- Wenden Sie auf Geräten mit macOS eine WLAN-Verbindung und deren Einstellungen einschließlich des Sicherheitstyps an.

Das [Anwenden von Features und Einstellungen auf Ihren Geräten mithilfe von Geräteprofilen](https://docs.microsoft.com/intune/device-profiles) eignet sich hervorragend zum Lesen von Profilen, Informationen zum Erstellen eines Profils und vieles mehr.

Denken Sie daran, beginnen Sie klein, und verwenden Sie einen mehrstufigen Ansatz. Weisen Sie das Profil einem Pilotprojekt oder einer Testgruppe zu. Weisen Sie dann das Profil mehreren Pilotgruppen zu.

## <a name="step-8-get-to-know-the-other-features"></a>Schritt 8: Kennenlernen der anderen Features

InTune ist ein leistungsstarker Dienst mit vielen Features. Im folgenden finden Sie einige andere Aufgaben, die Sie mit InTune ausführen können:

- Verwalten von Software und Updates auf [](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)auf Windows-Geräten und [IOS](https://docs.microsoft.com/intune/software-updates-ios) -Geräten
- Aktivieren Sie [Microsoft Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) auf Ihren Windows 10-Geräten, und verwenden Sie Compliance und bedingten Zugriff, um den Zugriff auf Unternehmensressourcen wie SharePoint oder Exchange Online zu schützen.
- Verwenden von [Lookout](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)und anderen Partnern für Mobile Verteidigungs Bedrohungen
- Hinzufügen einer [Partnerzertifizierungsstelle (Certification Authority, ca)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) zum ausgeben und erneuern von Zertifikaten
- [Bereitstellen von Anleitungen für Endbenutzer](https://docs.microsoft.com/intune/end-user-educate) in der Unternehmens Portal-APP, zum erhalten von apps und mehr
- Überwachen von [apps](https://docs.microsoft.com/intune/apps-monitor) und [Geräte Konformität und Konfigurationsprofilen](https://docs.microsoft.com/intune/compliance-policy-monitor)und mehr Telemetrie mithilfe der Überwachungsprotokolle. Sie können auch eine Verbindung mit dem [InTune-Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) herstellen und Power BI für noch mehr Berichtsanforderungen verwenden.


## <a name="identity-and-device-access-recommendations"></a>Empfehlungen für den Identitäts- und Gerätezugriff

Microsoft stellt eine Reihe von Empfehlungen für [Identität und Gerätezugriff](microsoft-365-policies-configurations.md) bereit, um sicherzustellen, dass die Mitarbeiter sicher und produktiv arbeiten können. Verwenden Sie für den Geräte Zugriff die Empfehlungen und Einstellungen in den folgenden Artikeln zusammen mit den Schritten in dieser Phase:

- [Voraussetzungen](identity-access-prerequisites.md)
- [Allgemeine Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie, wie IT-Experten bei Microsoft [Geräte mit EMS verwalten](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [Ihre Infrastruktur für Mobile Geräteverwaltung](contoso-mdm.md) mit Microsoft 365 Cloud Services bereitgestellt hat.

![Die Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Infrastruktur der mobilen Geräteverwaltung](mobility-infrastructure-exit-criteria.md)

