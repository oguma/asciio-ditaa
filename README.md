# Asciio ditaa stencil

- ditaa stencil
- auto-generate .txt .png files

## Installation log

OS X, X11

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
