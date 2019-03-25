# Modul 300 LB02

Dies ist die LB02 Dokumentation von Timon Müller.

#### Idee

Ich habe mich für einen Apache Webserver entschieden, da ich diesen im Modul 239 auch brauchen kann und Herr Kaelin uns dies empfohlen hat.

#### Vorgehen 

Ich habe mich für die Vagrant Box "ubuntu/xenial64" entschieden, da diese die am meisten gebrauchte ist.  Diese Box konnte ich dann mit dem Vagrantfile konfigurieren. 

#### Konfiguration

###### Portweiterleitung

Zuerst leitete ich den Port "8080" des Hosts auf den Port "80" der Vagrant Vm um. 

###### Shared Folder

Danach definierte ich einen shared Folder. Dies hat denn Vorteil, das ich z.B. das "index.html" File direkt auf dem Host bearbeiten kann. 

###### Disksize

Um die Disksize anzupassen, musste ich noch ein Plugin installieren, dies ging sehr einfach mit diesem Befehl:

``vagrant plugin install vagrant-disksize``

Die Disksize habe ich auf 30GB festgelegt

###### Arbeitsspeicher

Der Virtuellen Maschine gab ich 2048 MB Arbeitsspeicher.

###### Sicherheit

Als Firewall benutze ich "ufw". Uncomplicated Firewall(ufw) ist standartmässig vorinstalliert bei ubuntu. Diese Konfigurierte ich dann mit inline commands. Ich öffnete den Port 80 (HTTP) allgemein und den Port 22 (SSH) vom localhost (127.0.0.1) her. zum schluss musste ich ufw noch enablen mit: 

`ufw enable`

###### Update

Des weiteren führte ich noch ein Update durch mit:

`apt-get update`

###### Apache

Ich entschied mich für Apache2 und installierte diesen mit dem inline command: 

`apt-get -y install apache2`

#### Arbeitsmittel

Für die Arbeitsmittel benutze ich folgende Tools:

1. Git Bash - CLI
2. Atom - Code Editor
3. Vagrant 
4. VirtualBox
5. Typora - Markdown Editor

#### Virtuelle Umgebung

Ich habe einen Apache Server erstellt welcher auf Ubuntu/Xenial64 basiert. Dies läuft in einer Virtualbox Umgebung.

#### Test

Der Apacheserver ist ereichbar, wenn man auf dem Host dies im Browser eingibt:

[http://localhost:8080/index.html]()

Die VM kann mit `vagrant ssh`  erreicht werden.

#### Reflexion

Ich konnte in dieser LB sehr viel lernen, da ich zuvor noch nie mit Vagrant gearbeitet habe und besonders darüber viel lernen konnte. Ich finde Vagrant ein sehr nützliches Tool, welches ich sicherlich wieder brauchen werde. Über GitHub und Editors wusste ich schon ziemlich gut bescheid, aber es war sehr gut wieder ein Update zu erhalten. Der Einstieg in Markdown war für mich sehr hilfreich, da ich es immer zu mühsam fand aber ich nun mit Typora einen sehr guten Editor fand welcher das erstellen von Markdown Dokumentation massiv erleichtert.



###### 