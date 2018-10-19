..  _api_guide_detection:

图像检测
#########

PaddlePaddle Fluid在图像检测过程中实现了多个特有的操作。
这些操作仅在某些模型中存在，因此将此类api统一存在 detection_ 中。以下分模型介绍各个api：

.. _detection: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-197-detection

SSD
----------------
* Prior Box：根据不同参数为每个输入位置生成一系列候选框

API Reference 请参考 api_fluid_detection_prior_box_

.. _api_fluid_detection_prior_box: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-198-prior_box

* multi_box_head ：得到不同prior box的位置和置信度

API Reference 请参考 api_fluid_detection_multi_box_head_

.. _api_fluid_detection_multi_box_head: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-199-multi_box_head

* detection_output：对prioir box解码，通过多分类NMS得到检测结果

API Reference 请参考 api_fluid_detection_output_

.. _api_fluid_detection_output: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-202-detection_output

* ssd_loss：通过位置偏移预测值，置信度，检测框位置和真实框位置和标签计算损失

API Reference 请参考 api_fluid_detection_ssd_loss_

.. _api_fluid_detection_ssd_loss: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-203-ssd_loss

* detection map: 利用mAP评估SSD网络模型

API Reference 请参考 api_fluid_detection_detection_map_

.. _api_fluid_detection_detection_map: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-204-detection_map



Faster RCNN
-------------
* rpn_target_assign：通过anchor和真实框为anchor分配RPN网络的分类和回归目标值

API Reference 请参考 api_fluid_detection_rpn_target_assign_

.. _api_fluid_detection_rpn_target_assign: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-205-rpn_target_assign

* anchor_generator：为每个位置生成一系列anchor

API Reference 请参考 api_fluid_detection_anchor_generator_

.. _api_fluid_detection_anchor_generator: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-206-anchor_generator

* generate_proposal_labels: 通过generate_proposals得到的候选框和真实框得到RCNN部分的分类和回归的目标值

API Reference 请参考 api_fluid_detection_generate_proposal_labels_

.. _api_fluid_detection_generate_proposal_labels: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-208-generate_proposal_labels

* generate_proposals: 对RPN网络输出box解码并筛选得到新的候选框

API Reference 请参考 api_fluid_detection_generate_proposals_

.. _api_fluid_detection_generate_proposals: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-209-generate_proposals


OCR
---------
* roi_perspective_transform：对输入roi做透视变换

API Reference 请参考 api_fluid_detection_roi_perspective_transform_

.. _api_fluid_detection_roi_perspective_transform: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-207-roi_perspective_transform

* polygon_box_transform：对不规则检测框进行坐标变换

API Reference 请参考 api_fluid_detection_polygon_box_transform_

.. _api_fluid_detection_polygon_box_transform: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-212-polygon_box_transform


通用操作
-------------

图像检测中的一些通用操作：

* bipartite_match： 通过贪心二分匹配算法得到每一列中距离最大的一行

API Reference 请参考 api_fluid_detection_bipartite_match_

.. _api_fluid_detection_bipartite_match: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-200-bipartite_match

* target_assign: 根据目标检测框和标签，分配分类和回归目标以及对应权重

API Reference 请参考 api_fluid_detection_target_assign_

.. _api_fluid_detection_target_assign: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-201-target_assign

* iou_similarity：计算两组框的IOU值

API Reference 请参考 api_fluid_detection_iou_similarity_

.. _api_fluid_detection_iou_similarity: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-210-iou_similarity

* box_coder：对检测框进行编码，解码

API Reference 请参考 api_fluid_detection_box_coder_

.. _api_fluid_detection_box_coder: http://www.paddlepaddle.org/documentation/api/zh/1.0/layers.html#permalink-211-box_coder

