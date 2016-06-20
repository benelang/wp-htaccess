# htaccess für Wordpress

Dieses Repository enthält eine Version der .htaccess Datei, die den Zugriff auf Dateien verbietet, die für Sicherheitslücken bekannt sind. Für jedes neue Wordpress das installiert wird sollte dieses Repository in das Verzeichnis geklont werden, dass die Wordpressinstallation enthält.

## Setup
### Repository auschecken
Dieses Repository muss in das Wordpressverzeichnis geklont werden. Für mehr Informationen bietet Bitbucket eine [Anleitung](https://confluence.atlassian.com/bitbucket/clone-a-repository-223217891.html).

### .htpasswd erstellen
Das Backend (konkret die Datei wp-login.php) ist durch HTTP-Basic-Auth vor Brute-Force Attacken geschützt. Damit ein Zugriff auf das Backend möglich ist, muss eine Datei auf den Server gelegt werden, die die Zugangsdaten enthält. Diese Datei muss .htpasswd heißen.

Wenn ein Kunde mehrere Wordpressinstanzen hat, ist es möglich, die .htpasswd in das Homeverzeichnis zu legen und damit das gleichhe Passwort für mehrere Wordpressinstanzen verwendet werden.

In der .htpasswd finden sich ein Benutzername und ein Passwort. Der Inhalt der Datei lässt sich am einfachsten mit einem [Generator](http://www.htaccesstools.com/htpasswd-generator/) erstellen.

### Pfad zur .htpasswd anpassen
Der Pfad zur .htpasswd Datei muss in der .htaccess Datei ergänzt werden:
``` bash
  AuthUserFile /var/customers/webs/customer/wordpress/.htpasswd
```

# Hilfe und Support
Bei Fragen oder Problemen hilft eine E-Mail mit einer konkreten Beschreibung des Problems an [it@schuelerbuero.de](mailto:it@schuelerbuero.de) weiter.
