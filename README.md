### Concourse構築
```
# 公式docker-compose.ymlからコンテナ起動
$ wget https://raw.githubusercontent.com/starkandwayne/concourse-tutorial/master/docker-compose.yml
$ docker-compose up -d

# ターゲット作成
$ fly --target tutorial login --concourse-url http://127.0.0.1:8080 -u admin -p admin
$ fly --target tutorial sync
```

### Pipelineセット
```
# cd_tutorial用Pipelineセット
$ fly -t tutorial set-pipeline -c cd_tutorial/pipeline.yml -p cd_tutorial
$ fly -t tutorial unpause-pipeline -p cd_tutorial

# (Job手動トリガー)
$ fly -t tutorial trigger-job -j cd_tutorial/commit
```
