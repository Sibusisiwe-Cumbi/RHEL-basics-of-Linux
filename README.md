# Red Hat Enterprise Linux Technical Overview

This repository documents my learning journey through **Red Hat's Linux Technical Overview (RH024)** course.

The course introduced me to the fundamentals of **Red Hat Enterprise Linux (RHEL)** and Linux system administration. I used the course to build on my existing Software Engineering experience and better understand what happens at the operating-system and infrastructure level behind the applications I develop and deploy.

## What I Learned

Throughout the course, I covered the following areas:

### Linux Fundamentals

* Understanding the Linux kernel and the role of an operating system.
* The RHEL ecosystem, including Fedora, CentOS Stream, and RHEL.
* Using the Linux shell and understanding command structure.
* Finding information through Linux documentation and `man` pages.
* Navigating the Linux filesystem.
* Managing files and directories from the command line.
* Basic Vim usage.

### Users, Groups and Security

* Managing local users and groups.
* Understanding `sudo` and administrative privileges.
* Understanding UIDs and why user identity matters.
* Managing the `wheel` group.
* File permissions and ownership.
* Understanding `r`, `w`, and `x` permissions.
* Using `chmod`, `chown`, and `chgrp`.
* Applying the principle of least privilege.

### Networking

* Understanding how Linux network interfaces work.
* Using NetworkManager to manage network connections.
* Using `nmcli` and `nmtui`.
* Checking IP addresses and network interfaces with `ip`.
* Understanding routing and default gateways.
* Understanding DNS configuration.
* Configuring static network settings.

### Software and System Updates

* Registering RHEL systems with Red Hat.
* Understanding the Red Hat Content Delivery Network and Satellite.
* Managing software with DNF.
* Understanding Red Hat errata, CVEs, and CVSS.
* Finding and applying security updates.
* Understanding when a system may require a reboot after updates.

### Services and System Management

* Understanding `systemd` and its role in managing Linux systems.
* Working with systemd units and services.
* Using `systemctl` to start, stop, restart, enable, and check services.
* Understanding the difference between starting a service and enabling it at boot.
* Understanding `firewalld`, zones, services, and firewall rules.
* Understanding the difference between runtime and permanent firewall configuration.

### Application Deployment

One of the areas I found most interesting was learning how Linux can be used to properly manage and deploy applications.

I connected these concepts to my **Java Robot World project**, where I worked with a server, client-server communication, ports, Docker, and CI/CD.

The course helped me understand how the Linux environment underneath an application can be managed more systematically. For example, a Java server such as Robot World could be configured as a **systemd service**, allowing it to start automatically, restart after failures, and be managed through `systemctl`.

I also learned how application availability depends on more than simply running the application:

**Application → Listening Port → Firewall → Client Connection**

### Image-Based RHEL

Another topic that stood out to me was **image-based RHEL**.

Instead of manually configuring every server over time, an entire system can be defined and deployed as a versioned image. This provides:

* Consistency
* Predictability
* Repeatability
* Easier upgrades
* Rollback capabilities

This connected strongly with my previous experience using **Docker and CI/CD in the Robot World project**. While a Docker image packages an application and its environment, image-based RHEL takes the concept further by managing the **complete operating system environment**.

I also learned about **golden images**, **RHEL Image Builder**, and **blueprints** for defining the desired system configuration.

### RHEL Web Console

The course also introduced **Cockpit**, the RHEL Web Console.

Cockpit provides a graphical interface for managing RHEL systems, including:

* System resources and logs.
* Services.
* Networking.
* Storage.
* Firewall configuration.
* Users.
* Containers and virtual machines.

An important takeaway was that Cockpit does not replace the Linux command line. It provides a graphical layer over the same underlying RHEL administration capabilities.

## Key Takeaways

The course helped me understand Linux beyond simply using the command line.

Some of my biggest takeaways were:

* **Linux systems are managed through clearly defined resources, services, users, permissions, and configurations.**
* **Networking requires both a correctly configured application and correctly configured network access.**
* **systemd provides a structured way to manage applications and services.**
* **Security involves controlling users, permissions, services, and network traffic.**
* **Automation and standardisation make deployments more predictable and repeatable.**
* **Image-based deployment provides a way to manage an entire system as a versioned environment.**

Most importantly, I was able to relate the Linux concepts from this course back to my existing Software Engineering experience. Concepts that I previously encountered while building and deploying **Robot World** — such as servers, ports, Docker, CI/CD, and application deployment — became easier to understand from an infrastructure perspective.

## Course

**Red Hat Enterprise Linux Technical Overview (RH024)**

This repository contains my notes and key learnings from the course, organised by topic/lesson.
