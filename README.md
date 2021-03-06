# grouping-tool-for-ws

## これはなに？
* ワークショップなどで、参加者のグループ分けを作成するためのツールです。
    * Excelファイルの参加者情報を読み込み、標準出力に結果を出力します。
    * 「ある属性が同じ人同士をなるべく異なるグループにする」ことをするためのツールです。
        * 同じ会社の人（会社という属性が同じ人同士）をなるべく異なるグループ同士にしたい、役職者（役職という属性が同じ人同士）が複数グループに散らばるようにしたい、など。

## 利用手順
## 準備
* Java1.8系とgradleをインストールしておく。
* grouping-tool-for-wsをクローンかダウンロードで入手する。
* データファイル data.xlsx とプロパティファイル grouping.properties を、同じフォルダに配置する。
## 実行
* grouping-tool-for-wsフォルダ直下で、以下を実行する。第1引数として、-Pargs=以下にデータとプロパティファイルがあるフォルダのパスを指定する。
    * 例　C:\hogeファイルにデータとプロパティファイルがあり、同じフォルダに結果を出力する場合  
    gradle run -Pargs=C:\hoge > C:\hoge\result.txt
* 結果は、1行＝1人で標準出力に出力する。1人ずつ、所属グループのID、参加者ID、参加者名をタブ区切りで表示する
    * 所属グループのIDは、数字（1～プロパティファイルで指定したグループ数）で表現される

## 動作検証環境
* java-1.8.0_74
* gradle-2.9

## データファイルの例とルール
準備中

## プロパティファイルの例とルール
準備中

## 結果例
    *************** result
    group-ID	participant-ID	participant-NAME
    2	33	Fさん
    2	23	Eさん
    2	43	Gさん
    2	2	Aさん
    3	34	Hさん
    3	12	Cさん
    3	4	Bさん
    3	21	Jさん
    1	15	Dさん
    1	45	Iさん
    1	46	Kさん
    1	47	Lさん

## Tips
* データの名寄せはあらかじめ実施しておくこと
    * 例：属性が英名と和名混じりの場合
* ある属性について同じ値の人が沢山いる場合（ある会社の人ばかりいるなど）、あらかじめデータを並び替えて、その値を持つ人たちをデータファイルが上にくるようにしておくとばらけやすくなる
* データファイルを開いた状態でプログラムを実行するとエラーになるので注意
