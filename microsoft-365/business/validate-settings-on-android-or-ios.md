---
title: Überprüfen der App-Schutzeinstellungen auf Android- oder iOS-Geräten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Erfahren Sie, wie Sie Microsoft 365 Business Premium App-Schutzeinstellungen auf Ihren Android- oder iOS-Geräten überprüfen.
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578065"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Überprüfen der App-Schutzeinstellungen auf Android- oder iOS-Geräten

Befolgen Sie die Anweisungen in den folgenden Abschnitten, um die App-Schutzeinstellungen auf Android- oder iOS-Geräten zu überprüfen.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Überprüfen, ob die App-Schutzeinstellungen auf Benutzergeräten funktionieren

Nachdem Sie [App-Konfigurationen für Android-Geräte festgelegt haben](app-protection-settings-for-android-and-ios.md), um die Apps zu schützen, können Sie folgendermaßen überprüfen, ob die gewählten Einstellungen funktionieren. 
  
Stellen Sie zunächst sicher, dass die Richtlinie für die App gilt, in der Sie sie überprüfen möchten.
  
1. Wechseln Sie Microsoft 365 Business Premium [Admin Center](https://portal.office.com)zu **Richtlinien** \> **bearbeiten Richtlinie**.
    
2. Wählen **Sie Anwendungsrichtlinie für Android** für die Einstellungen aus, die Sie beim Setup erstellt haben, oder eine andere richtlinie, die Sie erstellt haben, und stellen Sie sicher, dass sie z. B. für Outlook erzwungen wird. 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Überprüfen von "Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern** auf **Ein** festgelegt ist.
  
![Stellen Sie sicher, dass für den Zugriff auf apps eine PIN oder einen Fingerabdruck Office auf Ein festgelegt ist.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Öffnen Sie auf dem Android-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an.
    
2. Sie werden außerdem aufgefordert, eine PIN ein- oder zu verwenden.
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Überprüfen von "PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen"

Wählen  Sie im Bereich  Richtlinie bearbeiten neben Office-Dokumentzugriffssteuerung bearbeiten aus, erweitern Sie Verwalten, wie Benutzer auf Office-Dateien auf **mobilen** Geräten zugreifen, und stellen Sie sicher, dass **pin** zurücksetzen nach der Anzahl der fehlgeschlagenen Versuche auf eine bestimmte Zahl festgelegt ist.  Dies ist standardmäßig 5. 
  
1. Öffnen Sie auf dem Android-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an.
    
2. Geben Sie so oft, wie in der Richtlinie angegeben, eine falsche PIN ein. Es wird eine Eingabeaufforderung angezeigt, in der **der Pinversuchsgrenzwert erreicht ist,** um die PIN zurückzusetzen. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Drücken Sie **PIN zurücksetzen**. Sie werden aufgefordert, sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium und müssen dann eine neue PIN festlegen.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Überprüfen von "Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Ein** festgelegt ist.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Öffnen Sie auf dem Android-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an, und geben Sie eine PIN ein, wenn sie angefordert wird.
    
2. Öffnen Sie eine E-Mail mit einer Anlage, und tippen Sie neben den Informationen zur Anlage auf den Abwärtspfeil.
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Unten auf dem Bildschirm **wird Nicht** speichern auf dem Gerät angezeigt. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Da "Auf OneDrive for Business speichern" für Android zu diesem Zeitpunkt nicht aktiviert ist, können Sie nur sehen, dass lokales Speichern blockiert ist. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Überprüfen von "Benutzer müssen sich erneut anmelden, nachdem Office-Apps für eine bestimmte Zeit im Leerlauf waren"

Wählen  Sie im Bereich  Richtlinie bearbeiten neben Office-Dokumentzugriffssteuerung bearbeiten aus, erweitern Sie Verwalten, wie Benutzer auf mobilen Geräten auf **Dateien** Office zugreifen, und stellen Sie sicher, dass Benutzer erneut anmelden müssen, nachdem **Office-Apps** im Leerlauf waren, auf einige Minuten festgelegt ist.  Dies ist standardmäßig 30 Minuten. 
  
1. Öffnen Sie auf dem Android-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an, und geben Sie eine PIN ein, wenn sie angefordert wird.
    
2. Jetzt sollte der Outlook-Posteingang angezeigt werden. Lassen Sie das Android-Gerät im Leerlauf für mindestens 30 Minuten unberührt liegen (oder einen anderen Zeitraum, der länger als die in der Richtlinie festgelegte Einstellung ist). Wahrscheinlich wird der Bildschirm des Geräts dunkel.
    
3. Zugriff Outlook auf dem Android-Gerät erneut.
    
4. Sie werden aufgefordert, Ihre PIN ein eingeben, bevor Sie erneut auf Outlook können.
    
### <a name="validate-protect-work-files-with-encryption"></a>Überprüfen von "Arbeitsdateien mit Verschlüsselung schützen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Arbeitsdateien mit Verschlüsselung schützen** auf **Ein** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Aus** festgelegt ist.
  
1. Öffnen Sie auf dem Android-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an, und geben Sie eine PIN ein, wenn sie angefordert wird.
    
2. Öffnen Sie eine E-Mail mit einigen Bilddateianlagen.
    
3. Tippen Sie neben den Informationen zur Anlage auf den Abwärtspfeil, um sie zu speichern.
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Möglicherweise werden Sie aufgefordert, Outlook den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät zu erlauben. Tippen Sie auf **Zulassen**.
    
5. Wählen Sie unten auf dem Bildschirm **Auf Gerät speichern** aus, und öffnen Sie die App **Katalog**. 
    
6. Es sollte ein verschlüsseltes Foto (oder mehrere Fotos, falls Sie mehrere Bildanlagedateien gespeichert haben) in der Liste angezeigt werden. Dieses Foto kann in der Liste "Bilder" als graues Quadrat mit einem weißen Ausrufezeichen in einem weißen Kreis in der Mitte des Quadrats angezeigt werden.
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Überprüfen, ob die Einstellungen für den App-Schutz auf Benutzergeräten funktionieren

Nachdem Sie [App-Konfigurationen für iOS-Geräte festgelegt haben](app-protection-settings-for-android-and-ios.md), um Apps zu schützen, können Sie folgendermaßen überprüfen, ob die gewählten Einstellungen funktionieren. 
  
Stellen Sie zunächst sicher, dass die Richtlinie für die App gilt, in der Sie sie überprüfen möchten.
  
1. Wechseln Sie Microsoft 365 Business Premium [Admin Center](https://portal.office.com)zu **Richtlinien** \> **bearbeiten Richtlinie**.
    
2. Wählen **Sie Anwendungsrichtlinie für iOS** für die Einstellungen aus, die Sie beim Setup erstellt haben, oder eine andere richtlinie, die Sie erstellt haben, und stellen Sie sicher, dass sie z. B. Outlook erzwungen wird. 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Überprüfen von "Für den Zugriff auf Office-Apps PIN anfordern"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern** auf **Ein** festgelegt ist.
  
![Stellen Sie sicher, dass für den Zugriff auf apps eine PIN oder einen Fingerabdruck Office auf Ein festgelegt ist.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Öffnen Sie auf dem iOS-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an.
    
2. Sie werden außerdem aufgefordert, eine PIN ein- oder zu verwenden.
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Überprüfen von "PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen"

Wählen  Sie im Bereich  Richtlinie bearbeiten neben Office-Dokumentzugriffssteuerung bearbeiten aus, erweitern Sie Verwalten, wie Benutzer auf Office-Dateien auf **mobilen** Geräten zugreifen, und stellen Sie sicher, dass **pin** zurücksetzen nach der Anzahl der fehlgeschlagenen Versuche auf eine bestimmte Zahl festgelegt ist.  Dies ist standardmäßig 5. 
  
1. Öffnen Sie auf dem iOS-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an.
    
2. Geben Sie so oft, wie in der Richtlinie angegeben, eine falsche PIN ein. Es wird eine Eingabeaufforderung angezeigt, in der **der Pinversuchsgrenzwert erreicht ist,** um die PIN zurückzusetzen. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Klicken Sie auf **OK**. Sie werden aufgefordert, sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium und müssen dann eine neue PIN festlegen.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Überprüfen von "Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Ein** festgelegt ist.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Öffnen Sie im iOS-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an, und geben Sie eine PIN ein, wenn sie angefordert wird.
    
2. Öffnen Sie eine E-Mail-Nachricht, die eine Anlage enthält, öffnen Sie die Anlage, und klicken Sie am unteren Rand des Bildschirms auf **Speichern**. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Es sollte nur eine Option für OneDrive for Business angezeigt werden. Wenn nicht, tippen **Sie auf** Konto hinzufügen, und **wählen OneDrive for Business** auf dem Bildschirm Konto **Storage hinzufügen** aus. Geben Sie die Anmeldeinformationen des Endbenutzers Microsoft 365 Business Premium, wenn Sie dazu aufgefordert werden. 
    
    Tippen Sie auf **Speichern**, und wählen Sie **OneDrive for Business** aus.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Überprüfen von "Benutzer müssen sich erneut anmelden, nachdem Office-Apps für eine bestimmte Zeit im Leerlauf waren

Wählen  Sie im Bereich  Richtlinie bearbeiten neben Office-Dokumentzugriffssteuerung bearbeiten aus, erweitern Sie Verwalten, wie Benutzer auf mobilen Geräten auf **Dateien** Office zugreifen, und stellen Sie sicher, dass Benutzer erneut anmelden müssen, nachdem **Office-Apps** im Leerlauf waren, auf einige Minuten festgelegt ist.  Dies ist standardmäßig 30 Minuten. 
  
1. Öffnen Sie im iOS-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an, und geben Sie eine PIN ein, wenn sie angefordert wird.
    
2. Jetzt sollte der Outlook-Posteingang angezeigt werden. Lassen Sie die iOS-Gerät für mindestens 30 Minuten unberührt liegen (oder einen anderen Zeitraum, der länger als die in der Richtlinie angegebene Einstellung ist). Wahrscheinlich wird der Bildschirm des Geräts dunkel.
    
3. Zugriff Outlook auf dem iOS-Gerät erneut.
    
4. Sie werden aufgefordert, Ihre PIN ein eingeben, bevor Sie erneut auf Outlook können.
    
### <a name="validate-protect-work-files-with-encryption"></a>Überprüfen von "Arbeitsdateien mit Verschlüsselung schützen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Arbeitsdateien mit Verschlüsselung schützen** auf **Ein** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Aus** festgelegt ist.
  
1. Öffnen Sie im iOS-Gerät des Benutzers Outlook, und melden Sie sich mit den Anmeldeinformationen des Benutzers Microsoft 365 Business Premium an, und geben Sie eine PIN ein, wenn sie angefordert wird.
    
2. Öffnen Sie eine E-Mail mit einigen Bilddateianlagen.
    
3. Tippen Sie auf die Anlage und dann darunter auf die Option **Speichern**. 
    
4. Öffnen Sie die App **Fotos** auf dem Startbildschirm. Es sollte ein verschlüsseltes Foto (oder mehrere, falls Sie mehrere Bildanlagedateien gespeichert haben) angezeigt werden, gespeichert, aber verschlüsselt. 
    
---

