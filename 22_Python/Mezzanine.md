# django
## Python と django
* [Python3.4 + Djangoで作るWebアプリケーション(Part.2 アプリ開発編)](https://qiita.com/taijijiji/items/343fb56ab94eee28c401)
## Visual Studio と django
* [Visual Studio 2017でdjango 2](https://qiita.com/tenomoto/items/7a76b17883ef25792057)
# Mezzanine 
### 導入方法
	以下のように、Pythonさえ入っていれば5コマンドで実際に動かすところまで行えます。
* pip install mezzanine
* mezzanine-project myproject
* cd myproject
* python manage.py createdb
* python manage.py runserver

### 日本語対応
	以下の２箇所を設定することで日本語で動くようになってます。
* LANGUAGE_CODE = "ja" #112行目辺りの LANGUAGE_CODE = "en"からjaに
* USE_I18N = True #130行目辺りのこれをfalseからtrueに

### 認証基盤連携

### PostgreSQLの利用