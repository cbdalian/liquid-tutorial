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
