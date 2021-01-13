---
title: Gerätekonfiguration
description: Erfahren Sie mehr über die Standardrichtlinien, die auf Microsoft Managed Desktop-Geräte angewendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840331"
---
# <a name="device-configuration"></a>Gerätekonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wenn ein neues Microsoft Managed Desktop-Gerät eingerichtet wird, stellen wir sicher, dass es über die richtige Konfiguration verfügt, die für Microsoft Managed Desktop optimiert ist. Diese Konfiguration enthält eine Reihe von Standardrichtlinien, die im Rahmen des Onboardingprozesses festgelegt werden. Diese Richtlinien werden nach Möglichkeit mithilfe der Mobile Device Management (MDM) übermittelt. Weitere Informationen finden Sie unter [Verwaltung mobiler Geräte.](https://docs.microsoft.com/windows/client-management/mdm/) 

>[!NOTE]
>Um Konflikte zu vermeiden, ändern Sie diese Richtlinien nicht.

Geräte erhalten ein Signaturimage und treten dann der Azure Active Directory-Domäne bei, wenn sich der erste Benutzer meldet. Das Gerät installiert die erforderlichen Richtlinien und Anwendungen automatisch, ohne dass ihre Mitarbeiter eingreifen müssen.

## <a name="default-policies"></a>Standardrichtlinien

In dieser Tabelle werden die Standardrichtlinien aufgeführt, die während der Gerätebereitstellung auf alle Microsoft Managed Desktop-Geräte angewendet werden. Alle erkannten Änderungen, die nicht vom Microsoft Managed Desktop Operations Team an Objekten genehmigt wurden, die von Microsoft Managed Desktop verwaltet werden, werden zurückgesetzt.

Richtlinie | Beschreibung
--- | ---
Sicherheitsgrundlinie | [Die Sicherheitsbaseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) von Microsoft für MDM ist für alle Microsoft Managed Desktop-Geräte konfiguriert. Diese Grundlinie ist die Branchenstandardkonfiguration. Es wurde öffentlich veröffentlicht, gut getestet und von Sicherheitsexperten von Microsoft überprüft, um die Sicherheit von Microsoft Managed Desktop-Geräten und -Apps am modernen Arbeitsplatz zu gewährleisten. <br><br>Um Bedrohungen in der sich ständig weiterentwickelnden Sicherheitsbedrohungslandschaft zu mindern, wird die Sicherheitsgrundlinie von Microsoft mit jedem Windows 10-Featureupdate aktualisiert und auf Microsoft Managed Desktop-Geräten bereitgestellt.<br><br>Weitere Informationen finden Sie in den [Windows-Sicherheitsgrundwerten.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)
Empfohlene Sicherheitsvorlage für Microsoft Managed Desktop | Eine Reihe empfohlener Änderungen an der Sicherheitsbasislinie, die die Benutzerfreundlichkeit optimieren.  Diese Änderungen sind im Security [Addendum dokumentiert.](#security-addendum) Aktualisierungen der Richtlinienergänzung erfolgen bei Bedarf.  
Aktualisieren der Bereitstellung | Verwenden Sie Windows Update for Business, um die schrittweise Bereitstellung von Softwareupdates durchzuführen. It admins can't modify settings for the deployment group policies. Weitere Informationen zur gruppenbasierten Bereitstellung finden Sie unter So werden Updates [in Microsoft Managed Desktop behandelt.](updates.md)
Meterte Verbindungen | Standardmäßig sind Updates über meterte Verbindungen (z. B. LTE-Netzwerke) deaktiviert, obwohl jeder Benutzer dieses Feature unabhängig voneinander unter "Einstellungen > Updates und erweiterte Optionen" **> aktivieren kann.** Wenn Sie zulassen möchten, dass alle Benutzer Updates über meterte Verbindungen [aktivieren,](../working-with-managed-desktop/admin-support.md)senden Sie eine Änderungsanforderung, die diese Einstellung für alle Geräte aktiviert.
| Gerätekompatibilität | Diese Richtlinien sind für alle Microsoft Managed Desktop-Geräte konfiguriert. Ein Gerät wird als nicht konform gemeldet, wenn es von unserer erforderlichen Sicherheitskonfiguration abweht.

## <a name="windows-diagnostic-data"></a>Windows-Diagnosedaten

 Geräte werden so festgelegt, dass Microsoft unter einer bekannten kommerziellen ID erweiterte Diagnosedaten zur Verfügung stellt. Im Rahmen von Microsoft Managed Desktop können die ADMINISTRATOREN diese Einstellungen nicht ändern. Für Kunden in Regionen der DSGVO (DSGVO) können Benutzer die Bereitgestellte Diagnosedatenstufe reduzieren, es wird jedoch eine Verringerung des Diensts sein. Beispielsweise kann Microsoft Managed Desktop nicht die daten sammeln, die erforderlich sind, um Einstellungen und Richtlinien zu iterieren, um Leistungs- und Sicherheitsanforderungen optimal zu erfüllen. Weitere Informationen finden Sie unter ["Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation".](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Sicherheitsergänzung

 In diesem Abschnitt werden die Richtlinien beschrieben, die zusätzlich zu den standardmäßigen Microsoft Managed Desktop-Richtlinien bereitgestellt werden, die in den [Standardrichtlinien aufgeführt sind.](#default-policies) Diese Konfiguration ist auf Finanzdienstleistungen und stark regulierte Branchen ausgelegt und optimiert für die höchste Sicherheit bei gleichzeitiger Aufrechterhaltung der Benutzerproduktivität.

 ### <a name="additional-security-policies"></a>Zusätzliche Sicherheitsrichtlinien

 Diese Richtlinien werden hinzugefügt, um die Sicherheit für stark regulierte Branchen zu erhöhen. 
 - **Sicherheitsüberwachung:** Microsoft überwacht Geräte mit [Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Wenn eine Bedrohung erkannt wird, benachrichtigt Microsoft den Kunden, isoliert das Gerät und korrigiert das Problem remote. 
 - **PowerShell V2 deaktivieren:** Microsoft hat PowerShell V2 im August 2017 entfernt. Dieses Feature wurde auf allen Microsoft Managed Desktop-Geräten deaktiviert. Weitere Informationen zu dieser Änderung finden Sie unter [Windows PowerShell 2.0 Veraltet.](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)
