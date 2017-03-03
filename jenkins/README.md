# Docker container for Jenkins

# jenkins

## Usage

Before you create your container, you must decide on the type of networking you wish to use.  There are essentially three types of networking available:

- `bridge` (default)
- `host`
- `macvlan`

The `bridge` networking creates an entirely new network within the host and runs containers within there.  This network is connected to the physical network via an internal router and docker configures this router to forward certain ports through to the containers within.  The `host` networking uses the IP address of the host running docker such that a container's networking appears to be the host rather than separate.  The `macvlan` networking creates a new virtual computer on the network which is the container.

Using `host` or `macvlan` is the easier of the three setups and has the fewest issues that need to be worked around.  However, some setups may be restricted to only running in the `bridge` mode.