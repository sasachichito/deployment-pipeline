### Concourse構築
公式チュートリアルに従う
https://concoursetutorial.com/

### Pipelineセット
```
# cd_tutorial用
$ fly -t tutorial set-pipeline -c cd_tutorial/pipeline.yml -p cd_tutorial
$ fly -t tutorial unpause-pipeline -p cd_tutorial
```

### Pipeline削除
```
$ fly -t tutorial destroy-pipeline -p cd_tutorial
```

### Job手動トリガー例
```
$ fly -t tutorial trigger-job -j cd_tutorial/commit
```
