# Asciio ditaa stencil

- ditaa stencil
- <s>auto-generate .txt .png files</s>

## Ubuntu

    sudo apt install asciio    
    sudo apt install ditaa
    sudo cp ~/Downloads/asciio-ditaa-master/App/Asciio/setup/stencils/ditaa /usr/share/perl5/App/Asciio/setup/stencils/
    sudo cp ~/Downloads/asciio-ditaa-master/App/Asciio/setup/stencils/ditaatags /usr/share/perl5/App/Asciio/setup/stencils/
    sudo cp /usr/share/perl5/App/Asciio/setup/setup.ini /usr/share/perl5/App/Asciio/setup/setup.ini.orig
    sudo vi /usr/share/perl5/App/Asciio/setup/setup.ini
    diff /usr/share/perl5/App/Asciio/setup/setup.ini.orig /usr/share/perl5/App/Asciio/setup/setup.ini
    7a8,9
    > 	'stencils/ditaa',
    > 	'stencils/ditaatags',

## OS X, X11 Installation log

### asciio

    $ cpan App::cpanminus
        Would you like to configure as much as possible automatically? [yes]
        yes
    
        What approach do you want?  (Choose 'local::lib', 'sudo' or 'manual') [local::lib]
        sudo
    
        Would you like me to automatically choose some CPAN mirror
        sites for you? (This means connecting to the Internet) [yes]
        yes

    $ sudo ln -s /opt/local/libexec/perl5.16/sitebin/cpanm /usr/local/bin/cpanm
    $ sudo cpanm App::Asciio
    $ sudo ln -s /opt/local/libexec/perl5.16/sitebin/asciio /usr/local/bin/asciio
    
    $ asciio

### ditaa

    $ sudo port install ditaa
        /opt/local/share/java/ditaa0_9.jar

### Add ditaa stencil

    $ sudo mv /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/actions/file.pl /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/actions/file.pl.orig
    $ sudo vi ./App/Asciio/setup/actions/file.pl
        edit ditaa0_9.jar path
    $ sudo cp ./App/Asciio/setup/actions/file.pl /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/actions/
    $ sudo cp ./App/Asciio/setup/stencils/ditaa /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/stencils/
    $ sudo cp ./App/Asciio/setup/stencils/ditaatags /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/stencils/
    
    $ sudo cp /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/setup.ini /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/setup.ini.orig
    $ sudo vi /opt/local/lib/perl5/site_perl/5.16.3/App/Asciio/setup/setup.ini
        'stencils/ditaa',
    	'stencils/ditaatags',

## See also

- http://search.cpan.org/dist/App-Asciio/lib/App/Asciio.pm
- https://metacpan.org/pod/App::Asciio
- http://ditaa.sourceforge.net
- http://cornempire.net/2010/05/19/art-with-ascii-asciio-and-ditaa/
- http://wiki.cornempire.net/asciiart/start
- http://strawp.net/archive/geeking-out-with-diagrams-in-ascii/
