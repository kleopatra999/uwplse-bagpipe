Build and install bagpipe:

	$ make

Below use example Juniper configurations from
[Internet2](https://noc.net.internet2.edu/i2network/index.html) which are
in the `i2/` directory of this repo.

Project BGP relevant parts of a set of Juniper configurations:

    $ bagpipe project i2/*.conf

Generate visualization of network topology from a set of Juniper configurations:

    $ bagpipe infer topology i2/*.conf > topo.dot

    $ circo -Tpdf topo.dot > topo.pdf

    $ evince topo.pdf

Infer high level contracts:

    $ bagpipe infer contracts i2/*.conf

Inject new commands into existing configurations:

    $ bagpipe inject add i2/seat.conf \
        "protocols bgp neighbor a.b.c.d {}" \
        "protocols bgp neighbor a.b.c.d local-preference 400 ;"
