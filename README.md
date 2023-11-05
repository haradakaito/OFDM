# OFDM通信方式
## 1. OFDMの仕組み・原理
### 1.1 マルチキャリア通信
OFDMはマルチキャリア通信という通信方式に包含される通信規格の一つである.  
マルチキャリア通信方式とは, 搬送波(キャリア)と呼ばれるデータの伝達に使用される電波を複数用いることで, 同時に複数の通信を実現する通信方式のことである.  
 <img align=center width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/ee51f589-39fd-4ac9-a233-777b65ba4d69">
 
本来送信するデータを運ぶ搬送波を複数に分割し, サブキャリアとして送信する.  
このときサブキャリアは周波数や振幅などの特性が異なるように分割される.  
欠点としては, 周波数の占有帯域が大きくなり通信方式によっては通信効率が悪くなってしまう場合がある.  
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/e7fab41a-5ce0-4c07-9a53-de6c8d6b4217">

マルチキャリア通信において生成されるサブキャリアは, スライドに示すような周波数特性を持つように生成される.  
理想としては, 周波数成分を抽出した際に, 特定の周波数成分のみが現れるような電波になることであるが, そのためには, 観測時間が∞である必要があり, 現実には∞時間の観測を行うことは不可能であるため, 区間ΔTに注目した時の周波数成分の抽出を考える.  
その場合, 特定の周波数成分以外に, ノイズとなる他の周波数成分が現れてしまう.  
具体的には, 特定の周波数成分をピークとし, 広がるように1/ΔTの間隔で他の周波数成分が観測される.  
### 1.2 FDM(周波数分割多重方式)
OFDMの基本となる多重化方式であるFDMという通信方式について説明する.  
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/c69b7bc0-f1bf-4e53-9021-23a1a3cfe1a1">

FDM方式はサブキャリア同士の持つがお互いのノイズに影響を与えないように、周波数帯域の間隔を十分に空けてサブキャリアを配置する多重化方式である.  
通信世代では1Gにあたり, 欠点としては, 占有する周波数帯域が大きいという点が挙げられる.  
この多重化方式はテレビ, ラジオなどでよく耳にする, チャンネルという言葉の語源となっている周波数帯域の集合を用いて管理される.  
### 1.3 OFDM(直交周波数分割多重方式)
OFDMについて説明する. OFDMは完結にいうとFDMの多重化方式を改良したマルチキャリア通信方式と言える.  
OFDM(Orthogonal Frequency Division Multiplexing)は日本語訳で直交周波数分割多重という意味であり, その名の通りFDMのサブキャリアの配置に直交の性質を利用したものである.  
ここでいう直交とは, サブキャリア同士が放つノイズが0になる地点に他のサブキャリアのピークが来るような状態を周波数成分が直交していると言う.  
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/1d02c02b-d688-478b-9fbb-ac3835688976">

実現される原理としては, 直交しているベクトルは可逆な合成が可能であるというものである.  
これにより, FDMの欠点である占有周波数帯域が大きくなるという問題を改善したことで通信効率の高いマルチキャリア通信を実現している.  
通信世代としては4Gにあたる通信方式である.  
実用化の際には, QAMなどの変調をサブキャリアに施すことで更なる通信効率・速度の向上を行っています.  
## 2. OFDMの実用化
### 2.1 QAM(直交位相振幅変調)
OFDMの実用化の際にサブキャリアに変調を加えることで通信効率・速度が向上するという説明をしたが, ここではその仕組みについて説明する.  
QAM(Quadrature Amplitude Modulation)は日本語で直行位相振幅変調と言い, 位相の直交する電波を合成し, 振幅成分も細分化することで同じ周波数成分を持つ電波で複数のビットを表現することができるようになる変調技術である.  
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/1cfd3e03-1bf0-4474-9fd6-7bd2b0d1ff64">

写真の例では, 位相と振幅で４つづつ細分化することで全16状態を表現することができるようにした変調例を示している.  
これをサブキャリアに適用することで一つのサブキャリアが扱えるビットが増加し, それに伴い通信効率がさらに向上する.  
### 2.2 MIMO(マイモ)
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/5862fe9e-0ff2-4ad1-b2ce-d6babb4a3600">

IEEE 802.11n規格から初めて採用された通信方式であり, 複数のアンテナを用いて通信を行う方式である.  
これにより, 同じ各アンテナでマルチキャリア通信を行うことで, 更なる多重化を実現している.  
これにより, 従来の通信規格と比較しても格段に通信速度, 効率が向上した.  
## 3. まとめ・余談
### 3.1 OFDM(直行周波数分割多重方式)
OFDMはマルチキャリア通信を実現するための手法の一つであり, 周波数成分の直交を利用することで占有周波数帯域の増加というマルチキャリア通信のデメリットを改善した通信方式である.  
また, QAMという変調方式を適用することでOFDMで扱うことのできるビット数を増加させ, 通信効率・速度を向上させることで実用化されている.  
### 3.2 TDM(時間分割多重方式)
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/97f511ed-de75-4ee4-bd83-13b0a64da66b">

通信世代で2Gにあたる多重化方式である.  
時間軸を利用してサブキャリアを配置することで多重化を実現している.  
短い時間で各チャンネルの通信時間を切り替えることで多重化通信を実現し, FDMよりも効率良い通信を可能にした.  
### 3.3 CDM(符号分割多重方式)
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/18a9d1f8-9151-454d-95ec-8061fc4b121a">

通信世代では3Gにあたる通信方式である.  
符合を付与することでサブキャリアを識別し, 多重化を実現する.  
サブキャリアを混合させて符合をもとに複合するため, ノイズに強く, 秘匿性にも優れた通信方式である.  
### 3.4 NOM(非直行多重方式)
<img width="500" alt="image" src="https://github.com/haradakaito/OFDM/assets/75819611/4f0253fd-7179-4d82-8542-c4731deb5831">

通信世代の5Gにあたる通信方式である.  
これはサブキャリアごとの干渉を許容する通信方式である.  
つまり, 周波数成分の直交を行わずに, 振幅成分についても分割しサブキャリアを区別することで同じ占有周波数帯域の中により多くの通信を含ませることができるようにしたものである.  
実際にはOFDM方式と合わせて実用化される.  
この考え自体は, 前から考えられており, 信号の複合技術が進歩したことで実現するに至った方法である.  
