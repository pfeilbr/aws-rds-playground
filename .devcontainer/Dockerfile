# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.209.6/containers/javascript-node/.devcontainer/base.Dockerfile

# [Choice] Node.js version (use -bullseye variants on local arm64/Apple Silicon): 16, 14, 12, 16-bullseye, 14-bullseye, 12-bullseye, 16-buster, 14-buster, 12-buster
ARG VARIANT="16-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment if you want to install an additional version of node using nvm
# ARG EXTRA_NODE_VERSION=10
# RUN su node -c "source /usr/local/share/nvm/nvm.sh && nvm install ${EXTRA_NODE_VERSION}"

# [Optional] Uncomment if you want to install more global node modules
# RUN su node -c "npm install -g <your-package-list-here>"

# aws cli v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64-2.0.30.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && sudo ./aws/install

# aws sam cli
RUN curl -L "https://github.com/aws/aws-sam-cli/releases/download/v1.37.0/aws-sam-cli-linux-x86_64.zip" -o "aws-sam-cli-linux-x86_64.zip" && \
    unzip "aws-sam-cli-linux-x86_64.zip" -d sam-installation && \
    sudo ./sam-installation/install

# aws cdk
RUN npm -g install typescript && \
    npm install -g aws-cdk

# lumigo-cli
RUN npm install -g lumigo-cli

# homebrew installs
# ENV BREW_PREFIX=/home/linuxbrew/.linuxbrew
# ENV PATH=${BREW_PREFIX}/sbin:${BREW_PREFIX}/bin:${PATH}
# RUN brew install jq yq pipx pyenv tree 

    
