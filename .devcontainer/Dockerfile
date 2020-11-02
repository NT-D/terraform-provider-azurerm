FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Install Azure CLI
RUN curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash

# Install Terraform CLI
## Ready for using apt-add-repository
RUN sudo apt-get install --assume-yes software-properties-common
RUN sudo apt-get update

RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
RUN sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
RUN sudo apt-get update && sudo apt-get install terraform

# Install Go environment
RUN wget https://golang.org/dl/go1.15.3.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.15.3.linux-amd64.tar.gz
RUN rm go1.15.3.linux-amd64.tar.gz
ENV PATH $PATH:/usr/local/go/bin

# Install essential tools for "make build"
RUN sudo apt-get update && apt-get -y install build-essential