---
title: Erstellen von Gerätesicherheitsrichtlinien in grundlegender Mobilität und Sicherheit
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
description: Verwenden Sie grundlegende Mobilitäts-und Sicherheitseinstellungen zum Erstellen von Geräterichtlinien, die ihre Organisationsinformationen schützen.
ms.openlocfilehash: eddd3454e8f00bab7a830e7710331cafd097d7de
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430190"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Erstellen von Gerätesicherheitsrichtlinien in grundlegender Mobilität und Sicherheit 

Sie können die grundlegende Mobilität und Sicherheit verwenden, um Geräterichtlinien zu erstellen, die ihre Organisationsinformationen unter Microsoft 365 vor nicht autorisiertem Zugriff schützen. Sie können Richtlinien auf alle mobilen Geräte in Ihrer Organisation anwenden, in denen der Benutzer des Geräts über eine gültige Microsoft 365-Lizenz verfügt und das Gerät in grundlegender Mobilität und Sicherheit registriert hat.

## <a name="before-you-begin"></a>Vorabinformationen

>[!IMPORTANT]
>Bevor Sie eine Richtlinie für mobile Geräte erstellen können, müssen Sie grundlegende Mobilitäts-und Sicherheitseinstellungen aktivieren und einrichten. Weitere Informationen finden Sie unter Overview of Basic Mobility and Security.

- Erfahren Sie mehr über die Geräte, Apps für mobile Geräte und Sicherheitseinstellungen, die von grundlegender Mobilität und Sicherheit unterstützt werden. Weitere Informationen finden Sie unter [capabilities of Basic Mobility and Security](capabilities.md).
- Erstellen Sie Sicherheitsgruppen, die Microsoft 365-Benutzer enthalten, die Sie Richtlinien für und für Benutzer bereitstellen möchten, die Sie möglicherweise von einem blockierten Zugriff auf Microsoft 365 ausschließen möchten. Vor der Bereitstellung einer neuen Richtlinie für Ihre Organisation sollten Sie die Richtlinie testen, indem Sie diese für eine geringe Benutzeranzahl bereitstellen. Sie können eine Sicherheitsgruppe erstellen und verwenden, die nur sich selbst oder eine kleine Anzahl von Microsoft 365-Benutzern enthält, die die Richtlinie für Sie testen können. Weitere Informationen zu Sicherheitsgruppen finden Sie unter [erstellen, bearbeiten oder Löschen einer Sicherheitsgruppe](https://go.microsoft.com/fwlink/p/?LinkId=518555).
- Um grundlegende Mobilitäts-und Sicherheitsrichtlinien in Microsoft 365 zu erstellen und bereitzustellen, müssen Sie ein globaler Administrator von Microsoft 365 sein. Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Bevor Sie Richtlinien bereitstellen, sollten Sie Ihrer Organisation die potenziellen Auswirkungen der Registrierung eines Geräts in grundlegender Mobilität und Sicherheit bekannt geben. Je nachdem, wie Sie die Richtlinien einrichten, können nicht konforme Geräte für den Zugriff auf Microsoft 365 und Daten blockiert werden, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen auf einem registrierten Gerät, und Daten können gelöscht werden.

>[!NOTE]
>In MDM erstellte Richtlinien und Zugriffsregeln für Microsoft 365 Business Standard setzen Exchange ActiveSync-Postfachrichtlinien für mobile Geräte und Gerätezugriffsregeln, die im Exchange Admin Center erstellt wurden, außer Kraft. Nachdem ein Gerät in MDM für Microsoft 365 Business Standard registriert wurde, werden alle Exchange ActiveSync-Postfachrichtlinien für mobile Geräte oder Gerätezugriffsregeln, die auf das Gerät angewendet werden, ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie unter [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Schritt 1: Erstellen einer Geräterichtlinie und Bereitstellen in einer Testgruppe

Bevor Sie beginnen können, stellen Sie sicher, dass Sie die grundlegenden Mobilitäts-und Sicherheitseinstellungen aktiviert und eingerichtet haben. Anweisungen finden Sie unter [Overview of Basic Mobility and Security](overview.md).

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie **Richtlinie erstellen** aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Einstellungen für Mobilität und Sicherheitsrichtlinien":::

3. Geben Sie auf der Seite **Richtlinieneinstellungen** die Anforderungen an, die auf mobile Geräte in Ihrer Organisation angewendet werden sollen.

4. **Verwalten des e-Mail-Profils**: Wenn diese Option aktiviert ist, werden Geräte, die kein e-Mail-Profil haben, das von Basic Mobility and Security verwaltet wird, als nicht konform betrachtet Ein Gerät kann kein verwaltetes e-Mail-Profil haben, wenn es nicht ordnungsgemäß ausgerichtet ist, oder wenn der Benutzer das e-Mail-Konto manuell auf dem Gerät eingerichtet hat. Wenn Sie die Option **nicht aktiviert** lassen (Standardeinstellung), wird diese Einstellung nicht für die Konformität oder Nichteinhaltung ausgewertet. Anweisungen zur Kompatibilität von Benutzern bei Auswahl dieser Option finden Sie unter [ein vorhandenes e-Mail-Konto wurde gefunden](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

5. Wählen Sie auf der Seite soll **Diese Richtlinie jetzt angewendet werden?** die Gruppen aus, auf die diese Richtlinie angewendet werden soll.

6. Wählen Sie **Diese Richtlinie erstellen**aus.

Die Richtlinie wird auf das Gerät jedes Benutzers übertragen die Richtlinie gilt für das nächste Mal, wenn Sie sich mit Ihrem mobilen Gerät bei Microsoft 365 anmelden. Wenn für Benutzer noch keine Richtlinie auf Ihr mobiles Gerät angewendet wurde, erhalten Sie nach der Bereitstellung der Richtlinie eine Benachrichtigung auf dem Gerät, die die Schritte zum Registrieren und Aktivieren von grundlegender Mobilität und Sicherheit enthält. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md). Der Zugriff auf e-Mail, OneDrive und andere Dienste ist bis zum Abschluss der Registrierung in grundlegende Mobilität und Sicherheit, die vom InTune-Dienst gehostet wird, eingeschränkt. Nachdem Sie die Registrierung mithilfe der InTune-Unternehmens Portal-App abgeschlossen haben, können Sie die Dienste verwenden, und die Richtlinie wird auf Ihr Gerät angewendet.

## <a name="step-2-verify-that-your-policy-works"></a>Schritt 2: überprüfen, ob Ihre Richtlinie funktioniert

Nachdem Sie eine Geräterichtlinie erstellt haben, überprüfen Sie, ob die Richtlinie wie erwartet funktioniert, bevor Sie Sie in Ihrer Organisation bereitstellen.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie **die Liste der verwalteten Geräte anzeigen**aus.
3. Überprüfen Sie den Status von Benutzergeräten, für die die Richtlinie angewendet wurde. Sie möchten, dass der **Status** der Geräte **verwaltet wird.**
4. Sie können auch ein vollständiges oder selektives wischen auf einem Gerät durchführen, indem Sie nach dem Auswählen eines Geräts auf **Factory zurücksetzen** oder **Unternehmensdaten** aus der **Verwaltungs** Schaltfläche Entfernen klicken. Anweisungen hierzu finden Sie unter [wischen eines mobilen Geräts in Microsoft 365.

Schritt 3: Bereitstelleneiner Richtlinie in Ihrer Organisation

Nachdem Sie eine Geräterichtlinie erstellt und überprüft haben, dass Sie erwartungsgemäß funktioniert, stellen Sie Sie in Ihrer Organisation bereit.

1. Geben Sie im Browsertyp Folgendes ein: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie **Bearbeiten** neben **Gruppen, auf die angewendet** wird aus.
3. Suchen Sie nach einer Gruppe, die Sie hinzufügen möchten, und klicken Sie auf **auswählen**.
4. Wählen Sie **Schließen** und **Einstellung ändern aus.**
5. Wählen Sie **Richtlinie** **Schließen** und bearbeiten aus.

Die Richtlinie wird auf das Mobile Gerät jedes Benutzers übertragen die Richtlinie gilt für das nächste Mal, wenn Sie sich von Ihrem mobilen Gerät bei Microsoft 365 anmelden. Wenn Benutzer keine Richtlinie auf Ihr mobiles Gerät angewendet haben, erhalten Sie eine Benachrichtigung auf Ihrem Gerät mit Schritten zum Registrieren und aktivieren für die grundlegende Mobilität und Sicherheit. Nachdem Sie die Registrierung abgeschlossen haben, wird die Richtlinie auf Ihr Gerät angewendet. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Schritt 4: Blockieren des e-Mail-Zugriffs für nicht unterstützte Geräte

Um Ihre Organisationsinformationen zu schützen, sollten Sie den App-Zugriff auf Microsoft 365-e-Mails für mobile Geräte blockieren, die nicht von Basic Mobility and Security unterstützt werden. Eine Liste unterstützter Geräte finden Sie unter [Supported Devices](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices). 

**So blockieren Sie den App-Zugriff:**

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie **organisationsweite gerätezugriffseinstellungen verwalten**aus.
3. Wenn Sie nicht unterstützte Geräte blockieren möchten, wählen **Sie unter** **Wenn ein Gerät von MDM für Microsoft 365 nicht unterstützt**wird aus, und wählen Sie dann **Speichern**aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Grundlegende Mobilitäts-und Sicherheitsoptionen für den Blockzugriff":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Schritt 5: Auswählen von aus Überprüfungen für den bedingten Zugriff auszuschließenden Sicherheitsgruppen

Wenn Sie einige Personen aus den Überprüfungen für den bedingten Zugriff auf ihren Mobilgeräten ausschließen möchten und Sie mindestens eine Sicherheitsgruppe für diese Personen erstellt haben, fügen Sie die Sicherheitsgruppen hier hinzu. Für die Personen in diesen Gruppen werden keine Richtlinien für die unterstützten mobilen Geräte erzwungen. Dies ist die empfohlene Option, wenn Sie nicht mehr die grundlegende Mobilität und Sicherheit in Ihrer Organisation verwenden möchten.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie **organisationsweite gerätezugriffseinstellungen verwalten**aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Mobilität und Sicherheit Erstellen einer Richtlinienoption":::

3. Wählen Sie **Hinzufügen** aus, um die Sicherheitsgruppe hinzuzufügen, für die Benutzer, die Sie ausschließen möchten, den blockierten Zugriff auf Microsoft 365. Wenn ein Benutzer zu dieser Liste hinzugefügt wurde, kann er auf Microsoft 365-e-Mails zugreifen, wenn er ein nicht unterstütztes Gerät verwendet.

4. Wählen Sie die Sicherheitsgruppe aus, die Sie im **Gruppenbereich auswählen** verwenden möchten.

5. Wählen Sie den Namen aus, und **fügen**Sie dann  >  **Speichern**hinzu.

6. Wählen Sie im Bereich **organisationsweite gerätezugriffseinstellungen** die Option **Speichern**aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Einfache Option für Mobilitäts-und Sicherheitszugriff zulassen":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Wie wirken sich Sicherheitsrichtlinien auf verschiedene Gerätetypen aus?

Wenn Sie eine Richtlinie auf Benutzer Geräte anwenden, variiert die Auswirkung auf jedes Gerät geringfügig zwischen den Gerätetypen. In der folgenden Tabelle finden Sie Beispiele für die Auswirkung von Richtlinien auf verschiedene Geräte.

|**Sicherheitsrichtlinie**|**Android 4 und höher**|**Samsung Knox**|**IOS 6 und höher**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Verschlüsselte Sicherung erforderlich|Nein|Ja|Ja|IOS-verschlüsselte Sicherung erforderlich.|
|Cloudsicherung blockieren|Ja|Ja|Ja|Google-Sicherung auf Android blockieren (abgeblendet), Cloud-Sicherung auf iOS.|
|Dokumentsynchronisierung blockieren|Nein|Nein|Ja|iOS: Dokumente in der Cloud blockieren.|
|Fotosynchronisierung blockieren |Nein|Nein|Ja|iOS (systemeigen): Fotodatenstrom blockieren.|
|Screenshots blockieren |Nein|Ja|Ja|Bei Versuch blockiert.|
|Videokonferenz blockieren |Nein|Nein|Ja|FaceTime wurde in ios blockiert, nicht in Skype oder anderen.|
|Senden von Diagnosedaten blockieren |Nein|Ja|Ja|Senden von Google-Absturzbericht unter Android blockieren|
|Zugriff auf den App-Store blockieren |Nein|Ja|Ja|App-Store-Symbol fehlt auf Android-Startseite, ist deaktiviert unter Windows, fehlt unter iOS.|
|Kennwort für den App-Store anfordern |Nein|Nein|Ja|iOS: Kennwort für iTunes-Käufe erforderlich.|
|Verbindung mit Wechselmedien blockieren |Nein|Ja|Nicht zutreffend|Android: SD-Karte ist in Einstellungen abgeblendet, Windows benachrichtigt Benutzer, installierte apps sind nicht verfügbar|
|Bluetoothverbindung blockieren |Siehe Hinweise|Siehe Hinweise|Ja|Wir können Bluetooth nicht als Einstellung auf Android deaktivieren. Stattdessen deaktivieren wir alle Transaktionen, für die Bluetooth erforderlich ist: Erweiterte Audioverteilung, Audio/Video-Remote Steuerung, Freisprech Geräte, Headset, Telefonbuchzugriff und serielle Schnittstelle. Eine kleine Popupnachricht wird am unteren Rand der Seite angezeigt, wenn diese Transaktionen verwendet werden.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Was geschieht beim Löschen einer Richtlinie oder beim Entfernen eines Benutzers aus der Richtlinie?

Wenn Sie eine Richtlinie löschen oder einen Benutzer aus einer Gruppe entfernen, für die die Richtlinie bereitgestellt wurde, werden die Richtlinieneinstellungen, das Microsoft 365-e-Mail-Profil und die zwischengespeicherten e-Mails möglicherweise aus dem Gerät des Benutzers entfernt. In der folgenden Tabelle sehen Sie, was für die verschiedenen Gerätetypen entfernt wurde.

|**Was wurde entfernt**|**IOS 6 und höher**|**Android 4 und höher (einschließlich Samsung Knox**|
|:-----|:-----|:----------------------|
|Verwaltete e-Mail-Profile<sup>1</sup>|Ja|Nein|
|Cloud-Sicherung blockieren|Ja|Nein|
<sup>1</sup> Wenn die Richtlinie mit der Option **e-Mail-Profil wird verwaltet** ausgewählt wurde, werden das verwaltete e-Mail-Profil und die zwischengespeicherten e-Mails in diesem Profil aus dem Benutzergerät gelöscht.

Die Richtlinie wird für jeden Benutzer vom mobilen Gerät entfernt. die Richtlinie gilt für das nächste Mal, wenn Ihr Gerät mit grundlegender Mobilität und Sicherheit eingecheckt wird. Wenn Sie eine neue Richtlinie bereitstellen, die für diese Benutzer Geräte gilt, werden Sie aufgefordert, sich bei der grundlegenden Mobilität und Sicherheit erneut zu registrieren.

Sie können ein Gerät auch vollständig löschen oder organisatorische Informationen selektiv vom Gerät löschen. Weitere Informationen finden Sie unter [wischen eines mobilen Geräts in Basic Mobility and Security](wipe-mobile-device.md). 

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über grundlegende Mobilität und Sicherheit](overview.md)

[Funktionen der grundlegenden Mobilität und Sicherheit](capabilities.md)
