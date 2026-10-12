# Modular Pipe Combined 02

图三对应的组合顺序：

1. 左端弯管 `modular_pipe_assembly_04`，旋转 180°
2. 连接管 `modular_pipe_assembly_01`
3. 阀门 `modular_pipe_valve_01`，旋转 -90°
4. 直管 `modular_pipe_straight_segment_01`，旋转 -90°
5. 右端弯管 `modular_pipe_assembly_04`

每个部件均保存为独立 OBJ，并封装成独立嵌套 model；每个子模型内部有自己的 link、visual、collision 和 Label 插件。九个子模型同属一个静态父模型，因此仍作为一个组合模型插入和整体移动。

另外增加四个独立支架 `support_01` 至 `support_04`。支架来自 `modular_pipe_assembly_10`，统一旋转 90°，使横梁垂直于管道方向。横梁横向中心为 `Y=0`，与管道中心一致；横梁顶面和管道底面均为 `Z=1.2344 m`。

Label 插件放在各个嵌套 model 下，不再放在 visual 下，因此兼容 Gazebo Sim 8 / SDFormat 14 的正式模型插件位置。

对齐不是按包围盒完成的。阀门使用真实法兰端面 `Y=±0.662 m`，所有管口中心统一到 `Z=1.4344 m`。相邻端面在隐藏连接处重叠 5 mm，避免 Gazebo 渲染出白缝。

语义标签：管段 `10`、阀门 `20`、支架 `30`、弯管 `50`。同类部件可在 instance / panoptic 分割模式下按独立嵌套 model 区分实例。
