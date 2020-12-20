# 3.1.201 [/usr/share/dotnet/sdk]

FROM mcr.microsoft.com/dotnet/sdk:5.0-buster-slim

ARG project_dir=/var/project
ARG user=developer

RUN \
groupadd -g 1000 developer && \
useradd -g developer -G sudo -m -s /bin/bash ${user} && \
echo "Defaults visiblepw" >> /etc/sudoers && \
echo "${user} ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN mkdir ${project_dir}
USER ${user}

WORKDIR ${project_dir}

CMD [ "dotnet", "--list-sdks" ]

# docker build --build-arg user=$USER -t dotnet .
# docker run --rm -ti dotnet dotnet --version

# docker run --rm -ti -v $(pwd):/var/project -w /var/project dotnet dotnet new -n blazor
# docker run --rm -ti -v $(pwd):/var/project -w /var/project -p 5000:5000 -p 5001:5001 dotnet dotnet watch -p blazor run
