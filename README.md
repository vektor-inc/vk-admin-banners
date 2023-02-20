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
|  expansion-for  |  何かのアドオンに該当する場合はその「何か」|

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


例：リンク先を公式サイトにする場合

```
	{
		"type": "plugin",
		"slug": "vk-all-in-one-expansion-unit/vkExUnit.php",
		"image_file": "ExUnit_bnr.png",
		"link_url": "https://ex-unit.nagoya/ja/?rel=vkadmin",
		"alt": "VK All in One Expansion Unit",
		"language": "ja",
		"admin_url": false
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
		"admin_url": true
	},
```

