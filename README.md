# ceph-mgr-nagios-plugins
Set of nagios plugins for monitoring CEPH cluster via MGR daemon.
Inspiration comes from [ceph-nagios-plugins](https://github.com/ceph/ceph-nagios-plugins).

## Setup
You need to enable restful mgr module and create key for monitoring user.
For more information see http://docs.ceph.com/docs/master/mgr/restful/.

    # ceph mgr module enable restful
    # ceph restful create-key nagios

## check_ceph_mon
If no monitor id (-I) is specified, all monitors are checked by default.
Default user (-u) is nagios.

    usage: check_ceph_mon [-h] [-a ADDRESS] [-p PORT] [-V] [-I MONID] [-u USER]
                          [-w PASSWORD] [-r URLPREFIX]

Example:

    # ./check_ceph_mon -a mgr1 -u nagios -w <nagios-key> -I mon1

## check_ceph_osd
If no osd id (-I) is specified, all osds are checked by default.
Default user (-u) is nagios.

    usage: check_ceph_osd [-h] [-a ADDRESS] [-p PORT] [-V] [-I OSDID] [-u USER]
                          [-w PASSWORD] [-r URLPREFIX]

Example:

    # ./check_ceph_osd -a mgr1 -w <nagios-key>
    
