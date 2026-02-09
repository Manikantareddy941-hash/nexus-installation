# Nexus Repository Manager Installation (Ubuntu)

This guide explains how to install **Sonatype Nexus Repository Manager 3** on an Ubuntu server.
Nexus is used to host and manage artifacts like **Maven, Docker, npm, Helm, and Yum repositories**.

---

## Prerequisites

- Ubuntu 20.04 / 22.04
- Minimum 2 GB RAM (4 GB recommended)
- Java 8 or 11 (Nexus does NOT support Java 17)
- A non-root user with sudo privileges
- Port **8081** open

---

## Step 1: Update the Server

```bash

| Command | Use |
|-------|-----|
| `sudo apt update` | Update package index |

| `sudo apt upgrade -y` | Upgrade installed packages |

| `sudo apt install openjdk-11-jdk -y` | Install Java 11 (required for Nexus) |

| `java -version` | Verify Java installation |

| `sudo useradd -m -d /opt/nexus nexus` | Create a dedicated Nexus user |

| `cd /opt` | Move to installation directory |

| `sudo wget https://download.sonatype.com/nexus/3/latest-unix.tar.gz` | Download Nexus package |

| `sudo tar -xvzf latest-unix.tar.gz` | Extract Nexus archive |

| `sudo mv nexus-3* nexus` | Rename Nexus directory |

| `sudo mv sonatype-work nexusdata` | Rename Nexus data directory |

| `sudo chown -R nexus:nexus /opt/nexus` | Set ownership for Nexus files |

| `sudo chown -R nexus:nexus /opt/nexusdata` | Set ownership for Nexus data |

| `sudo nano /opt/nexus/bin/nexus.rc` | Edit Nexus run configuration |

| `run_as_user="nexus"` | Run Nexus as non-root user |

| `sudo nano /etc/systemd/system/nexus.service` | Create Nexus systemd service |

| `sudo systemctl daemon-reload` | Reload systemd services |

| `sudo systemctl enable nexus` | Enable Nexus at boot |

| `sudo systemctl start nexus` | Start Nexus service |

| `sudo systemctl status nexus` | Check Nexus service status |

| `cat /opt/nexusdata/admin.password` | Get initial admin password |
