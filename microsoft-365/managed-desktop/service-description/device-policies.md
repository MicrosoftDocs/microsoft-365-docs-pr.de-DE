---
title: Gerätekonfiguration
description: Informationen Sie zu den Standardrichtlinien an Microsoft verwalteter Desktop Geräte angewendet.
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 5a97f44641ac38a8785bde66819dbfffffee946d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868006"
---
# <a name="device-configuration"></a>Gerätekonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wenn ein neues Microsoft verwalteter Desktop-Gerät bereitgestellt wird, stellen wir sicher, dass die Rechte für Microsoft verwalteter Desktop optimierte Konfiguration vorhanden ist. Dies umfasst eine Reihe von Standardrichtlinien, die im Rahmen des Prozesses Onboarding konfiguriert sind. Um Konflikte zu vermeiden, sollten diese Richtlinien nicht geändert werden. 

Geräte werden mit einer Signaturbild eintreffen und dann Azure Active Directory-Domäne beitreten, wenn der erste Benutzer anmeldet. Das Gerät installiert automatisch Erforderlicher Richtlinien und Anwendungen ohne Eingriff IT benötigt.

## <a name="why-mdm-over-group-policy"></a>Warum MDM über Gruppenrichtlinien

Es gibt einige Gründe für die Verwaltung von mobilen Geräten (MDM) anstelle von Gruppenrichtlinien verwenden:

- Sicherheit - sind MDM Richtlinien in der modernen Welt sicherer. Gruppenrichtlinien entwickelt für Funktion am besten mit lokalen Identität. MDM Cloud Identitätsmanagement (Azure Active Directory (AD Azure)) am besten entwickelt.
- Zuverlässigkeit - MDM Richtlinien bieten mehr zuverlässige Bereitstellung von Gruppenrichtlinien. MDM Einstellungen überschreiben (Group Policy Object, GPO) Richtlinien. MDM Einstellungen wird beginnend mit Windows 10, Version 1803, über die Gruppenrichtlinien-Werte priorisiert. Kunden, wechseln zu Verwaltung der modernen unterstützt werden. 
- Richten Sie mit Microsoft verwalteter Desktop Vision - besser überwachen auf Bereitstellung von Gruppenrichtlinien. Unterstützung von Anrufen-basierten Ansatz für schrittweise Einführung Richtlinie Änderungen mit Möglichkeit zum Anhalten / Fortsetzen Bereitstellung bei Bedarf.

## <a name="default-policies"></a>Standardrichtlinien

Diese Tabelle Highlights, die Standard-Richtlinien, die an alle Geräte von Microsoft verwalteten Desktops während der Bereitstellung Gerät angewendet werden. Um einen Konflikt zu vermeiden, sollten diese Richtlinien nicht geändert werden. Alle erkannt, dass die Änderungen, die nicht von Microsoft verwalteten Desktops Vorgänge Team auf Objekte, die von Microsoft verwaltet Desktop verwaltet genehmigt werden wiederhergestellt werden.

Richtlinie | Beschreibung
--- | ---
Security baseline | [Microsoft Security Baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) für MDM ist für alle Microsoft verwalteter Desktop Geräte konfiguriert. Dieser Baseline ist die Industriestandard-Konfiguration. Öffentlich freigegeben ist, wird ebenfalls getestet, und wurden durch Microsoft Security-Experten zu Microsoft verwalteter Desktop Geräte geprüft und apps secure modernen am Arbeitsplatz.<br><br>Zum Verringern von Bedrohungen in die ständig wachsenden Sicherheit Bedrohung Querformat ein, werden die Microsoft Security Baseline aktualisiert und an Microsoft verwalteter Desktop Geräte bei jeder Aktualisierung der Windows-10-Feature bereitgestellt.<br><br>Weitere Informationen finden Sie unter [Security Baseline für Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Microsoft verwalteter Desktop Sicherheitsvorlage empfohlen | Eine Reihe von Empfohlene Änderungen an der Basislinie Sicherheit, die Benutzer zu optimieren.  Diese Änderungen werden in [Der Security Addendum](#security-addendum)dokumentiert. Updates für die Richtlinie Addendum treten bei Bedarf.  
Gerät-compliance | Diese Richtlinien werden standardmäßig für alle Microsoft verwalteter Desktop Geräte konfiguriert. Ein Gerät wird als nicht kompatible gemeldet, wenn eine der folgenden Security Bedingungen nicht erfüllt ist:<br>-BitLocker Geräteverschlüsselung aktiviert, um Daten auf Geräten zu schützen. Weitere Informationen finden Sie unter [Übersicht der BitLocker Geräteverschlüsselung in Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Sicheren Boot aktiviert und erzwungen, um die firmwareabbilder auf Geräten zu überprüfen, bevor sie ausgeführt werden können. Weitere Informationen finden Sie unter [Secure Boot und Gerät Übersicht über die Verschlüsselung.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Zugriff auf Microsoft verwalteter Desktop Geräte erforderliche Kennwort.
Update-Bereitstellung | Verwenden Sie Windows Update für Unternehmen (WUfB) zum schrittweisen Bereitstellung von Softwareupdates ausführen. IT-Administratoren können die Einstellungen für die Bereitstellung Ring Richtlinien nicht ändern. Weitere Informationen über die Ring-basierte Bereitstellung finden Sie unter [wie Updates behandelt werden](../working-with-managed-desktop/updates.md).
Telemetrie | Geräte werden unter einem bekannten kommerziellen Bezeichner erweiterter Diagnosedaten an Microsoft übermitteln festgelegt. Kunden können im Allgemeinen Regionen Data Protection Regulierung (GDPR), Endbenutzer die Ebene der Diagnosedaten reduzieren, die bereitgestellt wird. Sie können dies anpassen eine Verringerung der Dienst werden jedoch. Weitere Informationen finden Sie unter [Diagnosedaten in Ihrer Organisation konfigurieren von Windows.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="advanced-policies"></a>Erweiterte Richtlinien

 Dies sind die zusätzlichen Richtlinien, die für eine Umgebung mehr secure/gesperrten für stark regulierten Branchen konfiguriert werden können.

 Richtlinie | Beschreibung
 --- | ---
 Erweiterte Funktionen | Windows Informationen Schutz (WIP) & Azure Informationen Schutz (per) werden verwendet, um Enterprise-Daten zu schützen, indem nur ermöglicht den Zugriff auf bestimmte Benutzer oder eine Teilmenge der Applications-Dienste. Weitere Informationen finden Sie unter<br>- [Schützen Sie Ihre Enterprise-Daten mithilfe von Windows INformation Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Azure Information Protection-Client-Administratorhandbuch](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [Microsoft verwaltete Desktopsicherheit Addendum](#security-addendum)

 ## <a name="security-addendum"></a>Security addendum

 Dieser Abschnitt stellt die Richtlinien, die als zusätzlich zu den Microsoft verwalteter Desktop Standardrichtlinien bereitgestellt werden soll. Standardrichtlinien sind in [die Standardrichtlinien](#default-policies)aufgeführt. Diese Konfiguration ist darauf ausgelegt, mit Finanzdienstleister und stark regulierten Branchen im Hinterkopf: Optimieren für die sicherste Abwehr Benutzer Produktivität zu beeinträchtigen.

Eine Änderung an der veröffentlichten **Security Baseline**wird die Einstellung [**nicht Netzwerkauswahl Benutzeroberfläche anzeigen**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowslogon#windowslogon-dontdisplaynetworkselectionui) deaktiviert.

 ### <a name="additional-security-policies"></a>Zusätzliche Sicherheitsrichtlinien

 Diese Richtlinien werden zur Verbesserung der Sicherheit für stark regulierten Branchen hinzugefügt. 
 - **App-Zulassungsliste**: Apps zur Ausführung in Microsoft verwalteter Desktop Geräte der Organisation vertrauenswürdig sein müssen. Dadurch wird die eine gesperrten Umgebung. Das Desktop Vorgänge Team von Microsoft verwaltet mitzuteilen alle apps, die Onboarded werden müssen. Weitere Informationen finden Sie unter [Windows Defender Gerät Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Überwachung der Sicherheit**: Microsoft überwacht Geräten über [Windows Defender erweiterte Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Wenn eine Bedrohung erkannt werden, wird Microsoft benachrichtigen der Kunde, das Gerät zu isolieren und Remote, das Problem beheben. 
 - **Guard ausnutzen**: Es wird sichergestellt, dass Microsoft verwalteter Desktop Geräte immer mit dem neuesten Sicherheitsupdate für Betriebssystem und apps, gesichert werden mithilfe von [Windows-Update für Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb). Angriff Guard wird mit diesen Einstellungen konfiguriert werden:

 Einstellung | Richtlinie
 --- | ---
 Kennzeichnen von Anmeldeinformationen, die vom Windows lokalen Behörde Teilsystem stehlen | Nur überwachen
 Office-apps in andere Prozesse einfügen | Nur überwachen
 Office-apps/Makros erstellen ausführbaren Inhalt | Blockieren
 Office-apps, die untergeordnete Prozesse starten | Nur überwachen
 Win32 importiert aus Office-Makrocode | Blockieren
 Verschleierte Js/Vbs/Ps/Makrocode | Blockieren
 Ausführen von Nutzlast Js/Vbs heruntergeladen Internet (Ausnahmen) | Blockieren
 Erstellung von PSExec und WMI-Befehlen | Nur überwachen
 Nicht vertrauenswürdige und nicht signierte Prozesse, die über USB ausführen | Blockieren
 Ausführbare Dateien, die eine Verbreitung, Alter oder Liste vertrauenswürdiger Kriterien nicht entsprechen. | Nur überwachen
 Ausführung der ausführbaren Inhalt aus e-Mail abgelegt | Blockieren
 Erweiterte Ransomware Schutz | Nur überwachen









