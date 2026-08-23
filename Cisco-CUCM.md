### LastUpdate:2026/08/23<br>

### 1 Cisco CUCMとは<br>
### 2 CUCM構成要素<br>
### 3 CUCMで使用する音声プロトコル<br>
### 4 CUCMを理解するための用語及び構成要素<br>
#### (1) CUCMクラスタ<br>
#### (2) Device Pool<br>
#### (3) CP<br>
#### (4) MOH（Music on Hold）<br>

#### (5) TFTP<br>
  IP-Phoneに対してコンフィグレーション及びファームウェアを提供するサービス<br>
   【TFTPサービスを実行するCUCMをTFTPサーバと呼びます】<br>
  DHCPサービスでは Option ID=150 でTFTPサーバのIPアドレスを登録します<br>
　　　　　　　　　　　　⇒　サーバーを複数登録できるため、TFTPサービスの2重化、負荷分散が可能<br>

##### IP-Phoneにおける起動シーケンスについて<br>
###### 全体構成<br>
<img width="1383" height="703" alt="image" src="https://github.com/user-attachments/assets/af64e37a-e0c5-4f4d-ae42-612351b58176" />


#### (5) CFB<br>
### 5 コールルーティングとCSS<br>
### 6 環境構成例<br>
