### Azure Container Instancse
	Dcokerベースのコンテナを簡単かつ高速に構築することができる、フルマネージドなDockerサービス。
### Azure Container Service
	コンテナーのオーケストレーション
### HTTPS
	独自ドメインではなく *.azurewebsites.net で構わない場合は元々用意されているワイルドカード証明書を使う。
* [Let's Encrypt](https://letsencrypt.jp/)
* [Azure Web Apps に Let's Encrypt を使って簡単に SSL を導入する](https://m2wasabi.hatenablog.com/entry/2017/02/07/100000)
### テキスト読み上げ(Python)
* クラウド東北きりたん
### 画像認識API
* Computer Vision
	https://azure.microsoft.com/ja-jp/services/cognitive-services/computer-vision/

### Docker Compose
* [qiita](https://qiita.com/zembutsu/items/9e9d80e05e36e882caaa)

docker run -d -p 28939:80 --name moodle_0 -e WEBSITES_ENABLE_APP_SERVICE_STORAGE=false -e WEBSITE_SITE_NAME=moodle -e WEBSITE_AUTH_ENABLED=False -e PORT=80 -e WEBSITE_ROLE_INSTANCE_ID=0 -e WEBSITE_INSTANCE_ID=3916373d45caa6ffedc64207efc38e9026ce64d967b5e3e43b9c7e27102c584d jauer/moodle

<publishData>
  <publishProfile profileName="moodle - Web Deploy" publishMethod="MSDeploy" publishUrl="moodle.scm.azurewebsites.net:443" msdeploySite="moodle" userName="$moodle" userPWD="NwK3WeeGYdyGiPK8uu7aGPMwXXkxFqtkWsz7JychGzKLuef0n7JYH6aDPdRW" destinationAppUrl="http://moodle.azurewebsites.net" SQLServerDBConnectionString="" mySQLDBConnectionString="Database=mysqldatabase32431;Data Source=moodle-mysqldbserver.mysql.database.azure.com;User Id=mysqldbuser@moodle-mysqldbserver;Password=p@ssw0rd" hostingProviderForumLink="" controlPanelLink="http://windows.azure.com" webSystem="WebSites">
    <databases>
      <add name="defaultConnection" connectionString="Database=mysqldatabase32431;Data Source=moodle-mysqldbserver.mysql.database.azure.com;User Id=mysqldbuser@moodle-mysqldbserver;Password=p@ssw0rd" providerName="MySql.Data.MySqlClient" type="MySql" />
    </databases>
  </publishProfile>
  <publishProfile profileName="moodle - FTP" publishMethod="FTP" publishUrl="ftp://waws-prod-dm1-123.ftp.azurewebsites.windows.net/site/wwwroot" ftpPassiveMode="True" userName="moodle\$moodle" userPWD="NwK3WeeGYdyGiPK8uu7aGPMwXXkxFqtkWsz7JychGzKLuef0n7JYH6aDPdRW" destinationAppUrl="http://moodle.azurewebsites.net" SQLServerDBConnectionString="" mySQLDBConnectionString="Database=mysqldatabase32431;Data Source=moodle-mysqldbserver.mysql.database.azure.com;User Id=mysqldbuser@moodle-mysqldbserver;Password=p@ssw0rd" hostingProviderForumLink="" controlPanelLink="http://windows.azure.com" webSystem="WebSites">
    <databases>
      <add name="defaultConnection" connectionString="Database=mysqldatabase32431;Data Source=moodle-mysqldbserver.mysql.database.azure.com;User Id=mysqldbuser@moodle-mysqldbserver;Password=p@ssw0rd" providerName="MySql.Data.MySqlClient" type="MySql" />
    </databases>
  </publishProfile>
</publishData>

$con=mysqli_init(); mysqli_ssl_set($con, NULL, NULL, {ca-cert filename}, NULL, NULL); mysqli_real_connect($con, "moodle-mysqldbserver.mysql.database.azure.com", "mysqldbuser@moodle-mysqldbserver", {your_password}, {your_database}, 3306);


docker run -d --name DB -p 3306:3306 -e MYSQL_DATABASE=moodle -e MYSQL_USER=moodle -e MYSQL_PASSWORD=moodle centurylink/mysql

