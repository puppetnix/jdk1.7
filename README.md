Oracle java jdk7 debian package

BUILD DEB PACKAGE
1. Download jdk archive 

  wget --continue --no-check-certificate -O jdk-7u45-linux-x64.tar.gz --header "Cookie: gpw_e24=h" http://download.oracle.com/otn-pub/java/jdk/7u45-b18/jdk-7u45-linux-x64.tar.gz

2. Unzip archive 

  tar -xzvf jdk-7u45-linux-x64.tar.gz -O 
  mv jdk1.7.0_45 java-7u45.jdk-custom1

3. Generate directory debina in root of package

  cd java-7u45.jdk-custom1 
  dh_make -e email@domain.com -n -s -c gpl2

4. replace files

  git clone https://github.com/puppetnix/jdk1.7.git
  mv jdk1.7/* java-7u45.jdk-custom1/
