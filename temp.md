# Deploying the tutorial
## Deployed addresses and class hashes
starknet call --function balanceOf --address 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de --input 0x0360C4F27Bd9af2a05b416ff573738E8587883862A90965A1716DfA9D17F3E79

| Contract | Class hash | Deployed contract | Permissions |
| ------------------------------------- | ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Players registry | 0x25f0f9beb3c3bf0c01678aa830ff96fad5f2bd05b23a8f4c0a2bce92ec5f25d | 0x04732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 |  |
| TDERC20 | 0x2de7e654139db6c8c05d7c456b953e8feba7055a25d6dc0ab5d538314d96a6 | 0x044f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de |  |
| Ex01 | 0x27956db0c99ea0959280a6b3b14bdd1615a96bcf318e2d0826ed90abbd399a9 | 0x031d1866cb827c4e27bbca9ffee59fa2158b679413ffb58c3f90af56e1140e85 |  |
| Ex02 | 0x5acbc7548d1fc3f189427ce2c7480e4f7e4bda2844833cd8e57f5b918eadfdc | 0x0600f8fe0752e598b4e6b27839f00ad65215d129f385e12931323c487b6f9b36 |  |
| Ex03 | 0x5df061a4185d402e0b211ea6a7c772f837a028444c03e376b4dc066be5a40ec | 0x033d5fc40c0e262612528a9a652ada70be854d98241fb7548745262b5273c9d1 |  |
| Ex04 | 0x23e5c477e3892b705e1c16831ebecc2d2e534c6563e1e528fd2f3b8b7d06ed5 | 0x06967cd33c6e064087123958e239c98f0de5e6d663660fa16a2526e8b115688a |  |
| Ex05 | 0x5e805c2c57f5b7040401bef5af5439bb70add3403374d47eb1b9ead1b2f553c | 0x076c32e000f7112724bba3c5f51fb1290217a1010ae555e6ecbdb2bfe6613e33 |  |
| Ex06 | 0x7d0b5a20ff1bccb2e568779cfc24f35b6f4ffd4b97a3ab0b3f02cb072c08077 | 0x060987aea322cd12657588b6cdb0892db79322ab4533f7d74838ff2e2614a015 |  |
| Ex07 | 0x25dbaec22271885e5329a359537668c28c7474a3c4c92cf8b9f5efdfdb9f4b | 0x006051096480f375894eebb99948bce14a84c25093636c4b4e8222cc32a67cf0 |  |
| Ex08 | 0x18c34d459b1a86f1e7579692e989a8cde55448f39f506d00ad69731c857e481 | 0x01ec8e981b1b6a7256a71f21790dd07cafeb15d02c18534a2bd4a6c8551860aa |  |
| Ex09 | 0x14bfacc68ba10a1de50de173f11eaf5e2ddedb9df1a7ed220f7c0139c1cea | 0x053b96c4ee027c53ea001479f24c10b543063e3c26d037c600e5bd31f0b21e5c |  |
| Ex10 | 0x7df7072e0f054ae1f6cefe4d57a118bb4fd2e4caa43adcdd36e5d71fe5de5e7 | 0x0584d0e036824d2ac1bd216beef2c0e7080e5abbc89bd6c14832b8fbf8518108 |  |
| Ex10b | 0x32a35c4bf9c8148689002ca501c973a135a30457c6507e28261bed0c3a1f35 | 0x04c62a0c28a0ac56169d71e97c078ebc32c5bbdda568ebb8e4475ec961ca1c49 |  |
| Ex11 | 0x7373764393f1307fa9730f2a3deabf8505826bddb162d3f9051b8d449669a5 | 0x029a9a484d22a6353eff0d60ea56c6ffabaaac5e4889182287ef1d261578b197 |  |
| Ex12 | 0x3174b379c0dae73d2ea25bd6d3546e67b859b710bcd7a92eaf8bda068c0f484 | 0x04a221a8e3155fb03d1708881213a2ecdb05a41cf0ae6de83ddcf8f12bb04282 |  |
| Ex13 | 0x5d4af31df1011e23e90bccf721f8dd7040c468d3f9df8eb4a175c0002c339ca | 0x067ed1d23c5cc3a34fb86edd4f8415250c79a374e87bcf2e6870321261ca9b0f |  |
| Ex14 | 0x46150b73087b1ea48e6748f4d77749590107e336f525c5fca5683da18d3cd70 | 0x031e9a701a24c1d2ecd576208087dfa52f1025072cf11e54407300f64f95ce5f |  |


## Useful commands
Setting venv and env variables
```bash
source ~/cairo_venv_v11/bin/activate
export STARKNET_NETWORK=alpha-goerli
export STARKNET_WALLET=starkware.starknet.wallets.open_zeppelin.OpenZeppelinAccount
```
Declaring ex 1
```bash
starknet declare --contract target/release/starknet_cairo_101_Ex14.json --account version_11
```
Deploying players registry and ERC20 and checking admin is registered
```bash
# Players registry
starknet deploy --class_hash 0x7a6e514bb54d60ac1cfe8c53a872fbc23ebf25137d093c23c3bf01a6ae5b1c6 --inputs 0x0360C4F27Bd9af2a05b416ff573738E8587883862A90965A1716DfA9D17F3E79 --account version_11 --max_fee 100000000000000000
#ERC20
starknet deploy --class_hash 0x6b1cea5c54aef607edc926dec33a205d3da187ad8c1514706ab1e28db425138 --inputs 0x434149524f312d313031 0x434149524f312d313031 18 0 0 0x0360C4F27Bd9af2a05b416ff573738E8587883862A90965A1716DfA9D17F3E79 0x0360C4F27Bd9af2a05b416ff573738E8587883862A90965A1716DfA9D17F3E79 --account version_11 --max_fee 100000000000000000
starknet call --function is_exercise_or_admin --address 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 --input 0x0360C4F27Bd9af2a05b416ff573738E8587883862A90965A1716DfA9D17F3E79
starknet call --function is_teacher_or_exercise --address 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de --input 0x0360C4F27Bd9af2a05b416ff573738E8587883862A90965A1716DfA9D17F3E79
```
Declaring exercices
```bash
# Ex01
starknet deploy --class_hash 0x27956db0c99ea0959280a6b3b14bdd1615a96bcf318e2d0826ed90abbd399a9 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 1 --account version_11 --max_fee 100000000000000000
# Ex02
starknet deploy --class_hash 0x5acbc7548d1fc3f189427ce2c7480e4f7e4bda2844833cd8e57f5b918eadfdc --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 2 0x4b454b --account version_11 --max_fee 100000000000000000
# Ex03
starknet deploy --class_hash 0x5df061a4185d402e0b211ea6a7c772f837a028444c03e376b4dc066be5a40ec --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 3 --account version_11 --max_fee 100000000000000000
# Ex04
starknet deploy --class_hash 0x23e5c477e3892b705e1c16831ebecc2d2e534c6563e1e528fd2f3b8b7d06ed5 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 4 --account version_11 --max_fee 100000000000000000
# Ex 05
starknet deploy --class_hash 0x5e805c2c57f5b7040401bef5af5439bb70add3403374d47eb1b9ead1b2f553c --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 5 --account version_11 --max_fee 100000000000000000
# Ex06
starknet deploy --class_hash 0x7d0b5a20ff1bccb2e568779cfc24f35b6f4ffd4b97a3ab0b3f02cb072c08077 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 6 --account version_11 --max_fee 100000000000000000
# Ex07
starknet deploy --class_hash 0x25dbaec22271885e5329a359537668c28c7474a3c4c92cf8b9f5efdfdb9f4b --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 7 --account version_11 --max_fee 100000000000000000
# Ex08
starknet deploy --class_hash 0x18c34d459b1a86f1e7579692e989a8cde55448f39f506d00ad69731c857e481 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 8 --account version_11 --max_fee 100000000000000000
# Ex09
starknet deploy --class_hash 0x14bfacc68ba10a1de50de173f11eaf5e2ddedb9df1a7ed220f7c0139c1cea --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 9 --account version_11 --max_fee 100000000000000000
# Ex10
starknet deploy --class_hash 0x7df7072e0f054ae1f6cefe4d57a118bb4fd2e4caa43adcdd36e5d71fe5de5e7 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 10 --account version_11 --max_fee 100000000000000000
# Ex10b
starknet deploy --class_hash 0x32a35c4bf9c8148689002ca501c973a135a30457c6507e28261bed0c3a1f35 --inputs 0x0307dbe1012a45617af8a708266eb3c300ab3bf9efe3d6e5a2a5693999daa962 --account version_11 --max_fee 100000000000000000
# Ex11
starknet deploy --class_hash 0x7373764393f1307fa9730f2a3deabf8505826bddb162d3f9051b8d449669a5 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 11 --account version_11 --max_fee 100000000000000000
# Ex 12
starknet deploy --class_hash 0x3174b379c0dae73d2ea25bd6d3546e67b859b710bcd7a92eaf8bda068c0f484 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 12 --account version_11 --max_fee 100000000000000000
# Ex 13
starknet deploy --class_hash 0x5d4af31df1011e23e90bccf721f8dd7040c468d3f9df8eb4a175c0002c339ca --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 13 --account version_11 --max_fee 100000000000000000
# Ex 14
starknet deploy --class_hash 0x46150b73087b1ea48e6748f4d77749590107e336f525c5fca5683da18d3cd70 --inputs 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 1 14 --account version_11 --max_fee 100000000000000000
```
Adding exercices as admin in ERC20 and players registry
```bash
# ERCO
starknet invoke --function set_teachers --address 0x044f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de --input 14 0x031d1866cb827c4e27bbca9ffee59fa2158b679413ffb58c3f90af56e1140e85 0x0600f8fe0752e598b4e6b27839f00ad65215d129f385e12931323c487b6f9b36 0x033d5fc40c0e262612528a9a652ada70be854d98241fb7548745262b5273c9d1 0x06967cd33c6e064087123958e239c98f0de5e6d663660fa16a2526e8b115688a 0x076c32e000f7112724bba3c5f51fb1290217a1010ae555e6ecbdb2bfe6613e33 0x060987aea322cd12657588b6cdb0892db79322ab4533f7d74838ff2e2614a015 0x006051096480f375894eebb99948bce14a84c25093636c4b4e8222cc32a67cf0 0x01ec8e981b1b6a7256a71f21790dd07cafeb15d02c18534a2bd4a6c8551860aa 0x053b96c4ee027c53ea001479f24c10b543063e3c26d037c600e5bd31f0b21e5c 0x0584d0e036824d2ac1bd216beef2c0e7080e5abbc89bd6c14832b8fbf8518108 0x029a9a484d22a6353eff0d60ea56c6ffabaaac5e4889182287ef1d261578b197 0x04a221a8e3155fb03d1708881213a2ecdb05a41cf0ae6de83ddcf8f12bb04282 0x067ed1d23c5cc3a34fb86edd4f8415250c79a374e87bcf2e6870321261ca9b0f 0x031e9a701a24c1d2ecd576208087dfa52f1025072cf11e54407300f64f95ce5f 14 1 1 1 1 1 1 1 1 1 1 1 1 1 1  --account version_11 --max_fee 100000000000000000
# Players registry
starknet invoke --function set_exercises_or_admins --address 0x04732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 --input 14 0x031d1866cb827c4e27bbca9ffee59fa2158b679413ffb58c3f90af56e1140e85 0x0600f8fe0752e598b4e6b27839f00ad65215d129f385e12931323c487b6f9b36 0x033d5fc40c0e262612528a9a652ada70be854d98241fb7548745262b5273c9d1 0x06967cd33c6e064087123958e239c98f0de5e6d663660fa16a2526e8b115688a 0x076c32e000f7112724bba3c5f51fb1290217a1010ae555e6ecbdb2bfe6613e33 0x060987aea322cd12657588b6cdb0892db79322ab4533f7d74838ff2e2614a015 0x006051096480f375894eebb99948bce14a84c25093636c4b4e8222cc32a67cf0 0x01ec8e981b1b6a7256a71f21790dd07cafeb15d02c18534a2bd4a6c8551860aa 0x053b96c4ee027c53ea001479f24c10b543063e3c26d037c600e5bd31f0b21e5c 0x0584d0e036824d2ac1bd216beef2c0e7080e5abbc89bd6c14832b8fbf8518108 0x029a9a484d22a6353eff0d60ea56c6ffabaaac5e4889182287ef1d261578b197 0x04a221a8e3155fb03d1708881213a2ecdb05a41cf0ae6de83ddcf8f12bb04282 0x067ed1d23c5cc3a34fb86edd4f8415250c79a374e87bcf2e6870321261ca9b0f 0x031e9a701a24c1d2ecd576208087dfa52f1025072cf11e54407300f64f95ce5f 14 1 1 1 1 1 1 1 1 1 1 1 1 1 1 --account version_11 --max_fee 100000000000000000
```
To check the status:
```bash
# ERC20
starknet call --function is_exercise_or_admin --address 0x4732b911740d44f8916db5e49ad3cb20aa2969afc942923eed04bf185738636 --input 0x042b34fe6f5e03d25c0adfdf7149ce21942f725f94dbfe4454e9ea793ff99cb8
starknet call --function is_teacher_or_exercise --address 0x44f65adbdb59bf1db71e8b69efb7c9d0b810db94c1730a05fa5751b02d396de --input 0x042b34fe6f5e03d25c0adfdf7149ce21942f725f94dbfe4454e9ea793ff99cb8

```
Setting random values
```bash
starknet invoke --function set_random_values --address 0x06967cd33c6e064087123958e239c98f0de5e6d663660fa16a2526e8b115688a --input 100 509 7151 5476 3518 3472 1072 2672 1522 2451 4950 9493 6340 6911 3571 7159 111 5431 3695 1758 4928 5139 6549 2252 1068 1624 480 6659 7521 9588 8679 1091 4111 5113 5727 4376 5287 5718 7204 8537 7240 3457 455 685 3467 9279 7243 1571 5229 3683 9881 622 4622 7388 4811 2961 7321 2199 3362 7477 9380 4547 8696 5393 3719 1001 699 646 824 3133 1946 89 2980 8677 6857 2800 8920 1224 2189 6094 2932 5363 4795 192 2695 853 6569 6941 7967 5070 2585 4675 3048 444 2487 5451 6121 945 9343 5757 9193 --account version_11 --max_fee 100000000000000000

starknet invoke --function set_random_values --address 0x076c32e000f7112724bba3c5f51fb1290217a1010ae555e6ecbdb2bfe6613e33 --input 100 9760 8893 9155 1504 3558 5806 3145 8537 9798 1834 7969 8581 2448 9523 2435 9242 5081 8715 4195 6467 1218 8174 2955 9996 4129 8850 512 3215 7527 2373 9350 2872 9705 4779 2068 7184 5795 4942 8624 1927 4821 5234 9554 1503 1963 2490 925 8189 4138 9562 8507 5719 2976 131 7059 6648 4584 6839 9692 8072 2047 4929 9464 4557 8502 173 4404 1511 1958 2814 7708 3867 7408 114 1805 5990 4761 1797 8443 8075 4903 597 5980 7592 9607 3224 7164 8408 6744 6689 6120 3494 6485 519 3526 9327 2334 9125 4709 9798 --account version_11 --max_fee 100000000000000000

starknet invoke --function set_random_values --address 0x060987aea322cd12657588b6cdb0892db79322ab4533f7d74838ff2e2614a015 --input 100 8308 5970 1409 7875 8633 6802 4987 2249 8843 3546 2519 5738 214 5185 6229 4843 8604 5121 4495 40 8045 3028 1327 8160 9376 6845 5219 6010 2220 253 5913 8682 1031 6173 690 1235 8918 5215 2276 1228 4315 9814 4099 9322 9672 5389 5795 9779 4535 5385 3787 6393 5306 7019 5447 7366 9283 7893 5210 2696 323 1824 2665 6720 7457 2627 1784 2730 2100 7622 8957 3193 8833 6583 428 5015 9026 6353 8905 5935 3224 7475 5910 5129 8137 9669 5646 4841 2318 7741 2280 9086 5248 7178 4496 1003 934 2803 9022 8656 --account version_11 --max_fee 100000000000000000

starknet invoke --function set_random_values --address 0x04a221a8e3155fb03d1708881213a2ecdb05a41cf0ae6de83ddcf8f12bb04282 --input 100 8308 5970 1409 7875 8633 6802 4987 2249 8843 3546 2519 5738 214 5185 6229 4843 8604 5121 4495 40 8045 3028 1327 8160 9376 6845 5219 6010 2220 253 5913 8682 1031 6173 690 1235 8918 5215 2276 1228 4315 9814 4099 9322 9672 5389 5795 9779 4535 5385 3787 6393 5306 7019 5447 7366 9283 7893 5210 2696 323 1824 2665 6720 7457 2627 1784 2730 2100 7622 8957 3193 8833 6583 428 5015 9026 6353 8905 5935 3224 7475 5910 5129 8137 9669 5646 4841 2318 7741 2280 9086 5248 7178 4496 1003 934 2803 9022 8656 --account version_11 --max_fee 100000000000000000

starknet invoke --function set_random_values --address 0x067ed1d23c5cc3a34fb86edd4f8415250c79a374e87bcf2e6870321261ca9b0f --input 100 8308 5970 1409 7875 8633 6802 4987 2249 8843 3546 2519 5738 214 5185 6229 4843 8604 5121 4495 40 8045 3028 1327 8160 9376 6845 5219 6010 2220 253 5913 8682 1031 6173 690 1235 8918 5215 2276 1228 4315 9814 4099 9322 9672 5389 5795 9779 4535 5385 3787 6393 5306 7019 5447 7366 9283 7893 5210 2696 323 1824 2665 6720 7457 2627 1784 2730 2100 7622 8957 3193 8833 6583 428 5015 9026 6353 8905 5935 3224 7475 5910 5129 8137 9669 5646 4841 2318 7741 2280 9086 5248 7178 4496 1003 934 2803 9022 8656 --account version_11 --max_fee 100000000000000000
```