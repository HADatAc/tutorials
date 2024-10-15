## Installing Java 11

The installation of the Java 11 depends on the machine's Operational System.

### Ubuntu

Installing Java 11 on linux, type the following code on terminal:
\`\`\`bash
sudo apt-get install openjdk-11-jdk
\`\`\`

### Windows and macOS

To install Java 11 on Windows, execute the following steps:

1. Download the respective Java 11 installer from official [Oracle web site](https://www.oracle.com/pt/java/technologies/javase/jdk11-archive-downloads.html);
2. Execute the downloaded file and follow the respective tutorial:
   - [Setup on Windows](https://www.java.com/en/download/help/windows_manual_download.html)
   - [Setup on macOS](https://www.java.com/en/download/help/mac_install.html)

## Installing `sbt`

### Ubuntu and other Debian-based distributions

[DEB](https://dl.bintray.com/sbt/debian/sbt-1.9.8.deb) package is officially supported by sbt.

Ubuntu and other Debian-based distributions use the DEB format, but usually, you don’t install your software from a local DEB file. Instead, they come with package managers for the command line (e.g. `apt-get`, `aptitude`) or a graphical user interface (e.g. Synaptic). Run the following from the terminal to install `sbt` (You’ll need superuser privileges to do so, hence the `sudo`).

\`\`\`bash
sudo apt-get update
sudo apt-get install apt-transport-https curl gnupg -yqq
echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | sudo tee /etc/apt/sources.list.d/sbt.list
echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | sudo tee /etc/apt/sources.list.d/sbt_old.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo -H gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/scalasbt-release.gpg --import
sudo chmod 644 /etc/apt/trusted.gpg.d/scalasbt-release.gpg
sudo apt-get update
sudo apt-get install sbt
\`\`\`

### Windows and macOS

To install on Windows or macOS, follow the official `sbt` tutorials:

- [Windows](https://www.scala-sbt.org/1.x/docs/Installing-sbt-on-Windows.html)
- [macOS](https://www.scala-sbt.org/1.x/docs/Installing-sbt-on-Mac.html)
