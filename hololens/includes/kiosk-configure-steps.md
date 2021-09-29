---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "129221168"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Modèle de kiosque mono-application Microsoft Intune](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Modèle de kiosque mono-application Microsoft Intune

1. Créez un profil de configuration. <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Choisissez un modèle de kiosque. <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Choisissez un kiosque mono-application ou multi-application ainsi que le type de ciblage utilisateur pour le mode kiosque. <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Choisissez l’application à exécuter en mode kiosque. <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Laissez les autres options telles quelles. <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Choisissez les groupes/appareils ou utilisateurs auxquels ce profil de configuration doit être affecté. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Passez en revue le profil de configuration, puis créez-le pour l’enregistrer.
8. Démarrez la synchronisation MDM sur l’appareil ou à partir d’Intune pour appliquer la configuration à l’appareil. [Synchronisez l’appareil à partir d’Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou sur l’appareil dans **Paramètres -> Comptes -> Professionnel ou scolaire ->** sélectionnez le compte connecté  **-> Info -> Synchroniser**.
9. Connectez-vous en tant qu’utilisateur cible pour accéder au mode kiosque.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Modèle de kiosque multi-application Microsoft Intune](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Modèle de kiosque multi-application Microsoft Intune

1. Créez un profil de configuration. <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Choisissez un modèle de kiosque. <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Choisissez un kiosque mono-application ou multi-application ainsi que le type de ciblage utilisateur pour le mode kiosque. <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Choisissez la ou les applications à exécuter en mode kiosque. <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Laissez les autres options telles quelles. <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Choisissez les groupes/appareils ou utilisateurs auxquels ce profil de configuration doit être affecté. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Passez en revue le profil de configuration, puis créez-le pour l’enregistrer.
8. Démarrez la synchronisation MDM sur l’appareil ou à partir d’Intune pour appliquer la configuration à l’appareil. [Synchronisez l’appareil à partir d’Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou sur l’appareil dans **Paramètres -> Comptes -> Professionnel ou scolaire ->** sélectionnez le compte connecté  **-> Info -> Synchroniser**.
9. Connectez-vous en tant qu’utilisateur cible pour accéder au mode kiosque.

# <a name="microsoft-intune-custom-template"></a>[Modèle personnalisé Microsoft Intune](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Modèle personnalisé Microsoft Intune

1. Créez une configuration XML pour obtenir l’expérience kiosque souhaitée. Pour commencer, consultez les [exemples ici](../hololens-kiosk-reference.md#kiosk-xml-code-samples).

1. Créer un profil de configuration personnalisé <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Spécifiez le nom du profil de configuration personnalisé, puis cliquez sur « Ajouter » dans la section « Paramètres de configuration » pour ajouter des paramètres OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Spécifiez le nom des paramètres OMA-URI.

    1. Dans la zone de texte OMA-URI, entrez **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Choisissez **Chaîne** comme type de données.
    1. Dans la zone de texte Valeur, copiez-collez le code XML de configuration de l’accès affecté (consultez les liens de référence pour obtenir des exemples en fonction de votre scénario et apportez les modifications nécessaires avant de copier-coller).
    1. Sélectionnez le bouton Enregistrer pour enregistrer le paramètre et la configuration.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Choisissez les groupes/appareils ou utilisateurs auxquels ce profil de configuration doit être affecté. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Passez en revue le profil de configuration, puis créez-le pour l’enregistrer.
1. Démarrez la synchronisation MDM sur l’appareil ou à partir d’Intune pour appliquer la configuration à l’appareil. [Synchronisez l’appareil à partir d’Intune](/mem/intune/remote-actions/device-sync#sync-a-device) ou sur l’appareil dans **Paramètres -> Comptes -> Professionnel ou scolaire ->** sélectionnez le compte connecté  **-> Info -> Synchroniser**.
1. Connectez-vous en tant qu’utilisateur cible pour accéder au mode kiosque.

# <a name="runtime-provisioning---multi-app"></a>[Provisionnement au moment de l’exécution - Multi-application](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Provisionnement au moment de l’exécution - Multi-application

1. Créez une configuration XML pour obtenir l’expérience kiosque souhaitée. Pour commencer, consultez les [exemples ici](../hololens-kiosk-reference.md#kiosk-xml-code-samples).

1. Ouvrez le [Concepteur de configuration Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Dans la page de démarrage, sélectionnez **Provisionner des appareils HoloLens**. <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Sélectionnez **Provisionner des appareils HoloLens 2**, puis Suivant. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Nommez votre projet. Ajoutez éventuellement une description. Sélectionnez **Terminer** pour continuer.

6. En bas à gauche de l’écran, sélectionnez **Basculer vers l’éditeur avancé**. Sélectionnez **Oui** pour confirmer. <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Sur le côté gauche, développez Paramètres d’exécution, AssignedAccess, puis sélectionnez **MultiAppAssignedAccess**. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Sélectionnez le bouton **Parcourir...** pour ouvrir l’Explorateur de fichiers. Sélectionnez le fichier XML du kiosque configuré.

9. Sélectionnez **Exporter**, puis **Package de provisionnement**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Remplacez le type de propriétaire par **Administrateur informatique**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Sélectionnez **Suivant** trois fois de suite. Sélectionnez ensuite **Générer**.

12. Une fois le package de provisionnement créé, ouvrez le dossier Emplacement de sortie. Le fichier .ppkg est votre package de provisionnement. Étape facultative : enregistrez votre projet.

13. Vous pouvez maintenant appliquer votre package de provisionnement. Vous pouvez appliquer un package de provisionnement à HoloLens [durant l’installation](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ou [après l’installation](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Connectez-vous en tant qu’utilisateur cible pour accéder au mode kiosque.

# <a name="runtime-provisioning---single-app"></a>[Provisionnement au moment de l’exécution - Mono-application](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Provisionnement au moment de l’exécution - Mono-application

1. Ouvrez le [Concepteur de configuration Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. Dans la page de démarrage, sélectionnez **Provisionner des appareils HoloLens**. <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Sélectionnez **Provisionner des appareils HoloLens 2**, puis Suivant. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Nommez votre projet. Ajoutez éventuellement une description. Sélectionnez **Terminer** pour continuer.

5. En bas à gauche de l’écran, sélectionnez **Basculer vers l’éditeur avancé**. Sélectionnez **Oui** pour confirmer. <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Sur le côté gauche, développez Paramètres d’exécution, AssignedAccess, puis sélectionnez **AssignedAccessSettings**. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Définissez votre kiosque dans la zone de texte. Par exemple, le code suivant crée un kiosque mono-application pour un compte local nommé LocalAccount qui est l’application Paramètres.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Sélectionnez **Exporter**, puis **Package de provisionnement**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Remplacez le type de propriétaire par **Administrateur informatique**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Sélectionnez **Suivant** trois fois de suite. Sélectionnez ensuite **Générer**.

11. Une fois le package de provisionnement créé, ouvrez le dossier Emplacement de sortie. Le fichier .ppkg est votre package de provisionnement. Étape facultative : enregistrez votre projet.

12. Vous pouvez maintenant appliquer votre package de provisionnement. Vous pouvez appliquer un package de provisionnement à HoloLens [durant l’installation](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) ou [après l’installation](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).