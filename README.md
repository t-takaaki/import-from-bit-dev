# import-from-bit-dev
bit.devに登録したコンポーネントをインストールして利用するサンプルコードです。

Yarn / Parcel.js / React.js を利用しています

## 使い方
[bit.dev](https://bit.dev/)について詳しくは[Quick Start](https://docs.bit.dev/docs/quick-start)や[Bit for React](https://docs.bit.dev/docs/tutorials/bit-react-tutorial)を参考にしてください。

### bitにコンポーネントを登録する
* bit.dev でアカウント作成
* ``` $ npm install bit-bin -g ```
	* 依存パッケージが見つからずエラーになるのでhomebrewで入れたほうがよいかも
		* ``` $ brew install bit ```
		* [Installation · Bit - Docs](https://docs.bit.dev/docs/installation#macos)
* ``` $ bit login ```
* ``` $ bit init ```
* ``` $ bit add components/*** ```
* ``` $ bit status ``` → git status
* ``` $ bit import bit.envs/compilers/react --compiler ```
  * build for React Components
	* 他にも ``` $ bit import bit.envs/compilers/babel --compiler ```
* ``` $ bit build ``` →他プロジェクトから使えるようにするためにビルドするらしい
* バージョン管理するためにタグをセットする
	* ``` $ bit tag --all 0.0.1 ```
* ```$ bit export <username>.<collection name> ```でプッシュできる

### bitからコンポーネントを取得する
* ``` $ yarn add @bit/<username>.<collection name>.<component name> ```
  * package.jsonのdependenciesに追加されていることを確認してください
* あとはソースコード内で ``` import HogeHoge from "@bit/<username>.<collection name>.<component name>" ``` すればOK
  * ローカルにあるコンポーネントと同じように使える
