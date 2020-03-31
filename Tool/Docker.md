- 参考
  - https://www.slideshare.net/zembutsu/docker-images-containers-and-lifecycle
  - https://qiita.com/a-pompom/items/bf568322b190d0e283b6
  - https://qiita.com/nl0_blu/items/1de829288db2670276e8
  - https://www.slideshare.net/zembutsu/explaining-best-practices-for-writing-dockerfiles

### Docker Container
- Linuxカーネルを使っている
  - その上にDockerエンジンがある
    - その上に複数のコンテナが動いている
- リソースを持っている
  - プロセス、メモリ、デバイス、ネットワーク
- Dockerイメージ上に生成される

### Docker Image
- コンテナを実行するときに必要なファイルシステム
  - root、ベースのOS
- コンテナとは別の読み込み専用の領域
- イメージが同じコンテナが複数ある場合は、イメージは共有される
- Dockerfileからdocker buildすることで作られる

### Dockerfile
- FROM
  - ベースのイメージを指定する。Ubuntu、CentOSなどOSや、Ruby、Nginxなどの開発環境まで浅く深く様々
- ENV
  - コンテナ上で使用される環境変数を設定する。
  - キー=値
    - 一つのキーに複数の値を半角スペース区切りで指定できる
- WORKDIR
  - RUNやCOPY,CMD,ADDなどを実行する際の作業ディレクトリの指定を行う
  - 複数回実行すると直前の相対パスが指定される。
    - /a => b => c と実行したら、作業ディレクトリは /a/b/c

# Rails 関連

- 参考
  - https://qiita.com/jshimazu/items/ba13ce87dfdb11e2d1d9
  
- database.yml
  - hostに設定できる値はdocker内のネットワークに存在するデータベースであれば、そのコンテナ名を指定すれば良い。
    - db-containerというコンテナがあるなら、 host: db-container
