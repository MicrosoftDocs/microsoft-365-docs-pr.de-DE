---
title: Überprüfen der APP-Schutzeinstellungen auf Android-oder IOS-Geräten
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 309dbf5bdba81bbf8ad0a9707c136a03c4a28586
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575526"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Überprüfen der APP-Schutzeinstellungen auf Android-oder IOS-Geräten

Befolgen Sie die Anweisungen in den folgenden Abschnitten, um Einstellungen für den App-Schutz auf Android-oder IOS-Geräten zu validieren.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Überprüfen, ob die Einstellungen für den App-Schutz auf Benutzergeräten funktionieren

Nachdem Sie [App-Konfigurationen für Android-Geräte festgelegt haben](app-protection-settings-for-android-and-ios.md), um die Apps zu schützen, können Sie folgendermaßen überprüfen, ob die gewählten Einstellungen funktionieren. 
  
Stellen Sie zuerst sicher, dass die Richtlinie auf die App angewendet wird, in der Sie sie überprüfen möchten.
  
1. Wechseln Sie im Microsoft 365 Business [Admin Center](https://portal.office.com) zu **Richtlinien** \> **Richtlinie bearbeiten**.
    
2. Wählen Sie für die bei der Einrichtung erstellten Einstellungen die **Anwendungsrichtlinie für Android** oder eine andere von Ihnen erstellte Richtlinie aus, und vergewissern Sie sich, dass sie z. B. für Outlook erzwungen wird. 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Überprüfen von "Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern** auf **Ein** festgelegt ist.
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, und melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an.
    
2. Sie werden auch aufgefordert, eine PIN einzugeben oder einen Fingerabdruck zu verwenden.
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Überprüfen von "PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen** auf eine Zahl (standardmäßig "5") festgelegt ist. 
  
1. Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, und melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an.
    
2. Geben Sie so oft, wie in der Richtlinie angegeben, eine falsche PIN ein. Eine Eingabeaufforderung, die besagt **Maximale Anzahl von PIN-Eingabeversuchen erreicht** wird angezeigt, um die PIN zurückzusetzen. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Drücken Sie **PIN zurücksetzen**. Sie werden aufgefordert, sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers anzumelden, und müssen dann eine neue PIN festlegen.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Überprüfen von "Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Ein** festgelegt ist.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.
    
2. Öffnen Sie eine E-Mail mit einer Anlage, und tippen Sie neben den Informationen zur Anlage auf den Abwärtspfeil.
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Unten auf dem Bildschirm wird **Speichern auf Gerät nicht möglich** angezeigt. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Da "Auf OneDrive for Business speichern" für Android zu diesem Zeitpunkt nicht aktiviert ist, können Sie nur sehen, dass lokales Speichern blockiert ist. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Überprüfen von "Benutzer müssen sich erneut anmelden, nachdem Office-Apps für eine bestimmte Zeit im Leerlauf waren"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für** auf eine Zahl (standardmäßig "30 Minuten") festgelegt ist. 
  
1. Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.
    
2. Jetzt sollte der Outlook-Posteingang angezeigt werden. Lassen Sie das Android-Gerät im Leerlauf für mindestens 30 Minuten unberührt liegen (oder einen anderen Zeitraum, der länger als die in der Richtlinie festgelegte Einstellung ist). Wahrscheinlich wird der Bildschirm des Geräts dunkel.
    
3. Greifen Sie auf dem Android-Gerät erneut auf Outlook zu.
    
4. Sie werden aufgefordert, Ihre PIN einzugeben, bevor Sie Outlook wieder öffnen können.
    
### <a name="validate-protect-work-files-with-encryption"></a>Überprüfen von "Arbeitsdateien mit Verschlüsselung schützen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Arbeitsdateien mit Verschlüsselung schützen** auf **Ein** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Aus** festgelegt ist.
  
1. Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.
    
2. Öffnen Sie eine E-Mail mit einigen Bilddateianlagen.
    
3. Tippen Sie neben den Informationen zur Anlage auf den Abwärtspfeil, um sie zu speichern.
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Möglicherweise werden Sie aufgefordert, Outlook den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät zu erlauben. Tippen Sie auf **Zulassen**.
    
5. Wählen Sie unten auf dem Bildschirm **Auf Gerät speichern** aus, und öffnen Sie die App **Katalog**. 
    
6. Es sollte ein verschlüsseltes Foto (oder mehrere Fotos, falls Sie mehrere Bildanlagedateien gespeichert haben) in der Liste angezeigt werden. Dieses Foto kann in der Liste "Bilder" als graues Quadrat mit einem weißen Ausrufezeichen in einem weißen Kreis in der Mitte des Quadrats angezeigt werden.
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Überprüfen, ob die Einstellungen für den App-Schutz auf Benutzergeräten funktionieren

Nachdem Sie [App-Konfigurationen für iOS-Geräte festgelegt haben](app-protection-settings-for-android-and-ios.md), um Apps zu schützen, können Sie folgendermaßen überprüfen, ob die gewählten Einstellungen funktionieren. 
  
Stellen Sie zuerst sicher, dass die Richtlinie auf die App angewendet wird, in der Sie sie überprüfen möchten.
  
1. Wechseln Sie im Microsoft 365 Business [Admin Center](https://portal.office.com) zu **Richtlinien** \> **Richtlinie bearbeiten**.
    
2. Wählen Sie für die bei der Installation erstellten Einstellungen die **Anwendungsrichtlinie für iOS** oder eine andere Richtlinie aus, die Sie erstellt haben, und vergewissern Sie sich, dass sie z. B. für Outlook durchgesetzt wird. 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Überprüfen von "Für den Zugriff auf Office-Apps PIN anfordern"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern** auf **Ein** festgelegt ist.
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, und melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an.
    
2. Sie werden aufgefordert, zusätzlich eine PIN oder einen Fingerabdruck einzugeben.
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Überprüfen von "PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen"

Wählen Sie im Bereich **Richtlinie bearbeiten** die Option **Bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen** auf eine Zahl (standardmäßig "5") festgelegt ist. 
  
1. Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, und melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an.
    
2. Geben Sie so oft, wie in der Richtlinie angegeben, eine falsche PIN ein. Eine Eingabeaufforderung, die besagt **Maximale Anzahl von PIN-Eingabeversuchen erreicht** wird angezeigt, um die PIN zurückzusetzen. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Klicken Sie auf **OK**. Sie werden aufgefordert, sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers anzumelden, und müssen dann eine neue PIN festlegen.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Überprüfen von "Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen"

Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Ein** festgelegt ist.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.
    
2. Öffnen Sie eine E-Mail-Nachricht, die eine Anlage enthält, öffnen Sie die Anlage, und klicken Sie am unteren Rand des Bildschirms auf **Speichern**. 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Es sollte nur eine Option für OneDrive for Business angezeigt werden. Wenn dies nicht der Fall ist, tippen Sie auf **Konto hinzufügen**, und wählen Sie im Bildschirm **Speicherkonto hinzufügen** die Option **OneDrive for Business** aus. Stellen Sie das Microsoft 365 Business des Endbenutzers zum Anmelden bereit, falls Sie dazu aufgefordert werden. 
    
    Tippen Sie auf **Speichern**, und wählen Sie **OneDrive for Business** aus.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Überprüfen von "Benutzer müssen sich erneut anmelden, nachdem Office-Apps für eine bestimmte Zeit im Leerlauf waren

Wählen Sie im Bereich **Richtlinie bearbeiten** die Option **Bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für** auf eine Zahl (standardmäßig "30 Minuten") festgelegt ist. 
  
1. Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.
    
2. Jetzt sollte der Outlook-Posteingang angezeigt werden. Lassen Sie die iOS-Gerät für mindestens 30 Minuten unberührt liegen (oder einen anderen Zeitraum, der länger als die in der Richtlinie angegebene Einstellung ist). Wahrscheinlich wird der Bildschirm des Geräts dunkel.
    
3. Greifen Sie auf dem iOS-Gerät erneut auf Outlook zu.
    
4. Sie werden aufgefordert, Ihre PIN einzugeben, bevor Sie Outlook wieder öffnen können.
    
### <a name="validate-protect-work-files-with-encryption"></a>Überprüfen von "Arbeitsdateien mit Verschlüsselung schützen"

Wählen Sie im Bereich **Richtlinie bearbeiten** die Option **Bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Arbeitsdateien mit Verschlüsselung schützen** auf **Ein** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Aus** festgelegt ist.
  
1. Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.
    
2. Öffnen Sie eine E-Mail-Nachricht, die einige Bilddateianlagen enthält.
    
3. Tippen Sie auf die Anlage und dann darunter auf die Option **Speichern**. 
    
4. Öffnen Sie die App **Fotos** auf dem Startbildschirm. Es sollte ein verschlüsseltes Foto (oder mehrere, falls Sie mehrere Bildanlagedateien gespeichert haben) angezeigt werden, gespeichert, aber verschlüsselt. 
    
---

