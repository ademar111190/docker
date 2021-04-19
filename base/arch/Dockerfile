FROM archlinux:base-20210404.0.18927

# pacman
RUN yes | pacman -Syu
RUN yes | pacman -S neofetch
RUN yes | pacman -S --noconfirm base-devel
RUN yes | pacman -S git
RUN yes | pacman -S go

# Sudo
RUN echo 'root ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers
RUN echo 'nobody ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

# yay
RUN git clone https://aur.archlinux.org/yay.git
RUN chmod 777 yay
RUN mkdir -p /.cache/go-build
RUN chmod 777 /.cache/go-build
WORKDIR /yay
RUN yes | sudo -u nobody makepkg -si
WORKDIR /
RUN rm -rf yay /.cache/go-build
RUN yes | yay -Syu

# command
CMD neofetch
