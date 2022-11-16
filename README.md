# haproxy-issue-1914
Test runs &amp; logs for https://github.com/haproxy/haproxy/issues/1914

mb errors matched by running:

    $ grep error mb.log | awk '{print $9}' | while IFS=":" read host port; do echo; needle="::ffff:192.168.7.64:$port"; echo "Matching $needle"; rg "^${needle} \[" haproxy.log; done > errors.log
