LAB-7 - Analyse Dynamique Mobile avec MobSF
Réalisé par : zouhairelghouate
Application analysée : diva-android-master.zip — jakhar.aseem.diva
MobSF Version : v4.5.0

Environnement utilisé
ÉlémentDétailSystème HôteWindows (Local)Émulateur AndroidPixel 6 (2) API 35MobSFv4.5.0 (Docker)JADXv1.5.0 (téléchargé automatiquement par MobSF)Docker Imageopensecurity/mobile-security-framework-mobsf:latestREST API Key652dd352a52e3f1c5d313ce3bbed11a1c8b50c75dd772a9aef65515059f07a1Credentials par défautmobsf / mobsf

Outils utilisés

MobSF : Framework d'analyse statique et dynamique des applications mobiles.
Docker : Conteneurisation de MobSF.
Android Studio AVD : Émulateur Pixel 6 API 35.
Git : Clonage du dépôt MobSF.
ADB : Communication avec l'émulateur.


Étapes du Lab
Étape 1 — Émulateur Android (Pixel 6 API 35)
L'émulateur Pixel 6 (2) API 35 a été lancé via Android Studio.
Applications visibles : YouTube, Photos, Clock, Contacts, Calendar, Camera, Chrome, Drive, Files, Gmail, Google, Maps, Messages, Phone, Safety, Settings, TMobile, Uncrackable, YouTube Music.

Étape 2 — Chargement de l'APK / Clonage MobSF
bash$ git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
Cloning into 'Mobile-Security-Framework-MobSF'...
remote: Enumerating objects: 22233, done.
remote: Counting objects: 100% (52/52), done.
remote: Compressing objects: 100% (48/48), done.
remote: Total 22233 (delta 8), reused 5 (delta 4), pack-reused 22181 (from 2)
Receiving objects: 100% (22233/22233), 1.45 GiB | 3.94 MiB/s, done.
Resolving deltas: 100% (11925/11925), done.
Updating files: 100% (530/530), done.

Étape 3 — Lancement de l'analyse (AVD MobSF)
powershellPS D:\4thS2emsi\securite mobile\lab7 mobsf\Mobile-Security-Framework-MobSF>
scripts\start_avd.ps1 MobSF_DIVA_API_30
Available AVDs:
MobSF_DIVA_API_30
Use any Android AVD 5.0 - 11, up to API 30 without Google Play (production image).
Usage: .\script.ps1 -AVD_NAME <AVD_NAME> [-START_PORT <START_PORT>]
Example: .\script.ps1 -AVD_NAME Pixel_6_Pro_API_28 -START_PORT 5554

Étape 4 — Pull de l'image Docker MobSF
bashC:\Users\zouhairelghouate> docker pull opensecurity/mobile-security-framework-mobsf:latest
latest: Pulling from opensecurity/mobile-security-framework-mobsf
0b03c5abb644: Pull complete
63706ab84aa5: Pull complete
aa0ff2f729c8: Pull complete
219a2e93422d: Pull complete
5f4836bfc719: Pull complete
792aba8f9d95: Pull complete
231aa360dc09: Pull complete
8b6abb057bb6: Pull complete
6db0909c4473: Pull complete
19851ebfeaad: Pull complete
ae14b11b20fb: Pull complete
28ec1fde30db: Pull complete
f6eeee67085b: Pull complete
Digest: sha256:3b59941ac842e5c91668d4ffd385df8a9e6e565264ffd9d9538d880272ce2c69
Status: Downloaded newer image for opensecurity/mobile-security-framework-mobsf:latest
docker.io/opensecurity/mobile-security-framework-mobsf:latest

Étape 5 — Démarrage et résultats de l'analyse
bashC:\Users\zouhairelghouate> docker run -it --rm -p 8000:8000 \
  -e MOBSF_ANALYZER_IDENTIFIER=emulator-5554 \
  opensecurity/mobile-security-framework-mobsf:latest
[INFO] 23/Mar/2026 14:24:29 - Downloading JADX from https://github.com/skylot/jadx/releases/download/v1.5.0/jadx-1.5.0.zip
[INFO] 23/Mar/2026 14:24:29 - Loading User config from: /home/mobsf/.MobSF/config.py

MobSFv4.5

[INFO] 23/Mar/2026 14:24:35 - Author: Ajin Abraham | opensecurity.in
[INFO] 23/Mar/2026 14:24:35 - Mobile Security Framework v4.5.0
REST API Key: 652dd352a52e3f1c5d313ce3bbed11a1c8b50c75dd772a9aef65515059f07a1
Default Credentials: mobsf/mobsf
[INFO] 23/Mar/2026 14:24:35 - OS Environment: linux (debian 12 bookworm) linux-6.6.87.2-microsoft-standard-WSL2-x86_64-with-glibc2.36
[INFO] 23/Mar/2026 14:24:35 - Python Version: 3.13.12
[INFO] 23/Mar/2026 14:24:35 - CPU Cores: 4, Threads: 8, RAM: 7.72 GB
[INFO] 23/Mar/2026 14:24:35 - MobSF Basic Environment Check
[INFO] 23/Mar/2026 14:24:36 - Checking for Update.
[INFO] 23/Mar/2026 14:24:36 - No updates available.
[INFO] 23/Mar/2026 14:24:56 - JADX download complete. File size: 104967983 bytes
[INFO] 23/Mar/2026 14:24:56 - Extracting JADX to /home/mobsf/.MobSF/tools/jadx/jadx-1.5.0
[INFO] 23/Mar/2026 14:24:57 - Setting execute permission for JADX directory
[INFO] 23/Mar/2026 14:24:57 - JADX installed successfully

Étape 6 — Fichier analysé
FichierDateTypeTaillediva-android-master.zip3/23/2026 3:27 PMArchive WinRAR ZIP165 KB

Étape 7 — Résultats détaillés (Static Analyzer)
Scores et informations :
MétriqueValeurSecurity Score52/100Trackers0/422App NameDivaPackagejakhar.aseem.divaMain ActivityMainActivityTarget SDKNon défini
Composants exportés :
ComposantNombreExported Activities2/17Exported Services0/0Exported Receivers0/0Exported Providers1/1

Étape 8 — Analyse des permissions
PermissionStatutDescriptionandroid.permission.INTERNETnormalAccès complet à Internetandroid.permission.READ_EXTERNAL_STORAGE🔴 dangerousLecture du stockage externeandroid.permission.WRITE_EXTERNAL_STORAGE🔴 dangerousÉcriture/suppression du stockage externe

Étape 9 — Analyse du Manifest (Données observées)
Résumé : HIGH: 0 | ⚠️ WARNING: 4 | INFO: 0 | SUPPRESSED: 0
#ProblèmeSévéritéDescription1allowBackup=true⚠️ WARNINGPermet la sauvegarde des données via ADB — extraction possible2Activity APICredsActivity non protégée⚠️ WARNINGAccessible par toute application (intent-filter présent)3Activity APICredsActivity2 non protégée⚠️ WARNINGAccessible par toute application (intent-filter présent)4Content Provider NotesProvider non protégé⚠️ WARNINGAccessible par toute application (android:exported=true)

Étape 10 — Résumé final (Code Analysis)
Résumé : 🔴 HIGH: 1 | ⚠️ WARNING: 3 | INFO: 2 | SECURE: 0 | SUPPRESSED: 0
#ProblèmeSévéritéStandardsFichiers1L'app peut écrire dans l'App Directory — données sensibles non chiffréesINFOCWE-276, MSTG-STORAGE-14InsecureDataStorageActivity.java, InjectionActivity.java2L'app enregistre des informations dans les logs — données sensibles ne doivent pas être loguéesINFOCWE-532: Insertion of Sensitive Information into Log File—

Récapitulatif des Vulnérabilités
#VulnérabilitéSévéritéStandard1allowBackup=true⚠️ WARNINGMSTG-STORAGE-82APICredsActivity exportée sans protection⚠️ WARNINGMSTG-PLATFORM-13APICredsActivity2 exportée sans protection⚠️ WARNINGMSTG-PLATFORM-14NotesProvider exporté sans protection⚠️ WARNINGMSTG-PLATFORM-25Permissions dangereuses (READ/WRITE_EXTERNAL_STORAGE)🔴 dangerousMSTG-STORAGE-26Données sensibles non chiffrées sur le disqueINFOCWE-276, MSTG-STORAGE-147Logs contenant des informations sensiblesINFOCWE-532

Conclusion
Ce lab a couvert l'analyse complète de l'application Diva avec MobSF v4.5.0 via Docker. L'analyse statique a révélé un score de sécurité de 52/100, avec 4 avertissements liés au Manifest (composants exportés non protégés, backup activé) et plusieurs problèmes d'analyse de code (stockage non chiffré, logs sensibles). MobSF offre une vue centralisée combinant Static Analyzer, Dynamic Analyzer et API pour une analyse complète des APKs Android.
