FROM mlaxwong/php:8.2-dev

# Working dir
WORKDIR /workspace
VOLUME /workspace

# VSCode as Git editor 
RUN git config --global core.editor "code --wait"

ENTRYPOINT ["bash"]