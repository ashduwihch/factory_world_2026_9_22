# factory_world_2026.9.22

适用于 Gazebo Harmonic 的工厂仿真场景包，包含完整的 World 文件以及场景使用的模型、网格和纹理资源。

## 目录内容

```text
worlds/factory_world_2026.9.22.sdf   场景文件
models/                               场景所需模型
使用说明.txt                          中文使用说明
```

## 使用方法

先把模型目录加入 Gazebo 资源路径（请换成自己的实际路径）：

```bash
export GZ_SIM_RESOURCE_PATH="/实际路径/factory_world_2026.9.22_package/models:${GZ_SIM_RESOURCE_PATH}"
```

启动场景：

```bash
gz sim worlds/factory_world_2026.9.22.sdf
```

如需通过 PX4 启动 X500 MID-360，请在对应的 launch 文件中将 World 路径指向：

```text
worlds/factory_world_2026.9.22.sdf
```

MID-360 仿真需要提前安装并编译对应的 Gazebo Harmonic 插件。

## 版本记录

| 版本 | 日期 | 说明 |
| --- | --- | --- |
| v1.0.0 | 2026-10-12 | 首次发布，包含 `factory_world_2026.9.22.sdf` 及其所需模型资源。 |

