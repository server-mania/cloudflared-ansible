# cloudflared-ansible

cloudflare tunnel経由でhomelabへアクセスして  
ansibleでアップデートを自動化してみる。

接続パスワード、sudoパスワードはvaultを利用して取得する。  
（パスワードはvaultで30mごとに自動ローテーション）  

またansibleからvaultへのアクセスはuriモジュールを利用する。  
（本当はvault用のモジュールを利用したかったが  
cloudflare access用のヘッダー認証を行うことが出来ないことが判明したのと  
30mごとにローテーションされるパスワードであるためリスクは低いと判断してuriモジュールを利用）  

パブリック公開することで制限が緩くなるgithub actionsを活用する。  