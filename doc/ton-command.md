# ton 命令

- [ton 命令](#ton-命令)
  - [adnl-pong](#adnl-pong)
  - [adnl-proxy](#adnl-proxy)
  - [blockchain-explorer](#blockchain-explorer)
  - [create-hardfork](#create-hardfork)
  - [adjust-block](#adjust-block)
  - [create-state](#create-state)
  - [dump-block](#dump-block)
  - [fift](#fift)
  - [func](#func)
  - [pow-miner](#pow-miner)
  - [tlbc](#tlbc)
  - [dht-server](#dht-server)
  - [http-proxy](#http-proxy)
  - [lite-client](#lite-client)
  - [rldp-http-proxy](#rldp-http-proxy)
  - [storage-cli](#storage-cli)
  - [io-bench](#io-bench)
  - [tcp_ping_pong](#tcp_ping_pong)
  - [udp_ping_pong](#udp_ping_pong)
  - [generate_common](#generate_common)
  - [tonlib_generate_java_api](#tonlib_generate_java_api)
  - [tonlib-cli](#tonlib-cli)
  - [benchmark-fec](#benchmark-fec)
  - [generate-random-id](#generate-random-id)
  - [json2tlo](#json2tlo)
  - [pack-viewer](#pack-viewer)
  - [validator-engine](#validator-engine)
  - [validator-engine-console](#validator-engine-console)
## adnl-pong
```
adnl pinger. Options:
  -v, --verbosity<arg> set verbosity level
  -V, --version        shows adnl-pong build information
  -h, --help           prints_help
  -d, --daemonize      set SIGHUP
  -l, --logname<arg>   log to file
  -t, --threads<arg>   number of threads (default=7)
  -u, --user<arg>      change user
  -k, --key<arg>       private key
  -a, --addr<arg>      ip:port of instance
```

## adnl-proxy
```
validator or full node for TON network. Options:
  -v, --verbosity<arg> set verbosity level
  -V, --version        shows adnl-proxy build information
  -h, --help           prints_help
  -c, --config<arg>    config file
  -d, --daemonize      set SIGHUP
  -l, --logname<arg>   log to file
  -t, --threads<arg>   number of threads (default=7)
  -u, --user<arg>      change user
```

## blockchain-explorer
```
  TON Blockchain explorer. Options:
  -h, --help               prints_help
  -I, --hide-ips           hides ips from status
  -u, --user<arg>          change user
  -C, --global-config<arg> file to read global config
  -a, --addr<arg>          connect to ip:port
  -p, --pub<arg>           remote public key
  -v, --verbosity<arg>     set verbosity level
  -d, --daemonize          set SIGHUP
  -H, --http-port<arg>     listen on http port
  -L, --local-scripts      use local copy of ajax/bootstrap/... JS
  -l, --logname<arg>       log to file
```

## create-hardfork
```
test collate block. Options:
  -h, --help                   prints_help
  -V, --version                shows create-hardfork build information
  -D, --db<arg>                root for dbs
  -C, --config<arg>            global config path
  -m, --ext-message<arg>       binary file with serialized inbound external message
  -M, --top-shard-message<arg> binary file with serialized shard top block description
  -v, --verbosity<arg>         set verbosity level
  -w, --workchain<arg>         <workchain>[:<shard>]	collate block in this workchain
  -T, --top-block<arg>         BlockIdExt of top block (new block will be generated atop of it)
  -d, --daemonize              set SIGHUP
```
## adjust-block
```
usage: adjust-block [-i<vs-incr>] <in-boc-file> <out-boc-file>
	or adjust-block -h
	Adjusts block loaded from <in-boc-file> by incrementing vert_seqno by <vs-incr> (1 by default)
```
## create-state
```
Creates initial state for a TON blockchain, using configuration defined by Fift-language source files
usage: create-state [-i] [-n] [-I <source-include-path>] {-L <library-fif-file>} <source-file1-fif> <source-file2-fif> ...
	-n	Do not preload preamble files `Fift.fif` and `CreateState.fif`
	-i	Force interactive mode even if explicit source file names are indicated
	-I<source-search-path>	Sets colon-separated library source include path. If not indicated, $FIFTPATH is used instead.
	-L<library-fif-file>	Pre-loads a library source file
	-v<verbosity-level>	Set verbosity level
	-V<version>	Show create-state build information
```
## dump-block
```
usage: dump-block [-t<typename>][-S][<boc-file>]
	or dump-block -h
	Dumps specified blockchain block or state from <boc-file>, or runs some tests
	-S	Dump a blockchain state instead of a block
	-V<version>	Show fift build information
```
## fift
```
usage: fift [-i] [-n] [-I <source-include-path>] {-L <library-fif-file>} <source-file1-fif> <source-file2-fif> ...
	-n	Do not preload standard preamble file `Fift.fif`
	-i	Force interactive mode even if explicit source file names are indicated
	-I<source-search-path>	Sets colon-separated library source include path. If not indicated, $FIFTPATH is used instead.
	-L<library-fif-file>	Pre-loads a library source file
	-d<ton-db-path>	Use a ton database
	-s	Script mode: use first argument as a fift source file and import remaining arguments as $n)
	-v<verbosity-level>	Set verbosity level
	-V<version>	Show fift build information
```
## func
```
usage: func [-vIAPSR][-O<level>][-i<indent-spc>][-o<output-filename>][-W<boc-filename>] {<func-source-filename> ...}
	Generates Fift TVM assembler code from a funC source
-I	Enables interactive mode (parse stdin)
-o<fift-output-filename>	Writes generated code into specified file instead of stdout
-v	Increases verbosity level (extra information output into stderr)
-i<indent>	Sets indentation for the output code (in two-space units)
-A	Prefix code with `"Asm.fif" include` preamble
-O<level>	Sets optimization level (2 by default)
-P	Envelope code into PROGRAM{ ... }END>c
-S	Include stack layout comments in the output code
-R	Include operation rewrite comments in the output code
-W<output-boc-file>	Include Fift code to serialize and save generated code into specified BoC file. Enables -A and -P.
	-s	Output semantic version of FunC and exit
	-V<version>	Show func build information
```
##  pow-miner
```
pow-miner: option requires an argument -- h
unknown option
usage: pow-miner [-v][-B][-w<threads>] [-t<timeout>] <my-address> <pow-seed> <pow-complexity> <iterations> [<miner-addr> <output-ext-msg-boc>] [-V]
Outputs a valid <rdata> value for proof-of-work testgiver after computing at most <iterations> hashes or terminates with non-zero exit code
``` 
## tlbc
```
tlbc: illegal option -- e
usage: tlbc [-v][-i][-h][-c][-z][-t][-T][-q][-n<namespace>][-o<output-filename>] {<tlb-filename> ...}
-v	Increase verbosity level
-t	Show tag mismatch warnings
-q	Omit code generation (TLB scheme check only)
-h	Generate C++ header file only (usually .h or .hpp)
-c	Generate C++ source file only (usually .cpp)
-T	Add type pointer members into generated C++ data record classes
-z	Append .cpp or .hpp to output filename
-n<namespace>	Put generated code into specified namespace (default `tlb`)
```
## dht-server
```
dht server for TON DHT network. Options:
  -v, --verbosity<arg>     set verbosity level
  -V, --version            shows dht-server build information
  -h, --help               prints_help
  -C, --global-config<arg> file to read global config
  -c, --local-config<arg>  file to read local config
  -I, --ip<arg>            ip:port of instance
  -D, --db<arg>            root for dbs
  -d, --daemonize          set SIGHUP
  -l, --logname<arg>       log to file
  -t, --threads<arg>       number of threads (default=7)
  -u, --user<arg>          change user
```
## http-proxy
```
simple http proxy. Options:
  -v, --verbosity<arg> set verbosity level
  -V, --version        shows http-proxy build version
  -h, --help           prints_help
  -p, --port<arg>      sets listening port
  -d, --daemonize      set SIGHUP
  -l, --logname<arg>   log to file
```
## lite-client
```
Test Lite Client for TON Blockchain. Options:
  -h, --help               prints_help
  -C, --global-config<arg> file to read global config
  -r, --disable-readline
  -R, --enable-readline
  -D, --db<arg>            root for dbs
  -L, --print-limit<arg>   sets maximum count of recursively printed objects
  -v, --verbosity<arg>     set verbosity level
  -V, --version            shows lite-client build information
  -i, --idx<arg>           set liteserver idx
  -a, --addr<arg>          connect to ip:port
  -c, --cmd<arg>           schedule command
  -t, --timeout<arg>       timeout in batch mode
  -p, --pub<arg>           remote public key
  -b, --b64<arg>           remote public key as base64
  -d, --daemonize          set SIGHUP
  -l, --logname<arg>       log to file
```
## rldp-http-proxy
```
A simple rldp-to-http and http-to-rldp proxy for running and accessing ton sites
Example:
	rldp-http-proxy -p 8080 -c 3333 -C ton-global.config.json	Runs a local HTTP->RLDP proxy that accepts HTTP proxy queries at localhost:8080
Example:
	rldp-http-proxy -a <global-ip>:3333 -L example.ton -C ton-global.config.json	Runs a local RLDP->HTTP proxy on UDP port <global-ip>:3333 that forwards all queries for http://example.ton to HTTP server at localhost:80
. Options:
  -v, --verbosity<arg>     set verbosity level
  -V, --version            shows rldp-http-proxy build information
  -h, --help               prints a help message
  -p, --port<arg>          sets http listening port
  -a, --address<arg>       local <ip>:<port> to use for adnl queries
  -A, --adnl<arg>          server ADNL addr
  -c, --client-port<arg>   local <port> to use for client adnl queries
  -C, --global-config<arg> global TON configuration file
  -L, --local<arg>         http hostname that will be proxied to http server at localhost:80
  -D, --db<arg>            db root
  -R, --remote<arg>        <hostname>@<ip>:<port>, indicates a http hostname that will be proxied to remote http server at <ip>:<port>
  -d, --daemonize          set SIGHUP
  -l, --logname<arg>       log to file
  -P, --proxy-all<arg>     value=[YES|NO]. proxy all HTTP requests (default only *.ton and *.adnl)
```
## storage-cli
```
experimental cli for ton storage. Options:
  -h, --help           prints_help
  -v, --verbosity<arg> set verbosity level
  -V, --version        shows storage-cli build information
  -C, --config<arg>    set ton config
  -D, --db<arg>        root for dbs
  -I, --ip<arg>        set ip:port
  -E, --execute<arg>   execute one command
  -d, --dir<arg>       working directory
```
## io-bench
```
[ 1][t 0][2022-05-28 10:13:55.101412][io-bench.cpp:640]	[Error : 0 : Option h was unrecognized]
Options:
  -f, --from<arg>   read from file
  -m, --mode<arg>   mode
  -b, --buffer<arg> buffer size
```
## tcp_ping_pong
```
[ 1][t 0][2022-05-28 10:14:05.189420][tcp_ping_pong.cpp:118]	[Error : 0 : Option h was unrecognized]
[ 3][t 0][2022-05-28 10:14:05.189455][tcp_ping_pong.cpp:119]	Tcp ping server/client (based on td::actors2). Options:
  -p, --port<arg> listen/connect to tcp port (8081 by default)
  -c, --client    Work as client (server by default)
```
## udp_ping_pong
```
[ 1][t 0][2022-05-28 10:14:15.705771][udp_ping_pong.cpp:127]	[Error : 0 : Option h was unrecognized]
[ 3][t 0][2022-05-28 10:14:15.705795][udp_ping_pong.cpp:128]	Udp ping server/client (8083 <-> 8084) (based on td::actors2). Options:
  -c, --client Work as client (server by default)
  -t, --tcp    Use tcp (udp by default)
```
## generate_common
```
Config file scheme/ton_api.tlo is empty
[1]    72712 abort      generate_common -h
```
## tonlib_generate_java_api
```

```
## tonlib-cli
```
cli wrapper around tonlib. Options:
  -h, --help                      prints_help
  -r, --disable-readline          disable readline
  -R, --enable-readline           enable readline
  -D, --directory<arg>            set keys directory
  -M, --in-memory                 store keys only in-memory
  -E, --execute<arg>              execute one command
  -v, --verbosity<arg>            set verbosity level
  -V, --version                   show tonlib-cli build information
  -C, --config-force<arg>         set lite server config, drop config related blockchain cache
  -c, --config<arg>               set lite server config
  -N, --config-name<arg>          set lite server config name
  -n, --use-callbacks-for-network do not use this
  -w, --wallet-id<arg>            do not use this
  -x, --workchain<arg>            default workchain
  -W, --wallet-version<arg>       do not use this (version[.revision])
```
## benchmark-fec
```

```
## generate-random-id
```
generate random id. Options:
  -m, --mode<arg>      sets mode (one of id/adnl/dht/keys/adnlid)
  -h, --help           prints this help
  -V, --version        shows generate-random-id build information
  -n, --name<arg>      path to save private keys to
  -k, --key<arg>       path to private key to import
  -a, --addr-list<arg> addr list to sign
```
## json2tlo
```
json2tlo. Options:
  -i, --in<arg>  input
  -o, --out<arg> output
  -r, --reverse  read tlo, print json
  -V, --version  shows json2tlo build information
  -h, --help     prints_help
```
## pack-viewer
```

```
## validator-engine
```
validator or full node for TON network. Options:
  -v, --verbosity<arg>               set verbosity level
  -V, --version                      shows validator-engine build information
  -h, --help                         prints_help
  -C, --global-config<arg>           file to read global config
  -c, --local-config<arg>            file to read local config
  -I, --ip<arg>                      ip:port of instance
  -D, --db<arg>                      root for dbs
  -f, --fift-dir<arg>                directory with fift scripts
  -d, --daemonize                    set SIGHUP
  -l, --logname<arg>                 log to file
  -s, --state-ttl<arg>               state will be gc'd after this time (in seconds) default=3600
  -m, --mempool-num<arg>             Maximal number of mempool external message
  -b, --block-ttl<arg>               blocks will be gc'd after this time (in seconds) default=7*86400
  -A, --archive-ttl<arg>             archived blocks will be deleted after this time (in seconds) default=365*86400
  -K, --key-proof-ttl<arg>           key blocks will be deleted after this time (in seconds) default=365*86400*10
  -S, --sync-before<arg>             in initial sync download all blocks for last given seconds default=3600
  -T, --truncate-db<arg>             truncate db (with specified seqno as new top masterchain block seqno)
  -U, --unsafe-catchain-restore<arg> use SLOW and DANGEROUS catchain recover method
  -F, --unsafe-catchain-rotate<arg>  use forceful and DANGEROUS catchain rotation
  -t, --threads<arg>                 number of threads (default=7)
  -u, --user<arg>                    change user
```
## validator-engine-console
```
console for validator for TON Blockchain. Options:
  -h, --help             prints_help
  -V, --version          shows validator-engine-console build information
  -a, --address<arg>     server address
  -k, --key<arg>         private key
  -p, --pub<arg>         server public key
  -r, --disable-readline disable readline
  -R, --enable-readline  enable readline
  -v, --verbosity<arg>   set verbosity level
  -c, --cmd<arg>         schedule command
  -t, --timeout<arg>     timeout in batch mode
```
