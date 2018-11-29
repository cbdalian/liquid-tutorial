# liquid-tutorial


clone 
------------------
git clone 

start services

pegin from bitcoin into liquid
=================================

    # liquid-cli getnewaddress
    CTEr64MwkHNni2LzsDe2W5sVet25rBqVWSSjYF1kCA4cW6HtxigdkMxKegKWRFt9wA7uuMRpJouFrmxE

    # liquid-cli validateaddress CTEr64MwkHNni2LzsDe2W5sVet25rBqVWSSjYF1kCA4cW6HtxigdkMxKegKWRFt9wA7uuMRpJouFrmxE
    {
      "isvalid": true,
      "address": "CTEr64MwkHNni2LzsDe2W5sVet25rBqVWSSjYF1kCA4cW6HtxigdkMxKegKWRFt9wA7uuMRpJouFrmxE",
      "scriptPubKey": "76a9144b16c9cb7609f0cb468173f5e448109edfe0d11988ac",
      "confidential_key": "02ec7347be7c2b779e5b14cb9b8a3e3aa929fbd343c31ce7f21510544fd949aff5",
      "unconfidential": "2dgGnNGAWNbxvtkFEieF4kXcWLGGa9F4FqZ",
      "ismine": true,
      "iswatchonly": false,
      "isscript": false,
      "pubkey": "0208bcf93c48d7d590257e94cbbf6c85c565c7e98f8126e7418e71f53f0de3a97d",
      "iscompressed": true,
      "account": "",
      "timestamp": 1543465929,
      "hdkeypath": "m/0'/0'/1'",
      "hdmasterkeyid": "c6a41fb8f639697d3d84fe45e83f3495a4b2ee0b"
    }
    
    # liquid-cli dumpprivkey CTEr64MwkHNni2LzsDe2W5sVet25rBqVWSSjYF1kCA4cW6HtxigdkMxKegKWRFt9wA7uuMRpJouFrmxE
    cQ5qbxT4sDkpfWAKCbnf3grrVpnHv6nKBUPSudi6X7aaTvTBQ78H
    
    # liquid-cli createmultisig 1 \[\"0208bcf93c48d7d590257e94cbbf6c85c565c7e98f8126e7418e71f53f0de3a97d\"\]
    {
      "address": "XNfjdteaKBeGGDzreW4xuQFYnRbFita4s8",
      "redeemScript": "51210208bcf93c48d7d590257e94cbbf6c85c565c7e98f8126e7418e71f53f0de3a97d51ae"
    }
