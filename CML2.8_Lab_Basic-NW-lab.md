# CML2.8_Lab_Basic-NW-lab<br>

## １　Basic-NW-labの構成<br>
今回の演習は以下の３つの構成で実施します<br>
構成はルーター３台、スイッチ２台です<br>
（その１）<br>
<img width="1385" height="706" alt="image" src="https://github.com/user-attachments/assets/d6eb29fb-801c-4241-86ad-e64340bf11a0" />

 (その２）<br>
<img width="1386" height="708" alt="image" src="https://github.com/user-attachments/assets/b3c1f7a6-c0d8-4c60-8cb0-9ec4876a5622" />

 (その３）<br>
<img width="1385" height="618" alt="image" src="https://github.com/user-attachments/assets/2e4cf69e-25f7-43ed-8c48-290d850328e8" />


## 2 　Basic-NW-labで取り上げるテーマ<br>
　①【ルータネットワーク実習】<br>
　　(1)　RIPv1/V2による経路情報の交換<br>
　　(2)　OSPFによる経路情報の交換<br>
　　(3） EIGRPによる経路情報の交換<br>
　　(4)　RIP/OSPF併用による経路情報の交換<br>
　　(5)　HSRPによるデフォルトGWの冗長化と確認<br>
　②【SWネットワーク実習】<br>
　　(1） CDP/LLDPによる隣接関係の確認<br>
　　(2)　VLANの構成及び確認<br>
　　(3)　STPの構成および確認<br>
   （4)　Storm Control設定と確認<br>
　　(6)　LAG設定と確認<br>
　　(7)　ACL設定と確認<br>

## 3 　各ノードへのアクセス<br>

## 4　【ルーターネットワーク実習】<br>
### (1)　RIPv1/V2による経路情報の交換<br>
#### (1)-1 RIPv1による経路情報の交換<br>
<img width="1350" height="701" alt="image" src="https://github.com/user-attachments/assets/68ecbe5e-06db-40cf-ae64-76884c70468f" />

#### (1)-2 RIPv2による経路情報の交換<br>
<img width="1338" height="704" alt="image" src="https://github.com/user-attachments/assets/ddcf094c-5622-4f1d-959b-2503171f18f9" />

### 2 OSPFによる経路情報の交換<br>
<img width="1344" height="703" alt="image" src="https://github.com/user-attachments/assets/beaa7fbd-7e05-45aa-bd08-e7ee155c2258" />

### 3 EIGRPによる経路情報の交換<br>
<img width="1588" height="745" alt="image" src="https://github.com/user-attachments/assets/4cc2ebbd-5021-48b6-95f8-a4eddb1623fd" />


設定するAS番号は100とします<br>
ア） R1及びR２にEIGRPを設定します。
イ）

#### 復号メトリックを使用した経路制御<br>
<img width="1592" height="776" alt="image" src="https://github.com/user-attachments/assets/f2e52af3-ddd6-4d6e-b63c-b9057c10dc94" />

上記の構成で以下の内容を実施して確認します<br>
<img width="1584" height="734" alt="image" src="https://github.com/user-attachments/assets/b4b9827c-5eb0-4c06-ae0d-e6a5c71ba8a9" />

ア）R1、R2及びR3にEIGRPを設定します。<br>

イ）以下の条件で複合メトリック設定（delay）を実施します。<br>
　　　　R1～R３～R2　　　→　プライマリ経路　各インタフェース間をdelay:10で設定<br>
　　　　R1～R2　　　　　 →　セカンダリ経路　各インタフェース間をdelay:100で設定<br>

ウ）SW1～SW2間にtracerouteを実施し、通信経路が、R1～R3～R2経由になることを確認してください<br>
　　　
エ）設定変更後、以下のコマンドで確認します<br>
　　　show ip eigrp neigbor<br>
      show ip eigrp interfaces<br>
      show ip eigrp topology<br>
      show ip route eigrp<br>  

###### show ip eigrp topolocyの情報は以下のようになります<br>
<img width="1399" height="696" alt="image" src="https://github.com/user-attachments/assets/25317c59-ec65-42bb-8bc4-e831bc60e85d" />

##### 復号メトリックを使用した経路制御における回線のバックアップ<br>
<img width="1384" height="689" alt="image" src="https://github.com/user-attachments/assets/0b395b74-b9a1-43f2-b905-685711bebdcf" />

   




