# vk-admin-banners
Banners of Vektor,Inc's Pruducts

## バナーの追加方法

1. 画像を images フォルダに置きます。
1. vk-admin-banners.json を編集します。（詳細は下記を参照）

### テーマを追加する場合

|  属性名 | 説明 |
| --- | --- |
|  type  | theme  |
|  slug  | 【テーマのディレクトリ名】/style.css  |
|  image_file  | バナーのファイル名  |
|  link_url  | リンク先の URL  |
|  alt  | ALT 属性のテキスト |
|  language  | 言語 ( 現状 ja or en )  |
|  admin_url  | true の場合管理画面の url に変換されます。<br>その際は link_url には URL の ```/wp-admin/``` までを削除した<br> ```theme-install.php?search=lightning``` <br>のような部分を入力する必要があります。 |
|  include  | このプラグインの機能を内包するテーマ・プラグインの slug をカンマで区切って記述  |

例：リンク先を公式サイトにする場合

```
	{
		"type": "theme",
		"slug": "lightning/style.css",
		"image_file": "lightning_bnr_ja.jpg",
		"link_url": "https://lightning.nagoya/ja/?rel=vkadmin",
		"alt": "Lightning",
		"language": "ja",
		"admin_url": false
	},
```

例：リンク先をテーマの検索結果にする場合

```
	{
		"type": "theme",
		"slug": "lightning/style.css",
		"image_file": "lightning_bnr_ja.jpg",
		"link_url": "theme-install.php?search=lightning",
		"alt": "Lightning",
		"language": "ja",
		"admin_url": true
	},
```

### プラグインを追加する場合

|  属性名 | 説明 |
| --- | --- |
|  type  | plugin  |
|  slug  | 【プラグインのディレクトリ名】/【プラグイン本体のファイル名】   |
|  image_file  | バナーのファイル名  |
|  link_url  | リンク先の URL  |
|  alt  | ALT 属性のテキスト |
|  language  | 言語 ( 現状 ja or en )  |
|  admin_url  | true の場合管理画面の url に変換されます。<br>その際は link_url には URL の ```/wp-admin/``` までを削除した<br> ```plugin-install.php?s=vk+all+in+one+expansion+unit&tab=search&type=term``` <br>のような部分を入力する必要があります。 |
|  include  | このプラグインの機能を内包するテーマ・プラグインの slug をカンマで区切って記述  |
|  active_theme  | テーマが有効なときのみ表示したい項目のテーマ名 （半角小文字の英数字） |


例：リンク先を公式サイトにする場合

```
	{
		"type": "plugin",
		"slug": "vk-all-in-one-expansion-unit/vkExUnit.php",
		"image_file": "ExUnit_bnr.png",
		"link_url": "https://ex-unit.nagoya/ja/?rel=vkadmin",
		"alt": "VK All in One Expansion Unit",
		"language": "ja",
		"admin_url": false,
	},
```

例：リンク先をプラグインの検索結果にする場合

```
	{
		"type": "plugin",
		"slug": "vk-all-in-one-expansion-unit/vkExUnit.php",
		"image_file": "ExUnit_bnr.png",
		"link_url": "plugin-install.php?s=vk+all+in+one+expansion+unit&tab=search&type=term",
		"alt": "VK All in One Expansion Unit",
		"language": "ja",
		"admin_url": true,
	},
```

## ロゴ画像について

images フォルダのロゴ画像は、vk-admin（各プラグイン・テーマに同梱されている管理画面の共通部品）がダッシュボードのウィジェットと設定画面に表示している Vektor,Inc. のロゴです。
vk-admin は GitHub の URL（raw.githubusercontent.com の main）でファイル名を直接指定して読み込んでいます。

|  ファイル名 | 説明 |
| --- | --- |
|  vektor_logo-2026.png  | 現在のロゴ（2026 年のロゴ）  |
|  vektor_logo-2020.png  | 旧ロゴ。更新していない古いバージョンの製品が今も参照しています。  |

1. ロゴを更新するときは、既存のファイルを差し替えず、新しいファイル名（`vektor_logo-<年>.png`）で追加します。
1. 追加した画像を、このリポジトリの main にマージします。vk-admin は main のファイルを読み込むため、マージされるまで新しい画像は読み込めません。
1. vk-admin 側の参照先を、追加した新しいファイル名に変更します。この変更は、手順 2 の画像が main に入ってからマージしてください。順序が逆だと、その間は管理画面のロゴが表示されません。
1. 古いファイルは、それを参照している古いバージョンの製品があるため、変更・削除しないでください。
1. 画像は、幅 300px（表示幅 150px の 2 倍）・背景透明の PNG にします。
