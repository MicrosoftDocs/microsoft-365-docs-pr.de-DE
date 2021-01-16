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
description: Verwenden Sie "Basic Mobility and Security", um Geräterichtlinien zu erstellen, die Ihre Unternehmensinformationen schützen.
ms.openlocfilehash: 077f1e7e0d763aaecfc38fd4b57d9e8912900a3c
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877068"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security

Sie können Basic Mobility and Security verwenden, um Geräterichtlinien zu erstellen, die Ihre Unternehmensinformationen in Microsoft 365 vor unbefugtem Zugriff schützen. Sie können Richtlinien auf jedes mobile Gerät in Ihrer Organisation anwenden, auf dem der Benutzer des Geräts über eine entsprechende Microsoft 365-Lizenz verfügt und das Gerät in Basic Mobility and Security registriert hat.

## <a name="before-you-begin"></a>Vorabinformationen

> [!IMPORTANT]
> Bevor Sie eine Richtlinie für mobile Geräte erstellen können, müssen Sie Basic Mobility and Security aktivieren und einrichten. Weitere Informationen finden Sie unter "Übersicht über grundlegende Mobilität und Sicherheit".

- Erfahren Sie mehr über die Geräte, Apps für mobile Geräte und Sicherheitseinstellungen, die Basic Mobility and Security unterstützt. Siehe ["Funktionen der grundlegenden Mobilität und Sicherheit".](capabilities.md)
- Erstellen Sie Sicherheitsgruppen, die Microsoft 365-Benutzer umfassen, für die Sie Richtlinien bereitstellen möchten, sowie für Benutzer, die Sie möglicherweise vom Sperren des Zugriffs auf Microsoft 365 ausschließen möchten. Vor der Bereitstellung einer neuen Richtlinie für Ihre Organisation sollten Sie die Richtlinie testen, indem Sie diese für eine geringe Benutzeranzahl bereitstellen. Sie können eine Sicherheitsgruppe erstellen und verwenden, die nur sich selbst oder eine kleine Anzahl von Microsoft 365-Benutzern umfasst, die die Richtlinie für Sie testen können. Weitere Informationen zu Sicherheitsgruppen finden Sie unter Erstellen, Bearbeiten oder Löschen [einer Sicherheitsgruppe.](https://go.microsoft.com/fwlink/p/?LinkId=518555)
- Zum Erstellen und Bereitstellen von Grundlegenden Mobilitäts- und Sicherheitsrichtlinien in Microsoft 365 müssen Sie ein globaler Microsoft 365-Administrator sein. Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center.](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)
- Bevor Sie Richtlinien bereitstellen, teilen Sie Ihrer Organisation die potenziellen Auswirkungen der Registrierung eines Geräts in Basic Mobility and Security mit. Je nachdem, wie Sie die Richtlinien einrichten, können nicht kompatible Geräte am Zugriff auf Microsoft 365 und Daten, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen auf einem registrierten Gerät, blockiert werden, und Daten können gelöscht werden.

>[!NOTE]
>Richtlinien und Zugriffsregeln, die in Basic Mobility and Security für Microsoft 365 Business Standard erstellt wurden, setzen Exchange ActiveSync Postfachrichtlinien und Gerätezugriffsregeln für mobile Geräte außer Kraft, die im Exchange Admin Center erstellt wurden. Nachdem ein Gerät in Basic Mobility and Security für Microsoft 365 Business Standard registriert wurde, werden alle auf das Gerät angewendeten Exchange ActiveSync-Postfachrichtlinien oder Gerätezugriffsregeln für mobile Geräte ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie unter [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Schritt 1: Erstellen einer Geräterichtlinie und Bereitstellen in einer Testgruppe

Bevor Sie beginnen können, stellen Sie sicher, dass Sie Basic Mobility and Security aktiviert und eingerichtet haben. Anweisungen finden Sie unter [Overview of Basic Mobility and Security](overview.md).

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein .

2. Wählen Sie **Richtlinie erstellen** aus.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Richtlinieneinstellungen für Mobilität und Sicherheit":::

3. Geben Sie **auf der Seite "Richtlinieneinstellungen"** die Anforderungen an, die auf mobile Geräte in Ihrer Organisation angewendet werden.

4. **Verwalten des E-Mail-Profils** erforderlich: Wenn diese Option aktiviert ist, werden Geräte ohne E-Mail-Profil, das von Basic Mobility and Security verwaltet wird, als nicht kompatibel betrachtet. Ein Gerät kann kein verwaltetes E-Mail-Profil haben, wenn es nicht korrekt ausgerichtet ist oder wenn der Benutzer das E-Mail-Konto auf dem Gerät manuell eingerichtet hat. Wenn Sie die Einstellung **nicht aktiviert** lassen (Standardeinstellung), wird diese Einstellung nicht auf Kompatibilität oder Nichtkonformität überprüft. Anweisungen dazu, wie Benutzer die Richtlinien erfüllen können, wenn diese Option ausgewählt ist, finden Sie unter [Ein vorhandenes E-Mail-Konto wurde gefunden.](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)

5. Wählen Sie **auf der Seite "Möchten Sie diese Richtlinie** jetzt anwenden?" die Gruppen aus, auf die Sie diese Richtlinie anwenden möchten.

6. Wählen **Sie "Diese Richtlinie erstellen" aus.**

Die Richtlinie wird an das Gerät jedes Benutzers übertragen, auf das die Richtlinie angewendet wird, wenn er sich das nächste Mal mit dem mobilen Gerät bei Microsoft 365 anmeldet. Wenn Benutzer zuvor noch keine Richtlinie auf ihr mobiles Gerät angewendet haben, erhalten sie nach der Bereitstellung der Richtlinie eine Benachrichtigung auf ihrem Gerät, die die Schritte zum Registrieren und Aktivieren von Basic Mobility and Security enthält. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md). Bis sie die Registrierung in Basic Mobility and Security abgeschlossen haben, die vom #A0 gehostet wird, ist der Zugriff auf E-Mail, OneDrive und andere Dienste eingeschränkt. Nachdem sie die Registrierung mithilfe der Intune-Unternehmensportal-App abgeschlossen haben, können sie die Dienste verwenden, und die Richtlinie wird auf ihr Gerät angewendet.

## <a name="step-2-verify-that-your-policy-works"></a>Schritt 2: Überprüfen, ob ihre Richtlinie funktioniert

Nachdem Sie eine Geräterichtlinie erstellt haben, überprüfen Sie, ob die Richtlinie wie erwartet funktioniert, bevor Sie sie in Ihrer Organisation bereitstellen.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein .
2. Wählen **Sie "Liste der verwalteten Geräte anzeigen" aus.**
3. Überprüfen Sie den Status von Benutzergeräten, für die die Richtlinie angewendet wurde. Der Status **der** Geräte soll verwaltet **werden.**
4. Sie können auch eine vollständige oder selektive Zurücksetzung auf  einem Gerät  durchführen, indem Sie nach dem Auswählen eines Geräts auf die Schaltfläche **"Zurücksetzen** auf Werkseinstellungen" klicken oder Unternehmensdaten aus der Schaltfläche "Verwalten" entfernen klicken. Anweisungen finden Sie unter [Wipe a mobile device in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Schritt 3: Bereitstellen einer Richtlinie in Ihrer Organisation

Nachdem Sie eine Geräterichtlinie erstellt und überprüft haben, ob sie wie erwartet funktioniert, stellen Sie sie in Ihrer Organisation sicher.

1. Von Ihrem Browsertyp: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie die Richtlinie aus, die Sie bereitstellen möchten, und wählen **Sie "Bearbeiten"** neben **"Angewendete Gruppen" aus.**
3. Suchen Sie nach einer Gruppe, die hinzugefügt werden soll, und klicken Sie auf **"Auswählen".**
4. Wählen Sie **die Einstellung** "Schließen" **und "Ändern" aus.**
5. Wählen Sie **"Richtlinie** **schließen" und "Bearbeiten" aus.**

Die Richtlinie wird an das mobile Gerät jedes Benutzers übertragen, auf das die Richtlinie angewendet wird, wenn er sich das nächste Mal von ihrem mobilen Gerät aus bei Microsoft 365 anmeldet. Wenn Benutzer keine Richtlinie auf ihr mobiles Gerät angewendet haben, erhalten sie eine Benachrichtigung auf ihrem Gerät mit Schritten zur Registrierung und Aktivierung für Basic Mobility and Security. Nachdem sie die Registrierung abgeschlossen haben, wird die Richtlinie auf ihr Gerät angewendet. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Schritt 4: Blockieren des E-Mail-Zugriffs für nicht unterstützte Geräte

Um ihre Unternehmensinformationen zu schützen, sollten Sie den Zugriff auf Microsoft 365-E-Mails für mobile Geräte blockieren, die von Basic Mobility and Security nicht unterstützt werden. Eine Liste der unterstützten Geräte finden Sie unter ["Unterstützte Geräte".](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)

**So blockieren Sie den App-Zugriff:**

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein .
2. Wählen **Sie Organisationsweite Gerätezugriffseinstellungen verwalten aus.**
3. Um nicht unterstützte Geräte  zu blockieren, wählen Sie "Blockieren" unter "Wenn ein Gerät von **Basic Mobility and Security für Microsoft 365** nicht unterstützt wird" aus, und wählen Sie dann "Speichern" **aus.**

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Standardoption für den Zugriff auf Mobilität und Sicherheit":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Schritt 5: Auswählen von aus Überprüfungen für den bedingten Zugriff auszuschließenden Sicherheitsgruppen

Wenn Sie einige Personen aus den Überprüfungen für den bedingten Zugriff auf ihren Mobilgeräten ausschließen möchten und Sie mindestens eine Sicherheitsgruppe für diese Personen erstellt haben, fügen Sie die Sicherheitsgruppen hier hinzu. Für die Personen in diesen Gruppen werden keine Richtlinien für ihre unterstützten mobilen Geräte erzwungen. Dies ist die empfohlene Option, wenn Sie basic Mobility and Security in Ihrer Organisation nicht mehr verwenden möchten.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) ein .

2. Wählen **Sie Organisationsweite Gerätezugriffseinstellungen verwalten aus.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Einfache Mobilität und Sicherheit erstellen eine Richtlinienoption":::

3. Wählen **Sie "Hinzufügen"** aus, um die Sicherheitsgruppe hinzuzufügen, die Benutzer hat, die sie von der Blockieren des Zugriffs auf Microsoft 365 ausschließen möchten. Wenn ein Benutzer dieser Liste hinzugefügt wurde, kann er auf Microsoft 365-E-Mails zugreifen, wenn er ein nicht unterstütztes Gerät verwendet.

4. Wählen Sie im Bereich "Gruppe auswählen" die **Sicherheitsgruppe aus,** die Sie verwenden möchten.

5. Wählen Sie den Namen aus, und fügen Sie **dann "Speichern"**  >  **hinzu.**

6. Wählen Sie **im Bereich "Organisationsweite Gerätezugriffseinstellungen"** "Speichern" **aus.**

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Option &quot;Basic Mobility and Security allow access&quot;":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Wie wirken sich Sicherheitsrichtlinien auf verschiedene Gerätetypen aus?

Wenn Sie eine Richtlinie auf Benutzergeräte anwenden, sind die Auswirkungen auf jedes Gerät je nach Gerätetyp unterschiedlich. In der folgenden Tabelle finden Sie Beispiele für die Auswirkung von Richtlinien auf verschiedene Geräte.

|**Sicherheitsrichtlinie**|**Android 4 und höher**|**Samsung KNOX**|**iOS 6 und höher**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Verschlüsselte Sicherung erforderlich|Nein|Ja|Ja|iOS-verschlüsselte Sicherung erforderlich.|
|Cloudsicherung blockieren|Ja|Ja|Ja|Google-Sicherung auf Android blockieren (abgeblendet), Cloud-Sicherung auf iOS.|
|Dokumentsynchronisierung blockieren|Nein|Nein|Ja|iOS: Dokumente in der Cloud blockieren.|
|Fotosynchronisierung blockieren |Nein|Nein|Ja|iOS (systemeigen): Fotodatenstrom blockieren.|
|Screenshots blockieren |Nein|Ja|Ja|Bei Versuch blockiert.|
|Videokonferenz blockieren |Nein|Nein|Ja|FaceTime unter iOS blockiert, nicht in Skype oder anderen.|
|Senden von Diagnosedaten blockieren |Nein|Ja|Ja|Senden von Google-Absturzbericht unter Android blockieren|
|Zugriff auf den App-Store blockieren |Nein|Ja|Ja|App-Store-Symbol fehlt auf Android-Startseite, ist deaktiviert unter Windows, fehlt unter iOS.|
|Kennwort für den App-Store anfordern |Nein|Nein|Ja|iOS: Kennwort für iTunes-Käufe erforderlich.|
|Verbindung mit Wechselmedien blockieren |Nein|Ja|Nicht zutreffend|Android: Die SD-Karte ist in den Einstellungen abgeblendet, Windows benachrichtigt den Benutzer, installierte Apps sind nicht verfügbar|
|Bluetoothverbindung blockieren |Siehe Hinweise|Siehe Hinweise|Ja|BlueTooth kann nicht als Einstellung unter Android deaktiviert werden. Stattdessen werden alle Transaktionen deaktiviert, für die BlueTooth erforderlich ist: erweiterte Audioverteilung, Audio-/Video-Fernbedienung, freihändige Geräte, Headset, Telefonbuchzugriff und serieller Port. Eine kleine Popupnachricht wird am unteren Rand der Seite angezeigt, wenn diese Transaktionen verwendet werden.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Was geschieht beim Löschen einer Richtlinie oder beim Entfernen eines Benutzers aus der Richtlinie?

Wenn Sie eine Richtlinie löschen oder einen Benutzer aus einer Gruppe entfernen, für die die Richtlinie bereitgestellt wurde, werden möglicherweise die Richtlinieneinstellungen, das Microsoft 365-E-Mail-Profil und zwischengespeicherte E-Mails vom Gerät des Benutzers entfernt. In der folgenden Tabelle finden Sie Informationen dazu, was für die verschiedenen Gerätetypen entfernt wurde.

|**Entfernte**|**iOS 6 und höher**|**Android 4 und höher (einschließlich Samsung KNOX**|
|:-----|:-----|:-----|
|Verwaltete E-Mail-Profile<sup>1</sup>|Ja|Nein|
|Cloud-Sicherung blockieren|Ja|Nein|

<sup>1</sup> Wenn die Richtlinie mit  der Option "E-Mail-Profil verwaltet" bereitgestellt wurde, werden das verwaltete E-Mail-Profil und zwischengespeicherte E-Mails in diesem Profil vom Benutzergerät gelöscht.

Die Richtlinie wird vom mobilen Gerät für jeden Benutzer entfernt, auf den die Richtlinie angewendet wird, wenn das Gerät das nächste Mal mit Basic Mobility and Security eincheckt. Wenn Sie eine neue Richtlinie bereitstellen, die für diese Benutzergeräte gilt, werden sie aufgefordert, sich erneut für Basic Mobility and Security zu registrieren.

Sie können ein Gerät auch vollständig oder selektiv vom Gerät löschen. Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Verwandte Themen

[Übersicht von grundlegender Mobilität und Sicherheit](overview.md)

[Funktionen von grundlegender Mobilität und Sicherheit](capabilities.md)
