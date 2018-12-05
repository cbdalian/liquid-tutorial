# pegin into elements 

  # create the config files
  
  cat bitcoin.conf
  
    #テスト環境か?(testnet=3 or regtest=1)
    regtest=1

    #外部からのRPCを受け付けるか(1=受け付ける)
    server=1
    #外部からのRPCを受け付けるIPの範囲
    rpcallowip=0.0.0.0/0

    #RPCの接続設定
    rpcbind=0.0.0.0
    rpcuser=username
    rpcpassword=password
    rpcport=8340

    # すべてのトランザクションをインデックス化する場合はtxindex=1
    # それ以外の場合は自分のウォレットに関連するトランザクションのみインデックス化する。
    # インデックス化している場合のみgetrawtransactionなどでトランザクションの情報を取得できる。
    txindex=1

    #デーモンでの起動
    daemon=1

    # 接続ノード
    #addnode=

  cat elements.conf
    
    rpcuser=username
    rpcpassword=password
    rpcport=8339
    daemon=1
    discover=0
    testnet=0
    regtest=1
    mainchainhost=127.0.0.1
    mainchainrpcport=8340
    mainchainrpcuser=username
    mainchainrpcpassword=password
    validatepegin=1
    txindex=1
  
  # start services
  
    bitcoind
    elementsd
    
  # create key for federation script on pegin
  
    $ elements-cli getnewaddress
    CTEkpNvfKWD6XsboFC3q9Wzx6UzC3MA7697YfokBmXFgTfk9i6nULhQC9UeV6E2ujV4JBQ7hkK91CHGE
    
    $ elements-cli validateaddress CTEkpNvfKWD6XsboFC3q9Wzx6UzC3MA7697YfokBmXFgTfk9i6nULhQC9UeV6E2ujV4JBQ7hkK91CHGE
    {
      "isvalid": true,
      "address": "CTEkpNvfKWD6XsboFC3q9Wzx6UzC3MA7697YfokBmXFgTfk9i6nULhQC9UeV6E2ujV4JBQ7hkK91CHGE",
      "scriptPubKey": "76a91497f257c97abc2473b70c2aec5721e7dbf7fd1eab88ac",
      "confidential_key": "0229d6c0e4eb68108fc20b5f26cc88285f4049cd8d8fe883b16ae8e4ab1e52c18a",
      "unconfidential": "2doHAjmQRDUfDyhHyryAAzwdgX3WNgSHdy6",
      "ismine": true,
      "iswatchonly": false,
      "isscript": false,
      "pubkey": "035760e39484d925efbf385d08c00745083e0502522cb3307fec436c82b255d5ca",
      "iscompressed": true,
      "account": "",
      "timestamp": 1543974339,
      "hdkeypath": "m/0'/0'/1'",
      "hdmasterkeyid": "841a41ec9952d8f0be33aae25f8642c163dcf0ea"
    }

    $ elements-cli dumpprivkey CTEkpNvfKWD6XsboFC3q9Wzx6UzC3MA7697YfokBmXFgTfk9i6nULhQC9UeV6E2ujV4JBQ7hkK91CHGE
    cNaE78vQ3S6Fex74shyEjSPX6AJDMcDoQZDwjyiJXkdAfL2KoEmG
    
    $ elements-cli createmultisig 1 \[\"035760e39484d925efbf385d08c00745083e0502522cb3307fec436c82b255d5ca\"\]
    {
      "address": "XHUY3JBUFqXehUdeWK9BqpKEd82GZWQevU",
      "redeemScript": "5121035760e39484d925efbf385d08c00745083e0502522cb3307fec436c82b255d5ca51ae"
    }

    $ elements-cli stop
    Elements server stopping
    
    $ pwd
    /Users/cao/Library/Application Support/Bitcoin

    $ rm -rf elementsregtest

    $ elementsd -signblockscript=5121035760e39484d925efbf385d08c00745083e0502522cb3307fec436c82b255d5ca51ae -fedpegscript=5121035760e39484d925efbf385d08c00745083e0502522cb3307fec436c82b255d5ca51ae
    Elements server starting
    
    $ elements-cli importprivkey cNaE78vQ3S6Fex74shyEjSPX6AJDMcDoQZDwjyiJXkdAfL2KoEmG
    
    

    elementsd 
    elementsd
