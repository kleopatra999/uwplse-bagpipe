The directions below assume you have the input Juniper configurations in a directory named "configs/"

- Project only the BGP relevant parts of the Juniper configurations with:

    $ bagpipe project configs/*

- Infer the topology:

    $ bagpipe infer topology configs/* > out.dot

  and plot it using dot (requires graphviz to be installed) with:

    $ circo -Tpdf out.dot > out.pdf

- Infer contracts with:

    $ bagpipe infer contracts configs/*

- Inject new commands into the existing configurations with:

    $ bagpipe inject add configs/foo.conf  "protocols bgp neighbor a.b.c.d {}" "protocols bgp neighbor a.b.c.d local-preference 400 ;"

