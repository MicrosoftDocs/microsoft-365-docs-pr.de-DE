---
title: Die 12 Am besten 12 Aufgaben für Sicherheitsteams, die die Arbeit von zu Hause aus unterstützen
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: Schützen Sie Ihre Geschäftlichen E-Mails und Daten vor Cyberbedrohungen, einschließlich Ransomware, Phishing und schädlichen Anlagen.
ms.openlocfilehash: a1850438d02042ba5931a6208b82f74766ae0be8
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097270"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>Die 12 Am besten 12 Aufgaben für Sicherheitsteams, die die Arbeit von zu Hause aus unterstützen

Wenn Sie Wie [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) sind und plötzlich feststellen, dass sie hauptsächlich heimbasierte Mitarbeiter unterstützen, möchten wir Ihnen dabei helfen, sicherzustellen, dass Ihre Organisation so sicher wie möglich arbeitet. In diesem Artikel werden Aufgaben priorisiert, mit deren Hilfe Sicherheitsteams die wichtigsten Sicherheitsfunktionen so schnell wie möglich implementieren können.

![Führen Sie diese Hauptaufgaben aus, um die Arbeit von zu Hause aus zu unterstützen.](../media/security/security-support-remote-work.png)

Wenn Sie eine kleine oder mittelständische Organisation sind, die einen der Geschäftspläne von Microsoft verwendet, sehen Sie sich stattdessen die folgenden Ressourcen an:

- [Die 10 besten Methoden zum Sichern von Office 365- und Microsoft 365 Business-Plänen](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 für Kampagnen](https://docs.microsoft.com/microsoft-365/campaigns/) (enthält eine empfohlene Sicherheitskonfiguration für Microsoft 365 Business)

Für Kunden, die unsere Unternehmenspläne verwenden, empfiehlt Microsoft, die in der folgenden Tabelle aufgeführten Aufgaben auszuführen, die für Ihren Serviceplan gelten. Wenn Sie anstelle eines Microsoft 365 -Enterprise-Plans Abonnements kombinieren, beachten Sie Folgendes:

- Microsoft 365 E3 umfasst Enterprise Mobility + Security (EMS) E3 und Azure AD P1
- Microsoft 365 E5 umfasst EMS E5 und Azure AD P2

****

|Schritt|Aufgabe|Alle Office 365 Enterprise-Pläne|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1 |[Aktivieren der mehrstufigen Azure AD-Authentifizierung (MFA)](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2 |[Schutz vor Bedrohungen](#2-protect-against-threats)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Konfigurieren von Microsoft Defender für Office 365](#3-configure-microsoft-defender-for-office-365)|||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Konfigurieren von Microsoft Defender for Identity](#4-configure-microsoft-defender-for-identity)|||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Aktivieren von Microsoft 365 Defender](#5-turn-on-microsoft-365-defender)|||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Konfigurieren von Intune Mobile App Protection für Smartphones und Tablets](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Konfigurieren von MFA und bedingten Zugriff für Gäste, einschließlich Intune-App-Schutz](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Registrieren von PCs für die Geräteverwaltung und Erfordern kompatibler PCs](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Optimieren Ihres Netzwerks für cloudbasierte Konnektivität](#9-optimize-your-network-for-cloud-connectivity)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[Benutzer trainieren](#10-train-users)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Erste Schritte mit Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security)|||![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[Überwachen auf Bedrohungen und Ergreifen von Maßnahmen](#12-monitor-for-threats-and-take-action)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

Bevor Sie beginnen, überprüfen Sie Ihre [Microsoft 365-Sicherheitsüberprüfung](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) im Microsoft 365 Security Center. Über ein zentrales Dashboard können Sie die Sicherheit für Ihre Microsoft 365-Identitäten, -Daten, -Apps, -Geräte und -Infrastruktur überwachen und verbessern. Sie erhalten Punkte zum Konfigurieren empfohlener Sicherheitsfeatures, zum Ausführen sicherheitsbezogener Aufgaben (z. B. zum Anzeigen von Berichten) oder zum Adressieren von Empfehlungen mit einer Drittanbieteranwendung oder -software. Die empfohlenen Aufgaben in diesem Artikel erhöhen Ihre Bewertung.

![Screenshot der Microsoft Secure Score](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Aktivieren der mehrstufigen Azure AD-Authentifizierung (MFA)

Das Beste, was Sie tun können, um die Sicherheit für Mitarbeiter zu verbessern, die von zu Hause aus arbeiten, ist das Aktivieren der MFA. Wenn Noch keine Prozesse vorhanden sind, behandeln Sie dies als Notfallpilot, und stellen Sie sicher, dass Supportmitarbeiter bereit sind, um Mitarbeiter zu unterstützen, die nicht weiterkommen. Da Hardwaresicherheitsgeräte wahrscheinlich nicht verteilt werden können, verwenden Sie biometrische Windows Hello- und Smartphone-Authentifizierungs-Apps wie Microsoft Authenticator.

In der Regel empfiehlt Microsoft, Benutzern 14 Tage Zeit zu geben, um ihr Gerät für die mehrstufige Authentifizierung zu registrieren, bevor MFA erforderlich ist. Wenn Ihre Mitarbeiter jedoch plötzlich von zu Hause aus arbeiten, müssen Sie MFA als Sicherheitspriorität benötigen und darauf vorbereitet sein, Benutzern zu helfen, die sie benötigen.

Die Anwendung dieser Richtlinien dauert nur ein paar Minuten, ist jedoch darauf vorbereitet, Ihre Benutzer in den nächsten Tagen zu unterstützen.

****

|Plan|Empfehlung|
|---|---|
|Microsoft 365-Pläne (ohne Azure AD P1 oder P2)|[Aktivieren Sie die Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Zu den Sicherheitsstandards in Azure AD gehört MFA für Nutzer und Administratoren.|
|Microsoft 365 E3 (mit Azure AD P1)|Verwenden Sie [Allgemeine Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common), um die folgenden Richtlinien zu konfigurieren: <br/>- [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [MFA für alle Nutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [Blockieren von Legacy-Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (mit Azure AD P2)|Nutzen Sie den Azure AD-Identity Protection, beginnen Sie mit der Implementierung des von Microsoft [empfohlenen Satzes von bedingtem Zugriff und zugehörigen Richtlinien](./office-365-security/identity-access-policies.md), indem Sie die folgenden 2 Richtlinien nutzen:<br/> - [MFA erforderlich, wenn das Anmelderisiko mittel oder hoch ist](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [Nutzer mit hohem Risiko müssen das Kennwort ändern](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2: Schutz vor Bedrohungen

Alle Microsoft 365-Pläne enthalten eine Vielzahl von Bedrohungsschutzfeatures. Das Einrichten des Schutzes für diese Features dauert nur ein paar Minuten.

- Schutz vor Schadsoftware
- Schutz vor schädlichen URLs und Dateien
- Antiphishingschutz
- Antispamschutz

Anleitungen, die Sie als Ausgangspunkt verwenden können, finden Sie unter "Schutz vor Bedrohungen [in Office 365".](office-365-security/protect-against-threats.md)

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Konfigurieren von Microsoft Defender für Office 365

Microsoft Defender für Office 365, enthalten in Microsoft 365 E5 und Office 365 E5, schützt Ihre Organisation vor böswilligen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. Die Konfiguration kann mehrere Stunden dauern.

Microsoft Defender für Office 365:

- Schützt Ihre Organisation vor unbekannten E-Mail-Bedrohungen in Echtzeit, indem intelligente Systeme verwendet werden, die Anlagen und Links auf schädliche Inhalte untersuchen. Diese automatisierten Systeme umfassen eine robuste Detonationsplattform, Heuristiken und Machine Learning-Modelle.
- Schützt Ihre Organisation, wenn Benutzer zusammenarbeiten und Dateien freigeben, indem schädliche Dateien in Teamwebsites und Dokumentbibliotheken identifiziert und blockiert werden.
- Wendet Machine Learning Modelle und erweiterte Algorithmen zur Erkennung von Identitätswechseln an, um Phishingangriffe zu verhindern.

Eine Übersicht, einschließlich einer Zusammenfassung der Pläne, finden Sie unter [Defender für Office 365](office-365-security/office-365-atp.md).

Ihr globaler Administrator kann die folgenden Schutzmaßnahmen konfigurieren:

- [Einrichten von Richtlinien für sichere Links](office-365-security/set-up-atp-safe-links-policies.md)
- [Konfigurieren der globalen Einstellungen für sichere Links](office-365-security/configure-global-settings-for-safe-links.md)
- [Einrichten von Richtlinien für sichere Anlagen](office-365-security/set-up-atp-safe-attachments-policies.md)

Sie müssen mit Ihrem Exchange Online- und SharePoint Online-Administrator zusammenarbeiten, um Defender für Office 365 für diese Workloads zu konfigurieren:

- [ATP für SharePoint, OneDrive und Microsoft Teams](office-365-security/atp-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Konfigurieren von Microsoft Defender for Identity

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ist eine cloudbasierte Sicherheitslösung, die Ihre lokalen Active Directory-Signale nutzt, um komplexe Bedrohungen, kompromittierte Identitäten und bösartige, gegen Ihre Organisation gerichtete Insideraktionen zu identifizieren, zu erkennen und zu untersuchen. Konzentrieren Sie sich als Nächstes darauf, da sie Ihre vor Ort und Ihre Cloudinfrastruktur schützt, keine Abhängigkeiten oder Voraussetzungen aufweist und sofortige Vorteile bieten kann.

- Informationen zum schnellen Einrichten [von Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) für Identitätsstarts finden Sie unter "Schnellstarts für Identitäten".
- Video [ansehen: Einführung in Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Überprüfen der [drei Phasen der Bereitstellung von Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Aktivieren von Microsoft 365 Defender

Nachdem Sie nun Microsoft Defender für Office 365 und Microsoft Defender for Identity konfiguriert haben, können Sie die kombinierten Signale dieser Funktionen in einem Dashboard anzeigen. [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) vereint Warnungen, Vorfälle, automatisierte Untersuchung und Reaktion sowie die erweiterte Suche über Workloads hinweg (Microsoft Defender for Identity, Defender für Office 365, Microsoft Defender für Endpoint und Microsoft Cloud App Security) in einem einzigen Bereich unter [security.microsoft.com](https://security.microsoft.com).

![Abbildung des MTP-Dashboards](../media/top-ten-security-remote-work-mtp-dashboard.png)

Nachdem Sie einen oder mehrere Ihrer Defender für Office 365-Dienste konfiguriert haben, aktivieren Sie MTP. Neue Features werden MTP kontinuierlich hinzugefügt. Erwägen Sie, sich für den Erhalt von Vorschaufeatures zu entscheiden.

- [Weitere Informationen zu MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Aktivieren von MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
- [Melden Sie sich für Vorschaufeatures an.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Konfigurieren von Intune Mobile App Protection für Smartphones und Tablets

Mit Microsoft Intune Mobile Application Management (MAM) können Sie die Daten Ihrer Organisation auf Smartphones und Tablets verwalten und schützen, ohne diese Geräte zu verwalten. So funktioniert es:

- Sie erstellen eine App-Schutz-Richtlinie (APP), die bestimmt, welche Apps auf einem Gerät verwaltet werden und welche Verhaltensweisen zulässig sind (z. B. verhindern, dass Daten aus einer verwalteten App in eine nicht verwaltete App kopiert werden). Sie erstellen eine Richtlinie für jede Plattform (iOS, Android).
- Nachdem Sie die App-Schutzrichtlinien erstellt haben, erzwingen Sie diese, indem Sie eine Regel für bedingten Zugriff in Azure AD erstellen, um genehmigte Apps und den Schutz von APP-Daten zu erfordern.

Die Richtlinien für den Schutz von APPS umfassen viele Einstellungen. Glücklicherweise müssen Sie nicht jede Einstellung lesen und die Optionen abwägen. Microsoft erleichtert die Anwendung einer Konfiguration von Einstellungen, indem es Ausgangspunkte empfiehlt. Das [Datenschutzframework unter Verwendung von App-Schutzrichtlinien](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) umfasst drei Ebenen, aus der Sie wählen können.

Noch besser koordiniert Microsoft dieses App-Schutz-Framework mit einer Reihe von bedingten Zugriffen und zugehörigen Richtlinien, die von allen Organisationen als Ausgangspunkt empfohlen werden. Wenn Sie MFA mithilfe der Anleitungen in diesem Artikel implementiert haben, sind Sie auf halber Weg!

Verwenden Sie zum Konfigurieren des Schutzes mobiler Apps die Anleitungen in [allgemeinen Identitäts- und Gerätezugriffsrichtlinien:](./office-365-security/identity-access-policies.md)

 1. Verwenden Sie die [Richtlinien zum Anwenden von APP-Datenschutzrichtlinien,](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) um Richtlinien für iOS und Android zu erstellen. Ebene 2 (erweiterter Datenschutz) wird für den grundlegenden Schutz empfohlen.
 2. Erstellen Sie eine Regel für bedingten Zugriff, um [genehmigte Apps und den App-Schutz zu erfordern.](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Konfigurieren von MFA und bedingten Zugriff für Gäste, einschließlich Intune Mobile App Protection

Als Nächstes stellen wir sicher, dass Sie weiterhin mit Gästen zusammenarbeiten und mit ihnen zusammenarbeiten können. Wenn Sie den Microsoft 365 E3-Plan verwenden und MFA für alle Benutzer implementiert haben, sind Sie festgelegt.

Wenn Sie den Microsoft 365 E5-Plan verwenden und Azure Identity Protection für risikobasierte MFA nutzen, müssen Sie einige Anpassungen vornehmen (da Azure AD Identity Protection nicht für Gäste gilt):

- Erstellen Sie eine neue Regel für bedingten Zugriff, damit MFA immer für Gäste und externe Benutzer erforderlich ist.
- Aktualisieren Sie die risikobasierte MFA-Regel für bedingten Zugriff, um Gäste und externe Benutzer auszuschließen.

Verwenden Sie die Anleitungen unter [Aktualisieren](./office-365-security/identity-access-policies-guest-access.md) der allgemeinen Richtlinien, um Gast- und externen Zugriff zu ermöglichen und zu schützen, um zu verstehen, wie der Gastzugriff mit Azure AD funktioniert, und um die betroffenen Richtlinien zu aktualisieren.

Die von Ihnen erstellten Intune-Richtlinien für den Schutz mobiler Apps gelten zusammen mit der Regel für bedingten Zugriff, um genehmigte Apps und den App-Schutz zu verlangen, für Gästekonten und tragen zum Schutz Ihrer Unternehmensdaten bei.

> [!NOTE]
> Wenn Sie PCs bereits für die Geräteverwaltung registriert haben, um kompatible PCs erforderlich zu machen, müssen Sie auch Gastkonten aus der Regel für bedingten Zugriff ausschließen, die die Gerätekonformität erzwingt.

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Registrieren von PCs für die Geräteverwaltung und Erfordern kompatibler PCs

Es gibt mehrere Methoden zum Registrieren der Geräte Ihrer Mitarbeiter. Jede Methode hängt von der Art des Besitzes des Geräts (privat oder geschäftlich), vom Gerätetyp (iOS, Windows, Android) und von Verwaltungsanforderungen (Zurücksetzungen, Affinität, Sperrung) ab. Dies kann einige Zeit dauern, bis die Sortierung durchgeführt wurde. Siehe: [Registrieren von Geräten in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/).

Der schnellste Weg, um zu gehen, ist das [Einrichten der automatischen Registrierung für Windows 10-Geräte.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

Sie können auch die folgenden Lernprogramme nutzen:

- [Verwenden von Autopilot zum Registrieren von Windows-Geräten in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Verwenden der Registrierungsfunktionen für Unternehmensgeräte von Apple in Apple Business Manager (ABM) zum Registrieren von iOS-/iPadOS-Geräten in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Verwenden Sie nach der Registrierung von Geräten die Anleitungen in [allgemeinen Identitäts- und](./office-365-security/identity-access-policies.md) Gerätezugriffsrichtlinien, um diese Richtlinien zu erstellen:

- [Definieren von Richtlinien für die Gerätekonformität](./office-365-security/identity-access-policies.md#define-device-compliance-policies) – Die empfohlenen Einstellungen für Windows 10 umfassen das Erfordern von Antivirusschutz. Wenn Sie über Microsoft 365 E5 verfügen, verwenden Sie Microsoft Defender for Endpoint, um die Integrität von Mitarbeitergeräten zu überwachen. Stellen Sie sicher, dass die Konformitätsrichtlinien für andere Betriebssysteme Antivirenschutz und Endpunktschutzsoftware enthalten.
- [Kompatible PCs erforderlich](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) – Dies ist die Regel für bedingten Zugriff in Azure AD, die die Gerätekonformitätsrichtlinien erzwingt.

Nur eine Organisation kann ein Gerät verwalten. Schließen Sie daher Gastkonten aus der Regel für bedingten Zugriff in Azure AD aus. Wenn Sie Gastbenutzer und externe Benutzer nicht von Richtlinien ausschließen, die Gerätekonformität erfordern, blockieren diese Richtlinien diese Benutzer. Weitere Informationen finden Sie unter [Aktualisieren der allgemeinen Richtlinien zum Zulassen und Schützen des Gast-](./office-365-security/identity-access-policies-guest-access.md)und externen Zugriffs.

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Optimieren Ihres Netzwerks für Cloudkonnektivität

Wenn Sie den Großteil Ihrer Mitarbeiter schnell von zu Hause aus arbeiten lassen, kann dieser plötzliche Wechsel von Verbindungsmustern erhebliche Auswirkungen auf die Unternehmensnetzwerkinfrastruktur haben. Viele Netzwerke wurden skaliert und entworfen, bevor Clouddienste übernommen wurden. In vielen Fällen sind Netzwerke für Remotemitarbeiter tolerant, wurden jedoch nicht für die gleichzeitige Remoteverwaltung durch alle Benutzer konzipiert.

Netzwerkelemente wie VPN-Schlüsse, zentrale Netzwerk-Ausgangsgeräte (z. B. Proxys und Geräte zur Verhinderung von Datenverlust), zentrale Internetbandbreite, Backhaul-MPLS-Schaltungen, NAT-Funktionen und so weiter werden plötzlich aufgrund der Last des gesamten Unternehmens, das sie verwendet, stark belastet. Das Endergebnis ist eine schlechte Leistung und Produktivität zusammen mit einer schlechten Benutzererfahrung für Benutzer, die sich an die Arbeit von zu Hause aus anpassen.

Einige der Schutzmaßnahmen, die traditionell durch die Zurückleitung von Datenverkehr über ein Unternehmensnetzwerk bereitgestellt wurden, werden von den Cloud-Apps bereitgestellt, auf die Ihre Benutzer zugreifen. Wenn Sie diesen Schritt in diesem Artikel erreicht haben, haben Sie eine Reihe komplexer Cloudsicherheitssteuerelemente für Microsoft 365-Dienste und -Daten implementiert. Wenn diese Steuerelemente verfügbar sind, können Sie den Datenverkehr von Remotebenutzern direkt an Office 365 weiter routen. Wenn Sie weiterhin eine VPN-Verbindung für den Zugriff auf andere Anwendungen benötigen, können Sie Die Leistung und die Benutzerfreundlichkeit durch die Implementierung von geteilten Tunnelings erheblich verbessern. Sobald Sie eine Vereinbarung in Ihrer Organisation erzielt haben, kann dies innerhalb eines Tages von einem gut koordinierten Netzwerkteam erreicht werden.

Weitere Informationen finden Sie in diesen Ressourcen unter "Dokumente":

- [Übersicht: Optimieren der Konnektivität für Remotebenutzer mithilfe von geteilten VPN-Tunneling](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementieren eines geteilten VPN-Tunnels für Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Aktuelle Blogartikel zu diesem Thema:

- [Schnelles Optimieren des Datenverkehrs für Remotemitarbeiter & die Auslastung Ihrer Infrastruktur zu reduzieren](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternative Möglichkeiten für Sicherheitsexperten und IT, moderne Sicherheitskontrollen in den heutigen einzigartigen Remotearbeitsszenarien zu erreichen](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: Schulen von Benutzern

Schulungsbenutzer können Ihren Benutzern und Ihrem Sicherheitsteam viel Zeit und Frustration sparen. Versierte Benutzer sind weniger wahrscheinlich, Anlagen zu öffnen oder auf Links in fragwürdigen E-Mail-Nachrichten zu klicken, und sie vermeiden eher verdächtige Websites.

Das Handbuch zur [Cybersicherheitskampagne](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) der "University University" bietet hervorragende Anleitungen zum Aufbau einer starken Kultur des Sicherheitsbewusstseins in Ihrer Organisation, einschließlich der Schulung von Benutzern zur Identifizierung von Phishingangriffen.

Microsoft 365 bietet die folgenden Ressourcen, um Benutzer in Ihrer Organisation zu informieren:

****

|Konzept|Ressourcen|
|---|---|
|Microsoft 365|[Anpassbare Lernpfade](https://docs.microsoft.com/office365/customlearning/) <p>Diese Ressourcen können Ihnen dabei helfen, Schulungen für Endbenutzer in Ihrer Organisation zusammen zu stellen.|
|Microsoft 365 Security|[Lernmodul: Sichern Ihrer Organisation mit integrierter, intelligenter Sicherheit von Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>In diesem Modul können Sie beschreiben, wie Microsoft 365-Sicherheitsfeatures zusammenarbeiten und welche Vorteile diese Sicherheitsfeatures bieten.|
|Mehrstufige Authentifizierung|[Überprüfung in zwei Schritten: Was ist die zusätzliche Überprüfungsseite?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Dieser Artikel hilft Endbenutzern zu verstehen, was die mehrstufige Authentifizierung ist und warum sie in Ihrer Organisation verwendet wird.|
|

Zusätzlich zu dieser Anleitung empfiehlt Microsoft Ihren Benutzern, die in diesem Artikel beschriebenen Aktionen zu ergreifen: Schützen Ihres Kontos und Ihrer Geräte [vor Hackern und Schadsoftware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Diese setzen sich wie folgt zusammen:

- Verwenden von starken Kennwörtern
- Schützen von Geräten
- Aktivieren von Sicherheitsfeatures auf Windows 10- und Mac-PCs (für nicht verwaltete Geräte)

Microsoft empfiehlt benutzern außerdem, ihre persönlichen E-Mail-Konten zu schützen, indem sie die in den folgenden Artikeln empfohlenen Aktionen ausführen:

- [Schützen Ihres E Outlook.com-E-Mail-Kontos](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Schützen Ihres Gmail-Kontos mit der Überprüfung in zwei Schritten](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Erste Schritte mit Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) bietet umfassende Transparenz, Kontrolle über den Datenverkehr und komplexe Analysen, um Cyberbedrohungen in allen Ihren Clouddiensten zu identifizieren und zu bekämpfen. Sobald Sie mit Cloud App Security beginnen, werden Richtlinien für die Anomalieerkennung automatisch aktiviert, aber Cloud App Security hat einen anfänglichen Lernzeitraum von sieben Tagen, in dem nicht alle Anomalieerkennungswarnungen ausgelöst werden.

Beginnen Sie jetzt mit Cloud App Security. Später können Sie komplexere Überwachungen und Kontrollen einrichten.

- [Schnellstart: Erste Schritte mit Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Sofortige Verhaltensanalyse und Anomalieerkennung](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Weitere Informationen zu Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Überprüfen neuer Features und Funktionen](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Grundlegende Setupanweisungen](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Überwachen auf Bedrohungen und Ergreifen von Maßnahmen

Microsoft 365 bietet verschiedene Möglichkeiten, den Status zu überwachen und geeignete Maßnahmen zu ergreifen. Der beste Ausgangspunkt ist das Microsoft 365 Security Center ( ), in dem Sie die Microsoft Secure Score Ihrer Organisation sowie alle Warnungen oder Entitäten anzeigen können, die Ihre Aufmerksamkeit [https://security.microsoft.com](https://security.microsoft.com) erfordern. [](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

- [Erste Schritte mit dem Microsoft 365 Security Center](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Überwachen und Anzeigen von Berichten](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Siehe die Sicherheitsportale in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Nächste Schritte

Herzlichen Glückwunsch! Sie haben schnell einige der wichtigsten Sicherheitsvorkehrungen implementiert, und Ihre Organisation ist wesentlich sicherer. Jetzt können Sie mit den Funktionen zum Schutz vor Bedrohungen (einschließlich Microsoft Defender for Endpoint), datenklassifizierung und Schutzfunktionen und dem Sichern von Administratorkonten noch weiter gehen. Eine tiefer gehende, methodische Reihe von Sicherheitsempfehlungen für Microsoft 365 finden Sie unter [Microsoft 365 Security for Business Decision Makers (BDMs).](Microsoft-365-security-for-bdm.md)

Besuchen Sie auch das neue Sicherheitscenter von Microsoft auf [docs.microsoft.com/security](https://docs.microsoft.com/security).
