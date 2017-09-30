#【実行前に決めておく事】

ジョブ名を予め決めておいてください。

Ansible実行時のJenkins/インスペクタライブラリの
設定と同時にworkspace配下にジョブも作成されます。

ジョブ名は「Job名を指定して下さい。」と表示された
時に入力して下さい。

#【設定方法】
```
su -
yum install -y epel-release
yum install -y sshpass libselinux-python
yum install -y ansible
ansible --version

echo 127.0.0.1 >> /etc/ansible/hosts
```

#【実行方法】
```
cd server-jenkins-ansible
ansible-playbook main.yml --connection=local
```

#【レポートの出力先等を変更する場合】
Jenkinsからのビルド指示は一度phingに送られ
そこから各ライブラリが連動します。
プロジェクト直下の「build.xml」が設定ファイルになります。


==================================================================
ここらへんを参考にディレクトリ構造を組んでいただければと思います。
http://docs.ansible.com/ansible/playbooks_best_practices.html
