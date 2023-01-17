FROM node:18-alpine3.17 AS setup

# Packages needed
RUN apk update
RUN apk add --update --no-cache build-base git openssl openssl-dev neovim tree c-ares-dev util-linux-dev libwebsockets-dev libxslt
RUN apk add mosquitto && apk add coreutils 
RUN apk add fzf

# RUN apk add --upgrade fzf-zsh-completion
RUN npm install -g prettier
RUN npm install -g expo-cli
ENV RUNNING_IN_DOCKER true



# we install the dependencies for ZSH
RUN apk --no-cache add zsh curl git

USER node

# we just create a a folder to put our app in, 
# and give ownership of it to the, by default, user node
#RUN mkdir -p /app 
#&& chown -R node:node /app

# Oh My ZSH - INSTALLATION
RUN cd ~ && wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh && sh install.sh
RUN /bin/zsh ~/.zshrc
RUN cd ~ .oh-my-zsh/custom/plugins/ && git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
RUN cd ~ .oh-my-zsh/custom/plugins/ && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
RUN cp -r ~/.oh-my-zsh/plugins/fzf ~/.oh-my-zsh/custom/plugins

RUN mkdir -p ~/.config/nvim/autoload
RUN cd ~/.config/nvim/autoload \
&& wget https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
#RUN cd ~/.config/nvim && nvim +'PlugInstall --sync' +qa

USER root

RUN chmod +s /bin/su
RUN chmod +s /usr/bin/passwd

RUN echo "root:123456" | chpasswd




