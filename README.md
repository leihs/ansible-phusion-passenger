# ansible-phusion-passenger

Turns any Debian GNU/Linux 7.x (wheezy) server into a Rails server using Phusion Passenger.

Just add this role to any server you want to pimp like that. It doesn't do much, just:

* Adds the official Phusion Passenger package source.
* Runs apt-get update.
* Installs the Phusion Passenger Apache module.
* Reloads Apache.

This means you will also receive the "standard" system-wide Ruby under `/usr/bin` because Phusion's Passenger packages depend on it. So if you have virtual hosts that need other Rubies, make sure those other Rubies are also installed, or are available via a Ruby version manager. Then set `PassengerRuby` to that particular Ruby for that particular virtual host.

## Adding to your own Ansible dir

If you stick reasonably closely to Ansible's recommended directory layout and if you keep your Ansible stuff in a git repo, you can add this role as a submodule:

    git submodule add https://github.com/psy-q/ansible-phusion-passenger.git roles/servers/rails
    git submodule init
    git submodule update

Of course you use a target path that's cooler than mine.
