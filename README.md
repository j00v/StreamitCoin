StreamitCoin Core (fork of PIVX) integration/staging repository
======================================


It is recommended [use the shell script](https://github.com/StreamitCoin/stream-install) to install a StreamitCoin Masternode on a Linux server running Ubuntu 14.04, 16.04, 18.04

***

Quick installation of the StreamitCoin daemon under linux. See detailed instructions there [build-unix.md](build-unix.md)

Installation of libraries (using root user):

    add-apt-repository ppa:bitcoin/bitcoin -y
    apt-get update
    apt-get install -y build-essential libtool autotools-dev automake pkg-config libevent-dev bsdmainutils libgmp-dev
    apt-get install -y libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    apt-get install -y libdb4.8-dev libdb4.8++-dev

    For Ubuntu 18.04 type:
    apt-get install -y libssl1.0-dev

    For Ubuntu 16.04 type:
    apt-get install -y libssl-dev

Cloning the repository and compiling (use any user with the sudo group):

    cd
    git clone https://github.com/StreamitCoin/StreamitCoin.git
    cd StreamitCoin
    ./autogen.sh
    ./configure
    sudo make install
    cd src
    sudo strip streamitcoind
    sudo strip streamitcoin-cli
    sudo strip streamitcoin-tx
    cd ..

Running the daemon:

    streamitcoind &

Stopping the daemon:

    streamitcoin-cli stop

Demon status:

    streamitcoin-cli getinfo
    streamitcoin-cli mnsync status

All binaries for different operating systems, you can download in the releases repository:

https://github.com/StreamitCoin/StreamitCoin/releases

P2P port: 63636, RPC port: 63637
-
Distributed under the MIT software license, see the accompanying file COPYING or http://www.opensource.org/licenses/mit-license.php.
