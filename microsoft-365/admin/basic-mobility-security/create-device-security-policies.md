---
title: Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security
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
description: Verwenden Sie Grundlegende Mobilität und Sicherheit, um Geräterichtlinien zu erstellen, die Ihre Unternehmensinformationen schützen.
ms.openlocfilehash: 5abd27f963208140a53cfd885152301992830b5e
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023905"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security

Sie können grundlegende Mobilität und Sicherheit verwenden, um Geräterichtlinien zu erstellen, mit deren Hilfe Sie Ihre Unternehmensinformationen auf Microsoft 365 nicht autorisierten Zugriff schützen können. Sie können Richtlinien auf jedes mobile Gerät in Ihrer Organisation anwenden, auf dem der Benutzer des Geräts über eine entsprechende Microsoft 365 verfügt und das Gerät in Basic Mobility and Security registriert hat.

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!IMPORTANT]
> Bevor Sie eine Richtlinie für mobile Geräte erstellen können, müssen Sie Basic Mobility and Security aktivieren und einrichten. Weitere Informationen finden Sie unter Overview of Basic Mobility and Security.

- Erfahren Sie mehr über die Von Basic Mobility and Security unterstützten Geräte, Apps für mobile Geräte und Sicherheitseinstellungen. Weitere [Informationen finden Sie unter Capabilities of Basic Mobility and Security](capabilities.md).
- Erstellen Sie Sicherheitsgruppen, die Microsoft 365 benutzer enthalten, für die Sie Richtlinien bereitstellen möchten, und für Benutzer, die Sie möglicherweise davon ausschließen möchten, dass der Zugriff auf Benutzer blockiert Microsoft 365. Vor der Bereitstellung einer neuen Richtlinie für Ihre Organisation sollten Sie die Richtlinie testen, indem Sie diese für eine geringe Benutzeranzahl bereitstellen. Sie können eine Sicherheitsgruppe erstellen und verwenden, die nur sich selbst oder eine kleine Microsoft 365 enthält, die die Richtlinie für Sie testen kann. Weitere Informationen zu Sicherheitsgruppen finden Sie unter Erstellen, Bearbeiten oder Löschen [einer Sicherheitsgruppe.](../email/create-edit-or-delete-a-security-group.md)
- Zum Erstellen und Bereitstellen grundlegender Mobilitäts- und Sicherheitsrichtlinien in Microsoft 365 müssen Sie ein globaler administrator Microsoft 365 sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md).
- Bevor Sie Richtlinien bereitstellen, teilen Sie Ihrer Organisation die potenziellen Auswirkungen der Registrierung eines Geräts in Basic Mobility and Security mit. Je nachdem, wie Sie die Richtlinien einrichten, können nicht kompatible Geräte am Zugriff auf Microsoft 365 und Daten, einschließlich installierter Anwendungen, Fotos und personenbezogener Informationen auf einem registrierten Gerät, blockiert werden, und Daten können gelöscht werden.

>[!NOTE]
>Richtlinien und Zugriffsregeln, die in Basic Mobility and Security for Microsoft 365 Business Standard erstellt wurden, setzen Exchange ActiveSync Postfachrichtlinien für mobile Geräte und Gerätezugriffsregeln außer Kraft, die im Exchange admin center erstellt wurden. Nachdem ein Gerät in Basic Mobility and Security for Microsoft 365 Business Standard registriert wurde, werden alle Exchange ActiveSync Postfachrichtlinien oder Gerätezugriffsregel für mobile Geräte ignoriert, die auf das Gerät angewendet werden. Weitere Informationen zu Exchange ActiveSync finden Sie [unter Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Schritt 1: Erstellen einer Geräterichtlinie und Bereitstellen in einer Testgruppe

Bevor Sie beginnen können, stellen Sie sicher, dass Sie Basic Mobility and Security aktiviert und eingerichtet haben. Anweisungen finden Sie unter [Overview of Basic Mobility and Security](overview.md).

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein.

2. Wählen Sie **Richtlinie erstellen** aus.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Mobilitäts- und Sicherheitsrichtlinieneinstellungen":::

3. Geben Sie **auf der** Seite Richtlinieneinstellungen die Anforderungen an, die auf mobile Geräte in Ihrer Organisation angewendet werden sollten.

4. **Verwalten des E-Mail-Profils** erforderlich: Wenn diese Option aktiviert ist, gelten Geräte, auf denen kein E-Mail-Profil von Basic Mobility and Security verwaltet wird, als nicht kompatibel. Ein Gerät kann kein verwaltetes E-Mail-Profil haben, wenn es nicht richtig ausgerichtet ist oder wenn der Benutzer das E-Mail-Konto manuell auf dem Gerät eingerichtet hat. Wenn Sie die Einstellung **nicht aktiviert** lassen (Standardeinstellung), wird diese Einstellung nicht auf Compliance oder Nichtkonformität überprüft. Anweisungen dazu, wie Benutzer richtlinienkonform werden können, wenn diese Option ausgewählt ist, finden Sie unter [Ein vorhandenes E-Mail-Konto wurde gefunden.](/intune-user-help/existing-company-email-account-found)

5. Wählen Sie auf der Seite Möchten Sie diese Richtlinie jetzt **anwenden?** die Gruppen aus, auf die Sie diese Richtlinie anwenden möchten.

6. Wählen **Sie Diese Richtlinie erstellen aus.**

Die Richtlinie wird auf das Gerät jedes Benutzers übertragen, auf das die Richtlinie angewendet wird, wenn sie sich das nächste Mal mit ihrem Microsoft 365 anmelden. Wenn Benutzer zuvor noch keine Richtlinie auf ihr mobiles Gerät angewendet haben, erhalten sie nach der Bereitstellung der Richtlinie eine Benachrichtigung auf ihrem Gerät, die die Schritte zum Registrieren und Aktivieren von Basic Mobility and Security enthält. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md). Der Zugriff auf E-Mails, OneDrive und andere Dienste wird eingeschränkt, bis sie die Registrierung in basic Mobility and Security abgeschlossen haben, die vom Intune-Dienst gehostet werden. Nachdem sie die Registrierung mithilfe der Intune-Unternehmensportal abgeschlossen haben, können sie die Dienste verwenden, und die Richtlinie wird auf ihr Gerät angewendet.

## <a name="step-2-verify-that-your-policy-works"></a>Schritt 2: Überprüfen, ob Ihre Richtlinie funktioniert

Nachdem Sie eine Geräterichtlinie erstellt haben, überprüfen Sie, ob die Richtlinie wie erwartet funktioniert, bevor Sie sie in Ihrer Organisation bereitstellen.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein.
2. Wählen **Sie Die Liste der verwalteten Geräte anzeigen aus.**
3. Überprüfen Sie den Status von Benutzergeräten, für die die Richtlinie angewendet wurde. Sie möchten, **dass der** Status der Geräte verwaltet **wird.**
4. Sie können auch eine vollständige oder selektive Löschung auf  einem Gerät  durchführen, indem Sie auf Werkseinstellungen zurücksetzen oder Unternehmensdaten aus der Schaltfläche Verwalten entfernen klicken, nachdem Sie ein Gerät ausgewählt haben.  Anweisungen finden Sie unter [Wipe a mobile device in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Schritt 3: Bereitstellen einer Richtlinie in Ihrer Organisation

Nachdem Sie eine Geräterichtlinie erstellt und überprüft haben, ob sie wie erwartet funktioniert, stellen Sie sie in Ihrer Organisation sicher.

1. Von Ihrem Browsertyp: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie **Bearbeiten** neben **Gruppen aus, auf die angewendet wird.**
3. Suchen Sie nach einer Gruppe, die hinzugefügt werden soll, und klicken Sie auf **Auswählen**.
4. Wählen **Sie Schließen** und Ändern **aus.**
5. Wählen **Sie Richtlinie** schließen und bearbeiten **aus.**

Die Richtlinie wird auf das mobile Gerät jedes Benutzers übertragen, auf das die Richtlinie angewendet wird, wenn sie sich das nächste Mal bei Microsoft 365 ihrem mobilen Gerät anmeldet. Wenn Benutzer keine Richtlinie auf ihr mobiles Gerät angewendet haben, erhalten sie auf ihrem Gerät eine Benachrichtigung mit Schritten zur Registrierung und Aktivierung für Grundlegende Mobilität und Sicherheit. Nachdem sie die Registrierung abgeschlossen haben, wird die Richtlinie auf ihr Gerät angewendet. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Schritt 4: Blockieren des E-Mail-Zugriffs für nicht unterstützte Geräte

Um Ihre Unternehmensinformationen zu schützen, sollten Sie den App-Zugriff auf Microsoft 365 für mobile Geräte blockieren, die von Basic Mobility and Security nicht unterstützt werden. Eine Liste der unterstützten Geräte finden Sie unter [Supported devices](../../admin/basic-mobility-security/capabilities.md).

**So blockieren Sie den App-Zugriff:**

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein.
2. Wählen **Sie Organisationsweite Gerätezugriffseinstellungen verwalten aus.**
3. Um nicht unterstützte Geräte zu blockieren, wählen Sie **Blockieren** unter Wenn ein Gerät von **Basic Mobility and Security for Microsoft 365** nicht unterstützt wird, und wählen Sie dann Speichern **aus.**

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Standardoption für den Zugriff auf Mobilität und Sicherheit":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Schritt 5: Auswählen von aus Überprüfungen für den bedingten Zugriff auszuschließenden Sicherheitsgruppen

Wenn Sie einige Personen aus den Überprüfungen für den bedingten Zugriff auf ihren Mobilgeräten ausschließen möchten und Sie mindestens eine Sicherheitsgruppe für diese Personen erstellt haben, fügen Sie die Sicherheitsgruppen hier hinzu. Für die Personen in diesen Gruppen werden keine Richtlinien für ihre unterstützten mobilen Geräte erzwungen. Dies ist die empfohlene Option, wenn Sie grundlegende Mobilität und Sicherheit in Ihrer Organisation nicht mehr verwenden möchten.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein.

2. Wählen **Sie Organisationsweite Gerätezugriffseinstellungen verwalten aus.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Mobilität und Sicherheit erstellen eine Richtlinienoption":::

3. Wählen **Sie Hinzufügen** aus, um die Sicherheitsgruppe hinzuzufügen, die Benutzer hat, die Sie von blockierten Zugriffen auf Microsoft 365. Wenn ein Benutzer dieser Liste hinzugefügt wurde, kann er auf Microsoft 365 zugreifen, wenn er ein nicht unterstütztes Gerät verwendet.

4. Wählen Sie die Sicherheitsgruppe aus, die Sie im Gruppenbereich **Auswählen verwenden** möchten.

5. Wählen Sie den Namen aus, und fügen **Sie dann Speichern**  >  **hinzu.**

6. Wählen Sie **im Bereich Organisationsweite Gerätezugriffseinstellungen** die Option **Speichern aus.**

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Grundlegende Option für Mobilität und Sicherheit":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Wie wirken sich Sicherheitsrichtlinien auf verschiedene Gerätetypen aus?

Wenn Sie eine Richtlinie auf Benutzergeräte anwenden, variieren die Auswirkungen auf jedes Gerät je nach Gerätetyp etwas. In der folgenden Tabelle finden Sie Beispiele für die Auswirkung von Richtlinien auf verschiedene Geräte.

|**Sicherheitsrichtlinie**|**Android 4 und höher**|**Samsung KNOX**|**iOS 6 und höher**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Verschlüsselte Sicherung erforderlich|Nein|Ja|Ja|iOS-verschlüsselte Sicherung erforderlich.|
|Cloudsicherung blockieren|Ja|Ja|Ja|Google-Sicherung auf Android blockieren (abgeblendet), Cloud-Sicherung auf iOS.|
|Dokumentsynchronisierung blockieren|Nein|Nein|Ja|iOS: Dokumente in der Cloud blockieren.|
|Fotosynchronisierung blockieren |Nein|Nein|Ja|iOS (systemeigen): Fotodatenstrom blockieren.|
|Screenshots blockieren |Nein|Ja|Ja|Bei Versuch blockiert.|
|Videokonferenz blockieren |Nein|Nein|Ja|FaceTime unter iOS blockiert, nicht auf Skype oder anderen.|
|Senden von Diagnosedaten blockieren |Nein|Ja|Ja|Senden von Google-Absturzbericht unter Android blockieren|
|Zugriff auf den App-Store blockieren |Nein|Ja|Ja|App-Store-Symbol fehlt auf Android-Startseite, ist deaktiviert unter Windows, fehlt unter iOS.|
|Kennwort für den App-Store anfordern |Nein|Nein|Ja|iOS: Kennwort für iTunes-Käufe erforderlich.|
|Verbindung mit Wechselmedien blockieren |Nein|Ja|Nicht zutreffend|Android: DIE SD-Karte ist in den Einstellungen ausgegraut, Windows Benutzer benachrichtigt, installierte Apps sind nicht verfügbar|
|Bluetoothverbindung blockieren |Siehe Hinweise|Siehe Hinweise|Ja|BlueTooth kann nicht als Einstellung unter Android deaktiviert werden. Stattdessen deaktivieren wir alle Transaktionen, die BlueTooth erfordern: Advanced Audio Distribution, Audio/Video Remote Control, Freisprechgeräte, Headset, Telefon Book Access und Serial Port. Eine kleine Popupnachricht wird am unteren Rand der Seite angezeigt, wenn diese Transaktionen verwendet werden.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Was geschieht beim Löschen einer Richtlinie oder beim Entfernen eines Benutzers aus der Richtlinie?

Wenn Sie eine Richtlinie löschen oder einen Benutzer aus einer Gruppe entfernen, in der die Richtlinie bereitgestellt wurde, werden möglicherweise die Richtlinieneinstellungen, Microsoft 365 E-Mail-Profil und zwischengespeicherte E-Mails vom Gerät des Benutzers entfernt. In der folgenden Tabelle finden Sie Informationen dazu, was für die verschiedenen Gerätetypen entfernt wurde.

|**Entfernte**|**iOS 6 und höher**|**Android 4 und höher (einschließlich Samsung KNOX**|
|:-----|:-----|:-----|
|Verwaltete E-Mail-Profile<sup>1</sup>|Ja|Nein|
|Cloud-Sicherung blockieren|Ja|Nein|

<sup>1</sup> Wenn die Richtlinie mit  der Option E-Mail-Profil verwaltet bereitgestellt wurde, werden das verwaltete E-Mail-Profil und zwischengespeicherte E-Mails in diesem Profil vom Benutzergerät gelöscht.

Die Richtlinie wird vom mobilen Gerät für jeden Benutzer entfernt, für den die Richtlinie gilt, wenn das Gerät das nächste Mal mit Basic Mobility and Security eincheckt. Wenn Sie eine neue Richtlinie bereitstellen, die für diese Benutzergeräte gilt, werden sie aufgefordert, sich erneut bei Basic Mobility and Security zu registrieren.

Sie können ein Gerät auch vollständig oder selektiv vom Gerät löschen. Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht von grundlegender Mobilität und Sicherheit](overview.md)

[Funktionen von grundlegender Mobilität und Sicherheit](capabilities.md)