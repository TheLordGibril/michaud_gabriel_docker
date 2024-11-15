Aller dans le fichier hosts de windows `C:\Windows\System32\drivers\etc\hosts` puis ajouter ces trois lignes :

127.0.0.1 frontend.localhost

127.0.0.1 backend.localhost

127.0.0.1 phpmyadmin.localhost

---

Aller dans la racine du projet

exécuter docker-compose -d --build

Si tout se passe bien, l'installation est terminée.