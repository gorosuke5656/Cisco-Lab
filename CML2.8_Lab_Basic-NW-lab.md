# CML2.8_Lab_Basic-NW-lab<br>

## １　Basic-NW-labの構成<br>
今回の演習は以下の３つの構成で実施します<br>
構成はルーター３台、スイッチ２台です<br>
（その１）<br>
<img width="1385" height="706" alt="image" src="https://github.com/user-attachments/assets/d6eb29fb-801c-4241-86ad-e64340bf11a0" />

 (その２）<br>
<img width="1389" height="704" alt="image" src="https://github.com/user-attachments/assets/69081536-5f8f-4fa6-aa3b-c2fa1588cd1b" />


 (その３）<br>
<img width="1385" height="618" alt="image" src="https://github.com/user-attachments/assets/2e4cf69e-25f7-43ed-8c48-290d850328e8" />


## 2 　Basic-NW-labで取り上げるテーマ<br>
　①【ルータネットワーク実習】<br>
　　(1)　RIPv1/V2による経路情報の交換<br>
　　(2)　OSPFによる経路情報の交換<br>
　　(3） EIGRPによる経路情報の交換<br>
　　(4)　複数のRoutingプロトコルによる経路情報の交換<br>
　　(5)　HSRPによるデフォルトGWの冗長化と確認<br>
　②【SWネットワーク実習】<br>
　　(1） CDP/LLDPによる隣接関係の確認<br>
　　(2)　VLANの構成及び確認<br>
　　(3)　STPの構成および確認<br>
   （4)　Storm Control設定と確認<br>
　　(6)　LAG設定と確認<br>
　　(7)　ACL設定と確認<br>

## 3 　各ノードへのアクセス<br>
### CML内臓コンソールサーバ機能を使用してSSH経由で接続→CML内のデバイスにアクセス<br>
<img width="1385" height="686" alt="image" src="https://github.com/user-attachments/assets/d5afc0de-5d46-4b76-b437-85ee48aa4852" />

#### (1) SSHクライアント（Tereterm等）でコンソールサーバーに接続<br> 
<img width="911" height="610" alt="image" src="https://github.com/user-attachments/assets/cf9bcd3a-661c-464c-9fc7-f91abb12c9d0" />

#### (2) コンソールサーバー画面<br> 
<img width="1128" height="600" alt="image" src="https://github.com/user-attachments/assets/0ddfd5db-30f5-48f8-a613-dff157c901f0" />

#### (3) Listコマンドでノード一覧を表示<br> 
<img width="1226" height="611" alt="image" src="https://github.com/user-attachments/assets/cf9d21bc-839f-4d15-8ea9-b15c8b556e53" />

#### (4) OPENコマンドで該当装置に接続<br>
<img width="1168" height="538" alt="image" src="https://github.com/user-attachments/assets/3a4aa78d-ca67-41f4-acc6-1c066c705df6" />



## 4　【ルーターネットワーク実習】<br>
### (1)　RIPv1/V2による経路情報の交換<br>
#### (1)-1 RIPv1による経路情報の交換<br>
<img width="1350" height="701" alt="image" src="https://github.com/user-attachments/assets/68ecbe5e-06db-40cf-ae64-76884c70468f" />

#### (1)-2 RIPv2による経路情報の交換<br>
<img width="1338" height="704" alt="image" src="https://github.com/user-attachments/assets/ddcf094c-5622-4f1d-959b-2503171f18f9" />

### 2 OSPFによる経路情報の交換<br>
#### シングルエリア構成と確認（構成）<br>
<img width="1386" height="678" alt="image" src="https://github.com/user-attachments/assets/e78c077c-3abc-4af9-a7aa-8521190a7a87" />

#### OSPF設定その１<br>
<img width="1386" height="598" alt="image" src="https://github.com/user-attachments/assets/a28efaa8-d112-4b83-a9ff-e6de70f5d690" />

<img width="1384" height="684" alt="image" src="https://github.com/user-attachments/assets/b6bf13c4-df28-4eac-bc7b-7430044c6fcb" />

##### OSPF確認（show ip ospf ne/show ip ospf database)<br>
<img width="1394" height="688" alt="image" src="https://github.com/user-attachments/assets/48dda8a0-46a4-4368-8bfe-ab8d701621da" />

##### OSPF確認（show ip protocols)<br>
<img width="1380" height="656" alt="image" src="https://github.com/user-attachments/assets/c33bef9f-2977-4d60-b9d3-882446f0ba99" />

##### OSPF確認（show ip route)<br>
<img width="1387" height="647" alt="image" src="https://github.com/user-attachments/assets/1761b1df-3815-4a5f-8d58-9008e75c9342" />

#### OSPF設定その２<br>
<img width="1370" height="684" alt="image" src="https://github.com/user-attachments/assets/ad2e0b88-7f4b-44ef-96f2-0ae202cb01d7" />

##### 設定例<br>
<img width="1379" height="687" alt="image" src="https://github.com/user-attachments/assets/273669c1-6f8c-483c-ad08-8123bcb14f5c" />

#### 【オプション課題】<br>
<img width="1382" height="625" alt="image" src="https://github.com/user-attachments/assets/d3d27aab-7051-435c-812d-9e4aa3828e09" />

##### 【オプション課題実施手順】<br>
<img width="1382" height="629" alt="image" src="https://github.com/user-attachments/assets/f0d9244b-30cd-46c9-ba1a-fbc497fd84b3" />



### ３ EIGRPによる経路情報の交換<br>
<img width="1588" height="745" alt="image" src="https://github.com/user-attachments/assets/4cc2ebbd-5021-48b6-95f8-a4eddb1623fd" />


#### 復号メトリックを使用した経路制御<br>
##### 構成は以下のようになります<br>
<img width="1592" height="776" alt="image" src="https://github.com/user-attachments/assets/f2e52af3-ddd6-4d6e-b63c-b9057c10dc94" />

##### 上記の構成で以下の内容を実施して確認します<br>
<img width="1584" height="734" alt="image" src="https://github.com/user-attachments/assets/b4b9827c-5eb0-4c06-ae0d-e6a5c71ba8a9" />

##### EIGRP設定後の確認（ネイバー及び対象インタフェース設定）<br>
<img width="1383" height="598" alt="image" src="https://github.com/user-attachments/assets/7443a471-da39-4e52-8cc0-7301641d38fb" />

##### EIGRP設定後の確認（EIGRPトポロジー情報の確認）<br>
<img width="1399" height="696" alt="image" src="https://github.com/user-attachments/assets/25317c59-ec65-42bb-8bc4-e831bc60e85d" />

##### EIGRP設定後の確認（ルーティングテーブルの確認）<br>
<img width="1384" height="655" alt="image" src="https://github.com/user-attachments/assets/6b397f1f-6844-449d-b2ce-e19fff49f0ee" />

##### EIGRP設定後の確認（SW１→SW２へのPING及びtraceroute結果）<br>
<img width="1376" height="586" alt="image" src="https://github.com/user-attachments/assets/e61c3f59-fbca-4ccf-a4ac-ee5a1cbfed23" />

##### 復号メトリックを使用した経路制御における回線のバックアップ<br>

###### （今回の構成）プライマリ経路に障害を発生させ、バックアップ経路に切り替えをします<br>
<img width="1390" height="623" alt="image" src="https://github.com/user-attachments/assets/f4799ddf-a30e-49b2-ad84-bce285c87b8b" />
###### 実施手順<br>

###### 実施手順<br>
<img width="1397" height="622" alt="image" src="https://github.com/user-attachments/assets/681e60f7-9df6-4be1-9c22-059365b689bb" />
##### R3のインタフェースをshutdown<br>
<img width="1380" height="424" alt="image" src="https://github.com/user-attachments/assets/8970e450-0d05-480b-9a63-66f9aff3e807" />
##### R1におけるEIGRPネイバー状態<br>
<img width="1372" height="285" alt="image" src="https://github.com/user-attachments/assets/c03c3a0b-f0ea-4393-b3f2-0ca5658d5eff" />
##### R1におけるトポロジテーブル<br>
<img width="1374" height="582" alt="image" src="https://github.com/user-attachments/assets/7c29fb49-feba-466e-9083-520297157ad1" />
##### R1における経路情報<br>
<img width="1388" height="653" alt="image" src="https://github.com/user-attachments/assets/f7e81c37-7a45-48de-a030-cb7d49fcf76f" />
##### SW1からのPING及びTraceroute<br>
 <img width="1376" height="596" alt="image" src="https://github.com/user-attachments/assets/8a70fc54-a080-465e-b204-c3a5b7dd137f" />

  
##### （参考）復号メトリックを使用した経路制御について<br>
<img width="1393" height="681" alt="image" src="https://github.com/user-attachments/assets/832b88d7-f860-4958-800b-800532be5de8" />

<img width="1386" height="681" alt="image" src="https://github.com/user-attachments/assets/c22c72c9-afcd-4f61-b64e-e11eebecdb96" />

<img width="1386" height="678" alt="image" src="https://github.com/user-attachments/assets/d44056d2-d48f-48f1-95e4-badbeeca9565" />

<img width="1388" height="665" alt="image" src="https://github.com/user-attachments/assets/bc4887e5-6e45-4d95-a14f-e61e130cef17" />

### 5 HSRPによるデフォルトGW冗長化と確認　<br>
#### 構成は以下のようになります
<img width="1386" height="659" alt="image" src="https://github.com/user-attachments/assets/e1c1b188-34b1-4d67-a447-1edb121cb61b" />

<img width="1381" height="643" alt="image" src="https://github.com/user-attachments/assets/885a02ee-39c3-49c8-af77-25824873aedc" />



## 4　【SWネットワーク実習】<br>
### (3)　STPの構成及び確認<br>
#### 以下の構成でSTP設定及び確認を実施します
<img width="1183" height="518" alt="image" src="https://github.com/user-attachments/assets/8beb6f55-289d-47cb-a5aa-f9b21f983121" />

##### STP構成の確認
<img width="1183" height="579" alt="image" src="https://github.com/user-attachments/assets/92a0e8b9-cdd5-4bb0-90dc-3cc39dad6d6b" />

今回は上記のように確認できました！<br>

##### 参考：show spanning-treeの表示について<br>
<img width="1190" height="520" alt="image" src="https://github.com/user-attachments/assets/6beaea85-f743-4ff7-8c41-08aea47c16a3" />

###### CiscoのSWはPVST+（Per-VLAN Spanning Tree）が動作するためこのようになります
