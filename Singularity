BootStrap: docker
From: centos:centos7
# Tru Huynh <tru@pasteur.fr>

%runscript
echo "running code from the container:"
echo "singularity exec -B /run vscode-container.img /usr/bin/code "
echo "singularity exec -B /run shub://truatpasteurdotfr/singularity-docker-centos7-vscode /usr/bin/code "


%post
yum -y upgrade
# https://code.visualstudio.com/docs/setup/linux
rpm --import https://packages.microsoft.com/keys/microsoft.asc
echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo
yum -y install code
# missing Requires but provided by CentOS-7
yum -y install which xorg-x11-fonts-Type1 liberation-sans-fonts

# specific to my setup
mkdir -p /local-storage /mnt/beegfs /baycells/home /baycells/scratch /c6/shared /c6/eb /local/gensoft2 /c6/shared/rpm /Bis/Scratch2 /mnt/beegfs


%runscript
PATH=/opt/blender-2.78c-linux-glibc219-x86_64/:${PATH}
export PATH
/opt/blender-2.78c-linux-glibc219-x86_64/blender "$@"

