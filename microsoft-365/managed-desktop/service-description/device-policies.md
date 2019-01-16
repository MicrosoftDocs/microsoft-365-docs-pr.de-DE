---
title: Gerätekonfiguration
description: Informationen Sie zu den Standardrichtlinien an Microsoft verwalteter Desktop Geräte angewendet.
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868006"
---
# <a name="device-configuration"></a>Gerätekonfiguration


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Wenn ein neues Microsoft verwalteter Desktop-Gerät bereitgestellt wird, stellen wir sicher, dass die Rechte für Microsoft verwalteter Desktop optimierte Konfiguration vorhanden ist. Dies umfasst eine Reihe von Standardrichtlinien, die im Rahmen des Prozesses Onboarding festgelegt sind. Um Konflikte zu vermeiden, sollten diese Richtlinien nicht geändert werden. 

Geräte werden mit einer Signaturbild eintreffen und dann Azure Active Directory-Domäne beitreten, wenn der erste Benutzer anmeldet. Das Gerät installiert automatisch Erforderlicher Richtlinien und Anwendungen ohne Eingriff IT benötigt.

## <a name="why-mdm-over-group-policy"></a>Warum MDM über Gruppenrichtlinien

Es gibt einige Gründe für die Verwaltung von mobilen Geräten (MDM) anstelle von Gruppenrichtlinien verwenden:

- Sicherheit - sind MDM Richtlinien in der modernen Welt sicherer. Gruppenrichtlinien ist darauf ausgelegt, am besten mit lokalen Identität Arbeit während des MDM entwickelt für Funktion am besten mit Cloud Identitätsmanagement (Azure Active Directory).
- Zuverlässigkeit - MDM Richtlinien bieten mehr zuverlässige Bereitstellung von Gruppenrichtlinien. Darüber hinaus überschreiben MDM-Einstellungen (Group Policy Object, GPO) Richtlinien. Beginnend mit Windows Version 1803 10, werden MDM Einstellungen über die Werte von Gruppenrichtlinien priorisiert werden der Kunden, wechseln zu Verwaltung der modernen unterstützt. 
- Richten Sie mit Microsoft verwalteter Desktop Vision – bietet umfassendere Überwachung auf Bereitstellung von Gruppenrichtlinien und Arbeitsgruppen-Methode für die schrittweise Einführung Richtlinie Änderungen mit Möglichkeit zum anhalten / fortsetzen bei Bedarf Bereitstellung unterstützt.

Weitere Informationen finden Sie unter [Verwaltung mobiler Geräte](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Standardrichtlinien

In dieser Tabelle werden die Standard-Richtlinien, die an alle Geräte von Microsoft verwalteten Desktops während der Bereitstellung Gerät angewendet werden. Alle erkannt, dass die Änderungen, die nicht von Microsoft verwalteten Desktops Vorgänge Team auf Objekte, die von Microsoft verwaltet Desktop verwaltet genehmigt werden wiederhergestellt werden.

Richtlinie | Beschreibung
--- | ---
Security baseline | [Microsoft Security Baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) für MDM ist für alle Microsoft verwalteter Desktop Geräte konfiguriert. Dieser Baseline ist die Industriestandard-Konfiguration. Öffentlich freigegeben ist, wird ebenfalls getestet, und wurden durch Microsoft Security-Experten zu Microsoft verwalteter Desktop Geräte geprüft und apps secure modernen am Arbeitsplatz.<br><br>Zum Verringern von Bedrohungen in die ständig wachsenden Sicherheit Bedrohung Querformat ein, werden die Microsoft Security Baseline aktualisiert und an Microsoft verwalteter Desktop Geräte bei jeder Aktualisierung der Windows-10-Feature bereitgestellt.<br><br>Weitere Informationen finden Sie unter [Security Baseline für Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Microsoft verwalteter Desktop Sicherheitsvorlage empfohlen | Eine Reihe von Empfohlene Änderungen an der Basislinie Sicherheit, die Benutzer zu optimieren.  Diese Änderungen werden in [Der Security Addendum](#security-addendum)dokumentiert. Updates für die Richtlinie Addendum treten bei Bedarf.  
Gerät-compliance | Diese Richtlinien werden standardmäßig für alle Microsoft verwalteter Desktop Geräte konfiguriert. Ein Gerät wird als nicht kompatible gemeldet, wenn eine der folgenden Security Bedingungen nicht erfüllt ist:<br>-BitLocker Geräteverschlüsselung aktiviert, um Daten auf Geräten zu schützen. Weitere Informationen finden Sie unter [Übersicht der BitLocker Geräteverschlüsselung in Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Sicheren Boot aktiviert und erzwungen, um die firmwareabbilder auf Geräten zu überprüfen, bevor sie ausgeführt werden können. Weitere Informationen finden Sie unter [Secure Boot und Gerät Übersicht über die Verschlüsselung.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Microsoft verwalteter Desktop-Gerät muss das Kennwort für die Anmeldung.
Update-Bereitstellung | Verwenden Sie Windows Update für Unternehmen (WUfB) zum schrittweisen Bereitstellung von Softwareupdates ausführen. IT-Administratoren können Einstellungen für die Bereitstellung von Gruppenrichtlinien nicht ändern. Weitere Informationen über die Arbeitsgruppen-Bereitstellung finden Sie unter [wie Updates behandelt werden](../working-with-managed-desktop/updates.md).
Telemetrie | Geräte werden unter einem bekannten kommerziellen Bezeichner erweiterte Diagnosedaten an Microsoft übermitteln festgelegt. Als Teil des Microsoft verwalteten Desktops können IT-Administratoren diese Einstellungen nicht ändern. Für Kunden im Allgemeinen Regionen Data Protection Regulierung (GDPR), Endbenutzer können reduziert die Ebene der Diagnosedaten, die bereitgestellt wird, aber eine Verringerung der Dienst werden. Beispielsweise werden Microsoft verwalteter Desktop kann nicht zum Sammeln der Daten erforderlich sind, um auf Einstellungen und Richtlinien, um optimale Leistung und Sicherheit Bedürfnisse durchlaufen. Weitere Informationen finden Sie unter [Diagnosedaten in Ihrer Organisation konfigurieren von Windows.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Security addendum

 Dieser Abschnitt stellt die Richtlinien, die als zusätzlich zu den Microsoft verwalteter Desktop Standardrichtlinien bereitgestellt werden soll. Standardrichtlinien sind in [die Standardrichtlinien](#default-policies)aufgeführt. Diese Konfiguration ist darauf ausgelegt, mit Finanzdienstleister und stark regulierten Branchen im Hinterkopf: Optimieren für die sicherste Abwehr Benutzer Produktivität zu beeinträchtigen.

 ### <a name="additional-security-policies"></a>Zusätzliche Sicherheitsrichtlinien

 Diese Richtlinien werden zur Verbesserung der Sicherheit für stark regulierten Branchen hinzugefügt. 
 - **App-Zulassungsliste**: Apps zur Ausführung in Microsoft verwalteter Desktop Geräte der Organisation vertrauenswürdig sein müssen. Dadurch wird die eine gesperrten Umgebung. Das Desktop Vorgänge Team von Microsoft verwaltet mitzuteilen alle apps, die Onboarded werden müssen. Weitere Informationen finden Sie unter [Windows Defender Gerät Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Überwachung der Sicherheit**: Microsoft überwacht Geräten über [Windows Defender erweiterte Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Wenn eine Bedrohung erkannt werden, wird Microsoft benachrichtigen der Kunde, das Gerät zu isolieren und Remote, das Problem beheben. 

