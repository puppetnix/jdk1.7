# Oracle java jdk7 debian package

##BUILD DEB PACKAGE
### Download jdk archive 

    wget --continue --no-check-certificate -O jdk-7u45-linux-x64.tar.gz --header "Cookie: gpw_e24=h" http://download.oracle.com/otn-pub/java/jdk/7u45-b18/jdk-7u45-linux-x64.tar.gz`

### Unzip archive 

    tar -xzvf jdk-7u45-linux-x64.tar.gz -O
	mv jdk1.7.0_45 java-7u45.jdk-custom1

### Generate directory debina in root of package

    cd java-7u45.jdk-custom1
	dh_make -e kobrin.artem@gmail.com -n -s -c gpl2

### Replace files

    git clone https://github.com/puppetnix/jdk1.7.git
	mv jdk1.7/* java-7u45.jdk-custom1/`

### Build package

    dpkg-buildpackage -rfakeroot
