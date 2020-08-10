FROM python:3.8.3-buster

LABEL maintainer="contact@z3b4.xyz"
LABEL version="1.0"
LABEL description="A container for developing platformio applications in a Visual Studio Code devcontainer"
LABEL license="Apache-2.0"
LABEL repository="https://github.com/LennartZebandt/platformio-devcontainer-template"

ENV USER vscode

# Create a new user with home dir and bash as default shell
RUN useradd -ms /bin/bash $USER

# Change to home folder
WORKDIR /home/${USER}

# Install udev for managing devices
RUN apt-get update && apt-get install -y udev

# Install 99-platformio-udev.rules for platform.io udevhttps://docs.platformio.org/en/latest/faq.html#platformio-udev-rules
RUN curl -fsSL https://raw.githubusercontent.com/platformio/platformio-core/master/scripts/99-platformio-udev.rules | tee /etc/udev/rules.d/99-platformio-udev.rules

# Restart udev service to use the newly installed udev rules
RUN service udev restart

# Give our non root user the groups necessary for udev
RUN usermod -a -G dialout $USER
RUN usermod -a -G plugdev $USER

# Change to new user after setup
USER $USER