# vk-banners
Banners of Vektor,Inc's Pruducts 

## バナーの追加方法

### テーマの場合
vk-theme-banners.json を編集します。

| slug | 【テーマのディレクトリ名】/style.css |
| image_file | バナーのファイル名 |
| link_url | リンク先の URL |
| alt| ALT 属性のテキスト|
| language | 言語 ( 現状 ja or en ) |
| admin_url | true の場合管理画面の url に変換されます。<br>
その際は link_url には ```theme-install.php?search=lightning```のように入力する必要があります。|

例：リンク先を公式サイトにする場合

```
	{
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
		"slug": "lightning/style.css",
		"image_file": "lightning_bnr_ja.jpg",
		"link_url": "theme-install.php?search=lightning",
		"alt": "Lightning",
		"language": "ja",
		"admin_url": true
	},
```

### プラグインの場合
vk-plugin-banners.json を編集します。

slug: 【プラグインのディレクトリ名】/【プラグイン本体のファイル名】  
image_file: バナーのファイル名  
link_url: リンク先の URL  
alt: ALT 属性のテキスト  
language: 言語 ( 現状 ja or en )  
admin_url: true の場合管理画面の url に変換されます。
その際は link_url には ```plugin-install.php?s=vk+all+in+one+expansion+unit&tab=search&type=term```のように入力する必要があります。

例：リンク先を公式サイトにする場合

```
	{
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
		"slug": "vk-all-in-one-expansion-unit/vkExUnit.php",
		"image_file": "ExUnit_bnr.png",
		"link_url": "plugin-install.php?s=vk+all+in+one+expansion+unit&tab=search&type=term",
		"alt": "VK All in One Expansion Unit",
		"language": "ja",
		"admin_url": true
	},
```

