# CML2.8_Lab_Basic-NW-lab<br>
### LastUpdate:2026/05/16<br>

# １　Basic-NW-labの実習構成<br>
## 今回の演習は以下の３つの構成で実施します<br>
## 構成はルーター３台、スイッチ２台です<br>
### その１<br>
<img width="1385" height="706" alt="image" src="https://github.com/user-attachments/assets/d6eb29fb-801c-4241-86ad-e64340bf11a0" />

### その２<br>
<img width="1389" height="704" alt="image" src="https://github.com/user-attachments/assets/69081536-5f8f-4fa6-aa3b-c2fa1588cd1b" />

### その３<br>
<img width="1385" height="618" alt="image" src="https://github.com/user-attachments/assets/2e4cf69e-25f7-43ed-8c48-290d850328e8" />


# 2 　Basic-NW-labで取り上げるテーマ<br>
# 【ルータネットワーク実習】<br>
 - [(1) RIPv1/V2による経路情報の交換](#RIP-Routing)<br>
 - [(2) OSPFによる経路情報の交換](#OSPF-routing)<br>
 - [(3) EIGRPによる経路情報の交換](#EIGRP-routing)<br>
 - [(4) 複数のRoutingプロトコルによる経路情報の交換](#Multu-routing)<br>
 - [(5) HSRPによるデフォルトGWの冗長化と確認](#HSRP)<br>
# 【SWネットワーク実習】<br>
 - [(1) CDP/LLDPによる隣接関係の確認](#CDP/LLDP)<br>
 - [(2) VLANの構成及び確認](#VLAN)<br>
 - [(3) STPの構成及び確認](#STP)<br>
 - [(4) Strom Control設定と確認](#StromControl)<br>
 - [(5) LAG設定と確認](#LAG)<br>
 - [(6) ACL設定と確認](#ACL)<br>
# 【参考資料】<br>
- [(1) Cisco機器に対するSSH設定](#SSH)<br>
- [(2) Ciscoスイッチにおけるポートミラーリング設定](#Mirror-config)<br>


# 3 　各ノードへのアクセス<br>
## CML内臓コンソールサーバ機能を使用してSSH経由で接続→CML内のデバイスにアクセス<br>
<img width="1385" height="686" alt="image" src="https://github.com/user-attachments/assets/d5afc0de-5d46-4b76-b437-85ee48aa4852" />

### (1) SSHクライアント（Tereterm等）でコンソールサーバーに接続<br> 
<img width="911" height="610" alt="image" src="https://github.com/user-attachments/assets/cf9bcd3a-661c-464c-9fc7-f91abb12c9d0" />

### (2) コンソールサーバー画面<br> 
<img width="1128" height="600" alt="image" src="https://github.com/user-attachments/assets/0ddfd5db-30f5-48f8-a613-dff157c901f0" />

### (3) Listコマンドでノード一覧を表示<br> 
<img width="1226" height="611" alt="image" src="https://github.com/user-attachments/assets/cf9d21bc-839f-4d15-8ea9-b15c8b556e53" />

### (4) OPENコマンドで該当装置に接続<br>
<img width="1168" height="538" alt="image" src="https://github.com/user-attachments/assets/3a4aa78d-ca67-41f4-acc6-1c066c705df6" />



# 4　【ルーターネットワーク実習】<br>
## RIP-Routing<br>
### (1)-1 RIPv1による経路情報の交換<br>
<img width="1350" height="701" alt="image" src="https://github.com/user-attachments/assets/68ecbe5e-06db-40cf-ae64-76884c70468f" />

### (1)-2 RIPv2による経路情報の交換<br>
<img width="1338" height="704" alt="image" src="https://github.com/user-attachments/assets/ddcf094c-5622-4f1d-959b-2503171f18f9" />

#### 参考：RIPVer1運用における問題点とRIPVer2の利点<br>
<img width="1191" height="593" alt="image" src="https://github.com/user-attachments/assets/563142d0-c5bd-4fa1-9b01-fe8d7727fbb0" />

<img width="1199" height="555" alt="image" src="https://github.com/user-attachments/assets/7a31a9b9-692d-45b8-97c8-702fceecdfaf" />

##### RIPVer2の特徴<br>
<img width="1384" height="673" alt="image" src="https://github.com/user-attachments/assets/22b609a9-d3ad-4b18-a8f9-2d35aab4dfc7" />

<img width="1387" height="624" alt="image" src="https://github.com/user-attachments/assets/f5a7913c-de4c-47a5-b799-c896a780d3ba" />


#### 【オプション課題(RIPVer2における自動集約機能の有無における違いを確認しましょう！）】<br>
<img width="1389" height="630" alt="image" src="https://github.com/user-attachments/assets/86d15e85-8cb9-4a0c-ba0d-91459e29a346" />

##### R1/R2においてRIPv2の自動集約を無効にしていない場合、R3のルーティングテーブルは以下のようになります<br>
<img width="1395" height="634" alt="image" src="https://github.com/user-attachments/assets/b2e6d0ff-39d5-45e9-9702-8265a54df2f0" />


##### R1/R2においてRIPv2の自動集約を無効を設定<br>
<img width="1393" height="645" alt="image" src="https://github.com/user-attachments/assets/de6c9d1e-cdf8-42b4-a4c7-f3e0cdea999c" />

##### R1/R2においてRIPv2の自動集約を無効を設定<br>
<img width="1374" height="642" alt="image" src="https://github.com/user-attachments/assets/1cba72d6-793d-415b-8880-dcc7470a0b14" />





# ospf-routing<br>
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

#### マルチエリアOSPF構成と確認（構成）<br>
<img width="1372" height="682" alt="image" src="https://github.com/user-attachments/assets/157f98b2-a055-4284-a63b-26583680091c" />

##### 〇 経路情報の確認（show ip route ospf)<br>
<img width="1385" height="627" alt="image" src="https://github.com/user-attachments/assets/fb22e3e9-4c1e-483e-aefd-9cd183566f92" />

##### 〇 リンクステートデータベースの確認（show ip ospf database)<br>
<img width="1372" height="633" alt="image" src="https://github.com/user-attachments/assets/41cc6c95-d9bd-446f-88f2-f4ac63d685b1" />

#### マルチエリアOSPF&再配送構成と確認（構成）<br>
<img width="1384" height="683" alt="image" src="https://github.com/user-attachments/assets/97044908-90c7-4eda-8521-70d8a8068999" />

##### 〇 R2の設定変更<br>
<img width="1383" height="656" alt="image" src="https://github.com/user-attachments/assets/d3965936-2094-4cf0-8bfa-a808b924b2e6" />

##### 〇 経路情報の確認（show ip route ospf)<br>
<img width="1376" height="651" alt="image" src="https://github.com/user-attachments/assets/50316b9b-263a-45d3-8c10-105997afee7b" />

##### 〇 リンクステートデータベースの確認（show ip ospf database)<br>
<img width="1386" height="669" alt="image" src="https://github.com/user-attachments/assets/f80f1a5f-93a0-446e-9464-64280d88f0a3" />

#### （参考）OSPFの関連情報<br>
<img width="1383" height="691" alt="image" src="https://github.com/user-attachments/assets/0eb39cfb-466d-42e7-8708-eaafb295358d" />
<img width="1387" height="673" alt="image" src="https://github.com/user-attachments/assets/192871f0-e491-4c51-9ae0-927a19c8580a" />
<img width="1390" height="680" alt="image" src="https://github.com/user-attachments/assets/2328b6e2-ff5f-4488-8fad-3f0c5c71e1f9" />

##### （参考）主なリンク状態広告（LSA：Link-State Advertizement）の種類<br>
<img width="1378" height="619" alt="image" src="https://github.com/user-attachments/assets/e9f240c0-6887-441a-8852-2a1b689faa63" />

<img width="1378" height="625" alt="image" src="https://github.com/user-attachments/assets/bb502c89-3924-4336-a843-db00717417b3" />

<img width="1398" height="572" alt="image" src="https://github.com/user-attachments/assets/47035a9a-d8e7-4467-9e7d-3a25d5461743" />

<img width="1391" height="637" alt="image" src="https://github.com/user-attachments/assets/92b315df-302d-402c-9c1a-a0790b6372d0" />

<img width="1380" height="617" alt="image" src="https://github.com/user-attachments/assets/c1381d24-8f35-4a6f-ad35-307a46507651" />


#### 【オプション課題(MTU値の違いによるOSPFネイバー未確立の確認】<br>
<img width="1382" height="625" alt="image" src="https://github.com/user-attachments/assets/d3d27aab-7051-435c-812d-9e4aa3828e09" />

##### 【オプション課題実施手順】<br>
<img width="1382" height="629" alt="image" src="https://github.com/user-attachments/assets/f0d9244b-30cd-46c9-ba1a-fbc497fd84b3" />

##### 事前確認　ア）OSPFインタフェース確認　/　イ）　OSPFネイバー確認<br>
<img width="1374" height="564" alt="image" src="https://github.com/user-attachments/assets/4b10cc77-582c-4008-a86c-787587e04140" />

##### 事前確認　ウ）  MTU値確認<br>
<img width="1354" height="571" alt="image" src="https://github.com/user-attachments/assets/882b52ac-f312-4d1d-85b0-e4c473c635e5" />

##### debugコマンド実行(debug ip ospf adj)/MTU値変更（MTU:1500 → MTU:1280）/OSPFプロセスをクリア<br>
<img width="1359" height="517" alt="image" src="https://github.com/user-attachments/assets/57b571ff-7b8a-4745-9814-578d14905399" />

##### debugコマンドを確認（debug ip ospf adjログを抜粋）<br>
<img width="1376" height="593" alt="image" src="https://github.com/user-attachments/assets/84e701b9-a599-4fd9-a1b2-6c455aa06b1c" />

##### debugコマンドを停止（undebug all)/OSPFネイバーを確認<br>
<img width="1378" height="399" alt="image" src="https://github.com/user-attachments/assets/205cde1e-730b-4664-936a-d36cd35982d7" />

##### MTU値変更（MTU:1280 → MTU:1500）/OSPFネイバーを確認<br>
<img width="1381" height="522" alt="image" src="https://github.com/user-attachments/assets/2d35c4c0-85f9-430b-848e-3dba16fc8c52" />

# EIGRP-routing<br>
<img width="1588" height="745" alt="image" src="https://github.com/user-attachments/assets/4cc2ebbd-5021-48b6-95f8-a4eddb1623fd" />

##### EIGRPの設定<br>
<img width="1377" height="673" alt="image" src="https://github.com/user-attachments/assets/96332535-10cc-4f2b-8e9c-add5e6704732" />

<img width="1582" height="779" alt="image" src="https://github.com/user-attachments/assets/4876e3f8-b3e1-4168-9bdd-7d3c352f9897" />


#### 複合メトリックを使用した経路制御<br>
##### 構成は以下のようになります<br>
<img width="1592" height="776" alt="image" src="https://github.com/user-attachments/assets/f2e52af3-ddd6-4d6e-b63c-b9057c10dc94" />

##### 上記の構成で以下の内容を実施して確認します<br>
<img width="1584" height="734" alt="image" src="https://github.com/user-attachments/assets/b4b9827c-5eb0-4c06-ae0d-e6a5c71ba8a9" />

##### R1及びR2におけるインタフェースのdelay設定<br>
<img width="1321" height="491" alt="image" src="https://github.com/user-attachments/assets/6292008a-e98c-47ed-8159-3d5c38f7a404" />


##### EIGRP設定後の確認（ネイバー及び対象インタフェース設定）<br>
<img width="1383" height="598" alt="image" src="https://github.com/user-attachments/assets/7443a471-da39-4e52-8cc0-7301641d38fb" />

##### EIGRP設定後の確認（EIGRPトポロジー情報の確認）<br>
<img width="1399" height="696" alt="image" src="https://github.com/user-attachments/assets/25317c59-ec65-42bb-8bc4-e831bc60e85d" />

##### EIGRP設定後の確認（ルーティングテーブルの確認）<br>
<img width="1384" height="655" alt="image" src="https://github.com/user-attachments/assets/6b397f1f-6844-449d-b2ce-e19fff49f0ee" />

##### EIGRP設定後の確認（SW１→SW２へのPING及びtraceroute結果）<br>
<img width="1376" height="586" alt="image" src="https://github.com/user-attachments/assets/e61c3f59-fbca-4ccf-a4ac-ee5a1cbfed23" />

##### 複合メトリックを使用した経路制御における回線のバックアップ<br>

###### （今回の構成）プライマリ経路に障害を発生させ、バックアップ経路に切り替えをします<br>
<img width="1390" height="623" alt="image" src="https://github.com/user-attachments/assets/f4799ddf-a30e-49b2-ad84-bce285c87b8b" />


###### 実施手順<br>
<img width="1397" height="622" alt="image" src="https://github.com/user-attachments/assets/681e60f7-9df6-4be1-9c22-059365b689bb" />

###### R3のインタフェースをshutdown<br>
<img width="1380" height="424" alt="image" src="https://github.com/user-attachments/assets/8970e450-0d05-480b-9a63-66f9aff3e807" />

###### R1におけるEIGRPネイバー状態を確認<br>
<img width="1372" height="285" alt="image" src="https://github.com/user-attachments/assets/c03c3a0b-f0ea-4393-b3f2-0ca5658d5eff" />

###### R1におけるトポロジーテーブルを確認<br>
<img width="1374" height="582" alt="image" src="https://github.com/user-attachments/assets/7c29fb49-feba-466e-9083-520297157ad1" />

###### R1における経路情報を確認<br>
<img width="1388" height="653" alt="image" src="https://github.com/user-attachments/assets/f7e81c37-7a45-48de-a030-cb7d49fcf76f" />

###### SW1からのPING及びtraceroute確認<br>
 <img width="1376" height="596" alt="image" src="https://github.com/user-attachments/assets/8a70fc54-a080-465e-b204-c3a5b7dd137f" />

  
##### （参考）複合メトリックを使用した経路制御について<br>
<img width="1393" height="681" alt="image" src="https://github.com/user-attachments/assets/832b88d7-f860-4958-800b-800532be5de8" />

<img width="1386" height="681" alt="image" src="https://github.com/user-attachments/assets/c22c72c9-afcd-4f61-b64e-e11eebecdb96" />

<img width="1386" height="678" alt="image" src="https://github.com/user-attachments/assets/d44056d2-d48f-48f1-95e4-badbeeca9565" />

<img width="1388" height="665" alt="image" src="https://github.com/user-attachments/assets/bc4887e5-6e45-4d95-a14f-e61e130cef17" />

##### 【オプション課題：Stack in Activeが発生するネットワーク構成と対策】<br>
<img width="1333" height="588" alt="image" src="https://github.com/user-attachments/assets/f18a79ef-84be-478e-af23-554c71c0783b" />

# Multu-routing<br>

# HSRP<br>

#### 構成は以下のようになります<br>
<img width="1385" height="638" alt="image" src="https://github.com/user-attachments/assets/41f8face-9f55-4adb-9d90-a42c14b01f87" />

<img width="1594" height="762" alt="image" src="https://github.com/user-attachments/assets/b209be78-dca6-41b3-b31d-efefc55e2fd4" />

#### HSRP正常時における動作確認<br>
##### 正常時における動作確認（R1）<br>
<img width="1574" height="682" alt="image" src="https://github.com/user-attachments/assets/28d9c5e1-583e-44df-9b1d-0a4f172f70bf" />

##### 正常時における動作確認（R2）<br>
<img width="1596" height="683" alt="image" src="https://github.com/user-attachments/assets/a97b4fb3-6d1f-4aec-8bd6-74120202ba6a" />

##### 正常時における動作確認（SW1からのPING及びTraceroute）<br>
<img width="1585" height="733" alt="image" src="https://github.com/user-attachments/assets/bebaae30-01a6-414c-ac06-86ba3027d70b" />

<img width="1365" height="562" alt="image" src="https://github.com/user-attachments/assets/bc30e0b0-3cad-46fb-ad09-28205c0718cd" />


#### HSRP障害時における動作確認<br>
<img width="1590" height="734" alt="image" src="https://github.com/user-attachments/assets/650d3330-0682-4343-9273-91752601303b" />

##### 障害時における動作確認（R1）<br>
<img width="1576" height="573" alt="image" src="https://github.com/user-attachments/assets/740c81c6-df53-42ea-8f72-41e3dd8eab86" />
<img width="1547" height="626" alt="image" src="https://github.com/user-attachments/assets/cf69edb7-8dd1-4256-bf4d-5bf4d56ffd51" />

##### 障害時における動作確認（R2）<br>
<img width="1563" height="671" alt="image" src="https://github.com/user-attachments/assets/44a9d59e-adc6-4502-ba13-ca565662390a" />

##### 障害時における動作確認（SW1からのPING及びTraceroute）<br>
<img width="1382" height="578" alt="image" src="https://github.com/user-attachments/assets/ed306b2e-88e0-40e2-8888-de0b4a6b1300" />



##### （確認）HSRP障害時におけるR1/R2のARPテーブルはどうなっているでしょうか？？<br>
<img width="1584" height="665" alt="image" src="https://github.com/user-attachments/assets/1e8a4c11-822f-4fc6-bea1-4b4ff7ae552d" />

##### （確認）HSRP Preemptの設定と確認<br>
<img width="1188" height="557" alt="image" src="https://github.com/user-attachments/assets/847587ab-9192-4f38-bea8-8abf1867f534" />





# 4　【SWネットワーク実習】<br>
# CDP/LLDP<br>
### CDP/LLDPを使用して対向のSWの情報を確認してみましょう！<br>
<img width="1392" height="674" alt="image" src="https://github.com/user-attachments/assets/45ef4ade-6e7c-4eaf-a7ca-d5602eb02772" />

### (1)-1 CDPによる隣接関係の確認<br>
<img width="1373" height="619" alt="image" src="https://github.com/user-attachments/assets/fc5a97c7-2520-4c7a-9543-f3979d3b49ea" />

<img width="1375" height="654" alt="image" src="https://github.com/user-attachments/assets/e44bdc3b-2027-4b46-b4f9-0e2cf065aeda" />

### (1)-2 LLDPによる隣接関係の確認<br>
<img width="1383" height="632" alt="image" src="https://github.com/user-attachments/assets/39518d90-27cc-4399-8270-9d5db987d7f4" />

<img width="1387" height="616" alt="image" src="https://github.com/user-attachments/assets/3aaaccc7-c6e9-4a7b-ae33-7112160b0253" />

<img width="1362" height="667" alt="image" src="https://github.com/user-attachments/assets/4da82ea8-6294-479f-84e9-e402414c47e1" />

# VLAN<br>


# STP<br>
## 以下の構成でSTP設定及び確認を実施します
<img width="1183" height="518" alt="image" src="https://github.com/user-attachments/assets/8beb6f55-289d-47cb-a5aa-f9b21f983121" />

#### STP構成の確認
<img width="1183" height="579" alt="image" src="https://github.com/user-attachments/assets/92a0e8b9-cdd5-4bb0-90dc-3cc39dad6d6b" />

今回は上記のように確認できました！<br>

#### 参考：show spanning-treeの表示について<br>
<img width="1190" height="520" alt="image" src="https://github.com/user-attachments/assets/6beaea85-f743-4ff7-8c41-08aea47c16a3" />

##### 参考 CiscoのSWはPVST+（Per-VLAN Spanning Tree）が動作するためこのようになります
<img width="1333" height="663" alt="image" src="https://github.com/user-attachments/assets/412c20c0-26a4-498e-917d-816d99eb9c66" />

##### （実習１）ブロッキングポートを変更して見ましょう!<br>
<img width="1329" height="572" alt="image" src="https://github.com/user-attachments/assets/aa977b52-0fb5-41b3-a0e4-92852e3ef0ff" />
<img width="1333" height="604" alt="image" src="https://github.com/user-attachments/assets/3d62d6c4-a159-42fb-b4b0-bd33beca39f5" />
<img width="1327" height="633" alt="image" src="https://github.com/user-attachments/assets/15b6a974-427f-440d-af36-5a2b8500e2c9" />

##### SW2のパスコストを変更してブロッキングポートを変更
<img width="1341" height="482" alt="image" src="https://github.com/user-attachments/assets/36ec91fa-06be-47a5-8c23-2e7fa647d0c9" />

##### ブロッキングポートが変更されました～<br>
<img width="1326" height="637" alt="image" src="https://github.com/user-attachments/assets/736ef4d5-1f34-4f43-9f8e-7bd8173bd3f2" />

##### （実習２）ルートブリッジを変更して見ましょう!<br>

# StromControl<br>

# LAG<br>
## 構成図<br>
<img width="1379" height="636" alt="image" src="https://github.com/user-attachments/assets/3ae79f27-d0ea-402a-8e05-ae29f8ca75f1" />

## LAG障害時<br>
<img width="1373" height="629" alt="image" src="https://github.com/user-attachments/assets/306a3c49-bfa9-4933-9cea-5efcaf467aba" />



# ACL<br>

# 【参考資料】<br>

# SSH<br>

# Mirror-config




