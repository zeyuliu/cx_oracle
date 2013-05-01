If installing on Fedora-based OS, download the rpms from the fedora directory

Install Oracle's instant client:
  
    $ rpm -ivh oracle-instantclient11.2-basic-11.2.0.3.0-1.x86_64.rpm
  
    $ rpm -ivh oracle-instantclient11.2-sqlplus-11.2.0.3.0-1.x86_64.rpm
  
    $ rpm -ivh oracle-instantclient11.2-devel-11.2.0.3.0-1.x86_64.rpm

Move the oracle.conf file into /etc/ld.so.conf.d/

    $ mv oracle.conf /etc/ld.so.conf.d/oracle.conf

Enable the shared library path system wide with ldconfig:
    
    $ ldconfig
    

You can use the source code for cx_Oracle 5.1.2 or you can download the source from http://cx-oracle.sourceforge.net/.

Extract the source

    $ tar xvfz cx_Oracle.<fileversion>.tar.gz

Move into working directory

    cd cx_Oracle.<fileversion>

Setup Path, compile, and install

    $ ORACLE_HOME=/usr/lib/oracle/11.2/client64/ python3 setup.py build #(oracle version and python version will depend on your working version)

    $ ORACLE_HOME=/usr/lib/oracle/11.2/client64/ python3 setup.py install

To use cx_Oracle, simply import it inside Python:

    $ python3
    >>> import cx_Oracle
