---
title: Verwalten von Geräten, die in der Verwaltung mobiler Geräte in Microsoft 365 registriert sind
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
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
description: Grundlegende Mobilität und Sicherheit können Ihnen helfen, Mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: e07ff0704afcb5bca1db4e2a5c2aff9c7d6008fd
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430173"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Verwalten von Geräten, die in der Verwaltung mobiler Geräte in Microsoft 365 registriert sind

Die integrierte Verwaltung mobiler Geräte für Microsoft 365 hilft Ihnen, die mobilen Geräte ihrer Benutzer wie iPhones, iPads, Androiden und Windows phones zu sichern und zu verwalten. Der erste Schritt besteht darin, sich bei Microsoft 365 anzumelden und grundlegende Mobilitäts-und Sicherheitseinstellungen einzurichten. Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).

Nachdem Sie es eingerichtet haben, müssen die Personen in Ihrer Organisation ihre Geräte im Dienst registrieren. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).Anschließend können Sie die grundlegende Mobilität und Sicherheit verwenden, um die Verwaltung von Geräten in Ihrer Organisation zu unterstützen. Beispielsweise können Sie Gerätesicherheitsrichtlinien verwenden, um den e-Mail-Zugriff oder andere Dienste einzuschränken, Geräte Berichte anzuzeigen und ein Gerät remote zu löschen. Diese Aufgaben werden normalerweise im Security & Compliance Center durchlaufen. Weitere Informationen finden Sie unter [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

## <a name="device-management-tasks"></a>Geräte Verwaltungsaufgaben

Führen Sie die folgenden Schritte aus, um zur geräteverwaltungskonsole zu gelangen:

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie in der Ergebnisliste die **Verwaltung mobiler Geräte**   aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Option für die Verwaltung mobiler Geräte":::

3. Wählen Sie  **Geräte verwalten**aus.

## <a name="manage-mobile-devices"></a>Verwalten von mobilen Geräten
    
Nachdem Sie grundlegende Mobilitäts-und Sicherheitseinstellungen eingerichtet haben, finden Sie hier einige Möglichkeiten zum Verwalten der mobilen Geräte in Ihrer Organisation.

|**Zweck**|**Aktion...**|
|:----------------|:------------------------------------------------------------------------------|
|Zurücksetzen eines Geräts |Wählen Sie im Bereich Geräteverwaltung die Option *Gerätename*und dann  **vollständige Löschung** aus,   um alle Informationen oder  **selektive** Zurücksetzung zu löschen,   um nur Organisationsinformationen auf dem Gerät zu löschen. Weitere Informationen finden Sie unter [wischen eines mobilen Geräts in Basic Mobility and Security](wipe-mobile-device.md).|
|Blockieren des Zugriffs auf Exchange-E-Mail für nicht unterstützte Geräte unter Verwendung von Exchange ActiveSync |Wählen Sie im Bereich Geräteverwaltung die Option  **blockieren**aus. |
|Einrichten von Geräterichtlinien wie Kennwortanforderungen und Sicherheitseinstellungen |Wählen Sie in der Gruppe Geräteverwaltung die Option **Gerätesicherheitsrichtlinien**   >  **Hinzufügen +** aus. Weitere Informationen finden Sie unter [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies.md).|
|Anzeigen des Liste blockierter Geräte  |Klicken Sie in der geräteverwaltungskonsole unter  **Wählen Sie eine Ansicht** auswählen auf     **blockiert**. |
|Entsperren eines nicht kompatiblen oder nicht unterstützten Geräts für einen Benutzer oder eine Benutzergruppe  |Wählen Sie eine der folgenden Optionen aus, um die Blockierung der Geräte aufzuheben:<br/>– Entfernen Sie den Benutzer oder die Benutzer aus der Sicherheitsgruppe, auf die die Richtlinie angewendet wurde. Wechseln Sie zu Microsoft 365 Admin Center > **Gruppen**, und wählen Sie dann Gruppenname aus. Wählen Sie **Mitglieder und Administratoren bearbeiten**aus.<br/>– Entfernen Sie die Sicherheitsgruppe, der die Benutzer angehören, aus der Geräterichtlinie. Wechseln Sie zu Security & Compliance Center > **Security Policies**   >  **Device Security Policies**. Wählen Sie Geräterichtlinien Name aus, und **Edit**klicken Sie dann auf  >  **Bereitstellung**bearbeiten.<br/>-Aufheben der Blockierung aller nicht konformen Geräte für eine Geräterichtlinie. Wechseln Sie zu Security & Compliance Center > **Security Policies**   >  **Device Security Policies**. Wählen Sie Geräterichtlinien Name aus, **Edit**und wählen Sie dann  >  **Zugriffsanforderungen**bearbeiten aus. Wählen Sie  **Zugriffs-und Berichts Verletzung zulassen**aus.<br/>-Zum Aufheben der Blockierung eines nicht konformen oder nicht unterstützten Geräts für einen Benutzer oder eine Gruppe von Benutzern wechseln Sie zu Sicherheits & Compliance Center > **Sicherheitsrichtlinien**   >  **Geräteverwaltung**Geräte   >  **Zugriffseinstellungen verwalten**. Fügen Sie eine Sicherheitsgruppe mit den Mitgliedern hinzu, die Sie ausschließen möchten, indem Sie den Zugriff auf Microsoft 365 blockiert haben. Weitere Informationen finden Sie unter [erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).|
|Entfernen von Benutzern, damit Ihre Geräte nicht mehr durch grundlegende Mobilität und Sicherheit verwaltet werden |Um den Benutzer zu entfernen, bearbeiten Sie die Sicherheitsgruppe mit Geräteverwaltungsrichtlinien für grundlegende Mobilität und Sicherheit. Weitere Informationen finden Sie unter  [erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).<br/>Informationen zum Entfernen von grundlegender Mobilität und Sicherheit durch alle Microsoft 365-Benutzer finden Sie unter [Deaktivieren der grundlegenden Mobilität und Sicherheit](turn-off.md).|

Live (v14)