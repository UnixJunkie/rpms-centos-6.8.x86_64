# ocaml-rpms-centos-6.8.x86_64
Some RPMs for OCaml survival under centos-6.8.x86_64

# how the opam rpm was created

    cd ~/src/opam
    ./configure --prefix=/usr
    make
    mkdir /tmp/installdir
    make install DESTDIR=/tmp/installdir
    gem install --user-install fpm
    fpm -s dir -t rpm -n opam-1.2.2 -C /tmp/installdir
