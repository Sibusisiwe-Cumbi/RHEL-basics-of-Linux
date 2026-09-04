What I Learned:
This lesson introduced systemd, the system and service manager used by RHEL. It manages system startup, services, dependencies, and other system resources.

systemd
systemd is responsible for:
•	Starting the system during boot.
•	Starting and stopping services.
•	Managing the order in which services start.
•	Managing system events and dependencies.
•	Controlling which services start automatically at boot.
systemd manages resources using units.

systemd Unit Types
Different unit types represent different resources:
•	.service → system services and daemons.
•	.socket → socket-based or on-demand service activation.
•	.timer → scheduled tasks.
•	.path → watches files or directories for changes.
•	.target → groups related units together.

The key idea is:
systemd is the manager; units are the things it manages.

systemctl
systemctl is the main command used to interact with systemd.
systemctl start <service>
Starts a service immediately.
systemctl stop <service>
Stops a service immediately.
systemctl restart <service>
Stops and starts the service again.
systemctl status <service>
Checks the current state of a service.
systemctl enable <service>
Configures a service to start automatically at boot.
systemctl disable <service>
Prevents a service from starting automatically at boot.
systemctl enable --now <service>
Enables the service at boot and starts it immediately.

Start vs Enable
This is an important distinction:
start/stop → controls the service in the current session.
enable/disable → controls the service's boot behaviour.
Starting a service does not automatically configure it to start after a reboot.

Services
A service is a background program managed by systemd and is often referred to as a daemon.
Installing software does not necessarily mean that its service is running or configured to start at boot.

A typical administrator workflow is:
Install → Start → Enable → Check status
When a service's configuration changes, the service can usually be restarted instead of rebooting the entire system.

Apache HTTP Server
RHEL commonly uses Apache HTTP Server, provided by the httpd package.
The package is installed using DNF:
dnf install -y httpd
Apache runs as a systemd service.
Its default web content directory is:
/var/www/html/
HTTP normally uses TCP port 80.

firewalld
firewalld is the dynamic firewall management service used by RHEL.
It controls network traffic according to configured firewall rules.
Instead of only thinking about whether a port is open, it is useful to think of firewalld as controlling which network traffic is allowed through the system's firewall.

firewalld Zones
firewalld uses zones to apply different firewall rules and levels of trust to network connections.
The public zone is commonly used for network interfaces connected to untrusted or public networks.

firewalld Services
firewalld provides predefined services that represent common network services and their associated ports.
For example:
•	http → TCP port 80
•	https → TCP port 443
Using services makes firewall rules easier to understand and manage.

Runtime vs Permanent Firewall Rules
Firewall configuration can be applied as either runtime or permanent configuration.

Runtime configuration:
•	Takes effect immediately.
•	Does not survive a firewall or system restart.

Permanent configuration:
•	Saves the configuration.
•	Survives a restart or reload.

Allow HTTP immediately:
firewall-cmd --add-service=http
Save the HTTP rule permanently:
firewall-cmd --add-service=http --permanent
View the current firewall configuration:
firewall-cmd --list-all

Final Mental Model
systemd → manages the system and services.
systemctl → controls systemd.
service → background program managed by systemd.
firewalld → controls network traffic.
firewall-cmd → controls firewalld.

The two important distinctions are:
Start is not Enable
Start controls now. Enable controls boot.
Runtime is not Permanent
Runtime affects now. Permanent survives restarts.

Overall Understanding
systemd provides a central way to manage services and system resources. systemctl is used to control those services, while firewalld manages network traffic and firewall-cmd is used to configure the firewall.

