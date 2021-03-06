# MEMmultilepton
Matrix Element Method for multilepton final states in High Energy Physics

Author: Nicolas Chanon (IPNL) with the help of Jing Li (PKU) and Nicolas Tonon (IPHC)

#INSTALLATION

git clone https://github.com/nchanon/MEMmultilepton

#Install and configure LHAPDF (here, on lxplus6). See http://lhapdf.hepforge.org/install.html

wget http://www.hepforge.org/archive/lhapdf/LHAPDF-6.2.1.tar.gz -O- | tar xz

cd LHAPDF-6.2.1

./configure --prefix=$PWD/../LHAPDF-6.2.1-install \ 

--with-boost=/afs/cern.ch/sw/lcg/external/Boost/1.55.0_python2.7/x86_64-slc6-gcc47-opt

make -j2

make install

#Source LHAPDF environmental variables:

setenv LHAPDF $PWD/../LHAPDF-6.2.1-install

setenv LHAPATH $LHAPDF/share/LHAPDF/

setenv LHAPDF_BIN $LHAPDF/bin

setenv PATH ${PATH}:${LHAPDF_BIN}

setenv LD_LIBRARY_PATH ${LD_LIBRARY_PATH}:$LHAPDF/lib

#Get the NNPDF3.0 LO pdf set at leading order:

cd $PWD/../LHAPDF-6.2.1-install

cd share/LHAPDF

wget http://www.hepforge.org/archive/lhapdf/pdfsets/6.2/NNPDF30_lo_as_0118.tar.gz -O- | tar xz

cd ../../../

#Setup ROOT (most importantly, it has to be installed with GSL and Minuit2 dependences)

source /afs/cern.ch/sw/lcg/external/gcc/4.9/x86_64-slc6-gcc49-opt/setup.csh

source /afs/cern.ch/sw/lcg/app/releases/ROOT/6.06.06/x86_64-slc6-gcc49-opt/root/bin/thisroot.csh

#Configure MEMmultilepton (mostly compilations)

cd MEMmultilepton

./installMEM.sh

#Test MEMmultilepton from an example

cd Examples

./simpleMEManalyzer config.cfg

#Please use config/config.cfg instead of Example/config.cfg if your interface the MEM with your own code (contains absolute path to the transfer functions and Madgraph directory)
