# elements node1 node2 
<https://github.com/ElementsProject/elements/blob/elements-0.14.1/contrib/assets_tutorial/assets_tutorial.sh>

# memo

    $e1-cli getwalletinfo
    {
      "walletversion": 130000,
      "balance": {
        "bitcoin": 21000000.00000000
      },
      "unconfirmed_balance": {
      },
      "immature_balance": {
      },
      "txcount": 1,
      "keypoololdest": 1544060102,
      "keypoolsize": 100,
      "paytxfee": 0.00000000,
      "hdmasterkeyid": "7f5cd8baa7cafcd6a1b8559591288c7c4b9ffaa8"
    }
    $e2-cli getwalletinfo
    {
      "walletversion": 130000,
      "balance": {
      },
      "unconfirmed_balance": {
      },
      "immature_balance": {
      },
      "txcount": 0,
      "keypoololdest": 1544060119,
      "keypoolsize": 100,
      "paytxfee": 0.00000000,
      "hdmasterkeyid": "1ac10d44c85fcbeb0f503d9e62d448c3f29fd6b1"
    }
    
    # First, drain OP_TRUE and split funds evenly between e1 and e2
    $e1-cli listunspent
    [
      {
        "txid": "027f015923d266ffb8af1fadd09a3743dffebd199e8f1e45c96ca12e58992d5f",
        "vout": 0,
        "scriptPubKey": "51",
        "amount": 21000000.00000000,
        "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
        "assetlabel": "bitcoin",
        "confirmations": 1,
        "spendable": true,
        "solvable": true,
        "blinder": "0000000000000000000000000000000000000000000000000000000000000000",
        "assetblinder": "0000000000000000000000000000000000000000000000000000000000000000"
      }
    ]
    $e1-cli sendtoaddress $(e1-cli getnewaddress) 21000000 "" "" true
    3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae
    $e1-cli listunspent
    [
    ]
    $e1-cli listunspent 0 0
    [
      {
        "txid": "3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae",
        "vout": 0,
        "address": "2dnkzCcTTKn57XGVfUtk7H6MH8WWgRCAnAz",
        "account": "",
        "scriptPubKey": "76a914923d116f0cc845e6b485083753eddb77642819b188ac",
        "amount": 20999999.99996700,
        "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
        "assetlabel": "bitcoin",
        "confirmations": 0,
        "spendable": true,
        "solvable": true,
        "blinder": "0000000000000000000000000000000000000000000000000000000000000000",
        "assetblinder": "0000000000000000000000000000000000000000000000000000000000000000"
      }
    ]

    $e1-cli generate 101
    [
      "883bcbfd4f6c94822ffedd1fd23c7e704fbc1a1d1ca5073c880395a1ea8ccf92", 
      "45d184cd2c70ed94607334894f95d169ecfb19faecbb3a900bbe088a4dfaa630", 
      "bdd5170345a05a623058bcc9589b9d9244cbb55bac0bec2cef730410b1d472a2", 
      "94555d5a1c740729f77122eba209dccb7962d28a4cd038449207993aa45cf5c0", 
      "77aa39deb5bf58b42159c38deda5362c026c3d58219f1fbca60acc7411cd9be9", 
      "d2cfc6dd448cbbfa19d770e82eba1edd3922f9e33f6367b46872735f2cddb8a9", 
      "f13ddf90f2b36fcbd4465e0d9f050e1213f29afa61014c92417f31decc47c18f", 
      "5921f423ea4835c6ea36280f54f7b93a68837ab3007a96559078ba90f894a294", 
      "905ce7dc34316f2a8114215912b386971b8f79ca6e53047fd3d8d2161caabaeb", 
      "85e7cb6b50d84a6702488807f4a2f9ed24444f38fc47c2f467f61eb68c503a89", 
      "1805629ed5a90806fe4b5838a68bace17d647493c38dbd6819eee383e1731384", 
      "df1ab8f251b15ae7f0e3dfad62dd179f35abba0c06d8567bfc00c65e97f7d57a", 
      "9d4a567e5f9f0762bbb4a43555745e8b47ee099c778999eb61e88b5c978a6f7a", 
      "7e738dddc087c761e12c231de0aaa2ab94646957dfa23d870e884b627b80e96e", 
      "34e38872374f72b52889d054437605e7f4f73c5745a23efe9ffcb2d024dcd79a", 
      "88fc9a334d3b1342976c6461490f1d4a728c4c176e4d04612a1fdf48907446ed", 
      "2a80dc6ad2c58b73e75a60776e9f96e9f9e771ad66912fdd04e648e7cd95c571", 
      "ac747cad84b5dc8762c53a46d206fd97e3e21af9013dc608377300bbf50e3096", 
      "a001f7282f18c4f522e9554085ac8569d8a96cab3f1b3c8a6493c5303a2752a0", 
      "038311989d550a926c3ae2151dadafb7cb38fd926e360ce91b11cecbf06a779e", 
      "d314d02427bb5d59039c7f63fe12b4371704e67769bdf53d33df44a390613302", 
      "5ad3bee567cf8bc8b9ac17dd4d2cf96917c8b215f90c80651ee6e7ad7bde5d18", 
      "c340ea9c04607392f91a8ac675ec2bf12e72fd032075205d0ced2dfd19d4dbd4", 
      "68235063e101dd76eadad6b6f55c1018ad394222351018cbac6273cde612e74f", 
      "7f50719008b5bc802a9dde2235be4abbb142f0a950608ad7c329e0e912d7ed77", 
      "0c1da05ac3945d5357df800bcbfc1868e08643187a13363fe3deae0a19b1a78b", 
      "9e88a04a0cff0618a95fa72a912b1319e88b1eb74f8d195e9442539290722f4d", 
      "8c1771c0f01885e4aa83b84f748a4590648936a3b7fade0fcc1f402213e29697", 
      "a623bfe6ea553a98dfaf9c28d7a0963c0efa03f942ca0e68033cb5aed10eb673", 
      "6f055c50bf516742263533ec48c122f90884ee388282c5afdf0e4faefd61ba6a", 
      "a3e70bf001b25512e986a45ec108db602b059660d16f4abbdbb9d1704969e6d4", 
      "cbd2ae3592b4e5e17a29fe432dee62a5bb8c2f98d5107b65e9682fa3c3023ee9", 
      "b8764753607eddb9b1a6f75ce59120733ee19b28289422296eab901822f05a87", 
      "92249092773b0b2089cc3319a20276c46c5a6afe76dbe5415385591312e3a046", 
      "ceb9dfde95a87f7ec61650e42814c954e9ebe396670429df9bd78cb2a3fd7756", 
      "684b59cad2195309bb88bbc9057372ebda44313ccb862ff85a3f8c20713cad14", 
      "23d12ee22b72e7f71b15ebde60b21251faa3ee7ab52ace33d9b63667511d97f6", 
      "a3ea15adfa97df091deada285c3713531f680d5b2e4a1084161cfc82b63769ae", 
      "d0bd41e48ceec94908a9caac99dc858dfea4651f8ac59359f5b54344c4d56c72", 
      "be5b745908c56eccfb0a482e4f458c2b1a242a92c2da1eef1829a33689a75d18", 
      "a68a07a9b83441e63e1e56c56fd54002ebd5c6b1a90e2a1b8eceeb3184df7577", 
      "a105bc8da0f9cc0f5de1ba8b75528ec19a7b47b7127508ad18b7ed664e1d1ec9", 
      "58dfd55a391f6cfae99b62a0f0ec517bd4c08d63134944c0b7da4fcef44fe966", 
      "926698bae592eea9ebf30472a5d7078d2b7c1c589f67d6be4dc7678df42f8015", 
      "eb5c1656bedae6aedd96fe1369f587a2fba913105d4d1fbf8a429e071bc8c2cd", 
      "c8ccb7bb485dab15b54b1893dc08fbe2aee6ede377672b2e2d246328ec0c63a6", 
      "a92eae15666dae6934f1b9a4ef3d8c6ff7d74ef7a3916a174cb212f40c44a6e2", 
      "f7fde8b0370541f1ce55c252be0bfddd8d65dea831e059e96eaeae9dacf5a5ec", 
      "94cb84f43cee538d7b3ef2d8b736e936c2237f0f8d5cd63e3ac38eb4919c0502", 
      "86cd549f31ccceb108db9d38b4203399e1bcd29811a657fb3a293fc6e4f9c32c", 
      "02d85a1ede349bd5903ec18a08cfbb53f51c349690eb08e967a3bdfd0a87e397", 
      "2756691129c68c9e97a3efbb0f03c043f34024f5391c14b53b08e5568e03ea8b", 
      "10637e297842b7dabeeab71e9f4f805e56c9467077993dd0bd21be42c590ac30", 
      "cea411818063ddafa31504b409a5d7af436c784fb1590f1dd51b0a811bb16460", 
      "38949040549545f16795fe54feee464c377ae5e251911891cd7cc14d64e3cc81", 
      "04108f7abcab351ff1bac5047dcc128138dc07ca852a5b7f7582092adabc54cc", 
      "97ef038916b02810da0d43cd30670893b6ccd0694f1d27f9f728d713e36e75ba", 
      "33fac9ba22c5d832dd26d3b5153bd845e8a41ae7e7d1cb7ea9ba4fe3a515c120", 
      "9044ec20d3b745ad15759d2265698f67c12147ab57b0ee2e2245fb2b8d2c9136", 
      "c4928feb6466656d0bdca2f5d0d67745d8d047af84424889e00b8b098b5dc559", 
      "16bc7175d7b75fff79b7ccb0c43c0e5aecb88b92e6c3fc57ca0faffeccfbaf35", 
      "31859dab116c57de6293e462d1a3f0657c7bcc95f3e84777de2a82e517009ed9", 
      "c14a2734c026a144a880fec5291d84b082bd876c83ab14a5e99564de223f843c", 
      "b7a11eda52c668a19b4a3edd82a1d368be95f499a13700ef8134ba7618a26a88", 
      "ba15cea9b2302aad7ddeea8297c863b5a3d1318cb14f3c6df1635f89c6de34ff", 
      "c717df576a7526c06d3a61a787e12ffe64f53dc939a208117d25538f3aa10bbb", 
      "372478296c8595fd3cec66ac05d3e0a69a61383e4f813b29a5ca236410c60e3d", 
      "2c9b9a1beef2e287960e8ffadb8f1ff332e9ec4d4c7dc63a81e1cfef1be416e7", 
      "fc3a5659ccc94d97afd6dc44e19562fc1a0ab0870ab98f644039c939c7004e1a", 
      "c5bcfe3763d6c9cbf09e4000f4eb00bef9fedd87ef973982e9fd4de5aa0d5982", 
      "0c00f9712a9de1c53fb622ec29e7e28ee282ae703f5314f1e55995e8880793db", 
      "a76327a288cc4ce3f7bb0aa9c79241e07813370fe71d48710e079c03144ee6e3", 
      "fabefdcba8bbd2e2394e23005879bd5308ddefe5dd79c28c3adf2fbc6de06964", 
      "5517ee16368e184c79b4edf2163e7082591b300c38db86dbee3464cf3223bcc1", 
      "a7c9095de7ebeae72bfe56f743b5a24de11a81d1593cd276b6f1382986584e6d", 
      "bb1ba08057e60dfbd25d07dae414f669901953b1b8f5db15232312abb902d9c4", 
      "54424106a08ba21375da9cb6b4ce6b94963686ac9329856eaa2cdb920ca59fc9", 
      "5bc391875277422d774c0b35a74a7c1dc632434efe1b76fcb195d052763823f1", 
      "bd8b60c784f87ae4f651af2f150a99bd01602331a93fbf9a54a342ac6c863020", 
      "44c6c67a9f7e8e66385db5932d9effa5504c5d825e2a15a8a7dec1cd266665c9", 
      "6683cc1a1a006782ea665780a3a02ff828bbe20f0f87c4fd84b387145901826c", 
      "e6ae5aade0a6667abe95bdde617f92bbd938e8c19eba206334e5075aac2c6c72", 
      "a2417526b288174a29cd8a6278d1243d76d0d7b266d609fd0f73038c70a04653", 
      "97f060c56afaab79986c33ee3a00ad877705dea3d138c2a8d2212d51ef9195d9", 
      "b023594105897f3b2b71a37d05a40bfc30c56512a98f8d06c98ad2b4541049ec", 
      "29a2f14a09acc440201591aff6205f978e0d11c910486278c937b6628c0886e5", 
      "f6b8a17de4c21da98cca59ebc67767d2b4ab0fbcfc85d43f51b918bfc6a11062", 
      "6062373a73288661af54e74ea7687ad91a90651fc2f322d3decad1ccd4764fe1", 
      "4bf9e01c2025297b008a2d873c918a6084550e797a5ef64bd83539573d32c90d", 
      "c323778e30260b1db1d2a81df6d309c2827e264b9d16af18215362e9cd3e37cb", 
      "dc3354cfa8e4291850644c7fae1be5112824f9ff4e51aa3fbe76728842280b88", 
      "cb65f5557857ed2c4f51dd1a7d9f02d379da6084d9382f1eba20d8a32b55e4a1", 
      "01509fe20f37acb1c5e0ba19f763e24e148b0d8982bfe26e52051731798f7a3e", 
      "cc9a41dc8ccb31286358ed82242fb1b964ff94a46327024c25c36e421bfcf1d1", 
      "2be2662fcff7a078376227fff445e8df59dc80503022a942b8d33ffb69240f05", 
      "bd1d02a071ff26d6a7d21168b3c10144000eea623828647d8f6887fa7378bc74", 
      "abb369f2dbdf5a53949c6fa90a97de8cd17e1fa77349b0c930ebae2223d3191a", 
      "c0ae23449940b23851985884804e1e7810025ebb3e80a4bc4590f13304785a9a", 
      "65e3bd7ebebaa1574d6ee0995c48e00c14f8359ba3157716df053ddc3e382040", 
      "838ef0c1ae0301831a25f921c7d8a7ebe3e12d775fcfb352620f4de17973732f", 
      "7f74e8d45b180d66d1bc71bc6c1ba1bb89cbbaca5d580f706be44b37cfa937f1"
    ]

    $e1-cli listunspent
    [
      {
        "txid": "3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae",
        "vout": 0,
        "address": "2dnkzCcTTKn57XGVfUtk7H6MH8WWgRCAnAz",
        "account": "",
        "scriptPubKey": "76a914923d116f0cc845e6b485083753eddb77642819b188ac",
        "amount": 20999999.99996700,
        "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
        "assetlabel": "bitcoin",
        "confirmations": 101,
        "spendable": true,
        "solvable": true,
        "blinder": "0000000000000000000000000000000000000000000000000000000000000000",
        "assetblinder": "0000000000000000000000000000000000000000000000000000000000000000"
      }, 
      {
        "txid": "6f7e4810a489ce27a786133d0c7c05a171d02feef9cd6954761d6a3c12a8aedd",
        "vout": 0,
        "address": "2dgqTakTsM8raprpjYx6QanyUrrER4ZfZ2A",
        "account": "",
        "scriptPubKey": "76a9145144d5969d877616f4c4c9270ec20b57ecde7b7488ac",
        "amount": 0.00003300,
        "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
        "assetlabel": "bitcoin",
        "confirmations": 101,
        "spendable": true,
        "solvable": true,
        "blinder": "0000000000000000000000000000000000000000000000000000000000000000",
        "assetblinder": "0000000000000000000000000000000000000000000000000000000000000000"
      }
    ]
    
    $e1-cli gettransaction 3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae
    {
      "amount": {
        "bitcoin": 0.00000000
      },
      "fee": -0.00003300,
      "confirmations": 101,
      "blockhash": "883bcbfd4f6c94822ffedd1fd23c7e704fbc1a1d1ca5073c880395a1ea8ccf92",
      "blockindex": 1,
      "blocktime": 1544060998,
      "txid": "3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae",
      "walletconflicts": [
      ],
      "time": 1544060913,
      "timereceived": 1544060913,
      "bip125-replaceable": "no",
      "comment": "",
      "to": "",
      "details": [
        {
          "account": "",
          "address": "2dnkzCcTTKn57XGVfUtk7H6MH8WWgRCAnAz",
          "category": "send",
          "amount": -20999999.99996700,
          "amountblinder": "0000000000000000000000000000000000000000000000000000000000000000",
          "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
          "assetblinder": "0000000000000000000000000000000000000000000000000000000000000000",
          "label": "",
          "vout": 0,
          "fee": -0.00003300,
          "abandoned": false
        }, 
        {
          "account": "",
          "address": "2dnkzCcTTKn57XGVfUtk7H6MH8WWgRCAnAz",
          "category": "receive",
          "amount": 20999999.99996700,
          "amountblinder": "0000000000000000000000000000000000000000000000000000000000000000",
          "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
          "assetblinder": "0000000000000000000000000000000000000000000000000000000000000000",
          "label": "",
          "vout": 0
        }
      ],
      "hex": "0200000000015f2d99582ea16cc9451e8f9e19bdfedf43379ad0ad1fafb8ff66d22359017f020000000000feffffff0201230f4f5d4b7c6fa845806ee4f67713459e1b69e8e60fcee2e4940c7a0d5de1b201000775f05a07331c001976a914923d116f0cc845e6b485083753eddb77642819b188ac01230f4f5d4b7c6fa845806ee4f67713459e1b69e8e60fcee2e4940c7a0d5de1b2010000000000000ce4000000000000"
    }

    $e1-cli getrawtransaction 3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae 1
    {
      "hex": "0200000000015f2d99582ea16cc9451e8f9e19bdfedf43379ad0ad1fafb8ff66d22359017f020000000000feffffff0201230f4f5d4b7c6fa845806ee4f67713459e1b69e8e60fcee2e4940c7a0d5de1b201000775f05a07331c001976a914923d116f0cc845e6b485083753eddb77642819b188ac01230f4f5d4b7c6fa845806ee4f67713459e1b69e8e60fcee2e4940c7a0d5de1b2010000000000000ce4000000000000",
      "txid": "3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae",
      "hash": "3deffa93f7e8ccd5b98894b5d6f9a5a6d7567781188c6a1cb48c8d56967f37ae",
      "withash": "f150819cebd18e742bd70158fbf154dc6ca75b445141c87e8492bf48b758e628",
      "size": 165,
      "vsize": 165,
      "version": 2,
      "locktime": 0,
      "vin": [
        {
          "txid": "027f015923d266ffb8af1fadd09a3743dffebd199e8f1e45c96ca12e58992d5f",
          "vout": 0,
          "scriptSig": {
            "asm": "",
            "hex": ""
          },
          "is_pegin": false,
          "sequence": 4294967294
        }
      ],
      "vout": [
        {
          "value": 20999999.99996700,
          "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
          "n": 0,
          "scriptPubKey": {
            "asm": "OP_DUP OP_HASH160 923d116f0cc845e6b485083753eddb77642819b1 OP_EQUALVERIFY OP_CHECKSIG",
            "hex": "76a914923d116f0cc845e6b485083753eddb77642819b188ac",
            "reqSigs": 1,
            "type": "pubkeyhash",
            "addresses": [
              "2dnkzCcTTKn57XGVfUtk7H6MH8WWgRCAnAz"
            ]
          }
        }, 
        {
          "value": 0.00003300,
          "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
          "n": 1,
          "scriptPubKey": {
            "asm": "",
            "hex": "",
            "type": "fee"
          }
        }
      ],
      "blockhash": "883bcbfd4f6c94822ffedd1fd23c7e704fbc1a1d1ca5073c880395a1ea8ccf92",
      "confirmations": 101,
      "time": 1544060998,
      "blocktime": 1544060998
    }
    
    $e1-cli getrawtransaction 027f015923d266ffb8af1fadd09a3743dffebd199e8f1e45c96ca12e58992d5f 1
    {
      "hex": "01000000000178fdfddeafc3bac34abe63efee0d64f7d817cee508ded08746ba4ae6df5349cb0000008000ffffffff000000000000000000000000000000000000000000000000000000000000000006226e46111a0b59caaf126043eb5bbf28c34f3a5e332a1fc7b2b73cf188910f01000775f05a0740000100000000000000000101230f4f5d4b7c6fa845806ee4f67713459e1b69e8e60fcee2e4940c7a0d5de1b201000775f05a07400000015100000000",
      "txid": "027f015923d266ffb8af1fadd09a3743dffebd199e8f1e45c96ca12e58992d5f",
      "hash": "027f015923d266ffb8af1fadd09a3743dffebd199e8f1e45c96ca12e58992d5f",
      "withash": "7714b57149a7fe65e55cb528b1c091f3fa8cd52d0eed028e926ab270dd75801b",
      "size": 179,
      "vsize": 179,
      "version": 1,
      "locktime": 0,
      "vin": [
        {
          "txid": "cb4953dfe64aba4687d0de08e5ce17d8f7640deeef63be4ac3bac3afdefdfd78",
          "vout": 0,
          "scriptSig": {
            "asm": "",
            "hex": ""
          },
          "is_pegin": false,
          "issuance": {
            "assetBlindingNonce": "0000000000000000000000000000000000000000000000000000000000000000",
            "assetEntropy": "1c0edf6c0472150b1e91d57ddfbea15b005b3a6a70578c9e6796d386277638c5",
            "isreissuance": false,
            "token": "a6be6b365498cd451be75ba0f68c258ee01e08f3cb30d5f8469f6628db58dc61",
            "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
            "assetamount": 21000000.00000000,
            "tokenamount": 0.00000000
          },
          "sequence": 4294967295
        }
      ],
      "vout": [
        {
          "value": 21000000.00000000,
          "asset": "b2e15d0d7a0c94e4e2ce0fe6e8691b9e451377f6e46e8045a86f7c4b5d4f0f23",
          "n": 0,
          "scriptPubKey": {
            "asm": "1",
            "hex": "51",
            "type": "true"
          }
        }
      ],
      "blockhash": "209577bda6bf4b5804bd46f8621580dd6d4e8bfa2d190e1c50e932492baca07d",
      "confirmations": 102,
      "time": 1296688602,
      "blocktime": 1296688602
    }
    $e1-cli getrawtransaction cb4953dfe64aba4687d0de08e5ce17d8f7640deeef63be4ac3bac3afdefdfd78 1
    error code: -5
    error message:
    No such mempool or blockchain transaction. Use gettransaction for wallet transactions.
    $e1-cli gettransaction cb4953dfe64aba4687d0de08e5ce17d8f7640deeef63be4ac3bac3afdefdfd78 
    error code: -5
    error message:
    Invalid or non-wallet transaction id


