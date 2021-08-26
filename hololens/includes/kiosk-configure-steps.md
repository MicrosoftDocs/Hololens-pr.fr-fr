---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859218"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune modèle kiosque d’application unique](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune modèle kiosque d’application unique

1. Créer un profil de configuration <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Choisir un modèle plein écran <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Choisissez une application unique ou plusieurs bornes d’applications et choisissez le type de ciblage utilisateur pour le mode plein écran <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Choisir l’application à exécuter en mode plein écran <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Laissez les autres options telles quelles <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Choisir les groupes/appareils ou utilisateurs auxquels ce profil de configuration doit être affecté <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Examiner et créer pour enregistrer le profil de configuration
8. Exécutez la synchronisation MDM à partir de l’appareil ou d’Intune pour appliquer la configuration à l’appareil. [synchroniser des appareils à partir d’Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou sur un appareil par le biais de **comptes Paramètres->-> professionnel ou scolaire->** sélectionnez le compte connecté **-> la synchronisation**
9. Connectez-vous en tant qu’utilisateur cible pour découvrir la borne.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune modèle kiosque d’applications multiples](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune modèle kiosque d’applications multiples

1. Créer un profil de configuration <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Choisir un modèle plein écran <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Choisissez une application unique ou plusieurs bornes d’applications et choisissez le type de ciblage utilisateur pour le mode plein écran <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Choisir les applications à exécuter en mode plein écran <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Laissez les autres options telles quelles <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Choisir les groupes/appareils ou utilisateurs auxquels ce profil de configuration doit être affecté <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Examiner et créer pour enregistrer le profil de configuration
8. Exécutez la synchronisation MDM à partir de l’appareil ou d’Intune pour appliquer la configuration à l’appareil. [synchroniser des appareils à partir d’Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou sur un appareil par le biais de **comptes Paramètres->-> professionnel ou scolaire->** sélectionnez le compte connecté **-> la synchronisation**
9. Connectez-vous en tant qu’utilisateur cible pour découvrir la borne.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune modèle personnalisé](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune modèle personnalisé

1. Créez une configuration XML pour l’expérience plein écran souhaitée. Consultez les [exemples](../hololens-kiosk-reference.md#kiosk-xml-code-samples) ici pour commencer.

1. Créer un profil de configuration personnalisé <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Spécifiez le nom du profil de configuration personnalisé, puis cliquez sur « Ajouter » dans la section « paramètres de configuration » pour ajouter des paramètres OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Spécifiez le nom des paramètres OMA-URI.

    1. Dans la zone de texte OMA-URI, entrez **./Device/Vendor/msft/AssignedAccess/configuration**
    1. Choisissez le type de données **chaîne**.
    1. Dans la zone de texte valeur, copiez-collez le fichier XML de configuration d’accès assigné (consultez les liens de référence pour obtenir des exemples en fonction de votre scénario et mettez à jour selon vos besoins avant de copier-coller).
    1. Sélectionnez le bouton enregistrer pour enregistrer le paramètre et la configuration.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Choisissez les groupes/appareils ou utilisateurs auxquels ce profil de configuration doit être affecté. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Passez en revue et créez pour enregistrer le profil de configuration.
1. Exécutez la synchronisation MDM à partir de l’appareil ou d’Intune pour appliquer la configuration à l’appareil. [synchroniser des appareils à partir d’Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou sur un appareil par le biais de **comptes Paramètres->-> professionnel ou scolaire->** sélectionnez le compte connecté **-> la synchronisation**
1. Connectez-vous en tant qu’utilisateur cible pour découvrir la borne.

# <a name="runtime-provisioning---multi-app"></a>[Approvisionnement du runtime-applications multiples](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Approvisionnement du runtime-applications multiples

1. Créez une configuration XML pour l’expérience plein écran souhaitée. Consultez les [exemples](../hololens-kiosk-reference.md#kiosk-xml-code-samples) ici pour commencer.

1. ouvrez le [concepteur de Configuration Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. dans la page de démarrage **, sélectionnez configurer des appareils HoloLens.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. sélectionnez **approvisionner HoloLens 2 appareils,** puis sélectionnez suivant. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Nommez votre projet. Vous pouvez également écrire une description. Sélectionnez **Terminer** pour continuer.

6. En bas à gauche de l’écran, sélectionnez **basculer vers l’éditeur avancé.** Confirmez le basculement vers l’éditeur avancé en sélectionnant **Oui.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Sur le côté gauche, développez Paramètres d’exécution, AssignedAccess et sélectionnez **MultiAppAssignedAccess**. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Sélectionnez le bouton **Parcourir...** pour ouvrir l’Explorateur de fichiers. Et sélectionnez le fichier XML Kiosk configuré.

9. Sélectionnez **Exporter** , puis **package d’approvisionnement**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Changez le type de propriétaire en **administrateur informatique**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Sélectionnez **Suivant** trois fois de suite. Puis sélectionnez **générer**.

12. Une fois le package d’approvisionnement créé, ouvrez le dossier emplacement de sortie. Le fichier. ppkg est votre package de configuration. Étape facultative : enregistrez votre projet.

13. Vous pouvez maintenant appliquer votre package d’approvisionnement. vous pouvez [appliquer un package d’approvisionnement à HoloLens lors](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) de l’installation ou [appliquer un package d’approvisionnement à HoloLens après l’installation](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Connectez-vous en tant qu’utilisateur cible pour découvrir la borne.

# <a name="runtime-provisioning---single-app"></a>[Approvisionnement du runtime-application unique](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Approvisionnement du runtime-application unique

1. ouvrez le [concepteur de Configuration Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. dans la page de démarrage **, sélectionnez configurer des appareils HoloLens.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. sélectionnez **approvisionner HoloLens 2 appareils,** puis sélectionnez suivant. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Nommez votre projet. Vous pouvez également écrire une description. Sélectionnez **Terminer** pour continuer.

5. En bas à gauche de l’écran, sélectionnez **basculer vers l’éditeur avancé.** Confirmez le basculement vers l’éditeur avancé en sélectionnant **Oui.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Sur le côté gauche, développez Paramètres d’exécution, AssignedAccess et sélectionnez **AssignedAccessSettings**. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Définissez votre kiosque dans la zone de texte. Par exemple, le code suivant crée une borne d’application unique pour un compte local nommé LocalAccount qui est l’application paramètres.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Sélectionnez **Exporter** , puis **package d’approvisionnement**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Changez le type de propriétaire en **administrateur informatique**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Sélectionnez **Suivant** trois fois de suite. Puis sélectionnez **générer**.

11. Une fois le package d’approvisionnement créé, ouvrez le dossier emplacement de sortie. Le fichier. ppkg est votre package de configuration. Étape facultative : enregistrez votre projet.

12. Vous pouvez maintenant appliquer votre package d’approvisionnement. vous pouvez [appliquer un package d’approvisionnement à HoloLens lors](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) de l’installation ou [appliquer un package d’approvisionnement à HoloLens après l’installation](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).