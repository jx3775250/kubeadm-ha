## Docker 切换为 containerd

### 约定

- Docker 切换为 containerd 指的是已有集群用的是 docker 作为运行时，现将运行时切换为 containerd。
- 切换时会清除 docker 的所有数据，包括 image、containers，networks，停止 docker 运行。

### Docker 切换为 containerd

- 修改 container_manager 变量值为 containerd

- 基本配置执行
  ```
  ansible-playbook -i example/hosts.m-master.ip.ini 31-docker-to-containerd.yml
  ```

- 高级配置执行
  ```
  ansible-playbook -i example/hosts.m-master.ip.ini -e @example/variables.yaml 31-docker-to-containerd.yml
  ```
  > 若 `example/hosts.m-master.ip.ini` 文件中与 `example/variables.yaml` 变量值冲突时， `example/variables.yaml` 文件中的变量值优先级最高。